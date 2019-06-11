---
title: Práticas recomendadas do Servidor de Chat Persistente
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ac9419485212df8ecf0a11841a6eaee4c752640
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844212"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>Práticas recomendadas do Servidor de Chat Persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-06_

À medida que você cria suas categorias e salas de chat persistentes e cria seu escopo e associação, as dicas a seguir podem ajudar no seu planejamento:

  - Se a sua empresa não exigir uma parede ética, não restrinja o escopo na sua árvore de categoria. Coloque todos os usuários no escopo de uma categoria e crie todas as salas de chat nessa categoria. Em seguida, use somente listas de associação para conceder ou restringir o acesso a cada sala de chat.

  - Na maioria dos casos, você deve permitir que os usuários criem novas salas de chat para que as discussões sobre novos tópicos possam ser iniciadas a qualquer momento. Faça isso fazendo com que a lista de **criadores** seja a mesma que a lista **AllowedMembers** . No entanto, se você quiser permitir que apenas uma equipe de suporte central ou usuários designados criem salas, torne a lista de **criadores** como o subconjunto apropriado.

  - Dê a cada sala de chat um resumo completo de nome e descrição que descreva onde cabe em sua organização. Como os usuários não conseguem ver o nome da categoria quando usam a sala de chat, você não pode depender do nome da categoria para ajudar os usuários a determinar o fórum de discussão desejado para a sala de chat.

  - Talvez você queira ter um fluxo de trabalho de criação de sala personalizado se tiver determinadas convenções de nomenclatura ou outros controles ou validações de acesso a implementar. A configuração de chat persistente permite que você personalize o **RoomManagementUrl** para algo que você hospeda. Por exemplo, quando os usuários clicam em **criar uma sala** em seus clientes Lync, eles podem ser redirecionados para sua solução personalizada.

  - Crie uma variedade de suplementos que ajudam a aprimorar a experiência de salas de chat, trazendo outros dados comerciais para salas de chat. Os administradores devem registrar os suplementos que desejam permitir no sistema. Os criadores e os criadores da sala de chat podem escolher na lista de suplementos permitidos para aqueles que são mais relevantes para suas respectivas salas.

<div>

## <a name="see-also"></a>Confira também


[Gerenciando categotias, salas e suplementos no Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

