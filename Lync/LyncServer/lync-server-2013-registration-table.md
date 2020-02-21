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
ms.openlocfilehash: a64bde9cabcae282be83b671115a5cda4e5580e4
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42201497"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="registration-table-in-lync-server-2013"></a><span data-ttu-id="05ee7-102">Tabela de registro no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="05ee7-102">Registration table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="05ee7-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="05ee7-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="05ee7-104">Cada registro representa um evento de registro de usuário.</span><span class="sxs-lookup"><span data-stu-id="05ee7-104">Each record represents one user registration event.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="05ee7-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="05ee7-105">Column</span></span></th>
<th><span data-ttu-id="05ee7-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="05ee7-106">Data Type</span></span></th>
<th><span data-ttu-id="05ee7-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="05ee7-107">Key/Index</span></span></th>
<th><span data-ttu-id="05ee7-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="05ee7-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="05ee7-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-110">datetime</span><span class="sxs-lookup"><span data-stu-id="05ee7-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="05ee7-111">Primária, Estrangeira</span><span class="sxs-lookup"><span data-stu-id="05ee7-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ee7-112">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="05ee7-112">Time of session request.</span></span> <span data-ttu-id="05ee7-113">Usado em conjunto com <strong>SessionIdSeq</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="05ee7-113">Used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a session.</span></span> <span data-ttu-id="05ee7-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="05ee7-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ee7-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-116">int</span><span class="sxs-lookup"><span data-stu-id="05ee7-116">int</span></span></p></td>
<td><p><span data-ttu-id="05ee7-117">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="05ee7-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ee7-118">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="05ee7-118">ID number to identify the session.</span></span> <span data-ttu-id="05ee7-119">Usado em conjunto com <strong>SessionIdTime</strong> para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="05ee7-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a session.</span></span> <span data-ttu-id="05ee7-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="05ee7-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ee7-121"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-121"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-122">int</span><span class="sxs-lookup"><span data-stu-id="05ee7-122">int</span></span></p></td>
<td><p><span data-ttu-id="05ee7-123">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="05ee7-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ee7-124">A ID do usuário.</span><span class="sxs-lookup"><span data-stu-id="05ee7-124">The user ID.</span></span> <span data-ttu-id="05ee7-125">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="05ee7-125">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ee7-126"><strong>Endpointid</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-126"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-127">identificador</span><span class="sxs-lookup"><span data-stu-id="05ee7-127">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ee7-p104">Um GUID para identificar um ponto de extremidade de registro. Geralmente, o evento de registro do mesmo computador do mesmo usuário terá a mesma ID de ponto de extremidade. Máquinas diferentes possuem uma ID de ponto de extremidade diferente.</span><span class="sxs-lookup"><span data-stu-id="05ee7-p104">A GUID to identify a registration endpoint. Usually the register event from the same computer of the same user will have the same endpoint ID. Different machines have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ee7-131"><strong>Ponteiro de fim</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-131"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-132">Identificador</span><span class="sxs-lookup"><span data-stu-id="05ee7-132">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ee7-133">ID usado para diferenciar registros que envolvem o mesmo usuário e o mesmo ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="05ee7-133">ID used to differentiate registrations that involve the same user and the same endpoint.</span></span></p>
<p><span data-ttu-id="05ee7-134">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05ee7-134">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ee7-135"><strong>ClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-135"><strong>ClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-136">int</span><span class="sxs-lookup"><span data-stu-id="05ee7-136">int</span></span></p></td>
<td><p><span data-ttu-id="05ee7-137">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="05ee7-137">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ee7-138">Versão do cliente do usuário atual.</span><span class="sxs-lookup"><span data-stu-id="05ee7-138">Client version of current user.</span></span> <span data-ttu-id="05ee7-139">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="05ee7-139">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ee7-140"><strong>Registrador de registro</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-140"><strong>RegistrarId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-141">int</span><span class="sxs-lookup"><span data-stu-id="05ee7-141">int</span></span></p></td>
<td><p><span data-ttu-id="05ee7-142">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="05ee7-142">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ee7-143">ID do Servidor Registrador usado para registro.</span><span class="sxs-lookup"><span data-stu-id="05ee7-143">ID of the Registrar Server used for registration.</span></span> <span data-ttu-id="05ee7-144">Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="05ee7-144">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ee7-145"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-145"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-146">int</span><span class="sxs-lookup"><span data-stu-id="05ee7-146">int</span></span></p></td>
<td><p><span data-ttu-id="05ee7-147">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="05ee7-147">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ee7-148">A ID do pool no qual a sessão foi capturada.</span><span class="sxs-lookup"><span data-stu-id="05ee7-148">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="05ee7-149">Consulte a <a href="lync-server-2013-pools-table.md">tabela pools no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="05ee7-149">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ee7-150"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-150"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-151">int</span><span class="sxs-lookup"><span data-stu-id="05ee7-151">int</span></span></p></td>
<td><p><span data-ttu-id="05ee7-152">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="05ee7-152">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ee7-153">Servidor de Borda pelo qual o registro está passando.</span><span class="sxs-lookup"><span data-stu-id="05ee7-153">Edge Server the registration is going through.</span></span> <span data-ttu-id="05ee7-154">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="05ee7-154">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ee7-155"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-155"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-156">Bits</span><span class="sxs-lookup"><span data-stu-id="05ee7-156">Bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ee7-157">Quer o usuário esteja conectado internamente ou não.</span><span class="sxs-lookup"><span data-stu-id="05ee7-157">Whether the user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ee7-158"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-158"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-159">bits</span><span class="sxs-lookup"><span data-stu-id="05ee7-159">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ee7-160">Quer o UserService esteja disponível ou não.</span><span class="sxs-lookup"><span data-stu-id="05ee7-160">Whether the UserService is available or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ee7-161"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-161"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-162">bits</span><span class="sxs-lookup"><span data-stu-id="05ee7-162">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ee7-163">Quer registre-se no primeiro Registrador ou não.</span><span class="sxs-lookup"><span data-stu-id="05ee7-163">Whether register to the primary Registrar or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ee7-164"><strong>IsPrimaryRegistrarCentral</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-164"><strong>IsPrimaryRegistrarCentral</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-165">bits</span><span class="sxs-lookup"><span data-stu-id="05ee7-165">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ee7-166">Indica se o usuário é registrado com um Aparelho de Filial Persistente.</span><span class="sxs-lookup"><span data-stu-id="05ee7-166">Indicates whether or not the user is registered with a survivable branch appliance.</span></span></p>
<p><span data-ttu-id="05ee7-167">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05ee7-167">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ee7-168"><strong>Registertime</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-168"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-169">datetime</span><span class="sxs-lookup"><span data-stu-id="05ee7-169">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ee7-170">Período de registro.</span><span class="sxs-lookup"><span data-stu-id="05ee7-170">Registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ee7-171"><strong>Cancelar o Registrotime</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-171"><strong>DeRegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-172">datetime</span><span class="sxs-lookup"><span data-stu-id="05ee7-172">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ee7-173">Período de cancelamento de registro.</span><span class="sxs-lookup"><span data-stu-id="05ee7-173">De-Registration time.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ee7-174"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-174"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-175">int</span><span class="sxs-lookup"><span data-stu-id="05ee7-175">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ee7-176">Código de resposta da solicitação de registro.</span><span class="sxs-lookup"><span data-stu-id="05ee7-176">Response code of the register request.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ee7-177"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-177"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-178">int</span><span class="sxs-lookup"><span data-stu-id="05ee7-178">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ee7-p109">ID do diagnóstico da solicitação de registro, que indica o tipo de informação de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="05ee7-p109">Diagnostic ID of the register request. This indicates that diagnostic information type.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ee7-181"><strong>DeviceId</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-181"><strong>DeviceId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-182">int</span><span class="sxs-lookup"><span data-stu-id="05ee7-182">int</span></span></p></td>
<td><p><span data-ttu-id="05ee7-183">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="05ee7-183">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ee7-184">O dispositivo do qual a solicitação de registro está vindo.</span><span class="sxs-lookup"><span data-stu-id="05ee7-184">The device that the register request is coming from.</span></span> <span data-ttu-id="05ee7-185">Consulte a <a href="lync-server-2013-devices-table.md">tabela de dispositivos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="05ee7-185">See the <a href="lync-server-2013-devices-table.md">Devices table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="05ee7-186"><strong>DeRegisterTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-186"><strong>DeRegisterTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-187">tinyint</span><span class="sxs-lookup"><span data-stu-id="05ee7-187">tinyint</span></span></p></td>
<td><p><span data-ttu-id="05ee7-188">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="05ee7-188">Foreign</span></span></p></td>
<td><p><span data-ttu-id="05ee7-189">O motivo do cancelamento do registro, como ‘iniciado pelo usuário’, ‘registro expirado’, ‘falha do cliente’ e mais.</span><span class="sxs-lookup"><span data-stu-id="05ee7-189">The reason of de-register, such as ‘user initiated’, ‘registration expired’, ‘client fail’, and more.</span></span> <span data-ttu-id="05ee7-190">Consulte a <a href="lync-server-2013-deregistertype-table.md">tabela Canregistertype no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="05ee7-190">See the <a href="lync-server-2013-deregistertype-table.md">DeRegisterType table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="05ee7-191"><strong>IPAddress</strong></span><span class="sxs-lookup"><span data-stu-id="05ee7-191"><strong>IPAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="05ee7-192">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="05ee7-192">nvarchar(256)</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="05ee7-193">Iendereço de IP address do ponto da extremidade que o usuário é registrado.</span><span class="sxs-lookup"><span data-stu-id="05ee7-193">IP address of the endpoint the user registered with.</span></span> <span data-ttu-id="05ee7-194">Pode ser um endereço IPv4 ou IPv6 address.</span><span class="sxs-lookup"><span data-stu-id="05ee7-194">This can be an IPv4 address or an IPv6 address.</span></span></p>
<p><span data-ttu-id="05ee7-195">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="05ee7-195">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

