---
title: 'Lync Server 2013: cenários para acesso de usuário externo'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Scenarios for external user access
ms:assetid: 25697446-b045-4d12-9b1c-47f694b4f224
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425727(v=OCS.15)
ms:contentKeyID: 48183640
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bd560105303db5d09656c36620c9e8435feed86f
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42049583"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="1584b-102">Cenários para acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="1584b-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="1584b-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="1584b-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="1584b-104">Fornecer acesso de usuário externo para o Lync Server 2013 requer que você implante pelo menos um servidor de borda e um proxy reverso na sua rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="1584b-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="1584b-105">Opcionalmente, você pode implantar um diretor ou pool de diretor em sua rede interna.</span><span class="sxs-lookup"><span data-stu-id="1584b-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="1584b-106">Se você precisar de capacidade maior do que um servidor de borda único pode fornecer, ou se você precisar de alta disponibilidade para a implantação do servidor de borda, você pode configurar o balanceamento de carga e implantar vários servidores de borda em um pool com balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="1584b-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="1584b-107">Se sua organização tiver vários data centers, você pode ter implantações de servidor de borda ou de pool de borda em mais de um local.</span><span class="sxs-lookup"><span data-stu-id="1584b-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="1584b-108">No entanto, apenas uma das implantações do servidor de borda pode ser designada como a rota de Federação.</span><span class="sxs-lookup"><span data-stu-id="1584b-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="1584b-109">Esta seção define os cenários de implantações do servidor de borda e mapeia as seções de planejamento para os cenários possíveis.</span><span class="sxs-lookup"><span data-stu-id="1584b-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="1584b-110">Por exemplo, se sua implantação requer alta disponibilidade, Federação com contatos extensível de mensagens e presença (XMPP) e Lync Mobility, selecione as entradas correspondentes na seguinte tabela que atendam a esses requisitos e use o seções de planejamento referenciadas para definir sua implantação, conforme ilustrado no fluxograma a seguir.</span><span class="sxs-lookup"><span data-stu-id="1584b-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="1584b-111">**Processo de seleção do cenário de implantação do Servidor de Borda**</span><span class="sxs-lookup"><span data-stu-id="1584b-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="1584b-112">![Exemplo de fluxograma de implantação](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Exemplo de fluxograma de implantação")</span><span class="sxs-lookup"><span data-stu-id="1584b-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="1584b-113">Usando este processo, é possível planejar e documentar a configuração de todos os recursos em potencial que você pretende implantar para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="1584b-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="1584b-114">No entanto, você pode adicionar serviços de Federação e mobilidade depois de implantar o servidor de borda e ter confirmado a operação correta antes de adicionar outros recursos.</span><span class="sxs-lookup"><span data-stu-id="1584b-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="1584b-115">O processo de adição de recursos a uma implantação de servidor de borda existente é abordado na seção implantação.</span><span class="sxs-lookup"><span data-stu-id="1584b-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="1584b-116">Para obter detalhes sobre a implantação, consulte [implantando o acesso de usuário externo no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) incluindo o planejamento desses recursos durante o processo de planejamento inicial, você pode se preparar para os requisitos de DNS, firewall e certificado para os recursos adicionados, o que permite que você adquira os certificados e configure os requisitos de DNS e de porta/protocolo com antecedência.</span><span class="sxs-lookup"><span data-stu-id="1584b-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="1584b-117">Se você estiver planejando instalar os servidores de borda e o proxy reverso e adicionar recursos posteriormente (por exemplo, Federação e mobilidade), determine quais certificados você precisará para todos os serviços após a implantação.</span><span class="sxs-lookup"><span data-stu-id="1584b-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="1584b-118">O planejamento e a aquisição dos certificados para todos os recursos de antemão, implantados inicialmente ou não, evita que você precise solicitar novos certificados para atender aos requisitos de Federação (ou seja, nos servidores de borda) ou no proxy reverso (ou seja, para mobilidade serviços).</span><span class="sxs-lookup"><span data-stu-id="1584b-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="1584b-119">Todos os serviços de borda são executados em cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1584b-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="1584b-120">Os serviços não podem ser divididos entre dois servidores de borda diferentes.</span><span class="sxs-lookup"><span data-stu-id="1584b-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="1584b-121">Se você implantar um pool de borda para escalabilidade, todos os serviços de borda serão implantados em cada servidor de borda no pool.</span><span class="sxs-lookup"><span data-stu-id="1584b-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="1584b-122">XMPP Federation, Office Communications Server e Lync Server Federation, conectividade pública de IM e mobilidade de cliente são serviços adicionais que podem ser implantados após a implantação do seu primeiro pool de borda ou servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1584b-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="1584b-123">Serviços de mobilidade é o recurso que usa proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="1584b-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="1584b-124">A instalação dos serviços de mobilidade não adicionará recursos aos servidores de borda, mas exigirá a reconfiguração de seu proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="1584b-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="1584b-125">A coluna <STRONG>objetivo de instalação</STRONG> que lista esses recursos fornece diretrizes de planejamento na coluna associada na <STRONG>seção planejamento do servidor de borda ou seções</STRONG> para planejar simultaneamente que esses recursos sejam implantados quando os servidores de borda são instalados e configurados.</span><span class="sxs-lookup"><span data-stu-id="1584b-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="1584b-126">Identificando e mapeando suas metas de implantação</span><span class="sxs-lookup"><span data-stu-id="1584b-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="1584b-127">Objetivo de instalação</span><span class="sxs-lookup"><span data-stu-id="1584b-127">Installation goal</span></span></th>
<th><span data-ttu-id="1584b-128">Documentação de planejamento do Servidor de Borda</span><span class="sxs-lookup"><span data-stu-id="1584b-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="1584b-p107">Você decidiu que um único servidor é suficiente para serviços de Borda em sua infraestrutura. Você também pretende usar endereços IP privados para interfaces externas do servidor de Borda com NAT para a Internet.</span><span class="sxs-lookup"><span data-stu-id="1584b-p107">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="1584b-131">Use esta seção de planejamento se você estiver implantando um único servidor de borda em seu perímetro.</span><span class="sxs-lookup"><span data-stu-id="1584b-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="1584b-132">Você implantará um servidor de borda com endereços IP privados atribuídos ao servidor de borda e usará o NAT para fornecer os endereços IP públicos para os usuários externos na Internet.</span><span class="sxs-lookup"><span data-stu-id="1584b-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1584b-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Única borda consolidada com endereços IP privados e NAT no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1584b-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1584b-p109">Você decidiu que um único servidor é suficiente para serviços de Borda em sua infraestrutura. Você também pretende usar endereços IP públicos para interfaces externas do servidor de Borda para a Internet.</span><span class="sxs-lookup"><span data-stu-id="1584b-p109">You have decided that a single server is sufficient for Edge services in your infrastructure. You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="1584b-136">Use esta seção de planejamento se você estiver implantando um único servidor de borda em seu perímetro.</span><span class="sxs-lookup"><span data-stu-id="1584b-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="1584b-137">Você implantará um servidor de borda com endereços IP públicos atribuídos ao servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="1584b-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="1584b-138">Ao invés do NAT, você usará o roteamento neste cenário.</span><span class="sxs-lookup"><span data-stu-id="1584b-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="1584b-139">O endereço IP público real do servidor de borda é disponibilizado para conexões de usuário externo.</span><span class="sxs-lookup"><span data-stu-id="1584b-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="1584b-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Única borda consolidada com endereços IP públicos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1584b-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1584b-p111">Você decidiu que alta disponibilidade dos serviços de Borda é importante para seus usuários e irá implantar dois ou mais Servidores de Borda neste pool. Você também pretende usar endereços IP privados para as interfaces externas do Servidor de Borda com NAT para a Internet.</span><span class="sxs-lookup"><span data-stu-id="1584b-p111">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool. You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="1584b-143">Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro.</span><span class="sxs-lookup"><span data-stu-id="1584b-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="1584b-144">Você implantará os servidores de borda com endereços IP privados atribuídos ao servidor de borda, usando o balanceamento de carga DNS para distribuir a comunicação entre o pool.</span><span class="sxs-lookup"><span data-stu-id="1584b-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="1584b-145">Você usará NAT para oferecer endereços IP públicos para usuários externos na Internet.</span><span class="sxs-lookup"><span data-stu-id="1584b-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1584b-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1584b-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1584b-147">Você decidiu que alta disponibilidade dos serviços de Borda é importante para seus usuários e irá implantar dois ou mais Servidores de Borda neste pool.</span><span class="sxs-lookup"><span data-stu-id="1584b-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="1584b-148">Você também pretende usar endereços IP públicos para as interfaces externas do servidor de borda para a Internet.</span><span class="sxs-lookup"><span data-stu-id="1584b-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="1584b-149">Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro.</span><span class="sxs-lookup"><span data-stu-id="1584b-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="1584b-150">Você implantará os servidores de borda com endereços IP públicos atribuídos ao servidor de borda, usando o balanceamento de carga DNS para distribuir a comunicação entre o pool.</span><span class="sxs-lookup"><span data-stu-id="1584b-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="1584b-151">Ao invés do NAT, você usará o roteamento para oferecer endereços IP públicos para usuários externos na Internet.</span><span class="sxs-lookup"><span data-stu-id="1584b-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1584b-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1584b-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1584b-153">Você decidiu que a alta disponibilidade dos serviços de borda é importante para seus usuários e implantar dois ou mais servidores de borda nesse pool usando um balanceador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="1584b-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="1584b-154">Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro.</span><span class="sxs-lookup"><span data-stu-id="1584b-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="1584b-155">Você implantará os servidores de borda com endereços IP públicos atribuídos ao servidor de borda, usando balanceadores de carga de hardware para distribuir a comunicação entre o pool.</span><span class="sxs-lookup"><span data-stu-id="1584b-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="1584b-156">Ao invés do NAT, você usará o roteamento para oferecer endereços IP públicos para usuários externos na Internet.</span><span class="sxs-lookup"><span data-stu-id="1584b-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="1584b-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1584b-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="1584b-158">Os cenários de federação permite planejar o recurso que irá estender os tipos de parceiros que os usuários podem se comunicar.</span><span class="sxs-lookup"><span data-stu-id="1584b-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="1584b-159">Federação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="1584b-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="1584b-160">Federação do Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="1584b-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="1584b-161">Conectividade a redes públicas de mensagens instantâneas</span><span class="sxs-lookup"><span data-stu-id="1584b-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="1584b-162">Federação XMPP</span><span class="sxs-lookup"><span data-stu-id="1584b-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="1584b-163">Planejamento para cenários de federação</span><span class="sxs-lookup"><span data-stu-id="1584b-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="1584b-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planejamento para Federação do Lync Server 2013 e Office Communications Server</a></span><span class="sxs-lookup"><span data-stu-id="1584b-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="1584b-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planejando a conectividade de mensagens instantâneas públicas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1584b-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="1584b-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planejando a Federação do protocolo XMPP (Extensible Messaging and Presence Protocol) no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1584b-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="1584b-167">Serviços de mobilidade são oferecidos através do proxy inverso.</span><span class="sxs-lookup"><span data-stu-id="1584b-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="1584b-168">Os serviços que permitem a mobilidade para usuários externos são implantados no servidor front-end ou no pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="1584b-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="1584b-169">Você cria ou modifica regras de publicação existentes no proxy inverso para habilitar os serviços de mobilidade para seus usuários externos.</span><span class="sxs-lookup"><span data-stu-id="1584b-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="1584b-170"><a href="lync-server-2013-planning-for-mobility.md">Planejamento de mobilidade no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="1584b-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="1584b-171">Nas seguintes seções Cenários existem arquiteturas de referência, DNS de exemplo, definições de porta/protocolo e requisitos de certificado.</span><span class="sxs-lookup"><span data-stu-id="1584b-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="1584b-172">Também inclui diagramas para seu DNS, definições de porta/protocolo e necessidades de certificado.</span><span class="sxs-lookup"><span data-stu-id="1584b-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="1584b-173">Os diagramas oferecerão um modelo para você preencher e distribuir para outras equipes (por exemplo, a Equipe de Rede da sua organização, Equipe de Infraestrutura de Chave Pública e Equipe de Implantação do Servidor).</span><span class="sxs-lookup"><span data-stu-id="1584b-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="1584b-174">O objetivo dos diagramas é aprimorar a comunicação e garantir o sucesso ao comunicar os elementos de configuração necessários do servidor de borda às pessoas que farão o trabalho de configuração real.</span><span class="sxs-lookup"><span data-stu-id="1584b-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="1584b-175">Recomendamos que você use os diagramas e as arquiteturas de referência associados para planejar sua implantação.</span><span class="sxs-lookup"><span data-stu-id="1584b-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

