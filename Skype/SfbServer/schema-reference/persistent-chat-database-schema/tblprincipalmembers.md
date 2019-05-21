---
title: tblPrincipalMembers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 9a3e24cf-6ef7-4b82-99fc-50ba41800b6f
description: tblPrincipalMembers contém associações de entidades de segurança.
ms.openlocfilehash: 12c3bf86b7416665f0f2355af0bfc9f98e3c1f1a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295283"
---
# <a name="tblprincipalmembers"></a><span data-ttu-id="8dae9-103">tblPrincipalMembers</span><span class="sxs-lookup"><span data-stu-id="8dae9-103">tblPrincipalMembers</span></span>
 
<span data-ttu-id="8dae9-104">tblPrincipalMembers contém associações de entidades de segurança.</span><span class="sxs-lookup"><span data-stu-id="8dae9-104">tblPrincipalMembers contains principal memberships.</span></span>
  
<span data-ttu-id="8dae9-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="8dae9-105">**Columns**</span></span>

|<span data-ttu-id="8dae9-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8dae9-106">**Column**</span></span>|<span data-ttu-id="8dae9-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8dae9-107">**Type**</span></span>|<span data-ttu-id="8dae9-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8dae9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8dae9-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="8dae9-109">prinID</span></span>  <br/> |<span data-ttu-id="8dae9-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="8dae9-110">int, not null</span></span>  <br/> |<span data-ttu-id="8dae9-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="8dae9-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="8dae9-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="8dae9-112">memberADPath</span></span>  <br/> |<span data-ttu-id="8dae9-113">nvarchar (384), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="8dae9-113">nvarchar (384), not null</span></span>  <br/> |<span data-ttu-id="8dae9-114">Nome diferenciado de um membro.</span><span class="sxs-lookup"><span data-stu-id="8dae9-114">Distinguished name of a member.</span></span> <span data-ttu-id="8dae9-115">Um membro não precisa ser um principal (na tabela tblPrincipal).</span><span class="sxs-lookup"><span data-stu-id="8dae9-115">A member does not have to be a principal (in tblPrincipal table).</span></span>  <br/> |
   
<span data-ttu-id="8dae9-116">**As**</span><span class="sxs-lookup"><span data-stu-id="8dae9-116">**Keys**</span></span>

|<span data-ttu-id="8dae9-117">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8dae9-117">**Column**</span></span>|<span data-ttu-id="8dae9-118">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8dae9-118">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8dae9-119">\<memberADPath\></span><span class="sxs-lookup"><span data-stu-id="8dae9-119">\<prinID, memberADPath\></span></span>  <br/> |<span data-ttu-id="8dae9-120">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="8dae9-120">Primary key.</span></span>  <br/> |
|<span data-ttu-id="8dae9-121">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="8dae9-121">prinID</span></span>  <br/> |<span data-ttu-id="8dae9-122">Chave estrangeira com Lookup em tblPrincipal. importaid.</span><span class="sxs-lookup"><span data-stu-id="8dae9-122">Foreign key with lookup in tblPrincipal.prinID.</span></span>  <br/> |
   

