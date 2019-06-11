---
title: 'Lync Server 2013: modo de exibição de registro'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Registration view
ms:assetid: 8a42bc7d-3d4f-43c1-9e15-89b2ee419ade
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688120(v=OCS.15)
ms:contentKeyID: 49733718
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fe1b01b748204d3d4365b6f28ae4480d3632b35a
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34823823"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="registration-view-in-lync-server-2013"></a><span data-ttu-id="f6661-102">Modo de exibição de registro no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f6661-102">Registration view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f6661-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="f6661-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="f6661-104">O modo de exibição de registro armazena informações sobre o registro de usuário.</span><span class="sxs-lookup"><span data-stu-id="f6661-104">The Registration view stores information about user registration.</span></span> <span data-ttu-id="f6661-105">Este modo de exibição foi apresentado no Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="f6661-105">This view was introduced in Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="f6661-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="f6661-106">Column</span></span></th>
<th><span data-ttu-id="f6661-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="f6661-107">Data Type</span></span></th>
<th><span data-ttu-id="f6661-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="f6661-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="f6661-109"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f6661-110">datetime</span></span></p></td>
<td><p><span data-ttu-id="f6661-111">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="f6661-111">Time of session request.</span></span> <span data-ttu-id="f6661-112">Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="f6661-112">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="f6661-113">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f6661-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-115">int</span><span class="sxs-lookup"><span data-stu-id="f6661-115">int</span></span></p></td>
<td><p><span data-ttu-id="f6661-116">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="f6661-116">ID number to identify the session.</span></span> <span data-ttu-id="f6661-117">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="f6661-117">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="f6661-118">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f6661-118">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-119"><strong>Registertime</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-119"><strong>RegisterTime</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-120">datetime</span><span class="sxs-lookup"><span data-stu-id="f6661-120">datetime</span></span></p></td>
<td><p><span data-ttu-id="f6661-121">Hora em que ocorreu o registro.</span><span class="sxs-lookup"><span data-stu-id="f6661-121">Time at which registration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-122"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-122"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-123">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="f6661-123">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="f6661-124">URL do usuário que se cadastrou.</span><span class="sxs-lookup"><span data-stu-id="f6661-124">URI of the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-125"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-125"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-126">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f6661-126">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6661-127">Tipo de URI do usuário que se cadastrou.</span><span class="sxs-lookup"><span data-stu-id="f6661-127">Type of URI of the user who registered.</span></span> <span data-ttu-id="f6661-128">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f6661-128">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-129"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-129"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-130">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f6661-130">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6661-131">Locatário do usuário que se cadastrou.</span><span class="sxs-lookup"><span data-stu-id="f6661-131">Tenant of the user who registered.</span></span> <span data-ttu-id="f6661-132">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f6661-132">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-133"><strong>Endpointid</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-133"><strong>EndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-134">identificador</span><span class="sxs-lookup"><span data-stu-id="f6661-134">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f6661-135">Identificador exclusivo do ponto de extremidade do usuário registrado.</span><span class="sxs-lookup"><span data-stu-id="f6661-135">Unique identifier of the endpoint of the user registered with.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-136"><strong>Ponteiro de fim</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-136"><strong>EndpointEra</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-137">identificador</span><span class="sxs-lookup"><span data-stu-id="f6661-137">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="f6661-138">Identificador exclusivo usado para diferenciar os registros que envolvem o mesmo usuário e o mesmo ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="f6661-138">Unique identifier used to differentiate registrations that involve the same user and the same endpoint.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-139"><strong>DeRegisterType</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-139"><strong>DeRegisterType</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-140">datetime</span><span class="sxs-lookup"><span data-stu-id="f6661-140">datetime</span></span></p></td>
<td><p><span data-ttu-id="f6661-141">Tempo em que o cancelamento ocorreu.</span><span class="sxs-lookup"><span data-stu-id="f6661-141">Time at which deregistration occurred.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-142"><strong>DeRegisterReason</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-142"><strong>DeRegisterReason</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-143">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f6661-143">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6661-144">Motivo do cancelamento de registro.</span><span class="sxs-lookup"><span data-stu-id="f6661-144">Reason for deregistration.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-145"><strong>ClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-145"><strong>ClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-146">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f6661-146">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6661-147">Versão do cliente usada pelo usuário que se cadastrou.</span><span class="sxs-lookup"><span data-stu-id="f6661-147">Version of client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-148"><strong>ClientType</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-148"><strong>ClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-149">int</span><span class="sxs-lookup"><span data-stu-id="f6661-149">int</span></span></p></td>
<td><p><span data-ttu-id="f6661-150">Cliente usado pelo usuário que se cadastrou.</span><span class="sxs-lookup"><span data-stu-id="f6661-150">Client used by the user who registered.</span></span> <span data-ttu-id="f6661-151">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="f6661-151">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-152"><strong>ClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-152"><strong>ClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-153">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="f6661-153">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="f6661-154">Categoria do cliente usada pelo usuário que se cadastrou.</span><span class="sxs-lookup"><span data-stu-id="f6661-154">Category of the client used by the user who registered.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-155"><strong>IP</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-155"><strong>IpAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-156">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f6661-156">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6661-157">Endereço IP com o qual o usuário se cadastrou.</span><span class="sxs-lookup"><span data-stu-id="f6661-157">IP Address the user registered with.</span></span> <span data-ttu-id="f6661-158">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="f6661-158">This may be an IPv4 or IPv6 address.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-159"><strong>Caixa de diálogo</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-159"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-160">VARSTRING (775)</span><span class="sxs-lookup"><span data-stu-id="f6661-160">varstring(775)</span></span></p></td>
<td><p><span data-ttu-id="f6661-161">ID da caixa de diálogo SIP.</span><span class="sxs-lookup"><span data-stu-id="f6661-161">SIP dialog ID.</span></span> <span data-ttu-id="f6661-162">O formato do é:</span><span class="sxs-lookup"><span data-stu-id="f6661-162">The format of the is:</span></span></p>
<p><span data-ttu-id="f6661-163">caixa de diálogo; de-marca; até-marca</span><span class="sxs-lookup"><span data-stu-id="f6661-163">dialog;from-tag;to-tag</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-164"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-164"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-165">int</span><span class="sxs-lookup"><span data-stu-id="f6661-165">int</span></span></p></td>
<td><p><span data-ttu-id="f6661-166">Código de resposta SIP para o convite da sessão.</span><span class="sxs-lookup"><span data-stu-id="f6661-166">SIP response code to the session invitation.</span></span> <span data-ttu-id="f6661-167">Geralmente, esse campo é preenchido por dados gerados da mensagem de convite inicial na sessão.</span><span class="sxs-lookup"><span data-stu-id="f6661-167">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="f6661-168">Se não houver nenhuma mensagem de convite, o campo será preenchido com a data e a hora da primeira mensagem SIP relevante (até mais, cancelamento, mensagem ou informações).</span><span class="sxs-lookup"><span data-stu-id="f6661-168">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-169"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-169"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-170">int</span><span class="sxs-lookup"><span data-stu-id="f6661-170">int</span></span></p></td>
<td><p><span data-ttu-id="f6661-171">ID de diagnóstico capturada do cabeçalho SIP.</span><span class="sxs-lookup"><span data-stu-id="f6661-171">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-172"><strong>Registrador</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-172"><strong>Registrar</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-173">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f6661-173">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6661-174">FQDN do registrador.</span><span class="sxs-lookup"><span data-stu-id="f6661-174">FQDN of the Registrar.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-175"><strong>Pool</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-175"><strong>Pool</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-176">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f6661-176">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6661-177">FQDN do pool que capturou os dados da sessão.</span><span class="sxs-lookup"><span data-stu-id="f6661-177">FQDN of the pool that captured the data for the session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-178"><strong>EdgeServer</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-178"><strong>EdgeServer</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-179">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f6661-179">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6661-180">FQDN do servidor de borda usado pelo usuário que se cadastrou.</span><span class="sxs-lookup"><span data-stu-id="f6661-180">FQDN of the Edge Server used by the user who registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-181"><strong>IsInternal</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-181"><strong>IsInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-182">bit</span><span class="sxs-lookup"><span data-stu-id="f6661-182">bit</span></span></p></td>
<td><p><span data-ttu-id="f6661-183">Indica se o usuário está conectado à rede interna.</span><span class="sxs-lookup"><span data-stu-id="f6661-183">Indicates whether the user logged on from the internal network.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-184"><strong>IsUserServiceAvailable</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-184"><strong>IsUserServiceAvailable</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-185">bit</span><span class="sxs-lookup"><span data-stu-id="f6661-185">bit</span></span></p></td>
<td><p><span data-ttu-id="f6661-186">Indica se o UserService estava disponível no momento do registro.</span><span class="sxs-lookup"><span data-stu-id="f6661-186">Indicates whether the UserService was available at registration time.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-187"><strong>IsPrimaryRegistrar</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-187"><strong>IsPrimaryRegistrar</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-188">bit</span><span class="sxs-lookup"><span data-stu-id="f6661-188">bit</span></span></p></td>
<td><p><span data-ttu-id="f6661-189">Indica se o registro foi com o registrador principal.</span><span class="sxs-lookup"><span data-stu-id="f6661-189">Indicates whether registration was with the primary Registrar.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-190"><strong>DeviceMacAddress</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-190"><strong>DeviceMacAddress</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-191">bigint</span><span class="sxs-lookup"><span data-stu-id="f6661-191">bigint</span></span></p></td>
<td><p><span data-ttu-id="f6661-192">Endereço MAC do dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="f6661-192">MAC Address of device registered.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="f6661-193"><strong>DeviceManufacturer</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-193"><strong>DeviceManufacturer</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-194">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f6661-194">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6661-195">Fabricante do dispositivo registrado.</span><span class="sxs-lookup"><span data-stu-id="f6661-195">Manufacturer of the device registered.</span></span> <span data-ttu-id="f6661-196">Consulte a <a href="lync-server-2013-manufacturers-table.md">tabela fabricantes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f6661-196">See the <a href="lync-server-2013-manufacturers-table.md">Manufacturers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="f6661-197"><strong>DeviceHardwareVersion</strong></span><span class="sxs-lookup"><span data-stu-id="f6661-197"><strong>DeviceHardwareVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="f6661-198">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="f6661-198">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="f6661-199">Versão de hardware do dispositivo registrada.</span><span class="sxs-lookup"><span data-stu-id="f6661-199">Hardware version of the device registered.</span></span> <span data-ttu-id="f6661-200">Consulte a <a href="lync-server-2013-hardwareversions-table.md">tabela HardwareVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f6661-200">See the <a href="lync-server-2013-hardwareversions-table.md">HardwareVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

