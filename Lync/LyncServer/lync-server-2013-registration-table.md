---
title: 'Lync Server 2013: tabela de registro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration table
ms:assetid: 05ff9dd3-1aaa-4af0-bd69-8789fb8eaeb3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398114(v=OCS.15)
ms:contentKeyID: 48183298
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0679915e73061e550e01c0809fd5c5b20b566ff6
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050713"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="d316b-102">Tabela de registro no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d316b-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d316b-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d316b-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d316b-104">Cada registro representa um evento de registro de usuário.</span><span class="sxs-lookup"><span data-stu-id="d316b-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d316b-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="d316b-105">Column</span></span></th>
<th><span data-ttu-id="d316b-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="d316b-106">Data Type</span></span></th>
<th><span data-ttu-id="d316b-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="d316b-107">Key/Index</span></span></th>
<th><span data-ttu-id="d316b-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d316b-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d316b-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-110">datetime</span><span class="sxs-lookup"><span data-stu-id="d316b-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="d316b-111">Primária, Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d316b-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d316b-112">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="d316b-112">Time of session request.</span></span> <span data-ttu-id="d316b-113">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d316b-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d316b-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d316b-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d316b-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-116">int</span><span class="sxs-lookup"><span data-stu-id="d316b-116">int</span></span></p></td>
<td><p><span data-ttu-id="d316b-117">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="d316b-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d316b-118">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="d316b-118">ID number to identify the session.</span></span> <span data-ttu-id="d316b-119">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d316b-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="d316b-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d316b-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d316b-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-122">int</span><span class="sxs-lookup"><span data-stu-id="d316b-122">int</span></span></p></td>
<td><p><span data-ttu-id="d316b-123">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d316b-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d316b-124">A ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="d316b-124">The user ID.</span></span> <span data-ttu-id="d316b-125">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d316b-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d316b-126"><strong>Endpointid</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-127">identificador</span><span class="sxs-lookup"><span data-stu-id="d316b-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d316b-p104">Um GUID para identificar um ponto de extremidade de registro. Geralmente, o evento de registro do mesmo computador do mesmo usuário terá a mesma ID de ponto de extremidade. Máquinas diferentes possuem uma ID de ponto de extremidade diferente.</span><span class="sxs-lookup"><span data-stu-id="d316b-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d316b-131"><strong>Ponteiro de fim</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-132">Identificador</span><span class="sxs-lookup"><span data-stu-id="d316b-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d316b-133">ID usado para diferenciar registros que envolvem o mesmo usuário e o mesmo ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="d316b-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="d316b-134">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d316b-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d316b-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-136">int</span><span class="sxs-lookup"><span data-stu-id="d316b-136">int</span></span></p></td>
<td><p><span data-ttu-id="d316b-137">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d316b-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d316b-138">Versão do cliente do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="d316b-138">Client version of current user.</span></span> <span data-ttu-id="d316b-139">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d316b-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d316b-140"><strong>Registrador de registro</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-141">int</span><span class="sxs-lookup"><span data-stu-id="d316b-141">int</span></span></p></td>
<td><p><span data-ttu-id="d316b-142">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d316b-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d316b-143">ID do Servidor Registrador usado para registro.</span><span class="sxs-lookup"><span data-stu-id="d316b-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="d316b-144">Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d316b-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d316b-145"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-146">int</span><span class="sxs-lookup"><span data-stu-id="d316b-146">int</span></span></p></td>
<td><p><span data-ttu-id="d316b-147">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d316b-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d316b-148">A ID do pool no qual a sessão foi capturada.</span><span class="sxs-lookup"><span data-stu-id="d316b-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="d316b-149">Consulte a <a href="lync-server-2013-pools-table.md">tabela pools no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d316b-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d316b-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-151">int</span><span class="sxs-lookup"><span data-stu-id="d316b-151">int</span></span></p></td>
<td><p><span data-ttu-id="d316b-152">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d316b-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d316b-153">Servidor de Borda pelo qual o registro está passando.</span><span class="sxs-lookup"><span data-stu-id="d316b-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="d316b-154">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d316b-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d316b-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-156">Bits</span><span class="sxs-lookup"><span data-stu-id="d316b-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d316b-157">Quer o usuário esteja conectado internamente ou não.</span><span class="sxs-lookup"><span data-stu-id="d316b-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d316b-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-159">bits</span><span class="sxs-lookup"><span data-stu-id="d316b-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d316b-160">Quer o UserService esteja disponível ou não.</span><span class="sxs-lookup"><span data-stu-id="d316b-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d316b-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-162">bits</span><span class="sxs-lookup"><span data-stu-id="d316b-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d316b-163">Quer registre-se no primeiro Registrador ou não.</span><span class="sxs-lookup"><span data-stu-id="d316b-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d316b-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-165">bits</span><span class="sxs-lookup"><span data-stu-id="d316b-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d316b-166">Indica se o usuário é registrado com um Aparelho de Filial Persistente.</span><span class="sxs-lookup"><span data-stu-id="d316b-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="d316b-167">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d316b-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d316b-168"><strong>Registertime</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-169">datetime</span><span class="sxs-lookup"><span data-stu-id="d316b-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d316b-170">Período de registro.</span><span class="sxs-lookup"><span data-stu-id="d316b-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d316b-171"><strong>Cancelar o Registrotime</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-172">datetime</span><span class="sxs-lookup"><span data-stu-id="d316b-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d316b-173">Período de cancelamento de registro.</span><span class="sxs-lookup"><span data-stu-id="d316b-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d316b-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-175">int</span><span class="sxs-lookup"><span data-stu-id="d316b-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d316b-176">Código de resposta da solicitação de registro.</span><span class="sxs-lookup"><span data-stu-id="d316b-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d316b-177"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-178">int</span><span class="sxs-lookup"><span data-stu-id="d316b-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d316b-p109">ID do diagnóstico da solicitação de registro, que indica o tipo de informação de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="d316b-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d316b-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-182">int</span><span class="sxs-lookup"><span data-stu-id="d316b-182">int</span></span></p></td>
<td><p><span data-ttu-id="d316b-183">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d316b-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d316b-184">O dispositivo do qual a solicitação de registro está vindo.</span><span class="sxs-lookup"><span data-stu-id="d316b-184">The device that the register request is coming from.</span></span> <span data-ttu-id="d316b-185">Consulte a <a href="lync-server-2013-devices-table.md">tabela de dispositivos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d316b-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d316b-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="d316b-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d316b-188">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d316b-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d316b-189">O motivo do cancelamento do registro, como ‘iniciado pelo usuário’, ‘registro expirado’, ‘falha do cliente’ e mais.</span><span class="sxs-lookup"><span data-stu-id="d316b-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="d316b-190">Consulte a <a href="lync-server-2013-deregistertype-table.md">tabela Canregistertype no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d316b-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d316b-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="d316b-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="d316b-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="d316b-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d316b-193">Iendereço de IP address do ponto da extremidade que o usuário é registrado.</span><span class="sxs-lookup"><span data-stu-id="d316b-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="d316b-194">Pode ser um endereço IPv4 ou IPv6 address.</span><span class="sxs-lookup"><span data-stu-id="d316b-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="d316b-195">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d316b-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

