---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: tblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos serviços de domínio Active Directory, em contêineres do Active Directory, em domínios.
ms.openlocfilehash: cda9827f4a4ab7e17a156cc867e4925c88d06ff3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295311"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="d3491-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="d3491-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="d3491-104">tblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos serviços de domínio Active Directory, em contêineres do Active Directory, em domínios.</span><span class="sxs-lookup"><span data-stu-id="d3491-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="d3491-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d3491-105">**Columns**</span></span>

|<span data-ttu-id="d3491-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d3491-106">**Column**</span></span>|<span data-ttu-id="d3491-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d3491-107">**Type**</span></span>|<span data-ttu-id="d3491-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d3491-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d3491-109">entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="d3491-109">principalID</span></span>  <br/> |<span data-ttu-id="d3491-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d3491-110">int, not null</span></span>  <br/> |<span data-ttu-id="d3491-111">ID do objeto associado.</span><span class="sxs-lookup"><span data-stu-id="d3491-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="d3491-112">afiliaid</span><span class="sxs-lookup"><span data-stu-id="d3491-112">affiliationID</span></span>  <br/> |<span data-ttu-id="d3491-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d3491-113">int, not null</span></span>  <br/> |<span data-ttu-id="d3491-114">ID da entidade de segurança que representa a afiliada.</span><span class="sxs-lookup"><span data-stu-id="d3491-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="d3491-115">Cada entidade de segurança (exceto tipos de usuário do sistema) também tem uma afiliada.</span><span class="sxs-lookup"><span data-stu-id="d3491-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="d3491-116">dedo</span><span class="sxs-lookup"><span data-stu-id="d3491-116">index</span></span>  <br/> |<span data-ttu-id="d3491-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d3491-117">int, not null</span></span>  <br/> |<span data-ttu-id="d3491-118">Dedo.</span><span class="sxs-lookup"><span data-stu-id="d3491-118">Index.</span></span> <span data-ttu-id="d3491-119">O valor para autoafiliações é-1 e para as outras afiliações que ele aumenta sequencialmente de 1 dentro de cada \<objeto de entidade de segurança\> , o BucketID.</span><span class="sxs-lookup"><span data-stu-id="d3491-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="d3491-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="d3491-120">updatedBy</span></span>  <br/> |<span data-ttu-id="d3491-121">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d3491-121">int, not null</span></span>  <br/> |<span data-ttu-id="d3491-122">Entidade de segurança que fez a atualização mais recente.</span><span class="sxs-lookup"><span data-stu-id="d3491-122">Principal that did the latest update.</span></span> <span data-ttu-id="d3491-123">Geralmente, isso é 1, o que significa sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="d3491-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="d3491-124">**As**</span><span class="sxs-lookup"><span data-stu-id="d3491-124">**Keys**</span></span>

|<span data-ttu-id="d3491-125">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d3491-125">**Columns**</span></span>|<span data-ttu-id="d3491-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d3491-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d3491-127">\<entidade de segurança, índice, afiliaid\></span><span class="sxs-lookup"><span data-stu-id="d3491-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="d3491-128">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="d3491-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="d3491-129">entidade de segurança</span><span class="sxs-lookup"><span data-stu-id="d3491-129">principalID</span></span>  <br/> |<span data-ttu-id="d3491-130">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="d3491-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="d3491-131">afiliaid</span><span class="sxs-lookup"><span data-stu-id="d3491-131">affiliationID</span></span>  <br/> |<span data-ttu-id="d3491-132">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="d3491-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

