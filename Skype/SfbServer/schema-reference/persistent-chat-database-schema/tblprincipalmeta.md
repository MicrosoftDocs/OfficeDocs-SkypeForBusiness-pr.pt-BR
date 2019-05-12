---
title: tblPrincipalMeta
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta inclui as entidades que precisam ser atualizadas dos serviços de domínio Active Directory.
ms.openlocfilehash: a13fdcf705075188ae4febd5a2e0c3bc93a4738f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924539"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="9f171-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="9f171-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="9f171-104">tblPrincipalMeta inclui as entidades que precisam ser atualizadas dos serviços de domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="9f171-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="9f171-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="9f171-105">**Columns**</span></span>

|<span data-ttu-id="9f171-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9f171-106">**Column**</span></span>|<span data-ttu-id="9f171-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9f171-107">**Type**</span></span>|<span data-ttu-id="9f171-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9f171-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9f171-109">prinID</span><span class="sxs-lookup"><span data-stu-id="9f171-109">prinID</span></span>  <br/> |<span data-ttu-id="9f171-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="9f171-110">int, not null</span></span>  <br/> |<span data-ttu-id="9f171-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="9f171-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9f171-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="9f171-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="9f171-113">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="9f171-113">bit, not null</span></span>  <br/> |<span data-ttu-id="9f171-114">True se a entidade afiliações precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="9f171-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="9f171-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="9f171-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="9f171-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="9f171-116">bit, not null</span></span>  <br/> |<span data-ttu-id="9f171-117">True se a entidade atributos precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="9f171-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="9f171-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="9f171-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="9f171-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="9f171-119">bit, not null</span></span>  <br/> |<span data-ttu-id="9f171-120">True se a entidade foi excluída.</span><span class="sxs-lookup"><span data-stu-id="9f171-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="9f171-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="9f171-121">tryCount</span></span>  <br/> |<span data-ttu-id="9f171-122">int</span><span class="sxs-lookup"><span data-stu-id="9f171-122">int</span></span>  <br/> |<span data-ttu-id="9f171-123">Número de tentativas para atualizar a entidade do AD DS que ocorreram até o momento.</span><span class="sxs-lookup"><span data-stu-id="9f171-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="9f171-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="9f171-124">lastTry</span></span>  <br/> |<span data-ttu-id="9f171-125">datetime</span><span class="sxs-lookup"><span data-stu-id="9f171-125">datetime</span></span>  <br/> |<span data-ttu-id="9f171-126">Carimbo de hora da última tentativa para atualizar a entidade.</span><span class="sxs-lookup"><span data-stu-id="9f171-126">Time stamp from the latest attempt to refresh the principal.</span></span> <span data-ttu-id="9f171-127">Pode ser null se nenhuma atualização foi tentada ainda.</span><span class="sxs-lookup"><span data-stu-id="9f171-127">Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="9f171-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="9f171-128">nextTry</span></span>  <br/> |<span data-ttu-id="9f171-129">datetime</span><span class="sxs-lookup"><span data-stu-id="9f171-129">datetime</span></span>  <br/> |<span data-ttu-id="9f171-130">Carimbo de hora para a próxima atualização agendada.</span><span class="sxs-lookup"><span data-stu-id="9f171-130">Time stamp for the next scheduled refresh.</span></span> <span data-ttu-id="9f171-131">Pode ser null se nenhuma outra atualização foi agendada.</span><span class="sxs-lookup"><span data-stu-id="9f171-131">Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="9f171-132">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="9f171-132">**Keys**</span></span>

|<span data-ttu-id="9f171-133">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9f171-133">**Column**</span></span>|<span data-ttu-id="9f171-134">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9f171-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9f171-135">prinID</span><span class="sxs-lookup"><span data-stu-id="9f171-135">prinID</span></span>  <br/> |<span data-ttu-id="9f171-136">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="9f171-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9f171-137">prinID</span><span class="sxs-lookup"><span data-stu-id="9f171-137">prinID</span></span>  <br/> |<span data-ttu-id="9f171-138">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="9f171-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

