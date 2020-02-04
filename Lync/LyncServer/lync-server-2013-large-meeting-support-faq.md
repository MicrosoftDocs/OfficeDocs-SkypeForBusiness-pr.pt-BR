---
title: 'Lync Server 2013: perguntas frequentes sobre suporte a reuniões grandes'
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
ms.openlocfilehash: 6f5a8d63fddf3b8633ebf31651d501458eaf4893
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41762169"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a>Perguntas frequentes sobre suporte a reuniões grandes do Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-22_

As seções a seguir fornecem respostas a perguntas comuns para criar e executar reuniões grandes.

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a>P: quantos usuários podem participar de uma reunião grande?

O modelo de usuário do Lync Server especifica os limites de usuários do 250 em um pool compartilhado ou 1000 usuários em um pool dedicado a reuniões grandes, mas esses números representam apenas o número de usuários que testamos e somente para o conjunto específico de hardwares que usamos em nossos testes. Com base em nossos testes, recomendamos os limites para os tamanhos máximos. No entanto, você controla o número real de participantes permitidos em reuniões em sua organização Configurando uma ou mais políticas de conferência (que você configura usando cmdlets do Windows PowerShell no Shell de gerenciamento do Lync Server ou usando o Lync Server Painel de controle). O número que você especificar em uma política de conferência pode ser qualquer número inteiro de 32 bits entre 1 e 4.294.967.295, mas o tamanho recomendado é entre 2 e 250 participantes, inclusive; e o valor padrão é 250.

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a>P: quantas reuniões ou outras cargas de trabalho posso ter em um pool dedicado a reuniões grandes?

Para garantir a melhor experiência do usuário em reuniões grandes de até 1000 participantes, recomendamos hospedar apenas uma única reunião grande de cada vez em um pool dedicado a reuniões grandes. Também recomendamos que você não permita que outras cargas de trabalho sejam executadas nesse pool quando a reunião grande estiver em andamento.

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a>P: os organizadores de reuniões grandes devem ser hospedados no pool dedicado?

Não. Recomendamos não agrupar outros usuários além da equipe dedicada que gerencia o agendamento de reuniões grandes no pool dedicado. Isso impede que outro tráfego de comunicação em tempo real cause problemas com reuniões grandes hospedadas no pool. Você deve agendar reuniões grandes no pool dedicado usando uma conta de usuário da grande equipe de agendamento de reunião. Você deve adicionar a conta de usuário do organizador da reunião (o usuário que solicita uma reunião grande) como apresentador da reunião grande.

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a>P: quais modalidades de mídia posso usar em uma reunião grande?

Reuniões grandes com até 1000 usuários podem incluir áudio, vídeo, compartilhamento do PowerPoint, quadros de comunicações e sondagem de presença.

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a>P: posso usar mensagens instantâneas em grupo (IM) em reuniões grandes?

Sim. No entanto, números grandes de mensagens de chat, especialmente quando enviados por um grande número de participantes da reunião, podem afetar a experiência do usuário devido a problemas com a rolagem rápida de texto na janela de mensagens instantâneas. Fornecendo uma grande quantidade de mensagens de chat para até 1000 os usuários também podem introduzir cargas de servidor significativas, que podem afetar o desempenho. Geralmente, as mensagens instantâneas são necessárias somente para perguntas e\&respostas (p as).

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a>Os usuários podem ingressar em reuniões grandes ao discar de um telefone?

Sim. Se o pool do Lync Server 2013 estiver adequadamente implantado e habilitado para conferência discada, os usuários poderão ingressar nas reuniões grandes discando. Nosso teste mostrou que até 15% dos usuários do 1000 podem ingressar na reunião grande durante um período de 10 minutos.

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a>P: é possível hospedar reuniões grandes em uma topologia virtual?

Não testamos reuniões grandes em uma topologia virtual, portanto, não oferecemos suporte ao uso de máquinas virtuais para hospedar um pool dedicado para reuniões grandes.

</div>

</div>

<span> </span>

</div>

</div>

</div>

