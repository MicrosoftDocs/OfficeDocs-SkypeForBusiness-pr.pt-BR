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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874784"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="babf2-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="babf2-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="babf2-104">Skippedaffiliations inclui as afiliações que não podiam ser lidas (geralmente devido a erros de acesso do Active Directory Domain Services).</span><span class="sxs-lookup"><span data-stu-id="babf2-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="babf2-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="babf2-105">**Columns**</span></span>

|<span data-ttu-id="babf2-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="babf2-106">**Column**</span></span>|<span data-ttu-id="babf2-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="babf2-107">**Type**</span></span>|<span data-ttu-id="babf2-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="babf2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="babf2-109">prinID</span><span class="sxs-lookup"><span data-stu-id="babf2-109">prinID</span></span>  <br/> |<span data-ttu-id="babf2-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="babf2-110">int, not null</span></span>  <br/> |<span data-ttu-id="babf2-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="babf2-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="babf2-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="babf2-112">affDescription</span></span>  <br/> |<span data-ttu-id="babf2-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="babf2-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="babf2-114">Uma cadeia de caracteres identificando a afiliação.</span><span class="sxs-lookup"><span data-stu-id="babf2-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="babf2-115">O formato é: guid: _{0}_ uri: _{1}_ gt _ id:_{2}_</span><span class="sxs-lookup"><span data-stu-id="babf2-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="babf2-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="babf2-116">updatedBy</span></span>  <br/> |<span data-ttu-id="babf2-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="babf2-117">int, not null</span></span>  <br/> |<span data-ttu-id="babf2-118">ID da entidade que atualizou esta linha.</span><span class="sxs-lookup"><span data-stu-id="babf2-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="babf2-119">Sempre é 1 (usuário do sistema) porque a sincronização do Active Directory é a única fonte para essas entradas.</span><span class="sxs-lookup"><span data-stu-id="babf2-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="babf2-120">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="babf2-120">**Keys**</span></span>

|<span data-ttu-id="babf2-121">**Coluna (s)**</span><span class="sxs-lookup"><span data-stu-id="babf2-121">**Column(s)**</span></span>|<span data-ttu-id="babf2-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="babf2-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="babf2-123">\<prinID, affDescription\></span><span class="sxs-lookup"><span data-stu-id="babf2-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="babf2-124">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="babf2-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="babf2-125">prinID</span><span class="sxs-lookup"><span data-stu-id="babf2-125">prinID</span></span>  <br/> |<span data-ttu-id="babf2-126">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="babf2-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

