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
ms.openlocfilehash: 27d2afd025897df4f9b98e235d408a264d2cceb2
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41724001"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-watcher-nodes-in-lync-server-2013"></a>Gerenciando nós de Inspetor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

Além de modificar as transações sintéticas que são executadas em um nó de Inspetor, os administradores também podem usar o cmdlet **set-CsWatcherNodeConfiguration** para executar duas outras tarefas importantes: habilitar e desabilitar o nó do Inspetor e configurar o nó do inspetor para usar URLs internas ou URLs externas ao executar seus testes.

Por padrão, os nós do inspetor são projetados para executar periodicamente todas as transações sintéticas habilitadas. Às vezes, no entanto, talvez seja necessário suspender essas transações. Por exemplo, se o nó do inspetor estiver temporariamente desconectado da rede, não há motivo para executar as transações sintéticas. Sem conectividade de rede, a garantia dessas transações falha. Se você quiser desativar temporariamente um nó do Inspetor, execute um comando semelhante a este do Shell de gerenciamento do Lync Server:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $False

Esse comando desabilitará a execução de transações sintéticas no nó Inspetor-Inspetor-001.litwareinc.com. Para retomar a execução das transações sintéticas, defina a propriedade Enabled novamente como True ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -Enabled $True

<div>


> [!NOTE]  
> A propriedade Enabled pode ser usada para habilitar e desabilitar os nós do inspetor. Se você desejar excluir permanentemente um nó do inspetor, use o cmdlet <STRONG>Remove-CsWatcherNodeConfiguration</STRONG> :<BR>Remove-CsWatcherNodeConfiguration – Identity "atl-watcher-001.litwareinc.com"<BR>Esse comando Remove todas as configurações do nó do Inspetor do computador especificado, o que impede que o computador execute automaticamente transações sintéticas. No entanto, o comando não desinstala os arquivos do agente do System Center ou os arquivos do sistema do Lync Server 2013.



</div>

Por padrão, os nós de Inspetor usam as URLs externas de uma organização ao conduzir seus testes. No entanto, nós de Inspetor também podem ser configurados para usar as URLs internas da organização. Isso permite que os administradores verifiquem o acesso a URLs para os usuários localizados dentro da rede de perímetro. Para configurar um nó de inspetor para usar URLs internas em vez de URLs externas, defina a propriedade UseInternalWebUrls como true ($True):

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $True

Se você redefinir essa propriedade para o valor padrão de false ($False), o Inspetor usará as URLs externas:

    Set-CsWatcherNodeConfiguration -Identity "atl-watcher-001.litwareinc.com" -UseInternalWebUrls $False

</div>

<span> </span>

</div>

</div>

</div>

