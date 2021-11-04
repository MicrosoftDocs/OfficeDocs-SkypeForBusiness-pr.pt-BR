---
title: Configurando e monitorando o Serviço de Backup
ms.reviewer: ''
author: cichur
ms.author: v-mahoffman
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
description: Você pode usar Skype for Business Server do Shell de Gerenciamento para configurar e monitorar o Serviço de Backup.
ms.openlocfilehash: f50f8ab13c2013505beace71f7e35cbc7674777c
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60747039"
---
# <a name="configuring-and-monitoring-the-backup-service-in-skype-for-business-server"></a>Configurando e monitorando o Serviço de Backup Skype for Business Server

Você pode usar os seguintes comandos Skype for Business Server Shell de Gerenciamento para configurar e monitorar o Serviço de Backup. Para restaurar informações de conferência armazenadas no armazenamento de arquivos de um pool de Front-End, consulte [Restore conference contents using the Backup Service](#restore-conference-contents-using-the-backup-service), below.

> [!NOTE]  
> O grupo RTCUniversalServerAdmins é o único grupo que possui permissões para executar o **Get-CsBackupServiceStatus** por padrão. Para usar este cmdlet, faça o login como membro deste grupo. Em alternativa, é possível conceder acesso a este comando para outros grupos (por exemplo, CSAdministrator) usando o cmdlet **Set-CsBackupServiceConfiguration**.

## <a name="to-see-the-backup-service-configuration"></a>Para ver a configuração do Serviço de Backup

Execute o seguinte cmdlet:<br/><br/>Get-CsBackupServiceConfiguration

O padrão para SyncInterval é dois minutos.

## <a name="to-set-the-backup-service-sync-interval"></a>Para definir o intervalo de sincronização do Serviço de Backup

Execute o seguinte cmdlet:<br/><br/>Set-CsBackupServiceConfiguration intervalo -SyncInterval

Por exemplo, o seguinte define o intervalo para três minutos.<br/><br/>Set-CsBackupServiceConfiguration -SyncInterval 00:03:00


> [!IMPORTANT]  
> Embora seja possível usar este cmdlet para alterar o intervalo de sincronização padrão para o Serviço de Backup, você não deve fazer menos do que o absolutamente necessário, pois o intervalo de sincronização possui um grande impacto no desempenho do Serviço de Backup e o objetivo de ponto de recuperação (RPO).

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Para obter o status do Serviço de Backup para um determinado pool

Execute o seguinte cmdlet:<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<pool-FQDN>

> [!NOTE]  
> O status de sincronização do Serviço de Backup é definido unidirecionalmente de um pool (P1) para seu pool de backup (P2). O status de sincronização de P1 para P2 pode ser diferente do que de P2 para P1. Para P1 para P2, o Serviço de Backup está em estado "pronto" se todas as alterações realizadas em P1 são completamente replicadas para P2 dentro do intervalo de sincronização. Está no estado “final” se não há mais mudanças a serem sincronizadas de P1 para P2. Ambos os estados indicam um instantâneo do Serviço de Backup no momento que o cmdlet é executado. Não implica que o estado retornado permanecerá como é posteriormente. Em particular, o estado “final” continuará a manter apenas se P1 não gerar qualquer mudança após o cmdlet ser executado. Isto é verdadeiro em caso de falha de P1 por P2 após P1 ser inserido no modo somente leitura como parte da lógica de execução do **Invoke-CsPoolfailover**.

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Para obter informações sobre a relação de backup de um determinado pool

Execute o seguinte cmdlet:<br/><br/>Get-CsPoolBackupRelationship -PoolFQDN \<poolFQDN>

## <a name="to-force-a-backup-service-sync"></a>Para forçar uma sincronização do Serviço de Backup

Execute o seguinte cmdlet:<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<poolFqdn> [-BackupModule {All| PresenceFocus| DataConf| CMSMaster}]

## <a name="restore-conference-contents-using-the-backup-service"></a>Restaurar o conteúdo da conferência usando o Serviço de Backup 

Se as informações de conferência armazenadas no armazenamento de arquivos de um pool de Front-End ficar indisponíveis, você deverá restaurar essas informações para que os usuários que estão no pool mantenham seus dados de conferência. Se o pool de Front-End que perdeu dados de conferência estiver emparelhado com outro pool de Front-End, você poderá usar o Serviço de Backup para restaurar os dados.

Você também deve efetuar tal tarefa caso todo um pool falhe e você tenha que executar failover nos usuários para um pool de backup. Quando esses usuários retornarem para o pool original, você deve utilizar este procedimento para copiar o conteúdo de conferência de volta para o pool original.

Presuma que o Pool1 está pareado com Pool2, e os dados de conferência de Pool1 foram perdidos. Você pode usar o seguinte cmdlet para invocar o Serviço de Backup para restaurar o conteúdo:<br/><br/>Invoke-CsBackupServiceSync -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

Restaurar o conteúdo pode levar algum tempo, dependendo do tamanho. Você pode utilizar o seguinte cmdlet para verificar o status do processo:<br/><br/>Get-CsBackupServiceStatus -PoolFqdn \<Pool2 FQDN> -BackupModule ConfServices.DataConf

O processo é concluído quando este cmdlet retorna um valor de Estado Estável para o módulo de conferência de dados.
