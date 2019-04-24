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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212443"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="cb2ce-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="cb2ce-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="cb2ce-104">a tabela Principalmemberdifference inclui as alterações de associação do grupo (tanto adicionadas e removidas membros) que ainda não foram processadas pelas etapas posteriores de sincronização de serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="cb2ce-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="cb2ce-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="cb2ce-105">**Columns**</span></span>

|<span data-ttu-id="cb2ce-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cb2ce-106">**Column**</span></span>|<span data-ttu-id="cb2ce-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cb2ce-107">**Type**</span></span>|<span data-ttu-id="cb2ce-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cb2ce-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="cb2ce-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="cb2ce-109">prinGuid</span></span>  <br/> |<span data-ttu-id="cb2ce-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="cb2ce-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="cb2ce-111">GUID principal do grupo que mudou.</span><span class="sxs-lookup"><span data-stu-id="cb2ce-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="cb2ce-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="cb2ce-112">memberADPath</span></span>  <br/> |<span data-ttu-id="cb2ce-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="cb2ce-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="cb2ce-114">Nome distinto do membro.</span><span class="sxs-lookup"><span data-stu-id="cb2ce-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="cb2ce-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="cb2ce-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="cb2ce-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="cb2ce-116">bit, not null</span></span>  <br/> |<span data-ttu-id="cb2ce-117">False se o membro foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="cb2ce-117">False if the member was added.</span></span> <span data-ttu-id="cb2ce-118">True se o membro foi removido.</span><span class="sxs-lookup"><span data-stu-id="cb2ce-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="cb2ce-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="cb2ce-119">**Key**</span></span>

|<span data-ttu-id="cb2ce-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cb2ce-120">**Column**</span></span>|<span data-ttu-id="cb2ce-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cb2ce-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="cb2ce-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="cb2ce-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="cb2ce-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="cb2ce-123">Primary key.</span></span>  <br/> |
   

