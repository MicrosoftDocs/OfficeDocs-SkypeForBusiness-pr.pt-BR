---
title: Noções básicas sobre associação de chat persistente
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
ms.openlocfilehash: 3cc357eff6cdc68c5285eeb915f5534b6f38b871
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42189144"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="understanding-persistent-chat-membership"></a>Noções básicas sobre associação de chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

O acesso do usuário a salas de chat persistente é gerenciado por associação; os usuários devem ser membros de uma sala de chat para poder postar e ler mensagens. Apenas **Apresentadores** que projetaram a afiliação com salas de chat têm permissão para usar a **publicação às salas de auditório**. Um auditório é um tipo de sala de chat (a outra é a **Normal**), onde apenas Apresentadores podem postar e todos podem ler.

Além disso, as salas de chat persistente operam sob as regras de uma categoria. Para obter detalhes sobre categorias, consulte [Gerenciando categorias, salas e suplementos no Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)e também as seções "como o escopo da categoria funciona" e "estratégias de categoria de sala", mais adiante neste tópico.

Um administrador de chat persistente pode criar e gerenciar categorias de sala de chat. Como parte da criação e do gerenciamento de categorias de sala de chat, o administrador de chat persistente pode configurar entidades (grupos, contêineres e usuários dos serviços de domínio Active Directory) que têm acesso a membros ou criadores de salas de chat de uma determinada categoria.

<div>

## <a name="active-directory-domain-services-and-persistent-chat"></a>Serviços de domínio do Active Directory e chat persistente

O servidor de chat persistente utiliza o Active Directory para o pool de usuários de chat persistente internos. Após instalar o chat persistente (cliente), você pode adicionar domínios de usuários e grupos de usuários à categoria de sala. Você poderá depois adicionar esses usuários e grupos aos membros de suas categorias de salas.

<div>


> [!IMPORTANT]  
> Você deve garantir que não haja nomes duplicados para os usuários que desejam fazer alterações na (s) sala (s) de chat persistente. Se nomes de usuários duplicados existirem, altere-os para nomes diferentes para desbloquear os usuários par fazer essas alterações. Se um usuário tiver nomes duplicados no Active Directory e tentar fazer alterações na (s) sala (s), uma mensagem de erro será exibida solicitando que o usuário contate o administrador para resolução.



</div>

</div>

<div>

## <a name="how-category-scoping-works"></a>Como funciona a associação de categoria

Uma categoria especifica todos os usuários e grupos que podem ser membros de uma lista de membros de uma sala de chat persistente nessa categoria, com base em sua propriedade **Membros permitidos** . Por exemplo, se você definir o **Membros permitidos** da categoria como contoso.com, poderá adicionar qualquer grupo ou usuário na *contoso* como membro para salas de chat nessa categoria. Se você definir o **Membros permitidos** em uma categoria como *vendas*, somente os grupos e usuários dessa lista de distribuição poderão ser adicionados como membros às salas de chat nessa categoria. Da mesma forma, a propriedade **Creators** permite que você controle quem pode criar salas de chat nessa categoria. Depois que a sala de chat é criada, qualquer pessoa do grupo **Membros permitidos** pode ser designada como **gerente** para operações de gerenciamento contínuo nas salas (por exemplo, alterações de associação e aprovações).

Definir uma lista de membros para uma categoria oferece os seguintes benefícios:

  - Todas as salas de chat nesta categoria estão sujeitas às restrições definidas no nível da categoria. Você pode usar isso para segregar as salas de chat baseando-se nas necessidades de negócios e políticas de acesso.

  - Um usuário membro na lista **Criadores ** pode criar novas salas de chat naquela categoria. Se você desejar implantar um sistema onde um número restrito de pessoas na organização possa criar salas de chat, este controle pode ser usado para atender a essa exigência.

</div>

<div>

## <a name="room-category-strategies"></a>Estratégias de categoria de salas

O **Membros permitidos** de uma categoria deve incluir todos os usuários que usarão qualquer sala de chat persistente nessa categoria. Dependendo dos seus requisitos para proteger dados empresariais e garantir o nível correto de acesso, você poderá definir uma ou mais categorias para especificar quem pode pesquisar e participar das salas. Se desejar permitir apenas um conjunto específico de usuários (um helpdesk central ou apenas funcionários de tempo integral) para criar salas, você pode fazer o escopo dos **Criadores** de uma categoria para satisfazer esse requisito.

As categorias podem ser também usadas para criar barreiras éticas. As barreiras éticas evitam qualquer conflito de interesses em uma organização. Por exemplo, um administrador pode criar salas de chat em uma categoria apenas para comerciantes, ao passo que as salas de chat em outra categoria podem ser usadas somente por analistas.

<div>


> [!NOTE]  
> No Lync Server 2013, servidor de chat persistente, não há suporte para acesso a usuários federados. Se houver chats de usuários federados em versões anteriores do servidor de chat persistente, eles serão migrados. Os usuários federados são adicionados como princípios desativados.



</div>

</div>

<div>

## <a name="narrowing-the-members-to-user-groups"></a>Como estreitar o escopo para grupos de usuário

Ao adicionar um domínio ao escopo da categoria raiz, os grupos de usuários cujos objetos de grupo estão contidos nesse domínio serão disponibilizados a você para serem especificados como membros das categorias e salas de chat no servidor.

Recomendamos, como regra geral, que você use contêineres do Active Directory, como domínios e unidades organizacionais, para definir os **Membros permitidos** e **criadores**de uma categoria. Você pode adicionar objetos de qualquer domínio a uma lista de  **Membros Permitidos** ou **Criadores**. Apenas objetos dentro da lista de **Membros Permitidos** ou **Criadores** pode ser adicionada a salas sob esta categoria.

</div>

</div>

<span> </span>

</div>

</div>

</div>

