---
title: 'Lync Server 2013: tabela ConferenceSessionDetails'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: ConferenceSessionDetails table
ms:assetid: 9eae6a54-69fd-4966-aa17-7ecee1297ad8
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412741(v=OCS.15)
ms:contentKeyID: 48184925
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3e991f6240d9c21815299a3ef169c5824cf5ef3b
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42213137"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="efb4d-102">Tabela ConferenceSessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efb4d-102">ConferenceSessionDetails table in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="efb4d-103">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="efb4d-103">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="efb4d-104">Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico.</span><span class="sxs-lookup"><span data-stu-id="efb4d-104">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="efb4d-105">Coluna</span><span class="sxs-lookup"><span data-stu-id="efb4d-105">Column</span></span></th>
<th><span data-ttu-id="efb4d-106">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="efb4d-106">Data Type</span></span></th>
<th><span data-ttu-id="efb4d-107">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="efb4d-107">Key/Index</span></span></th>
<th><span data-ttu-id="efb4d-108">Detalhes</span><span class="sxs-lookup"><span data-stu-id="efb4d-108">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-109"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-109"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-110">Datetime</span><span class="sxs-lookup"><span data-stu-id="efb4d-110">Datetime</span></span></p></td>
<td><p><span data-ttu-id="efb4d-111">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="efb4d-111">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-112">Tempo da solicitação da sessão; usado em conjunto com <strong>SessionIdSeq</strong> para identificar de forma única uma sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="efb4d-112">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="efb4d-113">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-113">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-114"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-114"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-115">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-115">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-116">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="efb4d-116">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-117">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="efb4d-117">ID number to identify the session.</span></span> <span data-ttu-id="efb4d-118">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="efb4d-118">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="efb4d-119">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-119">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-120"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-120"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-121">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-121">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-122">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-122">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-123">URI da conferência com foco relacionada a esta sessão.</span><span class="sxs-lookup"><span data-stu-id="efb4d-123">Focus conference URI related to this session.</span></span> <span data-ttu-id="efb4d-124">Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-124">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="efb4d-125">Esta é uma URI de conferência baseada em Foco.</span><span class="sxs-lookup"><span data-stu-id="efb4d-125">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-126"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-126"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-127">Identificador</span><span class="sxs-lookup"><span data-stu-id="efb4d-127">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-128">Identificador que diferencia entre instâncias de conferências recorrentes.</span><span class="sxs-lookup"><span data-stu-id="efb4d-128">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="efb4d-129">Cada instância de conferência recorrente possui o mesmo ConferenceURI, mas um valor ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="efb4d-129">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="efb4d-130">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="efb4d-130">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-131"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-131"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-132">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-132">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-133">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-133">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-134">URI da conferência do servidor de conferências relacionada a esta sessão.</span><span class="sxs-lookup"><span data-stu-id="efb4d-134">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="efb4d-135">Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-135">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="efb4d-136">Esta é a URI de conferência baseada em servidor.</span><span class="sxs-lookup"><span data-stu-id="efb4d-136">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="efb4d-137">Para sessões de conferência com foco, esta coluna estará nula.</span><span class="sxs-lookup"><span data-stu-id="efb4d-137">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-138"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-138"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-139">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-139">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-140">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-140">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-141">ID de um usuário na sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="efb4d-141">ID of one user in the conference session.</span></span> <span data-ttu-id="efb4d-142">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-142">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-143"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-143"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-144">identificador</span><span class="sxs-lookup"><span data-stu-id="efb4d-144">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-p107">Um GUID para identificar a instância do ponto de extremidade. Por exemplo, se um usuário faz logon em máquinas diferentes com a mesma conta, cada máquina terá um ID de ponto de extremidade diferente.</span><span class="sxs-lookup"><span data-stu-id="efb4d-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-147"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-147"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-148">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-148">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-149">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-149">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-150">Indica a ID do usuário que está em nome do chamador.</span><span class="sxs-lookup"><span data-stu-id="efb4d-150">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="efb4d-151">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-151">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-152"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-152"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-153">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-153">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-154">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-154">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-155">A ID do usuário a quem se refere a chamada.</span><span class="sxs-lookup"><span data-stu-id="efb4d-155">ID of the user by who the call is referred.</span></span> <span data-ttu-id="efb4d-156">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-156">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-157"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-157"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-158">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-158">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-159">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-159">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-160">Versão do cliente usado pelo usuário da conferência.</span><span class="sxs-lookup"><span data-stu-id="efb4d-160">Client version used by the conference user.</span></span> <span data-ttu-id="efb4d-161">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-161">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-162"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-162"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-163">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-163">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-164">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-164">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-165">Versão do cliente usado pelo servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="efb4d-165">Client version used by the conference server.</span></span> <span data-ttu-id="efb4d-166">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-166">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-167"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-167"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-168">datetime</span><span class="sxs-lookup"><span data-stu-id="efb4d-168">datetime</span></span></p></td>
<td><p><span data-ttu-id="efb4d-169">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-169">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-170">O número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual.</span><span class="sxs-lookup"><span data-stu-id="efb4d-170">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="efb4d-171">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-171">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-172"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-172"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-173">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-173">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-174">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-174">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-175">O número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="efb4d-175">ID number to identify the session.</span></span> <span data-ttu-id="efb4d-176">Usado em conjunto com <strong>ReplacesDialogIdTime </strong> para identificar exclusivamente uma sessão que é substituída por esta sessão.</span><span class="sxs-lookup"><span data-stu-id="efb4d-176">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="efb4d-177">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-177">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-178"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-178"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-179">bits</span><span class="sxs-lookup"><span data-stu-id="efb4d-179">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-180">Indica se a sessão é iniciada pelo Servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="efb4d-180">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-181"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-181"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-182">bits</span><span class="sxs-lookup"><span data-stu-id="efb4d-182">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-183">Indica se a sessão é encerrada pelo Servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="efb4d-183">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-184"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-184"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-185">bits</span><span class="sxs-lookup"><span data-stu-id="efb4d-185">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-186">Se o usuário está conectado de um local interno ou não.</span><span class="sxs-lookup"><span data-stu-id="efb4d-186">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-187"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-187"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-188">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-188">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-189">Código de resposta do Protocolo de Iniciação de Sessão (SIP) para o convite da sessão.</span><span class="sxs-lookup"><span data-stu-id="efb4d-189">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="efb4d-190">Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="efb4d-190">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="efb4d-191">Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="efb4d-191">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-192"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-192"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-193">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-193">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-194">ID de diagnóstico capturado do cabeçalho do SIP.</span><span class="sxs-lookup"><span data-stu-id="efb4d-194">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-195"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-195"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-196">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-196">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-197">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-197">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-198">A ID do servidor Front-End usado para esta sessão.</span><span class="sxs-lookup"><span data-stu-id="efb4d-198">ID of the front-end server used for this session.</span></span> <span data-ttu-id="efb4d-199">Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-199">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-200"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-200"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-201">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-201">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-202">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-202">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-203">A ID do pool no qual a sessão foi capturada.</span><span class="sxs-lookup"><span data-stu-id="efb4d-203">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="efb4d-204">Consulte a <a href="lync-server-2013-pools-table.md">tabela pools no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-204">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-205"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-205"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-206">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-206">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-207">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-207">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-208">O servidor de mediação que a chamada está usando.</span><span class="sxs-lookup"><span data-stu-id="efb4d-208">The Mediation Server the call is using.</span></span> <span data-ttu-id="efb4d-209">Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-209">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-210"><strong>Gatewayid</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-210"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-211">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-211">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-212">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-212">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-213">O gateway que a chamada está usando.</span><span class="sxs-lookup"><span data-stu-id="efb4d-213">The gateway the call is using.</span></span> <span data-ttu-id="efb4d-214">Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-214">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-215"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-215"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-216">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-216">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-217">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-217">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-218">O Servidor de Borda que a chamada está usando.</span><span class="sxs-lookup"><span data-stu-id="efb4d-218">The Edge Server the call is using.</span></span> <span data-ttu-id="efb4d-219">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-219">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-220"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-220"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-221">int</span><span class="sxs-lookup"><span data-stu-id="efb4d-221">int</span></span></p></td>
<td><p><span data-ttu-id="efb4d-222">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-222">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-223">Tipo de conteúdo usado na sessão.</span><span class="sxs-lookup"><span data-stu-id="efb4d-223">Content type used in the session.</span></span> <span data-ttu-id="efb4d-224">Consulte a <a href="lync-server-2013-contenttypes-table.md">tabela ContentTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="efb4d-224">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-225"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-225"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-226">datetime</span><span class="sxs-lookup"><span data-stu-id="efb4d-226">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-p121">A hora da primeira solicitação INVITE. Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão. Se não houver mensagem INVITE, então o campo será preenchido com a data e hora da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="efb4d-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-230"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-230"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-231">datetime</span><span class="sxs-lookup"><span data-stu-id="efb4d-231">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-232">A hora da primeira SIP RESPONSE.</span><span class="sxs-lookup"><span data-stu-id="efb4d-232">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="efb4d-233">Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="efb4d-233">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="efb4d-234">Se não houver mensagem INVITE, então o campo será preenchido com a data e hora da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="efb4d-234">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-235"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-235"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-236">datetime</span><span class="sxs-lookup"><span data-stu-id="efb4d-236">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-237">O horário em que a sessão terminou.</span><span class="sxs-lookup"><span data-stu-id="efb4d-237">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-238"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-238"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-239">tinyint</span><span class="sxs-lookup"><span data-stu-id="efb4d-239">tinyint</span></span></p></td>
<td><p><span data-ttu-id="efb4d-240">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="efb4d-240">Foreign</span></span></p></td>
<td><p><span data-ttu-id="efb4d-241">Contém o valor do tipo URI MCU da <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="efb4d-241">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="efb4d-242">Esse campo é usado para melhorar o desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="efb4d-242">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="efb4d-243">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="efb4d-243">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="efb4d-244"><strong>Sinalizador</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-244"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-245">smallint</span><span class="sxs-lookup"><span data-stu-id="efb4d-245">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-p124">Um conjunto de bits que indica os atributos do usuário. As definições de atributo a seguir são listadas:</span><span class="sxs-lookup"><span data-stu-id="efb4d-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="efb4d-248">Integrado com telefone de mesa - 1</span><span class="sxs-lookup"><span data-stu-id="efb4d-248">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="efb4d-249"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="efb4d-249"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="efb4d-250">smallint</span><span class="sxs-lookup"><span data-stu-id="efb4d-250">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="efb4d-p125">Um conjunto de bits que indica os atributos da chamada. As definições de atributo a seguir são listadas:</span><span class="sxs-lookup"><span data-stu-id="efb4d-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="efb4d-253">Sessão Repetida - 1</span><span class="sxs-lookup"><span data-stu-id="efb4d-253">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="efb4d-254">\*Para a maioria das sessões, SessionIdSeq terá o valor 1.</span><span class="sxs-lookup"><span data-stu-id="efb4d-254">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="efb4d-255">Se várias sessões iniciam exatamente ao mesmo tempo, o SessionIdSeq para uma delas será 1 e para a outra será 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="efb4d-255">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

