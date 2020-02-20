---
title: 'Lync Server 2013: Gerenciando nós do Inspetor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing watcher nodes
ms:assetid: 66deaf49-a71f-4a6e-ada0-ea8b688ee921
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688078(v=OCS.15)
ms:contentKeyID: 49733674
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c6422754da81aa17d6a746f6539258b3f6ae0d2c
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Gerenciando nós do Inspetor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

Além de modificar as transações sintéticas que são executadas em um nó do Inspetor, os administradores também podem usar o cmdlet **set-CsWatcherNodeConfiguration** para executar duas outras tarefas importantes: habilitar e desabilitar o nó do Inspetor e configurar o nó do inspetor para usar URLs internas ou externas ao executar seus testes.

Por padrão, os nós do Inspetor foram projetados para executar periodicamente todas as suas transações sintéticas habilitadas. Às vezes, no entanto, talvez seja necessário suspender essas transações. Por exemplo, se o nó do Inspetor estiver desconectado temporariamente da rede, não haverá motivo para executar as transações sintéticas. Sem conectividade de rede, essas transações são garantidas de falhar. Se você quiser desabilitar temporariamente um nó do Inspetor, execute um comando semelhante a este no Shell de gerenciamento do Lync Server:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Este comando desabilitará a execução de transações sintéticas no nó do Inspetor ATL-001.litwareinc.com. Para retomar a execução das transações sintéticas, defina a propriedade Enabled de volta como true ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> A propriedade Enabled pode ser usada para ativar ou desativar os nós do Inspetor. Se você quiser excluir permanentemente um nó do Inspetor, use o cmdlet <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> :<BR>Remove-CsWatcherNodeConfiguration – Identity "atl-watcher-001.litwareinc.com"<BR>Esse comando Remove todas as definições de configuração do nó do observador do computador especificado, o que impede que o computador execute transações sintéticas automaticamente. No entanto, o comando não desinstala os arquivos do agente do System Center ou os arquivos de sistema do Lync Server 2013.



</div>

Por padrão, os nós do Inspetor usam as URLs externas de uma organização ao conduzir seus testes. No entanto, os nós do Inspetor também podem ser configurados para usar as URLs internas da organização. Isso permite que os administradores verifiquem o acesso à URL para usuários localizados dentro da rede de perímetro. Para configurar um nó do inspetor para usar URLs internas em vez de URLs externas, defina a propriedade UseInternalWebUrls como true ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Se você redefinir essa propriedade para o valor padrão false ($False), o Inspetor usará as URLs externas:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

