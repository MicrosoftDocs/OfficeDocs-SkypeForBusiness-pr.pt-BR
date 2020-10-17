---
title: 'Lync Server 2013: recursos e recursos de mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Mobility features and capabilities
ms:assetid: 12517a88-2531-44a5-bea5-d8884aff53eb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh689983(v=OCS.15)
ms:contentKeyID: 48183457
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3eecf3d55ba3bb8e8629d41a9a924c65ac7a4c0e
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48516128"
---
# <a name="mobility-features-and-capabilities-in-lync-server-2013"></a><span data-ttu-id="577cc-102">Recursos e recursos de mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="577cc-102">Mobility features and capabilities in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="577cc-103">_**Última modificação do tópico:** 2013-02-19_</span><span class="sxs-lookup"><span data-stu-id="577cc-103">_**Topic Last Modified:** 2013-02-19_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="577cc-104">O recurso de mobilidade apresentado nas atualizações cumulativas do Lync Server 2013: fevereiro de 2013 oferece suporte à funcionalidade de clientes móveis do Lync 2010 Mobile e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="577cc-104">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2010 Mobile and Lync 2013 Mobile clients functionality.</span></span> <span data-ttu-id="577cc-105">Quando você implanta o serviço de mobilidade do Lync Server 2013, os usuários podem usar os dispositivos móveis Apple iOS, Android e Windows Phone compatíveis, ou dispositivos móveis Nokia Symbian para realizar atividades, como enviar e receber mensagens instantâneas, exibir contatos e ver a presença.</span><span class="sxs-lookup"><span data-stu-id="577cc-105">When you deploy the Lync Server 2013 Mobility Service, users can use supported Apple iOS, Android, and Windows Phone, or Nokia Symbian mobile devices to perform activities such as sending and receiving instant messages, viewing contacts, and viewing presence.</span></span> <span data-ttu-id="577cc-106">Além disso, os dispositivos móveis suportam alguns recursos do Enterprise Voice, como clicar para participar de uma conferência, Chamada via Trabalho, acesso a único número, caixa postal e chamadas perdidas.</span><span class="sxs-lookup"><span data-stu-id="577cc-106">In addition, mobile devices support some Enterprise Voice features, such as click to join a conference, Call via Work, single number reach, voice mail, and missed calls.</span></span> <span data-ttu-id="577cc-107">Novos recursos introduzidos nas atualizações cumulativas do Lync Server 2013: fevereiro de 2013 incluem recursos de voz sobre IP (VoIP) e vídeo (H. 264) para o participante da reunião.</span><span class="sxs-lookup"><span data-stu-id="577cc-107">New features introduced in the Cumulative Updates for Lync Server 2013: February 2013 include Voice over IP (VoIP) capability and video (H.264) for meeting attendee.</span></span>

<span data-ttu-id="577cc-108">O recurso de mobilidade apresentado nas atualizações cumulativas do Lync Server 2013: fevereiro de 2013 oferece suporte à funcionalidade de cliente móvel do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="577cc-108">The mobility feature introduced in the Cumulative Updates for Lync Server 2013: February 2013 supports Lync 2013 Mobile client functionality.</span></span> <span data-ttu-id="577cc-109">As atualizações cumulativas do Lync Server 2013: fevereiro de 2013 instalar a API da Web de comunicações unificadas ou UCWA.</span><span class="sxs-lookup"><span data-stu-id="577cc-109">The Cumulative Updates for Lync Server 2013: February 2013 install Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="577cc-110">UCWA é o componente usado para clientes móveis do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="577cc-110">UCWA is the component used for Lync 2013 Mobile clients.</span></span> <span data-ttu-id="577cc-111">No Lync Server 2013, MCX é usado para clientes móveis do Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="577cc-111">In Lync Server 2013, Mcx is used for Lync 2010 Mobile clients.</span></span> <span data-ttu-id="577cc-112">Atualizações cumulativas do Lync Server 2013: fevereiro de 2013 Introduza UCWA como o novo ponto de entrada para serviços de mobilidade.</span><span class="sxs-lookup"><span data-stu-id="577cc-112">Cumulative Updates for Lync Server 2013: February 2013 introduce UCWA as the new entry point for mobility services.</span></span> <span data-ttu-id="577cc-113">Lync Server 2013 implementa o serviço de mobilidade (MCX) simultaneamente, introduzido nas atualizações cumulativas do Lync Server 2010: de novembro de 2011 e fornece suporte para o Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="577cc-113">Lync Server 2013 concurrently implements the Mobility Service (Mcx), introduced in the Cumulative Updates for Lync Server 2010: November 2011, and provides support for Lync 2010 Mobile.</span></span> <span data-ttu-id="577cc-114">Ao implantar as atualizações cumulativas do Lync Server 2013:2013 de fevereiro, os usuários podem usar os dispositivos móveis Apple iOS, Android e Windows Phone compatíveis para executar essas atividades como:</span><span class="sxs-lookup"><span data-stu-id="577cc-114">When you deploy the Cumulative Updates for Lync Server 2013: February 2013, users can use supported Apple iOS, Android, and Windows Phone mobile devices to perform such activities as:</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="577cc-115">Recursos com suporte do serviço de mobilidade das atualizações cumulativas para Lync Server 2010: novembro de 2011 são observados com (MCX).</span><span class="sxs-lookup"><span data-stu-id="577cc-115">Features supported by the Mobility Service from the Cumulative Updates for Lync Server 2010: November 2011 are noted with (Mcx).</span></span> <span data-ttu-id="577cc-116">Todos os recursos listados têm suporte no UCWA, introduzidos nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="577cc-116">All listed features are supported by the UCWA, introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>



</div>

  - <span data-ttu-id="577cc-117">Enviar e receber mensagens instantâneas (MCX)</span><span class="sxs-lookup"><span data-stu-id="577cc-117">Send and receive instant messages (Mcx)</span></span>

  - <span data-ttu-id="577cc-118">Exibir presença (MCX)</span><span class="sxs-lookup"><span data-stu-id="577cc-118">View presence (Mcx)</span></span>

  - <span data-ttu-id="577cc-119">Exibir Contatos (MCX)</span><span class="sxs-lookup"><span data-stu-id="577cc-119">View contacts (Mcx)</span></span>

  - <span data-ttu-id="577cc-120">Clique para ingressar em uma conferência (MCX)</span><span class="sxs-lookup"><span data-stu-id="577cc-120">Click to join a conference (Mcx)</span></span>

  - <span data-ttu-id="577cc-121">Chamada via trabalho (MCX)</span><span class="sxs-lookup"><span data-stu-id="577cc-121">Call via work (Mcx)</span></span>

  - <span data-ttu-id="577cc-122">Alcance de número único (MCX)</span><span class="sxs-lookup"><span data-stu-id="577cc-122">Single number reach (Mcx)</span></span>

  - <span data-ttu-id="577cc-123">Caixa postal (MCX)</span><span class="sxs-lookup"><span data-stu-id="577cc-123">Voice mail (Mcx)</span></span>

  - <span data-ttu-id="577cc-124">Notificação de chamada não atendida (MCX)</span><span class="sxs-lookup"><span data-stu-id="577cc-124">Missed call notification (Mcx)</span></span>

  - <span data-ttu-id="577cc-125">Voice over IP (VoIP)</span><span class="sxs-lookup"><span data-stu-id="577cc-125">Voice over IP (VoIP)</span></span>

  - <span data-ttu-id="577cc-126">Vídeo de participante (H. 264)</span><span class="sxs-lookup"><span data-stu-id="577cc-126">Attendee video (H.264)</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="577cc-127">Lync 2010 Mobile fornecia um cliente para dispositivos Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="577cc-127">Lync 2010 Mobile provided a client for Nokia Symbian devices.</span></span> <span data-ttu-id="577cc-128">O Lync 2013 Mobile não terá um cliente para dispositivos baseados em Nokia Symbian.</span><span class="sxs-lookup"><span data-stu-id="577cc-128">Lync 2013 Mobile will not have a client for Nokia Symbian-based devices.</span></span>



</div>

<span data-ttu-id="577cc-129">Usuários do Apple iPad terão acesso a recursos avançados.</span><span class="sxs-lookup"><span data-stu-id="577cc-129">Apple iPad users will have access to enhanced capabilities.</span></span> <span data-ttu-id="577cc-130">Após ingressar em uma reunião usando o retorno de chamada de áudio, um usuário do iPad poderá exibir apresentações carregadas do Microsoft PowerPoint em uma reunião, compartilhar aplicativos e áreas de trabalho, exibir a lista de participantes da reunião e receber notificações de outros tipos de conteúdo que estão sendo compartilhados dentro da reunião.</span><span class="sxs-lookup"><span data-stu-id="577cc-130">After joining a meeting by using audio call back, an iPad user will be able to view uploaded Microsoft PowerPoint presentations within a meeting, share applications and desktops, view the meeting participant list, and receive notifications of other content types that are being shared within the meeting.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="577cc-131">Com o acesso a único número, um usuário recebe chamadas feitas para o número do trabalho em um celular.</span><span class="sxs-lookup"><span data-stu-id="577cc-131">With single number reach, a user receives calls on a mobile phone that were dialed to the work number.</span></span> <span data-ttu-id="577cc-132">Com a chamada via trabalho, o usuário faz uma chamada de saída do cliente móvel do Lync usando um número de telefone comercial em vez do número de telefone celular.</span><span class="sxs-lookup"><span data-stu-id="577cc-132">With Call via Work, the user places an outbound call from the Lync Mobile client by using a work phone number instead of the mobile phone number.</span></span> <span data-ttu-id="577cc-133">Com a discagem, o cliente envia uma solicitação para o MCX ou o UCWA (com base na versão do Lync Mobile) para fazer a chamada para eles.</span><span class="sxs-lookup"><span data-stu-id="577cc-133">With dial-out, the client sends a request to Mcx or UCWA (based on the Lync Mobile version) to make the call for them.</span></span> <span data-ttu-id="577cc-134">O servidor inicia a chamada e depois retorna a chamada no celular do usuário.</span><span class="sxs-lookup"><span data-stu-id="577cc-134">The server initiates the call and then calls the user back on the mobile phone.</span></span> <span data-ttu-id="577cc-135">Quando o usuário atende, o servidor completa a chamada discando para a outra parte.</span><span class="sxs-lookup"><span data-stu-id="577cc-135">When the user answers, the server completes the call by dialing the other party.</span></span> <span data-ttu-id="577cc-136">Usando o Chamada via Trabalho, os usuários podem manter sua identidade de trabalho durante uma chamada, o que significa que o destinatário da chamada não visualiza o número de celular do chamador, e este evita incorrer em tarifas da chamada de saída.</span><span class="sxs-lookup"><span data-stu-id="577cc-136">By using Call via Work, users can maintain their work identity during a call, which means that the call recipient does not see the caller's mobile number, and the caller avoids incurring outbound calling charges.</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="577cc-137">Nem todos os recursos funcionam exatamente da mesma forma em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="577cc-137">Not all features work exactly the same on all mobile devices.</span></span> <span data-ttu-id="577cc-138">Para obter detalhes sobre os recursos suportados em dispositivos móveis, consulte as tabelas de comparação de clientes móveis em <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A> .</span><span class="sxs-lookup"><span data-stu-id="577cc-138">For details about features supported on mobile devices, see the Mobile Client Comparison Tables at <A href="https://go.microsoft.com/fwlink/p/?linkid=234777">https://go.microsoft.com/fwlink/p/?LinkId=234777</A>.</span></span> <span data-ttu-id="577cc-139">Para obter detalhes sobre dispositivos e sistemas operacionais com suporte, consulte os tópicos requirements em <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for Mobile clients in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="577cc-139">For details about supported devices and operating systems, see the requirements topics under <A href="lync-server-2013-planning-for-mobile-clients.md">Planning for mobile clients in Lync Server 2013</A>.</span></span>



</div>

<span data-ttu-id="577cc-140">Quando você usa o recurso de descoberta automática do Lync Server 2013, os aplicativos móveis podem localizar automaticamente os serviços Web do Lync Server 2013, sem exigir que os usuários insiram manualmente as URLs em suas configurações de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="577cc-140">When you use the Lync Server 2013 Autodiscover feature, mobile applications can automatically locate Lync Server 2013 Web Services without requiring users to manually enter the URLs in their device settings.</span></span> <span data-ttu-id="577cc-141">A inserção manual de URLs nas configurações do dispositivo móvel também é suportada, principalmente para fins de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="577cc-141">Manually entering URLs in mobile device settings is also supported, primarily for troubleshooting purposes.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="577cc-142">O MCX e o UCWA são serviços complementares e ambos são implantados para oferecer suporte aos clientes móveis do Lync 2010 Mobile e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="577cc-142">The Mcx and UCWA are complimentary services and both are deployed to support Lync 2010 Mobile and Lync 2013 Mobile clients.</span></span> <span data-ttu-id="577cc-143">Lync 2013 Mobile não poderá entrar no Lync Server 2010 implantações.</span><span class="sxs-lookup"><span data-stu-id="577cc-143">Lync 2013 Mobile will not be able to sign in to Lync Server 2010 deployments.</span></span> <span data-ttu-id="577cc-144">Lync 2010 Mobile e Lync 2013 Mobile poderão usar uma implantação do Lync Server 2013 com as atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="577cc-144">Lync 2010 Mobile and Lync 2013 Mobile will be able to use a Lync Server 2013 deployment with the Cumulative Updates for Lync Server 2013: February 2013 applied.</span></span>



</div>

<span data-ttu-id="577cc-145">O recurso de mobilidade também oferece suporte a *notificações por push* para dispositivos móveis que não oferecem suporte a aplicativos em execução em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="577cc-145">The mobility feature also supports *push notifications* for mobile devices that do not support applications running in the background.</span></span> <span data-ttu-id="577cc-146">Uma notificação por push é uma notificação enviada a um dispositivo móvel sobre um evento que ocorre enquanto o aplicativo móvel está inativo.</span><span class="sxs-lookup"><span data-stu-id="577cc-146">A push notification is a notification that is sent to a mobile device about an event that occurs while a mobile application is inactive.</span></span> <span data-ttu-id="577cc-147">Por exemplo, um convite perdido de mensagens instantâneas (IM) pode resultar em uma notificação por push.</span><span class="sxs-lookup"><span data-stu-id="577cc-147">For example, a missed instant messaging (IM) invitation can result in a push notification.</span></span>

<span data-ttu-id="577cc-148">O MCX, o UCWA, o serviço de descoberta automática e o suporte para notificações por push são fornecidos no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="577cc-148">Mcx, UCWA, Autodiscover Service, and support for push notifications are provided in Lync Server 2013.</span></span> <span data-ttu-id="577cc-149">Recursos de cliente atualizados, recursos e o uso do UCWA como o ponto de entrada de mobilidade são introduzidos nas atualizações cumulativas do Lync Server 2013:2013 de fevereiro.</span><span class="sxs-lookup"><span data-stu-id="577cc-149">Updated client features, capabilities, and the use of UCWA as the mobility entry point are introduced in the Cumulative Updates for Lync Server 2013: February 2013.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

