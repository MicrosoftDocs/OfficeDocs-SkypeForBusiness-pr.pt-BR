---
title: 'Lync Server 2013: Suporte a cliente e servidor para Roteamento Baseado em Local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5ad7ead20eb9961180fec9204a84b3392b7fa96f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729851"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="bedd8-102">Suporte a cliente e servidor para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bedd8-103">_**Tópico da última modificação:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="bedd8-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="bedd8-104">O roteamento baseado em local é imposto pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="bedd8-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="bedd8-105">O Lync Server pode identificar os sites de rede nos quais os usuários estão se conectando dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="bedd8-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="bedd8-106">Como os usuários remotos estão fora da rede corporativa, seu local é considerado desconhecido.</span><span class="sxs-lookup"><span data-stu-id="bedd8-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="bedd8-107">Suporte ao Lync Server</span><span class="sxs-lookup"><span data-stu-id="bedd8-107">Lync Server Support</span></span>

<span data-ttu-id="bedd8-108">O roteamento baseado em localização requer que o Lync Server 2013 CU1 seja implantado em todos os pools de front-end e servidores Standard Edition em uma determinada topologia.</span><span class="sxs-lookup"><span data-stu-id="bedd8-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="bedd8-109">Se o Lync Server 2013 CU1 não estiver instalado em certos componentes do Lync na topologia, as restrições de roteamento baseadas em local não poderão ser totalmente impostas.</span><span class="sxs-lookup"><span data-stu-id="bedd8-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="bedd8-110">A tabela a seguir identifica a combinação de funções de servidor e versões com suporte para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="bedd8-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bedd8-111">Versão do pool</span><span class="sxs-lookup"><span data-stu-id="bedd8-111">Pool version</span></span></th>
<th><span data-ttu-id="bedd8-112">Versão do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="bedd8-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="bedd8-113">Com suporte</span><span class="sxs-lookup"><span data-stu-id="bedd8-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bedd8-114">Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="bedd8-115">Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="bedd8-116">sim</span><span class="sxs-lookup"><span data-stu-id="bedd8-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bedd8-117">Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="bedd8-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="bedd8-119">não</span><span class="sxs-lookup"><span data-stu-id="bedd8-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bedd8-120">Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="bedd8-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bedd8-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="bedd8-122">não</span><span class="sxs-lookup"><span data-stu-id="bedd8-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bedd8-123">Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="bedd8-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bedd8-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="bedd8-125">não</span><span class="sxs-lookup"><span data-stu-id="bedd8-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bedd8-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="bedd8-127">qualquer um</span><span class="sxs-lookup"><span data-stu-id="bedd8-127">any</span></span></p></td>
<td><p><span data-ttu-id="bedd8-128">não</span><span class="sxs-lookup"><span data-stu-id="bedd8-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bedd8-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="bedd8-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="bedd8-130">qualquer um</span><span class="sxs-lookup"><span data-stu-id="bedd8-130">any</span></span></p></td>
<td><p><span data-ttu-id="bedd8-131">não</span><span class="sxs-lookup"><span data-stu-id="bedd8-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bedd8-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bedd8-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="bedd8-133">qualquer um</span><span class="sxs-lookup"><span data-stu-id="bedd8-133">any</span></span></p></td>
<td><p><span data-ttu-id="bedd8-134">não</span><span class="sxs-lookup"><span data-stu-id="bedd8-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="bedd8-135">Suporte ao cliente do Lync</span><span class="sxs-lookup"><span data-stu-id="bedd8-135">Lync Client Support</span></span>

<span data-ttu-id="bedd8-136">A tabela a seguir identifica os clientes com suporte para o roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="bedd8-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="bedd8-137">Tipo de cliente</span><span class="sxs-lookup"><span data-stu-id="bedd8-137">Client type</span></span></th>
<th><span data-ttu-id="bedd8-138">Com suporte</span><span class="sxs-lookup"><span data-stu-id="bedd8-138">Supported</span></span></th>
<th><span data-ttu-id="bedd8-139">Detalhes</span><span class="sxs-lookup"><span data-stu-id="bedd8-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="bedd8-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="bedd8-141">sim</span><span class="sxs-lookup"><span data-stu-id="bedd8-141">yes</span></span></p></td>
<td><p><span data-ttu-id="bedd8-142">Incluindo a atualização cumulativa do Lync 2013 de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bedd8-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="bedd8-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="bedd8-144">sim</span><span class="sxs-lookup"><span data-stu-id="bedd8-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bedd8-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="bedd8-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="bedd8-146">não</span><span class="sxs-lookup"><span data-stu-id="bedd8-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bedd8-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="bedd8-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="bedd8-148">sim</span><span class="sxs-lookup"><span data-stu-id="bedd8-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bedd8-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="bedd8-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="bedd8-150">sim</span><span class="sxs-lookup"><span data-stu-id="bedd8-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bedd8-151">Lync para Windows 8</span><span class="sxs-lookup"><span data-stu-id="bedd8-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="bedd8-152">não</span><span class="sxs-lookup"><span data-stu-id="bedd8-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="bedd8-153">Lync móvel 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="bedd8-154">não</span><span class="sxs-lookup"><span data-stu-id="bedd8-154">no</span></span></p></td>
<td><p><span data-ttu-id="bedd8-155">O VoIP deve ser desabilitado para os clientes do Lync Mobile 2013 se usado por usuários com roteamento baseado em local habilitado.</span><span class="sxs-lookup"><span data-stu-id="bedd8-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="bedd8-156">Lync móvel 2010</span><span class="sxs-lookup"><span data-stu-id="bedd8-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="bedd8-157">sim</span><span class="sxs-lookup"><span data-stu-id="bedd8-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="bedd8-158">Para desabilitar o VoIP para clientes móveis do Lync 2013, atribua uma política de mobilidade com a configuração, áudio/vídeo IP, desabilitada para todos os usuários habilitados para roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="bedd8-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="bedd8-159">Para obter mais detalhes sobre política de mobilidade, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="bedd8-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bedd8-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="bedd8-160">See Also</span></span>


[<span data-ttu-id="bedd8-161">Planejamento de Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bedd8-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

