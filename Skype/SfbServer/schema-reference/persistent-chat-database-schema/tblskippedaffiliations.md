---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso aos serviços de domínio Active Directory).
ms.openlocfilehash: 481bf92a4014bf2af8e1c4794d1793f2c93e7c36
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295150"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="ebf80-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="ebf80-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="ebf80-104">tblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso aos serviços de domínio Active Directory).</span><span class="sxs-lookup"><span data-stu-id="ebf80-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="ebf80-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="ebf80-105">**Columns**</span></span>

|<span data-ttu-id="ebf80-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ebf80-106">**Column**</span></span>|<span data-ttu-id="ebf80-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ebf80-107">**Type**</span></span>|<span data-ttu-id="ebf80-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ebf80-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ebf80-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="ebf80-109">prinID</span></span>  <br/> |<span data-ttu-id="ebf80-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="ebf80-110">int, not null</span></span>  <br/> |<span data-ttu-id="ebf80-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="ebf80-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ebf80-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="ebf80-112">affDescription</span></span>  <br/> |<span data-ttu-id="ebf80-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="ebf80-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="ebf80-114">Uma cadeia de caracteres que identifica a afiliação.</span><span class="sxs-lookup"><span data-stu-id="ebf80-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="ebf80-115">O formato é: GUID: _{0}_ URI: _{1}_> ID:_{2}_</span><span class="sxs-lookup"><span data-stu-id="ebf80-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="ebf80-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="ebf80-116">updatedBy</span></span>  <br/> |<span data-ttu-id="ebf80-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="ebf80-117">int, not null</span></span>  <br/> |<span data-ttu-id="ebf80-118">ID da entidade de segurança que atualizou esta linha.</span><span class="sxs-lookup"><span data-stu-id="ebf80-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="ebf80-119">É sempre 1 (usuário do sistema) porque a sincronização do Active Directory é a única fonte dessas entradas.</span><span class="sxs-lookup"><span data-stu-id="ebf80-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="ebf80-120">**As**</span><span class="sxs-lookup"><span data-stu-id="ebf80-120">**Keys**</span></span>

|<span data-ttu-id="ebf80-121">**Coluna (s)**</span><span class="sxs-lookup"><span data-stu-id="ebf80-121">**Column(s)**</span></span>|<span data-ttu-id="ebf80-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ebf80-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ebf80-123">\<affDescription\></span><span class="sxs-lookup"><span data-stu-id="ebf80-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="ebf80-124">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="ebf80-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ebf80-125">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="ebf80-125">prinID</span></span>  <br/> |<span data-ttu-id="ebf80-126">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="ebf80-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

