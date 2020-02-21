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
ms.openlocfilehash: e103fa03aa747e0c04a680507fe6d57bd6de04d0
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42215577"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="persistent-chat-server-table-details-in-lync-server-2013"></a><span data-ttu-id="02d8c-102">Detalhes da tabela do servidor de chat persistente no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-102">Persistent Chat Server table details in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="02d8c-103">_**Última modificação do tópico:** 2012-06-25_</span><span class="sxs-lookup"><span data-stu-id="02d8c-103">_**Topic Last Modified:** 2012-06-25_</span></span>

<span data-ttu-id="02d8c-104">Os tópicos a seguir detalham as colunas em cada tabela de esquema de banco de dados de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="02d8c-104">The following topics detail the columns in each of the Persistent Chat database schema tables.</span></span>

<div>

## <a name="in-this-section"></a><span data-ttu-id="02d8c-105">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="02d8c-105">In This Section</span></span>

  - [<span data-ttu-id="02d8c-106">tblADCookie no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-106">tblADCookie in Lync Server 2013</span></span>](lync-server-2013-tbladcookie.md)

  - [<span data-ttu-id="02d8c-107">tblPrincipalMemberDifference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-107">tblPrincipalMemberDifference in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmemberdifference.md)

  - [<span data-ttu-id="02d8c-108">tblADUpdates no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-108">tblADUpdates in Lync Server 2013</span></span>](lync-server-2013-tbladupdates.md)

  - [<span data-ttu-id="02d8c-109">tblPrincipalMembers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-109">tblPrincipalMembers in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmembers.md)

  - [<span data-ttu-id="02d8c-110">tblPrincipalMeta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-110">tblPrincipalMeta in Lync Server 2013</span></span>](lync-server-2013-tblprincipalmeta.md)

  - [<span data-ttu-id="02d8c-111">tblSkippedAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-111">tblSkippedAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblskippedaffiliations.md)

  - [<span data-ttu-id="02d8c-112">tblPrincipalType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-112">tblPrincipalType in Lync Server 2013</span></span>](lync-server-2013-tblprincipaltype.md)

  - [<span data-ttu-id="02d8c-113">tblPrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-113">tblPrincipal in Lync Server 2013</span></span>](lync-server-2013-tblprincipal.md)

  - [<span data-ttu-id="02d8c-114">tblPrincipalAffiliations no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-114">tblPrincipalAffiliations in Lync Server 2013</span></span>](lync-server-2013-tblprincipalaffiliations.md)

  - [<span data-ttu-id="02d8c-115">tblNode no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-115">tblNode in Lync Server 2013</span></span>](lync-server-2013-tblnode.md)

  - [<span data-ttu-id="02d8c-116">tblRoleType no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-116">tblRoleType in Lync Server 2013</span></span>](lync-server-2013-tblroletype.md)

  - [<span data-ttu-id="02d8c-117">tblScopePrincipal no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-117">tblScopePrincipal in Lync Server 2013</span></span>](lync-server-2013-tblscopeprincipal.md)

  - [<span data-ttu-id="02d8c-118">tblPrincipalRole no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-118">tblPrincipalRole in Lync Server 2013</span></span>](lync-server-2013-tblprincipalrole.md)

  - [<span data-ttu-id="02d8c-119">tblSiopWhiteList no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-119">tblSiopWhiteList in Lync Server 2013</span></span>](lync-server-2013-tblsiopwhitelist.md)

  - [<span data-ttu-id="02d8c-120">tblEnumAttribute no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-120">tblEnumAttribute in Lync Server 2013</span></span>](lync-server-2013-tblenumattribute.md)

  - [<span data-ttu-id="02d8c-121">tblEnumValue no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-121">tblEnumValue in Lync Server 2013</span></span>](lync-server-2013-tblenumvalue.md)

  - [<span data-ttu-id="02d8c-122">tblPrincipalInvites no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-122">tblPrincipalInvites in Lync Server 2013</span></span>](lync-server-2013-tblprincipalinvites.md)

  - [<span data-ttu-id="02d8c-123">tblChat no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-123">tblChat in Lync Server 2013</span></span>](lync-server-2013-tblchat.md)

  - [<span data-ttu-id="02d8c-124">tblLastInviteId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-124">tblLastInviteId in Lync Server 2013</span></span>](lync-server-2013-tbllastinviteid.md)

  - [<span data-ttu-id="02d8c-125">tblLastChatId no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-125">tblLastChatId in Lync Server 2013</span></span>](lync-server-2013-tbllastchatid.md)

  - [<span data-ttu-id="02d8c-126">tblPreference no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-126">tblPreference in Lync Server 2013</span></span>](lync-server-2013-tblpreference.md)

  - [<span data-ttu-id="02d8c-127">tblFileToken no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-127">tblFileToken in Lync Server 2013</span></span>](lync-server-2013-tblfiletoken.md)

  - [<span data-ttu-id="02d8c-128">tblServerIdentity no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-128">tblServerIdentity in Lync Server 2013</span></span>](lync-server-2013-tblserveridentity.md)

  - [<span data-ttu-id="02d8c-129">tblAdminLock no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-129">tblAdminLock in Lync Server 2013</span></span>](lync-server-2013-tbladminlock.md)

  - [<span data-ttu-id="02d8c-130">tblSystemRevision no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-130">tblSystemRevision in Lync Server 2013</span></span>](lync-server-2013-tblsystemrevision.md)

  - [<span data-ttu-id="02d8c-131">tblActivePeers no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-131">tblActivePeers in Lync Server 2013</span></span>](lync-server-2013-tblactivepeers.md)

  - [<span data-ttu-id="02d8c-132">tblConfig no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-132">tblConfig in Lync Server 2013</span></span>](lync-server-2013-tblconfig.md)

  - [<span data-ttu-id="02d8c-133">tblComplianceData no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-133">tblComplianceData in Lync Server 2013</span></span>](lync-server-2013-tblcompliancedata.md)

  - [<span data-ttu-id="02d8c-134">tblComplianceFanout no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-134">tblComplianceFanout in Lync Server 2013</span></span>](lync-server-2013-tblcompliancefanout.md)

  - [<span data-ttu-id="02d8c-135">tblComplianceParticipant no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-135">tblComplianceParticipant in Lync Server 2013</span></span>](lync-server-2013-tblcomplianceparticipant.md)

  - [<span data-ttu-id="02d8c-136">tblComplianceState no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="02d8c-136">tblComplianceState in Lync Server 2013</span></span>](lync-server-2013-tblcompliancestate.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

