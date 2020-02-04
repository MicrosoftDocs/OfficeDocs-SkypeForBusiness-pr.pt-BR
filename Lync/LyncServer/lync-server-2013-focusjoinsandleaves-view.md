---
title: 'Lync Server 2013: modo de exibição FocusJoinsAndLeaves'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: FocusJoinsAndLeaves view
ms:assetid: 226460ef-766f-4d61-80cb-f332b65a210d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687992(v=OCS.15)
ms:contentKeyID: 49733582
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 9d7cc1da4f5923a7c42e74c9069054863f1d99a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41722401"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="focusjoinsandleaves-view-in-lync-server-2013"></a><span data-ttu-id="ca4ca-102">Exibição FocusJoinsAndLeaves no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="ca4ca-102">FocusJoinsAndLeaves view in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ca4ca-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="ca4ca-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="ca4ca-104">A exibição FocusJoinsAndLeaves armazena informações sobre as informações de ingressar e sair de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-104">The FocusJoinsAndLeaves view stores information about join and leave information for one conference.</span></span> <span data-ttu-id="ca4ca-105">Cada conferência é representada por um registro escrito a cada vez que um usuário entra e sai da conferência.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-105">Each conference is represented in this view by a record written each time a user joins and leaves the conference.</span></span> <span data-ttu-id="ca4ca-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-106">This view was introduced in Microsoft Lync Server 2013.</span></span>


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ca4ca-107">Coluna</span><span class="sxs-lookup"><span data-stu-id="ca4ca-107">Column</span></span></th>
<th><span data-ttu-id="ca4ca-108">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="ca4ca-108">Data Type</span></span></th>
<th><span data-ttu-id="ca4ca-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="ca4ca-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ca4ca-110"><strong>Id_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-111">datetime</span><span class="sxs-lookup"><span data-stu-id="ca4ca-111">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-112">Hora da ocorrência da conferência.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-112">Time of conference instance.</span></span> <span data-ttu-id="ca4ca-113">Usado em conjunto com SessionIdSeq para identificar uma instância de conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-113">Used in conjunction with SessionIdSeq to uniquely identify a conference instance.</span></span> <span data-ttu-id="ca4ca-114">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-114">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca4ca-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-116">int</span><span class="sxs-lookup"><span data-stu-id="ca4ca-116">int</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-117">Número de identificação para identificar a instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-117">ID number to identify the conference instance.</span></span> <span data-ttu-id="ca4ca-118">Usado em conjunto com a Identificação_da_sessãotime para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-118">Used in conjunction with SessionIdTime to uniquely identify a conference instance.</span></span> <span data-ttu-id="ca4ca-119">Consulte a <a href="lync-server-2013-conferences-table.md">tabela conferências no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-119">See the <a href="lync-server-2013-conferences-table.md">Conferences table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca4ca-120"><strong>UserUri</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-120"><strong>UserUri</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-121">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="ca4ca-121">nvarchar(450)</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-122">URI do usuário cujas informações de associação/licença da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-122">URI of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca4ca-123"><strong>UserUriType</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-123"><strong>UserUriType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-124">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca4ca-124">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-125">Tipo de URI do usuário cujas informações de associação/licença de conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-125">Type of URI of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="ca4ca-126">Consulte a <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-126">See the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca4ca-127"><strong>Userlocatário</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-127"><strong>UserTenant</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-128">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca4ca-128">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-129">Locatário do usuário cujas informações de associação/licença da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-129">Tenant of the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="ca4ca-130">Consulte a <a href="lync-server-2013-tenants-table.md">tabela locatários no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-130">See the <a href="lync-server-2013-tenants-table.md">Tenants table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca4ca-131"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-131"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-132">identificador</span><span class="sxs-lookup"><span data-stu-id="ca4ca-132">uniqueidentifier</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-133">Identificador exclusivo do usuário cujas informações de associação/licença da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-133">Unique identifier of the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca4ca-134"><strong>UserClientVersion</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-134"><strong>UserClientVersion</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-135">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca4ca-135">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-136">Versão do cliente usada pelo usuário cujas informações de associação/licença da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-136">Version of client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca4ca-137"><strong>Userclienttype</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-137"><strong>UserClientType</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-138">int</span><span class="sxs-lookup"><span data-stu-id="ca4ca-138">int</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-139">Cliente usado pelo usuário cujas informações de associação/licença da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-139">Client used by the user whose conference join/leave information was captured.</span></span> <span data-ttu-id="ca4ca-140">Consulte a <a href="lync-server-2013-useragentdef-table.md">tabela UserAgentDef no Lync Server 2013</a> para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-140">See <a href="lync-server-2013-useragentdef-table.md">UserAgentDef table in Lync Server 2013</a> for more details.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca4ca-141"><strong>UserClientCategory</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-141"><strong>UserClientCategory</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-142">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="ca4ca-142">nvarchar(64)</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-143">Nome da categoria do cliente usado pelo usuário cujas informações de associação/licença da conferência foram capturadas.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-143">Name of the category of the client used by the user whose conference join/leave information was captured.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca4ca-144"><strong>FocusUserInstance</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-144"><strong>FocusUserInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-145">int</span><span class="sxs-lookup"><span data-stu-id="ca4ca-145">int</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca4ca-146"><strong>IsuserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-146"><strong>IsuserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-147">bit</span><span class="sxs-lookup"><span data-stu-id="ca4ca-147">bit</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-148">Bit que representa se o usuário é um usuário interno ou não.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-148">Bit that represents whether the user is an internal user or not.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca4ca-149"><strong>DialogSessionIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-149"><strong>DialogSessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-150">datetime</span><span class="sxs-lookup"><span data-stu-id="ca4ca-150">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-151">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-151">Time of session request.</span></span> <span data-ttu-id="ca4ca-152">Usado em conjunto com o SessionIdSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-152">Used in conjunction with SessionIdSeq to uniquely identify a session.</span></span> <span data-ttu-id="ca4ca-153">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela de diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-153">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca4ca-154"><strong>DialogSessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-154"><strong>DialogSessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-155">int</span><span class="sxs-lookup"><span data-stu-id="ca4ca-155">int</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-156">Se um usuário estiver conectado em vários computadores ou dispositivos ao mesmo tempo, o UserInstance será usado para identificar exclusivamente a combinação de usuário/dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-156">If a user is logged on at multiple computers or devices at the same time, UserInstance is used to uniquely identify the user/device combination.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca4ca-157"><strong>Caixa de diálogo</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-157"><strong>DialogId</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-158">varchar (775)</span><span class="sxs-lookup"><span data-stu-id="ca4ca-158">varchar(775)</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-159">ID da caixa de diálogo SIP da sessão.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-159">SIP dialog ID of the session.</span></span> <span data-ttu-id="ca4ca-160">O formato é: caixa de diálogo; de-marca; para-marca.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-160">The format is: dialog;from-tag;to-tag.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca4ca-161"><strong>Userjointime</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-161"><strong>UserJoinTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-162">datetime</span><span class="sxs-lookup"><span data-stu-id="ca4ca-162">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-163">Hora em que o usuário ingressou na conferência.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-163">Time that the user joined the conference.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ca4ca-164"><strong>Userleavetime</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-164"><strong>UserLeaveTime</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-165">datetime</span><span class="sxs-lookup"><span data-stu-id="ca4ca-165">datetime</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-166">Tempo em que o usuário saiu da conferência.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-166">Time that the user left the conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ca4ca-167"><strong>Função</strong></span><span class="sxs-lookup"><span data-stu-id="ca4ca-167"><strong>UserRole</strong></span></span></p></td>
<td><p><span data-ttu-id="ca4ca-168">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ca4ca-168">nvarchar(256)</span></span></p></td>
<td><p><span data-ttu-id="ca4ca-169">Função do usuário na conferência, como apresentador ou participante.</span><span class="sxs-lookup"><span data-stu-id="ca4ca-169">User’s role in the conference, such as Presenter or Attendee.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

