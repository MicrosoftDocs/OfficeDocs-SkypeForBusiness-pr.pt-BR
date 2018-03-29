---
title: tblRoleType
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.
ms.openlocfilehash: 2a380539c547f4ba6eb911f7e5247056c59a73ca
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblroletype"></a><span data-ttu-id="0349f-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="0349f-103">tblRoleType</span></span>
 
<span data-ttu-id="0349f-104">tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.</span><span class="sxs-lookup"><span data-stu-id="0349f-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="0349f-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="0349f-105">**Columns**</span></span>

|<span data-ttu-id="0349f-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0349f-106">**Column**</span></span>|<span data-ttu-id="0349f-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0349f-107">**Type**</span></span>|<span data-ttu-id="0349f-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0349f-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0349f-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="0349f-109">rtypeID</span></span>  <br/> |<span data-ttu-id="0349f-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="0349f-110">int, not null</span></span>  <br/> |<span data-ttu-id="0349f-111">ID do tipo de função.</span><span class="sxs-lookup"><span data-stu-id="0349f-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="0349f-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="0349f-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="0349f-113">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="0349f-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="0349f-114">Descrição do tipo de função.</span><span class="sxs-lookup"><span data-stu-id="0349f-114">Role type description.</span></span> <span data-ttu-id="0349f-115">Há quatro funções disponíveis:</span><span class="sxs-lookup"><span data-stu-id="0349f-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="0349f-116">Membro: membro da sala de bate-papo</span><span class="sxs-lookup"><span data-stu-id="0349f-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="0349f-117">Gerente: gerente da sala de Chat</span><span class="sxs-lookup"><span data-stu-id="0349f-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="0349f-118">Com voz: Apresentador para uma sala de bate-papo de auditório</span><span class="sxs-lookup"><span data-stu-id="0349f-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="0349f-119">Criador: Pode criar salas de chat</span><span class="sxs-lookup"><span data-stu-id="0349f-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="0349f-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="0349f-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="0349f-121">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="0349f-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="0349f-122">Permissão definido para a função.</span><span class="sxs-lookup"><span data-stu-id="0349f-122">Permission set for the role.</span></span> <span data-ttu-id="0349f-123">Os bits usados são:</span><span class="sxs-lookup"><span data-stu-id="0349f-123">The used bits are:</span></span> <br/>  <span data-ttu-id="0349f-124">2: true se a função puder gerenciar nós.</span><span class="sxs-lookup"><span data-stu-id="0349f-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="0349f-125">4: true se a função puder criar nós filhos.</span><span class="sxs-lookup"><span data-stu-id="0349f-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="0349f-126">7: true se a função pode ingressar em uma sala de chat (ou salas de bate-papo filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="0349f-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="0349f-127">8: true se a função puder conversar em uma sala de chat (ou nas salas filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="0349f-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="0349f-128">10: true se a função puder ler o histórico do chat mesmo quando não está vinculada a uma sala de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="0349f-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="0349f-129">11: true se a função pode ver a sala de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="0349f-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="0349f-130">(Isso é ainda mais refinado por fatores como escopo e visibilidade.)</span><span class="sxs-lookup"><span data-stu-id="0349f-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="0349f-131">12: true se a função puder conversar em uma sala de bate-papo de auditório.</span><span class="sxs-lookup"><span data-stu-id="0349f-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="0349f-132">13: true se a função puder ignorar as regras de visibilidade ao exibir nós.</span><span class="sxs-lookup"><span data-stu-id="0349f-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="0349f-133">**Chave**</span><span class="sxs-lookup"><span data-stu-id="0349f-133">**Key**</span></span>

|<span data-ttu-id="0349f-134">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0349f-134">**Column**</span></span>|<span data-ttu-id="0349f-135">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0349f-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0349f-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="0349f-136">rtypeID</span></span>  <br/> |<span data-ttu-id="0349f-137">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="0349f-137">Primary key.</span></span>  <br/> |
   

