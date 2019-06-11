---
title: 'Lync Server 2013: Suporte a cliente e servidor para Roteamento Baseado em Local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3791b359422c4b5bef463a612db6f0b74c07f096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="b2cdc-102">Suporte a cliente e servidor para Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b2cdc-103">_**Tópico da última modificação:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="b2cdc-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="b2cdc-104">O roteamento baseado em local é imposto pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b2cdc-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="b2cdc-105">O Lync Server pode identificar os sites de rede nos quais os usuários estão se conectando dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="b2cdc-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="b2cdc-106">Como os usuários remotos estão fora da rede corporativa, seu local é considerado desconhecido.</span><span class="sxs-lookup"><span data-stu-id="b2cdc-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="b2cdc-107">Suporte ao Lync Server</span><span class="sxs-lookup"><span data-stu-id="b2cdc-107">Lync Server Support</span></span>

<span data-ttu-id="b2cdc-108">O roteamento baseado em localização requer que o Lync Server 2013 CU1 seja implantado em todos os pools de front-end e servidores Standard Edition em uma determinada topologia.</span><span class="sxs-lookup"><span data-stu-id="b2cdc-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="b2cdc-109">Se o Lync Server 2013 CU1 não estiver instalado em certos componentes do Lync na topologia, as restrições de roteamento baseadas em local não poderão ser totalmente impostas.</span><span class="sxs-lookup"><span data-stu-id="b2cdc-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="b2cdc-110">A tabela a seguir identifica a combinação de funções de servidor e versões com suporte para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="b2cdc-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2cdc-111">Versão do pool</span><span class="sxs-lookup"><span data-stu-id="b2cdc-111">Pool version</span></span></th>
<th><span data-ttu-id="b2cdc-112">Versão do Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="b2cdc-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="b2cdc-113">Com suporte</span><span class="sxs-lookup"><span data-stu-id="b2cdc-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2cdc-114">Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-115">Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-116">sim</span><span class="sxs-lookup"><span data-stu-id="b2cdc-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2cdc-117">Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-119">não</span><span class="sxs-lookup"><span data-stu-id="b2cdc-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2cdc-120">Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b2cdc-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-122">não</span><span class="sxs-lookup"><span data-stu-id="b2cdc-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2cdc-123">Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b2cdc-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-125">não</span><span class="sxs-lookup"><span data-stu-id="b2cdc-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2cdc-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-127">qualquer um</span><span class="sxs-lookup"><span data-stu-id="b2cdc-127">any</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-128">não</span><span class="sxs-lookup"><span data-stu-id="b2cdc-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2cdc-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b2cdc-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-130">qualquer um</span><span class="sxs-lookup"><span data-stu-id="b2cdc-130">any</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-131">não</span><span class="sxs-lookup"><span data-stu-id="b2cdc-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2cdc-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b2cdc-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-133">qualquer um</span><span class="sxs-lookup"><span data-stu-id="b2cdc-133">any</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-134">não</span><span class="sxs-lookup"><span data-stu-id="b2cdc-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="b2cdc-135">Suporte ao cliente do Lync</span><span class="sxs-lookup"><span data-stu-id="b2cdc-135">Lync Client Support</span></span>

<span data-ttu-id="b2cdc-136">A tabela a seguir identifica os clientes com suporte para o roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="b2cdc-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b2cdc-137">Tipo de cliente</span><span class="sxs-lookup"><span data-stu-id="b2cdc-137">Client type</span></span></th>
<th><span data-ttu-id="b2cdc-138">Com suporte</span><span class="sxs-lookup"><span data-stu-id="b2cdc-138">Supported</span></span></th>
<th><span data-ttu-id="b2cdc-139">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b2cdc-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b2cdc-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-141">sim</span><span class="sxs-lookup"><span data-stu-id="b2cdc-141">yes</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-142">Incluindo a atualização cumulativa do Lync 2013 de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2cdc-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b2cdc-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-144">sim</span><span class="sxs-lookup"><span data-stu-id="b2cdc-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2cdc-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b2cdc-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-146">não</span><span class="sxs-lookup"><span data-stu-id="b2cdc-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2cdc-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="b2cdc-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-148">sim</span><span class="sxs-lookup"><span data-stu-id="b2cdc-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2cdc-149">Lync Attendant</span><span class="sxs-lookup"><span data-stu-id="b2cdc-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-150">sim</span><span class="sxs-lookup"><span data-stu-id="b2cdc-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2cdc-151">Lync para Windows 8</span><span class="sxs-lookup"><span data-stu-id="b2cdc-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-152">não</span><span class="sxs-lookup"><span data-stu-id="b2cdc-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b2cdc-153">Lync móvel 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-154">não</span><span class="sxs-lookup"><span data-stu-id="b2cdc-154">no</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-155">O VoIP deve ser desabilitado para os clientes do Lync Mobile 2013 se usado por usuários com roteamento baseado em local habilitado.</span><span class="sxs-lookup"><span data-stu-id="b2cdc-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b2cdc-156">Lync móvel 2010</span><span class="sxs-lookup"><span data-stu-id="b2cdc-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="b2cdc-157">sim</span><span class="sxs-lookup"><span data-stu-id="b2cdc-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="b2cdc-158">Para desabilitar o VoIP para clientes móveis do Lync 2013, atribua uma política de mobilidade com a configuração, áudio/vídeo IP, desabilitada para todos os usuários habilitados para roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="b2cdc-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="b2cdc-159">Para obter mais detalhes sobre política de mobilidade, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="b2cdc-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b2cdc-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="b2cdc-160">See Also</span></span>


[<span data-ttu-id="b2cdc-161">Planejamento de Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b2cdc-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

