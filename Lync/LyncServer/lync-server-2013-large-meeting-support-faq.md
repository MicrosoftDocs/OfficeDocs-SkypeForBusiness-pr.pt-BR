---
title: 'Lync Server 2013: perguntas frequentes de suporte de reunião grande'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Lync Server large meeting support FAQ
ms:assetid: 34b4fb6a-e35c-47e8-8ab1-f8331741fed2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204804(v=OCS.15)
ms:contentKeyID: 48183837
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 4c8d834bbd38cbfeeccc74e90bad6f11e47cc805
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034963"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Perguntas frequentes de suporte para grandes reuniões do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-22_

A seção a seguir oferece respostas às perguntas comuns sobre a criação e execução de grandes reuniões.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>P: Quantos usuários podem participar de uma grande reunião?

O modelo de usuário do Lync Server especifica os limites de 250 usuários em um pool compartilhado ou 1000 usuários em um pool dedicado a grandes reuniões, mas esses números representam apenas o número de usuários testados e apenas para o conjunto específico de hardware que usamos em nossos testes. Com base nos testes, é recomendável manter esses limites para tamanhos máximos. No entanto, você controla o número real de participantes permitidos em reuniões em sua organização Configurando uma ou mais políticas de conferência (que você configura usando os cmdlets do Windows PowerShell no Shell de gerenciamento do Lync Server ou usando o Lync Server Painel de controle). O número especificado em uma política de conferência pode ser qualquer número inteiro de 32 bits entre 1 e 4.294.967.295, mas o tamanho recomendado está entre 2 e 250 participantes e o valor padrão é 250.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>P: Quantas reuniões ou cargas de trabalho posso ter em um pool dedicado a grandes reuniões?

Para assegurar a melhor experiência do usuário em grandes reuniões de até 1.000 participantes, é recomendável hospedar apenas uma única grande reunião por vez em um pool dedicado a grandes reuniões. É recomendável também não permitir que nenhuma outra carga de trabalho seja executada no pool enquanto a grande reunião estiver em andamento.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>P: Os organizadores de grandes reuniões devem ser hospedados no pool dedicado?

Não. É recomendável não hospedar nenhum usuário além da equipe dedicada que gerencia o agendamento de grandes reuniões no pool dedicado. Isso impede que outras comunicações em tempo real causem problemas com as grandes reuniões hospedadas no pool. Você deve agendar grandes reuniões no pool dedicado usando uma conta de usuário da equipe de agendamento da grande reunião. Você deve adicionar a conta de usuário do organizador da reunião (o usuário que solicita uma grande reunião) como um apresentador da grande reunião.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>P: Quais são as modalidades de mídia que posso usar em uma grande reunião?

As grandes reuniões com até 1.000 usuários podem conter áudio, vídeo, compartilhamento do PowerPoint, quadros de comunicações e  sondagem de presença.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>P: Posso usar IM (mensagens instantâneas) em grupo nas grandes reuniões?

Sim. No entanto, grandes números de mensagens instantâneas, especialmente quando enviadas por um grande número de participantes da reunião, podem afetar a experiência do usuário devido a problemas com a rolagem rápida do texto na janela de IM. A entrega de uma grande quantidade de mensagens instantâneas de até 1.000 usuários também pode introduzir cargas significativas do servidor, o que pode afetar o desempenho. Geralmente, o IM só é necessário para perguntas e respostas (\&p as).

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>P: Os usuários podem participar de grandes reuniões ligando de um telefone?

Sim. Se o pool do Lync Server 2013 estiver implantado e habilitado corretamente para conferência discada, os usuários poderão participar de grandes reuniões por discagem. Nossos testes mostraram que até 15% dos 1.000 usuários podem participar de uma grande reunião por um período de 10 minutos.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>P: Posso hospedar grandes reuniões em uma topologia virtual?

As grandes reuniões ainda não foram testadas em uma topologia virtual, portanto não há suporte para o uso de máquinas virtuais a fim de hospedar um pool dedicado a grandes reuniões.

</div>

</div>

<span> </span>

</div>

</div>

</div>

