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
ms.openlocfilehash: 8a6c09bd44f9fc4b98488c7825f8cab1d3eea7f6
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42202937"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configuring-enterprise-voice-in-lync-server-2013"></a><span data-ttu-id="84b8c-102">Configurando o Enterprise Voice no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b8c-102">Configuring Enterprise Voice in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="84b8c-103">_**Última modificação do tópico:** 2013-03-12_</span><span class="sxs-lookup"><span data-stu-id="84b8c-103">_**Topic Last Modified:** 2013-03-12_</span></span>

<span data-ttu-id="84b8c-104">Para implantar o Enterprise Voice, você precisará configurar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="84b8c-104">To deploy Enterprise Voice, you’ll need to configure the following:</span></span>

  - <span data-ttu-id="84b8c-105">Criar um tronco</span><span class="sxs-lookup"><span data-stu-id="84b8c-105">Create a Trunk</span></span>

  - <span data-ttu-id="84b8c-106">Definir uma política de voz</span><span class="sxs-lookup"><span data-stu-id="84b8c-106">Define a Voice Policy</span></span>

  - <span data-ttu-id="84b8c-107">Definir uma rota de voz</span><span class="sxs-lookup"><span data-stu-id="84b8c-107">Define a Voice Route</span></span>

  - <span data-ttu-id="84b8c-108">Habilitar usuários para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="84b8c-108">Enable Users for Enterprise Voice</span></span>

<div>

## <a name="create-a-trunk"></a><span data-ttu-id="84b8c-109">Criar um tronco</span><span class="sxs-lookup"><span data-stu-id="84b8c-109">Create a Trunk</span></span>

<span data-ttu-id="84b8c-110">Você deve definir troncos em sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="84b8c-110">You must define trunks in your Enterprise Voice deployment.</span></span> <span data-ttu-id="84b8c-111">Para o roteamento baseado em local, você deve criar uma configuração de tronco por tronco.</span><span class="sxs-lookup"><span data-stu-id="84b8c-111">For Location-Based Routing, you must create a trunk configuration per trunk.</span></span> <span data-ttu-id="84b8c-112">Use o construtor de topologias do Lync Server para definir seus troncos e use o comando do Lync Server Windows PowerShell, New-CsTrunkConfiguration ou o painel de controle do Lync Server para definir as configurações de tronco correspondentes.</span><span class="sxs-lookup"><span data-stu-id="84b8c-112">Use the Lync Server Topology Builder to define your trunks, and use the Lync Server Windows PowerShell command, New-CsTrunkConfiguration, or the Lync Server Control Panel to define the corresponding trunk configurations.</span></span> <span data-ttu-id="84b8c-113">É possível encontrar mais informações sobre como habilitar o roteamento baseado em local nas configurações de tronco na seção, habilitar o roteamento baseado em local para troncos, no tópico, [habilitando o roteamento baseado em local no Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span><span class="sxs-lookup"><span data-stu-id="84b8c-113">More information on how to enable Location-Based Routing on trunk configurations can be found in the section, Enable Location-Based Routing to Trunks, in the topic, [Enabling Location-Based Routing in Lync Server 2013](lync-server-2013-enabling-location-based-routing.md).</span></span> <span data-ttu-id="84b8c-114">Neste exemplo, a tabela a seguir ilustra os troncos usados neste cenário.</span><span class="sxs-lookup"><span data-stu-id="84b8c-114">For this example, the following table illustrates the trunks used in this scenario.</span></span>

<span data-ttu-id="84b8c-115">Para obter mais informações, consulte [definir troncos adicionais no construtor de topologias no Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span><span class="sxs-lookup"><span data-stu-id="84b8c-115">For more information, see [Define additional trunks in Topology Builder in Lync Server 2013](lync-server-2013-define-additional-trunks-in-topology-builder.md).</span></span>


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
<th><span data-ttu-id="84b8c-116">Nome do tronco</span><span class="sxs-lookup"><span data-stu-id="84b8c-116">Trunk name</span></span></th>
<th><span data-ttu-id="84b8c-117">Tipo de sistema</span><span class="sxs-lookup"><span data-stu-id="84b8c-117">System type</span></span></th>
<th><span data-ttu-id="84b8c-118">Nome</span><span class="sxs-lookup"><span data-stu-id="84b8c-118">Name</span></span></th>
<th><span data-ttu-id="84b8c-119">Local</span><span class="sxs-lookup"><span data-stu-id="84b8c-119">Location</span></span></th>
<th><span data-ttu-id="84b8c-120">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="84b8c-120">Mediation Server</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84b8c-121">Tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="84b8c-121">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="84b8c-122">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="84b8c-122">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="84b8c-123">DEL-GW</span><span class="sxs-lookup"><span data-stu-id="84b8c-123">DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="84b8c-124">Déli</span><span class="sxs-lookup"><span data-stu-id="84b8c-124">Delhi</span></span></p></td>
<td><p><span data-ttu-id="84b8c-125">MS1</span><span class="sxs-lookup"><span data-stu-id="84b8c-125">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84b8c-126">Tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="84b8c-126">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="84b8c-127">Gateway PSTN</span><span class="sxs-lookup"><span data-stu-id="84b8c-127">PSTN gateway</span></span></p></td>
<td><p><span data-ttu-id="84b8c-128">HYD-GW</span><span class="sxs-lookup"><span data-stu-id="84b8c-128">HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="84b8c-129">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b8c-129">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="84b8c-130">MS1</span><span class="sxs-lookup"><span data-stu-id="84b8c-130">MS1</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84b8c-131">Tronco 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="84b8c-131">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="84b8c-132">RESPECTIVA</span><span class="sxs-lookup"><span data-stu-id="84b8c-132">PBX</span></span></p></td>
<td><p><span data-ttu-id="84b8c-133">DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="84b8c-133">DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="84b8c-134">Déli</span><span class="sxs-lookup"><span data-stu-id="84b8c-134">Delhi</span></span></p></td>
<td><p><span data-ttu-id="84b8c-135">MS1</span><span class="sxs-lookup"><span data-stu-id="84b8c-135">MS1</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84b8c-136">Tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="84b8c-136">Trunk 4 HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="84b8c-137">RESPECTIVA</span><span class="sxs-lookup"><span data-stu-id="84b8c-137">PBX</span></span></p></td>
<td><p><span data-ttu-id="84b8c-138">HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="84b8c-138">HYD-PBX</span></span></p></td>
<td><p><span data-ttu-id="84b8c-139">Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b8c-139">Hyderabad</span></span></p></td>
<td><p><span data-ttu-id="84b8c-140">MS1</span><span class="sxs-lookup"><span data-stu-id="84b8c-140">MS1</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="defines-voice-policies"></a><span data-ttu-id="84b8c-141">Define políticas de voz</span><span class="sxs-lookup"><span data-stu-id="84b8c-141">Defines Voice Policies</span></span>

<span data-ttu-id="84b8c-142">Você deve definir políticas de voz para a implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="84b8c-142">You must define voice policies for your Enterprise Voice deployment.</span></span> <span data-ttu-id="84b8c-143">Defina uma política de voz para impor restrições de roteamento com base no local a um subconjunto de usuários, se apenas um subconjunto deles for necessário para usar o roteamento baseado em local.</span><span class="sxs-lookup"><span data-stu-id="84b8c-143">Define a Voice Policy to enforce Location-Based Routing restrictions to a subset of users if only a subset of them is required to use Location-Based Routing.</span></span> <span data-ttu-id="84b8c-144">Neste exemplo, a tabela a seguir ilustra as políticas de voz usadas neste cenário.</span><span class="sxs-lookup"><span data-stu-id="84b8c-144">For this example, the following table illustrates the voice policies used in this scenario.</span></span> <span data-ttu-id="84b8c-145">Somente as configurações específicas do roteamento baseado em local são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="84b8c-145">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="84b8c-146">Para saber mais, confira [Configurando políticas de voz e registros de uso de PSTN para autorizar recursos e privilégios de chamada no Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span><span class="sxs-lookup"><span data-stu-id="84b8c-146">For more information, see [Configuring voice policies and PSTN usage records to authorize calling features and privileges in Lync Server 2013](lync-server-2013-configuring-voice-policies-and-pstn-usage-records-to-authorize-calling-features-and-privileges.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="84b8c-147">Política de voz 1</span><span class="sxs-lookup"><span data-stu-id="84b8c-147">Voice policy 1</span></span></th>
<th><span data-ttu-id="84b8c-148">Política de voz 2</span><span class="sxs-lookup"><span data-stu-id="84b8c-148">Voice policy 2</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84b8c-149">ID da política de voz</span><span class="sxs-lookup"><span data-stu-id="84b8c-149">Voice policy ID</span></span></p></td>
<td><p><span data-ttu-id="84b8c-150">Política de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="84b8c-150">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="84b8c-151">Política de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b8c-151">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84b8c-152">Usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="84b8c-152">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="84b8c-153">Uso de Delhi, uso de PBX, uso do PBX Hyd</span><span class="sxs-lookup"><span data-stu-id="84b8c-153">Delhi usage, PBX Del usage, PBX Hyd usage</span></span></p></td>
<td><p><span data-ttu-id="84b8c-154">Uso do Hyderabad, uso do PBX Hyd, uso do PBX</span><span class="sxs-lookup"><span data-stu-id="84b8c-154">Hyderabad usage, PBX Hyd usage, PBX Del usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84b8c-155">PreventPSTNTollBypass</span><span class="sxs-lookup"><span data-stu-id="84b8c-155">PreventPSTNTollBypass</span></span></p></td>
<td><p><span data-ttu-id="84b8c-156">Falso</span><span class="sxs-lookup"><span data-stu-id="84b8c-156">False</span></span></p></td>
<td><p><span data-ttu-id="84b8c-157">Falso</span><span class="sxs-lookup"><span data-stu-id="84b8c-157">False</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="define-voice-routes"></a><span data-ttu-id="84b8c-158">Definir rotas de voz</span><span class="sxs-lookup"><span data-stu-id="84b8c-158">Define Voice Routes</span></span>

<span data-ttu-id="84b8c-159">Você deve definir rotas de voz para sua implantação do Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="84b8c-159">You must define voice routes for your Enterprise Voice deployment.</span></span> <span data-ttu-id="84b8c-160">Neste exemplo, a tabela a seguir ilustra as rotas de voz usadas neste cenário.</span><span class="sxs-lookup"><span data-stu-id="84b8c-160">For this example, the following table illustrates the voice routes used in this scenario.</span></span> <span data-ttu-id="84b8c-161">Somente as configurações específicas do roteamento baseado em local são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="84b8c-161">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="84b8c-162">Para obter mais informações, consulte [Configurando rotas de voz para chamadas de saída no Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span><span class="sxs-lookup"><span data-stu-id="84b8c-162">For more information, see [Configuring voice routes for outbound calls in Lync Server 2013](lync-server-2013-configuring-voice-routes-for-outbound-calls.md).</span></span>


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
<th><span data-ttu-id="84b8c-163">Rota de voz 1</span><span class="sxs-lookup"><span data-stu-id="84b8c-163">Voice route 1</span></span></th>
<th><span data-ttu-id="84b8c-164">Rota de voz 2</span><span class="sxs-lookup"><span data-stu-id="84b8c-164">Voice route 2</span></span></th>
<th><span data-ttu-id="84b8c-165">Rota de voz 3</span><span class="sxs-lookup"><span data-stu-id="84b8c-165">Voice route 3</span></span></th>
<th><span data-ttu-id="84b8c-166">Rota de voz 4</span><span class="sxs-lookup"><span data-stu-id="84b8c-166">Voice route 4</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84b8c-167">Nome</span><span class="sxs-lookup"><span data-stu-id="84b8c-167">Name</span></span></p></td>
<td><p><span data-ttu-id="84b8c-168">Rota de Déli</span><span class="sxs-lookup"><span data-stu-id="84b8c-168">Delhi route</span></span></p></td>
<td><p><span data-ttu-id="84b8c-169">Rota Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b8c-169">Hyderabad route</span></span></p></td>
<td><p><span data-ttu-id="84b8c-170">Rota de del do PBX</span><span class="sxs-lookup"><span data-stu-id="84b8c-170">PBX Del route</span></span></p></td>
<td><p><span data-ttu-id="84b8c-171">Rota de Hyd PBX</span><span class="sxs-lookup"><span data-stu-id="84b8c-171">PBX Hyd route</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84b8c-172">Usos de PSTN</span><span class="sxs-lookup"><span data-stu-id="84b8c-172">PSTN usages</span></span></p></td>
<td><p><span data-ttu-id="84b8c-173">Uso de Delhi</span><span class="sxs-lookup"><span data-stu-id="84b8c-173">Delhi usage</span></span></p></td>
<td><p><span data-ttu-id="84b8c-174">Uso do Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b8c-174">Hyderabad usage</span></span></p></td>
<td><p><span data-ttu-id="84b8c-175">Uso do PBX del</span><span class="sxs-lookup"><span data-stu-id="84b8c-175">PBX Del usage</span></span></p></td>
<td><p><span data-ttu-id="84b8c-176">Uso do Hyd PBX</span><span class="sxs-lookup"><span data-stu-id="84b8c-176">PBX Hyd usage</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="84b8c-177">Trunk</span><span class="sxs-lookup"><span data-stu-id="84b8c-177">Trunk</span></span></p></td>
<td><p><span data-ttu-id="84b8c-178">Tronco 1 DEL-GW</span><span class="sxs-lookup"><span data-stu-id="84b8c-178">Trunk 1 DEL-GW</span></span></p></td>
<td><p><span data-ttu-id="84b8c-179">Tronco 2 HYD-GW</span><span class="sxs-lookup"><span data-stu-id="84b8c-179">Trunk 2 HYD-GW</span></span></p></td>
<td><p><span data-ttu-id="84b8c-180">Tronco 3 DEL-PBX</span><span class="sxs-lookup"><span data-stu-id="84b8c-180">Trunk 3 DEL-PBX</span></span></p></td>
<td><p><span data-ttu-id="84b8c-181">Tronco 4 HYD-PBX</span><span class="sxs-lookup"><span data-stu-id="84b8c-181">Trunk 4 HYD-PBX</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-users-for-enterprise-voice"></a><span data-ttu-id="84b8c-182">Habilitar usuários para o Enterprise Voice</span><span class="sxs-lookup"><span data-stu-id="84b8c-182">Enable Users for Enterprise Voice</span></span>

<span data-ttu-id="84b8c-183">Habilite usuários para o Enterprise Voice e atribua a eles uma política de voz que você tenha definido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="84b8c-183">Enable users for Enterprise Voice and assign them a voice policy you’ve previously defined.</span></span> <span data-ttu-id="84b8c-184">Neste exemplo, a tabela a seguir ilustra a atribuição usada neste cenário.</span><span class="sxs-lookup"><span data-stu-id="84b8c-184">For this example, the following table illustrates the assignment used in this scenario.</span></span> <span data-ttu-id="84b8c-185">Somente as configurações específicas do roteamento baseado em local são incluídas na tabela para fins de ilustração.</span><span class="sxs-lookup"><span data-stu-id="84b8c-185">Only settings that are specific to Location-Based Routing are included in the table for illustration purposes.</span></span>

<span data-ttu-id="84b8c-186">Para obter mais informações, consulte [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span><span class="sxs-lookup"><span data-stu-id="84b8c-186">For more information, see [Enable users for Enterprise Voice in Lync Server 2013](lync-server-2013-enable-users-for-enterprise-voice.md).</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th><span data-ttu-id="84b8c-187">Usuários localizados em Delhi</span><span class="sxs-lookup"><span data-stu-id="84b8c-187">Users located in Delhi</span></span></th>
<th><span data-ttu-id="84b8c-188">Usuários localizados no Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b8c-188">Users located in Hyderabad</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="84b8c-189">Política de voz associada</span><span class="sxs-lookup"><span data-stu-id="84b8c-189">Associated voice policy</span></span></p></td>
<td><p><span data-ttu-id="84b8c-190">Política de voz de Delhi</span><span class="sxs-lookup"><span data-stu-id="84b8c-190">Delhi voice policy</span></span></p></td>
<td><p><span data-ttu-id="84b8c-191">Política de voz Hyderabad</span><span class="sxs-lookup"><span data-stu-id="84b8c-191">Hyderabad voice policy</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="84b8c-192">Usuários de exemplo</span><span class="sxs-lookup"><span data-stu-id="84b8c-192">Sample users</span></span></p></td>
<td><p><span data-ttu-id="84b8c-193">DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="84b8c-193">DEL-LYNC-1,DEL-LYNC-2,DEL-LYNC-3</span></span></p></td>
<td><p><span data-ttu-id="84b8c-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span><span class="sxs-lookup"><span data-stu-id="84b8c-194">HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</span></span></p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="84b8c-195">Confira também</span><span class="sxs-lookup"><span data-stu-id="84b8c-195">See Also</span></span>


[<span data-ttu-id="84b8c-196">Configurando o roteamento baseado em local no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="84b8c-196">Configuring Location-Based Routing in Lync Server 2013</span></span>](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

