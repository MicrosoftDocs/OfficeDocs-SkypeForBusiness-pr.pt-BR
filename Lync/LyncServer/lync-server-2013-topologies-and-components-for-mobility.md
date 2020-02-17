---
title: 'Lync Server 2013: topologias e componentes para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Topologies and components for mobility
ms:assetid: be3cae7a-095d-4785-91ba-6fac99eba92a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690037(v=OCS.15)
ms:contentKeyID: 48185282
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ac03d6b98b0b209a50f08e660fe6665b975d2ce
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045523"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="topologies-and-components-for-mobility-in-lync-server-2013"></a><span data-ttu-id="711f4-102">Topologias e componentes para mobilidade no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="711f4-102">Topologies and components for mobility in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="711f4-103">_**Última modificação do tópico:** 2013-02-17_</span><span class="sxs-lookup"><span data-stu-id="711f4-103">_**Topic Last Modified:** 2013-02-17_</span></span>

    The information in this topic pertains to Cumulative Updates for Lync Server 2013: February 2013.

<span data-ttu-id="711f4-104">Para oferecer suporte a aplicativos móveis do Lync em dispositivos móveis, o Lync Server 2013 fornece três serviços: Lync Server 2013 MCX Mobility Service, Lync Server 2013 autodiscover Service e Lync Server 2013 Push Notification Service.</span><span class="sxs-lookup"><span data-stu-id="711f4-104">To support Lync mobile applications on mobile devices, Lync Server 2013 provides three services: Lync Server 2013 Mcx Mobility Service, Lync Server 2013 Autodiscover Service, and Lync Server 2013 Push Notification Service.</span></span> <span data-ttu-id="711f4-105">As atualizações cumulativas do Lync Server 2013: fevereiro de 2013 adiciona um serviço gratuito, mas avançado para clientes móveis do Lync 2013, para obter suporte de mobilidade por meio do uso da API Web de comunicações unificadas ou UCWA.</span><span class="sxs-lookup"><span data-stu-id="711f4-105">The Cumulative Updates for Lync Server 2013: February 2013 adds a complimentary, but advanced, service for Lync 2013 Mobile clients—mobility support through the use of the Unified Communications Web API, or UCWA.</span></span> <span data-ttu-id="711f4-106">Esta seção descreve brevemente esses componentes e identifica as topologias do Lync Server 2013 que dão suporte à mobilidade.</span><span class="sxs-lookup"><span data-stu-id="711f4-106">This section briefly describes these components and identifies the Lync Server 2013 topologies that support mobility.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="711f4-107">Os serviços de mobilidade também estão disponíveis em implantações híbridas.</span><span class="sxs-lookup"><span data-stu-id="711f4-107">Mobility services are also available in hybrid deployments.</span></span> <span data-ttu-id="711f4-108">Não é necessário implantar serviços para suportar a mobilidade se os seus usuários estão hospedados online.</span><span class="sxs-lookup"><span data-stu-id="711f4-108">You are not required to deploy services for supporting mobility if your users are homed online.</span></span> <span data-ttu-id="711f4-109">Você precisa definir uma configuração para o serviço de descoberta automática para permitir que os usuários móveis encontrem sua identidade online.</span><span class="sxs-lookup"><span data-stu-id="711f4-109">You do need to define a setting for the Autodiscover Service to enable mobile users to find their online identity.</span></span>



</div>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="711f4-110">Se você estiver planejando qualquer conectividade de usuário externa (por exemplo, Federação, acesso de usuário externo ou recursos de mobilidade), deverá usar servidores de borda com o servidor Standard Edition e o servidor front-end ou o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="711f4-110">If you are planning any external user connectivity (for example, federation, external user access, or mobility features), you must use Edge Servers with Standard Edition server and the Front End Server or Front End pool.</span></span> <span data-ttu-id="711f4-111">O servidor Standard Edition e o servidor front-end ou o pool de front-ends não têm os componentes necessários para permitir que usuários externos acessem sua implantação interna ou para a implantação interna se comunicarem com os usuários externos.</span><span class="sxs-lookup"><span data-stu-id="711f4-111">The Standard Edition server and the Front End Server or Front End pool do not have the necessary components to enable external users to access your internal deployment, or for the internal deployment to communicate with your external users.</span></span> <span data-ttu-id="711f4-112">Para todos os cenários que incluem usuários externos que colaboram ou se comunicam com usuários internos, incluindo mobilidade, você deve implantar pelo menos um servidor de borda e um proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="711f4-112">For all scenarios that include external users collaborating or communicating with internal users, including mobility, you must deploy at least one Edge Server and one reverse proxy.</span></span><BR><span data-ttu-id="711f4-113">A <EM>notificação por push</EM> usa um tipo de Federação para os serviços do Lync Online, que hospeda a câmara de compensação de notificação por push (PNCH).</span><span class="sxs-lookup"><span data-stu-id="711f4-113"><EM>Push notification</EM> uses a type of federation to the Lync Online services, which hosts the Push Notification Clearing House (PNCH).</span></span> <span data-ttu-id="711f4-114">A notificação por push refere-se aos alertas sonoros, alertas na tela (texto) e selos que são enviados por aplicativos ao Apple iPhone, iPad e Windows Phone, quando o dispositivo móvel está inativo.</span><span class="sxs-lookup"><span data-stu-id="711f4-114">Push notification refers to the sound alerts, on-screen alerts (text), and badges that are pushed by applications to the Apple iPhone, iPad, and Windows Phone, when the mobile device is inactive.</span></span> <span data-ttu-id="711f4-115">PNCH recebe notificações por push do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="711f4-115">PNCH receives push notifications from Lync Server.</span></span> <span data-ttu-id="711f4-116">Quando o PNCH recebe uma notificação de uma mensagem, o PNCH encaminha uma notificação para clientes móveis através do Apple Push Notification Services ou do Lync Server 2013 Push Notification Service, com base no cliente móvel para o qual a mensagem é destinada.</span><span class="sxs-lookup"><span data-stu-id="711f4-116">When PNCH receives a notification of a message, PNCH forwards a notification to mobile clients through either the Apple Push Notification Services or Lync Server 2013 Push Notification Service, based on the mobile client that the message is intended for.</span></span> <span data-ttu-id="711f4-117">A PNCH é um serviço necessário para esses cliente móveis.</span><span class="sxs-lookup"><span data-stu-id="711f4-117">PNCH is a required service for these mobile clients.</span></span> <span data-ttu-id="711f4-118">Para federar o Lync Online, o PNCH usa servidores de borda e certificados para garantir confidencialidade e autenticação, políticas e registros de DNS (sistema de nomes de domínio) configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="711f4-118">To federate to Lync Online, PNCH uses Edge Servers and certificates to ensure confidentiality and authentication, policies, and correctly configured domain name system (DNS) records.</span></span> <span data-ttu-id="711f4-119">Os clientes móveis do Lync Symbian e com base em Android da Nokia não usam o PNCH.</span><span class="sxs-lookup"><span data-stu-id="711f4-119">Nokia Symbian and Android-based Lync Mobile clients do not use PNCH.</span></span> <span data-ttu-id="711f4-120">Para obter detalhes sobre como planejar e implantar servidores de borda, consulte <A href="lync-server-2013-planning-for-external-user-access.md">Planning for External User Access in Lync server 2013</A> e <A href="lync-server-2013-deploying-external-user-access.md">Deploying external User Access in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="711f4-120">For details about planning and deploying Edge Servers, see <A href="lync-server-2013-planning-for-external-user-access.md">Planning for external user access in Lync Server 2013</A> and <A href="lync-server-2013-deploying-external-user-access.md">Deploying external user access in Lync Server 2013</A>.</span></span><BR><span data-ttu-id="711f4-121">Os clientes móveis do Lync 2013 para dispositivos Apple introduzidos com as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 não usam mais a notificação por Push ou a casa de compensação de notificação por push (PNCH).</span><span class="sxs-lookup"><span data-stu-id="711f4-121">The Lync 2013 Mobile clients for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer use push notification or the push notification clearing house (PNCH).</span></span> <span data-ttu-id="711f4-122">Os clientes móveis do Lync 2013 no Windows Phone ainda usam a notificação por push e o (PNCH).</span><span class="sxs-lookup"><span data-stu-id="711f4-122">Lync 2013 Mobile clients on Windows Phone still use push notification and the (PNCH).</span></span>



</div>

<div>

## <a name="mobility-components"></a><span data-ttu-id="711f4-123">Componentes de mobilidade</span><span class="sxs-lookup"><span data-stu-id="711f4-123">Mobility Components</span></span>

<span data-ttu-id="711f4-124">Os serviços que suportam a mobilidade são:</span><span class="sxs-lookup"><span data-stu-id="711f4-124">The services that support mobility are as follows:</span></span>

  - <span data-ttu-id="711f4-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   fornece serviços para comunicação em tempo real com clientes móveis e da Web no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="711f4-125">**Lync Server 2013 Unified Communications Web API (UCWA)**   Provides services for real-time communications with mobile and web clients in Lync Server 2013.</span></span> <span data-ttu-id="711f4-126">Ao implantar as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 para o servidor front-end e diretor, a instalação cria um diretório virtual nos serviços Web internos e externos (Ucwa).</span><span class="sxs-lookup"><span data-stu-id="711f4-126">When you deploy the Cumulative Updates for Lync Server 2013: February 2013 to the Front End Server and Director, the installation creates a virtual directory in the internal and external web services (Ucwa).</span></span> <span data-ttu-id="711f4-127">Um componente da Web que faz parte do diretório virtual do Ucwa aceita chamadas de clientes habilitados para UCWA.</span><span class="sxs-lookup"><span data-stu-id="711f4-127">A web component that is part of the Ucwa virtual directory accepts calls from UCWA-enabled clients.</span></span> <span data-ttu-id="711f4-128">Os aplicativos cliente se comunicam por uma interface REST para presença, contatos, mensagens instantâneas, VoIP, conferência de vídeo e colaboração.</span><span class="sxs-lookup"><span data-stu-id="711f4-128">The client apps communicate over a REST interface for presence, contacts, instant messaging, VoIP, video conferencing, and collaboration.</span></span> <span data-ttu-id="711f4-129">O UCWA usa um canal baseado em P-GET para enviar eventos, como uma chamada de entrada, uma mensagem instantânea de entrada ou uma mensagem para o aplicativo cliente.</span><span class="sxs-lookup"><span data-stu-id="711f4-129">UCWA uses a P-GET based channel to send events, such as an incoming call, incoming instant message, or a message to the client app.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="711f4-130"><EM>REST</EM> ou Representational State Transfer, é um estilo de arquitetura de software para sistemas distribuídos que foram amplamente adotados em muitos formulários e é bem adequado para os requisitos de serviços Web em geral.</span><span class="sxs-lookup"><span data-stu-id="711f4-130"><EM>REST</EM> or representational state transfer, is a software architectural style for distributed systems that has been widely adopted in many forms and is well suited to the requirements of Web services in general.</span></span>

    
    </div>

  - <span data-ttu-id="711f4-131">**Lync Server 2013 Mobility Service (MCX)**   esse serviço oferece suporte à funcionalidade do Lync, como mensagens instantâneas (IM), presença e contatos, em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="711f4-131">**Lync Server 2013 Mobility Service (Mcx)**   This service supports Lync functionality, such as instant messaging (IM), presence, and contacts, on mobile devices.</span></span> <span data-ttu-id="711f4-132">O serviço de mobilidade é instalado em todos os servidores front-end em cada pool que oferece suporte à funcionalidade do Lync em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="711f4-132">The Mobility Service is installed on every Front End Server in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="711f4-133">Quando você instala o Lync Server 2013, um novo diretório virtual (MCX) é criado tanto no site interno quanto no site externo em seus servidores front-end.</span><span class="sxs-lookup"><span data-stu-id="711f4-133">When you install Lync Server 2013, a new virtual directory (Mcx) is created under both the internal website and the external website on your Front End Servers.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="711f4-134">Lync Server 2013 com as atualizações cumulativas para Lync Server 2013: fevereiro de 2013 suporta o serviço de mobilidade introduzido na atualização cumulativa do Lync Server 2010: novembro de 2011, comumente conhecido como MCX e o componente da Web do UCWA.</span><span class="sxs-lookup"><span data-stu-id="711f4-134">Lync Server 2013 with the Cumulative Updates for Lync Server 2013: February 2013 supports both the Mobility service introduced in the Cumulative Update for Lync Server 2010: November 2011, commonly known as Mcx, and the UCWA web component.</span></span> <span data-ttu-id="711f4-135">A combinação desses dois serviços de mobilidade oferece interoperabilidade e uso por usuários com clientes móveis do Lync 2010 e Lync 2013 no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="711f4-135">The combination of these two mobility services provides interoperability and use by users with Lync 2010 Mobile and Lync 2013 Mobile clients on Lync Server 2013.</span></span>

    
    </div>

  - <span data-ttu-id="711f4-136">**Lync Server 2013 serviço**   de descoberta automática este serviço identifica o local do usuário e permite que dispositivos móveis e outros clientes do Lync localizem recursos, como as URLs internas e externas para os serviços Web do Lync Server 2013 e a URL do MCX ou do UCWA, independentemente do local da rede.</span><span class="sxs-lookup"><span data-stu-id="711f4-136">**Lync Server 2013 Autodiscover Service**   This service identifies the location of the user and enables mobile devices and other Lync clients to locate resources—such as the internal and external URLs for Lync Server 2013 Web Services, and the URL for the Mcx or UCWA—regardless of network location.</span></span> <span data-ttu-id="711f4-137">A descoberta automática usa nomes de host codificados (lyncdiscoverinternal para usuários dentro da rede; lyncdiscover para usuários fora da rede) e o domínio SIP do usuário.</span><span class="sxs-lookup"><span data-stu-id="711f4-137">Automatic discovery uses hardcoded host names (lyncdiscoverinternal for users inside the network; lyncdiscover for users outside the network) and the SIP domain of the user.</span></span> <span data-ttu-id="711f4-138">Ele oferece suporte a conexões de clientes que usam HTTP ou HTTPS.</span><span class="sxs-lookup"><span data-stu-id="711f4-138">It supports client connections that use either HTTP or HTTPS.</span></span>
    
    <span data-ttu-id="711f4-139">O serviço de descoberta automática é instalado em todos os servidores front-end e em cada diretor de cada pool que oferece suporte à funcionalidade do Lync em dispositivos móveis.</span><span class="sxs-lookup"><span data-stu-id="711f4-139">The Autodiscover Service is installed on every Front End Server and on every Director in each pool that is to support Lync functionality on mobile devices.</span></span> <span data-ttu-id="711f4-140">Quando você instala o serviço de descoberta automática, um novo diretório virtual (descoberta automática) é criado no site interno e no site externo, em servidores front-end e diretores.</span><span class="sxs-lookup"><span data-stu-id="711f4-140">When you install the Autodiscover Service, a new virtual directory (Autodiscover) is created under both the internal website and the external website, on both Front End Servers and Directors.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="711f4-141">O serviço de descoberta automática está listado aqui porque continua sendo um componente crítico ao fornecer serviços de cliente móvel.</span><span class="sxs-lookup"><span data-stu-id="711f4-141">The Autodiscover Service is listed here because it remains a critical component when providing mobile client services.</span></span> <span data-ttu-id="711f4-142">A função de descoberta automática no Lync Server 2013 foi expandida para fornecer serviços para todos os clientes.</span><span class="sxs-lookup"><span data-stu-id="711f4-142">The role of Autodiscover in Lync Server 2013 has been expanded to provide services for all clients.</span></span> <span data-ttu-id="711f4-143">Para obter detalhes sobre o planejamento do serviço de descoberta automática, consulte <A href="lync-server-2013-planning-for-autodiscover.md">Planning for autodiscover in Lync Server 2013</A>.</span><span class="sxs-lookup"><span data-stu-id="711f4-143">For details about planning for the Autodiscover Service, see <A href="lync-server-2013-planning-for-autodiscover.md">Planning for Autodiscover in Lync Server 2013</A>.</span></span>

    
    </div>

  - <span data-ttu-id="711f4-144">**Serviço de notificação por push**   esse serviço é um serviço baseado em nuvem localizado no data center do Lync Online.</span><span class="sxs-lookup"><span data-stu-id="711f4-144">**Push Notification Service**   This service is a cloud-based service that is located in the Lync Online data center.</span></span> <span data-ttu-id="711f4-145">Quando o aplicativo móvel do Lync em um dispositivo Apple iOS com suporte ou no Windows Phone está inativo, ele não pode responder a novos eventos, como um novo convite de mensagens instantâneas (IM), uma mensagem instantânea perdida, uma chamada perdida ou uma caixa postal, pois esses dispositivos não dão suporte a aplicativos móveis executados em segundo plano.</span><span class="sxs-lookup"><span data-stu-id="711f4-145">When the Lync mobile application on a supported Apple iOS device or Windows Phone is inactive, it cannot respond to new events, such as a new instant messaging (IM) invitation, a missed instant message, a missed call, or voice mail, because these devices do not support mobile applications running in the background.</span></span> <span data-ttu-id="711f4-146">Nesses casos, uma notificação do novo evento – chamada de *notificação por push*, é enviada ao dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="711f4-146">In these cases, a notification of the new event—called a *push notification*—is sent to the mobile device.</span></span> <span data-ttu-id="711f4-147">O serviço de mobilidade envia a notificação para o serviço de notificação por push baseado em nuvem, que envia a notificação ao Apple Push Notification Service (APNS) (para dispositivos Apple iOS suportados) ou ao serviço de notificação por push da Microsoft (MPNS ) (para Windows Phone), que o envia para o dispositivo móvel.</span><span class="sxs-lookup"><span data-stu-id="711f4-147">The Mobility Service sends the notification to the cloud-based Push Notification Service, which then sends the notification either to the Apple Push Notification Service (APNS) (for supported Apple iOS devices) or to the Microsoft Push Notification Service (MPNS) (for Windows Phone), which then sends it on to the mobile device.</span></span> <span data-ttu-id="711f4-148">Em seguida, o usuário pode responder à notificação no dispositivo móvel para ativar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="711f4-148">The user can then respond to the notification on the mobile device to activate the application.</span></span>
    
    <span data-ttu-id="711f4-149">O Lync 2010 Mobile no Apple e dispositivos Windows Phone usam notificações por push.</span><span class="sxs-lookup"><span data-stu-id="711f4-149">The Lync 2010 Mobile on Apple and Windows Phone devices use push notifications.</span></span> <span data-ttu-id="711f4-150">O cliente móvel do Lync 2013 para dispositivos Apple apresentou as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 não usa mais a notificação por Push ou a casa de compensação de notificação por push (PNCH).</span><span class="sxs-lookup"><span data-stu-id="711f4-150">The Lync 2013 Mobile client for Apple devices introduced with the Cumulative Updates for Lync Server 2013: February 2013 no longer uses push notification or the push notification clearing house (PNCH).</span></span>

<span data-ttu-id="711f4-151">O diagrama a seguir ilustra como o serviço de notificação por Push se enquadra em uma topologia do Lync Server 2013 que usa clientes móveis UCWA e Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="711f4-151">The following diagram illustrates how the Push Notification Service fits within a Lync Server 2013 topology that uses UCWA and Lync 2013 Mobile clients.</span></span>

<span data-ttu-id="711f4-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span><span class="sxs-lookup"><span data-stu-id="711f4-152">![166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae](images/Hh690037.166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae(OCS.15).jpg "166d60fd-ff71-4ffe-9f66-3c8bbde0b5ae")</span></span>

<span data-ttu-id="711f4-153">Introduzido na atualização cumulativa do Lync Server 2010: novembro de 2011, o serviço MCX fornece serviços para clientes móveis do Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="711f4-153">Introduced in Cumulative Update for Lync Server 2010: November 2011, the Mcx service provides services to Lync 2010 Mobile clients.</span></span> <span data-ttu-id="711f4-154">O diagrama a seguir ilustra o serviço de notificação por push como ele se aplica a uma topologia usando clientes móveis do MCX e Lync 2010.</span><span class="sxs-lookup"><span data-stu-id="711f4-154">The following diagram illustrates the Push Notification Service as it applies to a topology using Mcx and Lync 2010 Mobile clients.</span></span>

<span data-ttu-id="711f4-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span><span class="sxs-lookup"><span data-stu-id="711f4-155">![3081634e-60e7-4348-b24e-bbbf05a90f5f](images/Hh690037.3081634e-60e7-4348-b24e-bbbf05a90f5f(OCS.15).jpg "3081634e-60e7-4348-b24e-bbbf05a90f5f")</span></span>

</div>

<div>

## <a name="supported-topologies"></a><span data-ttu-id="711f4-156">Topologias suportadas</span><span class="sxs-lookup"><span data-stu-id="711f4-156">Supported Topologies</span></span>

<span data-ttu-id="711f4-157">Aplicando as atualizações cumulativas do Lync Server 2013: fevereiro 2013 adiciona os componentes Web do UCWA para suportar a mobilidade para os recursos do cliente móvel do Lync 2013 nas seguintes topologias:</span><span class="sxs-lookup"><span data-stu-id="711f4-157">Applying the Cumulative Updates for Lync Server 2013: February 2013 adds the UCWA web components to support mobility for Lync 2013 Mobile client features in the following topologies:</span></span>

  - <span data-ttu-id="711f4-158">Lync Server 2013 Standard Edition</span><span class="sxs-lookup"><span data-stu-id="711f4-158">Lync Server 2013 Standard Edition</span></span>

  - <span data-ttu-id="711f4-159">Lync Server 2013 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="711f4-159">Lync Server 2013 Enterprise Edition</span></span>

<span data-ttu-id="711f4-160">O servidor de borda pode ser um servidor de borda do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="711f4-160">The Edge Server can be a Lync Server 2010 Edge Server.</span></span>

<span data-ttu-id="711f4-161">Uma implantação do Lync Server 2013 sem as atualizações cumulativas do Lync Server 2013: fevereiro de 2013 usará o serviço de mobilidade do MCX e só poderá fornecer serviços para o Lync 2010 Mobile.</span><span class="sxs-lookup"><span data-stu-id="711f4-161">A Lync Server 2013 deployment without the Cumulative Updates for Lync Server 2013: February 2013 will use the Mcx Mobility Service and can provide services only for Lync 2010 Mobile.</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="711f4-162">O serviço de mobilidade é suportado em servidores front-end posicionados com a função de servidor de mediação com duas interfaces de rede, mas você deve seguir as etapas apropriadas para configurar as interfaces.</span><span class="sxs-lookup"><span data-stu-id="711f4-162">The Mobility Service is supported on Front End Servers that is collocated with the Mediation Server role with two network interfaces, but you must take appropriate steps to configure the interfaces.</span></span> <span data-ttu-id="711f4-163">Você deve atribuir os endereços IP à interface específica que se comunicará como o servidor de mediação e o IP da interface de rede que se comunicará como o servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="711f4-163">You must assign the IP addresses to the specific interface that will communicate as the Mediation Server, and the network interface IP that will communicate as the Front End Server.</span></span> <span data-ttu-id="711f4-164">Você pode fazer isso no construtor de topologias selecionando o endereço IP correto para cada serviço, em vez de usar o padrão <STRONG>usar todos os endereços IP configurados</STRONG>.</span><span class="sxs-lookup"><span data-stu-id="711f4-164">You can do this in Topology Builder by selecting the correct IP address for each service, instead of using the default <STRONG>Use all configured IP addresses</STRONG>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="711f4-165">Confira Também</span><span class="sxs-lookup"><span data-stu-id="711f4-165">See Also</span></span>


[<span data-ttu-id="711f4-166">Planejamento para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="711f4-166">Planning for external user access in Lync Server 2013</span></span>](lync-server-2013-planning-for-external-user-access.md)  
[<span data-ttu-id="711f4-167">Implantando o acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="711f4-167">Deploying external user access in Lync Server 2013</span></span>](lync-server-2013-deploying-external-user-access.md)  
[<span data-ttu-id="711f4-168">Planejamento para descoberta automática no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="711f4-168">Planning for Autodiscover in Lync Server 2013</span></span>](lync-server-2013-planning-for-autodiscover.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

