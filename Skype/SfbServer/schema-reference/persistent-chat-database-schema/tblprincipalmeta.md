---
title: tblPrincipalMeta
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta inclui as entidades que precisam ser atualizadas dos serviços de domínio Active Directory.
ms.openlocfilehash: cfbff018167a3cde68061c3e04eb65d2742e51e9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="ddf8c-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="ddf8c-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="ddf8c-104">tblPrincipalMeta inclui as entidades que precisam ser atualizadas dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="ddf8c-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="ddf8c-105">**Columns**</span></span>

|<span data-ttu-id="ddf8c-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ddf8c-106">**Column**</span></span>|<span data-ttu-id="ddf8c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ddf8c-107">**Type**</span></span>|<span data-ttu-id="ddf8c-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ddf8c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ddf8c-109">prinID</span><span class="sxs-lookup"><span data-stu-id="ddf8c-109">prinID</span></span>  <br/> |<span data-ttu-id="ddf8c-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="ddf8c-110">int, not null</span></span>  <br/> |<span data-ttu-id="ddf8c-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="ddf8c-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="ddf8c-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="ddf8c-113">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="ddf8c-113">bit, not null</span></span>  <br/> |<span data-ttu-id="ddf8c-114">True se a entidade afiliações precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="ddf8c-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="ddf8c-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="ddf8c-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="ddf8c-116">bit, not null</span></span>  <br/> |<span data-ttu-id="ddf8c-117">True se a entidade atributos precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="ddf8c-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="ddf8c-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="ddf8c-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="ddf8c-119">bit, not null</span></span>  <br/> |<span data-ttu-id="ddf8c-120">True se a entidade foi excluída.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="ddf8c-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="ddf8c-121">tryCount</span></span>  <br/> |<span data-ttu-id="ddf8c-122">int</span><span class="sxs-lookup"><span data-stu-id="ddf8c-122">int</span></span>  <br/> |<span data-ttu-id="ddf8c-123">Número de tentativas para atualizar a entidade do AD DS que ocorreram até o momento.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="ddf8c-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="ddf8c-124">lastTry</span></span>  <br/> |<span data-ttu-id="ddf8c-125">datetime</span><span class="sxs-lookup"><span data-stu-id="ddf8c-125">datetime</span></span>  <br/> |<span data-ttu-id="ddf8c-126">Carimbo de hora da última tentativa para atualizar a entidade.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="ddf8c-127">Pode ser null se nenhuma atualização foi tentada ainda.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="ddf8c-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="ddf8c-128">nextTry</span></span>  <br/> |<span data-ttu-id="ddf8c-129">datetime</span><span class="sxs-lookup"><span data-stu-id="ddf8c-129">datetime</span></span>  <br/> |<span data-ttu-id="ddf8c-130">Carimbo de hora para a próxima atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="ddf8c-131">Pode ser null se nenhuma outra atualização foi agendada.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="ddf8c-132">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="ddf8c-132">**Keys**</span></span>

|<span data-ttu-id="ddf8c-133">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ddf8c-133">**Column**</span></span>|<span data-ttu-id="ddf8c-134">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ddf8c-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="ddf8c-135">prinID</span><span class="sxs-lookup"><span data-stu-id="ddf8c-135">prinID</span></span>  <br/> |<span data-ttu-id="ddf8c-136">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="ddf8c-137">prinID</span><span class="sxs-lookup"><span data-stu-id="ddf8c-137">prinID</span></span>  <br/> |<span data-ttu-id="ddf8c-138">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="ddf8c-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

