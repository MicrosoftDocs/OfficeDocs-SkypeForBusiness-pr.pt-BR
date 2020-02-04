---
title: 'Lync Server 2013: Componentes obrigatórios para acesso de usuário externo'
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
ms.openlocfilehash: 550eb864ff7cc26eb0bfeace37759bb15b9816f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757095"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="components-required-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="55b21-102">Componentes obrigatórios para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55b21-102">Components required for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="55b21-103">_**Tópico da última modificação:** 2014-05-29_</span><span class="sxs-lookup"><span data-stu-id="55b21-103">_**Topic Last Modified:** 2014-05-29_</span></span>

<span data-ttu-id="55b21-104">A maioria dos componentes de Borda é implantada em uma rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="55b21-104">Most Edge components are deployed in a perimeter network.</span></span> <span data-ttu-id="55b21-105">Os componentes a seguir compõem a topologia de borda da rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="55b21-105">The following components make up the edge topology of the perimeter network.</span></span> <span data-ttu-id="55b21-106">Exceto onde observado, os componentes fazem parte dos [cenários para o acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) e na rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="55b21-106">Except where noted, the components are part of the [Scenarios for external user access in Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md) and are in the perimeter network.</span></span> <span data-ttu-id="55b21-107">Os componentes de Borda incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="55b21-107">Edge components include the following:</span></span>

  - <span data-ttu-id="55b21-108">Edge Servers</span><span class="sxs-lookup"><span data-stu-id="55b21-108">Edge Servers</span></span>

  - <span data-ttu-id="55b21-109">Reverse proxies</span><span class="sxs-lookup"><span data-stu-id="55b21-109">Reverse proxies</span></span>

  - <span data-ttu-id="55b21-110">Firewalls</span><span class="sxs-lookup"><span data-stu-id="55b21-110">Firewalls</span></span>

  - <span data-ttu-id="55b21-111">Diretores (opcional e logicamente localizado na rede interna)</span><span class="sxs-lookup"><span data-stu-id="55b21-111">Directors (optional, and logically located on the internal network)</span></span>

  - <span data-ttu-id="55b21-112">Balanceamento de carga para Topologias de Borda Dimensionadas (balanceamento de carga DNS ou um balanceador de carga de hardware)</span><span class="sxs-lookup"><span data-stu-id="55b21-112">Load balancing for Scaled Edge Topologies (either DNS load balancing or a hardware load balancer)</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="55b21-p102">O uso do balanceamento de carga de DNS em uma interface e do balanceamento de carga de hardware na outra não é suportado. É preciso usar o balanceamento de carga de hardware ou de DNS nas duas interfaces.</span><span class="sxs-lookup"><span data-stu-id="55b21-p102">Using DNS load balancing on one interface and hardware load balancing on the other is not supported. You must use hardware load balancing for both interfaces or DNS load balancing for both.</span></span>

    
    </div>

<div>

## <a name="edge-servers"></a><span data-ttu-id="55b21-115">Servidores de Borda</span><span class="sxs-lookup"><span data-stu-id="55b21-115">Edge Servers</span></span>

<span data-ttu-id="55b21-116">Os servidores de borda enviam e recebem tráfego de rede para os serviços oferecidos pela implantação interna por usuários externos.</span><span class="sxs-lookup"><span data-stu-id="55b21-116">The Edge Servers send and receive network traffic for the services offered by internal deployment by external users.</span></span> <span data-ttu-id="55b21-117">O servidor de borda executa os seguintes serviços:</span><span class="sxs-lookup"><span data-stu-id="55b21-117">The Edge Server runs the following services:</span></span>

  - <span data-ttu-id="55b21-118">**Serviço de borda de acesso**   o serviço de borda de acesso fornece um ponto de conexão confiável e único para tráfego de protocolo de iniciação de sessão (SIP) de entrada e saída.</span><span class="sxs-lookup"><span data-stu-id="55b21-118">**Access Edge service**   The Access Edge service provides a single, trusted connection point for both outbound and inbound Session Initiation Protocol (SIP) traffic.</span></span>

  - <span data-ttu-id="55b21-119">**Serviço de borda de Webconferência**   o serviço de borda de Webconferência permite que usuários externos ingressem em reuniões hospedadas em sua implantação interna do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55b21-119">**Web Conferencing Edge service**   The Web Conferencing Edge service enables external users to join meetings that are hosted on your internal Lync Server 2013 deployment.</span></span>

  - <span data-ttu-id="55b21-120">**Serviço de borda**   a/v o serviço de borda a/v torna o áudio, o vídeo, o compartilhamento de aplicativos e a transferência de arquivos disponíveis para usuários externos.</span><span class="sxs-lookup"><span data-stu-id="55b21-120">**A/V Edge service**   The A/V Edge service makes audio, video, application sharing, and file transfer available to external users.</span></span> <span data-ttu-id="55b21-121">Seus usuários podem adicionar áudio e vídeo a reuniões que incluam participantes externos, e eles podem se comunicar usando áudio e/ou vídeo diretamente com um usuário externo em sessões ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="55b21-121">Your users can add audio and video to meetings that include external participants, and they can communicate using audio and/or video directly with an external user in point-to-point sessions.</span></span> <span data-ttu-id="55b21-122">O serviço de borda a/V também oferece suporte para compartilhamento de área de trabalho e transferência de arquivos.</span><span class="sxs-lookup"><span data-stu-id="55b21-122">The A/V Edge service also provides support for desktop sharing and file transfer.</span></span>

  - <span data-ttu-id="55b21-123">**Serviço de proxy XMPP**   o serviço de proxy do XMPP aceita e envia mensagens de protocolo de presença e mensagens extensível (XMPP) para e a partir de parceiros federados XMPP configurados.</span><span class="sxs-lookup"><span data-stu-id="55b21-123">**XMPP Proxy service**   The XMPP Proxy service accepts and sends extensible messaging and presence protocol (XMPP) messages to and from configured XMPP Federated partners.</span></span>

<span data-ttu-id="55b21-124">Usuários externos autorizados podem acessar os servidores de borda para se conectar à implantação interna do Lync Server 2013, mas os servidores de borda não fornecem meios para qualquer outro acesso à rede interna.</span><span class="sxs-lookup"><span data-stu-id="55b21-124">Authorized external users can access the Edge Servers in order to connect to your internal Lync Server 2013 deployment, but the Edge Servers do not provide a means for any other access to the internal network.</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55b21-125">Os servidores de borda são implantados para fornecer conexões para clientes Lync habilitados e outros servidores Microsoft Edge (como em cenários de Federação).</span><span class="sxs-lookup"><span data-stu-id="55b21-125">Edge servers are deployed to provide connections for enabled Lync clients and other Microsoft Edge servers (as in federation scenarios).</span></span> <span data-ttu-id="55b21-126">Elas não são projetadas para permitir conexões de outros tipos de cliente ou servidor de ponto final.</span><span class="sxs-lookup"><span data-stu-id="55b21-126">They are not designed to allow connections from other end point client or server types.</span></span> <span data-ttu-id="55b21-127">O servidor de Gateway XMPP pode ser implantado para permitir conexões com os parceiros do XMPP configurados.</span><span class="sxs-lookup"><span data-stu-id="55b21-127">The XMPP Gateway server can be deployed to allow connections with configured XMPP partners.</span></span> <span data-ttu-id="55b21-128">O servidor de borda e o Gateway XMPP só podem dar suporte a conexões de ponto de extremidade desses tipos de cliente e de Federação.</span><span class="sxs-lookup"><span data-stu-id="55b21-128">The Edge server and XMPP Gateway can only support end point connections from these client and federation types.</span></span>



</div>

</div>

<div>

## <a name="reverse-proxy"></a><span data-ttu-id="55b21-129">Proxy reverso</span><span class="sxs-lookup"><span data-stu-id="55b21-129">Reverse Proxy</span></span>

<span data-ttu-id="55b21-130">O proxy reverso é necessário para o seguinte:</span><span class="sxs-lookup"><span data-stu-id="55b21-130">The reverse proxy is required for the following:</span></span>

  - <span data-ttu-id="55b21-131">Para permitir que os usuários se conectem a reuniões ou conferências discadas usando URLs simples</span><span class="sxs-lookup"><span data-stu-id="55b21-131">To allow users to connect to meetings or dial-in conferences using simple URLs</span></span>

  - <span data-ttu-id="55b21-132">Para habilitar usuários externos para baixar o conteúdo da reunião</span><span class="sxs-lookup"><span data-stu-id="55b21-132">To enable external users to download meeting content</span></span>

  - <span data-ttu-id="55b21-133">Para permitir que usuários externos expandam grupos de distribuição</span><span class="sxs-lookup"><span data-stu-id="55b21-133">To enable external users to expand distribution groups</span></span>

  - <span data-ttu-id="55b21-134">Para permitir que o usuário obtenha um certificado baseado em usuário para autenticação baseada em certificado de cliente</span><span class="sxs-lookup"><span data-stu-id="55b21-134">To allow the user to obtain a user-based certificate for client certificate based authentication</span></span>

  - <span data-ttu-id="55b21-135">Para habilitar usuários remotos a baixar arquivos do servidor de catálogo de endereços ou enviar consultas para o serviço de consulta à Web do catálogo de endereços</span><span class="sxs-lookup"><span data-stu-id="55b21-135">To enable remote users to download files from the Address Book Server or to submit queries to the Address Book Web Query service</span></span>

  - <span data-ttu-id="55b21-136">Para permitir que os usuários remotos obtenham atualizações para software cliente e dispositivo</span><span class="sxs-lookup"><span data-stu-id="55b21-136">To enable remote users to obtain updates to client and device software</span></span>

  - <span data-ttu-id="55b21-137">Para habilitar dispositivos móveis para detectar automaticamente servidores front-end que oferecem serviços de mobilidade</span><span class="sxs-lookup"><span data-stu-id="55b21-137">To enable mobile devices to automatically discover Front End Servers offering mobility services</span></span>

  - <span data-ttu-id="55b21-138">Para habilitar as notificações por push para dispositivos móveis do Office 365 ou dos serviços de notificação por push da Apple</span><span class="sxs-lookup"><span data-stu-id="55b21-138">To enable push notifications to mobile devices from the Office 365 or Apple push notification services</span></span>

<span data-ttu-id="55b21-139">Para obter informações adicionais relacionadas a proxies invertidos e os requisitos que os proxies inversos devem atender, consulte os detalhes em [requisitos de configuração para o proxy inverso no Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="55b21-139">For additional information related to reverse proxies and the requirements that reverse proxies must meet, see the details in [Configuration requirements for reverse proxy in Lync Server 2013](lync-server-2013-configuration-requirements-for-reverse-proxy.md).</span></span>

<div>


> [!NOTE]  
> <span data-ttu-id="55b21-140">Os usuários externos não precisam de uma conexão de rede virtual privada (VPN) à sua organização para participar de comunicações usando o Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="55b21-140">External users do not need a virtual private network (VPN) connection to your organization in order to participate in communications using Lync Server 2013.</span></span> <span data-ttu-id="55b21-141">Se você implementou a tecnologia VPN em sua organização e seus usuários usam a VPN para o Lync, o tráfego de mídia (como videoconferência) pode ser afetado negativamente.</span><span class="sxs-lookup"><span data-stu-id="55b21-141">If you have implemented VPN technology in your organization and your users use the VPN for Lync, media traffic (such as video conferencing) can be adversely affected.</span></span> <span data-ttu-id="55b21-142">Você deve considerar o fornecimento de um meio para tráfego de mídia para se conectar ao serviço de borda de AV diretamente e ignorar a VPN.</span><span class="sxs-lookup"><span data-stu-id="55b21-142">You should consider providing a means for media traffic to connect to the AV Edge service directly and bypass the VPN.</span></span> <span data-ttu-id="55b21-143">Para obter detalhes, consulte o artigo sobre o blog NextHop, "Ativando o Lync Media para ignorar um <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>túnel VPN".</span><span class="sxs-lookup"><span data-stu-id="55b21-143">For details, see the NextHop Blog article, “Enabling Lync Media to Bypass a VPN Tunnel,” at <A href="http://go.microsoft.com/fwlink/p/?linkid=256532">http://go.microsoft.com/fwlink/p/?LinkId=256532</A>.</span></span>



</div>

</div>

<div>

## <a name="firewall"></a><span data-ttu-id="55b21-144">Firewall</span><span class="sxs-lookup"><span data-stu-id="55b21-144">Firewall</span></span>

<span data-ttu-id="55b21-145">Você pode implantar a topologia de borda com apenas um firewall externo ou firewalls internos e externos.</span><span class="sxs-lookup"><span data-stu-id="55b21-145">You can deploy your edge topology with only an external firewall or both external and internal firewalls.</span></span> <span data-ttu-id="55b21-146">As arquiteturas de cenário incluem dois firewalls.</span><span class="sxs-lookup"><span data-stu-id="55b21-146">The scenario architectures include two firewalls.</span></span> <span data-ttu-id="55b21-147">Usar dois firewalls é a abordagem recomendada porque garante um roteamento estrito de uma borda de rede para a outra e protege sua implantação interna atrás de dois níveis de firewall.</span><span class="sxs-lookup"><span data-stu-id="55b21-147">Using two firewalls is the recommended approach because it ensures strict routing from one network edge to the other, and it protects your internal deployment behind two levels of firewall.</span></span>

</div>

<div>

## <a name="director"></a><span data-ttu-id="55b21-148">Diretor</span><span class="sxs-lookup"><span data-stu-id="55b21-148">Director</span></span>

<span data-ttu-id="55b21-149">Um diretor é uma função de servidor opcional separada no Lync Server 2013 que não hospeda contas de usuário nem fornece serviços de presença ou conferência.</span><span class="sxs-lookup"><span data-stu-id="55b21-149">A Director is a separate, optional server role in Lync Server 2013 that does not home user accounts, or provide presence or conferencing services.</span></span> <span data-ttu-id="55b21-150">Ele funciona como um servidor de um próximo salto interno ao qual um servidor de Borda roteia o tráfego SIP de entrada destinado para servidores internos.</span><span class="sxs-lookup"><span data-stu-id="55b21-150">It serves as an internal next hop server to which an Edge Server routes inbound SIP traffic destined for internal servers.</span></span> <span data-ttu-id="55b21-151">O diretor autentica solicitações de entrada e as redireciona para o pool ou servidor primário do usuário.</span><span class="sxs-lookup"><span data-stu-id="55b21-151">The Director preauthenticates inbound requests and redirects them to the user’s home pool or server.</span></span> <span data-ttu-id="55b21-152">Ao autenticar no director, você pode descartar solicitações de contas de usuários desconhecidas para a implantação.</span><span class="sxs-lookup"><span data-stu-id="55b21-152">By preauthenticating at the Director, you can drop requests from user accounts that are unknown to the deployment.</span></span>

<span data-ttu-id="55b21-153">Um diretor ajuda a isolar servidores de front-end do Enterprise Edition em pools front-end do Enterprise Edition contra tráfego mal-intencionado, como ataques de negação de serviço (DoS).</span><span class="sxs-lookup"><span data-stu-id="55b21-153">A Director helps insulate Standard Edition servers and Front End Servers in Enterprise Edition Front End pools from malicious traffic such as denial-of-service (DoS) attacks.</span></span> <span data-ttu-id="55b21-154">Se a rede estiver inundada com tráfego externo inválido nesse tipo de ataque, o tráfego terminará no diretor.</span><span class="sxs-lookup"><span data-stu-id="55b21-154">If the network is flooded with invalid external traffic in such an attack, the traffic ends at the Director.</span></span> <span data-ttu-id="55b21-155">Para obter detalhes sobre o uso de directors, consulte [cenários do diretor do Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span><span class="sxs-lookup"><span data-stu-id="55b21-155">For details about the use of Directors, see [Scenarios for the Director in Lync Server 2013](lync-server-2013-scenarios-for-the-director.md).</span></span>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="55b21-156">Confira também</span><span class="sxs-lookup"><span data-stu-id="55b21-156">See Also</span></span>


[<span data-ttu-id="55b21-157">Requisitos do balanceador de carga do hardware para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="55b21-157">Hardware load balancer requirements for Lync Server 2013</span></span>](lync-server-2013-hardware-load-balancer-requirements.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

