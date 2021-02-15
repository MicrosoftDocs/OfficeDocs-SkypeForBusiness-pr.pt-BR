---
title: tblPrincipalMeta
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
ms.assetid: 808490d4-7d6d-47a2-b8af-b5940d47073b
description: tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas dos Serviços de Domínio Active Directory.
ms.openlocfilehash: e10b56a8a3a1c25f73cd1a07f4fdcde18c6f1215
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831541"
---
# <a name="tblprincipalmeta"></a><span data-ttu-id="f749f-103">tblPrincipalMeta</span><span class="sxs-lookup"><span data-stu-id="f749f-103">tblPrincipalMeta</span></span>
 
<span data-ttu-id="f749f-104">tblPrincipalMeta contém as entidades de segurança que devem ser atualizadas dos Serviços de Domínio Active Directory.</span><span class="sxs-lookup"><span data-stu-id="f749f-104">tblPrincipalMeta contains the principals that have to be refreshed from Active Directory Domain Services.</span></span>
  
<span data-ttu-id="f749f-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="f749f-105">**Columns**</span></span>

|<span data-ttu-id="f749f-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f749f-106">**Column**</span></span>|<span data-ttu-id="f749f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="f749f-107">**Type**</span></span>|<span data-ttu-id="f749f-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f749f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="f749f-109">prinID</span><span class="sxs-lookup"><span data-stu-id="f749f-109">prinID</span></span>  <br/> |<span data-ttu-id="f749f-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="f749f-110">int, not null</span></span>  <br/> |<span data-ttu-id="f749f-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="f749f-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="f749f-112">prinAffiliationsDirty</span><span class="sxs-lookup"><span data-stu-id="f749f-112">prinAffiliationsDirty</span></span>  <br/> |<span data-ttu-id="f749f-113">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="f749f-113">bit, not null</span></span>  <br/> |<span data-ttu-id="f749f-114">Verdadeiro se as afiliações da entidade precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="f749f-114">True if principal affiliations have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="f749f-115">prinAttributesDirty</span><span class="sxs-lookup"><span data-stu-id="f749f-115">prinAttributesDirty</span></span>  <br/> |<span data-ttu-id="f749f-116">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="f749f-116">bit, not null</span></span>  <br/> |<span data-ttu-id="f749f-117">Verdadeiro se os atributos da entidade precisam ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="f749f-117">True if principal attributes have to be refreshed.</span></span>  <br/> |
|<span data-ttu-id="f749f-118">prinDeleted</span><span class="sxs-lookup"><span data-stu-id="f749f-118">prinDeleted</span></span>  <br/> |<span data-ttu-id="f749f-119">bit, não nulo</span><span class="sxs-lookup"><span data-stu-id="f749f-119">bit, not null</span></span>  <br/> |<span data-ttu-id="f749f-120">Verdadeiro se a entidade foi excluída.</span><span class="sxs-lookup"><span data-stu-id="f749f-120">True if the principal has been deleted.</span></span>  <br/> |
|<span data-ttu-id="f749f-121">tryCount</span><span class="sxs-lookup"><span data-stu-id="f749f-121">tryCount</span></span>  <br/> |<span data-ttu-id="f749f-122">int</span><span class="sxs-lookup"><span data-stu-id="f749f-122">int</span></span>  <br/> |<span data-ttu-id="f749f-123">Número de tentativas para atualizar a entidade do AD DS que ocorreram até o momento.</span><span class="sxs-lookup"><span data-stu-id="f749f-123">Number of attempts to refresh the principal from AD DS that have happened so far.</span></span>  <br/> |
|<span data-ttu-id="f749f-124">lastTry</span><span class="sxs-lookup"><span data-stu-id="f749f-124">lastTry</span></span>  <br/> |<span data-ttu-id="f749f-125">datetime</span><span class="sxs-lookup"><span data-stu-id="f749f-125">datetime</span></span>  <br/> |<span data-ttu-id="f749f-p101">Carimbo de data/hora da tentativa mais recente para atualizar a entidade. Pode ser nulo se ainda não houve tentativa de atualização.</span><span class="sxs-lookup"><span data-stu-id="f749f-p101">Time stamp from the latest attempt to refresh the principal. Can be null if no refresh has been attempted yet.</span></span>  <br/> |
|<span data-ttu-id="f749f-128">nextTry</span><span class="sxs-lookup"><span data-stu-id="f749f-128">nextTry</span></span>  <br/> |<span data-ttu-id="f749f-129">datetime</span><span class="sxs-lookup"><span data-stu-id="f749f-129">datetime</span></span>  <br/> |<span data-ttu-id="f749f-p102">Carimbo de data/hora para a próxima atualização agendada. Pode ser nulo se nenhuma atualização foi agendada.</span><span class="sxs-lookup"><span data-stu-id="f749f-p102">Time stamp for the next scheduled refresh. Can be null if no further refresh has been scheduled.</span></span>  <br/> |
   
<span data-ttu-id="f749f-132">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="f749f-132">**Keys**</span></span>

|<span data-ttu-id="f749f-133">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f749f-133">**Column**</span></span>|<span data-ttu-id="f749f-134">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="f749f-134">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f749f-135">prinID</span><span class="sxs-lookup"><span data-stu-id="f749f-135">prinID</span></span>  <br/> |<span data-ttu-id="f749f-136">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="f749f-136">Primary key.</span></span>  <br/> |
|<span data-ttu-id="f749f-137">prinID</span><span class="sxs-lookup"><span data-stu-id="f749f-137">prinID</span></span>  <br/> |<span data-ttu-id="f749f-138">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="f749f-138">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   

