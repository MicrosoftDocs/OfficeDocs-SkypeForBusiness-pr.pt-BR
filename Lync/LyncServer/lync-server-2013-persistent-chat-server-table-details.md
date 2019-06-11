---
title: 'Lync Server 2013: Detalhes da tabela do Servidor de Chat Persistente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Persistent Chat Server table details
ms:assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615034(v=OCS.15)
ms:contentKeyID: 48185323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 81f23e3ea5642341248be304612d71f12148865c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825181"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="c3cb5-102">Detalhes da tabela do Servidor de Chat Persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-102">Persistent Chat Server table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="c3cb5-103">_**Tópico da última modificação:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="c3cb5-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="c3cb5-104">Os tópicos a seguir detalham as colunas em cada uma das tabelas de esquema de banco de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="c3cb5-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="c3cb5-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="c3cb5-105">In This Section</span></span>

  - [<span data-ttu-id="c3cb5-106">tblADCookie no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="c3cb5-107">tblPrincipalMemberDifference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="c3cb5-108">tblADUpdates no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="c3cb5-109">tblPrincipalMembers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="c3cb5-110">tblPrincipalMeta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="c3cb5-111">tblSkippedAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="c3cb5-112">tblPrincipalType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="c3cb5-113">tblPrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="c3cb5-114">tblPrincipalAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="c3cb5-115">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="c3cb5-116">tblRoleType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="c3cb5-117">tblScopePrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="c3cb5-118">tblPrincipalRole no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="c3cb5-119">tblSiopWhiteList no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="c3cb5-120">tblEnumAttribute no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="c3cb5-121">tblEnumValue no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="c3cb5-122">tblPrincipalInvites no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="c3cb5-123">tblChat no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="c3cb5-124">tblLastInviteId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="c3cb5-125">tblLastChatId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="c3cb5-126">tblPreference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="c3cb5-127">tblFileToken no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="c3cb5-128">tblServerIdentity no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="c3cb5-129">tblAdminLock no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="c3cb5-130">tblSystemRevision no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="c3cb5-131">tblActivePeers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="c3cb5-132">tblConfig no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="c3cb5-133">tblComplianceData no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="c3cb5-134">tblComplianceFanout no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="c3cb5-135">tblComplianceParticipant no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="c3cb5-136">tblComplianceState no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="c3cb5-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

