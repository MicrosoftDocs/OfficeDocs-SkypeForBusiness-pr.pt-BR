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
ms.openlocfilehash: 8b00c7d2713bed543dd42812d0d7c31bf75cd1d8
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42146334"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="large-meeting-support-faq-for-lync-server-2013"></a><span data-ttu-id="958d9-102">Perguntas frequentes de suporte para grandes reuniões do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="958d9-102">Large meeting support FAQ for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="958d9-103">_**Última modificação do tópico:** 2012-10-22_</span><span class="sxs-lookup"><span data-stu-id="958d9-103">_**Topic Last Modified:** 2012-10-22_</span></span>

<span data-ttu-id="958d9-104">A seção a seguir oferece respostas às perguntas comuns sobre a criação e execução de grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="958d9-104">The following sections provide answers to common questions for creating and running large meetings.</span></span>

<div>

## <a name="q-how-many-users-can-participate-in-a-large-meeting"></a><span data-ttu-id="958d9-105">P: Quantos usuários podem participar de uma grande reunião?</span><span class="sxs-lookup"><span data-stu-id="958d9-105">Q: How many users can participate in a large meeting?</span></span>

<span data-ttu-id="958d9-106">O modelo de usuário do Lync Server especifica os limites de 250 usuários em um pool compartilhado ou 1000 usuários em um pool dedicado a grandes reuniões, mas esses números representam apenas o número de usuários testados e apenas para o conjunto específico de hardware que usamos em nossos testes.</span><span class="sxs-lookup"><span data-stu-id="958d9-106">The Lync Server user model specifies limits of 250 users in a shared pool or 1000 users in a pool dedicated to large meetings, but these numbers only represent the number of users we tested and only for the specific set of hardware that we used in our testing.</span></span> <span data-ttu-id="958d9-107">Com base nos testes, é recomendável manter esses limites para tamanhos máximos.</span><span class="sxs-lookup"><span data-stu-id="958d9-107">Based on our testing, we recommend those limits for maximum sizes.</span></span> <span data-ttu-id="958d9-108">No entanto, você controla o número real de participantes permitidos em reuniões em sua organização Configurando uma ou mais políticas de conferência (que você configura usando os cmdlets do Windows PowerShell no Shell de gerenciamento do Lync Server ou usando o Lync Server Painel de controle).</span><span class="sxs-lookup"><span data-stu-id="958d9-108">However, you control the actual number of participants allowed in meetings in your organization by configuring one or more conferencing policies (which you configure using Windows PowerShell cmdlets in the Lync Server Management Shell or using the Lync Server Control Panel).</span></span> <span data-ttu-id="958d9-109">O número especificado em uma política de conferência pode ser qualquer número inteiro de 32 bits entre 1 e 4.294.967.295, mas o tamanho recomendado está entre 2 e 250 participantes e o valor padrão é 250.</span><span class="sxs-lookup"><span data-stu-id="958d9-109">The number that you specify in a conferencing policy can be any 32-bit whole number between 1 and 4,294,967,295, but the recommended size is between 2 and 250 participants, inclusive; and the default value is 250.</span></span>

</div>

<div>

## <a name="q-how-many-meetings-or-other-workloads-can-i-have-in-a-pool-that-is-dedicated-to-large-meetings"></a><span data-ttu-id="958d9-110">P: Quantas reuniões ou cargas de trabalho posso ter em um pool dedicado a grandes reuniões?</span><span class="sxs-lookup"><span data-stu-id="958d9-110">Q: How many meetings or other workloads can I have in a pool that is dedicated to large meetings?</span></span>

<span data-ttu-id="958d9-p102">Para assegurar a melhor experiência do usuário em grandes reuniões de até 1.000 participantes, é recomendável hospedar apenas uma única grande reunião por vez em um pool dedicado a grandes reuniões. É recomendável também não permitir que nenhuma outra carga de trabalho seja executada no pool enquanto a grande reunião estiver em andamento.</span><span class="sxs-lookup"><span data-stu-id="958d9-p102">To ensure the best user experience in large meetings of up to 1000 participants, we recommend hosting only a single large meeting at a time on a pool that is dedicated to large meetings. We also recommend not allowing any other workloads to run on that pool when the large meeting is in progress.</span></span>

</div>

<div>

## <a name="q-should-the-organizers-of-large-meeting-be-homed-on-the-dedicated-pool"></a><span data-ttu-id="958d9-113">P: Os organizadores de grandes reuniões devem ser hospedados no pool dedicado?</span><span class="sxs-lookup"><span data-stu-id="958d9-113">Q: Should the organizers of large meeting be homed on the dedicated pool?</span></span>

<span data-ttu-id="958d9-p103">Não. É recomendável não hospedar nenhum usuário além da equipe dedicada que gerencia o agendamento de grandes reuniões no pool dedicado. Isso impede que outras comunicações em tempo real causem problemas com as grandes reuniões hospedadas no pool. Você deve agendar grandes reuniões no pool dedicado usando uma conta de usuário da equipe de agendamento da grande reunião. Você deve adicionar a conta de usuário do organizador da reunião (o usuário que solicita uma grande reunião) como um apresentador da grande reunião.</span><span class="sxs-lookup"><span data-stu-id="958d9-p103">No. We recommend not homing any users other than the dedicated staff that manages scheduling of large meetings on the dedicated pool. This prevents other real-time communications traffic from causing problems with large meetings that are hosted in the pool. You should schedule large meetings on the dedicated pool using a user account of the large meeting scheduling staff. You should add the user account of the meeting organizer (the user who requests a large meeting) as a presenter for the large meeting.</span></span>

</div>

<div>

## <a name="q-what-media-modalities-can-i-use-in-a-large-meeting"></a><span data-ttu-id="958d9-119">P: Quais são as modalidades de mídia que posso usar em uma grande reunião?</span><span class="sxs-lookup"><span data-stu-id="958d9-119">Q: What media modalities can I use in a large meeting?</span></span>

<span data-ttu-id="958d9-120">As grandes reuniões com até 1.000 usuários podem conter áudio, vídeo, compartilhamento do PowerPoint, quadros de comunicações e  sondagem de presença.</span><span class="sxs-lookup"><span data-stu-id="958d9-120">Large meetings with up to 1000 users can include audio, video, PowerPoint sharing, whiteboards, and presence polling.</span></span>

</div>

<div>

## <a name="q-can-i-use-group-instant-messaging-im-in-large-meetings"></a><span data-ttu-id="958d9-121">P: Posso usar IM (mensagens instantâneas) em grupo nas grandes reuniões?</span><span class="sxs-lookup"><span data-stu-id="958d9-121">Q: Can I use group instant messaging (IM) in large meetings?</span></span>

<span data-ttu-id="958d9-122">Sim.</span><span class="sxs-lookup"><span data-stu-id="958d9-122">Yes.</span></span> <span data-ttu-id="958d9-123">No entanto, grandes números de mensagens instantâneas, especialmente quando enviadas por um grande número de participantes da reunião, podem afetar a experiência do usuário devido a problemas com a rolagem rápida do texto na janela de IM.</span><span class="sxs-lookup"><span data-stu-id="958d9-123">However, large numbers of instant messages, especially when sent by a large number of meeting participants, can affect the user experience due to problems with fast text scrolling in the IM window.</span></span> <span data-ttu-id="958d9-124">A entrega de uma grande quantidade de mensagens instantâneas de até 1.000 usuários também pode introduzir cargas significativas do servidor, o que pode afetar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="958d9-124">Delivering a large amount of instant messages to up to 1000 users can also introduce significant server loads, which can affect performance.</span></span> <span data-ttu-id="958d9-125">Geralmente, o IM só é necessário para perguntas e respostas (\&p as).</span><span class="sxs-lookup"><span data-stu-id="958d9-125">Generally, IM is only required for questions and answers (Q\&As).</span></span>

</div>

<div>

## <a name="can-users-join-large-meetings-by-dialing-in-from-a-phone"></a><span data-ttu-id="958d9-126">P: Os usuários podem participar de grandes reuniões ligando de um telefone?</span><span class="sxs-lookup"><span data-stu-id="958d9-126">Can users join large meetings by dialing in from a phone?</span></span>

<span data-ttu-id="958d9-127">Sim.</span><span class="sxs-lookup"><span data-stu-id="958d9-127">Yes.</span></span> <span data-ttu-id="958d9-128">Se o pool do Lync Server 2013 estiver implantado e habilitado corretamente para conferência discada, os usuários poderão participar de grandes reuniões por discagem.</span><span class="sxs-lookup"><span data-stu-id="958d9-128">If the Lync Server 2013 pool is properly deployed and enabled for dial-in conferencing, users will be able to join the large meetings by dialing in.</span></span> <span data-ttu-id="958d9-129">Nossos testes mostraram que até 15% dos 1.000 usuários podem participar de uma grande reunião por um período de 10 minutos.</span><span class="sxs-lookup"><span data-stu-id="958d9-129">Our testing has shown that up to 15% of the 1000 users can join the large meeting over a 10 minute period.</span></span>

</div>

<div>

## <a name="q-can-i-host-large-meetings-in-a-virtual-topology"></a><span data-ttu-id="958d9-130">P: Posso hospedar grandes reuniões em uma topologia virtual?</span><span class="sxs-lookup"><span data-stu-id="958d9-130">Q: Can I host large meetings in a virtual topology?</span></span>

<span data-ttu-id="958d9-131">As grandes reuniões ainda não foram testadas em uma topologia virtual, portanto não há suporte para o uso de máquinas virtuais a fim de hospedar um pool dedicado a grandes reuniões.</span><span class="sxs-lookup"><span data-stu-id="958d9-131">We have not tested large meetings in a virtual topology, so we do not support the use of virtual machines to host a dedicated pool for large meetings.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

