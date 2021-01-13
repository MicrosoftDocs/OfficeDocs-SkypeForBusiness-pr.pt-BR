---
title: tblPrincipalAffiliations
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
ms.assetid: 45fd8484-5837-44d2-85bb-45c83546607c
description: TblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos Serviços de Domínio Active Directory, em contêineres do Active Directory, em domínios.
ms.openlocfilehash: 149bb1b4603fa0f0e1909298659b881000464275
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815861"
---
# <a name="tblprincipalaffiliations"></a><span data-ttu-id="3f32f-103">tblPrincipalAffiliations</span><span class="sxs-lookup"><span data-stu-id="3f32f-103">tblPrincipalAffiliations</span></span>
 
<span data-ttu-id="3f32f-104">TblPrincipalAffiliations contém as afiliações principais que descrevem associações em locais, incluindo grupos de segurança dos Serviços de Domínio Active Directory, em contêineres do Active Directory, em domínios.</span><span class="sxs-lookup"><span data-stu-id="3f32f-104">tblPrincipalAffiliations contains the principal affiliations that describe memberships in locations, including Active Directory Domain Services security groups, in Active Directory containers, in domains.</span></span>
  
<span data-ttu-id="3f32f-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="3f32f-105">**Columns**</span></span>

|<span data-ttu-id="3f32f-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3f32f-106">**Column**</span></span>|<span data-ttu-id="3f32f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3f32f-107">**Type**</span></span>|<span data-ttu-id="3f32f-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3f32f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3f32f-109">principalID</span><span class="sxs-lookup"><span data-stu-id="3f32f-109">principalID</span></span>  <br/> |<span data-ttu-id="3f32f-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="3f32f-110">int, not null</span></span>  <br/> |<span data-ttu-id="3f32f-111">ID da entidade de segurança afiliada.</span><span class="sxs-lookup"><span data-stu-id="3f32f-111">ID of the affiliated principal.</span></span>  <br/> |
|<span data-ttu-id="3f32f-112">affiliationID</span><span class="sxs-lookup"><span data-stu-id="3f32f-112">affiliationID</span></span>  <br/> |<span data-ttu-id="3f32f-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="3f32f-113">int, not null</span></span>  <br/> |<span data-ttu-id="3f32f-p101">ID da entidade de segurança que representa a afiliação. Cada entidade (exceto system-user-types) tem também uma autoafiliação.</span><span class="sxs-lookup"><span data-stu-id="3f32f-p101">ID of the principal representing the affiliation. Each principal (except system-user-types) has a self-affiliation as well.</span></span>  <br/> |
|<span data-ttu-id="3f32f-116">index</span><span class="sxs-lookup"><span data-stu-id="3f32f-116">index</span></span>  <br/> |<span data-ttu-id="3f32f-117">int, not null</span><span class="sxs-lookup"><span data-stu-id="3f32f-117">int, not null</span></span>  <br/> |<span data-ttu-id="3f32f-118">Índice.</span><span class="sxs-lookup"><span data-stu-id="3f32f-118">Index.</span></span> <span data-ttu-id="3f32f-119">O valor para autoafiliações é -1 e, para as outras afiliações, aumenta sequencialmente de 1 dentro de cada \<principalID, affiliationId\> bucket.</span><span class="sxs-lookup"><span data-stu-id="3f32f-119">The value for self-affiliations is -1, and for the other affiliations it increases sequentially from 1 within each \<principalID, affiliationId\> bucket.</span></span>  <br/> |
|<span data-ttu-id="3f32f-120">updatedBy</span><span class="sxs-lookup"><span data-stu-id="3f32f-120">updatedBy</span></span>  <br/> |<span data-ttu-id="3f32f-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="3f32f-121">int, not null</span></span>  <br/> |<span data-ttu-id="3f32f-p103">Entidade de segurança que fez a atualização mais recente. Isso geralmente é 1, o que significa Sincronização do Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3f32f-p103">Principal that did the latest update. This is usually 1, which means Active Directory Sync.</span></span>  <br/> |
   
<span data-ttu-id="3f32f-124">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="3f32f-124">**Keys**</span></span>

|<span data-ttu-id="3f32f-125">**Columns**</span><span class="sxs-lookup"><span data-stu-id="3f32f-125">**Columns**</span></span>|<span data-ttu-id="3f32f-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3f32f-126">**Description**</span></span>|
|:-----|:-----|
|\<principalID, index, affiliationID\>  <br/> |<span data-ttu-id="3f32f-127">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="3f32f-127">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3f32f-128">principalID</span><span class="sxs-lookup"><span data-stu-id="3f32f-128">principalID</span></span>  <br/> |<span data-ttu-id="3f32f-129">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="3f32f-129">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
|<span data-ttu-id="3f32f-130">affiliationID</span><span class="sxs-lookup"><span data-stu-id="3f32f-130">affiliationID</span></span>  <br/> |<span data-ttu-id="3f32f-131">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="3f32f-131">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

