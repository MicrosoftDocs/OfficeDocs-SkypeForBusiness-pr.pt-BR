---
title: 'Lync Server 2013: tabela de registro'
description: 'Lync Server 2013: tabela de registro.'
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
ms.openlocfilehash: 806e1a4e944c9bc04ebdd167c41c80a57fde3f29
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578517"
---
# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="50207-103">Tabela de registro no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="50207-103">Registration table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="50207-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="50207-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="50207-105">Cada registro representa um evento de registro de usuário.</span><span class="sxs-lookup"><span data-stu-id="50207-105">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="50207-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="50207-106">Column</span></span></th>
<th><span data-ttu-id="50207-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="50207-107">Data Type</span></span></th>
<th><span data-ttu-id="50207-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="50207-108">Key/Index</span></span></th>
<th><span data-ttu-id="50207-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="50207-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="50207-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="50207-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-111">datetime</span><span class="sxs-lookup"><span data-stu-id="50207-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="50207-112">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="50207-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="50207-113">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="50207-113">Time of session request.</span></span> <span data-ttu-id="50207-114">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="50207-114">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="50207-115">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50207-115">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50207-116"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="50207-116"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-117">int</span><span class="sxs-lookup"><span data-stu-id="50207-117">int</span></span></p></td>
<td><p><span data-ttu-id="50207-118">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="50207-118">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="50207-119">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="50207-119">ID number to identify the session.</span></span> <span data-ttu-id="50207-120">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="50207-120">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="50207-121">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50207-121">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50207-122"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="50207-122"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-123">int</span><span class="sxs-lookup"><span data-stu-id="50207-123">int</span></span></p></td>
<td><p><span data-ttu-id="50207-124">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="50207-124">Foreign</span></span></p></td>
<td><p><span data-ttu-id="50207-125">A ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="50207-125">The user ID.</span></span> <span data-ttu-id="50207-126">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50207-126">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50207-127"><strong>Endpointid</strong></span><span class="sxs-lookup"><span data-stu-id="50207-127"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-128">identificador</span><span class="sxs-lookup"><span data-stu-id="50207-128">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50207-p104">Um GUID para identificar um ponto de extremidade de registro. Geralmente, o evento de registro do mesmo computador do mesmo usuário terá a mesma ID de ponto de extremidade. Máquinas diferentes possuem uma ID de ponto de extremidade diferente.</span><span class="sxs-lookup"><span data-stu-id="50207-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50207-132"><strong>Ponteiro de fim</strong></span><span class="sxs-lookup"><span data-stu-id="50207-132"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-133">Identificador</span><span class="sxs-lookup"><span data-stu-id="50207-133">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50207-134">ID usado para diferenciar registros que envolvem o mesmo usuário e o mesmo ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="50207-134">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="50207-135">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50207-135">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50207-136"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="50207-136"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-137">int</span><span class="sxs-lookup"><span data-stu-id="50207-137">int</span></span></p></td>
<td><p><span data-ttu-id="50207-138">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="50207-138">Foreign</span></span></p></td>
<td><p><span data-ttu-id="50207-139">Versão do cliente do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="50207-139">Client version of current user.</span></span> <span data-ttu-id="50207-140">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50207-140">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50207-141"><strong>Registrador de registro</strong></span><span class="sxs-lookup"><span data-stu-id="50207-141"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-142">int</span><span class="sxs-lookup"><span data-stu-id="50207-142">int</span></span></p></td>
<td><p><span data-ttu-id="50207-143">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="50207-143">Foreign</span></span></p></td>
<td><p><span data-ttu-id="50207-144">ID do Servidor Registrador usado para registro.</span><span class="sxs-lookup"><span data-stu-id="50207-144">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="50207-145">Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50207-145">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50207-146"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="50207-146"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-147">int</span><span class="sxs-lookup"><span data-stu-id="50207-147">int</span></span></p></td>
<td><p><span data-ttu-id="50207-148">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="50207-148">Foreign</span></span></p></td>
<td><p><span data-ttu-id="50207-149">A ID do pool no qual a sessão foi capturada.</span><span class="sxs-lookup"><span data-stu-id="50207-149">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="50207-150">Consulte a <a href="lync-server-2013-pools-table.md">tabela pools no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50207-150">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50207-151"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="50207-151"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-152">int</span><span class="sxs-lookup"><span data-stu-id="50207-152">int</span></span></p></td>
<td><p><span data-ttu-id="50207-153">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="50207-153">Foreign</span></span></p></td>
<td><p><span data-ttu-id="50207-154">Servidor de Borda pelo qual o registro está passando.</span><span class="sxs-lookup"><span data-stu-id="50207-154">Edge Server the registration is going through.</span></span> <span data-ttu-id="50207-155">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50207-155">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50207-156"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="50207-156"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-157">Bits</span><span class="sxs-lookup"><span data-stu-id="50207-157">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50207-158">Quer o usuário esteja conectado internamente ou não.</span><span class="sxs-lookup"><span data-stu-id="50207-158">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50207-159"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="50207-159"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-160">bits</span><span class="sxs-lookup"><span data-stu-id="50207-160">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50207-161">Quer o UserService esteja disponível ou não.</span><span class="sxs-lookup"><span data-stu-id="50207-161">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50207-162"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="50207-162"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-163">bits</span><span class="sxs-lookup"><span data-stu-id="50207-163">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50207-164">Quer registre-se no primeiro Registrador ou não.</span><span class="sxs-lookup"><span data-stu-id="50207-164">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50207-165"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="50207-165"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-166">bits</span><span class="sxs-lookup"><span data-stu-id="50207-166">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50207-167">Indica se o usuário é registrado com um Aparelho de Filial Persistente.</span><span class="sxs-lookup"><span data-stu-id="50207-167">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="50207-168">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50207-168">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50207-169"><strong>Registertime</strong></span><span class="sxs-lookup"><span data-stu-id="50207-169"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-170">datetime</span><span class="sxs-lookup"><span data-stu-id="50207-170">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50207-171">Período de registro.</span><span class="sxs-lookup"><span data-stu-id="50207-171">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50207-172"><strong>Cancelar o Registrotime</strong></span><span class="sxs-lookup"><span data-stu-id="50207-172"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-173">datetime</span><span class="sxs-lookup"><span data-stu-id="50207-173">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50207-174">Período de cancelamento de registro.</span><span class="sxs-lookup"><span data-stu-id="50207-174">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50207-175"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="50207-175"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-176">int</span><span class="sxs-lookup"><span data-stu-id="50207-176">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50207-177">Código de resposta da solicitação de registro.</span><span class="sxs-lookup"><span data-stu-id="50207-177">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50207-178"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="50207-178"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-179">int</span><span class="sxs-lookup"><span data-stu-id="50207-179">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50207-p109">ID do diagnóstico da solicitação de registro, que indica o tipo de informação de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="50207-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50207-182"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="50207-182"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-183">int</span><span class="sxs-lookup"><span data-stu-id="50207-183">int</span></span></p></td>
<td><p><span data-ttu-id="50207-184">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="50207-184">Foreign</span></span></p></td>
<td><p><span data-ttu-id="50207-185">O dispositivo do qual a solicitação de registro está vindo.</span><span class="sxs-lookup"><span data-stu-id="50207-185">The device that the register request is coming from.</span></span> <span data-ttu-id="50207-186">Consulte a <a href="lync-server-2013-devices-table.md">tabela de dispositivos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50207-186">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="50207-187"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="50207-187"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-188">tinyint</span><span class="sxs-lookup"><span data-stu-id="50207-188">tinyint</span></span></p></td>
<td><p><span data-ttu-id="50207-189">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="50207-189">Foreign</span></span></p></td>
<td><p><span data-ttu-id="50207-190">O motivo do cancelamento do registro, como ‘iniciado pelo usuário’, ‘registro expirado’, ‘falha do cliente’ e mais.</span><span class="sxs-lookup"><span data-stu-id="50207-190">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="50207-191">Consulte a <a href="lync-server-2013-deregistertype-table.md">tabela Canregistertype no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="50207-191">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="50207-192"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="50207-192"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="50207-193">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="50207-193">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="50207-194">Iendereço de IP address do ponto da extremidade que o usuário é registrado.</span><span class="sxs-lookup"><span data-stu-id="50207-194">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="50207-195">Pode ser um endereço IPv4 ou IPv6 address.</span><span class="sxs-lookup"><span data-stu-id="50207-195">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="50207-196">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50207-196">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

