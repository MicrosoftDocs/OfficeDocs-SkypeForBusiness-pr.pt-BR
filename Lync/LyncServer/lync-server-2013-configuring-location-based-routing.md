---
title: 'Lync Server 2013: Configurando o roteamento de Location-Based'
description: 'Lync Server 2013: Configurando o roteamento de Location-Based.'
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
ms.openlocfilehash: 080c2a3a82a8714fc35ce882b0c6cb1630552f27
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48570877"
---
# <a name="configuring-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="71c8a-103">Configurando o roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71c8a-103">Configuring Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="71c8a-104">_**Última modificação do tópico:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="71c8a-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="71c8a-105">Lync Server 2013 CU1, Location-Based roteamento é um recurso do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="71c8a-105">Lync Server 2013 CU1, Location-Based Routing is a feature of Enterprise Voice.</span></span> <span data-ttu-id="71c8a-106">Location-Based roteamento é um recurso de gerenciamento de chamadas que controla como as chamadas são encaminhadas pelo Lync Server 2013 CU1.</span><span class="sxs-lookup"><span data-stu-id="71c8a-106">Location-Based Routing is a call management feature that controls how calls are routed by Lync Server 2013 CU1.</span></span> <span data-ttu-id="71c8a-107">Ela impõe restrições sobre se as chamadas podem ser roteadas para destinos PBX ou PSTN com base no local do chamador do Lync.</span><span class="sxs-lookup"><span data-stu-id="71c8a-107">It enforces restrictions on whether calls can be routed to PBX or PSTN destinations based on the Lync caller’s location.</span></span> <span data-ttu-id="71c8a-108">Location-Based roteamento aplica regras de autorização de chamada a chamadas PSTN com base no local de rede do chamador.</span><span class="sxs-lookup"><span data-stu-id="71c8a-108">Location-Based Routing applies call authorization rules to PSTN calls based on the caller’s network location.</span></span> <span data-ttu-id="71c8a-109">O local do chamador é determinado com base no site de rede associado à sub-rede da rede na qual o chamador está conectado.</span><span class="sxs-lookup"><span data-stu-id="71c8a-109">The caller’s location is determined based on the network site associated with the network subnet the caller is connected on.</span></span> <span data-ttu-id="71c8a-110">A configuração do roteamento de Location-Based exige primeiro implantação do Enterprise Voice e, em seguida, a configuração de regiões de rede, sites e sub-redes.</span><span class="sxs-lookup"><span data-stu-id="71c8a-110">Configuring Location-Based Routing requires first deploying Enterprise Voice, then configuring network regions, sites and subnets.</span></span> <span data-ttu-id="71c8a-111">Isso configura a base para habilitar o roteamento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="71c8a-111">This sets up the foundation for enabling Location-Based Routing.</span></span>

<span data-ttu-id="71c8a-112">Antes de implantar o roteamento de Location-Based, você deve primeiro implantar o Enterprise Voice e configurar regiões de rede, sites e associar sub-redes de rede aos seus sites de rede.</span><span class="sxs-lookup"><span data-stu-id="71c8a-112">Before deploying Location-Based Routing, you must first deploy Enterprise Voice, and configure network regions, sites, and associate network subnets to your network sites.</span></span> <span data-ttu-id="71c8a-113">Após a conclusão, é possível configurar o roteamento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="71c8a-113">Once completed, you can configure Location-Based Routing.</span></span> <span data-ttu-id="71c8a-114">Para obter etapas sobre como configurar regiões de rede, sites e sub-redes, consulte [Deploying Advanced Enterprise Voice Features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span><span class="sxs-lookup"><span data-stu-id="71c8a-114">For steps on how to configure network regions, sites and subnets, see [Deploying advanced Enterprise Voice features in Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)</span></span>

<span data-ttu-id="71c8a-115">Esta seção orienta você durante a configuração do roteamento Location-Based usando o exemplo a seguir como ilustração.</span><span class="sxs-lookup"><span data-stu-id="71c8a-115">This section guides you through the configuration of Location-Based Routing using the following example as illustration.</span></span>

<span data-ttu-id="71c8a-116">![Exemplo de roteamento baseado no local do Enterprise Voice](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Exemplo de roteamento baseado no local do Enterprise Voice")</span><span class="sxs-lookup"><span data-stu-id="71c8a-116">![Enterprise Voice location-based routing example](images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Enterprise Voice location-based routing example")</span></span>

  
<span data-ttu-id="71c8a-117">A tabela a seguir representa os usuários definidos neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="71c8a-117">The following table represents the users defined in this example.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71c8a-118">Tipo de ponto de extremidade</span><span class="sxs-lookup"><span data-stu-id="71c8a-118">Endpoint type</span></span></th>
<th><span data-ttu-id="71c8a-119">Local</span><span class="sxs-lookup"><span data-stu-id="71c8a-119">Location</span></span></th>
<th><span data-ttu-id="71c8a-120">Usuários</span><span class="sxs-lookup"><span data-stu-id="71c8a-120">Users</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71c8a-121">Lync</span><span class="sxs-lookup"><span data-stu-id="71c8a-121">Lync</span></span></p></td>
<td><p><span data-ttu-id="71c8a-122">Escritório corporativo de Déli</span><span class="sxs-lookup"><span data-stu-id="71c8a-122">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="71c8a-123">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="71c8a-123">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c8a-124">Lync</span><span class="sxs-lookup"><span data-stu-id="71c8a-124">Lync</span></span></p></td>
<td><p><span data-ttu-id="71c8a-125">Escritório corporativo do Hyderabad</span><span class="sxs-lookup"><span data-stu-id="71c8a-125">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="71c8a-126">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="71c8a-126">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c8a-127">Lync</span><span class="sxs-lookup"><span data-stu-id="71c8a-127">Lync</span></span></p></td>
<td><p><span data-ttu-id="71c8a-128">Desconhecido (ou seja, Hotel)</span><span class="sxs-lookup"><span data-stu-id="71c8a-128">Unknown (i.e. hotel)</span></span></p></td>
<td><p><span data-ttu-id="71c8a-129">UNK-LYNC-1</span><span class="sxs-lookup"><span data-stu-id="71c8a-129">UNK-LYNC-1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c8a-130">RESPECTIVA</span><span class="sxs-lookup"><span data-stu-id="71c8a-130">PBX</span></span></p></td>
<td><p><span data-ttu-id="71c8a-131">Escritório corporativo de Déli</span><span class="sxs-lookup"><span data-stu-id="71c8a-131">Delhi corporate office</span></span></p></td>
<td><p><span data-ttu-id="71c8a-132">DEL-PBX-1, DEL-PBX-2</span><span class="sxs-lookup"><span data-stu-id="71c8a-132">DEL-PBX-1, DEL-PBX-2</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c8a-133">RESPECTIVA</span><span class="sxs-lookup"><span data-stu-id="71c8a-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="71c8a-134">Escritório corporativo do Hyderabad</span><span class="sxs-lookup"><span data-stu-id="71c8a-134">Hyderabad corporate office</span></span></p></td>
<td><p><span data-ttu-id="71c8a-135">HYD-PBX-1, HYD-PBX-2</span><span class="sxs-lookup"><span data-stu-id="71c8a-135">HYD-PBX-1, HYD-PBX-2</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c8a-136">PSTN</span><span class="sxs-lookup"><span data-stu-id="71c8a-136">PSTN</span></span></p></td>
<td><p><span data-ttu-id="71c8a-137">Desconhecido</span><span class="sxs-lookup"><span data-stu-id="71c8a-137">Unknown</span></span></p></td>
<td><p><span data-ttu-id="71c8a-138">PSTN-1, PSTN-2, PSTN-3</span><span class="sxs-lookup"><span data-stu-id="71c8a-138">PSTN-1, PSTN-2, PSTN-3</span></span></p></td>
</tr>
</tbody>
</table>

  

<span data-ttu-id="71c8a-139">A tabela a seguir representa os sistemas ilustrados neste exemplo de ambiente.</span><span class="sxs-lookup"><span data-stu-id="71c8a-139">The following table represents the systems illustrated in this example environment.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="71c8a-140">Sistema</span><span class="sxs-lookup"><span data-stu-id="71c8a-140">System</span></span></th>
<th><span data-ttu-id="71c8a-141">Local</span><span class="sxs-lookup"><span data-stu-id="71c8a-141">Location</span></span></th>
<th><span data-ttu-id="71c8a-142">Nome</span><span class="sxs-lookup"><span data-stu-id="71c8a-142">Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="71c8a-143">Lync Server 2013 CU1 pool</span><span class="sxs-lookup"><span data-stu-id="71c8a-143">Lync Server 2013 CU1 pool</span></span></p></td>
<td><p><span data-ttu-id="71c8a-144">qualquer</span><span class="sxs-lookup"><span data-stu-id="71c8a-144">any</span></span></p></td>
<td><p><span data-ttu-id="71c8a-145">LS-PL1</span><span class="sxs-lookup"><span data-stu-id="71c8a-145">LS-PL1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c8a-146">Lync Server 2013 CU1, servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="71c8a-146">Lync Server 2013 CU1, Mediation Server</span></span></p></td>
<td><p><span data-ttu-id="71c8a-147">qualquer</span><span class="sxs-lookup"><span data-stu-id="71c8a-147">any</span></span></p></td>
<td><p><span data-ttu-id="71c8a-148">MS-PL1</span><span class="sxs-lookup"><span data-stu-id="71c8a-148">MS-PL1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c8a-149">Gateway PSTN 1</span><span class="sxs-lookup"><span data-stu-id="71c8a-149">PSTN gateway 1</span></span></p></td>
<td><p><span data-ttu-id="71c8a-150">Déli</span><span class="sxs-lookup"><span data-stu-id="71c8a-150">Delhi</span></span></p></td>
<td><p><span data-ttu-id="71c8a-151">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="71c8a-151">DEL-GW</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c8a-152">Gateway PSTN 2</span><span class="sxs-lookup"><span data-stu-id="71c8a-152">PSTN gateway 2</span></span></p></td>
<td><p><span data-ttu-id="71c8a-153">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="71c8a-153">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="71c8a-154">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="71c8a-154">HYD-GW</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="71c8a-155">PBX 1</span><span class="sxs-lookup"><span data-stu-id="71c8a-155">PBX 1</span></span></p></td>
<td><p><span data-ttu-id="71c8a-156">Déli</span><span class="sxs-lookup"><span data-stu-id="71c8a-156">Delhi</span></span></p></td>
<td><p><span data-ttu-id="71c8a-157">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="71c8a-157">DEL-PBX</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="71c8a-158">PBX 2</span><span class="sxs-lookup"><span data-stu-id="71c8a-158">PBX 2</span></span></p></td>
<td><p><span data-ttu-id="71c8a-159">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="71c8a-159">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="71c8a-160">PBX VERMELHA</span><span class="sxs-lookup"><span data-stu-id="71c8a-160">RED-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a><span data-ttu-id="71c8a-161">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="71c8a-161">In This Section</span></span>

  - [<span data-ttu-id="71c8a-162">Configurando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71c8a-162">Configuring Enterprise Voice in Lync Server 2013</span></span>](lync-server-2013-configuring-enterprise-voice.md)

  - [<span data-ttu-id="71c8a-163">Implantando regiões de rede, sites e sub-redes no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71c8a-163">Deploying network regions, sites, and subnets in Lync Server 2013</span></span>](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [<span data-ttu-id="71c8a-164">Habilitando o roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71c8a-164">Enabling Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="71c8a-165">Confira também</span><span class="sxs-lookup"><span data-stu-id="71c8a-165">See Also</span></span>


[<span data-ttu-id="71c8a-166">Implantando recursos avançados do Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="71c8a-166">Deploying advanced Enterprise Voice features in Lync Server 2013</span></span>](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

