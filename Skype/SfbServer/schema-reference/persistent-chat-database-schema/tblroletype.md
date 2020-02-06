---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.
ms.openlocfilehash: 888628c1aca01e90694ed946569a81b1b7394b95
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812899"
---
# <a name="tblroletype"></a><span data-ttu-id="6afde-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="6afde-103">tblRoleType</span></span>
 
<span data-ttu-id="6afde-104">tblRoleType é uma tabela de pesquisa estática com tipos de função e seus conjuntos de permissões associados.</span><span class="sxs-lookup"><span data-stu-id="6afde-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="6afde-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="6afde-105">**Columns**</span></span>

|<span data-ttu-id="6afde-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6afde-106">**Column**</span></span>|<span data-ttu-id="6afde-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6afde-107">**Type**</span></span>|<span data-ttu-id="6afde-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6afde-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6afde-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="6afde-109">rtypeID</span></span>  <br/> |<span data-ttu-id="6afde-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6afde-110">int, not null</span></span>  <br/> |<span data-ttu-id="6afde-111">ID do tipo de função.</span><span class="sxs-lookup"><span data-stu-id="6afde-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="6afde-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="6afde-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="6afde-113">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6afde-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="6afde-114">Descrição do tipo de função.</span><span class="sxs-lookup"><span data-stu-id="6afde-114">Role type description.</span></span> <span data-ttu-id="6afde-115">Há quatro funções disponíveis:</span><span class="sxs-lookup"><span data-stu-id="6afde-115">There are four available roles:</span></span> <br/>  <span data-ttu-id="6afde-116">Membro: membro da sala de chat</span><span class="sxs-lookup"><span data-stu-id="6afde-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="6afde-117">Manager: gerente da sala de chat</span><span class="sxs-lookup"><span data-stu-id="6afde-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="6afde-118">Encaixado: apresentador para uma sala de chat do Auditorium</span><span class="sxs-lookup"><span data-stu-id="6afde-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="6afde-119">Creator: pode criar salas de chat</span><span class="sxs-lookup"><span data-stu-id="6afde-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="6afde-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="6afde-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="6afde-121">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="6afde-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="6afde-122">Conjunto de permissões para a função.</span><span class="sxs-lookup"><span data-stu-id="6afde-122">Permission set for the role.</span></span> <span data-ttu-id="6afde-123">Os bits usados são:</span><span class="sxs-lookup"><span data-stu-id="6afde-123">The used bits are:</span></span> <br/>  <span data-ttu-id="6afde-124">2: verdadeiro se a função puder gerenciar nós.</span><span class="sxs-lookup"><span data-stu-id="6afde-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="6afde-125">4: verdadeiro se a função puder criar nós filhos.</span><span class="sxs-lookup"><span data-stu-id="6afde-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="6afde-126">7: verdadeiro se a função puder ingressar em uma sala de chat (ou salas de chat dos filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="6afde-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="6afde-127">8: verdadeiro se a função puder conversar em uma sala de chat (ou nas salas de chat dos filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="6afde-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="6afde-128">10: verdadeiro se a função puder ler o histórico de chats mesmo quando não estiver associado a uma sala de chat.</span><span class="sxs-lookup"><span data-stu-id="6afde-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="6afde-129">11: verdadeiro se a função puder ver a sala de chat.</span><span class="sxs-lookup"><span data-stu-id="6afde-129">11: True if the role can see the chat room.</span></span> <span data-ttu-id="6afde-130">(Isso é ainda mais refinado por fatores como escopo e visibilidade.)</span><span class="sxs-lookup"><span data-stu-id="6afde-130">(This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="6afde-131">12: verdadeiro se a função puder conversar em uma sala de chat do Auditorium.</span><span class="sxs-lookup"><span data-stu-id="6afde-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="6afde-132">13: verdadeiro se a função puder ignorar as regras de visibilidade ao exibir nós.</span><span class="sxs-lookup"><span data-stu-id="6afde-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="6afde-133">**Chave**</span><span class="sxs-lookup"><span data-stu-id="6afde-133">**Key**</span></span>

|<span data-ttu-id="6afde-134">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6afde-134">**Column**</span></span>|<span data-ttu-id="6afde-135">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6afde-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6afde-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="6afde-136">rtypeID</span></span>  <br/> |<span data-ttu-id="6afde-137">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="6afde-137">Primary key.</span></span>  <br/> |
   

