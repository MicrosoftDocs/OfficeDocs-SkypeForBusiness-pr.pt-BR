---
title: tblRoleType
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.
ms.openlocfilehash: 074b65d3f701d122bbb311da3096e6727dd17264
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924960"
---
# <a name="tblroletype"></a><span data-ttu-id="67417-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="67417-103">tblRoleType</span></span>
 
<span data-ttu-id="67417-104">tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.</span><span class="sxs-lookup"><span data-stu-id="67417-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="67417-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="67417-105">**Columns**</span></span>

|<span data-ttu-id="67417-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="67417-106">**Column**</span></span>|<span data-ttu-id="67417-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="67417-107">**Type**</span></span>|<span data-ttu-id="67417-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="67417-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="67417-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="67417-109">rtypeID</span></span>  <br/> |<span data-ttu-id="67417-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="67417-110">int, not null</span></span>  <br/> |<span data-ttu-id="67417-111">ID do tipo de função.</span><span class="sxs-lookup"><span data-stu-id="67417-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="67417-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="67417-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="67417-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="67417-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="67417-114">Descrição do tipo de função.</span><span class="sxs-lookup"><span data-stu-id="67417-114">Role type description.</span></span> <span data-ttu-id="67417-115">Há quatro funções disponíveis:</span><span class="sxs-lookup"><span data-stu-id="67417-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="67417-116">Membro: membro da sala de bate-papo</span><span class="sxs-lookup"><span data-stu-id="67417-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="67417-117">Gerente: gerente da sala de Chat</span><span class="sxs-lookup"><span data-stu-id="67417-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="67417-118">Com voz: Apresentador para uma sala de bate-papo de auditório</span><span class="sxs-lookup"><span data-stu-id="67417-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="67417-119">Criador: Pode criar salas de chat</span><span class="sxs-lookup"><span data-stu-id="67417-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="67417-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="67417-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="67417-121">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="67417-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="67417-122">Permissão definido para a função.</span><span class="sxs-lookup"><span data-stu-id="67417-122">Permission set for the role.</span></span> <span data-ttu-id="67417-123">Os bits usados são:</span><span class="sxs-lookup"><span data-stu-id="67417-123">The used bits are:</span></span> <br/>  <span data-ttu-id="67417-124">2: true se a função puder gerenciar nós.</span><span class="sxs-lookup"><span data-stu-id="67417-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="67417-125">4: true se a função puder criar nós filhos.</span><span class="sxs-lookup"><span data-stu-id="67417-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="67417-126">7: true se a função pode ingressar em uma sala de chat (ou salas de bate-papo filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="67417-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="67417-127">8: true se a função puder conversar em uma sala de chat (ou nas salas filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="67417-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="67417-128">10: true se a função puder ler o histórico do chat mesmo quando não está vinculada a uma sala de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="67417-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="67417-129">11: true se a função pode ver a sala de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="67417-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="67417-130">(Isso é ainda mais refinado por fatores como escopo e visibilidade.)</span><span class="sxs-lookup"><span data-stu-id="67417-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="67417-131">12: true se a função puder conversar em uma sala de bate-papo de auditório.</span><span class="sxs-lookup"><span data-stu-id="67417-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="67417-132">13: true se a função puder ignorar as regras de visibilidade ao exibir nós.</span><span class="sxs-lookup"><span data-stu-id="67417-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="67417-133">**Chave**</span><span class="sxs-lookup"><span data-stu-id="67417-133">**Key**</span></span>

|<span data-ttu-id="67417-134">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="67417-134">**Column**</span></span>|<span data-ttu-id="67417-135">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="67417-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="67417-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="67417-136">rtypeID</span></span>  <br/> |<span data-ttu-id="67417-137">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="67417-137">Primary key.</span></span>  <br/> |
   

