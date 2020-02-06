---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas a partir dos serviços de domínio Active Directory.
ms.openlocfilehash: c76f4a74b3f627d360a2d745e46b6f2dac26bff0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41813569"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="e3bad-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="e3bad-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="e3bad-104">tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas a partir dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="e3bad-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="e3bad-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="e3bad-105">**Columns**</span></span>

|<span data-ttu-id="e3bad-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e3bad-106">**Column**</span></span>|<span data-ttu-id="e3bad-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e3bad-107">**Type**</span></span>|<span data-ttu-id="e3bad-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e3bad-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3bad-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="e3bad-109">prinID</span></span>  <br/> |<span data-ttu-id="e3bad-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="e3bad-110">int, not null</span></span>  <br/> |<span data-ttu-id="e3bad-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="e3bad-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="e3bad-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="e3bad-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="e3bad-113">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="e3bad-113">bit, not null</span></span>  <br/> |<span data-ttu-id="e3bad-114">Verdadeiro se as afiliações principais precisarem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="e3bad-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="e3bad-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="e3bad-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="e3bad-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="e3bad-116">bit, not null</span></span>  <br/> |<span data-ttu-id="e3bad-117">Verdadeiro se os atributos principais precisarem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="e3bad-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="e3bad-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="e3bad-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="e3bad-119">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="e3bad-119">bit, not null</span></span>  <br/> |<span data-ttu-id="e3bad-120">Verdadeiro se o capital foi excluído.</span><span class="sxs-lookup"><span data-stu-id="e3bad-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="e3bad-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="e3bad-121">tryCount</span></span>  <br/> |<span data-ttu-id="e3bad-122">int</span><span class="sxs-lookup"><span data-stu-id="e3bad-122">int</span></span>  <br/> |<span data-ttu-id="e3bad-123">Número de tentativas de atualizar a entidade de segurança do AD DS que aconteceram até agora.</span><span class="sxs-lookup"><span data-stu-id="e3bad-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="e3bad-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="e3bad-124">lastTry</span></span>  <br/> |<span data-ttu-id="e3bad-125">datetime</span><span class="sxs-lookup"><span data-stu-id="e3bad-125">datetime</span></span>  <br/> |<span data-ttu-id="e3bad-126">Carimbo de data/hora da tentativa mais recente de atualizar a entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="e3bad-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="e3bad-127">Pode ser NULL se ainda não houver uma tentativa de atualização.</span><span class="sxs-lookup"><span data-stu-id="e3bad-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="e3bad-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="e3bad-128">nextTry</span></span>  <br/> |<span data-ttu-id="e3bad-129">datetime</span><span class="sxs-lookup"><span data-stu-id="e3bad-129">datetime</span></span>  <br/> |<span data-ttu-id="e3bad-130">Carimbo de data/hora para a próxima atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="e3bad-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="e3bad-131">Pode ser NULL se não houver mais nenhuma atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="e3bad-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="e3bad-132">**As**</span><span class="sxs-lookup"><span data-stu-id="e3bad-132">**Keys**</span></span>

|<span data-ttu-id="e3bad-133">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e3bad-133">**Column**</span></span>|<span data-ttu-id="e3bad-134">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e3bad-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e3bad-135">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="e3bad-135">prinID</span></span>  <br/> |<span data-ttu-id="e3bad-136">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="e3bad-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e3bad-137">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="e3bad-137">prinID</span></span>  <br/> |<span data-ttu-id="e3bad-138">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="e3bad-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

