---
title: Backup de dados do serviço de grupo de resposta (RGS) no Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
description: Saiba como fazer backup de dados do serviço de grupo de resposta (RGS) no Skype for Business Server 2019.
ms.openlocfilehash: 0a37b4d4771a75513666597de5eb87dedcbcd0c7
ms.sourcegitcommit: 14700a4faab81a294ac794f25b26619a5ed242a5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/23/2019
ms.locfileid: "35821313"
---
# <a name="back-up-response-group-service-rgs-data"></a>Fazer backup de dados do serviço de grupo de resposta (RGS)

Com o Skype for Business Server 2019 atualização cumulativa de julho, incluímos a capacidade de incluir RGS dados como parte do backup padrão.

## <a name="rgs-data-replication"></a>A replicação de dados do RGS

Para experimentar a funcionalidade de replicação de dados do RGS, siga as etapas abaixo:

1. Instale a atualização cumulativa de julho em todas as front-ends (FEs) do seu pool emparelhado.
1. Instale o banco de dados do RGS em ambos os membros do pool emparelhado:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Execute o cmdlet a seguir nos dois pools para replicar os dados existentes do RGS para as tabelas de backup, de modo que os dados possam ser retirados por RGSBackupService:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Habilite o RGSBackupService (isso permitirá que o RGSBackupService globalmente. Se esse parâmetro for definido como true, o RGSBackupService começará a sincronizar os dados do RGS em pools emparelhados (os dois pools precisam ser CU1). Aguarde alguns minutos para começar. Inicialmente, RGS BackupService status será não inicializado.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. Para verificar o BackupServiceStatus:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Para verificar a replicação de dados entre pools, use esses cmdlets (estes cmdlets mostram somente dados do pool proprietário):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. Para verificar os dados do pool de proprietários RGS e seus dados de backup:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Verifique a funcionalidade do fluxo de trabalho fazendo uma chamada de áudio para o fluxo de trabalho.
1. Failover do pool de proprietários do RGS.
1. Verifique a funcionalidade do fluxo de trabalho fazendo uma chamada de áudio para o fluxo de trabalho.
1. Failback do pool.
1. Atualize RGS dados no pool de origem e execute outro failover para verificar se as alterações se refletem no pool de backup. RGS deve se comportar da mesma forma que era feita antes do failover.

> [!TIP]
> É recomendável executar essas etapas em uma grande quantidade de dados e fazer failover e failbacks frequentes. Qualquer novo RGS criado após essa atualização de RECOR também deve ser replicado.

## <a name="rgs-cmdlets"></a>Cmdlets RGS

- Para verificar BackupServiceStatus (o status de exportação deve estar no estado final ou Steady. O status da importação deve estar no estado normal. RGSBackupservice deve ser habilitado.):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Para sincronizar completamente os dados do pool de backup (isso sincronizará os dados completos do RGS no pool de backup.):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Para sincronizar completamente o repositório do RGS no pool de backup (isso irá sincronizar os dados completos dos RGS no pool de backup.):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- Para sincronizar os dados Delta do RGS no pool de backup (isso sincronizará os dados Delta no pool de backup somente para RGS.):
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- Para sincronizar todos os dados do módulo, incluindo RGS:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- Para desabilitar o RGSBackupService (isso irá desabilitar o RGSBackupService globalmente. Se esse parâmetro for definido como true, o RGSBackupService será desabilitado em todos os pools emparelhados.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
