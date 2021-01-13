---
title: tblRoleType
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
ms.assetid: 1eac3a54-656a-40ac-b771-edfc64d6e34b
description: tblRoleType é uma tabela de pesquisa estática com tipos de funções e seus conjuntos de permissões associados.
ms.openlocfilehash: c440463d822b908a89c84eb9c85b70e9daf442be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831521"
---
# <a name="tblroletype"></a><span data-ttu-id="80ed0-103">tblRoleType</span><span class="sxs-lookup"><span data-stu-id="80ed0-103">tblRoleType</span></span>
 
<span data-ttu-id="80ed0-104">tblRoleType é uma tabela de pesquisa estática com tipos de funções e seus conjuntos de permissões associados.</span><span class="sxs-lookup"><span data-stu-id="80ed0-104">tblRoleType is a static lookup table with role types and their associated permission sets.</span></span>
  
<span data-ttu-id="80ed0-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="80ed0-105">**Columns**</span></span>

|<span data-ttu-id="80ed0-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="80ed0-106">**Column**</span></span>|<span data-ttu-id="80ed0-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="80ed0-107">**Type**</span></span>|<span data-ttu-id="80ed0-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="80ed0-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="80ed0-109">rtypeID</span><span class="sxs-lookup"><span data-stu-id="80ed0-109">rtypeID</span></span>  <br/> |<span data-ttu-id="80ed0-110">int, not null</span><span class="sxs-lookup"><span data-stu-id="80ed0-110">int, not null</span></span>  <br/> |<span data-ttu-id="80ed0-111">ID do tipo de função.</span><span class="sxs-lookup"><span data-stu-id="80ed0-111">Role type ID.</span></span>  <br/> |
|<span data-ttu-id="80ed0-112">rtypeDesc</span><span class="sxs-lookup"><span data-stu-id="80ed0-112">rtypeDesc</span></span>  <br/> |<span data-ttu-id="80ed0-113">nvarchar (256), not null</span><span class="sxs-lookup"><span data-stu-id="80ed0-113">nvarchar (256), not null</span></span>  <br/> | <span data-ttu-id="80ed0-p101">Descrição do tipo de função. Existem quatro funções disponíveis:</span><span class="sxs-lookup"><span data-stu-id="80ed0-p101">Role type description. There are four available roles:</span></span> <br/>  <span data-ttu-id="80ed0-116">Membro: Membro da sala de chat</span><span class="sxs-lookup"><span data-stu-id="80ed0-116">Member: Chat room member</span></span> <br/>  <span data-ttu-id="80ed0-117">Gerente: Gerente da sala de chat</span><span class="sxs-lookup"><span data-stu-id="80ed0-117">Manager: Chat room manager</span></span> <br/>  <span data-ttu-id="80ed0-118">Com voz: Apresentador para uma sala de chat de auditório</span><span class="sxs-lookup"><span data-stu-id="80ed0-118">Voiced: Presenter for an auditorium chat room</span></span> <br/>  <span data-ttu-id="80ed0-119">Criador: Pode criar salas de bate-papo</span><span class="sxs-lookup"><span data-stu-id="80ed0-119">Creator: Can create chat rooms</span></span> <br/> |
|<span data-ttu-id="80ed0-120">rtypeAllowedPermSet</span><span class="sxs-lookup"><span data-stu-id="80ed0-120">rtypeAllowedPermSet</span></span>  <br/> |<span data-ttu-id="80ed0-121">bigint, not null</span><span class="sxs-lookup"><span data-stu-id="80ed0-121">bigint, not null</span></span>  <br/> | <span data-ttu-id="80ed0-p102">Permissão configurada para a função. Os bits usados são:</span><span class="sxs-lookup"><span data-stu-id="80ed0-p102">Permission set for the role. The used bits are:</span></span> <br/>  <span data-ttu-id="80ed0-124">2: True se a função puder gerenciar nós.</span><span class="sxs-lookup"><span data-stu-id="80ed0-124">2: True if the role can manage nodes.</span></span> <br/>  <span data-ttu-id="80ed0-125">4: True se a função puder criar nós filhos.</span><span class="sxs-lookup"><span data-stu-id="80ed0-125">4: True if the role can create children nodes.</span></span> <br/>  <span data-ttu-id="80ed0-126">7: True se a função puder entrar em uma sala de chat (ou nas salas filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="80ed0-126">7: True if the role can join a chat room (or children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="80ed0-127">8: True se a função puder conversar em uma sala de chat (ou nas salas filhos de uma categoria).</span><span class="sxs-lookup"><span data-stu-id="80ed0-127">8: True if the role can chat in a chat room (or in children chat rooms of a category).</span></span> <br/>  <span data-ttu-id="80ed0-128">10: True se a função puder ler o histórico do chat mesmo quando não tiver entrado na sala de chat.</span><span class="sxs-lookup"><span data-stu-id="80ed0-128">10: True if the role can read chat history even when not joined to a chat room.</span></span> <br/>  <span data-ttu-id="80ed0-p103">11: True se a função puder ver a sala de chat (refinado por fatores como escopo e visibilidade).</span><span class="sxs-lookup"><span data-stu-id="80ed0-p103">11: True if the role can see the chat room. (This is further refined by factors such as scope and visibility.)</span></span> <br/>  <span data-ttu-id="80ed0-131">12: True se a função puder conversar em uma sala de chat de auditório.</span><span class="sxs-lookup"><span data-stu-id="80ed0-131">12: True if the role can chat in an auditorium chat room.</span></span> <br/>  <span data-ttu-id="80ed0-132">13: True se a função puder ignorar as regras de visibilidade ao exibir nós.</span><span class="sxs-lookup"><span data-stu-id="80ed0-132">13: True if the role can bypass visibility rules when viewing nodes.</span></span> <br/> |
   
<span data-ttu-id="80ed0-133">**Chave**</span><span class="sxs-lookup"><span data-stu-id="80ed0-133">**Key**</span></span>

|<span data-ttu-id="80ed0-134">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="80ed0-134">**Column**</span></span>|<span data-ttu-id="80ed0-135">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="80ed0-135">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="80ed0-136">rtypeID</span><span class="sxs-lookup"><span data-stu-id="80ed0-136">rtypeID</span></span>  <br/> |<span data-ttu-id="80ed0-137">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="80ed0-137">Primary key.</span></span>  <br/> |
   

