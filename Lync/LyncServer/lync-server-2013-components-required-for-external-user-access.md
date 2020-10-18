---
title: 'Lync Server 2013: componentes necessários para acesso de usuário externo'
description: 'Lync Server 2013: componentes necessários para acesso de usuário externo.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Components required for external user access
ms:assetid: 2d0f9817-14e7-4109-95dc-62420e3c29e2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425779(v=OCS.15)
ms:contentKeyID: 48183711
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d75ef0c7f2000353a35acefa0b177c90bdcc879b
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48576777"
---
# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="65181-103">Componentes necessários para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65181-103">Components required for external user access in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="65181-104">_**Última modificação do tópico:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="65181-104">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="65181-105">A maioria dos componentes de borda é implantada em uma rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="65181-105">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="65181-106">Os componentes a seguir compõem a topologia de borda da rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="65181-106">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="65181-107">Exceto onde observado, os componentes fazem parte dos [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) e estão na rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="65181-107">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="65181-108">Os componentes de Borda incluem:</span><span class="sxs-lookup"><span data-stu-id="65181-108">Edge components include the following:</span></span>

  - <span data-ttu-id="65181-109">Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="65181-109">Edge Servers</span></span>

  - <span data-ttu-id="65181-110">Proxies reversos</span><span class="sxs-lookup"><span data-stu-id="65181-110">Reverse proxies</span></span>

  - <span data-ttu-id="65181-111">Firewalls</span><span class="sxs-lookup"><span data-stu-id="65181-111">Firewalls</span></span>

  - <span data-ttu-id="65181-112">Diretores (opcionais e logicamente localizados na rede interna)</span><span class="sxs-lookup"><span data-stu-id="65181-112">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="65181-113">Balanceamento de carga para Topologias de Borda Dimensionadas (balanceamento de carga DNS ou um balanceador de carga de hardware)</span><span class="sxs-lookup"><span data-stu-id="65181-113">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="65181-p102">O uso do balanceamento de carga de DNS em uma interface e do balanceamento de carga de hardware na outra não é suportado. É preciso usar o balanceamento de carga de hardware ou de DNS nas duas interfaces.</span><span class="sxs-lookup"><span data-stu-id="65181-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="65181-116">Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="65181-116">Edge Servers</span></span>

<span data-ttu-id="65181-117">Os servidores de borda enviam e recebem tráfego de rede para os serviços oferecidos pela implantação interna por usuários externos.</span><span class="sxs-lookup"><span data-stu-id="65181-117">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="65181-118">O Servidor de Borda executa os seguintes serviços:</span><span class="sxs-lookup"><span data-stu-id="65181-118">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="65181-119">Serviço de borda de **acesso**     O serviço de borda de acesso fornece um ponto de conexão único e confiável para o tráfego do protocolo SIP (Session Initiation Protocol) de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="65181-119">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="65181-120">Serviço de borda de **Webconferência**     O serviço de borda de Webconferência permite que usuários externos ingressem em reuniões hospedadas na sua implantação interna do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65181-120">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="65181-121">Serviço de borda **A/V**     O serviço de borda A/V disponibiliza áudio, vídeo, compartilhamento de aplicativos e transferência de arquivos para usuários externos.</span><span class="sxs-lookup"><span data-stu-id="65181-121">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="65181-122">Os usuários podem adicionar áudio e vídeo a reuniões que incluem participantes externos e podem se comunicar usando áudio e/ou vídeo diretamente com um usuário externo em sessões ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="65181-122">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="65181-123">O Serviço de Borda A/V também fornece suporte para compartilhamento de área de trabalho e transferência de arquivo.</span><span class="sxs-lookup"><span data-stu-id="65181-123">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="65181-124">Serviço de proxy **XMPP**     O serviço de proxy do XMPP aceita e envia mensagens de XMPP (Extensible Messaging and Presence Protocol) para e de parceiros federados XMPP configurados.</span><span class="sxs-lookup"><span data-stu-id="65181-124">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="65181-125">Usuários externos autorizados podem acessar os servidores de borda para se conectar à sua implantação interna do Lync Server 2013, mas os servidores de borda não fornecem meios para qualquer outro acesso à rede interna.</span><span class="sxs-lookup"><span data-stu-id="65181-125">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65181-126">Os servidores de borda são implantados para fornecer conexões para clientes Lync habilitados e outros servidores do Microsoft Edge (como em cenários de Federação).</span><span class="sxs-lookup"><span data-stu-id="65181-126">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="65181-127">Eles não são projetados para permitir conexões a partir de outros tipos de cliente ou servidor de ponto final.</span><span class="sxs-lookup"><span data-stu-id="65181-127">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="65181-128">O servidor Gateway XMPP pode ser implantado para permitir conexões com parceiros XMPP configurados.</span><span class="sxs-lookup"><span data-stu-id="65181-128">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="65181-129">O servidor de borda e Gateway XMPP somente pode suportar conexões de ponto final a partir desses tipos de clientes e federação.</span><span class="sxs-lookup"><span data-stu-id="65181-129">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="65181-130">Proxy reverso</span><span class="sxs-lookup"><span data-stu-id="65181-130">Reverse Proxy</span></span>

<span data-ttu-id="65181-131">O proxy reverso é necessário para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="65181-131">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="65181-132">Permitir que os usuários se conectem às reuniões ou conferências discadas usando URLs simples</span><span class="sxs-lookup"><span data-stu-id="65181-132">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="65181-133">Permitir que os usuários externos baixem o conteúdo da reunião</span><span class="sxs-lookup"><span data-stu-id="65181-133">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="65181-134">Habilitar os usuários externos a expandir grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="65181-134">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="65181-135">Permitir que o usuário obtenha um certificado baseado no usuário para autenticação com base no certificado cliente</span><span class="sxs-lookup"><span data-stu-id="65181-135">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="65181-136">Permitir que os usuários remotos baixem arquivos do Servidor de Catálogo de Endereço ou enviem consultas ao serviço Address Book Web Query</span><span class="sxs-lookup"><span data-stu-id="65181-136">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="65181-137">Permitir que os usuários remotos obtenham atualizações para softwares clientes ou de dispositivo</span><span class="sxs-lookup"><span data-stu-id="65181-137">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="65181-138">Permitir que os dispositivos móveis descubram automaticamente os Servidores Front-End que oferecem serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="65181-138">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="65181-139">Para habilitar as notificações por push para dispositivos móveis dos serviços de notificação por push da Microsoft 365, do Office 365 ou Apple push</span><span class="sxs-lookup"><span data-stu-id="65181-139">To enable push notifications to mobile devices from the Microsoft 365, Office 365, or Apple push notification services</span></span>

<span data-ttu-id="65181-140">Para obter informações adicionais relacionadas a proxies reversos e os requisitos que os proxies reverso devem atender, consulte os detalhes em [requisitos de configuração para o proxy reverso no Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="65181-140">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="65181-141">Os usuários externos não precisam de uma conexão VPN (rede virtual privada) à sua organização para participar de comunicações usando o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="65181-141">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="65181-142">Se você tiver implementado a tecnologia VPN em sua organização e seus usuários usarem a VPN para o Lync, o tráfego de mídia (como videoconferência) poderá ser afetado de forma adversa.</span><span class="sxs-lookup"><span data-stu-id="65181-142">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="65181-143">Considere fornecer um meio de tráfego de mídia para se conectar ao serviço de borda AV diretamente e ignorar a VPN.</span><span class="sxs-lookup"><span data-stu-id="65181-143">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="65181-144">Para obter detalhes, consulte o artigo de blog NextHop, "Habilitando o Lync Media para ignorar um túnel VPN" em <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A> .</span><span class="sxs-lookup"><span data-stu-id="65181-144">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="https://go.microsoft.com/fwlink/p/?linkid=256532">https://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="65181-145">Firewall</span><span class="sxs-lookup"><span data-stu-id="65181-145">Firewall</span></span>

<span data-ttu-id="65181-146">É possível implantar sua topologia de borda com apenas um firewall externo ou com firewalls internos e externos.</span><span class="sxs-lookup"><span data-stu-id="65181-146">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="65181-147">As arquiteturas de cenário incluem dois firewalls.</span><span class="sxs-lookup"><span data-stu-id="65181-147">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="65181-148">O uso de dois firewalls é a abordagem recomendada, pois garante o roteamento estrito de uma borda de rede para a outra, e protege sua implantação interna atrás de dois níveis de firewall.</span><span class="sxs-lookup"><span data-stu-id="65181-148">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="65181-149">Diretor</span><span class="sxs-lookup"><span data-stu-id="65181-149">Director</span></span>

<span data-ttu-id="65181-150">Um diretor é uma função de servidor opcional e separada no Lync Server 2013 que não hospeda contas de usuário ou fornece serviços de presença ou conferência.</span><span class="sxs-lookup"><span data-stu-id="65181-150">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="65181-151">Ele serve como um servidor de próximo salto interno para o qual um servidor de Borda roteia o tráfego SIP de entrada destinado a servidores internos.</span><span class="sxs-lookup"><span data-stu-id="65181-151">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="65181-152">O diretor autentica solicitações de entrada e as redireciona para o pool ou servidor de casa do usuário.</span><span class="sxs-lookup"><span data-stu-id="65181-152">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="65181-153">Ao autenticar no diretor, você pode descartar solicitações de contas de usuário que são desconhecidas para a implantação.</span><span class="sxs-lookup"><span data-stu-id="65181-153">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="65181-154">Um diretor ajuda a isolar servidores Standard Edition e servidores front-end em pools de front-ends Enterprise Edition de tráfego mal-intencionado, como ataques de negação de serviço (DoS).</span><span class="sxs-lookup"><span data-stu-id="65181-154">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="65181-155">Se a rede estiver inundada com tráfego externo inválido nesse ataque, o tráfego terminará no diretor.</span><span class="sxs-lookup"><span data-stu-id="65181-155">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="65181-156">Para obter detalhes sobre o uso de diretores, consulte [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="65181-156">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="65181-157">Confira também</span><span class="sxs-lookup"><span data-stu-id="65181-157">See Also</span></span>


[<span data-ttu-id="65181-158">Requisitos do balanceador de carga de hardware para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="65181-158">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

