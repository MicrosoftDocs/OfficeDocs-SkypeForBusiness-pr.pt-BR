---
title: 'Lync Server 2013: oferecendo suporte a reuniões grandes'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Supporting large meetings using Lync Server
ms:assetid: 509a424f-a33d-4e72-8f87-a3ec7bb1ddeb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204894(v=OCS.15)
ms:contentKeyID: 48184136
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d4e8c37c5498702e893da803497177c086a39a35
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844818"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="supporting-large-meetings-using-lync-server-2013"></a>Suporte a reuniões grandes usando o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-03_

Reuniões grandes não seguem o modelo de teste descrito na seção anterior porque têm as seguintes características:

  - O formato da reunião é uma apresentação de um-para-muitos.

  - Um ou alguns usuários são representados e todos eles participam somente como participantes.

  - O compartilhamento de apresentação do PowerPoint é a principal atividade de colaboração de dados.

  - O áudio é exigido e o vídeo também pode ser utilizado.

  - Uma pessoa dedicada, em geral, o organizador da reunião ou um assistente para o organizador configura a reunião de forma bem adiantada.

  - Uma equipe dedicada (não os apresentadores) conduz a reunião, incluindo estabelecer uma conexão para uma reunião online, verificar se o áudio, vídeo e compartilhamento de slides estão funcionando, gerenciar lobby e funções dos usuários, ligar e desligar o microfone dos participantes, responder perguntas e gerenciar gravações, conforme apropriado.

Dar suporte a reuniões grandes de até 1000 os usuários exigem a solução dos problemas relacionados ao modelo de hardware compartilhado e ao modelo sem reserva.

Para ter recursos de CPU e memória suficientes para as reuniões com até 1.000 usuários, os Servidores Front-End de hospedagem não devem hospedar nenhuma outra carga de trabalho de mensagens instantâneas (IM) e presença nem do Enterprise Voice. Ele também não deve hospedar nenhuma outra reunião, independentemente do tamanho das outras reuniões. Isso significa que hospedar reuniões de até 1000 usuários requer a configuração de um pool separado do Lync Server que seja dedicado a hospedar reuniões grandes de até 1000 usuários.

Um pool do Lync Server dedicado à Hospedagem de reuniões grandes deve hospedar uma e apenas uma reunião de até 1000 usuários ao mesmo tempo, para que os tempos da reunião precisem ser reservados antecipadamente por meio de um processo de agendamento fora da banda para garantir o suporte dedicado do serv do front-end ers. Para dar suporte a mais de uma reunião grande ao mesmo tempo, recomendamos configurar vários pools de reunião grandes dedicados.

Recomendamos que uma pessoa dedicada execute e monitore a parte online de uma reunião grande. Essa pessoa pode ser o organizador, o representante do organizador ou do apresentador, ou um membro da equipe de suporte de reunião grande dedicada, dependendo das preferências da organização.

Nas seções a seguir, descreveremos como implementar um pool dedicado para reuniões grandes, incluindo práticas recomendadas para usar o Lync Server 2013 para dar suporte a cenários de reunião grandes.

<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando o suporte para reuniões grandes no Lync Server 2013](lync-server-2013-setting-up-support-for-large-meetings.md)

  - [Gerenciar reuniões grandes no Lync Server 2013](lync-server-2013-managing-large-meetings.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

