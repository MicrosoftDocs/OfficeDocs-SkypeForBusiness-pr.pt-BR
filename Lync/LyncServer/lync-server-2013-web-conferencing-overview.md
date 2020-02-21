---
title: Lync Server 2013 visão geral da webconferência
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Web conferencing overview
ms:assetid: 40616dc4-f705-4890-85bf-79f76a033a9b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425913(v=OCS.15)
ms:contentKeyID: 48183949
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: c7a37578840191e8905827727e91665fc7a7512d
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42210937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Visão geral da webconferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-30_

Com a Webconferência, os usuários podem compartilhar e colaborar em documentos, como apresentações do PowerPoint, durante suas conferências. Além disso, os usuários podem compartilhar toda ou parte da área de trabalho com os outros em tempo real, dando a impressão de que todas as pessoas da conferência estão reunidas ao redor da mesma mesa da reunião.

<div>

## <a name="whiteboard-and-annotations"></a>Quadro de comunicações e anotações

Um quadro de comunicações é uma tela em branco que pode ser usada para colaboração com texto, tinta, desenhos e imagens. As anotações feitas nos quadros de comunicações podem ser vistas por todos os participantes da reunião. O recurso de quadro de comunicações aprimora a colaboração ao permitir que os participantes da reunião discutam ideias, façam brainstorm, anotações e outros.

</div>

<div>

## <a name="polling"></a>Sondagem

O recurso de sondagem aprimora a colaboração ao permitir que os apresentadores determinem rapidamente as preferências dos participantes. Durante reuniões online e conversas, os apresentadores podem utilizar a sondagem para obter respostas anônimas dos participantes. Todos os apresentadores podem ver os resultados e podem escondê-los ou mostrá-los aos presentes.

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>Compartilhamento de aplicativo e compartilhamento de Desktop

Durante uma conferência, você pode compartilhar toda a área de trabalho, um aplicativo individual ou monitores individuais em um ambiente de vários monitores. À parte de apenas visualizar o conteúdo, os outros participantes na conferência também podem solicitar controle da sua tela e, com permissão, interagir com o conteúdo (incluindo rolar e editar).

<div>


> [!NOTE]  
> Os participantes que estão visualizando a conferência podem assumir o controle e iniciar o compartilhamento de conteúdo durante a reunião.



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>Compartilhamento do PowerPoint

Nas apresentações do PowerPoint 2010 do Lync foram visualizadas de duas maneiras. Para usuários que executam o Lync 2010, as apresentações do PowerPoint foram exibidas usando o formato PowerPoint 97-2003 e foram exibidas usando uma cópia incorporada do Visualizador do PowerPoint. Para usuários que executam o Lync Web App, as apresentações do PowerPoint foram convertidas em arquivos HTML dinâmicos e, em seguida, visualizadas usando uma combinação desses arquivos DHTML personalizados e Silverlight. Apesar de normalmente ser eficaz, essa abordagem possuía algumas limitações:

  - O Visualizador do PowerPoint incorporado (que forneceu a experiência de visualização ideal) só está disponível na plataforma Windows.

  - Muitos dispositivos móveis (incluindo alguns dos telefones celulares mais populares) não oferecem suporte ao Silverlight.

  - O Visualizador do PowerPoint e a abordagem DHTML/Silverlight não dão suporte a todos os recursos (como transições de slides e vídeo incorporado) encontrados nas edições mais recentes do PowerPoint.

Para ajudar a resolver esses problemas e para melhorar a experiência geral dos usuários que estão apresentando ou visualizando apresentações do PowerPoint, o Lync Server 2013 emprega o Office Web Apps e o servidor do Office Web Apps para lidar com apresentações do PowerPoint. Entre outras vantagens, essa nova abordagem permite:

  - Exibições de alta resolução e melhor suporte para capacidades do PowerPoint, como animações, transições de slides e vídeo incorporado.

  - Dispositivos móveis adicionais para acessar tais apresentações. Isso ocorre porque o Lync Server 2013 usa DHTML e JavaScript padrão para transmitir apresentações do PowerPoint em vez de DHTML e Silverlight personalizados.

  - Usuários com os privilégios adequados para rolar uma apresentação do PowerPoint independente da apresentação propriamente dita. Por exemplo, enquanto Ken Myer está apresentando a apresentação dele, Pilar Ackerman pode olhar qualquer slide que desejar sem afetar a apresentação do Ken.

</div>

</div>

<span> </span>

</div>

</div>

</div>

