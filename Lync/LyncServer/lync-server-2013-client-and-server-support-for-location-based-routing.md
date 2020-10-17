---
title: 'Lync Server 2013: suporte de cliente e servidor para roteamento de Location-Based'
description: 'Lync Server 2013: suporte a cliente e servidor para roteamento Location-Based.'
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
ms.openlocfilehash: 20dca7444f58ee62dbc36edbb7d9e1c976a97807
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48549627"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a><span data-ttu-id="4cc92-103">Suporte a cliente e servidor para roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-103">Client and server support for Location-Based Routing in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4cc92-104">_**Última modificação do tópico:** 2013-06-18_</span><span class="sxs-lookup"><span data-stu-id="4cc92-104">_**Topic Last Modified:** 2013-06-18_</span></span>

<span data-ttu-id="4cc92-105">Location-Based roteamento é imposto pelo Lync Server.</span><span class="sxs-lookup"><span data-stu-id="4cc92-105">Location-Based Routing is enforced by Lync Server.</span></span> <span data-ttu-id="4cc92-106">O Lync Server pode identificar os sites de rede onde os usuários estão se conectando dentro da rede corporativa.</span><span class="sxs-lookup"><span data-stu-id="4cc92-106">Lync Server can identify the network sites where users are connecting from within the corporate network.</span></span> <span data-ttu-id="4cc92-107">Como os usuários remotos estão fora da rede corporativa, sua localização é considerada desconhecida.</span><span class="sxs-lookup"><span data-stu-id="4cc92-107">Since remote users are outside the corporate network, their location is considered to be unknown.</span></span>

<div>

## <a name="lync-server-support"></a><span data-ttu-id="4cc92-108">Suporte ao Lync Server</span><span class="sxs-lookup"><span data-stu-id="4cc92-108">Lync Server Support</span></span>

<span data-ttu-id="4cc92-109">Location-Based roteamento exige que o Lync Server 2013 CU1 seja implantado em todos os pools de front-ends e servidores Standard Edition em uma determinada topologia.</span><span class="sxs-lookup"><span data-stu-id="4cc92-109">Location-Based Routing requires that Lync Server 2013 CU1 is deployed on all Front End pools and Standard Edition servers in a given topology.</span></span> <span data-ttu-id="4cc92-110">Se o Lync Server 2013 CU1 não estiver instalado em determinados componentes do Lync na topologia, Location-Based restrições de roteamento não poderão ser totalmente impostas.</span><span class="sxs-lookup"><span data-stu-id="4cc92-110">If Lync Server 2013 CU1 is not installed on certain Lync components in the topology, Location-Based Routing restrictions cannot be fully enforced.</span></span>

<span data-ttu-id="4cc92-111">A tabela a seguir identifica a combinação de funções de servidor e versões compatíveis com o roteamento de Location-Based.</span><span class="sxs-lookup"><span data-stu-id="4cc92-111">The following table identifies the combination of server roles and versions that is supported for Location-Based Routing.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cc92-112">Versão do pool</span><span class="sxs-lookup"><span data-stu-id="4cc92-112">Pool version</span></span></th>
<th><span data-ttu-id="4cc92-113">Versão do servidor de mediação</span><span class="sxs-lookup"><span data-stu-id="4cc92-113">Mediation Server version</span></span></th>
<th><span data-ttu-id="4cc92-114">Com suporte</span><span class="sxs-lookup"><span data-stu-id="4cc92-114">Supported</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cc92-115">Lync Server 2013 atualização cumulativa de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-115">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4cc92-116">Lync Server 2013 atualização cumulativa de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-116">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4cc92-117">sim</span><span class="sxs-lookup"><span data-stu-id="4cc92-117">yes</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cc92-118">Lync Server 2013 atualização cumulativa de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-118">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4cc92-119">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-119">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="4cc92-120">não</span><span class="sxs-lookup"><span data-stu-id="4cc92-120">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cc92-121">Lync Server 2013 atualização cumulativa de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-121">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4cc92-122">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4cc92-122">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="4cc92-123">não</span><span class="sxs-lookup"><span data-stu-id="4cc92-123">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cc92-124">Lync Server 2013 atualização cumulativa de fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-124">Lync Server 2013 February 2013 Cumulative Update</span></span></p></td>
<td><p><span data-ttu-id="4cc92-125">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4cc92-125">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="4cc92-126">não</span><span class="sxs-lookup"><span data-stu-id="4cc92-126">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cc92-127">Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-127">Lync Server 2013</span></span></p></td>
<td><p><span data-ttu-id="4cc92-128">qualquer</span><span class="sxs-lookup"><span data-stu-id="4cc92-128">any</span></span></p></td>
<td><p><span data-ttu-id="4cc92-129">não</span><span class="sxs-lookup"><span data-stu-id="4cc92-129">no</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cc92-130">Lync Server 2010</span><span class="sxs-lookup"><span data-stu-id="4cc92-130">Lync Server 2010</span></span></p></td>
<td><p><span data-ttu-id="4cc92-131">qualquer</span><span class="sxs-lookup"><span data-stu-id="4cc92-131">any</span></span></p></td>
<td><p><span data-ttu-id="4cc92-132">não</span><span class="sxs-lookup"><span data-stu-id="4cc92-132">no</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cc92-133">Office Communications Server 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4cc92-133">Office Communications Server 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="4cc92-134">qualquer</span><span class="sxs-lookup"><span data-stu-id="4cc92-134">any</span></span></p></td>
<td><p><span data-ttu-id="4cc92-135">não</span><span class="sxs-lookup"><span data-stu-id="4cc92-135">no</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a><span data-ttu-id="4cc92-136">Suporte ao cliente do Lync</span><span class="sxs-lookup"><span data-stu-id="4cc92-136">Lync Client Support</span></span>

<span data-ttu-id="4cc92-137">A tabela a seguir identifica os clientes aos quais Location-Based roteamento oferece suporte.</span><span class="sxs-lookup"><span data-stu-id="4cc92-137">The following table identifies the clients that Location-Based Routing supports.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="4cc92-138">Tipo de cliente</span><span class="sxs-lookup"><span data-stu-id="4cc92-138">Client type</span></span></th>
<th><span data-ttu-id="4cc92-139">Com suporte</span><span class="sxs-lookup"><span data-stu-id="4cc92-139">Supported</span></span></th>
<th><span data-ttu-id="4cc92-140">Detalhes</span><span class="sxs-lookup"><span data-stu-id="4cc92-140">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4cc92-141">Lync 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-141">Lync 2013</span></span></p></td>
<td><p><span data-ttu-id="4cc92-142">sim</span><span class="sxs-lookup"><span data-stu-id="4cc92-142">yes</span></span></p></td>
<td><p><span data-ttu-id="4cc92-143">Incluindo a atualização cumulativa do Lync 2013 fevereiro de 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-143">Including Lync 2013 February 2013 Cumulative Update</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cc92-144">Lync 2010</span><span class="sxs-lookup"><span data-stu-id="4cc92-144">Lync 2010</span></span></p></td>
<td><p><span data-ttu-id="4cc92-145">sim</span><span class="sxs-lookup"><span data-stu-id="4cc92-145">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cc92-146">Office Communicator 2007 R2</span><span class="sxs-lookup"><span data-stu-id="4cc92-146">Office Communicator 2007 R2</span></span></p></td>
<td><p><span data-ttu-id="4cc92-147">não</span><span class="sxs-lookup"><span data-stu-id="4cc92-147">no</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cc92-148">Lync Phone Edition</span><span class="sxs-lookup"><span data-stu-id="4cc92-148">Lync Phone Edition</span></span></p></td>
<td><p><span data-ttu-id="4cc92-149">sim</span><span class="sxs-lookup"><span data-stu-id="4cc92-149">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cc92-150">Atendedor do Lync</span><span class="sxs-lookup"><span data-stu-id="4cc92-150">Lync Attendant</span></span></p></td>
<td><p><span data-ttu-id="4cc92-151">sim</span><span class="sxs-lookup"><span data-stu-id="4cc92-151">yes</span></span></p></td>
<td> </td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cc92-152">Lync para Windows 8</span><span class="sxs-lookup"><span data-stu-id="4cc92-152">Lync for Windows 8</span></span></p></td>
<td><p><span data-ttu-id="4cc92-153">não</span><span class="sxs-lookup"><span data-stu-id="4cc92-153">no</span></span></p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4cc92-154">Lync móvel 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-154">Lync Mobile 2013</span></span></p></td>
<td><p><span data-ttu-id="4cc92-155">não</span><span class="sxs-lookup"><span data-stu-id="4cc92-155">no</span></span></p></td>
<td><p><span data-ttu-id="4cc92-156">O VoIP deve estar desabilitado para clientes do Lync Mobile 2013 se for usado por usuários com roteamento de Location-Based habilitado.</span><span class="sxs-lookup"><span data-stu-id="4cc92-156">VoIP must be disabled for Lync Mobile 2013 clients if used by users with Location-Based Routing enabled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4cc92-157">Lync móvel 2010</span><span class="sxs-lookup"><span data-stu-id="4cc92-157">Lync Mobile 2010</span></span></p></td>
<td><p><span data-ttu-id="4cc92-158">sim</span><span class="sxs-lookup"><span data-stu-id="4cc92-158">yes</span></span></p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> <span data-ttu-id="4cc92-159">Para desabilitar o VoIP para clientes do Lync Mobile 2013, atribua uma política de mobilidade com a configuração, áudio/vídeo IP, desabilitada para todos os usuários habilitados para roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="4cc92-159">To disable VoIP for Lync Mobile 2013 clients, assign a mobility policy with the setting, IP Audio/Video, disabled for all users enabled for Location Based Routing.</span></span> <span data-ttu-id="4cc92-160">Para obter mais detalhes sobre a política de mobilidade, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span><span class="sxs-lookup"><span data-stu-id="4cc92-160">For more details about mobility policy, see <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.</span></span>



</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4cc92-161">Confira também</span><span class="sxs-lookup"><span data-stu-id="4cc92-161">See Also</span></span>


[<span data-ttu-id="4cc92-162">Planejamento de roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4cc92-162">Planning for Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

