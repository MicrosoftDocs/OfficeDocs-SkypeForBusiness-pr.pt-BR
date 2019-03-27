---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: a tabela Principalmemberdifference inclui as alterações de associação do grupo (tanto adicionadas e removidas membros) que ainda não foram processadas pelas etapas posteriores de sincronização de serviços de domínio do Active Directory.
ms.openlocfilehash: 77b246e96dbd13464b5655fe87d5a10861db30c7
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30885551"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="cbb72-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="cbb72-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="cbb72-104">a tabela Principalmemberdifference inclui as alterações de associação do grupo (tanto adicionadas e removidas membros) que ainda não foram processadas pelas etapas posteriores de sincronização de serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cbb72-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="cbb72-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="cbb72-105">**Columns**</span></span>

|<span data-ttu-id="cbb72-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cbb72-106">**Column**</span></span>|<span data-ttu-id="cbb72-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cbb72-107">**Type**</span></span>|<span data-ttu-id="cbb72-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cbb72-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cbb72-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="cbb72-109">prinGuid</span></span>  <br/> |<span data-ttu-id="cbb72-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="cbb72-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="cbb72-111">GUID principal do grupo que mudou.</span><span class="sxs-lookup"><span data-stu-id="cbb72-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="cbb72-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="cbb72-112">memberADPath</span></span>  <br/> |<span data-ttu-id="cbb72-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cbb72-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="cbb72-114">Nome distinto do membro.</span><span class="sxs-lookup"><span data-stu-id="cbb72-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="cbb72-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="cbb72-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="cbb72-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="cbb72-116">bit, not null</span></span>  <br/> |<span data-ttu-id="cbb72-117">False se o membro foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="cbb72-117">False if the member was added.</span></span> <span data-ttu-id="cbb72-118">True se o membro foi removido.</span><span class="sxs-lookup"><span data-stu-id="cbb72-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="cbb72-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="cbb72-119">**Key**</span></span>

|<span data-ttu-id="cbb72-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cbb72-120">**Column**</span></span>|<span data-ttu-id="cbb72-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cbb72-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cbb72-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="cbb72-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="cbb72-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="cbb72-123">Primary key.</span></span>  <br/> |
   

