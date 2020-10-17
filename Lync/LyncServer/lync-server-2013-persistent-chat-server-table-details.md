---
title: 'Lync Server 2013: detalhes da tabela do servidor de chat persistente'
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
ms.openlocfilehash: cde75ceb141a81af1b6a093742edd23b4adf1716
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48524218"
---
# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="2eeb9-102">Detalhes da tabela do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-102">Persistent Chat Server table details in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="2eeb9-103">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="2eeb9-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="2eeb9-104">Os tópicos a seguir detalham as colunas em cada tabela de esquema de banco de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="2eeb9-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="2eeb9-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="2eeb9-105">In This Section</span></span>

  - [<span data-ttu-id="2eeb9-106">tblADCookie no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="2eeb9-107">tblPrincipalMemberDifference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="2eeb9-108">tblADUpdates no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="2eeb9-109">tblPrincipalMembers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="2eeb9-110">tblPrincipalMeta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="2eeb9-111">tblSkippedAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="2eeb9-112">tblPrincipalType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="2eeb9-113">tblPrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="2eeb9-114">tblPrincipalAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="2eeb9-115">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="2eeb9-116">tblRoleType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="2eeb9-117">tblScopePrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="2eeb9-118">tblPrincipalRole no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="2eeb9-119">tblSiopWhiteList no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="2eeb9-120">tblEnumAttribute no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="2eeb9-121">tblEnumValue no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="2eeb9-122">tblPrincipalInvites no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="2eeb9-123">tblChat no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="2eeb9-124">tblLastInviteId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="2eeb9-125">tblLastChatId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="2eeb9-126">tblPreference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="2eeb9-127">tblFileToken no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="2eeb9-128">tblServerIdentity no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="2eeb9-129">tblAdminLock no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="2eeb9-130">tblSystemRevision no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="2eeb9-131">tblActivePeers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="2eeb9-132">tblConfig no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="2eeb9-133">tblComplianceData no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="2eeb9-134">tblComplianceFanout no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="2eeb9-135">tblComplianceParticipant no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="2eeb9-136">tblComplianceState no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="2eeb9-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

