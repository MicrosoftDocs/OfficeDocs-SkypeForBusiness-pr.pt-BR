---
title: 'Lync Server 2013: Restaurando conteúdos de conferência usando o Serviço de Backup'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Restoring conference contents using the Backup Service
ms:assetid: 3e0f18ec-7319-4c07-a59b-2938e7787bc9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688030(v=OCS.15)
ms:contentKeyID: 49733620
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 14ee33f24f7b1a58812db146901695cba1ae05f2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34822941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="restoring-conference-contents-using-the-backup-service-in-lync-server-2013"></a>Restaurando conteúdos de conferência usando o Serviço de Backup no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-01_

Se as informações de conferência armazenadas no repositório de arquivos de um pool de front-ends ficarem indisponíveis. Você deve restaurar essas informações para que os usuários hospedados no pool mantenham seus dados de conferência. Se o pool de front-ends que perdeu dados de conferências estiver emparelhado com outro pool de front-end, você pode usar o serviço de backup para restaurar os dados.

Você também deve realizar essa tarefa se um pool inteiro tiver falhado e tiver que fazer failover de seus usuários para um pool de backup. Quando esses usuários falham novamente em seu pool original, você deve usar esse procedimento para copiar o conteúdo de conferência de volta para o pool original também.

Suponha que o Pool1 está emparelhado com Pool2, e os dados de conferência no Pool1 são perdidos. Você pode usar o cmdlet a seguir para invocar o serviço de backup para restaurar o conteúdo:

    Invoke-CsBackupServiceSync -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

A restauração do conteúdo da conferência pode levar algum tempo, dependendo do tamanho. Você pode usar o cmdlet a seguir para verificar o status do processo:

    Get-CsBackupServiceStatus -PoolFqdn <Pool2 FQDN> -BackupModule ConfServices.DataConf

O processo é feito quando esse cmdlet retorna um valor de estado Steady para o módulo de conferência de dados.

</div>

<span> </span>

</div>

</div>

</div>

