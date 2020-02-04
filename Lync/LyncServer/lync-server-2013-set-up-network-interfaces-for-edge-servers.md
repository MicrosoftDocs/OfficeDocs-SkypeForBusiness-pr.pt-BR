---
title: 'Lync Server 2013: Configurar interfaces de rede para Servidores de Borda'
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
ms.openlocfilehash: dfbae47a5f5e99e603e3f095a2e07dbb9b49515f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41764637"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="set-up-network-interfaces-for-edge-servers-in-lync-server-2013"></a><span data-ttu-id="c0783-102">Configurar interfaces de rede para Servidores de Borda no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c0783-102">Set up network interfaces for Edge Servers in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c0783-103">_**Tópico da última modificação:** 2012-09-08_</span><span class="sxs-lookup"><span data-stu-id="c0783-103">_**Topic Last Modified:** 2012-09-08_</span></span>

<span data-ttu-id="c0783-104">Cada servidor de borda é um computador com várias bases, com interfaces opostas externas e internas.</span><span class="sxs-lookup"><span data-stu-id="c0783-104">Each Edge Server is a multihomed computer with external and internal facing interfaces.</span></span> <span data-ttu-id="c0783-105">As configurações de DNS (sistema de nomes de domínio) de adaptador dependem se há servidores DNS na rede de perímetro.</span><span class="sxs-lookup"><span data-stu-id="c0783-105">The adapter Domain Name System (DNS) settings depend on whether there are DNS servers in the perimeter network.</span></span> <span data-ttu-id="c0783-106">Se houver servidores DNS no perímetro, eles devem ter uma zona contendo um ou mais registros DNS A para o próximo servidor ou pool de salto (ou seja, um diretor ou um pool Front-end designado) e para consultas externas, elas fazem referência a nomes de pesquisa para outros servidores DNS públicos.</span><span class="sxs-lookup"><span data-stu-id="c0783-106">If DNS servers exist in the perimeter, they must have a zone containing one or more DNS A records for the next hop server or pool (that is, either a Director or a designated Front End pool), and for external queries they refer name lookups to other public DNS servers.</span></span> <span data-ttu-id="c0783-107">Se não existirem servidores DNS no perímetro, o (s) servidor (es) de borda usará servidores DNS externos para resolver pesquisas de nomes de Internet, e cada servidor de borda usará um HOST para resolver os nomes de servidor de salto seguinte para endereços IP.</span><span class="sxs-lookup"><span data-stu-id="c0783-107">If no DNS servers exist in the perimeter, the Edge Server(s) use external DNS servers to resolve Internet name lookups, and each Edge Server uses a HOST to resolve the next hop server names to IP addresses.</span></span>

<div>

<table>
<thead>
<tr class="header">
<th><img src="images/Gg398321.security(OCS.15).gif" title="segurança" alt="security" /><span data-ttu-id="c0783-109">Observação de segurança:</span><span class="sxs-lookup"><span data-stu-id="c0783-109">Security Note:</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c0783-110">Por motivos de segurança, recomendamos que você não tenha seus servidores de borda acessarem um servidor DNS localizado na rede interna.</span><span class="sxs-lookup"><span data-stu-id="c0783-110">For security reasons, we recommend that you do not have your Edge Servers access a DNS server located in the internal network.</span></span></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-configure-interfaces-with-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="c0783-111">Para configurar interfaces com servidores DNS na rede de perímetro</span><span class="sxs-lookup"><span data-stu-id="c0783-111">To configure interfaces with DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="c0783-112">Instale dois adaptadores de rede para cada servidor de borda, um para a interface de face interna e outro para a interface de face externa.</span><span class="sxs-lookup"><span data-stu-id="c0783-112">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0783-113">As sub-redes interna e externa não devem ser roteáveis ente si.</span><span class="sxs-lookup"><span data-stu-id="c0783-113">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="c0783-114">Na interface externa, configure três endereços IP estáticos na sub-rede externa de perímetro (também conhecida como DMZ, zona desmilitarizada e sub-rede filtrada) e aponte o gateway padrão para a interface interna do firewall externo.</span><span class="sxs-lookup"><span data-stu-id="c0783-114">On the external interface, configure three static IP addresses on the external perimeter network (also known as DMZ, demilitarized zone, and screened subnet) subnet, and point the default gateway to the internal interface of the external firewall.</span></span> <span data-ttu-id="c0783-115">Defina as configurações de DNS do adaptador para apontar para um par de servidores DNS do perímetro.</span><span class="sxs-lookup"><span data-stu-id="c0783-115">Configure adapter DNS settings to point to a pair of perimeter DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0783-116">É possível usar o mínimo de um endereço IP para essa interface, mas para fazer isso, você precisa mudar as atribuições de porta para valores não padrão.</span><span class="sxs-lookup"><span data-stu-id="c0783-116">It is possible to use as few as one IP address for this interface, but to do this you need to change the port assignments to non-standard values.</span></span> <span data-ttu-id="c0783-117">Você determina isso quando cria a topologia no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="c0783-117">You determine this when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="c0783-118">Na interface interna, configure um endereço IP estático na sub-rede de rede de perímetro interna e não defina um gateway padrão.</span><span class="sxs-lookup"><span data-stu-id="c0783-118">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="c0783-119">Defina as configurações de DNS do adaptador para apontar para pelo menos um servidor DNS, de preferência um par de servidores DNS de perímetro.</span><span class="sxs-lookup"><span data-stu-id="c0783-119">Configure adapter DNS settings to point to at least one DNS server, preferably a pair of perimeter DNS servers.</span></span>

4.  <span data-ttu-id="c0783-120">Crie rotas estáticas persistentes na interface interna para todas as redes internas em que os clientes, o Lync Server 2013 e os servidores Exchange Unified Messaging (UM) residem.</span><span class="sxs-lookup"><span data-stu-id="c0783-120">Create persistent static routes on the internal interface to all internal networks where clients, Lync Server 2013, and Exchange Unified Messaging (UM) servers reside.</span></span>

</div>

<div>

## <a name="to-configure-interfaces-without-dns-servers-in-the-perimeter-network"></a><span data-ttu-id="c0783-121">Para configurar interfaces sem servidores DNS na rede de perímetro</span><span class="sxs-lookup"><span data-stu-id="c0783-121">To configure interfaces without DNS servers in the perimeter network</span></span>

1.  <span data-ttu-id="c0783-122">Instale dois adaptadores de rede para cada servidor de borda, um para a interface de face interna e outro para a interface de face externa.</span><span class="sxs-lookup"><span data-stu-id="c0783-122">Install two network adapters for each Edge Server, one for the internal-facing interface and one for the external-facing interface.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="c0783-123">As sub-redes interna e externa não devem ser roteáveis ente si.</span><span class="sxs-lookup"><span data-stu-id="c0783-123">The internal and external subnets must not be routable to each other.</span></span>

    
    </div>

2.  <span data-ttu-id="c0783-124">Na interface externa, configure três endereços IP estáticos na sub-rede de rede do perímetro externo.</span><span class="sxs-lookup"><span data-stu-id="c0783-124">On the external interface, configure three static IP addresses on the external perimeter network subnet.</span></span> <span data-ttu-id="c0783-125">Você também pode configurar o gateway padrão na interface externa.</span><span class="sxs-lookup"><span data-stu-id="c0783-125">You also configure the default gateway on the external interface.</span></span> <span data-ttu-id="c0783-126">Por exemplo, defina o roteador voltado para a Internet ou o firewall externo como o gateway padrão.</span><span class="sxs-lookup"><span data-stu-id="c0783-126">For example, define the Internet-facing router or the external firewall as the default gateway.</span></span> <span data-ttu-id="c0783-127">Defina as configurações de DNS para apontar para um servidor DNS, de preferência a um par de servidores DNS externos.</span><span class="sxs-lookup"><span data-stu-id="c0783-127">Configure DNS settings to point to a DNS server, preferably to a pair of external DNS servers.</span></span>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="c0783-128">É possível, mas não recomendado, usar o mesmo que um endereço IP para a interface externa.</span><span class="sxs-lookup"><span data-stu-id="c0783-128">It is possible, but not recommended, to use as few as one IP address for the external interface.</span></span> <span data-ttu-id="c0783-129">Para permitir que isso funcione, você precisa mudar as atribuições de porta para valores não padrão e para longe da porta padrão 443 que geralmente é "compatível com firewall" para a comunicação do cliente.</span><span class="sxs-lookup"><span data-stu-id="c0783-129">To allow this to work, you need to change the port assignments to non-standard values, and away from the default port 443 that is typically “firewall friendly” for client communication.</span></span> <span data-ttu-id="c0783-130">Você determina a configuração de endereço IP e as configurações de porta ao criar a topologia no construtor de topologias.</span><span class="sxs-lookup"><span data-stu-id="c0783-130">You determine the IP address setting and the port settings when you create the topology in Topology Builder.</span></span>

    
    </div>

3.  <span data-ttu-id="c0783-131">Na interface interna, configure um endereço IP estático na sub-rede de rede de perímetro interna e não defina um gateway padrão.</span><span class="sxs-lookup"><span data-stu-id="c0783-131">On the internal interface, configure one static IP address on the internal perimeter network subnet and do not set a default gateway.</span></span> <span data-ttu-id="c0783-132">Deixe as configurações de DNS do adaptador vazias.</span><span class="sxs-lookup"><span data-stu-id="c0783-132">Leave adapter DNS settings empty.</span></span>

4.  <span data-ttu-id="c0783-133">Crie rotas estáticas persistentes na interface interna para todas as redes internas em que os clientes ou servidores do Lync que executam o Lync Server 2013 se encontram.</span><span class="sxs-lookup"><span data-stu-id="c0783-133">Create persistent static routes on the internal interface to all internal networks where Lync clients or servers running Lync Server 2013 reside.</span></span>

5.  <span data-ttu-id="c0783-134">Edite o arquivo de HOST em cada servidor de borda para conter um registro para o próximo servidor de salto ou IP virtual (VIP) (o registro será o diretor, Standard Edition Server ou um pool de front-ends configurado como o próximo endereço de salto do servidor de borda no construtor de topologias).</span><span class="sxs-lookup"><span data-stu-id="c0783-134">Edit the HOST file on each Edge Server to contain a record for the next hop server or virtual IP (VIP) (the record will be the Director, Standard Edition server, or a Front End pool that was configured as the Edge Server next hop address in Topology Builder).</span></span> <span data-ttu-id="c0783-135">Se você estiver usando o balanceamento de carga de DNS, inclua uma linha para cada membro do próximo pool de saltos.</span><span class="sxs-lookup"><span data-stu-id="c0783-135">If you are using DNS load balancing, include a line for each member of the next hop pool.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

