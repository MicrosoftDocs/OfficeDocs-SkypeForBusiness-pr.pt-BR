---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
ms.openlocfilehash: 80664d6b296fce9b4909674f9d21b1aa13285826
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816001"
---
# <a name="tbllastchatid"></a><span data-ttu-id="e3eb9-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="e3eb9-103">tblLastChatId</span></span>
 
<span data-ttu-id="e3eb9-104">tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="e3eb9-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="e3eb9-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e3eb9-105">**Columns**</span></span>

|<span data-ttu-id="e3eb9-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e3eb9-106">**Column**</span></span>|<span data-ttu-id="e3eb9-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e3eb9-107">**Type**</span></span>|<span data-ttu-id="e3eb9-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e3eb9-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e3eb9-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="e3eb9-109">nodeID</span></span>  <br/> |<span data-ttu-id="e3eb9-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="e3eb9-110">int, not null</span></span>  <br/> |<span data-ttu-id="e3eb9-111">ID de nó (apenas para tipo de sala de chat).</span><span class="sxs-lookup"><span data-stu-id="e3eb9-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="e3eb9-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="e3eb9-112">lastChatID</span></span>  <br/> |<span data-ttu-id="e3eb9-113">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="e3eb9-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="e3eb9-114">Último ID de chat usado.</span><span class="sxs-lookup"><span data-stu-id="e3eb9-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="e3eb9-115">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="e3eb9-115">**Keys**</span></span>

|<span data-ttu-id="e3eb9-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e3eb9-116">**Column**</span></span>|<span data-ttu-id="e3eb9-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e3eb9-117">**Description**</span></span>|
|:-----|:-----|
|\<nodeID, lastChatID\>  <br/> |<span data-ttu-id="e3eb9-118">Chave primária (apenas o nodeID é suficiente para o processamento).</span><span class="sxs-lookup"><span data-stu-id="e3eb9-118">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="e3eb9-119">nodeID</span><span class="sxs-lookup"><span data-stu-id="e3eb9-119">nodeID</span></span>  <br/> |<span data-ttu-id="e3eb9-120">Chave estrangeira com pesquisa na tabela tblNode.nodeID.</span><span class="sxs-lookup"><span data-stu-id="e3eb9-120">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="e3eb9-121">Confira também</span><span class="sxs-lookup"><span data-stu-id="e3eb9-121">See also</span></span>

[<span data-ttu-id="e3eb9-122">tblChat</span><span class="sxs-lookup"><span data-stu-id="e3eb9-122">tblChat</span></span>](tblchat.md)
