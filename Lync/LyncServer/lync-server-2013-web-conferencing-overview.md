---
title: Visão geral da webconferência do Lync Server 2013
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
ms.openlocfilehash: de63cb5bf2578359d012cda72b07b8fc7f62880d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41758533"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-web-conferencing-in-lync-server-2013"></a>Visão geral da Web conferência no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-30_

Com a conferência na Web, os usuários podem compartilhar e colaborar em documentos, como apresentações do PowerPoint, durante as conferências. Além disso, os usuários podem compartilhar todas as áreas de trabalho ou parte delas umas com as outras em tempo real, o que parece que as pessoas na conferência foram coletadas em torno da mesma tabela na reunião.

<div>

## <a name="whiteboard-and-annotations"></a>Quadro de comunicações e anotações

O quadro de comunicações é uma tela em branco que pode ser usada para colaboração com texto, tinta, desenhos e imagens. As anotações feitas nos quadros de comunicações podem ser vistas por todos os participantes da reunião. O recurso de quadro de comunicações aprimora a colaboração, pois habilita os participantes da reunião a discutirem ideias, fazerem brainstorming, anotações e muito mais.

</div>

<div>

## <a name="polling"></a>Poll

O recurso de sondagem aprimora a colaboração ao habilitar os apresentadores a determinarem rapidamente as preferências dos participantes. Durante reuniões online e conversas, os apresentadores podem utilizar a sondagem para obter respostas anônimas dos participantes. Todos os apresentadores podem ver os resultados e optar por escondê-los ou mostrá-los aos presentes.

</div>

<div>

## <a name="application-sharing-and-desktop-sharing"></a>Compartilhamento de aplicativos e compartilhamento de área de trabalho

Durante uma conferência, você pode compartilhar toda a área de trabalho, um aplicativo individual ou monitores individuais em um ambiente com vários monitores. Além de apenas exibir o conteúdo, outros participantes da conferência também podem solicitar o controle da sua tela e, com a permissão, interagir com o conteúdo (incluindo a rolagem e a edição).

<div>


> [!NOTE]  
> Os participantes que estão visualizando a conferência também podem assumir e começar a compartilhar conteúdo durante a reunião



</div>

</div>

<div>

## <a name="powerpoint-sharing"></a>Compartilhamento do PowerPoint

No Lync 2010, as apresentações do PowerPoint foram vistas de uma das duas maneiras. Para usuários que executam o Lync 2010, apresentações do PowerPoint foram exibidas usando o formato do PowerPoint 97-2003 e foram exibidas usando uma cópia inserida do Visualizador do PowerPoint. Para os usuários que executam o Lync Web App, as apresentações do PowerPoint foram convertidas em arquivos HTML dinâmicos e exibidas usando uma combinação desses arquivos DHTML personalizados e do Silverlight. Embora geralmente eficiente, essa abordagem tem algumas limitações:

  - O Visualizador do PowerPoint incorporado (que fornece a melhor experiência de exibição) só está disponível na plataforma Windows.

  - Muitos dispositivos móveis (incluindo alguns dos telefones celulares mais populares) não são compatíveis com o Silverlight.

  - O Visualizador do PowerPoint e a abordagem DHTML/Silverlight não dão suporte a todos os recursos (tais transições de slides e vídeo incorporado) encontrados nas edições mais recentes do PowerPoint.

Para ajudar a solucionar esses problemas e melhorar a experiência geral dos usuários de apresentar ou exibir apresentações do PowerPoint, o Lync Server 2013 emprega os aplicativos Web do Office e o Office Web Apps Server para manipular apresentações do PowerPoint. Entre outras vantagens, essa nova abordagem permite:

  - Monitores de alta resolução e suporte melhor para recursos do PowerPoint, como animações, transições de slides e vídeo incorporado.

  - Dispositivos móveis adicionais para acessar essas apresentações. Isso porque o Lync Server 2013 usa DHTML e JavaScript padrão para transmitir apresentações do PowerPoint em vez de DHTML e Silverlight personalizados.

  - Usuários com privilégios adequados para percorrer uma apresentação do PowerPoint independente da própria apresentação. Por exemplo, enquanto Ken Myer está apresentando sua apresentação de slides, pilar Alverca pode ver qualquer slide que queira e sem afetar a apresentação do Ken.

</div>

</div>

<span> </span>

</div>

</div>

</div>

