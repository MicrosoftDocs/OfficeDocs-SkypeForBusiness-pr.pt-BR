---
title: 'Lync Server 2013: suporte a reuniões grandes'
description: 'Lync Server 2013: suporte a reuniões grandes.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e116f4668c37fd26eea5cec322a8c6483385e7d3
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48554777"
---
# <a name="supporting-large-meetings-using-lync-server-2013"></a>Suporte a reuniões grandes usando o Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-03_

Reuniões grandes não seguem o modelo de teste descrito na seção anterior, pois elas possuem as seguintes características:

  - O formato da reunião é uma apresentação de um-para-muitos.

  - Um ou alguns usuários são representados e todos eles participam somente como participantes.

  - O compartilhamento de apresentação do PowerPoint é a principal atividade de colaboração de dados.

  - O áudio é exigido e o vídeo também pode ser utilizado.

  - Uma pessoa dedicada, geralmente, o organizador da reunião ou um assistente do organizador, define a reunião com antecedência.

  - Uma equipe dedicada (não os apresentadores) conduz a reunião, incluindo estabelecer uma conexão para uma reunião online, verificar se o áudio, vídeo e compartilhamento de slides estão funcionando, gerenciar lobby e funções dos usuários, ligar e desligar o microfone dos participantes, responder perguntas e gerenciar gravações, conforme apropriado.

Fornecer suporte a reuniões grandes com até 1.000 usuários requer correção de problemas relacionados ao modelo de hardware compartilhado e ao modelo sem reserva.

Para ter recursos suficientes de CPU e memória para reuniões de até 1000 usuários, os servidores front-end de hospedagem não devem hospedar nenhuma outra carga de mensagens instantâneas (IM) e presença ou cargas de trabalho do Enterprise Voice. Também não deve hospedar quaisquer outras reuniões, independente do tamanho das outras reuniões. Isso significa que a hospedagem de reuniões de até 1000 usuários exige a configuração de um pool separado do Lync Server dedicado à Hospedagem de grandes reuniões de até 1000 usuários.

Um pool do Lync Server dedicado à Hospedagem de grandes reuniões deve hospedar apenas uma reunião de até 1000 usuários ao mesmo tempo, portanto, os tempos de reunião precisam ser reservados antecipadamente por meio de um processo de agendamento fora da banda para garantir o suporte dedicado dos servidores front-end. Para suportar mais de uma reunião grande ao mesmo tempo, recomendamos a configuração de vários pool de reuniões grandes dedicados.

Recomendamos que uma pessoa dedicada conduza e monitore uma parte de uma grande reunião online. Essa pessoa deve ser o organizador, delegado do organizador ou apresentador, ou um membro da equipe de suporte à reunião grande dedicada, dependendo das preferências da organização.

Nas seções a seguir, descreveremos como implementar um pool dedicado para grandes reuniões, incluindo as práticas recomendadas para usar o Lync Server 2013 para suportar grandes cenários de reunião.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando o suporte para grandes reuniões no Lync Server 2013](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Gerenciando grandes reuniões no Lync Server 2013](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

