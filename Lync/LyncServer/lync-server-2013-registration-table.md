---
title: 'Lync Server 2013: Tabela de registro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dfee81d83fb58b2fbeccff68a672da47e6770bd6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823795"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="3872a-102">Tabela de registro no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3872a-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3872a-103">_**Tópico da última modificação:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="3872a-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="3872a-104">Cada registro representa um evento de registro de usuário.</span><span class="sxs-lookup"><span data-stu-id="3872a-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3872a-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="3872a-105">Column</span></span></th>
<th><span data-ttu-id="3872a-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3872a-106">Data Type</span></span></th>
<th><span data-ttu-id="3872a-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="3872a-107">Key/Index</span></span></th>
<th><span data-ttu-id="3872a-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3872a-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3872a-109"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="3872a-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="3872a-111">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="3872a-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3872a-112">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="3872a-112">Time of session request.</span></span> <span data-ttu-id="3872a-113">Usado em conjunto com o <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="3872a-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="3872a-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3872a-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3872a-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-116">int</span><span class="sxs-lookup"><span data-stu-id="3872a-116">int</span></span></p></td>
<td><p><span data-ttu-id="3872a-117">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="3872a-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="3872a-118">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="3872a-118">ID number to identify the session.</span></span> <span data-ttu-id="3872a-119">Usado em conjunto com <strong></strong> a identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="3872a-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="3872a-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3872a-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3872a-121"><strong>ID</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-122">int</span><span class="sxs-lookup"><span data-stu-id="3872a-122">int</span></span></p></td>
<td><p><span data-ttu-id="3872a-123">Exterior</span><span class="sxs-lookup"><span data-stu-id="3872a-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3872a-124">A ID de usuário.</span><span class="sxs-lookup"><span data-stu-id="3872a-124">The user ID.</span></span> <span data-ttu-id="3872a-125">Consulte a <a href="lync-server-2013-users-table.md">tabela usuários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3872a-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3872a-126"><strong>Endpointid</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-127">identificador</span><span class="sxs-lookup"><span data-stu-id="3872a-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3872a-128">Um GUID para identificar um ponto de extremidade de registro.</span><span class="sxs-lookup"><span data-stu-id="3872a-128">A GUID to identify a registration endpoint.</span></span> <span data-ttu-id="3872a-129">Geralmente, o evento Register do mesmo computador do mesmo usuário terá a mesma ID de ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="3872a-129">Usually the register event from the same computer of the same user will have the same endpoint ID.</span></span> <span data-ttu-id="3872a-130">Máquinas diferentes têm uma ID de ponto de extremidade diferente.</span><span class="sxs-lookup"><span data-stu-id="3872a-130">Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3872a-131"><strong>Ponteiro de fim</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-132">Identificador</span><span class="sxs-lookup"><span data-stu-id="3872a-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3872a-133">ID usada para diferenciar os registros que envolvem o mesmo usuário e o mesmo ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="3872a-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="3872a-134">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3872a-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3872a-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-136">int</span><span class="sxs-lookup"><span data-stu-id="3872a-136">int</span></span></p></td>
<td><p><span data-ttu-id="3872a-137">Exterior</span><span class="sxs-lookup"><span data-stu-id="3872a-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3872a-138">Versão cliente do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="3872a-138">Client version of current user.</span></span> <span data-ttu-id="3872a-139">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3872a-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3872a-140"><strong>Registrador de registro</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-141">int</span><span class="sxs-lookup"><span data-stu-id="3872a-141">int</span></span></p></td>
<td><p><span data-ttu-id="3872a-142">Exterior</span><span class="sxs-lookup"><span data-stu-id="3872a-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3872a-143">ID do servidor de registrador usado para registro.</span><span class="sxs-lookup"><span data-stu-id="3872a-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="3872a-144">Consulte a <a href="lync-server-2013-servers-table.md">tabela servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3872a-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3872a-145"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-146">int</span><span class="sxs-lookup"><span data-stu-id="3872a-146">int</span></span></p></td>
<td><p><span data-ttu-id="3872a-147">Exterior</span><span class="sxs-lookup"><span data-stu-id="3872a-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3872a-148">ID do pool no qual a sessão foi capturada.</span><span class="sxs-lookup"><span data-stu-id="3872a-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="3872a-149">Consulte a <a href="lync-server-2013-pools-table.md">tabela de grupos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3872a-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3872a-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-151">int</span><span class="sxs-lookup"><span data-stu-id="3872a-151">int</span></span></p></td>
<td><p><span data-ttu-id="3872a-152">Exterior</span><span class="sxs-lookup"><span data-stu-id="3872a-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3872a-153">Servidor de borda no qual o registro está indo.</span><span class="sxs-lookup"><span data-stu-id="3872a-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="3872a-154">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3872a-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3872a-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-156">Bit</span><span class="sxs-lookup"><span data-stu-id="3872a-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3872a-157">Se o usuário está conectado de Internal ou not.</span><span class="sxs-lookup"><span data-stu-id="3872a-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3872a-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-159">bit</span><span class="sxs-lookup"><span data-stu-id="3872a-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3872a-160">Se o UserService está disponível ou não.</span><span class="sxs-lookup"><span data-stu-id="3872a-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3872a-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-162">bit</span><span class="sxs-lookup"><span data-stu-id="3872a-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3872a-163">Se registrar ao registrador principal ou não.</span><span class="sxs-lookup"><span data-stu-id="3872a-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3872a-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-165">bit</span><span class="sxs-lookup"><span data-stu-id="3872a-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3872a-166">Indica se o usuário está ou não registrado em um aparelho de ramificação sobreviventes.</span><span class="sxs-lookup"><span data-stu-id="3872a-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="3872a-167">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3872a-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3872a-168"><strong>Registertime</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-169">datetime</span><span class="sxs-lookup"><span data-stu-id="3872a-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3872a-170">Hora do registro.</span><span class="sxs-lookup"><span data-stu-id="3872a-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3872a-171"><strong>Cancelar registro</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-172">datetime</span><span class="sxs-lookup"><span data-stu-id="3872a-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3872a-173">Hora de cancelamento de registro.</span><span class="sxs-lookup"><span data-stu-id="3872a-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3872a-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-175">int</span><span class="sxs-lookup"><span data-stu-id="3872a-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3872a-176">Código de resposta da solicitação de registro.</span><span class="sxs-lookup"><span data-stu-id="3872a-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3872a-177"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-178">int</span><span class="sxs-lookup"><span data-stu-id="3872a-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3872a-179">ID do diagnóstico da solicitação de registro.</span><span class="sxs-lookup"><span data-stu-id="3872a-179">Diagnostic ID of the register request.</span></span> <span data-ttu-id="3872a-180">Isso indica que o tipo de informações de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="3872a-180">This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3872a-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-182">int</span><span class="sxs-lookup"><span data-stu-id="3872a-182">int</span></span></p></td>
<td><p><span data-ttu-id="3872a-183">Exterior</span><span class="sxs-lookup"><span data-stu-id="3872a-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3872a-184">O dispositivo do qual a solicitação de registro provém.</span><span class="sxs-lookup"><span data-stu-id="3872a-184">The device that the register request is coming from.</span></span> <span data-ttu-id="3872a-185">Consulte a <a href="lync-server-2013-devices-table.md">tabela de dispositivos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3872a-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3872a-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="3872a-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="3872a-188">Exterior</span><span class="sxs-lookup"><span data-stu-id="3872a-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="3872a-189">O motivo do cancelamento de registro, como ' iniciado pelo usuário ', ' registro expirado ', ' falha do cliente ' e muito mais.</span><span class="sxs-lookup"><span data-stu-id="3872a-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="3872a-190">Consulte a <a href="lync-server-2013-deregistertype-table.md">tabela Canregistertype no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3872a-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3872a-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="3872a-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="3872a-192">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3872a-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="3872a-193">Endereço IP do ponto de extremidade ao qual o usuário se cadastrou.</span><span class="sxs-lookup"><span data-stu-id="3872a-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="3872a-194">Pode ser um endereço IPv4 ou um endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="3872a-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="3872a-195">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3872a-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

