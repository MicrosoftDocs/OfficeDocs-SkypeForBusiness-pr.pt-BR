---
title: 'Lync Server 2013: Configurando o Enterprise Voice'
description: 'Lync Server 2013: Configurando o Enterprise Voice.'
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
ms.openlocfilehash: 49a231b92bf7b04aa3466927a79258f0cbad4e3f
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548427"
---
# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="4c88c-103">Configurando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c88c-103">Configuring Enterprise Voice in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="4c88c-104">_**Última modificação do tópico:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="4c88c-104">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="4c88c-105">Para implantar o Enterprise Voice, você precisará configurar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4c88c-105">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="4c88c-106">Criar um tronco</span><span class="sxs-lookup"><span data-stu-id="4c88c-106">Create a Trunk</span></span>

  - <span data-ttu-id="4c88c-107">Definir uma política de voz</span><span class="sxs-lookup"><span data-stu-id="4c88c-107">Define a Voice Policy</span></span>

  - <span data-ttu-id="4c88c-108">Definir uma rota de voz</span><span class="sxs-lookup"><span data-stu-id="4c88c-108">Define a Voice Route</span></span>

  - <span data-ttu-id="4c88c-109">Habilitar usuários para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="4c88c-109">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="4c88c-110">Criar um tronco</span><span class="sxs-lookup"><span data-stu-id="4c88c-110">Create a Trunk</span></span>

<span data-ttu-id="4c88c-111">Você deve definir troncos em sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4c88c-111">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="4c88c-112">Para Location-Based roteamento, você deve criar uma configuração de tronco por tronco.</span><span class="sxs-lookup"><span data-stu-id="4c88c-112">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="4c88c-113">Use o construtor de topologias do Lync Server para definir seus troncos e use o comando do Lync Server Windows PowerShell, New-CsTrunkConfiguration ou o painel de controle do Lync Server para definir as configurações de tronco correspondentes.</span><span class="sxs-lookup"><span data-stu-id="4c88c-113">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="4c88c-114">É possível encontrar mais informações sobre como habilitar o roteamento de Location-Based nas configurações de tronco na seção, habilitar Location-Based roteamento para troncos, no tópico, [habilitando Location-Based roteamento no Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="4c88c-114">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="4c88c-115">Neste exemplo, a tabela a seguir ilustra os troncos usados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="4c88c-115">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="4c88c-116">Para obter mais informações, consulte [definir troncos adicionais no construtor de topologias no Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="4c88c-116">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="4c88c-117">Nome do tronco</span><span class="sxs-lookup"><span data-stu-id="4c88c-117">Trunk name</span></span></th>
<th><span data-ttu-id="4c88c-118">Tipo de sistema</span><span class="sxs-lookup"><span data-stu-id="4c88c-118">System type</span></span></th>
<th><span data-ttu-id="4c88c-119">Nome</span><span class="sxs-lookup"><span data-stu-id="4c88c-119">Name</span></span></th>
<th><span data-ttu-id="4c88c-120">Local</span><span class="sxs-lookup"><span data-stu-id="4c88c-120">Location</span></span></th>
<th><span data-ttu-id="4c88c-121">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="4c88c-121">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c88c-122">Tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="4c88c-122">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="4c88c-123">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="4c88c-123">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="4c88c-124">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="4c88c-124">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="4c88c-125">Déli</span><span class="sxs-lookup"><span data-stu-id="4c88c-125">Delhi</span></span></p></td>
<td><p><span data-ttu-id="4c88c-126">MS1</span><span class="sxs-lookup"><span data-stu-id="4c88c-126">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c88c-127">Tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="4c88c-127">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="4c88c-128">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="4c88c-128">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="4c88c-129">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="4c88c-129">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="4c88c-130">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="4c88c-130">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="4c88c-131">MS1</span><span class="sxs-lookup"><span data-stu-id="4c88c-131">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c88c-132">Tronco 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="4c88c-132">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="4c88c-133">RESPECTIVA</span><span class="sxs-lookup"><span data-stu-id="4c88c-133">PBX</span></span></p></td>
<td><p><span data-ttu-id="4c88c-134">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="4c88c-134">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="4c88c-135">Déli</span><span class="sxs-lookup"><span data-stu-id="4c88c-135">Delhi</span></span></p></td>
<td><p><span data-ttu-id="4c88c-136">MS1</span><span class="sxs-lookup"><span data-stu-id="4c88c-136">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c88c-137">Tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="4c88c-137">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="4c88c-138">RESPECTIVA</span><span class="sxs-lookup"><span data-stu-id="4c88c-138">PBX</span></span></p></td>
<td><p><span data-ttu-id="4c88c-139">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="4c88c-139">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="4c88c-140">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="4c88c-140">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="4c88c-141">MS1</span><span class="sxs-lookup"><span data-stu-id="4c88c-141">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="4c88c-142">Define políticas de voz</span><span class="sxs-lookup"><span data-stu-id="4c88c-142">Defines Voice Policies</span></span>

<span data-ttu-id="4c88c-143">Você deve definir políticas de voz para a implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4c88c-143">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="4c88c-144">Defina uma política de voz para impor restrições de roteamento Location-Based a um subconjunto de usuários se apenas um subconjunto deles for necessário para usar o roteamento Location-Based.</span><span class="sxs-lookup"><span data-stu-id="4c88c-144">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="4c88c-145">Neste exemplo, a tabela a seguir ilustra as políticas de voz usadas neste cenário.</span><span class="sxs-lookup"><span data-stu-id="4c88c-145">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="4c88c-146">Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="4c88c-146">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="4c88c-147">Para saber mais, confira [Configurando políticas de voz e registros de uso de PSTN para autorizar recursos e privilégios de chamada no Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="4c88c-147">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="4c88c-148">Política de voz 1</span><span class="sxs-lookup"><span data-stu-id="4c88c-148">Voice policy 1</span></span></th>
<th><span data-ttu-id="4c88c-149">Política de voz 2</span><span class="sxs-lookup"><span data-stu-id="4c88c-149">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c88c-150">ID da política de voz</span><span class="sxs-lookup"><span data-stu-id="4c88c-150">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="4c88c-151">Política de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="4c88c-151">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="4c88c-152">Política de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="4c88c-152">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c88c-153">Usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="4c88c-153">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="4c88c-154">Uso de Delhi, uso de PBX, uso do PBX Hyd</span><span class="sxs-lookup"><span data-stu-id="4c88c-154">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="4c88c-155">Uso do Hyderabad, uso do PBX Hyd, uso do PBX</span><span class="sxs-lookup"><span data-stu-id="4c88c-155">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c88c-156">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="4c88c-156">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="4c88c-157">Falso</span><span class="sxs-lookup"><span data-stu-id="4c88c-157">False</span></span></p></td>
<td><p><span data-ttu-id="4c88c-158">Falso</span><span class="sxs-lookup"><span data-stu-id="4c88c-158">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="4c88c-159">Definir rotas de voz</span><span class="sxs-lookup"><span data-stu-id="4c88c-159">Define Voice Routes</span></span>

<span data-ttu-id="4c88c-160">Você deve definir rotas de voz para sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="4c88c-160">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="4c88c-161">Neste exemplo, a tabela a seguir ilustra as rotas de voz usadas neste cenário.</span><span class="sxs-lookup"><span data-stu-id="4c88c-161">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="4c88c-162">Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="4c88c-162">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="4c88c-163">Para obter mais informações, consulte [Configurando rotas de voz para chamadas de saída no Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="4c88c-163">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="4c88c-164">Rota de voz 1</span><span class="sxs-lookup"><span data-stu-id="4c88c-164">Voice route 1</span></span></th>
<th><span data-ttu-id="4c88c-165">Rota de voz 2</span><span class="sxs-lookup"><span data-stu-id="4c88c-165">Voice route 2</span></span></th>
<th><span data-ttu-id="4c88c-166">Rota de voz 3</span><span class="sxs-lookup"><span data-stu-id="4c88c-166">Voice route 3</span></span></th>
<th><span data-ttu-id="4c88c-167">Rota de voz 4</span><span class="sxs-lookup"><span data-stu-id="4c88c-167">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c88c-168">Nome</span><span class="sxs-lookup"><span data-stu-id="4c88c-168">Name</span></span></p></td>
<td><p><span data-ttu-id="4c88c-169">Rota de Déli</span><span class="sxs-lookup"><span data-stu-id="4c88c-169">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="4c88c-170">Rota Hyderabad</span><span class="sxs-lookup"><span data-stu-id="4c88c-170">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="4c88c-171">Rota de del do PBX</span><span class="sxs-lookup"><span data-stu-id="4c88c-171">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="4c88c-172">Rota de Hyd PBX</span><span class="sxs-lookup"><span data-stu-id="4c88c-172">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c88c-173">Usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="4c88c-173">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="4c88c-174">Uso de Delhi</span><span class="sxs-lookup"><span data-stu-id="4c88c-174">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="4c88c-175">Uso do Hyderabad</span><span class="sxs-lookup"><span data-stu-id="4c88c-175">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="4c88c-176">Uso do PBX del</span><span class="sxs-lookup"><span data-stu-id="4c88c-176">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="4c88c-177">Uso do Hyd PBX</span><span class="sxs-lookup"><span data-stu-id="4c88c-177">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="4c88c-178">Trunk</span><span class="sxs-lookup"><span data-stu-id="4c88c-178">Trunk</span></span></p></td>
<td><p><span data-ttu-id="4c88c-179">Tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="4c88c-179">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="4c88c-180">Tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="4c88c-180">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="4c88c-181">Tronco 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="4c88c-181">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="4c88c-182">Tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="4c88c-182">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="4c88c-183">Habilitar usuários para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="4c88c-183">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="4c88c-184">Habilite usuários para o Enterprise Voice e atribua a eles uma política de voz que você tenha definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4c88c-184">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="4c88c-185">Neste exemplo, a tabela a seguir ilustra a atribuição usada neste cenário.</span><span class="sxs-lookup"><span data-stu-id="4c88c-185">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="4c88c-186">Somente as configurações específicas para o roteamento de Location-Based são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="4c88c-186">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="4c88c-187">Para obter mais informações, consulte [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="4c88c-187">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="4c88c-188">Usuários localizados em Delhi</span><span class="sxs-lookup"><span data-stu-id="4c88c-188">Users located in Delhi</span></span></th>
<th><span data-ttu-id="4c88c-189">Usuários localizados no Hyderabad</span><span class="sxs-lookup"><span data-stu-id="4c88c-189">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="4c88c-190">Política de voz associada</span><span class="sxs-lookup"><span data-stu-id="4c88c-190">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="4c88c-191">Política de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="4c88c-191">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="4c88c-192">Política de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="4c88c-192">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="4c88c-193">Usuários de exemplo</span><span class="sxs-lookup"><span data-stu-id="4c88c-193">Sample users</span></span></p></td>
<td><p><span data-ttu-id="4c88c-194">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="4c88c-194">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="4c88c-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="4c88c-195">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="4c88c-196">Confira também</span><span class="sxs-lookup"><span data-stu-id="4c88c-196">See Also</span></span>


[<span data-ttu-id="4c88c-197">Configurando o roteamento de Location-Based no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="4c88c-197">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

