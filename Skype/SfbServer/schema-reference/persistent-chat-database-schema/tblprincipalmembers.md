---
title: tblPrincipalMembers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contém associações de entidade.
ms.openlocfilehash: 77151cc245b90fa22d9da426a1448c49866dccc2
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="ff68c-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="ff68c-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="ff68c-104">tblPrincipalMembers contém associações de entidade.</span><span class="sxs-lookup"><span data-stu-id="ff68c-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="ff68c-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="ff68c-105">**Columns**</span></span>

|<span data-ttu-id="ff68c-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ff68c-106">**Column**</span></span>|<span data-ttu-id="ff68c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ff68c-107">**Type**</span></span>|<span data-ttu-id="ff68c-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ff68c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ff68c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ff68c-109">prinID</span></span>  <br/> |<span data-ttu-id="ff68c-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="ff68c-110">int, not null</span></span>  <br/> |<span data-ttu-id="ff68c-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="ff68c-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ff68c-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="ff68c-112">memberADPath</span></span>  <br/> |<span data-ttu-id="ff68c-113">nvarchar (384), não nulo</span><span class="sxs-lookup"><span data-stu-id="ff68c-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="ff68c-114">Nome distinto do membro.</span><span class="sxs-lookup"><span data-stu-id="ff68c-114">Distinguished name of a member.</span></span> <span data-ttu-id="ff68c-115">Membro não precisam ser uma entidade de segurança (na tabela tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="ff68c-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="ff68c-116">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="ff68c-116">**Keys**</span></span>

|<span data-ttu-id="ff68c-117">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ff68c-117">**Column**</span></span>|<span data-ttu-id="ff68c-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ff68c-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ff68c-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="ff68c-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="ff68c-120">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="ff68c-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ff68c-121">prinID</span><span class="sxs-lookup"><span data-stu-id="ff68c-121">prinID</span></span>  <br/> |<span data-ttu-id="ff68c-122">Chave estrangeira com pesquisa em Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="ff68c-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

