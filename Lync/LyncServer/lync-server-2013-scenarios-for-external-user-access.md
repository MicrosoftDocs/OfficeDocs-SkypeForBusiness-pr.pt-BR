---
title: 'Lync Server 2013: Cenários de acesso de usuário externo'
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
ms.openlocfilehash: eab8323744615dc3f5d0b68f4325fbfb85bf911e
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764969"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="scenarios-for-external-user-access-in-lync-server-2013"></a><span data-ttu-id="c0bd1-102">Cenários de acesso de usuário externo no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0bd1-102">Scenarios for external user access in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0bd1-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c0bd1-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c0bd1-104">O acesso de usuários externos para o Lync Server 2013 exige que você implante pelo menos um servidor de borda e um proxy reverso na sua rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-104">Providing external user access for Lync Server 2013 requires that you deploy at least one Edge Server and one reverse proxy in your perimeter network.</span></span> <span data-ttu-id="c0bd1-105">Opcionalmente, você pode implantar um diretor ou um pool de diretor em sua rede interna.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-105">Optionally, you may deploy a Director or Director pool in your internal network.</span></span>

<span data-ttu-id="c0bd1-106">Se você precisar de maior capacidade do que um único servidor de borda pode fornecer ou se precisar de alta disponibilidade para a implantação do servidor de borda, você pode configurar o balanceamento de carga e implantar vários servidores de borda em um pool de carga balanceada.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-106">If you need greater capacity than a single Edge Server can provide, or if you need high availability for your Edge Server deployment, you can configure load balancing and deploy multiple Edge Servers in a load balanced pool.</span></span> <span data-ttu-id="c0bd1-107">Se a sua organização tiver vários data centers, você poderá ter implantações de servidor de borda ou de pool de bordas em mais de um local.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-107">If your organization has multiple data centers, you can have Edge Server or Edge pool deployments at more than one location.</span></span> <span data-ttu-id="c0bd1-108">No entanto, apenas uma das implantações de servidor de borda pode ser designada como a rota de Federação.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-108">However, only one of the Edge Server deployments can be designated as the federation route.</span></span>

<span data-ttu-id="c0bd1-109">Esta seção define os cenários para implantações do servidor de borda e mapeia as seções de planejamento para os cenários possíveis.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-109">This section defines the scenarios for Edge Server deployments and maps the planning sections to the possible scenarios.</span></span> <span data-ttu-id="c0bd1-110">Por exemplo, se a sua implantação requer alta disponibilidade, Federação com contatos de presença e mensagens extensível (XMPP) e Lync Mobility, selecione as entradas correspondentes na tabela a seguir que atenderiam a esses requisitos e usar o seções de planejamento referenciadas para definir sua implantação, conforme ilustrado no fluxograma a seguir.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-110">For example, if your deployment requires high availability, federation with extensible messaging and presence (XMPP) contacts, and Lync mobility, you would select the matching entries in the following table that would satisfy these requirements and use the referenced planning sections to define your deployment, as illustrated in the following flowchart.</span></span>

<span data-ttu-id="c0bd1-111">**Processo de seleção do cenário de implantação do servidor de borda**</span><span class="sxs-lookup"><span data-stu-id="c0bd1-111">**Edge Server deployment scenario selection process**</span></span>

<span data-ttu-id="c0bd1-112">![Exemplo de fluxograma de implantação](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Exemplo de fluxograma de implantação")</span><span class="sxs-lookup"><span data-stu-id="c0bd1-112">![Sample deployment flowchart](images/Gg425727.007100b5-6923-4909-bfd7-897d8867205f(OCS.15).jpg "Sample deployment flowchart")</span></span>

<span data-ttu-id="c0bd1-113">Ao usar esse processo, você pode planejar e documentar a configuração de todos os recursos possíveis que pretende implantar para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-113">By using this process, you can plan for and document the configuration of all potential features that you intend to deploy for your users.</span></span> <span data-ttu-id="c0bd1-114">No entanto, é possível adicionar serviços de Federação e mobilidade após a implantação do servidor de borda e confirmar a operação correta antes de adicionar outros recursos.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-114">However, you can add federation and mobility services after you have deployed the Edge Server and have confirmed the correct operation before adding other features.</span></span> <span data-ttu-id="c0bd1-115">O processo de adicionar recursos a uma implantação de servidor de borda existente é abordado na seção implantação.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-115">The process of adding features to an existing Edge Server deployment is covered in the Deployment section.</span></span> <span data-ttu-id="c0bd1-116">Para obter detalhes sobre a implantação, consulte [implantando o acesso de usuários externos no Lync Server 2013](lync-server-2013-deploying-external-user-access.md) , incluindo o planejamento desses recursos durante o processo de planejamento inicial, você pode se preparar para os requisitos de DNS, firewall e certificado para os recursos adicionais, que permitem que você adquira os certificados e configure os requisitos de DNS e de porta/protocolo com antecedência.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-116">For details on deployment, see [Deploying external user access in Lync Server 2013](lync-server-2013-deploying-external-user-access.md) By including planning for these features during the initial planning process, you can prepare for the DNS, firewall, and certificate requirements for the added features, which enables you to acquire the certificates and configure DNS and port/protocol requirements in advance.</span></span>

<div>


> [!TIP]  
> <span data-ttu-id="c0bd1-117">Se você estiver planejando instalar os servidores de borda e o proxy reverso e adicionar recursos mais tarde (por exemplo, Federação e mobilidade), determine quais certificados você precisará para todos os serviços após a implantação.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-117">If you are planning to install the Edge Servers and reverse proxy and then add features later (for example, federation and mobility), determine what certificates you will require for all services after deployment.</span></span> <span data-ttu-id="c0bd1-118">Planejar e adquirir os certificados para todos os recursos de antemão, implantados inicialmente ou não, poupa a necessidade de solicitar novos certificados para satisfazer os requisitos de Federação (ou seja, nos servidores de borda) ou o proxy reverso (ou seja, para mobilidade serviços).</span><span class="sxs-lookup"><span data-stu-id="c0bd1-118">Planning for and acquiring the certificates for all features in advance, initially deployed or not, saves you from having to order new certificates to satisfy the requirements of federation (that is, on the Edge Servers) or the reverse proxy (that is, for mobility services).</span></span>



</div>

<div>


> [!NOTE]  
> <span data-ttu-id="c0bd1-119">Todos os serviços de borda são executados em cada servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-119">All edge services run on each Edge Server.</span></span> <span data-ttu-id="c0bd1-120">Os serviços não podem ser divididos entre dois servidores de borda diferentes.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-120">Services cannot be split between two different Edge Servers.</span></span> <span data-ttu-id="c0bd1-121">Se você implantar um pool de bordas para escalabilidade, todos os serviços de borda serão implantados em cada servidor de borda no pool.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-121">If you deploy an Edge pool for scalability, all edge services are deployed on each Edge Server in the pool.</span></span> <span data-ttu-id="c0bd1-122">A Federação do XMPP, o Office Communications Server e a Federação do Lync Server, a conectividade de mensagens de chat públicas e a mobilidade do cliente são serviços adicionais que podem ser implantados após a implantação do seu primeiro servidor de borda ou do pool de borda.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-122">XMPP federation, Office Communications Server, and Lync Server federation, public IM connectivity and client mobility are additional services that can be deployed after you have deployed your first Edge Server or Edge pool.</span></span> <span data-ttu-id="c0bd1-123">Serviços de mobilidade é um recurso que usa o proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-123">Mobility services is a feature that uses the reverse proxy.</span></span> <span data-ttu-id="c0bd1-124">A instalação dos serviços de mobilidade não adicionará recursos aos seus servidores de borda, mas exigirá a reconfiguração do seu proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-124">Installation of mobility services will not add features to your Edge Servers, but will require reconfiguration of your reverse proxy.</span></span> <span data-ttu-id="c0bd1-125">A coluna de <STRONG>metas de instalação</STRONG> que lista esses recursos fornece orientação de planejamento na coluna associada em seções de planejamento do <STRONG>servidor de borda ou seções</STRONG> para planejar simultaneamente esses recursos a serem implantados quando os servidores de borda estiverem instalados e configurados.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-125">The <STRONG>Installation goal</STRONG> column that lists these features provides planning guidance in the associated column under <STRONG>Edge Server planning section or sections</STRONG> for concurrently planning these features to be deployed when the Edge Servers are installed and configured.</span></span>



</div>

<div>

## <a name="identifying-and-mapping-your-deployment-goals"></a><span data-ttu-id="c0bd1-126">Identificar e mapear seus objetivos de implantação</span><span class="sxs-lookup"><span data-stu-id="c0bd1-126">Identifying and Mapping Your Deployment Goals</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="c0bd1-127">Objetivo de instalação</span><span class="sxs-lookup"><span data-stu-id="c0bd1-127">Installation goal</span></span></th>
<th><span data-ttu-id="c0bd1-128">Documentação de planejamento do servidor de borda</span><span class="sxs-lookup"><span data-stu-id="c0bd1-128">Edge Server planning documentation</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="c0bd1-129">Você decidiu que um único servidor é suficiente para serviços de Edge na sua infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-129">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="c0bd1-130">Você também pretende usar endereços IP particulares para as interfaces externas do servidor de borda com NAT para a Internet.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-130">You also intend to use private IP addresses for the Edge server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="c0bd1-131">Use esta seção de planejamento se você estiver implantando um servidor de borda único em seu perímetro.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-131">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="c0bd1-132">Você vai implantar um servidor de borda com endereços IP privados atribuídos ao servidor de borda e usar o NAT para fornecer os endereços IP públicos para os usuários externos na Internet.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-132">You will deploy an Edge Server with private IP addresses assigned to the Edge Server and will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="c0bd1-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Única borda consolidada com endereços IP privados e NAT no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c0bd1-133"><a href="lync-server-2013-single-consolidated-edge-with-private-ip-addresses-and-nat.md">Single consolidated edge with private IP addresses and NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bd1-134">Você decidiu que um único servidor é suficiente para serviços de Edge na sua infraestrutura.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-134">You have decided that a single server is sufficient for Edge services in your infrastructure.</span></span> <span data-ttu-id="c0bd1-135">Você também pretende usar endereços IP públicos para as interfaces externas do servidor de borda para a Internet.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-135">You also intend to use public IP addresses for the Edge server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="c0bd1-136">Use esta seção de planejamento se você estiver implantando um servidor de borda único em seu perímetro.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-136">Use this planning section if you are deploying a single Edge Server in your perimeter.</span></span> <span data-ttu-id="c0bd1-137">Você vai implantar um servidor de borda com endereços IP públicos atribuídos ao servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-137">You will deploy an Edge Server with public IP addresses assigned to the Edge Server.</span></span> <span data-ttu-id="c0bd1-138">Em vez de NAT, você usará o roteamento nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-138">Instead of NAT, you will use routing in this scenario.</span></span> <span data-ttu-id="c0bd1-139">O endereço IP público real do servidor de borda é disponibilizado para conexões de usuários externos.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-139">The actual public IP address of the Edge Server are made available for external user connections.</span></span></p></td>
<td><p><span data-ttu-id="c0bd1-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Única borda consolidada com endereços IP públicos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c0bd1-140"><a href="lync-server-2013-single-consolidated-edge-with-public-ip-addresses.md">Single consolidated edge with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bd1-141">Você decidiu que a alta disponibilidade dos serviços de borda é importante para seus usuários e irá implantar dois ou mais servidores de borda neste pool.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-141">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="c0bd1-142">Você também pretende usar endereços IP particulares para as interfaces externas do servidor de borda com NAT para a Internet.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-142">You also intend to use private IP addresses for the Edge Server external interfaces with NAT to the Internet.</span></span></p>
<p><span data-ttu-id="c0bd1-143">Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-143">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="c0bd1-144">Você implantará os servidores de borda com endereços IP privados atribuídos ao servidor de borda usando o balanceamento de carga de DNS para distribuir a comunicação entre o pool.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-144">You will deploy the Edge Servers with private IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="c0bd1-145">Você usará o NAT para fornecer os endereços IP públicos para os usuários externos na Internet.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-145">You will use NAT to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="c0bd1-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP privados usando NAT no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c0bd1-146"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-private-ip-addresses-using-nat.md">Scaled consolidated edge, DNS load balancing with private IP addresses using NAT in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bd1-147">Você decidiu que a alta disponibilidade dos serviços de borda é importante para seus usuários e irá implantar dois ou mais servidores de borda neste pool.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-147">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool.</span></span> <span data-ttu-id="c0bd1-148">Você também pretende usar endereços IP públicos para as interfaces externas do servidor de borda para a Internet.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-148">You also intend to use public IP addresses for the Edge Server external interfaces to the Internet.</span></span></p>
<p><span data-ttu-id="c0bd1-149">Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-149">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="c0bd1-150">Você implantará os servidores de borda com endereços IP públicos atribuídos ao servidor de borda usando o balanceamento de carga de DNS para distribuir a comunicação entre o pool.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-150">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using DNS load balancing to distribute communication across the pool.</span></span> <span data-ttu-id="c0bd1-151">Em vez de NAT, você usará o roteamento para fornecer os endereços IP públicos para os usuários externos na Internet.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-151">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="c0bd1-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Borda consolidada em escala, balanceamento de carga de DNS com endereços IP públicos no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c0bd1-152"><a href="lync-server-2013-scaled-consolidated-edge-dns-load-balancing-with-public-ip-addresses.md">Scaled consolidated edge, DNS load balancing with public IP addresses in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bd1-153">Você decidiu que a alta disponibilidade dos serviços de borda é importante para seus usuários e irá implantar dois ou mais servidores de borda nesse pool usando um balanceador de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-153">You have decided that high availability of the Edge services is important to your users and you will deploy two or more Edge Servers in this pool using a hardware load balancer.</span></span></p>
<p><span data-ttu-id="c0bd1-154">Use esta seção de planejamento se você estiver implantando um pool de servidores de borda em seu perímetro.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-154">Use this planning section if you are deploying a pool of Edge Servers in your perimeter.</span></span> <span data-ttu-id="c0bd1-155">Você implantará os servidores de borda com endereços IP públicos atribuídos ao servidor de borda usando balanceadores de carga de hardware para distribuir a comunicação em todo o pool.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-155">You will deploy the Edge Servers with public IP addresses assigned to the Edge Server, using hardware load balancers to distribute communication across the pool.</span></span> <span data-ttu-id="c0bd1-156">Em vez de NAT, você usará o roteamento para fornecer os endereços IP públicos para os usuários externos na Internet.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-156">Instead of NAT, you will use routing to provide the public IP addresses for the external users on the Internet.</span></span></p></td>
<td><p><span data-ttu-id="c0bd1-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Borda consolidada em escala com balanceadores de carga de hardware no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c0bd1-157"><a href="lync-server-2013-scaled-consolidated-edge-with-hardware-load-balancers.md">Scaled consolidated edge with hardware load balancers in Lync Server 2013</a></span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="c0bd1-158">Os cenários de Federação permitem que você planeje o recurso que estenderá os tipos de parceiros com os quais os usuários podem se comunicar.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-158">The federation scenarios allow you to plan for the feature that will extend the types of partners that your users can communicate with.</span></span></p>
<ul>
<li><p><span data-ttu-id="c0bd1-159">Federação do Lync Server</span><span class="sxs-lookup"><span data-stu-id="c0bd1-159">Lync Server federation</span></span></p></li>
<li><p><span data-ttu-id="c0bd1-160">Federação do Office Communications Server</span><span class="sxs-lookup"><span data-stu-id="c0bd1-160">Office Communications Server federation</span></span></p></li>
<li><p><span data-ttu-id="c0bd1-161">Conectividade de mensagem de chat Pública</span><span class="sxs-lookup"><span data-stu-id="c0bd1-161">Public IM connectivity</span></span></p></li>
<li><p><span data-ttu-id="c0bd1-162">Federação do XMPP</span><span class="sxs-lookup"><span data-stu-id="c0bd1-162">XMPP federation</span></span></p></li>
</ul></td>
<td><p><span data-ttu-id="c0bd1-163">Planejando cenários de Federação</span><span class="sxs-lookup"><span data-stu-id="c0bd1-163">Planning for Federation Scenarios</span></span></p>
<ul>
<li><p><span data-ttu-id="c0bd1-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planejando a Federação do Lync Server 2013 e do Office Communications Server</a></span><span class="sxs-lookup"><span data-stu-id="c0bd1-164"><a href="lync-server-2013-planning-for-lync-server-and-office-communications-server-federation.md">Planning for Lync Server 2013 and Office Communications Server federation</a></span></span></p></li>
<li><p><span data-ttu-id="c0bd1-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planejando a conectividade de mensagens instantâneas públicas no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c0bd1-165"><a href="lync-server-2013-planning-for-public-instant-messaging-connectivity.md">Planning for public instant messaging connectivity in Lync Server 2013</a></span></span></p></li>
<li><p><span data-ttu-id="c0bd1-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Como planejar a Federação do protocolo de presença e de mensagens extensíveis (XMPP) no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c0bd1-166"><a href="lync-server-2013-planning-for-extensible-messaging-and-presence-protocol-xmpp-federation.md">Planning for extensible messaging and presence protocol (XMPP) federation in Lync Server 2013</a></span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="c0bd1-167">Os serviços de mobilidade são oferecidos por meio do proxy reverso.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-167">Mobility services are offered through the reverse proxy.</span></span> <span data-ttu-id="c0bd1-168">Os serviços que permitem a mobilidade para usuários externos são implantados no servidor front-end ou no pool de front-end.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-168">Services that enable mobility for external users are deployed on the Front End Server or Front End pool.</span></span> <span data-ttu-id="c0bd1-169">Você cria ou modifica regras de publicação existentes no proxy reverso para habilitar serviços de mobilidade para seus usuários externos.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-169">You create or modify existing publishing rules on the reverse proxy to enable mobility services for your external users.</span></span></p></td>
<td><p><span data-ttu-id="c0bd1-170"><a href="lync-server-2013-planning-for-mobility.md">Planejamento para mobilidade no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="c0bd1-170"><a href="lync-server-2013-planning-for-mobility.md">Planning for mobility in Lync Server 2013</a></span></span></p></td>
</tr>
</tbody>
</table>


<div>


> [!TIP]  
> <span data-ttu-id="c0bd1-171">Nas seções de cenários a seguir estão as arquiteturas de referência, o exemplo de DNS, as definições de porta/protocolo e os requisitos de certificado.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-171">In the following Scenarios sections are reference architectures, example DNS, port/protocol definitions, and certificate requirements.</span></span> <span data-ttu-id="c0bd1-172">Também estão incluídos diagramas para suas definições de DNS, porta/protocolo e necessidades de certificado.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-172">Also included are diagrams for your DNS, port/protocol definitions and certificate needs.</span></span> <span data-ttu-id="c0bd1-173">Os diagramas fornecerão um modelo para você preencher e distribuir para outras equipes (por exemplo, a equipe de rede da sua organização, a equipe da infraestrutura de chave pública e a equipe de implantação do servidor).</span><span class="sxs-lookup"><span data-stu-id="c0bd1-173">The diagrams will provide a template for you to fill in and distribute to other teams (for example, your organization’s Network Team, Public Key Infrastructure Team, and Server Deployment Team).</span></span> <span data-ttu-id="c0bd1-174">A meta dos diagramas é melhorar a comunicação e garantir o sucesso ao comunicar os elementos de configuração do servidor de borda necessárias para as pessoas que farão o trabalho de configuração real.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-174">The goal of the diagrams is to enhance communication and to ensure success when communicating the required Edge Server configuration elements to the people who will do the actual configuration work.</span></span> <span data-ttu-id="c0bd1-175">Recomendamos que você use os diagramas e as arquiteturas de referência associadas para planejar a implantação.</span><span class="sxs-lookup"><span data-stu-id="c0bd1-175">We recommend that you use the diagrams and associated reference architectures to plan your deployment.</span></span>



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

