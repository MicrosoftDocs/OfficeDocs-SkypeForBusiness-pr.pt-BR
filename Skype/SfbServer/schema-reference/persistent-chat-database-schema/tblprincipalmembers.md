---
title: tblPrincipalMembers
ms.reviewer: ''
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
ms.openlocfilehash: 2b2b9616c76095ec27178887e69dd482bcf6da92
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874249"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="83665-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="83665-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="83665-104">tblPrincipalMembers contém associações de entidade.</span><span class="sxs-lookup"><span data-stu-id="83665-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="83665-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="83665-105">**Columns**</span></span>

|<span data-ttu-id="83665-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="83665-106">**Column**</span></span>|<span data-ttu-id="83665-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="83665-107">**Type**</span></span>|<span data-ttu-id="83665-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="83665-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="83665-109">prinID</span><span class="sxs-lookup"><span data-stu-id="83665-109">prinID</span></span>  <br/> |<span data-ttu-id="83665-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="83665-110">int, not null</span></span>  <br/> |<span data-ttu-id="83665-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="83665-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="83665-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="83665-112">memberADPath</span></span>  <br/> |<span data-ttu-id="83665-113">nvarchar (384), não nulo</span><span class="sxs-lookup"><span data-stu-id="83665-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="83665-114">Nome distinto do membro.</span><span class="sxs-lookup"><span data-stu-id="83665-114">Distinguished name of a member.</span></span> <span data-ttu-id="83665-115">Membro não precisam ser uma entidade de segurança (na tabela tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="83665-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="83665-116">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="83665-116">**Keys**</span></span>

|<span data-ttu-id="83665-117">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="83665-117">**Column**</span></span>|<span data-ttu-id="83665-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="83665-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="83665-119">\<prinID, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="83665-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="83665-120">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="83665-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="83665-121">prinID</span><span class="sxs-lookup"><span data-stu-id="83665-121">prinID</span></span>  <br/> |<span data-ttu-id="83665-122">Chave estrangeira com pesquisa em Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="83665-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

