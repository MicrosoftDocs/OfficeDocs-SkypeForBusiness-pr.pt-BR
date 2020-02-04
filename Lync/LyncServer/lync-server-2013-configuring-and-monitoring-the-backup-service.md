---
title: 'Lync Server 2013: Configurando e monitorando o Serviço de Backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring and monitoring the Backup Service
ms:assetid: c608280e-a7d1-4ae0-a75c-da6b524752fa
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205252(v=OCS.15)
ms:contentKeyID: 48185365
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9992f0466ceb2e01fa54cb2b2d511eeb96af755a
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41726531"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-and-monitoring-the-backup-service-in-lync-server-2013"></a>Configurando e monitorando o Serviço de Backup no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Você pode usar os seguintes comandos do Shell de gerenciamento do Lync Server para configurar e monitorar o serviço de backup.

<div>


> [!NOTE]  
> O grupo RTCUniversalServerAdmins é o único grupo que tem permissões para executar <STRONG>Get-CsBackupServiceStatus</STRONG> por padrão. Para usar esse cmdlet, faça logon como membro desse grupo. Ou você pode conceder acesso a esse comando para outros grupos (por exemplo, CSAdministrator) usando o cmdlet <STRONG>set-CsBackupServiceConfiguration</STRONG> .



</div>

<div>

## <a name="to-see-the-backup-service-configuration"></a>Para ver a configuração do serviço de backup

Execute o seguinte cmdlet:

    Get-CsBackupServiceConfiguration

O padrão para SyncInterval é de dois minutos.

</div>

<div>

## <a name="to-set-the-backup-service-sync-interval"></a>Para definir o intervalo de sincronização do serviço de backup

Execute o seguinte cmdlet:

    Set-CsBackupServiceConfiguration -SyncInterval interval

Por exemplo, o seguinte define o intervalo como três minutos.

    Set-CsBackupServiceConfiguration -SyncInterval 00:03:00

<div>


> [!IMPORTANT]  
> Embora você possa usar esse cmdlet para alterar o intervalo de sincronização padrão do serviço de backup, não deve fazê-lo, a menos que seja absolutamente necessário, pois o intervalo de sincronização tem um grande impacto sobre o desempenho do serviço de backup e o RPO (objetivo do ponto de recuperação).



</div>

</div>

<div>

## <a name="to-get-the-backup-service-status-for-a-particular-pool"></a>Para obter o status do serviço de backup para um determinado pool

Execute o seguinte cmdlet:

    Get-CsBackupServiceStatus -PoolFqdn <pool-FQDN>

<div>


> [!NOTE]  
> O status de sincronização do serviço de backup é definido unidirecionalmente de um pool (P1) para seu pool de backup (P2). O status de sincronização de P1 a P2 pode ser diferente do do P2 para P1. Para P1 a P2, o serviço de backup está em um estado "estacionário" se todas as alterações feitas em P1 são completamente duplicadas para P2 dentro do intervalo de sincronização. Ele está no estado "final" se não houver mais alterações a serem sincronizadas do P1 ao P2. Os dois Estados indicam um instantâneo do serviço de backup no momento em que o cmdlet é executado. Isso não significa que o estado retornado permanecerá como mais tarde. Em particular, o estado "final" continuará a ser suspenso apenas se P1 não gerar nenhuma alteração após a execução do cmdlet. Isso é verdade no caso de falha P1 para P2 após o P1 ser colocado no modo somente leitura como parte da lógica de execução <STRONG>Invoke-CsPoolfailover</STRONG> .



</div>

</div>

<div>

## <a name="to-get-information-about-the-backup-relationship-for-a-particular-pool"></a>Para obter informações sobre a relação de backup para um determinado pool

Execute o seguinte cmdlet:

    Get-CsPoolBackupRelationship -PoolFQDN <poolFQDN>

</div>

<div>

## <a name="to-force-a-backup-service-sync"></a>Para forçar uma sincronização do serviço de backup

Execute o seguinte cmdlet:

    Invoke-CsBackupServiceSync -PoolFqdn <poolFqdn> [-BackupModule  {All|PresenceFocus|DataConf|CMSMaster}]

</div>

</div>

<span> </span>

</div>

</div>

</div>

