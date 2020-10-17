---
title: 'Lync Server 2013: Gerenciando grupos de agente de grupo de resposta'
description: 'Lync Server 2013: Gerenciando grupos de agente do grupo de resposta.'
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
ms.openlocfilehash: 23a4f430981689f9794c05aa1472ff61cd32cd5f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48569387"
---
# <a name="managing-response-group-agent-groups-in-lync-server-2013"></a>Gerenciar grupos de agente de grupo de resposta no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-01_

Um grupo de operadores consiste em um grupo de pessoas designadas para atender às chamadas de um grupo de resposta. Ao criar um grupo de operadores, selecione os operadores que serão atribuídos ao grupo e especifique configurações de grupo adicionais, como o método de roteamento e se um operador pode entrar no grupo e sair dele.

<div>


> [!NOTE]  
> Os usuários devem estar habilitados para o Enterprise Voice para que você possa adicioná-los aos grupos de agentes. Para obter detalhes sobre como habilitar um usuário para o Enterprise Voice, consulte <A href="lync-server-2013-enable-users-for-enterprise-voice.md">Enable users for Enterprise Voice in Lync Server 2013</A>.



</div>

<div>


> [!NOTE]  
> Apenas os usuários locais podem ser operadores. Se um operador for movido de local para online, a chamada do grupo de resposta não será mais roteada para ele.



</div>

Um agente que deve entrar e sair do grupo, que é diferente de entrar ou sair do Lync Server, é chamado de um *agente formal*. Os operadores formais precisam entrar no grupo para que possam receber as chamadas roteadas para o grupo. Isso pode ser útil para os operadores que respondem às chamadas do grupo em tempo parcial. Os agentes formais entram e saem de seus grupos clicando em um item de menu no Lync 2013 para abrir o navegador Internet Windows Internet Explorer e exibir um console de página da Web.

Um operador que não precisa entrar ou sair do grupo é denominado *operador informal*. Os agentes informais são automaticamente conectados ao grupo quando entram no Lync Server e não podem sair do grupo.

<div>


> [!IMPORTANT]  
> Quando você atribuir os usuários como operadores do grupo de resposta, informe-os de que, se tiverem o modo de privacidade habilitado, precisarão pesquisar os contatos do "RGS Presence Watcher" e adicioná-los à sua lista de contatos. Os operadores com o modo de privacidade habilitado, mas que não têm o "RGS Presence Watcher" na lista de contatos, não podem receber chamadas para o grupo de resposta. Os operadores que não têm o modo de privacidade habilitado não são afetados.



</div>

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Criar ou modificar um grupo de agentes no Lync Server 2013](lync-server-2013-create-or-modify-an-agent-group.md)

  - [Excluir um grupo de agentes no Lync Server 2013](lync-server-2013-delete-an-agent-group.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

