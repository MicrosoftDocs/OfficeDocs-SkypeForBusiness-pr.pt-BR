---
title: Entendendo associações do Chat Persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Understanding Persistent Chat membership
ms:assetid: 900392d6-6e9f-4dae-93d6-39d7474409ef
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398730(v=OCS.15)
ms:contentKeyID: 48184781
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c2b4eb5fbe4342c1bd6bcb3bbb842e076e5863ad
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41741941"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>Entendendo associações do Chat Persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

O acesso do usuário a salas de chat persistente é gerenciado por associação; os usuários devem ser membros de uma sala de chat para poder postar e ler mensagens. Somente os **apresentadores** que têm uma afiliação designada com salas de chat podem usar o **lançamento para salas Auditorium**. Um Auditorium é um tipo de sala de chat (a outra é **normal**), onde somente os apresentadores podem postar e todos podem ler.

Além disso, as salas de chat persistente funcionam nas regras de uma categoria. Para obter detalhes sobre categorias, consulte [Gerenciando categorias, salas e suplementos no Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)e também as seções "como o escopo da categoria funciona" e "estratégias de categoria da sala", mais adiante neste tópico.

Um administrador de chat persistente pode criar e gerenciar categorias de sala de chat. Como parte da criação e do gerenciamento de categorias de salas de chat, o administrador de chat persistente pode configurar entidades de segurança (grupos, contêineres e usuários dos serviços de domínio Active Directory) que têm acesso a membros ou criadores de salas de chat de uma categoria específica.

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Serviços de domínio do Active Directory e chat persistente

O servidor de chat persistente depende do Active Directory para o pool de usuários de chat persistente internos. Depois de instalar o chat persistente (cliente), você pode adicionar domínios de usuários e grupos de usuários à categoria sala. Em seguida, você pode adicionar esses usuários e grupos à Associação das categorias da sala.

<div>


> [!IMPORTANT]  
> Você deve certificar-se de que não haja nomes duplicados para os usuários que desejam fazer alterações em suas salas de chat persistente (s). Se houver nomes de usuário duplicados, altere-os para nomes diferentes para desbloquear os usuários de fazerem essas alterações. Se um usuário tiver nomes duplicados no Active Directory e tentar fazer alterações na (s) sala (s), uma mensagem de erro será exibida solicitando que o usuário entre em contato com o administrador para obter resolução.



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>Como o escopo da categoria funciona

Uma categoria especifica todos os usuários e grupos que podem ser membros de uma lista de membros de uma sala de chat persistente na categoria, com base em sua propriedade **AllowedMembers** . Por exemplo, se você definir o **AllowedMembers** da categoria como contoso.com, poderá adicionar qualquer grupo ou usuário na *contoso* como membro para salas de chat nessa categoria. Se você definir o **AllowedMembers** em uma categoria para *vendas*, somente grupos e usuários nesta lista de distribuição poderão ser adicionados como membros a salas de chat nessa categoria. Da mesma forma, a propriedade **Creators** permite que você controle quem pode criar salas de chat nessa categoria. Após a criação da sala de chat, qualquer pessoa do grupo **AllowedMembers** pode ser designada como **gerente** para operações de gerenciamento contínuo nas salas (por exemplo, alterações de associação e aprovações).

A definição de **AllowedMembers** e **criadores** para uma categoria tem os seguintes benefícios:

  - Todas as salas de chat nesta categoria estão limitadas às restrições definidas no nível da categoria. Você pode usar isso para segregar as salas de chat com base nas necessidades de negócios e políticas de acesso.

  - Um usuário que está na lista de **criadores** pode criar novas salas de chat nessa categoria. Se você quiser implementar um sistema em que um número restrito de funcionários na organização possa criar salas de chat, esse controle poderá ser usado para atender a essa exigência.

</div>

<div>

## <a name="room-category-strategies"></a>Estratégias de categoria da sala

O **AllowedMembers** de uma categoria deve incluir todos os usuários que usarão qualquer sala de chat persistente nessa categoria. Dependendo dos seus requisitos de proteção de dados corporativos e garantia do nível apropriado de acesso, talvez você queira definir uma ou mais categorias para especificar quem pode pesquisar e participar de salas. Se você deseja permitir apenas um conjunto específico de usuários (um helpdesk central ou somente funcionários em tempo integral) para criar salas, é possível fazer o escopo dos **criadores** de uma categoria para atender a essa exigência.

As categorias também podem ser usadas para criar paredes éticas. As paredes éticas impedem qualquer conflito de interesse em uma organização. Por exemplo, um administrador pode criar salas de chat em uma categoria somente para os comerciantes, enquanto as salas de chat em outra categoria podem ser usadas somente por analistas.

<div>


> [!NOTE]  
> No Lync Server 2013, servidor de chat persistente, não oferecemos suporte ao acesso a usuários federados. Se houver chats de usuários federados nas versões anteriores do servidor de chat persistente, eles serão migrados. Os usuários federados são adicionados como entidades de segurança desabilitadas.



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>Restringir os membros a grupos de usuários

Quando você adiciona um domínio a uma categoria, os grupos de usuários cujos objetos de grupo estão contidos nesse domínio estão disponíveis para que você possa especificá-los como membros de salas na categoria.

Recomendamos, como regra geral, que você use contêineres do Active Directory, como domínios e unidades organizacionais, para definir a **AllowedMembers** e os **criadores**de uma categoria. Você pode adicionar objetos de qualquer domínio a uma lista de **AllowedMembers** ou **criadores** . Somente objetos na lista **AllowedMembers** ou **criadores** podem ser adicionados a salas sob essa categoria.

</div>

</div>

<span> </span>

</div>

</div>

</div>

