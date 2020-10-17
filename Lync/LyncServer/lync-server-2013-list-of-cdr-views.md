---
title: 'Lync Server 2013: lista de exibições de CDR'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: List of CDR views
ms:assetid: 2f72aead-d1da-4185-b75c-f6c31d76a6b3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688009(v=OCS.15)
ms:contentKeyID: 49733598
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 37f41be7781f3cdce6b458b1eeaeb5cb8431b8d0
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48513958"
---
# <a name="list-of-cdr-views-in-lync-server-2013"></a><span data-ttu-id="0b987-102">Lista de exibições de CDR no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="0b987-102">List of CDR views in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0b987-103">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="0b987-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="0b987-104">As exibições oferecem uma forma fácil de acessar informações sobre os cenários mais comuns usados para retornar dados do banco de dados CDR.</span><span class="sxs-lookup"><span data-stu-id="0b987-104">Views provide an easy way to access information about the most common scenarios used for returning data from the CDR database.</span></span> <span data-ttu-id="0b987-105">É recomendável que você use modos de exibição para criar relatórios personalizados, em vez de usar as tabelas de banco de dados CDR reais; Isso ocorre porque as exibições do banco de dados são mais prováveis de manter a compatibilidade com versões anteriores do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b987-105">It is recommended that you use views for building custom reports instead of using the actual CDR database tables ; that’s because the database views are more likely to maintain backwards compatibility with future releases of Lync Server.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="0b987-106">Nome de exibição</span><span class="sxs-lookup"><span data-stu-id="0b987-106">View Name</span></span></th>
<th><span data-ttu-id="0b987-107">Descrição</span><span class="sxs-lookup"><span data-stu-id="0b987-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="0b987-108"><a href="lync-server-2013-clientversions-view.md">Exibição ClientVersions no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-108"><a href="lync-server-2013-clientversions-view.md">ClientVersions view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-109">Retorna informações sobre o software/dispositivos clientes usados em uma sessão de comunicação.</span><span class="sxs-lookup"><span data-stu-id="0b987-109">Returns information about the client software/devices used in a communication session.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b987-110"><a href="lync-server-2013-conferencemessagecount-view.md">Exibição ConferenceMessageCount no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-110"><a href="lync-server-2013-conferencemessagecount-view.md">ConferenceMessageCount view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-111">Retorna informações sobre o número de mensagens enviadas pelos usuários em uma conferência.</span><span class="sxs-lookup"><span data-stu-id="0b987-111">Returns information about the number of messages sent by users in a conference.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b987-112"><a href="lync-server-2013-conferences-view.md">Exibição de conferências no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-112"><a href="lync-server-2013-conferences-view.md">Conferences view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-113">Retorna informações de conferência, incluindo hora inicial, final e organizador da conferência.</span><span class="sxs-lookup"><span data-stu-id="0b987-113">Returns conference information, including start time, end time, and conference organizer.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b987-114"><a href="lync-server-2013-conferencesessiondetails-view.md">Exibição ConferenceSessionDetails no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-114"><a href="lync-server-2013-conferencesessiondetails-view.md">ConferenceSessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-115">Retorna detalhes da sessão para todas as sessões de conferência, incluindo hora inicial e final, IDs do usuário, códigos de resposta e IDs de diagnóstico.</span><span class="sxs-lookup"><span data-stu-id="0b987-115">Returns session details for all conferencing sessions, including start and end time, user IDs, response codes, and diagnostic IDs.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b987-116"><a href="lync-server-2013-conferenceuris-view.md">Exibição ConferenceUris no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-116"><a href="lync-server-2013-conferenceuris-view.md">ConferenceUris view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-117">Retorna informações sobre as URIs de conferência usadas em uma conferência</span><span class="sxs-lookup"><span data-stu-id="0b987-117">Returns information about conference URIs used in a conference</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b987-118"><a href="lync-server-2013-errorreport-view.md">Exibição ErrorReport no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-118"><a href="lync-server-2013-errorreport-view.md">ErrorReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-119">Retorna informações sobre erros ocorridos durante uma sessão.</span><span class="sxs-lookup"><span data-stu-id="0b987-119">Returns information about errors that occurred during a session.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b987-120"><a href="lync-server-2013-filetransfers-view.md">Modo de transferência de filetransfers no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-120"><a href="lync-server-2013-filetransfers-view.md">FileTransfers view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-121">Retorna informações sobre sessões de transferência de arquivos, incluindo o nome do arquivo e se a transferência foi aceitada, rejeitada ou cancelada.</span><span class="sxs-lookup"><span data-stu-id="0b987-121">Returns information about file transfer sessions, including the file name and whether the transfer was accepted, rejected, or cancelled.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b987-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">Exibição FocusJoinsAndLeaves no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-122"><a href="lync-server-2013-focusjoinsandleaves-view.md">FocusJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-123">Retorna informações sobre as atividades de participação e saída da conferência.</span><span class="sxs-lookup"><span data-stu-id="0b987-123">Returns information about conference join and leave activities.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b987-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">Exibição McuJoinsAndLeaves no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-124"><a href="lync-server-2013-mcujoinsandleaves-view.md">McuJoinsAndLeaves view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-125">Retorna informação combinada sobre as atividades de participação e saída da conferência (cada participação da conferência é emparelhada com a saída correspondente).</span><span class="sxs-lookup"><span data-stu-id="0b987-125">Returns combined information about conference join and leave activities (each conference join is paired with the corresponding conference leave).</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b987-126"><a href="lync-server-2013-mcus-view.md">Exibição MCUs no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-126"><a href="lync-server-2013-mcus-view.md">Mcus view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-127">Retorna informações sobre os servidores de Conferência.</span><span class="sxs-lookup"><span data-stu-id="0b987-127">Returns information about Conferencing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b987-128"><a href="lync-server-2013-media-view.md">Exibição de mídia no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-128"><a href="lync-server-2013-media-view.md">Media view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-129">Retorna informações sobre os tipos de mídia usados nas sessões de comunicação ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="0b987-129">Returns information about the types of media used in peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b987-130"><a href="lync-server-2013-progressreport-view.md">Exibição ProgressReport no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-130"><a href="lync-server-2013-progressreport-view.md">ProgressReport view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-131">Retorna informações sobre as sessões concluídas.</span><span class="sxs-lookup"><span data-stu-id="0b987-131">Returns information about completed sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b987-132"><a href="lync-server-2013-registration-view.md">Exibição de registro no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-132"><a href="lync-server-2013-registration-view.md">Registration view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-133">Retorna informações sobre registros com o Lync Server.</span><span class="sxs-lookup"><span data-stu-id="0b987-133">Returns information about registrations with Lync Server.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b987-134"><a href="lync-server-2013-sessiondetails-view.md">Exibição SessionDetails no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-134"><a href="lync-server-2013-sessiondetails-view.md">SessionDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-135">Retorna informações sobre as sessões ponto a ponto, incluindo chamadas de telefone VoIP-VoIP, sessões de IM de terceiros ou outras sessões de comunicação ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="0b987-135">Returns information about peer-to-peer sessions, including VoIP-VoIP phone calls, two-party IM sessions, or other peer-to-peer communication sessions.</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="0b987-136"><a href="lync-server-2013-user-view.md">Exibição de usuário no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-136"><a href="lync-server-2013-user-view.md">User view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-137">Retorna informações sobre os usuários que participaram das sessões de comunicação.</span><span class="sxs-lookup"><span data-stu-id="0b987-137">Returns information about the users who have participated in communication sessions.</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="0b987-138"><a href="lync-server-2013-voipdetails-view.md">Exibição VoIPDetails no Lync Server 2013</a></span><span class="sxs-lookup"><span data-stu-id="0b987-138"><a href="lync-server-2013-voipdetails-view.md">VoIPDetails view in Lync Server 2013</a></span></span></p></td>
<td><p><span data-ttu-id="0b987-139">Retorna informações para sessões ponto a ponto envolvendo pelo menos um usuário VoIP (Voz por IP).</span><span class="sxs-lookup"><span data-stu-id="0b987-139">Returns information for peer-to-peer sessions involving at least one VoIP (Voice over IO) user.</span></span></p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

