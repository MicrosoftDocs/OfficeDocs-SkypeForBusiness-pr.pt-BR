---
title: tblPrincipalMeta
ms.reviewer: ''
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
ms.openlocfilehash: 049a273f7134ecb945e62da39469bcaf0defbffb
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889604"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="22f51-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="22f51-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="22f51-104">tblPrincipalMeta inclui as entidades que precisam ser atualizadas dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="22f51-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="22f51-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="22f51-105">**Columns**</span></span>

|<span data-ttu-id="22f51-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="22f51-106">**Column**</span></span>|<span data-ttu-id="22f51-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="22f51-107">**Type**</span></span>|<span data-ttu-id="22f51-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="22f51-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="22f51-109">prinID</span><span class="sxs-lookup"><span data-stu-id="22f51-109">prinID</span></span>  <br/> |<span data-ttu-id="22f51-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="22f51-110">int, not null</span></span>  <br/> |<span data-ttu-id="22f51-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="22f51-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="22f51-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="22f51-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="22f51-113">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="22f51-113">bit, not null</span></span>  <br/> |<span data-ttu-id="22f51-114">True se a entidade afiliações precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="22f51-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="22f51-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="22f51-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="22f51-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="22f51-116">bit, not null</span></span>  <br/> |<span data-ttu-id="22f51-117">True se a entidade atributos precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="22f51-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="22f51-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="22f51-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="22f51-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="22f51-119">bit, not null</span></span>  <br/> |<span data-ttu-id="22f51-120">True se a entidade foi excluída.</span><span class="sxs-lookup"><span data-stu-id="22f51-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="22f51-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="22f51-121">tryCount</span></span>  <br/> |<span data-ttu-id="22f51-122">int</span><span class="sxs-lookup"><span data-stu-id="22f51-122">int</span></span>  <br/> |<span data-ttu-id="22f51-123">Número de tentativas para atualizar a entidade do AD DS que ocorreram até o momento.</span><span class="sxs-lookup"><span data-stu-id="22f51-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="22f51-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="22f51-124">lastTry</span></span>  <br/> |<span data-ttu-id="22f51-125">datetime</span><span class="sxs-lookup"><span data-stu-id="22f51-125">datetime</span></span>  <br/> |<span data-ttu-id="22f51-126">Carimbo de hora da última tentativa para atualizar a entidade.</span><span class="sxs-lookup"><span data-stu-id="22f51-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="22f51-127">Pode ser null se nenhuma atualização foi tentada ainda.</span><span class="sxs-lookup"><span data-stu-id="22f51-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="22f51-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="22f51-128">nextTry</span></span>  <br/> |<span data-ttu-id="22f51-129">datetime</span><span class="sxs-lookup"><span data-stu-id="22f51-129">datetime</span></span>  <br/> |<span data-ttu-id="22f51-130">Carimbo de hora para a próxima atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="22f51-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="22f51-131">Pode ser null se nenhuma outra atualização foi agendada.</span><span class="sxs-lookup"><span data-stu-id="22f51-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="22f51-132">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="22f51-132">**Keys**</span></span>

|<span data-ttu-id="22f51-133">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="22f51-133">**Column**</span></span>|<span data-ttu-id="22f51-134">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="22f51-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="22f51-135">prinID</span><span class="sxs-lookup"><span data-stu-id="22f51-135">prinID</span></span>  <br/> |<span data-ttu-id="22f51-136">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="22f51-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="22f51-137">prinID</span><span class="sxs-lookup"><span data-stu-id="22f51-137">prinID</span></span>  <br/> |<span data-ttu-id="22f51-138">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="22f51-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

