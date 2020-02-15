---
title: 'Lync Server 2013: configurar interfaces de rede para servidores de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Set up network interfaces for Edge Servers
ms:assetid: b0aecdf6-4ae2-46f6-b9b6-948bfc3df11e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412847(v=OCS.15)
ms:contentKeyID: 48185152
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 49b363e4803d493ed5859455104945d0d1d2d23c
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034231"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="a34e5-102">Configurar interfaces de rede para servidores de borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="a34e5-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="a34e5-103">_**Última modificação do tópico:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="a34e5-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="a34e5-p101">Cada Servidor de Borda é um computador multihomed com interfaces externas e internas. As configurações de DNS do adaptador dependem da existência de servidores DNS na rede de perímetro. Se houver servidores DNS no perímetro, eles deverão ter uma zona contendo um ou mais registros A DNS para o servidor ou pool de próximo salto (ou seja, um Diretor ou um pool de Front-Ends designado) e, para consultas externas, eles farão referência a pesquisas de nome para outros servidores DNS públicos. Se não houver servidores DNS no perímetro, os Servidores de Borda usarão servidores DNS externos para resolver pesquisas de nome da Internet, e cada Servidor de Borda usará um HOST para resolver os nomes de servidor de próximo salto para endereços IP.</span><span class="sxs-lookup"><span data-stu-id="a34e5-p101">Each Edge Server is a multihomed computer with external and internal facing interfaces. The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network. If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers. If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" /><span data-ttu-id="a34e5-109">Observação de segurança:</span><span class="sxs-lookup"><span data-stu-id="a34e5-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="a34e5-110">Por motivos de segurança, recomendamos que seus Servidores de Borda não acessem um servidor DNS localizado na rede interna.</span><span class="sxs-lookup"><span data-stu-id="a34e5-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="a34e5-111">Para configurar interfaces com os servidores DNS na rede de perímetro</span><span class="sxs-lookup"><span data-stu-id="a34e5-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="a34e5-112">Instale dois adaptadores de rede para cada Servidor de Borda, um para a interface interna e outro para a interface externa.</span><span class="sxs-lookup"><span data-stu-id="a34e5-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a34e5-113">As sub-redes interna e externa não devem ser roteáveis ente si.</span><span class="sxs-lookup"><span data-stu-id="a34e5-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="a34e5-p102">Na interface externa, configure três endereços IP estáticos na sub-rede da rede de perímetro externa (também conhecida como DMZ, zona desmilitarizada, e sub-rede filtrada), e aponte o gateway padrão à interface interna do firewall externo. Defina as configurações DNS do adaptador para apontar para um par de servidores DNS de perímetro.</span><span class="sxs-lookup"><span data-stu-id="a34e5-p102">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall. Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a34e5-116">É possível usar um endereço IP para essa interface, mas para fazer isso você precisa alterar as atribuições de porta para valores não padrão.</span><span class="sxs-lookup"><span data-stu-id="a34e5-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="a34e5-117">Você determina isso ao criar a topologia no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="a34e5-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="a34e5-p104">Na interface interna, configure um endereço IP estático na sub-rede da rede de perímetro e não defina o gateway padrão. Defina as configurações DNS do adaptador a fim de apontar para pelo menos um servidor DNS, preferencialmente um par de servidores DNS de perímetro.</span><span class="sxs-lookup"><span data-stu-id="a34e5-p104">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="a34e5-120">Crie rotas estáticas persistentes na interface interna para todas as redes internas nas quais os clientes, o Lync Server 2013 e os servidores da UM (Unificação de mensagens) do Exchange residem.</span><span class="sxs-lookup"><span data-stu-id="a34e5-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="a34e5-121">Para configurar interfaces sem servidores DNS na rede de perímetro</span><span class="sxs-lookup"><span data-stu-id="a34e5-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="a34e5-122">Instale dois adaptadores de rede para cada Servidor de Borda, um para a interface interna e outro para a interface externa.</span><span class="sxs-lookup"><span data-stu-id="a34e5-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="a34e5-123">As sub-redes interna e externa não devem ser roteáveis ente si.</span><span class="sxs-lookup"><span data-stu-id="a34e5-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="a34e5-p105">Na interface externa, configure três endereços IP estáticos na sub-rede da rede de perímetro externa. Também é possível configurar o gateway padrão na interface externa. Por exemplo, defina o roteador da Internet ou o firewall externo como o gateway padrão. Defina as configurações de DNS a fim de apontar para um servidor DNS, preferencialmente para um par de servidores DNS externos.</span><span class="sxs-lookup"><span data-stu-id="a34e5-p105">On the external interface, configure three static IP addresses on the external perimeter network subnet. You also configure the default gateway on the external interface. For example, define the Internet-facing router or the external firewall as the default gateway. Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="a34e5-128">É possível, mas não recomendado, usar um endereço IP para a interface externa.</span><span class="sxs-lookup"><span data-stu-id="a34e5-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="a34e5-129">Para que isso funcione, você precisa alterar as atribuições de porta para valores não padrão e para longe da porta padrão 443 que normalmente é “amigável com firewall” para a comunicações do cliente.</span><span class="sxs-lookup"><span data-stu-id="a34e5-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="a34e5-130">Você determina a configuração de endereço IP e as configurações de porta ao criar a topologia no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="a34e5-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="a34e5-p107">Na interface interna, configure um endereço IP estático na sub-rede da rede de perímetro e não defina o gateway padrão. Deixe as configurações DNS do adaptador vazias.</span><span class="sxs-lookup"><span data-stu-id="a34e5-p107">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway. Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="a34e5-133">Crie rotas estáticas persistentes na interface interna para todas as redes internas nas quais os clientes do Lync ou servidores que executam o Lync Server 2013 residem.</span><span class="sxs-lookup"><span data-stu-id="a34e5-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="a34e5-134">Edite o arquivo HOST em cada servidor de borda para que contenha um registro para o próximo servidor de salto ou IP virtual (VIP) (o registro será o diretor, servidor Standard Edition ou um pool de front-ends configurado como o endereço de próximo salto do servidor de borda no construtor de topologias).</span><span class="sxs-lookup"><span data-stu-id="a34e5-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="a34e5-135">Se você estiver usando o balanceamento de carga DNS, inclua uma linha para cada membro do pool de próximo salto.</span><span class="sxs-lookup"><span data-stu-id="a34e5-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

