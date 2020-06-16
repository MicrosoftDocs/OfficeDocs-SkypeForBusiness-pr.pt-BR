---
title: Práticas recomendadas do servidor de chat persistente
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server best practices
ms:assetid: dc18e7f7-599b-4d32-abf7-cd9e691426a2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398970(v=OCS.15)
ms:contentKeyID: 48185612
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ebe9742b76ec6abfd7b7407f38edda937bdf6ecc
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44751193"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-best-practices"></a>Práticas recomendadas do servidor de chat persistente

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-06_

À medida que você cria suas categorias e salas de chat persistente e projeta seu escopo e sua associação, as dicas a seguir podem ajudar no planejamento:

  - Se sua empresa não exigir uma parede ética, não restrinja o escopo na sua árvore de categorias. Coloque todos os usuários no escopo de uma categoria e crie todas as salas de chat nessa categoria. Subsequentemente, use somente listas de associação para conceder ou restringir o acesso a cada sala de chat.

  - Na maioria dos casos, você deve permitir que os usuários criem novas salas de chat para que as discussões sobre novos tópicos possam ser iniciadas a qualquer momento. Faça isso fazendo com que a lista de **criadores** seja a mesma que a lista de **Membros permitidos** . No entanto, se você deseja permitir que apenas uma equipe de suporte central ou usuários designados criem salas, torne a lista de **criadores** como o subconjunto apropriado.

  - Dê a cada sala de chat um resumo completo de nome e descrição que descreva onde cabe em sua organização. Como os usuários não podem ver o nome da categoria quando usam a sala de chat, não é possível confiar no nome da categoria para ajudar os usuários a determinar o fórum de discussão desejado para a sala de chat.

  - Você pode desejar ter um fluxo de trabalho de criação de sala personalizado se tiver determinadas convenções de nomenclatura ou outros controles de acesso ou validações a serem implementadas. A configuração de chat persistente permite personalizar o **RoomManagementUrl** para algo que você hospeda. Por exemplo, quando os usuários clicam em **criar uma sala** no cliente Lync, eles podem ser redirecionados para sua solução personalizada.

  - Crie uma variedade de suplementos que ajudam a aprimorar a experiência de salas de chat, colocando outros dados corporativos em salas de chat. Os administradores devem registrar os suplementos que eles desejam permitir no sistema. Os criadores e os gerentes de sala de chat podem escolher a partir da lista de suplementos permitidos para os que são mais relevantes para suas respectivas salas.

<div>

## <a name="see-also"></a>Confira também


[Gerenciando categorias, salas e suplementos no Lync Server 2013](lync-server-2013-managing-categories-rooms-and-add-ins.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

