---
title: tblSkippedAffiliations
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b129b54-a7a8-42a6-9279-0e08410c06ec
description: TblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso aos Serviços de Domínio Active Directory).
ms.openlocfilehash: 3061a399de804898d3dc2c616fb3766206c2d624
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831421"
---
# <a name="tblskippedaffiliations"></a><span data-ttu-id="d592a-103">tblSkippedAffiliations</span><span class="sxs-lookup"><span data-stu-id="d592a-103">tblSkippedAffiliations</span></span>
 
<span data-ttu-id="d592a-104">TblSkippedAffiliations contém as afiliações que não puderam ser lidas (geralmente devido a erros de acesso aos Serviços de Domínio Active Directory).</span><span class="sxs-lookup"><span data-stu-id="d592a-104">tblSkippedAffiliations contains the affiliations that could not be read (usually due to Active Directory Domain Services access errors).</span></span>
  
<span data-ttu-id="d592a-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="d592a-105">**Columns**</span></span>

|<span data-ttu-id="d592a-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d592a-106">**Column**</span></span>|<span data-ttu-id="d592a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d592a-107">**Type**</span></span>|<span data-ttu-id="d592a-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d592a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d592a-109">prinID</span><span class="sxs-lookup"><span data-stu-id="d592a-109">prinID</span></span>  <br/> |<span data-ttu-id="d592a-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d592a-110">int, not null</span></span>  <br/> |<span data-ttu-id="d592a-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="d592a-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="d592a-112">affDescription</span><span class="sxs-lookup"><span data-stu-id="d592a-112">affDescription</span></span>  <br/> |<span data-ttu-id="d592a-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="d592a-113">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d592a-114">Uma cadeia identificando a afiliação.</span><span class="sxs-lookup"><span data-stu-id="d592a-114">A string identifying the affiliation.</span></span>  <br/> <span data-ttu-id="d592a-115">O formato é: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span><span class="sxs-lookup"><span data-stu-id="d592a-115">The format is: guid:  _{0}_ uri: _{1}_> id:  _{2}_</span></span> <br/> |
|<span data-ttu-id="d592a-116">updatedBy</span><span class="sxs-lookup"><span data-stu-id="d592a-116">updatedBy</span></span>  <br/> |<span data-ttu-id="d592a-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d592a-117">int, not null</span></span>  <br/> |<span data-ttu-id="d592a-p101">ID da principal que atualizou essa linha. É sempre 1 (usuário do sistema) porque a Sincronização do Active Directory é a única origem dessas entradas.</span><span class="sxs-lookup"><span data-stu-id="d592a-p101">ID of the principal that updated this row. It is always 1 (system user) because Active Directory Sync is the only source for these entries.</span></span>  <br/> |
   
<span data-ttu-id="d592a-120">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="d592a-120">**Keys**</span></span>

|<span data-ttu-id="d592a-121">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d592a-121">**Column(s)**</span></span>|<span data-ttu-id="d592a-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d592a-122">**Description**</span></span>|
|:-----|:-----|
|\<prinID, affDescription\>  <br/> |<span data-ttu-id="d592a-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="d592a-123">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d592a-124">prinID</span><span class="sxs-lookup"><span data-stu-id="d592a-124">prinID</span></span>  <br/> |<span data-ttu-id="d592a-125">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="d592a-125">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

