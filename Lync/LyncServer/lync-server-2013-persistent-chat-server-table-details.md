---
title: 'Lync Server 2013: detalhes da tabela do servidor de chat persistente'
description: 'Lync Server 2013: detalhes da tabela do servidor de chat persistente.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Persistent Chat Server table details
ms:assetid: c22d4a76-da50-49de-9038-e0ed7b8e1b58
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615034(v=OCS.15)
ms:contentKeyID: 48185323
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6a27feaaccf861d537127f06920cf903be5ae000
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545127"
---
# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="e1f17-103">Detalhes da tabela do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-103">Persistent Chat Server table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e1f17-104">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="e1f17-104">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="e1f17-105">Os tópicos a seguir detalham as colunas em cada tabela de esquema de banco de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="e1f17-105">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="e1f17-106">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="e1f17-106">In This Section</span></span>

  - [<span data-ttu-id="e1f17-107">tblADCookie no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-107">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="e1f17-108">tblPrincipalMemberDifference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-108">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="e1f17-109">tblADUpdates no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-109">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="e1f17-110">tblPrincipalMembers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-110">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="e1f17-111">tblPrincipalMeta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-111">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="e1f17-112">tblSkippedAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-112">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="e1f17-113">tblPrincipalType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-113">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="e1f17-114">tblPrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-114">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="e1f17-115">tblPrincipalAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-115">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="e1f17-116">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-116">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="e1f17-117">tblRoleType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-117">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="e1f17-118">tblScopePrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-118">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="e1f17-119">tblPrincipalRole no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-119">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="e1f17-120">tblSiopWhiteList no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-120">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="e1f17-121">tblEnumAttribute no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-121">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="e1f17-122">tblEnumValue no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-122">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="e1f17-123">tblPrincipalInvites no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-123">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="e1f17-124">tblChat no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-124">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="e1f17-125">tblLastInviteId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-125">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="e1f17-126">tblLastChatId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-126">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="e1f17-127">tblPreference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-127">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="e1f17-128">tblFileToken no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-128">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="e1f17-129">tblServerIdentity no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-129">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="e1f17-130">tblAdminLock no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-130">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="e1f17-131">tblSystemRevision no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-131">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="e1f17-132">tblActivePeers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-132">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="e1f17-133">tblConfig no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-133">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="e1f17-134">tblComplianceData no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-134">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="e1f17-135">tblComplianceFanout no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-135">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="e1f17-136">tblComplianceParticipant no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-136">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="e1f17-137">tblComplianceState no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e1f17-137">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

