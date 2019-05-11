---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contém associações de entidade.
ms.openlocfilehash: be66ee6124c7b0306583bcb10f7d78b777fcf10c
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33904157"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="52873-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="52873-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="52873-104">tblPrincipalMembers contém associações de entidade.</span><span class="sxs-lookup"><span data-stu-id="52873-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="52873-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="52873-105">**Columns**</span></span>

|<span data-ttu-id="52873-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="52873-106">**Column**</span></span>|<span data-ttu-id="52873-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="52873-107">**Type**</span></span>|<span data-ttu-id="52873-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="52873-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="52873-109">prinID</span><span class="sxs-lookup"><span data-stu-id="52873-109">prinID</span></span>  <br/> |<span data-ttu-id="52873-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="52873-110">int, not null</span></span>  <br/> |<span data-ttu-id="52873-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="52873-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="52873-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="52873-112">memberADPath</span></span>  <br/> |<span data-ttu-id="52873-113">nvarchar (384), não nulo</span><span class="sxs-lookup"><span data-stu-id="52873-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="52873-114">Nome distinto do membro.</span><span class="sxs-lookup"><span data-stu-id="52873-114">Distinguished name of a member.</span></span> <span data-ttu-id="52873-115">Membro não precisam ser uma entidade de segurança (na tabela tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="52873-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="52873-116">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="52873-116">**Keys**</span></span>

|<span data-ttu-id="52873-117">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="52873-117">**Column**</span></span>|<span data-ttu-id="52873-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="52873-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="52873-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="52873-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="52873-120">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="52873-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="52873-121">prinID</span><span class="sxs-lookup"><span data-stu-id="52873-121">prinID</span></span>  <br/> |<span data-ttu-id="52873-122">Chave estrangeira com pesquisa em Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="52873-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

