---
title: Principalmemberdifference
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
ms.openlocfilehash: 603c8345f2adc2ba7d5eb04835218fd3e83d8ed4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="04ba6-103">Principalmemberdifference</span><span class="sxs-lookup"><span data-stu-id="04ba6-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="04ba6-104">a tabela Principalmemberdifference inclui as alterações de associação do grupo (tanto adicionadas e removidas membros) que ainda não foram processadas pelas etapas posteriores de sincronização de serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="04ba6-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="04ba6-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="04ba6-105">**Columns**</span></span>

|<span data-ttu-id="04ba6-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="04ba6-106">**Column**</span></span>|<span data-ttu-id="04ba6-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="04ba6-107">**Type**</span></span>|<span data-ttu-id="04ba6-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="04ba6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="04ba6-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="04ba6-109">prinGuid</span></span>  <br/> |<span data-ttu-id="04ba6-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="04ba6-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="04ba6-111">GUID principal do grupo que mudou.</span><span class="sxs-lookup"><span data-stu-id="04ba6-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="04ba6-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="04ba6-112">memberADPath</span></span>  <br/> |<span data-ttu-id="04ba6-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="04ba6-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="04ba6-114">Nome distinto do membro.</span><span class="sxs-lookup"><span data-stu-id="04ba6-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="04ba6-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="04ba6-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="04ba6-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="04ba6-116">bit, not null</span></span>  <br/> |<span data-ttu-id="04ba6-117">False se o membro foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="04ba6-117">False if the member was added.</span></span> <span data-ttu-id="04ba6-118">True se o membro foi removido.</span><span class="sxs-lookup"><span data-stu-id="04ba6-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="04ba6-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="04ba6-119">**Key**</span></span>

|<span data-ttu-id="04ba6-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="04ba6-120">**Column**</span></span>|<span data-ttu-id="04ba6-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="04ba6-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="04ba6-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="04ba6-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="04ba6-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="04ba6-123">Primary key.</span></span>  <br/> |
   

