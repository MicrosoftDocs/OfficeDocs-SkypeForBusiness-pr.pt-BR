---
title: 'Lync Server 2013: tabela ConferenceSessionDetails'
description: 'Lync Server 2013: tabela ConferenceSessionDetails.'
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
ms.openlocfilehash: 0d101eb1607e366ab814e60acaeee80820fe87c5
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48566777"
---
# <a name="conferencesessiondetails-table-in-lync-server-2013"></a><span data-ttu-id="d1e98-103">Tabela ConferenceSessionDetails no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d1e98-103">ConferenceSessionDetails table in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d1e98-104">_**Última modificação do tópico:** 2012-09-28_</span><span class="sxs-lookup"><span data-stu-id="d1e98-104">_**Topic Last Modified:** 2012-09-28_</span></span>

<span data-ttu-id="d1e98-105">Cada registro representa uma sessão de conferência, que poderia ser a sessão com Foco ou a sessão com um servidor de conferência específico.</span><span class="sxs-lookup"><span data-stu-id="d1e98-105">Each record represents one conference session, which could be either the session with Focus or the session with a specific conferencing server.</span></span>


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="d1e98-106">Coluna</span><span class="sxs-lookup"><span data-stu-id="d1e98-106">Column</span></span></th>
<th><span data-ttu-id="d1e98-107">Tipo de dados</span><span class="sxs-lookup"><span data-stu-id="d1e98-107">Data Type</span></span></th>
<th><span data-ttu-id="d1e98-108">Chave/índice</span><span class="sxs-lookup"><span data-stu-id="d1e98-108">Key/Index</span></span></th>
<th><span data-ttu-id="d1e98-109">Detalhes</span><span class="sxs-lookup"><span data-stu-id="d1e98-109">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-110"><strong>Identificação_da_sessãotime</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-110"><strong>SessionIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-111">Datetime</span><span class="sxs-lookup"><span data-stu-id="d1e98-111">Datetime</span></span></p></td>
<td><p><span data-ttu-id="d1e98-112">Primária, Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-112">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-113">Tempo da solicitação da sessão; usado em conjunto com <strong>SessionIdSeq</strong> para identificar de forma única uma sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="d1e98-113">Time of session request; used in conjunction with <strong>SessionIdSeq</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="d1e98-114">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-114">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-115"><strong>SessionIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-115"><strong>SessionIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-116">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-116">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-117">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="d1e98-117">Primary, Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-118">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="d1e98-118">ID number to identify the session.</span></span> <span data-ttu-id="d1e98-119">Usado em conjunto com a <strong>identificação_da_sessãotime</strong> para identificar exclusivamente uma sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="d1e98-119">Used in conjunction with <strong>SessionIdTime</strong> to uniquely identify a conference session.</span></span> <span data-ttu-id="d1e98-120">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-120">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span> *</p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-121"><strong>ConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-121"><strong>ConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-122">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-122">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-123">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-123">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-124">URI da conferência com foco relacionada a esta sessão.</span><span class="sxs-lookup"><span data-stu-id="d1e98-124">Focus conference URI related to this session.</span></span> <span data-ttu-id="d1e98-125">Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-125">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="d1e98-126">Esta é uma URI de conferência baseada em Foco.</span><span class="sxs-lookup"><span data-stu-id="d1e98-126">This URI is a Focus-based conference URI.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-127"><strong>ConfInstance</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-127"><strong>ConfInstance</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-128">Identificador</span><span class="sxs-lookup"><span data-stu-id="d1e98-128">uniqueIdentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-129">Identificador que diferencia entre instâncias de conferências recorrentes.</span><span class="sxs-lookup"><span data-stu-id="d1e98-129">Identifier that differentiates between instances of recurring conferences.</span></span> <span data-ttu-id="d1e98-130">Cada instância de conferência recorrente possui o mesmo ConferenceURI, mas um valor ConfInstance diferente.</span><span class="sxs-lookup"><span data-stu-id="d1e98-130">Each recurring conference instance has the same ConferenceURI but a different ConfInstance value.</span></span></p>
<p><span data-ttu-id="d1e98-131">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1e98-131">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-132"><strong>McuConferenceUriId</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-132"><strong>McuConferenceUriId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-133">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-133">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-134">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-134">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-135">URI da conferência do servidor de conferências relacionada a esta sessão.</span><span class="sxs-lookup"><span data-stu-id="d1e98-135">Conferencing server conference URI related to this session.</span></span> <span data-ttu-id="d1e98-136">Consulte a <a href="lync-server-2013-conferenceuris-table.md">tabela ConferenceUris no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-136">See the <a href="lync-server-2013-conferenceuris-table.md">ConferenceUris table in Lync Server 2013</a> for more information.</span></span> <span data-ttu-id="d1e98-137">Esta é a URI de conferência baseada em servidor.</span><span class="sxs-lookup"><span data-stu-id="d1e98-137">This URI is the conferencing server-based conference URI.</span></span> <span data-ttu-id="d1e98-138">Para sessões de conferência com foco, esta coluna estará nula.</span><span class="sxs-lookup"><span data-stu-id="d1e98-138">For Focus conference sessions, this column will be null.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-139"><strong>UserId</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-139"><strong>UserId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-140">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-140">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-141">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-141">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-142">ID de um usuário na sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="d1e98-142">ID of one user in the conference session.</span></span> <span data-ttu-id="d1e98-143">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-143">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-144"><strong>Userendpointid</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-144"><strong>UserEndpointId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-145">identificador</span><span class="sxs-lookup"><span data-stu-id="d1e98-145">uniqueidentifier</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-p107">Um GUID para identificar a instância do ponto de extremidade. Por exemplo, se um usuário faz logon em máquinas diferentes com a mesma conta, cada máquina terá um ID de ponto de extremidade diferente.</span><span class="sxs-lookup"><span data-stu-id="d1e98-p107">A GUID to identify the instance of endpoint. For example, if one user logs on to different machines with the same account, then each machine will have a different endpoint ID.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-148"><strong>OnBehalfOfId</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-148"><strong>OnBehalfOfId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-149">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-149">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-150">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-150">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-151">Indica a ID do usuário que está em nome do chamador.</span><span class="sxs-lookup"><span data-stu-id="d1e98-151">Indicates the ID of the user of who the caller is on behalf.</span></span> <span data-ttu-id="d1e98-152">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-152">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-153"><strong>ReferredById</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-153"><strong>ReferredById</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-154">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-154">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-155">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-155">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-156">A ID do usuário a quem se refere a chamada.</span><span class="sxs-lookup"><span data-stu-id="d1e98-156">ID of the user by who the call is referred.</span></span> <span data-ttu-id="d1e98-157">Consulte a <a href="lync-server-2013-users-table.md">tabela Users no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-157">See the <a href="lync-server-2013-users-table.md">Users table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-158"><strong>UserClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-158"><strong>UserClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-159">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-159">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-160">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-160">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-161">Versão do cliente usado pelo usuário da conferência.</span><span class="sxs-lookup"><span data-stu-id="d1e98-161">Client version used by the conference user.</span></span> <span data-ttu-id="d1e98-162">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-162">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-163"><strong>ConfClientVersionId</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-163"><strong>ConfClientVersionId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-164">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-164">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-165">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-165">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-166">Versão do cliente usado pelo servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="d1e98-166">Client version used by the conference server.</span></span> <span data-ttu-id="d1e98-167">Consulte a <a href="lync-server-2013-clientversions-table.md">tabela ClientVersions no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-167">See the <a href="lync-server-2013-clientversions-table.md">ClientVersions table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-168"><strong>ReplaceDialogIdTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-168"><strong>ReplaceDialogIdTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-169">datetime</span><span class="sxs-lookup"><span data-stu-id="d1e98-169">datetime</span></span></p></td>
<td><p><span data-ttu-id="d1e98-170">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-170">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-171">O número de identificação para identificar a caixa de diálogo que foi substituída pela sessão atual.</span><span class="sxs-lookup"><span data-stu-id="d1e98-171">ID number to identify the dialog which was replaced by current session.</span></span> <span data-ttu-id="d1e98-172">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-172">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-173"><strong>ReplaceDialogIdSeq</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-173"><strong>ReplaceDialogIdSeq</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-174">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-174">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-175">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-175">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-176">O número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="d1e98-176">ID number to identify the session.</span></span> <span data-ttu-id="d1e98-177">Usado em conjunto com <strong>ReplacesDialogIdTime </strong> para identificar exclusivamente uma sessão que é substituída por esta sessão.</span><span class="sxs-lookup"><span data-stu-id="d1e98-177">Used in conjunction with <strong>ReplacesDialogIdTime</strong> to uniquely identify a session that is replaced by this session.</span></span> <span data-ttu-id="d1e98-178">Consulte a <a href="lync-server-2013-dialogs-table.md">tabela diálogos no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-178">See the <a href="lync-server-2013-dialogs-table.md">Dialogs table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-179"><strong>IsStartedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-179"><strong>IsStartedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-180">bits</span><span class="sxs-lookup"><span data-stu-id="d1e98-180">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-181">Indica se a sessão é iniciada pelo Servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="d1e98-181">Indicates if the session started by the conferencing Server.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-182"><strong>IsEndedByConfServer</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-182"><strong>IsEndedByConfServer</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-183">bits</span><span class="sxs-lookup"><span data-stu-id="d1e98-183">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-184">Indica se a sessão é encerrada pelo Servidor de conferências.</span><span class="sxs-lookup"><span data-stu-id="d1e98-184">Indicates if the session ended by the conferencing server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-185"><strong>IsUserInternal</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-185"><strong>IsUserInternal</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-186">bits</span><span class="sxs-lookup"><span data-stu-id="d1e98-186">bit</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-187">Se o usuário está conectado de um local interno ou não.</span><span class="sxs-lookup"><span data-stu-id="d1e98-187">Whether user is logged on from internal or not.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-188"><strong>ResponseCode</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-188"><strong>ResponseCode</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-189">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-189">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-190">Código de resposta do Protocolo de Iniciação de Sessão (SIP) para o convite da sessão.</span><span class="sxs-lookup"><span data-stu-id="d1e98-190">Session Initiation Protocol (SIP) response code to the session invitation.</span></span> <span data-ttu-id="d1e98-191">Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d1e98-191">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d1e98-192">Caso não haja nenhuma mensagem CONVIDAR, o campo é preenchidos com a data e horário da primeira mensagem de SIP relevante (ATÉ LOGO, CANCELAR, MENSAGEM ou INFO).</span><span class="sxs-lookup"><span data-stu-id="d1e98-192">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-193"><strong>Diagnosticid</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-193"><strong>DiagnosticId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-194">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-194">int</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-195">ID de diagnóstico capturado do cabeçalho do SIP.</span><span class="sxs-lookup"><span data-stu-id="d1e98-195">Diagnostic ID captured from SIP header.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-196"><strong>ServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-196"><strong>ServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-197">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-197">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-198">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-198">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-199">A ID do servidor Front-End usado para esta sessão.</span><span class="sxs-lookup"><span data-stu-id="d1e98-199">ID of the front-end server used for this session.</span></span> <span data-ttu-id="d1e98-200">Consulte a <a href="lync-server-2013-servers-table.md">tabela de servidores no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-200">See the <a href="lync-server-2013-servers-table.md">Servers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-201"><strong>Poolid</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-201"><strong>PoolId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-202">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-202">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-203">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-203">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-204">A ID do pool no qual a sessão foi capturada.</span><span class="sxs-lookup"><span data-stu-id="d1e98-204">ID of the pool in which the session was captured.</span></span> <span data-ttu-id="d1e98-205">Consulte a <a href="lync-server-2013-pools-table.md">tabela pools no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-205">See the <a href="lync-server-2013-pools-table.md">Pools table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-206"><strong>MediationServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-206"><strong>MediationServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-207">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-207">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-208">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-208">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-209">O servidor de mediação que a chamada está usando.</span><span class="sxs-lookup"><span data-stu-id="d1e98-209">The Mediation Server the call is using.</span></span> <span data-ttu-id="d1e98-210">Consulte a <a href="lync-server-2013-mediationservers-table.md">tabela MediationServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-210">See the <a href="lync-server-2013-mediationservers-table.md">MediationServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-211"><strong>Gatewayid</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-211"><strong>GatewayId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-212">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-212">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-213">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-213">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-214">O gateway que a chamada está usando.</span><span class="sxs-lookup"><span data-stu-id="d1e98-214">The gateway the call is using.</span></span> <span data-ttu-id="d1e98-215">Consulte a <a href="lync-server-2013-gateways-table.md">tabela gateways no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-215">See the <a href="lync-server-2013-gateways-table.md">Gateways table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-216"><strong>EdgeServerId</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-216"><strong>EdgeServerId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-217">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-217">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-218">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-218">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-219">O Servidor de Borda que a chamada está usando.</span><span class="sxs-lookup"><span data-stu-id="d1e98-219">The Edge Server the call is using.</span></span> <span data-ttu-id="d1e98-220">Consulte a <a href="lync-server-2013-edgeservers-table.md">tabela EdgeServers no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-220">See the <a href="lync-server-2013-edgeservers-table.md">EdgeServers table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-221"><strong>ContentTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-221"><strong>ContentTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-222">int</span><span class="sxs-lookup"><span data-stu-id="d1e98-222">int</span></span></p></td>
<td><p><span data-ttu-id="d1e98-223">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-223">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-224">Tipo de conteúdo usado na sessão.</span><span class="sxs-lookup"><span data-stu-id="d1e98-224">Content type used in the session.</span></span> <span data-ttu-id="d1e98-225">Consulte a <a href="lync-server-2013-contenttypes-table.md">tabela ContentTypes no Lync Server 2013</a> para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="d1e98-225">See the <a href="lync-server-2013-contenttypes-table.md">ContentTypes table in Lync Server 2013</a> for more information.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-226"><strong>Invitetime</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-226"><strong>InviteTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-227">datetime</span><span class="sxs-lookup"><span data-stu-id="d1e98-227">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-p121">A hora da primeira solicitação INVITE. Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão. Se não houver mensagem INVITE, então o campo será preenchido com a data e hora da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="d1e98-p121">The time of the first INVITE request. This field is typically populated by data generated from the initial INVITE message in the session. If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-231"><strong>ResponseTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-231"><strong>ResponseTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-232">datetime</span><span class="sxs-lookup"><span data-stu-id="d1e98-232">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-233">A hora da primeira SIP RESPONSE.</span><span class="sxs-lookup"><span data-stu-id="d1e98-233">Time of the first SIP RESPONSE.</span></span> <span data-ttu-id="d1e98-234">Este campo é geralmente preenchido por dados gerados da mensagem INVITE inicial em uma sessão.</span><span class="sxs-lookup"><span data-stu-id="d1e98-234">This field is typically populated by data generated from the initial INVITE message in the session.</span></span> <span data-ttu-id="d1e98-235">Se não houver mensagem INVITE, então o campo será preenchido com a data e hora da primeira mensagem SIP relevante (BYE, CANCEL, MESSAGE ou INFO).</span><span class="sxs-lookup"><span data-stu-id="d1e98-235">If there is no INVITE message then the field is populated with the date and time of the first relevant SIP message (BYE, CANCEL, MESSAGE, or INFO).</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-236"><strong>SessionEndTime</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-236"><strong>SessionEndTime</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-237">datetime</span><span class="sxs-lookup"><span data-stu-id="d1e98-237">datetime</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-238">O horário em que a sessão terminou.</span><span class="sxs-lookup"><span data-stu-id="d1e98-238">The time when the session is ended.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-239"><strong>UriTypeId</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-239"><strong>UriTypeId</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-240">tinyint</span><span class="sxs-lookup"><span data-stu-id="d1e98-240">tinyint</span></span></p></td>
<td><p><span data-ttu-id="d1e98-241">Estrangeira</span><span class="sxs-lookup"><span data-stu-id="d1e98-241">Foreign</span></span></p></td>
<td><p><span data-ttu-id="d1e98-242">Contém o valor do tipo URI MCU da <a href="lync-server-2013-uritypes-table.md">tabela UriTypes no Lync Server 2013</a>.</span><span class="sxs-lookup"><span data-stu-id="d1e98-242">Contains the MCU URI type value from the <a href="lync-server-2013-uritypes-table.md">UriTypes table in Lync Server 2013</a>.</span></span> <span data-ttu-id="d1e98-243">Esse campo é usado para melhorar o desempenho da consulta.</span><span class="sxs-lookup"><span data-stu-id="d1e98-243">This field is used for improving query performance.</span></span></p>
<p><span data-ttu-id="d1e98-244">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="d1e98-244">This field was introduced in Microsoft Lync Server 2013.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="d1e98-245"><strong>Sinalizador</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-245"><strong>UserFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-246">smallint</span><span class="sxs-lookup"><span data-stu-id="d1e98-246">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-p124">Um conjunto de bits que indica os atributos do usuário. As definições de atributo a seguir são listadas:</span><span class="sxs-lookup"><span data-stu-id="d1e98-p124">A bit set that indicates the user attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="d1e98-249">Integrado com telefone de mesa - 1</span><span class="sxs-lookup"><span data-stu-id="d1e98-249">Integrated with desktop phone - 1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="d1e98-250"><strong>CallFlag</strong></span><span class="sxs-lookup"><span data-stu-id="d1e98-250"><strong>CallFlag</strong></span></span></p></td>
<td><p><span data-ttu-id="d1e98-251">smallint</span><span class="sxs-lookup"><span data-stu-id="d1e98-251">smallint</span></span></p></td>
<td></td>
<td><p><span data-ttu-id="d1e98-p125">Um conjunto de bits que indica os atributos da chamada. As definições de atributo a seguir são listadas:</span><span class="sxs-lookup"><span data-stu-id="d1e98-p125">A bit set that indicates the call attributes. The following attribute definitions are listed:</span></span></p>
<ul>
<li><p><span data-ttu-id="d1e98-254">Sessão Repetida - 1</span><span class="sxs-lookup"><span data-stu-id="d1e98-254">Retried Session - 1</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>


<span data-ttu-id="d1e98-255">\* Para a maioria das sessões, SessionIdSeq terá o valor 1.</span><span class="sxs-lookup"><span data-stu-id="d1e98-255">\* For most sessions, SessionIdSeq will have the value of 1.</span></span> <span data-ttu-id="d1e98-256">Se várias sessões iniciam exatamente ao mesmo tempo, o SessionIdSeq para uma delas será 1 e para a outra será 2 e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="d1e98-256">If multiple sessions start at exactly the same time, the SessionIdSeq for one will be 1, for another will be 2, and so on.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

