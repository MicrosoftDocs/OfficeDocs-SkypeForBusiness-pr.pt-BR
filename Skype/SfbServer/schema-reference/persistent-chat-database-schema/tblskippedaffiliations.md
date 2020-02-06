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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: tblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso aos serviços de domínio Active Directory).
ms.openlocfilehash: 8a138993e12a49f72842808d720a5f778195c6ff
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812009"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="d516d-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="d516d-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="d516d-104">tblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso aos serviços de domínio Active Directory).</span><span class="sxs-lookup"><span data-stu-id="d516d-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="d516d-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d516d-105">**Columns**</span></span>

|<span data-ttu-id="d516d-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d516d-106">**Column**</span></span>|<span data-ttu-id="d516d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d516d-107">**Type**</span></span>|<span data-ttu-id="d516d-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d516d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d516d-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="d516d-109">prinID</span></span>  <br/> |<span data-ttu-id="d516d-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d516d-110">int, not null</span></span>  <br/> |<span data-ttu-id="d516d-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="d516d-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d516d-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="d516d-112">affDescription</span></span>  <br/> |<span data-ttu-id="d516d-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="d516d-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d516d-114">Uma cadeia de caracteres que identifica a afiliação.</span><span class="sxs-lookup"><span data-stu-id="d516d-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="d516d-115">O formato é: GUID: _{0}_ URI: _{1}_ ID do>:_{2}_</span><span class="sxs-lookup"><span data-stu-id="d516d-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="d516d-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="d516d-116">updatedBy</span></span>  <br/> |<span data-ttu-id="d516d-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d516d-117">int, not null</span></span>  <br/> |<span data-ttu-id="d516d-118">ID da entidade de segurança que atualizou esta linha.</span><span class="sxs-lookup"><span data-stu-id="d516d-118">ID of the principal that updated this row.</span></span> <span data-ttu-id="d516d-119">É sempre 1 (usuário do sistema) porque a sincronização do Active Directory é a única fonte dessas entradas.</span><span class="sxs-lookup"><span data-stu-id="d516d-119">It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="d516d-120">**As**</span><span class="sxs-lookup"><span data-stu-id="d516d-120">**Keys**</span></span>

|<span data-ttu-id="d516d-121">**Coluna (s)**</span><span class="sxs-lookup"><span data-stu-id="d516d-121">**Column(s)**</span></span>|<span data-ttu-id="d516d-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d516d-122">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d516d-123">\<affDescription\></span><span class="sxs-lookup"><span data-stu-id="d516d-123">\<prinID, affDescription\></span></span>  <br/> |<span data-ttu-id="d516d-124">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="d516d-124">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d516d-125">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="d516d-125">prinID</span></span>  <br/> |<span data-ttu-id="d516d-126">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="d516d-126">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

