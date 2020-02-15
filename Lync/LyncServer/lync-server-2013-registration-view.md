---
title: 'Lync Server 2013: modo de exibição de registro'
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
ms.openlocfilehash: a7418c5aa80e35d783517a86626dd2b77a393e1d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42050703"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="3aea7-102">Exibição de registro no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="3aea7-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="3aea7-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="3aea7-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="3aea7-104">A visualização "Registro" armazena informações sobre o registro do usuário.</span><span class="sxs-lookup"><span data-stu-id="3aea7-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="3aea7-105">Este modo de exibição foi introduzido no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3aea7-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="3aea7-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="3aea7-106">Column</span></span></th>
<th><span data-ttu-id="3aea7-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="3aea7-107">Data Type</span></span></th>
<th><span data-ttu-id="3aea7-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="3aea7-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-110">datetime</span><span class="sxs-lookup"><span data-stu-id="3aea7-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="3aea7-111">Hora da solicitação da sessão.</span><span class="sxs-lookup"><span data-stu-id="3aea7-111">Time of session request.</span></span> <span data-ttu-id="3aea7-112">Utilizada em conjunto com o SessionIdSeq para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="3aea7-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="3aea7-113">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3aea7-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-115">int</span><span class="sxs-lookup"><span data-stu-id="3aea7-115">int</span></span></p></td>
<td><p><span data-ttu-id="3aea7-116">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="3aea7-116">ID number to identify the session.</span></span> <span data-ttu-id="3aea7-117">Utilizado em conjunto com o SessionIdTime para identificar de forma exclusiva uma sessão.</span><span class="sxs-lookup"><span data-stu-id="3aea7-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="3aea7-118">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3aea7-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-119"><strong>Registertime</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-120">datetime</span><span class="sxs-lookup"><span data-stu-id="3aea7-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="3aea7-121">Hora do registro.</span><span class="sxs-lookup"><span data-stu-id="3aea7-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="3aea7-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-124">URI do usuário registrado.</span><span class="sxs-lookup"><span data-stu-id="3aea7-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-126">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aea7-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-127">Tipo de  URI do usuário registrado.</span><span class="sxs-lookup"><span data-stu-id="3aea7-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="3aea7-128">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3aea7-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-129"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-130">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aea7-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-131">Locatário do usuário registrado.</span><span class="sxs-lookup"><span data-stu-id="3aea7-131">Tenant of the user who registered.</span></span> <span data-ttu-id="3aea7-132">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3aea7-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-133"><strong>Endpointid</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-134">identificador</span><span class="sxs-lookup"><span data-stu-id="3aea7-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="3aea7-135">Identificador exclusivo do ponto de extremidade em que o usuário se registrou.</span><span class="sxs-lookup"><span data-stu-id="3aea7-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-136"><strong>Ponteiro de fim</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-137">identificador</span><span class="sxs-lookup"><span data-stu-id="3aea7-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="3aea7-138">Identificador exclusivo usado para diferenciar registros que envolvam o mesmo usuário e o mesmo ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="3aea7-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-140">datetime</span><span class="sxs-lookup"><span data-stu-id="3aea7-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="3aea7-141">Hora do cancelamento do registro.</span><span class="sxs-lookup"><span data-stu-id="3aea7-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-143">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aea7-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-144">Motivo para o cancelamento do registro.</span><span class="sxs-lookup"><span data-stu-id="3aea7-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-146">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aea7-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-147">Versão do cliente usada no registro.</span><span class="sxs-lookup"><span data-stu-id="3aea7-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-149">int</span><span class="sxs-lookup"><span data-stu-id="3aea7-149">int</span></span></p></td>
<td><p><span data-ttu-id="3aea7-150">Cliente usado pelo usuário no registro.</span><span class="sxs-lookup"><span data-stu-id="3aea7-150">Client used by the user who registered.</span></span> <span data-ttu-id="3aea7-151">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="3aea7-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="3aea7-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-154">Categoria do cliente do usuário no registro.</span><span class="sxs-lookup"><span data-stu-id="3aea7-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-155"><strong>IpAddress</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-156">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aea7-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-157">Endereço IP com o qual o usuário se registrou.</span><span class="sxs-lookup"><span data-stu-id="3aea7-157">IP Address the user registered with.</span></span> <span data-ttu-id="3aea7-158">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="3aea7-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-159"><strong>DialogId</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-160">VARSTRING (775)</span><span class="sxs-lookup"><span data-stu-id="3aea7-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-p108">ID do diálogo de SIP. O formato é:</span><span class="sxs-lookup"><span data-stu-id="3aea7-p108">SIP dialog ID. The format of the is:</span></span></p>
<p><span data-ttu-id="3aea7-163">caixa de diálogo; de-tag; to-tag</span><span class="sxs-lookup"><span data-stu-id="3aea7-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-165">int</span><span class="sxs-lookup"><span data-stu-id="3aea7-165">int</span></span></p></td>
<td><p><span data-ttu-id="3aea7-p109">Código de resposta SIP para convite de sessão. Este campo é normalmente preenchido por dados gerados na mensagem CONVIDAR inicial na sessão. Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="3aea7-p109">SIP response code to the session invitation. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-169"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-170">int</span><span class="sxs-lookup"><span data-stu-id="3aea7-170">int</span></span></p></td>
<td><p><span data-ttu-id="3aea7-171">ID de diagnóstico registrado do cabeçalho do SIP.</span><span class="sxs-lookup"><span data-stu-id="3aea7-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-172"><strong>Registrador</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-173">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aea7-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-174">FQDN do registrador.</span><span class="sxs-lookup"><span data-stu-id="3aea7-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-176">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aea7-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-177">FQDN do pool que registrou os dados da sessão.</span><span class="sxs-lookup"><span data-stu-id="3aea7-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-179">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aea7-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-180">FQDN do servidor de borda usado pelo usuário que se registrou.</span><span class="sxs-lookup"><span data-stu-id="3aea7-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-182">bits</span><span class="sxs-lookup"><span data-stu-id="3aea7-182">bit</span></span></p></td>
<td><p><span data-ttu-id="3aea7-183">Indica se o usuário fez logon a partir da rede interna.</span><span class="sxs-lookup"><span data-stu-id="3aea7-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-185">bits</span><span class="sxs-lookup"><span data-stu-id="3aea7-185">bit</span></span></p></td>
<td><p><span data-ttu-id="3aea7-186">Indica se o UserService estava disponível no momento do registro.</span><span class="sxs-lookup"><span data-stu-id="3aea7-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-188">bits</span><span class="sxs-lookup"><span data-stu-id="3aea7-188">bit</span></span></p></td>
<td><p><span data-ttu-id="3aea7-189">Indica se o registro foi feito com o registrador principal.</span><span class="sxs-lookup"><span data-stu-id="3aea7-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-191">bigint</span><span class="sxs-lookup"><span data-stu-id="3aea7-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="3aea7-192">Endereço MAC do dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="3aea7-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="3aea7-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-194">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aea7-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-195">Fabricante do dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="3aea7-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="3aea7-196">Consulte a <a href="lync-server-2013-manufacturers-table.md">tabela fabricantes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3aea7-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="3aea7-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="3aea7-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="3aea7-198">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="3aea7-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="3aea7-199">Versão do hardware do dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="3aea7-199">Hardware version of the device registered.</span></span> <span data-ttu-id="3aea7-200">Consulte a <a href="lync-server-2013-hardwareversions-table.md">tabela HardwareVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="3aea7-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

