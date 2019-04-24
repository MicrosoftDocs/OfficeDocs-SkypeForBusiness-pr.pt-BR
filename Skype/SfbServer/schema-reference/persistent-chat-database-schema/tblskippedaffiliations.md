---
title: tblSkippedAffiliations
ms.reviewer: ''
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
ms.openlocfilehash: 7072cf1d9ebef1040b78bc2fe93ccac02808099a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212604"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="830b1-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="830b1-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="830b1-104">Skippedaffiliations inclui as afiliações que não podiam ser lidas (geralmente devido a erros de acesso do Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="830b1-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="830b1-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="830b1-105">**Columns**</span></span>

|<span data-ttu-id="830b1-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="830b1-106">**Column**</span></span>|<span data-ttu-id="830b1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="830b1-107">**Type**</span></span>|<span data-ttu-id="830b1-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="830b1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="830b1-109">prinID</span><span class="sxs-lookup"><span data-stu-id="830b1-109">prinID</span></span>  <br/> |<span data-ttu-id="830b1-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="830b1-110">int, not null</span></span>  <br/> |<span data-ttu-id="830b1-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="830b1-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="830b1-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="830b1-112">affDescription</span></span>  <br/> |<span data-ttu-id="830b1-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="830b1-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="830b1-114">Uma cadeia de caracteres identificando a afiliação.</span><span class="sxs-lookup"><span data-stu-id="830b1-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="830b1-115">O formato é: guid: _{0}_ uri: _{1}_ gt _ id:_{2}_</span><span class="sxs-lookup"><span data-stu-id="830b1-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="830b1-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="830b1-116">updatedBy</span></span>  <br/> |<span data-ttu-id="830b1-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="830b1-117">int, not null</span></span>  <br/> |<span data-ttu-id="830b1-118">ID da entidade que atualizou esta linha.</span><span class="sxs-lookup"><span data-stu-id="830b1-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="830b1-119">Sempre é 1 (usuário do sistema) porque a sincronização do Active Directory é a única fonte para essas entradas.</span><span class="sxs-lookup"><span data-stu-id="830b1-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="830b1-120">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="830b1-120">**Keys**</span></span>

|<span data-ttu-id="830b1-121">**Coluna (s)**</span><span class="sxs-lookup"><span data-stu-id="830b1-121">**Column(s)**</span></span>|<span data-ttu-id="830b1-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="830b1-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="830b1-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="830b1-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="830b1-124">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="830b1-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="830b1-125">prinID</span><span class="sxs-lookup"><span data-stu-id="830b1-125">prinID</span></span>  <br/> |<span data-ttu-id="830b1-126">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="830b1-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

