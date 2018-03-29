---
title: Skippedaffiliations
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: Skippedaffiliations inclui as afiliações que não podiam ser lidas (geralmente devido a erros de acesso do Active Directory Domain Services).
ms.openlocfilehash: 8809e75f7da7f08c3dee9a846cef332d9cba4371
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="5c016-103">Skippedaffiliations</span><span class="sxs-lookup"><span data-stu-id="5c016-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="5c016-104">Skippedaffiliations inclui as afiliações que não podiam ser lidas (geralmente devido a erros de acesso do Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="5c016-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="5c016-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="5c016-105">**Columns**</span></span>

|<span data-ttu-id="5c016-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="5c016-106">**Column**</span></span>|<span data-ttu-id="5c016-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="5c016-107">**Type**</span></span>|<span data-ttu-id="5c016-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5c016-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5c016-109">prinID</span><span class="sxs-lookup"><span data-stu-id="5c016-109">prinID</span></span>  <br/> |<span data-ttu-id="5c016-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="5c016-110">int, not null</span></span>  <br/> |<span data-ttu-id="5c016-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="5c016-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="5c016-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="5c016-112">affDescription</span></span>  <br/> |<span data-ttu-id="5c016-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="5c016-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="5c016-114">Uma cadeia de caracteres identificando a afiliação.</span><span class="sxs-lookup"><span data-stu-id="5c016-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="5c016-115">O formato é: guid: _{0}_ uri: _{1}_> id: _{2}_</span><span class="sxs-lookup"><span data-stu-id="5c016-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="5c016-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="5c016-116">updatedBy</span></span>  <br/> |<span data-ttu-id="5c016-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="5c016-117">int, not null</span></span>  <br/> |<span data-ttu-id="5c016-118">ID da entidade que atualizou esta linha.</span><span class="sxs-lookup"><span data-stu-id="5c016-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="5c016-119">Sempre é 1 (usuário do sistema) porque a sincronização do Active Directory é a única fonte para essas entradas.</span><span class="sxs-lookup"><span data-stu-id="5c016-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="5c016-120">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="5c016-120">**Keys**</span></span>

|<span data-ttu-id="5c016-121">**Coluna (s)**</span><span class="sxs-lookup"><span data-stu-id="5c016-121">**Column(s)**</span></span>|<span data-ttu-id="5c016-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="5c016-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5c016-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="5c016-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="5c016-124">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="5c016-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="5c016-125">prinID</span><span class="sxs-lookup"><span data-stu-id="5c016-125">prinID</span></span>  <br/> |<span data-ttu-id="5c016-126">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="5c016-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

