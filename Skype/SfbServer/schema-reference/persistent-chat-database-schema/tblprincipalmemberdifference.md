---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: a tabela Principalmemberdifference inclui as alterações de associação do grupo (tanto adicionadas e removidas membros) que ainda não foram processadas pelas etapas posteriores de sincronização de serviços de domínio do Active Directory.
ms.openlocfilehash: 4445bc6a4b83053d7d9244fc20d0a7a8cbd01b26
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902233"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="b5104-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="b5104-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="b5104-104">a tabela Principalmemberdifference inclui as alterações de associação do grupo (tanto adicionadas e removidas membros) que ainda não foram processadas pelas etapas posteriores de sincronização de serviços de domínio do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="b5104-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="b5104-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="b5104-105">**Columns**</span></span>

|<span data-ttu-id="b5104-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b5104-106">**Column**</span></span>|<span data-ttu-id="b5104-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b5104-107">**Type**</span></span>|<span data-ttu-id="b5104-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b5104-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b5104-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="b5104-109">prinGuid</span></span>  <br/> |<span data-ttu-id="b5104-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="b5104-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="b5104-111">GUID principal do grupo que mudou.</span><span class="sxs-lookup"><span data-stu-id="b5104-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="b5104-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="b5104-112">memberADPath</span></span>  <br/> |<span data-ttu-id="b5104-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b5104-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="b5104-114">Nome distinto do membro.</span><span class="sxs-lookup"><span data-stu-id="b5104-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="b5104-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="b5104-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="b5104-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="b5104-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b5104-117">False se o membro foi adicionado.</span><span class="sxs-lookup"><span data-stu-id="b5104-117">False if the member was added.</span></span> <span data-ttu-id="b5104-118">True se o membro foi removido.</span><span class="sxs-lookup"><span data-stu-id="b5104-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="b5104-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b5104-119">**Key**</span></span>

|<span data-ttu-id="b5104-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b5104-120">**Column**</span></span>|<span data-ttu-id="b5104-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b5104-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b5104-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="b5104-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="b5104-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="b5104-123">Primary key.</span></span>  <br/> |
   

