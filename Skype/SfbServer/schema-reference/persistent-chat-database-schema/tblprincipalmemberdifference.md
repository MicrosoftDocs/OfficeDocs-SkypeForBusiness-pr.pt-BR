---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processados pelas etapas de sincronização dos serviços de domínio Active Directory mais recentes.
ms.openlocfilehash: 18d0f3f5c8700db0bb81470f5ee90851e8d277ad
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295297"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="fbf31-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="fbf31-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="fbf31-104">tblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processados pelas etapas de sincronização dos serviços de domínio Active Directory mais recentes.</span><span class="sxs-lookup"><span data-stu-id="fbf31-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="fbf31-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="fbf31-105">**Columns**</span></span>

|<span data-ttu-id="fbf31-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="fbf31-106">**Column**</span></span>|<span data-ttu-id="fbf31-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fbf31-107">**Type**</span></span>|<span data-ttu-id="fbf31-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fbf31-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fbf31-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="fbf31-109">prinGuid</span></span>  <br/> |<span data-ttu-id="fbf31-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="fbf31-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="fbf31-111">O principal GUID do grupo que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="fbf31-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="fbf31-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="fbf31-112">memberADPath</span></span>  <br/> |<span data-ttu-id="fbf31-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="fbf31-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="fbf31-114">Nome diferenciado do membro.</span><span class="sxs-lookup"><span data-stu-id="fbf31-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="fbf31-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="fbf31-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="fbf31-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="fbf31-116">bit, not null</span></span>  <br/> |<span data-ttu-id="fbf31-117">Falso se o membro tiver sido adicionado.</span><span class="sxs-lookup"><span data-stu-id="fbf31-117">False if the member was added.</span></span> <span data-ttu-id="fbf31-118">Verdadeiro se o membro tiver sido removido.</span><span class="sxs-lookup"><span data-stu-id="fbf31-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="fbf31-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="fbf31-119">**Key**</span></span>

|<span data-ttu-id="fbf31-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="fbf31-120">**Column**</span></span>|<span data-ttu-id="fbf31-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fbf31-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fbf31-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="fbf31-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="fbf31-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="fbf31-123">Primary key.</span></span>  <br/> |
   

