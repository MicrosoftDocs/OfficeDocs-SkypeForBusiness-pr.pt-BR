---
title: Configurando e monitorando o Serviço de Backup
author: heidip
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode usar o Skype para comandos do Shell de gerenciamento do servidor de negócios para configurar e monitorar o serviço de Backup.
ms.openlocfilehash: f06da0cad4bf6a7deb5ab098530bfea548db21f9
ms.sourcegitcommit: 5576463b0295e48e0506f7e4b44006ffc0b38a95
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2018
ms.locfileid: "27222881"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Configurando e monitorando o serviço de Backup no Skype para Business Server

Você pode usar o seguinte Skype para comandos do Shell de gerenciamento do servidor de negócios para configurar e monitorar o serviço de Backup. Para restaurar informações de conferência armazenadas no repositório de arquivo de um pool de Front-End, consulte [restaurar conteúdo de conferência usando o serviço de Backup](#restore-conference-contents-using-the-backup-service), abaixo.

> [!NOTE]  
> Grupo RTCUniversalServerAdmins é o único grupo que tem permissões para executar **Get-CsBackupServiceStatus** por padrão. Para usar esse cmdlet, faça logon como um membro desse grupo. Ou então, você pode conceder acesso a esse comando a outros grupos (por exemplo, CSAdministrator) usando o cmdlet **Set-CsBackupServiceConfiguration** .

## <a name="to-see-the-backup-service-configuration"></a>Para ver a configuração do serviço de Backup

Execute o seguinte cmdlet:

    Get-CsBackupServiceConfiguration

O padrão para SyncInterval é dois minutos.

## <a name="to-set-the-backup-service-sync-interval"></a>Para definir o intervalo de sincronização do serviço de Backup

Execute o seguinte cmdlet:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Por exemplo, o exemplo a seguir define o intervalo para três minutos.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Embora você possa usar esse cmdlet para alterar o intervalo de sincronização padrão para o serviço de Backup, você não deve fazer para que a menos que seja absolutamente necessário, como a sincronização intervalo tem um grande impacto sobre o desempenho do serviço de Backup e o objetivo de ponto de recuperação (RPO).

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Para obter o status do serviço de Backup para um determinado pool

Execute o seguinte cmdlet:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> O status de sincronização do serviço de Backup é definido unidirectionally de um pool (P1) para seu pool de backup (P2). O status de sincronização de P1 para P2 pode ser diferente de P2 a P1. Para P1 para o P2, o serviço de Backup está em um estado "estável" se todas as alterações feitas em P1 são replicadas completamente via para P2 dentro do intervalo de sincronização. Não é no estado "final" se não houver nenhuma alteração mais sejam sincronizadas de P1 P2. Ambos os estados indicam um instantâneo do serviço de Backup no momento em que o cmdlet é executado. Ele não supõe que o estado retornado permanecerá como está posteriormente. Em particular, o estado "final" continuará mantenha apenas se P1 não gera quaisquer alterações depois que o cmdlet é executado. Isso acontece no caso de failover dos P1 P2 depois P1 é colocado no modo de somente leitura como parte da lógica de execução do **Invoke-CsPoolfailover** .

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Para obter informações sobre o relacionamento de backup para um determinado pool

Execute o seguinte cmdlet:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>Para forçar uma sincronização do serviço de Backup

Execute o seguinte cmdlet:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Restaurar conteúdo de conferência usando o serviço de Backup 

Se as informações de conferência armazenadas no repositório de arquivo de um pool de Front-End ficam indisponíveis, você deve restaurar essas informações para que os usuários hospedados no pool mantêm seus dados de conferência. Se o pool de Front-End que tem perda de dados de conferência é emparelhado com outro pool de Front-End, você pode usar o serviço de Backup para restaurar os dados.

Você também deve executar essa tarefa, se um pool inteiro falhar e você precisar realizar failover seus usuários para um pool de backup. Quando esses usuários são falhou volta para seu pool original, você deve usar este procedimento para copiar o conteúdo de sua conferências volta ao seu pool original também.

Suponha que Pool1 está emparelhado com o Pool2, e os dados de conferência no Pool1 são perdidos. Você pode usar o seguinte cmdlet para chamar o serviço de Backup para restaurar o conteúdo:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

Restaurar o conteúdo de conferência pode levar algum tempo, dependendo de seu tamanho. Você pode usar o seguinte cmdlet para verificar o status do processo:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

O processo é concluído quando este cmdlet retorna um valor de estado estável para o módulo de conferência de dados.