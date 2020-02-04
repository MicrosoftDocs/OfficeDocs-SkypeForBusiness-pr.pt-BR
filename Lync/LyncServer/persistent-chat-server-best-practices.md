---
title: Práticas recomendadas do Servidor de Chat Persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 119bc67622928ec2e60f082e72322e7b0b923c2e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41743671"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a><span data-ttu-id="5c593-102">Práticas recomendadas do Servidor de Chat Persistente</span><span class="sxs-lookup"><span data-stu-id="5c593-102">Persistent Chat Server best practices</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="5c593-103">_**Tópico da última modificação:** 2012-10-06_</span><span class="sxs-lookup"><span data-stu-id="5c593-103">_**Topic Last Modified:** 2012-10-06_</span></span>

<span data-ttu-id="5c593-104">À medida que você cria suas categorias e salas de chat persistentes e cria seu escopo e associação, as dicas a seguir podem ajudar no seu planejamento:</span><span class="sxs-lookup"><span data-stu-id="5c593-104">As you create your categories and Persistent Chat rooms and design your scoping and membership, the following tips can help your planning:</span></span>

  - <span data-ttu-id="5c593-105">Se a sua empresa não exigir uma parede ética, não restrinja o escopo na sua árvore de categoria.</span><span class="sxs-lookup"><span data-stu-id="5c593-105">If your company does not require an ethical wall, do not narrow the scope in your category tree.</span></span> <span data-ttu-id="5c593-106">Coloque todos os usuários no escopo de uma categoria e crie todas as salas de chat nessa categoria.</span><span class="sxs-lookup"><span data-stu-id="5c593-106">Put all your users in the scope of one category, and create all chat rooms in that category.</span></span> <span data-ttu-id="5c593-107">Em seguida, use somente listas de associação para conceder ou restringir o acesso a cada sala de chat.</span><span class="sxs-lookup"><span data-stu-id="5c593-107">Subsequently, use only membership lists to grant or restrict access to each chat room.</span></span>

  - <span data-ttu-id="5c593-108">Na maioria dos casos, você deve permitir que os usuários criem novas salas de chat para que as discussões sobre novos tópicos possam ser iniciadas a qualquer momento.</span><span class="sxs-lookup"><span data-stu-id="5c593-108">In most cases, you should enable users to create new chat rooms so that discussions about new topics can be started any time.</span></span> <span data-ttu-id="5c593-109">Faça isso fazendo com que a lista de **criadores** seja a mesma que a lista **AllowedMembers** .</span><span class="sxs-lookup"><span data-stu-id="5c593-109">Do this by making the **Creators** list the same as the **AllowedMembers** list.</span></span> <span data-ttu-id="5c593-110">No entanto, se você quiser permitir que apenas uma equipe de suporte central ou usuários designados criem salas, torne a lista de **criadores** como o subconjunto apropriado.</span><span class="sxs-lookup"><span data-stu-id="5c593-110">However, if you want to allow only a central support team or designated users to create rooms, then make the **Creators** list as the appropriate subset.</span></span>

  - <span data-ttu-id="5c593-111">Dê a cada sala de chat um resumo completo de nome e descrição que descreva onde cabe em sua organização.</span><span class="sxs-lookup"><span data-stu-id="5c593-111">Give each chat room a complete name and description summary that describes where it fits in with your organization.</span></span> <span data-ttu-id="5c593-112">Como os usuários não conseguem ver o nome da categoria quando usam a sala de chat, você não pode depender do nome da categoria para ajudar os usuários a determinar o fórum de discussão desejado para a sala de chat.</span><span class="sxs-lookup"><span data-stu-id="5c593-112">Because users cannot see the category name when they use the chat room, you cannot rely on the category name to help users determine the intended discussion forum for the chat room.</span></span>

  - <span data-ttu-id="5c593-113">Talvez você queira ter um fluxo de trabalho de criação de sala personalizado se tiver determinadas convenções de nomenclatura ou outros controles ou validações de acesso a implementar.</span><span class="sxs-lookup"><span data-stu-id="5c593-113">You may want to have a custom room creation workflow if you have certain naming conventions or other access controls or validations to implement.</span></span> <span data-ttu-id="5c593-114">A configuração de chat persistente permite que você personalize o **RoomManagementUrl** para algo que você hospeda.</span><span class="sxs-lookup"><span data-stu-id="5c593-114">The Persistent Chat configuration enables you to customize the **RoomManagementUrl** to something that you host.</span></span> <span data-ttu-id="5c593-115">Por exemplo, quando os usuários clicam em **criar uma sala** em seus clientes Lync, eles podem ser redirecionados para sua solução personalizada.</span><span class="sxs-lookup"><span data-stu-id="5c593-115">For example, when users click **Create a room** in their Lync client, they can be redirected to your custom solution.</span></span>

  - <span data-ttu-id="5c593-116">Crie uma variedade de suplementos que ajudam a aprimorar a experiência de salas de chat, trazendo outros dados comerciais para salas de chat.</span><span class="sxs-lookup"><span data-stu-id="5c593-116">Create a variety of add-ins that help to enhance the experience of chat rooms by bringing in other business data into chat rooms.</span></span> <span data-ttu-id="5c593-117">Os administradores devem registrar os suplementos que desejam permitir no sistema.</span><span class="sxs-lookup"><span data-stu-id="5c593-117">Administrators must register the add-ins that they want to allow in the system.</span></span> <span data-ttu-id="5c593-118">Os criadores e os criadores da sala de chat podem escolher na lista de suplementos permitidos para aqueles que são mais relevantes para suas respectivas salas.</span><span class="sxs-lookup"><span data-stu-id="5c593-118">Chat room managers and creators can choose from the list of allowed add-ins for the ones most relevant to their respective rooms.</span></span>

<div>

## <a name="see-also"></a><span data-ttu-id="5c593-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="5c593-119">See Also</span></span>


[<span data-ttu-id="5c593-120">Gerenciando categotias, salas e suplementos no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="5c593-120">Managing categories, rooms, and add-ins in Lync Server 2013</span></span>](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

