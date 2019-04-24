---
title: tblPrincipalAffiliations
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: o tblPrincipalAffiliations inclui as principais afiliações que descrevem as associações em locais, incluindo grupos de segurança do Active Directory Domain Services, em contêineres do Active Directory, em domínios.
ms.openlocfilehash: c93edb552c63ebd4f7344926a7d43858b42506ae
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212499"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="f09b6-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="f09b6-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="f09b6-104">o tblPrincipalAffiliations inclui as principais afiliações que descrevem as associações em locais, incluindo grupos de segurança do Active Directory Domain Services, em contêineres do Active Directory, em domínios.</span><span class="sxs-lookup"><span data-stu-id="f09b6-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="f09b6-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="f09b6-105">**Columns**</span></span>

|<span data-ttu-id="f09b6-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f09b6-106">**Column**</span></span>|<span data-ttu-id="f09b6-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f09b6-107">**Type**</span></span>|<span data-ttu-id="f09b6-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f09b6-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f09b6-109">principalID</span><span class="sxs-lookup"><span data-stu-id="f09b6-109">principalID</span></span>  <br/> |<span data-ttu-id="f09b6-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="f09b6-110">int, not null</span></span>  <br/> |<span data-ttu-id="f09b6-111">ID da entidade de segurança afiliada.</span><span class="sxs-lookup"><span data-stu-id="f09b6-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="f09b6-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="f09b6-112">affiliationID</span></span>  <br/> |<span data-ttu-id="f09b6-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="f09b6-113">int, not null</span></span>  <br/> |<span data-ttu-id="f09b6-114">ID da entidade de segurança que representa a afiliação.</span><span class="sxs-lookup"><span data-stu-id="f09b6-114">ID of the principal representing the affiliation.</span></span> <span data-ttu-id="f09b6-115">Cada entidade (exceto o usuário digita sistema) tem uma afiliação Self também.</span><span class="sxs-lookup"><span data-stu-id="f09b6-115">Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="f09b6-116">índice</span><span class="sxs-lookup"><span data-stu-id="f09b6-116">index</span></span>  <br/> |<span data-ttu-id="f09b6-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="f09b6-117">int, not null</span></span>  <br/> |<span data-ttu-id="f09b6-118">Índice.</span><span class="sxs-lookup"><span data-stu-id="f09b6-118">Index.</span></span> <span data-ttu-id="f09b6-119">O valor de afiliações Self é -1 e para as outras afiliações aumenta sequencialmente de 1 dentro de cada \<principalID, affiliationId\> no processo de Balde.</span><span class="sxs-lookup"><span data-stu-id="f09b6-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="f09b6-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="f09b6-120">updatedBy</span></span>  <br/> |<span data-ttu-id="f09b6-121">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="f09b6-121">int, not null</span></span>  <br/> |<span data-ttu-id="f09b6-122">Entidade de segurança que efetuou a atualização mais recente.</span><span class="sxs-lookup"><span data-stu-id="f09b6-122">Principal that did the latest update.</span></span> <span data-ttu-id="f09b6-123">Isso geralmente é 1, o que significa que a sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f09b6-123">This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="f09b6-124">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="f09b6-124">**Keys**</span></span>

|<span data-ttu-id="f09b6-125">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="f09b6-125">**Columns**</span></span>|<span data-ttu-id="f09b6-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f09b6-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f09b6-127">\<principalID, índice, affiliationID\></span><span class="sxs-lookup"><span data-stu-id="f09b6-127">\<principalID, index, affiliationID\></span></span>  <br/> |<span data-ttu-id="f09b6-128">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="f09b6-128">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f09b6-129">principalID</span><span class="sxs-lookup"><span data-stu-id="f09b6-129">principalID</span></span>  <br/> |<span data-ttu-id="f09b6-130">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="f09b6-130">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="f09b6-131">affiliationID</span><span class="sxs-lookup"><span data-stu-id="f09b6-131">affiliationID</span></span>  <br/> |<span data-ttu-id="f09b6-132">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="f09b6-132">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

