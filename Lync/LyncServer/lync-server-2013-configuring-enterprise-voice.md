---
title: 'Lync Server 2013: Configurando o Enterprise Voice'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Enterprise Voice
ms:assetid: 7df179fa-d3a2-4b23-a433-b750aedf980b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994041(v=OCS.15)
ms:contentKeyID: 51803952
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d6bf9f79725f1f4812ac1e1c1c3c0e3217b939b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41728931"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="08ea6-102">Configurando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08ea6-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="08ea6-103">_**Tópico da última modificação:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="08ea6-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="08ea6-104">Para implantar o Enterprise Voice, você precisará configurar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="08ea6-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="08ea6-105">Criar um tronco</span><span class="sxs-lookup"><span data-stu-id="08ea6-105">Create a Trunk</span></span>

  - <span data-ttu-id="08ea6-106">Definir uma política de voz</span><span class="sxs-lookup"><span data-stu-id="08ea6-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="08ea6-107">Definir uma rota de voz</span><span class="sxs-lookup"><span data-stu-id="08ea6-107">Define a Voice Route</span></span>

  - <span data-ttu-id="08ea6-108">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="08ea6-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="08ea6-109">Criar um tronco</span><span class="sxs-lookup"><span data-stu-id="08ea6-109">Create a Trunk</span></span>

<span data-ttu-id="08ea6-110">Você deve definir troncos na sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="08ea6-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="08ea6-111">Para roteamento baseado em local, você deve criar uma configuração de tronco por tronco.</span><span class="sxs-lookup"><span data-stu-id="08ea6-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="08ea6-112">Use o construtor de topologia do Lync Server para definir seus troncos e use o comando do Windows PowerShell do Lync Server, o New-CsTrunkConfiguration ou o painel de controle do Lync Server para definir as configurações de tronco correspondentes.</span><span class="sxs-lookup"><span data-stu-id="08ea6-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="08ea6-113">Mais informações sobre como habilitar o roteamento baseado em localização nas configurações de tronco podem ser encontradas na seção habilitar o roteamento baseado em local para troncos, no tópico [habilitando o roteamento baseado em local no Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="08ea6-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="08ea6-114">Para este exemplo, a tabela a seguir ilustra os troncos usados nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="08ea6-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="08ea6-115">Para obter mais informações, consulte [definir troncos adicionais no construtor de topologias no Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="08ea6-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="08ea6-116">Nome do tronco</span><span class="sxs-lookup"><span data-stu-id="08ea6-116">Trunk name</span></span></th>
<th><span data-ttu-id="08ea6-117">Tipo de sistema</span><span class="sxs-lookup"><span data-stu-id="08ea6-117">System type</span></span></th>
<th><span data-ttu-id="08ea6-118">Nome</span><span class="sxs-lookup"><span data-stu-id="08ea6-118">Name</span></span></th>
<th><span data-ttu-id="08ea6-119">Local</span><span class="sxs-lookup"><span data-stu-id="08ea6-119">Location</span></span></th>
<th><span data-ttu-id="08ea6-120">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="08ea6-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08ea6-121">Tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="08ea6-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="08ea6-122">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="08ea6-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="08ea6-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="08ea6-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="08ea6-124">Delhi</span><span class="sxs-lookup"><span data-stu-id="08ea6-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="08ea6-125">MS1</span><span class="sxs-lookup"><span data-stu-id="08ea6-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ea6-126">Tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="08ea6-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="08ea6-127">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="08ea6-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="08ea6-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="08ea6-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="08ea6-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="08ea6-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="08ea6-130">MS1</span><span class="sxs-lookup"><span data-stu-id="08ea6-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ea6-131">Tronco 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="08ea6-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="08ea6-132">RESPECTIVA</span><span class="sxs-lookup"><span data-stu-id="08ea6-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="08ea6-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="08ea6-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="08ea6-134">Delhi</span><span class="sxs-lookup"><span data-stu-id="08ea6-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="08ea6-135">MS1</span><span class="sxs-lookup"><span data-stu-id="08ea6-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ea6-136">Tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="08ea6-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="08ea6-137">RESPECTIVA</span><span class="sxs-lookup"><span data-stu-id="08ea6-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="08ea6-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="08ea6-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="08ea6-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="08ea6-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="08ea6-140">MS1</span><span class="sxs-lookup"><span data-stu-id="08ea6-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="08ea6-141">Define as políticas de voz</span><span class="sxs-lookup"><span data-stu-id="08ea6-141">Defines Voice Policies</span></span>

<span data-ttu-id="08ea6-142">Você deve definir políticas de voz para a implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="08ea6-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="08ea6-143">Defina uma política de voz para impor restrições de roteamento baseado em localização a um subconjunto de usuários se apenas um subconjunto deles for necessário para usar o roteamento baseado em localização.</span><span class="sxs-lookup"><span data-stu-id="08ea6-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="08ea6-144">Para este exemplo, a tabela a seguir ilustra as políticas de voz usadas neste cenário.</span><span class="sxs-lookup"><span data-stu-id="08ea6-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="08ea6-145">Somente as configurações específicas do roteamento baseado em localização são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="08ea6-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="08ea6-146">Para obter mais informações, consulte [Configurando políticas de voz e registros de uso PSTN para autorizar os recursos e privilégios de chamada no Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="08ea6-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="08ea6-147">Política de voz 1</span><span class="sxs-lookup"><span data-stu-id="08ea6-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="08ea6-148">Política de voz 2</span><span class="sxs-lookup"><span data-stu-id="08ea6-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08ea6-149">ID da política de voz</span><span class="sxs-lookup"><span data-stu-id="08ea6-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="08ea6-150">Política de voz de Délhi</span><span class="sxs-lookup"><span data-stu-id="08ea6-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="08ea6-151">Política de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="08ea6-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ea6-152">Usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="08ea6-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="08ea6-153">Uso de Delhi, uso do PBX, uso do PBX Hyd</span><span class="sxs-lookup"><span data-stu-id="08ea6-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="08ea6-154">Uso do Hyderabad, Hyd do PBX, uso do PBX</span><span class="sxs-lookup"><span data-stu-id="08ea6-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ea6-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="08ea6-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="08ea6-156">Falso</span><span class="sxs-lookup"><span data-stu-id="08ea6-156">False</span></span></p></td>
<td><p><span data-ttu-id="08ea6-157">Falso</span><span class="sxs-lookup"><span data-stu-id="08ea6-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="08ea6-158">Definir roteiros de voz</span><span class="sxs-lookup"><span data-stu-id="08ea6-158">Define Voice Routes</span></span>

<span data-ttu-id="08ea6-159">Você deve definir rotas de voz para a implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="08ea6-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="08ea6-160">Para este exemplo, a tabela a seguir ilustra as rotas de voz usadas nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="08ea6-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="08ea6-161">Somente as configurações específicas do roteamento baseado em localização são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="08ea6-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="08ea6-162">Para obter mais informações, consulte [Configurando rotas de voz para chamadas de saída no Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="08ea6-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


<table>
<colgroup>
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
<col style="width: 20%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="08ea6-163">Rota de voz 1</span><span class="sxs-lookup"><span data-stu-id="08ea6-163">Voice route 1</span></span></th>
<th><span data-ttu-id="08ea6-164">Rota de voz 2</span><span class="sxs-lookup"><span data-stu-id="08ea6-164">Voice route 2</span></span></th>
<th><span data-ttu-id="08ea6-165">Rota de voz 3</span><span class="sxs-lookup"><span data-stu-id="08ea6-165">Voice route 3</span></span></th>
<th><span data-ttu-id="08ea6-166">Rota de voz 4</span><span class="sxs-lookup"><span data-stu-id="08ea6-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08ea6-167">Nome</span><span class="sxs-lookup"><span data-stu-id="08ea6-167">Name</span></span></p></td>
<td><p><span data-ttu-id="08ea6-168">Rota de Délhi</span><span class="sxs-lookup"><span data-stu-id="08ea6-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="08ea6-169">Rota Hyderabad</span><span class="sxs-lookup"><span data-stu-id="08ea6-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="08ea6-170">Rota de del do PBX</span><span class="sxs-lookup"><span data-stu-id="08ea6-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="08ea6-171">Rota Hyd do PBX</span><span class="sxs-lookup"><span data-stu-id="08ea6-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ea6-172">Usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="08ea6-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="08ea6-173">Uso de Delhi</span><span class="sxs-lookup"><span data-stu-id="08ea6-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="08ea6-174">Uso do Hyderabad</span><span class="sxs-lookup"><span data-stu-id="08ea6-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="08ea6-175">Uso do PBX del</span><span class="sxs-lookup"><span data-stu-id="08ea6-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="08ea6-176">Uso do Hyd do PBX</span><span class="sxs-lookup"><span data-stu-id="08ea6-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="08ea6-177">Tronco</span><span class="sxs-lookup"><span data-stu-id="08ea6-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="08ea6-178">Tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="08ea6-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="08ea6-179">Tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="08ea6-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="08ea6-180">Tronco 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="08ea6-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="08ea6-181">Tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="08ea6-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="08ea6-182">Enable Users for Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="08ea6-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="08ea6-183">Habilite os usuários para o Enterprise Voice e atribua a eles uma política de voz que você definiu anteriormente.</span><span class="sxs-lookup"><span data-stu-id="08ea6-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="08ea6-184">Para este exemplo, a tabela a seguir ilustra a atribuição usada neste cenário.</span><span class="sxs-lookup"><span data-stu-id="08ea6-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="08ea6-185">Somente as configurações específicas do roteamento baseado em localização são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="08ea6-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="08ea6-186">Para obter mais informações, consulte [habilitar usuários para Enterprise Voice no Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="08ea6-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="08ea6-187">Usuários localizados em Delhi</span><span class="sxs-lookup"><span data-stu-id="08ea6-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="08ea6-188">Usuários localizados no Hyderabad</span><span class="sxs-lookup"><span data-stu-id="08ea6-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="08ea6-189">Política de voz associada</span><span class="sxs-lookup"><span data-stu-id="08ea6-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="08ea6-190">Política de voz de Délhi</span><span class="sxs-lookup"><span data-stu-id="08ea6-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="08ea6-191">Política de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="08ea6-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="08ea6-192">Usuários de exemplo</span><span class="sxs-lookup"><span data-stu-id="08ea6-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="08ea6-193">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="08ea6-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="08ea6-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="08ea6-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="08ea6-195">Confira também</span><span class="sxs-lookup"><span data-stu-id="08ea6-195">See Also</span></span>


[<span data-ttu-id="08ea6-196">Configurando o Roteamento Baseado em Local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="08ea6-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

