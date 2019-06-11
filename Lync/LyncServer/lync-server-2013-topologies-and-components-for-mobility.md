---
title: 'Lync Server 2013: Topologia e componentes para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 537eda14f2587e06bd8a1112f2a6a44299b0b78e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844593"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="51ec0-102">Topologia e componentes para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51ec0-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="51ec0-103">_**Tópico da última modificação:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="51ec0-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="51ec0-104">Para dar suporte a aplicativos móveis do Lync em dispositivos móveis, o Lync Server 2013 oferece três serviços: Lync Server 2013 MCX Mobility Service, Lync Server 2013 autodiscover Service e Lync Server 2013 Push Notification Service.</span><span class="sxs-lookup"><span data-stu-id="51ec0-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="51ec0-105">As atualizações cumulativas do Lync Server 2013:2013 de fevereiro adicionam um serviço gratuito, mas avançado, para clientes móveis do Lync 2013 — suporte à mobilidade por meio do uso da API da Web de comunicação unificada ou UCWA.</span><span class="sxs-lookup"><span data-stu-id="51ec0-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="51ec0-106">Esta seção descreve brevemente esses componentes e identifica as topologias do Lync Server 2013 que dão suporte à mobilidade.</span><span class="sxs-lookup"><span data-stu-id="51ec0-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="51ec0-107">Serviços de mobilidade também estão disponíveis em implantações híbridas.</span><span class="sxs-lookup"><span data-stu-id="51ec0-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="51ec0-108">Você não é obrigado a implantar serviços para oferecer suporte à mobilidade se seus usuários estiverem em casa online.</span><span class="sxs-lookup"><span data-stu-id="51ec0-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="51ec0-109">Você precisa definir uma configuração para o serviço de descoberta automática para permitir que os usuários móveis encontrem sua identidade online.</span><span class="sxs-lookup"><span data-stu-id="51ec0-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="51ec0-110">Se você estiver planejando qualquer conectividade de usuário externa (por exemplo, Federação, acesso de usuário externo ou recursos de mobilidade), você deve usar servidores de borda com o servidor Standard Edition e o servidor front-end ou o pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="51ec0-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="51ec0-111">O servidor Standard Edition e o servidor front-end ou o pool de front-end não têm os componentes necessários para permitir que os usuários externos acessem sua implantação interna ou para que a implantação interna se comunique com os usuários externos.</span><span class="sxs-lookup"><span data-stu-id="51ec0-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="51ec0-112">Para todos os cenários que incluem usuários externos que colaboram ou se comunicam com usuários internos, incluindo mobilidade, você deve implantar pelo menos um servidor de borda e um proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="51ec0-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="51ec0-113">A <EM>notificação por push</EM> usa um tipo de Federação para os serviços do Lync Online, que hospeda a casa de compensação de notificação por push (PNCH).</span><span class="sxs-lookup"><span data-stu-id="51ec0-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="51ec0-114">A notificação por Push se refere a alertas sonoros, alertas na tela (texto) e selos que são enviados por aplicativos para o iPhone, iPad e Windows Phone da Apple, quando o dispositivo móvel está inativo.</span><span class="sxs-lookup"><span data-stu-id="51ec0-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="51ec0-115">O PNCH recebe notificações por push do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="51ec0-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="51ec0-116">Quando o PNCH recebe uma notificação de uma mensagem, o PNCH encaminha uma notificação para clientes móveis por meio do serviço de notificação por push do Apple ou do Lync Server 2013, com base no cliente móvel para o qual a mensagem se destina.</span><span class="sxs-lookup"><span data-stu-id="51ec0-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="51ec0-117">O PNCH é um serviço obrigatório para esses clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="51ec0-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="51ec0-118">Para federar o Lync Online, o PNCH usa servidores de borda e certificados para garantir confidencialidade e autenticação, políticas e registros DNS (Domain Name System) configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="51ec0-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="51ec0-119">Os clientes móveis do Lync Symbian e Android baseados em Android não usam o PNCH.</span><span class="sxs-lookup"><span data-stu-id="51ec0-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="51ec0-120">Para obter detalhes sobre o planejamento e a implantação de servidores de borda, consulte <A href="lync-server-2013-planning-for-external-user-access.md">planejando o acesso de usuários externos no Lync server 2013</A> e implantando o <A href="lync-server-2013-deploying-external-user-access.md">acesso de usuários externos no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="51ec0-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="51ec0-121">Os clientes móveis do Lync 2013 para dispositivos Apple introduzidos com as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 não usam mais a notificação por Push ou a casa de compensação de notificação por push (PNCH).</span><span class="sxs-lookup"><span data-stu-id="51ec0-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="51ec0-122">Os clientes móveis do Lync 2013 no Windows Phone ainda usam a notificação por push e o (PNCH).</span><span class="sxs-lookup"><span data-stu-id="51ec0-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="51ec0-123">Componentes da mobilidade</span><span class="sxs-lookup"><span data-stu-id="51ec0-123">Mobility Components</span></span>

<span data-ttu-id="51ec0-124">Os serviços que dão suporte à mobilidade são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="51ec0-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="51ec0-125">**A API da Web de comunicação unificada do Lync Server 2013 (UCWA)**   fornece serviços para comunicações em tempo real com clientes móveis e Web no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51ec0-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="51ec0-126">Ao implantar as atualizações cumulativas do Lync Server 2013:2013 de fevereiro para o servidor e diretor de front-end, a instalação cria um diretório virtual nos serviços Web internos e externos (Ucwa).</span><span class="sxs-lookup"><span data-stu-id="51ec0-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="51ec0-127">Um componente da Web que faz parte do diretório virtual Ucwa aceita chamadas de clientes habilitados para UCWA.</span><span class="sxs-lookup"><span data-stu-id="51ec0-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="51ec0-128">Os aplicativos cliente se comunicam em uma interface REST para presença, contatos, mensagens instantâneas, VoIP, videoconferência e colaboração.</span><span class="sxs-lookup"><span data-stu-id="51ec0-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="51ec0-129">O UCWA usa um canal baseado em P para enviar eventos, como uma chamada recebida, mensagem de chat recebida ou uma mensagem para o aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="51ec0-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="51ec0-130">A transferência de estado <EM>REST</EM> ou Representational é um estilo arquitetônico de software para sistemas distribuídos que foram amplamente adotados em muitos formatos e é bem adequado aos requisitos dos serviços Web em geral.</span><span class="sxs-lookup"><span data-stu-id="51ec0-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="51ec0-131">**Serviço de mobilidade do Lync Server 2013 (MCX)**   esse serviço é compatível com a funcionalidade do Lync, como mensagens instantâneas (IM), presença e contatos, em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="51ec0-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="51ec0-132">O serviço de mobilidade está instalado em cada servidor front-end em cada pool que tem suporte à funcionalidade do Lync em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="51ec0-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="51ec0-133">Quando você instala o Lync Server 2013, um novo diretório virtual (MCX) é criado em ambos os sites internos e externos em seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="51ec0-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="51ec0-134">Lync Server 2013 com as atualizações cumulativas do Lync Server 2013:2013 de fevereiro suporta o serviço de mobilidade apresentado na atualização cumulativa do Lync Server 2010: novembro de 2011, geralmente conhecida como MCX, e o componente da Web do UCWA.</span><span class="sxs-lookup"><span data-stu-id="51ec0-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="51ec0-135">A combinação desses dois serviços de mobilidade fornece interoperabilidade e uso por usuários com os clientes Lync 2010 Mobile e Lync 2013 Mobile no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="51ec0-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="51ec0-136">**Serviço de descoberta automática do Lync Server 2013**   esse serviço identifica a localização do usuário e permite que dispositivos móveis e outros clientes do Lync localizem recursos, como URLs internas e externas dos serviços da Web do Lync Server 2013 e a URL do MCX ou UCWA, independentemente do local de rede.</span><span class="sxs-lookup"><span data-stu-id="51ec0-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="51ec0-137">A descoberta automática usa nomes de host codificados (lyncdiscoverinternal para usuários dentro da rede; lyncdiscover para usuários fora da rede) e o domínio SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="51ec0-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="51ec0-138">Ela dá suporte a conexões de clientes que usam HTTP ou HTTPS.</span><span class="sxs-lookup"><span data-stu-id="51ec0-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="51ec0-139">O serviço de descoberta automática está instalado em cada servidor front-end e em cada director em cada pool compatível com a funcionalidade do Lync em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="51ec0-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="51ec0-140">Quando você instala o serviço de descoberta automática, um novo diretório virtual (descoberta automática) é criado no site interno e no site externo, em servidores e directors de front-end.</span><span class="sxs-lookup"><span data-stu-id="51ec0-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="51ec0-141">O serviço descoberta automática está listado aqui porque continua sendo um componente essencial ao oferecer serviços de cliente móvel.</span><span class="sxs-lookup"><span data-stu-id="51ec0-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="51ec0-142">A função de descoberta automática no Lync Server 2013 foi expandida para fornecer serviços para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="51ec0-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="51ec0-143">Para obter detalhes sobre o planejamento do serviço de descoberta automática, consulte <A href="lync-server-2013-planning-for-autodiscover.md">planejando para descoberta automática no Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="51ec0-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="51ec0-144">**Serviço de notificação por push**   esse serviço é um serviço baseado em nuvem localizado no centro de dados do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="51ec0-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="51ec0-145">Quando o aplicativo móvel do Lync em um dispositivo Apple iOS compatível ou Windows Phone está inativo, ele não pode responder a novos eventos, como um novo convite de mensagens instantâneas (IM), uma mensagem instantânea perdida, uma chamada perdida ou caixa postal, pois esses dispositivos não dão suporte a aplicativos móveis em execução em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="51ec0-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="51ec0-146">Nesses casos, uma notificação do novo evento, chamada de *notificação por push*, é enviada para o dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="51ec0-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="51ec0-147">O serviço de mobilidade envia a notificação para o serviço de notificação por push baseado na nuvem, que envia a notificação para o serviço de notificação por push da Apple (APNS) (para dispositivos Apple iOS compatíveis) ou para o serviço de notificação por push da Microsoft (MPNS ) (para Windows Phone), que o envia para o dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="51ec0-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="51ec0-148">Em seguida, o usuário pode responder à notificação no dispositivo móvel para ativar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="51ec0-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="51ec0-149">O Lync 2010 móvel no Apple e dispositivos Windows Phone usam notificações por push.</span><span class="sxs-lookup"><span data-stu-id="51ec0-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="51ec0-150">O cliente móvel do Lync 2013 para dispositivos Apple introduzido com as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 não usa mais a notificação por Push ou a casa de compensação de notificação por push (PNCH).</span><span class="sxs-lookup"><span data-stu-id="51ec0-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="51ec0-151">O diagrama a seguir ilustra como o serviço de notificação por Push se encaixa em uma topologia do Lync Server 2013 que usa UCWA e clientes móveis do Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="51ec0-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="51ec0-152">![166d60fd-ff71-4FFE-9f66-3c8bbde0b5ae] (images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4FFE-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="51ec0-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="51ec0-153">Apresentado na atualização cumulativa do Lync Server 2010:2011 de novembro, o serviço MCX fornece serviços para clientes móveis do Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="51ec0-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="51ec0-154">O diagrama a seguir ilustra o serviço de notificação por push como ele se aplica a uma topologia usando clientes móveis MCX e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="51ec0-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="51ec0-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f] (images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="51ec0-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="51ec0-156">Topologias suportadas</span><span class="sxs-lookup"><span data-stu-id="51ec0-156">Supported Topologies</span></span>

<span data-ttu-id="51ec0-157">Aplicar as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 adiciona os componentes da Web do UCWA para dar suporte a mobilidade para recursos de cliente móvel do Lync 2013 nas seguintes topologias:</span><span class="sxs-lookup"><span data-stu-id="51ec0-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="51ec0-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="51ec0-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="51ec0-159">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="51ec0-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="51ec0-160">O servidor de borda pode ser um servidor de borda do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="51ec0-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="51ec0-161">Uma implantação do Lync Server 2013 sem as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 usará o serviço de mobilidade do MCX e poderá fornecer serviços somente para o Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="51ec0-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="51ec0-162">O serviço de mobilidade tem suporte em servidores front-end posicionados com a função de servidor de mediação com duas interfaces de rede, mas você deve tomar as medidas adequadas para configurar as interfaces.</span><span class="sxs-lookup"><span data-stu-id="51ec0-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="51ec0-163">Você deve atribuir os endereços IP para a interface específica que se comunicará como servidor de mediação e o IP da interface de rede que se comunicará como servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="51ec0-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="51ec0-164">Você pode fazer isso no construtor de topologias selecionando o endereço IP correto para cada serviço, em vez de usar o padrão <STRONG>usar todos os endereços IP</STRONG>configurados.</span><span class="sxs-lookup"><span data-stu-id="51ec0-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="51ec0-165">Confira também</span><span class="sxs-lookup"><span data-stu-id="51ec0-165">See Also</span></span>


[<span data-ttu-id="51ec0-166">Planejamento para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51ec0-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="51ec0-167">Implantação de acesso do usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51ec0-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="51ec0-168">Planejando a descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="51ec0-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

