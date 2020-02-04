---
title: 'Lync Server 2013: modo de exibição McuJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: McuJoinsAndLeaves view
ms:assetid: 6f00b8e7-b8b6-4657-ac5e-d8a571806ae2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688088(v=OCS.15)
ms:contentKeyID: 49733687
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d339df5b3b591cbf67376c36c5e0e4261c390851
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41757735"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="mcujoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="d1717-102">Exibição McuJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1717-102">McuJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1717-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="d1717-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="d1717-104">A exibição McuJoinsAndLeaves armazena informações sobre como os usuários unem e deixam informações para um servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="d1717-104">The McuJoinsAndLeaves view stores information about users join and leave information for one conference server.</span></span> <span data-ttu-id="d1717-105">Cada registro nesse modo de exibição contém detalhes da chamada sobre uma combinação de um servidor de ingresso ou de saída e conferência do usuário.</span><span class="sxs-lookup"><span data-stu-id="d1717-105">Each record in this view contains call details about one combination of a user join or leave and conferencing server.</span></span> <span data-ttu-id="d1717-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1717-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1717-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="d1717-107">Column</span></span></th>
<th><span data-ttu-id="d1717-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="d1717-108">Data Type</span></span></th>
<th><span data-ttu-id="d1717-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d1717-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1717-110"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-111">datetime</span><span class="sxs-lookup"><span data-stu-id="d1717-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1717-112">Hora da ocorrência da conferência.</span><span class="sxs-lookup"><span data-stu-id="d1717-112">Time of conference instance.</span></span> <span data-ttu-id="d1717-113">Usado em conjunto com SessionIdSeq para identificar uma instância de conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="d1717-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="d1717-114">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1717-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1717-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-116">int</span><span class="sxs-lookup"><span data-stu-id="d1717-116">int</span></span></p></td>
<td><p><span data-ttu-id="d1717-117">Número de identificação para identificar a instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="d1717-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="d1717-118">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="d1717-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="d1717-119">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1717-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1717-120"><strong>McuUri</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-120"><strong>McuUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-121">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d1717-121">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1717-122">O URI do servidor de conferência ao qual o usuário se conectou.</span><span class="sxs-lookup"><span data-stu-id="d1717-122">The URI of the conferencing server that the user connected to.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1717-123"><strong>McuUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-123"><strong>McuUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d1717-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1717-125">O URI do servidor de conferência ao qual o usuário se conectou.</span><span class="sxs-lookup"><span data-stu-id="d1717-125">The URI of the conferencing server that the user connected to.</span></span> <span data-ttu-id="d1717-126">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1717-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1717-127"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-127"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-128">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="d1717-128">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="d1717-129">O URI do usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="d1717-129">The URI of the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1717-130"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-130"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-131">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d1717-131">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1717-132">O tipo de URI do usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="d1717-132">The type of URI of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="d1717-133">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1717-133">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1717-134"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-134"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d1717-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1717-136">O locatário do usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="d1717-136">The tenant of the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="d1717-137">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1717-137">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1717-138"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-138"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-139">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d1717-139">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="d1717-140">A versão do cliente usada pelo usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="d1717-140">The version of client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1717-141"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-141"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-142">int</span><span class="sxs-lookup"><span data-stu-id="d1717-142">int</span></span></p></td>
<td><p><span data-ttu-id="d1717-143">O cliente usado pelo usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="d1717-143">The client used by the user whose conferencing server join/leave information was captured.</span></span> <span data-ttu-id="d1717-144">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d1717-144">See the <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1717-145"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-145"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-146">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="d1717-146">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="d1717-147">O nome da categoria do cliente usado pelo usuário cujas informações de associação/licença do servidor de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="d1717-147">The name of the category of the client used by the user whose conferencing server join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1717-148"><strong>McuUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-148"><strong>McuUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-149">int</span><span class="sxs-lookup"><span data-stu-id="d1717-149">int</span></span></p></td>
<td><p><span data-ttu-id="d1717-150">Identifica exclusivamente a combinação de usuário/dispositivo para usuários conectados simultaneamente a vários dispositivos.</span><span class="sxs-lookup"><span data-stu-id="d1717-150">Uniquely identifies the user/device combination for users simultaneously logged on to multiple devices.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1717-151"><strong>IsUserFromPstn</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-151"><strong>IsUserFromPstn</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-152">bit</span><span class="sxs-lookup"><span data-stu-id="d1717-152">bit</span></span></p></td>
<td><p><span data-ttu-id="d1717-153">Bit que representa se o usuário é um usuário interno ou não.</span><span class="sxs-lookup"><span data-stu-id="d1717-153">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1717-154"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-154"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-155">datetime</span><span class="sxs-lookup"><span data-stu-id="d1717-155">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1717-156">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="d1717-156">Time of session request.</span></span> <span data-ttu-id="d1717-157">Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d1717-157">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="d1717-158">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1717-158">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1717-159"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-159"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-160">int</span><span class="sxs-lookup"><span data-stu-id="d1717-160">int</span></span></p></td>
<td><p><span data-ttu-id="d1717-161">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="d1717-161">ID number to identify the session.</span></span> <span data-ttu-id="d1717-162">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d1717-162">Used in conjunction with SessionIdTime to uniquely identify a session.</span></span> <span data-ttu-id="d1717-163">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1717-163">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1717-164"><strong>Caixa de diálogo</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-164"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-165">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="d1717-165">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="d1717-166">ID da caixa de diálogo SIP da sessão.</span><span class="sxs-lookup"><span data-stu-id="d1717-166">SIP dialog ID of the session.</span></span> <span data-ttu-id="d1717-167">O formato é: caixa de diálogo; de-marca; para-marca.</span><span class="sxs-lookup"><span data-stu-id="d1717-167">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1717-168"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-168"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-169">datetime</span><span class="sxs-lookup"><span data-stu-id="d1717-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1717-170">Vez que o usuário ingressou no servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="d1717-170">Time the user joined the conferencing server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1717-171"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="d1717-171"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1717-172">datetime</span><span class="sxs-lookup"><span data-stu-id="d1717-172">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1717-173">Vez que o usuário saiu do servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="d1717-173">Time the user left the conferencing server.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

