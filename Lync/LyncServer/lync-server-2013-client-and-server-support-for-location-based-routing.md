---
title: 'Lync Server 2013: suporte de cliente e servidor para roteamento baseado em local'
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
ms.openlocfilehash: efdb03adbdf1392e27c3107eef4aaf97f3708e66
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42043833"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="b5418-102">Suporte a cliente e servidor para roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-102">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b5418-103">_**Última modificação do tópico:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="b5418-103">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="b5418-104">O roteamento baseado em local é imposto pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b5418-104">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="b5418-105">O Lync Server pode identificar os sites de rede onde os usuários estão se conectando dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="b5418-105">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="b5418-106">Como os usuários remotos estão fora da rede corporativa, sua localização é considerada desconhecida.</span><span class="sxs-lookup"><span data-stu-id="b5418-106">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="b5418-107">Suporte ao Lync Server</span><span class="sxs-lookup"><span data-stu-id="b5418-107">Lync Server Support</span></span>

<span data-ttu-id="b5418-108">O roteamento baseado em local exige que o Lync Server 2013 CU1 seja implantado em todos os pools de front-ends e servidores Standard Edition em uma determinada topologia.</span><span class="sxs-lookup"><span data-stu-id="b5418-108">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="b5418-109">Se o Lync Server 2013 CU1 não estiver instalado em determinados componentes do Lync na topologia, as restrições de roteamento baseadas em local não poderão ser totalmente impostas.</span><span class="sxs-lookup"><span data-stu-id="b5418-109">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="b5418-110">A tabela a seguir identifica a combinação de funções de servidor e versões com suporte para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="b5418-110">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5418-111">Versão do pool</span><span class="sxs-lookup"><span data-stu-id="b5418-111">Pool version</span></span></th>
<th><span data-ttu-id="b5418-112">Versão do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="b5418-112">Mediation Server version</span></span></th>
<th><span data-ttu-id="b5418-113">Com suporte</span><span class="sxs-lookup"><span data-stu-id="b5418-113">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5418-114">Lync Server 2013 atualização cumulativa de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-114">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b5418-115">Lync Server 2013 atualização cumulativa de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b5418-116">sim</span><span class="sxs-lookup"><span data-stu-id="b5418-116">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5418-117">Lync Server 2013 atualização cumulativa de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-117">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b5418-118">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-118">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="b5418-119">não</span><span class="sxs-lookup"><span data-stu-id="b5418-119">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5418-120">Lync Server 2013 atualização cumulativa de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-120">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b5418-121">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b5418-121">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="b5418-122">não</span><span class="sxs-lookup"><span data-stu-id="b5418-122">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5418-123">Lync Server 2013 atualização cumulativa de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-123">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="b5418-124">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b5418-124">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="b5418-125">não</span><span class="sxs-lookup"><span data-stu-id="b5418-125">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5418-126">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-126">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="b5418-127">qualquer</span><span class="sxs-lookup"><span data-stu-id="b5418-127">any</span></span></p></td>
<td><p><span data-ttu-id="b5418-128">não</span><span class="sxs-lookup"><span data-stu-id="b5418-128">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5418-129">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="b5418-129">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="b5418-130">qualquer</span><span class="sxs-lookup"><span data-stu-id="b5418-130">any</span></span></p></td>
<td><p><span data-ttu-id="b5418-131">não</span><span class="sxs-lookup"><span data-stu-id="b5418-131">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5418-132">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b5418-132">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="b5418-133">qualquer</span><span class="sxs-lookup"><span data-stu-id="b5418-133">any</span></span></p></td>
<td><p><span data-ttu-id="b5418-134">não</span><span class="sxs-lookup"><span data-stu-id="b5418-134">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="b5418-135">Suporte ao cliente do Lync</span><span class="sxs-lookup"><span data-stu-id="b5418-135">Lync Client Support</span></span>

<span data-ttu-id="b5418-136">A tabela a seguir identifica os clientes com suporte para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="b5418-136">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="b5418-137">Tipo de cliente</span><span class="sxs-lookup"><span data-stu-id="b5418-137">Client type</span></span></th>
<th><span data-ttu-id="b5418-138">Com suporte</span><span class="sxs-lookup"><span data-stu-id="b5418-138">Supported</span></span></th>
<th><span data-ttu-id="b5418-139">Detalhes</span><span class="sxs-lookup"><span data-stu-id="b5418-139">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="b5418-140">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-140">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="b5418-141">sim</span><span class="sxs-lookup"><span data-stu-id="b5418-141">yes</span></span></p></td>
<td><p><span data-ttu-id="b5418-142">Incluindo a atualização cumulativa do Lync 2013 fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-142">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5418-143">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="b5418-143">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="b5418-144">sim</span><span class="sxs-lookup"><span data-stu-id="b5418-144">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5418-145">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="b5418-145">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="b5418-146">não</span><span class="sxs-lookup"><span data-stu-id="b5418-146">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5418-147">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="b5418-147">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="b5418-148">sim</span><span class="sxs-lookup"><span data-stu-id="b5418-148">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5418-149">Atendedor do Lync</span><span class="sxs-lookup"><span data-stu-id="b5418-149">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="b5418-150">sim</span><span class="sxs-lookup"><span data-stu-id="b5418-150">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5418-151">Lync para Windows 8</span><span class="sxs-lookup"><span data-stu-id="b5418-151">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="b5418-152">não</span><span class="sxs-lookup"><span data-stu-id="b5418-152">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="b5418-153">Lync móvel 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-153">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="b5418-154">não</span><span class="sxs-lookup"><span data-stu-id="b5418-154">no</span></span></p></td>
<td><p><span data-ttu-id="b5418-155">O VoIP deve estar desabilitado para clientes do Lync Mobile 2013 se for usado por usuários com roteamento baseado em local habilitado.</span><span class="sxs-lookup"><span data-stu-id="b5418-155">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="b5418-156">Lync móvel 2010</span><span class="sxs-lookup"><span data-stu-id="b5418-156">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="b5418-157">sim</span><span class="sxs-lookup"><span data-stu-id="b5418-157">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="b5418-158">Para desabilitar o VoIP para clientes do Lync Mobile 2013, atribua uma política de mobilidade com a configuração, áudio/vídeo IP, desabilitada para todos os usuários habilitados para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="b5418-158">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="b5418-159">Para obter mais detalhes sobre a política de mobilidade, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="b5418-159">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="b5418-160">Confira também</span><span class="sxs-lookup"><span data-stu-id="b5418-160">See Also</span></span>


[<span data-ttu-id="b5418-161">Planejamento de roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="b5418-161">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

