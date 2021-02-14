---
title: Fazer o back up de dados de RGS (Serviço de Grupo de Resposta) no Skype for Business Server 2019
ms.reviewer: rogupta
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.date: 07/22/2019
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
description: Saiba como fazer o back up de dados RGS (Serviço de Grupo de Resposta) no Skype for Business Server 2019.
ms.openlocfilehash: f9c62953dcb859be2aa34bdee84ca76e3303d738
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824065"
---
# <a name="back-up-response-group-service-rgs-data"></a>Fazer o back up de dados do Serviço de Grupo de Resposta (RGS)

Com a atualização cumulativa de julho de 2019 do Skype for Business Server, incluímos a capacidade de incluir dados RGS como parte do backup padrão.

## <a name="rgs-data-replication"></a>Replicação de dados RGS

Para experimentar a funcionalidade de replicação de dados RGS, siga as etapas abaixo:

1. Instale a atualização cumulativa de julho em todos os front-ends (FEs) do seu pool emparelhado.
1. Instale o banco de dados RGS em ambos os membros do pool emparelhado:
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool1 BackendDatabase FQDN>`
    - `Install-CsDatabase -ConfiguredDatabases -SqlServerFqdn <Pool2 BackendDatabase FQDN>`
1. Execute o seguinte cmdlet em ambos os pools para replicar dados RGS existentes para as tabelas de backup para que os dados possam ser coletados pelo RGSBackupService:
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool1 FQDN>`
    - `Invoke-CsRGSStoreReplicateData -PoolFqdn <Pool2 FQDN>`
1. Habilitar RGSBackupService (isso habilita o RGSBackupService globalmente. Se esse parâmetro for definido como true, o RGSBackupService começará a sincronizar dados RGS em pools emparelhados (ambos os pools precisam ser CU1). Aguarde alguns minutos para começar. Inicialmente, o status do RGS BackupService será NotInitialized.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 1`
1. Para verificar BackupServiceStatus:
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
1. Para verificar DataReplication entre pools, use esses cmdlets (esses cmdlets mostram apenas os dados do pool do proprietário):
    - `Get-csRGSWorkflow`
    - `Get-csRGSQueue`
    - `Get-csRGSAgentGroup`
    - `Get-csRGSHourOfBusiness`
    - `Get-csRGSHolidaySet`
1. Para verificar os dados RGS do pool do Proprietário e seus dados de backup:
    - `Get-csRGSWorkflow -showAll`
    - `Get-csRGSQueue  -showAll`
    - `Get-csRGSAgentGroup -showAll`
    - `Get-csRGSHourOfBusiness -showAll`
    - `Get-csRGSHolidaySet -showAll`
1. Verifique a funcionalidade do fluxo de trabalho fazendo uma chamada de áudio para o Fluxo de Trabalho.
1. Failover do seu pool de Proprietários RGS.
1. Verifique a funcionalidade do fluxo de trabalho fazendo uma chamada de áudio para o Fluxo de Trabalho.
1. Failback do pool.
1. Atualize os dados RGS no pool de origem e execute outro failover para verificar se as alterações são refletidas no pool de backup. O RGS deve se comportar da mesma forma que estava se comportando antes do failover.

> [!TIP]
> É recomendável que você execute essas etapas em uma grande parte dos dados e faça failover e failbacks frequentes. Qualquer novo RGS criado após essa atualização cu também deve ser replicado.

## <a name="rgs-cmdlets"></a>Cmdlets RGS

- Para verificar BackupServiceStatus (o status de exportação deve estar no estado Final ou Estável. O status de importação deve estar no estado Normal. RGSBackupservice deve estar habilitado.):
    - `Get-CsBackupServiceStatus -Category RGS -PoolFqdn <Pool1 FQDN>`
- Para sincronizar totalmente os dados RGS no pool de backup (isso sincroniza os dados RGS completos no pool de backup).):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSDataStore`
- Para sincronizar totalmente o repositório de arquivos RGS no pool de backup (isso sincroniza os dados RGS completos no pool de backup).):
    - `Invoke-CsBackupServiceSync -PoolFqdn <Pool1 FQDN> -BackupModule ApplicationServer.RGSFileStore`
- Para sincronizar dados delta RGS no pool de backup (isso sincroniza os dados delta no pool de backup somente para RGS).):
    - `Backup-CsPool -PoolFqdn <Pool FQDN> -Category RGS`
- Para sincronizar todos os dados do módulo, incluindo RGS:
    - `Backup-CsPool -PoolFqdn <Pool FQDN>`
- Para desabilitar o RGSBackupService (isso desabilitará globalmente o RGSBackupService. Se esse parâmetro for definido como true , RGSBackupService será desabilitado em todos os pools emparelhados.):
    - `Set-CsBackupServiceConfiguration -EnableRgsBackupService 0`
