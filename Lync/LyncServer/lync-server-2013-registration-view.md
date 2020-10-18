---
title: 'Lync Server 2013: modo de exibição de registro'
description: 'Lync Server 2013: modo de exibição registro.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: be169cafc324f89cacedda154ca49a8ff1ff39aa
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48578518"
---
# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="9954f-103">Exibição de registro no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="9954f-103">Registration view in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="9954f-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="9954f-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="9954f-105">A visualização "Registro" armazena informações sobre o registro do usuário.</span><span class="sxs-lookup"><span data-stu-id="9954f-105">The Registration view stores information about user registration.</span></span> <span data-ttu-id="9954f-106">Este modo de exibição foi introduzido no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="9954f-106">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="9954f-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="9954f-107">Column</span></span></th>
<th><span data-ttu-id="9954f-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="9954f-108">Data Type</span></span></th>
<th><span data-ttu-id="9954f-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="9954f-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="9954f-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-111">datetime</span><span class="sxs-lookup"><span data-stu-id="9954f-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="9954f-112">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="9954f-112">Time of session request.</span></span> <span data-ttu-id="9954f-113">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="9954f-113">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="9954f-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9954f-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-116">int</span><span class="sxs-lookup"><span data-stu-id="9954f-116">int</span></span></p></td>
<td><p><span data-ttu-id="9954f-117">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="9954f-117">ID number to identify the session.</span></span> <span data-ttu-id="9954f-118">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="9954f-118">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="9954f-119">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9954f-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-120"><strong>Registertime</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-120"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-121">datetime</span><span class="sxs-lookup"><span data-stu-id="9954f-121">datetime</span></span></p></td>
<td><p><span data-ttu-id="9954f-122">Hora do registro.</span><span class="sxs-lookup"><span data-stu-id="9954f-122">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-123"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-123"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-124">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="9954f-124">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="9954f-125">URI do usuário registrado.</span><span class="sxs-lookup"><span data-stu-id="9954f-125">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-126"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-126"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-127">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9954f-127">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9954f-128">Tipo de  URI do usuário registrado.</span><span class="sxs-lookup"><span data-stu-id="9954f-128">Type of URI of the user who registered.</span></span> <span data-ttu-id="9954f-129">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9954f-129">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-130"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-130"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-131">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9954f-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9954f-132">Locatário do usuário registrado.</span><span class="sxs-lookup"><span data-stu-id="9954f-132">Tenant of the user who registered.</span></span> <span data-ttu-id="9954f-133">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9954f-133">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-134"><strong>Endpointid</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-134"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-135">identificador</span><span class="sxs-lookup"><span data-stu-id="9954f-135">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9954f-136">Identificador exclusivo do ponto de extremidade em que o usuário se registrou.</span><span class="sxs-lookup"><span data-stu-id="9954f-136">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-137"><strong>Ponteiro de fim</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-137"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-138">identificador</span><span class="sxs-lookup"><span data-stu-id="9954f-138">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="9954f-139">Identificador exclusivo usado para diferenciar registros que envolvam o mesmo usuário e o mesmo ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="9954f-139">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-140"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-140"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-141">datetime</span><span class="sxs-lookup"><span data-stu-id="9954f-141">datetime</span></span></p></td>
<td><p><span data-ttu-id="9954f-142">Hora do cancelamento do registro.</span><span class="sxs-lookup"><span data-stu-id="9954f-142">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-143"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-143"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-144">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9954f-144">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9954f-145">Motivo para o cancelamento do registro.</span><span class="sxs-lookup"><span data-stu-id="9954f-145">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-146"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-146"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-147">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9954f-147">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9954f-148">Versão do cliente usada no registro.</span><span class="sxs-lookup"><span data-stu-id="9954f-148">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-149"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-149"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-150">int</span><span class="sxs-lookup"><span data-stu-id="9954f-150">int</span></span></p></td>
<td><p><span data-ttu-id="9954f-151">Cliente usado pelo usuário no registro.</span><span class="sxs-lookup"><span data-stu-id="9954f-151">Client used by the user who registered.</span></span> <span data-ttu-id="9954f-152">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="9954f-152">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-153"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-153"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-154">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="9954f-154">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="9954f-155">Categoria do cliente do usuário no registro.</span><span class="sxs-lookup"><span data-stu-id="9954f-155">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-156"><strong>IpAddress</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-156"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-157">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9954f-157">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9954f-158">Endereço IP com o qual o usuário se registrou.</span><span class="sxs-lookup"><span data-stu-id="9954f-158">IP Address the user registered with.</span></span> <span data-ttu-id="9954f-159">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="9954f-159">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-160"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-160"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-161">VARSTRING (775)</span><span class="sxs-lookup"><span data-stu-id="9954f-161">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="9954f-p108">ID do diálogo de SIP. O formato é:</span><span class="sxs-lookup"><span data-stu-id="9954f-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="9954f-164">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="9954f-164">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-165"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-165"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-166">int</span><span class="sxs-lookup"><span data-stu-id="9954f-166">int</span></span></p></td>
<td><p><span data-ttu-id="9954f-p109">Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="9954f-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-170"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-170"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-171">int</span><span class="sxs-lookup"><span data-stu-id="9954f-171">int</span></span></p></td>
<td><p><span data-ttu-id="9954f-172">ID de diagnóstico registrado do cabeçalho do SIP.</span><span class="sxs-lookup"><span data-stu-id="9954f-172">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-173"><strong>Registrador</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-173"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-174">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9954f-174">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9954f-175">FQDN do registrador.</span><span class="sxs-lookup"><span data-stu-id="9954f-175">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-176"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-176"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-177">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9954f-177">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9954f-178">FQDN do pool que registrou os dados da sessão.</span><span class="sxs-lookup"><span data-stu-id="9954f-178">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-179"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-179"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-180">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9954f-180">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9954f-181">FQDN do servidor de borda usado pelo usuário que se registrou.</span><span class="sxs-lookup"><span data-stu-id="9954f-181">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-182"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-182"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-183">bits</span><span class="sxs-lookup"><span data-stu-id="9954f-183">bit</span></span></p></td>
<td><p><span data-ttu-id="9954f-184">Indica se o usuário fez logon a partir da rede interna.</span><span class="sxs-lookup"><span data-stu-id="9954f-184">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-185"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-185"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-186">bits</span><span class="sxs-lookup"><span data-stu-id="9954f-186">bit</span></span></p></td>
<td><p><span data-ttu-id="9954f-187">Indica se o UserService estava disponível no momento do registro.</span><span class="sxs-lookup"><span data-stu-id="9954f-187">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-188"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-188"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-189">bits</span><span class="sxs-lookup"><span data-stu-id="9954f-189">bit</span></span></p></td>
<td><p><span data-ttu-id="9954f-190">Indica se o registro foi feito com o registrador principal.</span><span class="sxs-lookup"><span data-stu-id="9954f-190">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-191"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-191"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-192">bigint</span><span class="sxs-lookup"><span data-stu-id="9954f-192">bigint</span></span></p></td>
<td><p><span data-ttu-id="9954f-193">Endereço MAC do dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="9954f-193">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="9954f-194"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-194"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-195">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9954f-195">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9954f-196">Fabricante do dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="9954f-196">Manufacturer of the device registered.</span></span> <span data-ttu-id="9954f-197">Consulte a <a href="lync-server-2013-manufacturers-table.md">tabela fabricantes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9954f-197">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="9954f-198"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="9954f-198"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="9954f-199">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="9954f-199">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="9954f-200">Versão do hardware do dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="9954f-200">Hardware version of the device registered.</span></span> <span data-ttu-id="9954f-201">Consulte a <a href="lync-server-2013-hardwareversions-table.md">tabela HardwareVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9954f-201">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

