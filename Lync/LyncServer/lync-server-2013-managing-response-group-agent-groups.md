---
title: 'Lync Server 2013: gerenciamento de grupos de agentes de grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Managing Response Group agent groups
ms:assetid: 36084cdc-38f1-4c45-922f-f81c7e86210c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg520976(v=OCS.15)
ms:contentKeyID: 48183806
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6001e8b6301df1863de21e0d88369116cef03ff5
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756085"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Gerenciamento de grupos de agente de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-01_

Um grupo de agente consiste em um grupo de pessoas que são designadas para atender chamadas para um grupo de resposta. Ao criar um grupo de agente, você seleciona os agentes atribuídos ao grupo e Especifica configurações de grupo adicionais, como o método de roteamento e se um agente pode entrar e sair do grupo.

<div>


> [!NOTE]  
> Os usuários devem ser habilitados para o Enterprise Voice para que você possa adicioná-los a grupos de agente. Para obter detalhes sobre como habilitar um usuário para o Enterprise Voice, consulte <A href="lync-server-2013-enable-users-for-enterprise-voice.md">habilitar usuários do Enterprise Voice no Lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Somente os usuários no local podem ser agentes. Se um agente for movido do local para o online, as chamadas em grupo de resposta não serão roteadas para esse agente.



</div>

Um agente que deve entrar e sair do grupo, que é diferente de entrar ou sair do Lync Server, é chamado de *agente formal*. Os agentes formais devem estar conectados ao grupo antes que eles possam receber chamadas roteadas para o grupo. Isso pode ser útil para os operadores que respondem às chamadas do grupo em tempo parcial. Os agentes formais entram e saem de seus grupos clicando em um item de menu no Lync 2013 para abrir o navegador da Internet do Windows Internet Explorer e exibir um console de página da Web.

Um operador que não precisa entrar ou sair do grupo é denominado *operador informal*. Agentes informais são automaticamente conectados ao grupo quando são conectados ao Lync Server, e não podem sair do grupo.

<div>


> [!IMPORTANT]  
> Quando você atribui usuários como agentes de grupo de resposta, informe-os de que, se eles tiverem o modo Privacidade habilitado, precisarão pesquisar por contatos "RGS Presence Watcher" e adicioná-los à sua lista Contatos. Agentes que tem o modo Privacidade habilitado, mas não tem "RGS Presence Watcher" em sua lista de Contatos, não podem receber chamadas no grupo de resposta. Agentes que não têm o modo Privacidade habilitado não são afetados.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criar ou modificar um grupo de agente no Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Excluir um grupo de agente no Lync Server 2013](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

