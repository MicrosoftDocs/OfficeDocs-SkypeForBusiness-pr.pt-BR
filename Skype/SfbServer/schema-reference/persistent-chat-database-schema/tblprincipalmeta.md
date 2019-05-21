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
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas a partir dos serviços de domínio Active Directory.
ms.openlocfilehash: 9cff5b2515613ac3540d82e545862bf4fdb58b94
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295255"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="3583f-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="3583f-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="3583f-104">tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas a partir dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3583f-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="3583f-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="3583f-105">**Columns**</span></span>

|<span data-ttu-id="3583f-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3583f-106">**Column**</span></span>|<span data-ttu-id="3583f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3583f-107">**Type**</span></span>|<span data-ttu-id="3583f-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3583f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3583f-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="3583f-109">prinID</span></span>  <br/> |<span data-ttu-id="3583f-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="3583f-110">int, not null</span></span>  <br/> |<span data-ttu-id="3583f-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="3583f-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="3583f-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="3583f-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="3583f-113">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="3583f-113">bit, not null</span></span>  <br/> |<span data-ttu-id="3583f-114">Verdadeiro se as afiliações principais precisarem ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="3583f-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="3583f-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="3583f-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="3583f-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="3583f-116">bit, not null</span></span>  <br/> |<span data-ttu-id="3583f-117">Verdadeiro se os atributos principais precisarem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="3583f-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="3583f-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="3583f-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="3583f-119">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="3583f-119">bit, not null</span></span>  <br/> |<span data-ttu-id="3583f-120">Verdadeiro se o capital foi excluído.</span><span class="sxs-lookup"><span data-stu-id="3583f-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="3583f-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="3583f-121">tryCount</span></span>  <br/> |<span data-ttu-id="3583f-122">int</span><span class="sxs-lookup"><span data-stu-id="3583f-122">int</span></span>  <br/> |<span data-ttu-id="3583f-123">Número de tentativas de atualizar a entidade de segurança do AD DS que aconteceram até agora.</span><span class="sxs-lookup"><span data-stu-id="3583f-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="3583f-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="3583f-124">lastTry</span></span>  <br/> |<span data-ttu-id="3583f-125">datetime</span><span class="sxs-lookup"><span data-stu-id="3583f-125">datetime</span></span>  <br/> |<span data-ttu-id="3583f-126">Carimbo de data/hora da tentativa mais recente de atualizar a entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="3583f-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="3583f-127">Pode ser NULL se ainda não houver uma tentativa de atualização.</span><span class="sxs-lookup"><span data-stu-id="3583f-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="3583f-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="3583f-128">nextTry</span></span>  <br/> |<span data-ttu-id="3583f-129">datetime</span><span class="sxs-lookup"><span data-stu-id="3583f-129">datetime</span></span>  <br/> |<span data-ttu-id="3583f-130">Carimbo de data/hora para a próxima atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="3583f-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="3583f-131">Pode ser NULL se não houver mais nenhuma atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="3583f-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="3583f-132">**As**</span><span class="sxs-lookup"><span data-stu-id="3583f-132">**Keys**</span></span>

|<span data-ttu-id="3583f-133">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3583f-133">**Column**</span></span>|<span data-ttu-id="3583f-134">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3583f-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3583f-135">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="3583f-135">prinID</span></span>  <br/> |<span data-ttu-id="3583f-136">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="3583f-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="3583f-137">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="3583f-137">prinID</span></span>  <br/> |<span data-ttu-id="3583f-138">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="3583f-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

