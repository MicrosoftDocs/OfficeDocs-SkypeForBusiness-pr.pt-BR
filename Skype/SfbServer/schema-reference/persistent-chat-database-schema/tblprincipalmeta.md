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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212429"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="f89bf-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="f89bf-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="f89bf-104">tblPrincipalMeta inclui as entidades que precisam ser atualizadas dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f89bf-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="f89bf-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="f89bf-105">**Columns**</span></span>

|<span data-ttu-id="f89bf-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f89bf-106">**Column**</span></span>|<span data-ttu-id="f89bf-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f89bf-107">**Type**</span></span>|<span data-ttu-id="f89bf-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f89bf-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f89bf-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f89bf-109">prinID</span></span>  <br/> |<span data-ttu-id="f89bf-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="f89bf-110">int, not null</span></span>  <br/> |<span data-ttu-id="f89bf-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="f89bf-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f89bf-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="f89bf-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="f89bf-113">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="f89bf-113">bit, not null</span></span>  <br/> |<span data-ttu-id="f89bf-114">True se a entidade afiliações precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f89bf-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="f89bf-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="f89bf-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="f89bf-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="f89bf-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f89bf-117">True se a entidade atributos precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f89bf-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="f89bf-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="f89bf-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="f89bf-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="f89bf-119">bit, not null</span></span>  <br/> |<span data-ttu-id="f89bf-120">True se a entidade foi excluída.</span><span class="sxs-lookup"><span data-stu-id="f89bf-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="f89bf-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="f89bf-121">tryCount</span></span>  <br/> |<span data-ttu-id="f89bf-122">int</span><span class="sxs-lookup"><span data-stu-id="f89bf-122">int</span></span>  <br/> |<span data-ttu-id="f89bf-123">Número de tentativas para atualizar a entidade do AD DS que ocorreram até o momento.</span><span class="sxs-lookup"><span data-stu-id="f89bf-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="f89bf-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="f89bf-124">lastTry</span></span>  <br/> |<span data-ttu-id="f89bf-125">datetime</span><span class="sxs-lookup"><span data-stu-id="f89bf-125">datetime</span></span>  <br/> |<span data-ttu-id="f89bf-126">Carimbo de hora da última tentativa para atualizar a entidade.</span><span class="sxs-lookup"><span data-stu-id="f89bf-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="f89bf-127">Pode ser null se nenhuma atualização foi tentada ainda.</span><span class="sxs-lookup"><span data-stu-id="f89bf-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="f89bf-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="f89bf-128">nextTry</span></span>  <br/> |<span data-ttu-id="f89bf-129">datetime</span><span class="sxs-lookup"><span data-stu-id="f89bf-129">datetime</span></span>  <br/> |<span data-ttu-id="f89bf-130">Carimbo de hora para a próxima atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="f89bf-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="f89bf-131">Pode ser null se nenhuma outra atualização foi agendada.</span><span class="sxs-lookup"><span data-stu-id="f89bf-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="f89bf-132">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="f89bf-132">**Keys**</span></span>

|<span data-ttu-id="f89bf-133">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f89bf-133">**Column**</span></span>|<span data-ttu-id="f89bf-134">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f89bf-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f89bf-135">prinID</span><span class="sxs-lookup"><span data-stu-id="f89bf-135">prinID</span></span>  <br/> |<span data-ttu-id="f89bf-136">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="f89bf-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f89bf-137">prinID</span><span class="sxs-lookup"><span data-stu-id="f89bf-137">prinID</span></span>  <br/> |<span data-ttu-id="f89bf-138">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="f89bf-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

