---
title: 'Lync Server 2013: Configurando o roteamento de Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7b703aa084204a2c103e02ebff5f913a6647ae94
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517408"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="97da0-102">Configurando o roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97da0-102">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="97da0-103">_**Última modificação do tópico:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="97da0-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="97da0-104">Lync Server 2013 CU1, Location-Based roteamento é um recurso do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="97da0-104">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="97da0-105">Location-Based roteamento é um recurso de gerenciamento de chamadas que controla como as chamadas são encaminhadas pelo Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="97da0-105">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="97da0-106">Ela impõe restrições sobre se as chamadas podem ser roteadas para destinos PBX ou PSTN com base no local do chamador do Lync.</span><span class="sxs-lookup"><span data-stu-id="97da0-106">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="97da0-107">Location-Based roteamento aplica regras de autorização de chamada a chamadas PSTN com base no local de rede do chamador.</span><span class="sxs-lookup"><span data-stu-id="97da0-107">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="97da0-108">O local do chamador é determinado com base no site de rede associado à sub-rede da rede na qual o chamador está conectado.</span><span class="sxs-lookup"><span data-stu-id="97da0-108">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="97da0-109">A configuração do roteamento de Location-Based exige primeiro implantação do Enterprise Voice e, em seguida, a configuração de regiões de rede, sites e sub-redes.</span><span class="sxs-lookup"><span data-stu-id="97da0-109">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="97da0-110">Isso configura a base para habilitar o roteamento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="97da0-110">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="97da0-111">Antes de implantar o roteamento de Location-Based, você deve primeiro implantar o Enterprise Voice e configurar regiões de rede, sites e associar sub-redes de rede aos seus sites de rede.</span><span class="sxs-lookup"><span data-stu-id="97da0-111">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="97da0-112">Após a conclusão, é possível configurar o roteamento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="97da0-112">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="97da0-113">Para obter etapas sobre como configurar regiões de rede, sites e sub-redes, consulte [Deploying Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="97da0-113">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="97da0-114">Esta seção orienta você durante a configuração do roteamento Location-Based usando o exemplo a seguir como ilustração.</span><span class="sxs-lookup"><span data-stu-id="97da0-114">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="97da0-115">![Exemplo de roteamento baseado no local do Enterprise Voice](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Exemplo de roteamento baseado no local do Enterprise Voice")</span><span class="sxs-lookup"><span data-stu-id="97da0-115">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="97da0-116">A tabela a seguir representa os usuários definidos neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="97da0-116">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97da0-117">Tipo de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="97da0-117">Endpoint type</span></span></th>
<th><span data-ttu-id="97da0-118">Local</span><span class="sxs-lookup"><span data-stu-id="97da0-118">Location</span></span></th>
<th><span data-ttu-id="97da0-119">Usuários</span><span class="sxs-lookup"><span data-stu-id="97da0-119">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97da0-120">Lync</span><span class="sxs-lookup"><span data-stu-id="97da0-120">Lync</span></span></p></td>
<td><p><span data-ttu-id="97da0-121">Escritório corporativo de Déli</span><span class="sxs-lookup"><span data-stu-id="97da0-121">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="97da0-122">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="97da0-122">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97da0-123">Lync</span><span class="sxs-lookup"><span data-stu-id="97da0-123">Lync</span></span></p></td>
<td><p><span data-ttu-id="97da0-124">Escritório corporativo do Hyderabad</span><span class="sxs-lookup"><span data-stu-id="97da0-124">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="97da0-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="97da0-125">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97da0-126">Lync</span><span class="sxs-lookup"><span data-stu-id="97da0-126">Lync</span></span></p></td>
<td><p><span data-ttu-id="97da0-127">Desconhecido (ou seja, Hotel)</span><span class="sxs-lookup"><span data-stu-id="97da0-127">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="97da0-128">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="97da0-128">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97da0-129">RESPECTIVA</span><span class="sxs-lookup"><span data-stu-id="97da0-129">PBX</span></span></p></td>
<td><p><span data-ttu-id="97da0-130">Escritório corporativo de Déli</span><span class="sxs-lookup"><span data-stu-id="97da0-130">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="97da0-131">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="97da0-131">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97da0-132">RESPECTIVA</span><span class="sxs-lookup"><span data-stu-id="97da0-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="97da0-133">Escritório corporativo do Hyderabad</span><span class="sxs-lookup"><span data-stu-id="97da0-133">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="97da0-134">HYD-PBX-1, HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="97da0-134">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97da0-135">PSTN</span><span class="sxs-lookup"><span data-stu-id="97da0-135">PSTN</span></span></p></td>
<td><p><span data-ttu-id="97da0-136">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="97da0-136">Unknown</span></span></p></td>
<td><p><span data-ttu-id="97da0-137">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="97da0-137">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="97da0-138">A tabela a seguir representa os sistemas ilustrados neste exemplo de ambiente.</span><span class="sxs-lookup"><span data-stu-id="97da0-138">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="97da0-139">Sistema</span><span class="sxs-lookup"><span data-stu-id="97da0-139">System</span></span></th>
<th><span data-ttu-id="97da0-140">Local</span><span class="sxs-lookup"><span data-stu-id="97da0-140">Location</span></span></th>
<th><span data-ttu-id="97da0-141">Nome</span><span class="sxs-lookup"><span data-stu-id="97da0-141">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="97da0-142">Lync Server 2013 CU1 pool</span><span class="sxs-lookup"><span data-stu-id="97da0-142">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="97da0-143">qualquer</span><span class="sxs-lookup"><span data-stu-id="97da0-143">any</span></span></p></td>
<td><p><span data-ttu-id="97da0-144">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="97da0-144">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97da0-145">Lync Server 2013 CU1, servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="97da0-145">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="97da0-146">qualquer</span><span class="sxs-lookup"><span data-stu-id="97da0-146">any</span></span></p></td>
<td><p><span data-ttu-id="97da0-147">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="97da0-147">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97da0-148">Gateway PSTN 1</span><span class="sxs-lookup"><span data-stu-id="97da0-148">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="97da0-149">Déli</span><span class="sxs-lookup"><span data-stu-id="97da0-149">Delhi</span></span></p></td>
<td><p><span data-ttu-id="97da0-150">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="97da0-150">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97da0-151">Gateway PSTN 2</span><span class="sxs-lookup"><span data-stu-id="97da0-151">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="97da0-152">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="97da0-152">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="97da0-153">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="97da0-153">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="97da0-154">PBX 1</span><span class="sxs-lookup"><span data-stu-id="97da0-154">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="97da0-155">Déli</span><span class="sxs-lookup"><span data-stu-id="97da0-155">Delhi</span></span></p></td>
<td><p><span data-ttu-id="97da0-156">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="97da0-156">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="97da0-157">PBX 2</span><span class="sxs-lookup"><span data-stu-id="97da0-157">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="97da0-158">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="97da0-158">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="97da0-159">PBX VERMELHA</span><span class="sxs-lookup"><span data-stu-id="97da0-159">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="97da0-160">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="97da0-160">In This Section</span></span>

  - [<span data-ttu-id="97da0-161">Configurando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97da0-161">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="97da0-162">Implantando regiões de rede, sites e sub-redes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97da0-162">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="97da0-163">Habilitando o roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97da0-163">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="97da0-164">Confira também</span><span class="sxs-lookup"><span data-stu-id="97da0-164">See Also</span></span>


[<span data-ttu-id="97da0-165">Implantando recursos avançados do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="97da0-165">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

