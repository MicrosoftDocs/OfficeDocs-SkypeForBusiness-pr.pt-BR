---
title: Configurando e monitorando o Serviço de Backup
ms.reviewer: ''
author: lanachin
ms.author: v-lanac
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Você pode usar os comandos do Shell de gerenciamento do Skype for Business Server para configurar e monitorar o serviço de backup.
ms.openlocfilehash: 2170f58fcc60a648788934048f3d0e6bbfac9c77
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303902"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Configurando e monitorando o serviço de backup no Skype for Business Server

Você pode usar os seguintes comandos do Shell de gerenciamento do Skype for Business Server para configurar e monitorar o serviço de backup. Para restaurar as informações de conferência armazenadas no repositório de arquivos de um pool de front-end, consulte [restaurar conteúdo da conferência usando o serviço de backup](#restore-conference-contents-using-the-backup-service)abaixo.

> [!NOTE]  
> O grupo RTCUniversalServerAdmins é o único grupo que tem permissões para executar **Get-CsBackupServiceStatus** por padrão. Para usar esse cmdlet, faça logon como membro desse grupo. Ou você pode conceder acesso a esse comando para outros grupos (por exemplo, CSAdministrator) usando o cmdlet **set-CsBackupServiceConfiguration** .

## <a name="to-see-the-backup-service-configuration"></a>Para ver a configuração do serviço de backup

Execute o seguinte cmdlet:

    Get-CsBackupServiceConfiguration

O padrão para SyncInterval é de dois minutos.

## <a name="to-set-the-backup-service-sync-interval"></a>Para definir o intervalo de sincronização do serviço de backup

Execute o seguinte cmdlet:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Por exemplo, o seguinte define o intervalo como três minutos.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Embora você possa usar esse cmdlet para alterar o intervalo de sincronização padrão do serviço de backup, não deve fazê-lo, a menos que seja absolutamente necessário, pois o intervalo de sincronização tem um grande impacto sobre o desempenho do serviço de backup e o RPO (objetivo do ponto de recuperação).

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Para obter o status do serviço de backup para um determinado pool

Execute o seguinte cmdlet:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

> [!NOTE]  
> O status de sincronização do serviço de backup é definido unidirecionalmente de um pool (P1) para seu pool de backup (P2). O status de sincronização de P1 a P2 pode ser diferente do do P2 para P1. Para P1 a P2, o serviço de backup está em um estado "estacionário" se todas as alterações feitas em P1 são completamente duplicadas para P2 dentro do intervalo de sincronização. Ele está no estado "final" se não houver mais alterações a serem sincronizadas do P1 ao P2. Os dois Estados indicam um instantâneo do serviço de backup no momento em que o cmdlet é executado. Isso não significa que o estado retornado permanecerá como mais tarde. Em particular, o estado "final" continuará a ser suspenso apenas se P1 não gerar nenhuma alteração após a execução do cmdlet. Isso é verdade no caso de falha P1 para P2 após o P1 ser colocado no modo somente leitura como parte da lógica de execução **Invoke-CsPoolfailover** .

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Para obter informações sobre a relação de backup para um determinado pool

Execute o seguinte cmdlet:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>Para forçar uma sincronização do serviço de backup

Execute o seguinte cmdlet:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Restaurar o conteúdo da conferência usando o serviço de backup 

Se as informações de conferência armazenadas no repositório de arquivos de um pool de front-ends ficar indisponíveis, você deverá restaurar essas informações para que os usuários hospedados no pool mantenham seus dados de conferência. Se o pool de front-ends que perdeu dados de conferências estiver emparelhado com outro pool de front-end, você pode usar o serviço de backup para restaurar os dados.

Você também deve realizar essa tarefa se um pool inteiro tiver falhado e tiver que fazer failover de seus usuários para um pool de backup. Quando esses usuários falham novamente em seu pool original, você deve usar esse procedimento para copiar o conteúdo de conferência de volta para o pool original também.

Suponha que o Pool1 está emparelhado com Pool2, e os dados de conferência no Pool1 são perdidos. Você pode usar o cmdlet a seguir para invocar o serviço de backup para restaurar o conteúdo:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

A restauração do conteúdo da conferência pode levar algum tempo, dependendo do tamanho. Você pode usar o cmdlet a seguir para verificar o status do processo:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

O processo é feito quando esse cmdlet retorna um valor de estado Steady para o módulo de conferência de dados.
