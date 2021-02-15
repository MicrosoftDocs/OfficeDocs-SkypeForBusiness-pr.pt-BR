---
title: tblPrincipalMembers
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
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contém associações principais.
ms.openlocfilehash: 93a012ea82acf071a28752eb79682866c0faa418
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831591"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="2e70b-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="2e70b-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="2e70b-104">tblPrincipalMembers contém associações principais.</span><span class="sxs-lookup"><span data-stu-id="2e70b-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="2e70b-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="2e70b-105">**Columns**</span></span>

|<span data-ttu-id="2e70b-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2e70b-106">**Column**</span></span>|<span data-ttu-id="2e70b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2e70b-107">**Type**</span></span>|<span data-ttu-id="2e70b-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2e70b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2e70b-109">prinID</span><span class="sxs-lookup"><span data-stu-id="2e70b-109">prinID</span></span>  <br/> |<span data-ttu-id="2e70b-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="2e70b-110">int, not null</span></span>  <br/> |<span data-ttu-id="2e70b-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="2e70b-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="2e70b-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="2e70b-112">memberADPath</span></span>  <br/> |<span data-ttu-id="2e70b-113">nvarchar (384), não nulo</span><span class="sxs-lookup"><span data-stu-id="2e70b-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="2e70b-114">Nome diferenciado de um membro.</span><span class="sxs-lookup"><span data-stu-id="2e70b-114">Distinguished name of a member.</span></span> <span data-ttu-id="2e70b-115">Um membro não precisa ser um diretor (na tabela tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="2e70b-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="2e70b-116">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="2e70b-116">**Keys**</span></span>

|<span data-ttu-id="2e70b-117">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2e70b-117">**Column**</span></span>|<span data-ttu-id="2e70b-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2e70b-118">**Description**</span></span>|
|:-----|:-----|
|\<prinID, memberADPath\>  <br/> |<span data-ttu-id="2e70b-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="2e70b-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="2e70b-120">prinID</span><span class="sxs-lookup"><span data-stu-id="2e70b-120">prinID</span></span>  <br/> |<span data-ttu-id="2e70b-121">Chave estrangeira com a lookup em tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="2e70b-121">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

