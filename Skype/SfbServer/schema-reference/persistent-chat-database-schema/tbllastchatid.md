---
title: tblLastChatId
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
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
ms.openlocfilehash: 95498f077948e1b400d0a370762c121def703e8c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814579"
---
# <a name="tbllastchatid"></a><span data-ttu-id="39cc8-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="39cc8-103">tblLastChatId</span></span>
 
<span data-ttu-id="39cc8-104">tblLastChatId contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="39cc8-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="39cc8-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="39cc8-105">**Columns**</span></span>

|<span data-ttu-id="39cc8-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="39cc8-106">**Column**</span></span>|<span data-ttu-id="39cc8-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="39cc8-107">**Type**</span></span>|<span data-ttu-id="39cc8-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="39cc8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="39cc8-109">NodeId</span><span class="sxs-lookup"><span data-stu-id="39cc8-109">nodeID</span></span>  <br/> |<span data-ttu-id="39cc8-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="39cc8-110">int, not null</span></span>  <br/> |<span data-ttu-id="39cc8-111">ID do nó (somente sala de chat-tipo).</span><span class="sxs-lookup"><span data-stu-id="39cc8-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="39cc8-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="39cc8-112">lastChatID</span></span>  <br/> |<span data-ttu-id="39cc8-113">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="39cc8-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="39cc8-114">ID do Chat usado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="39cc8-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="39cc8-115">**As**</span><span class="sxs-lookup"><span data-stu-id="39cc8-115">**Keys**</span></span>

|<span data-ttu-id="39cc8-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="39cc8-116">**Column**</span></span>|<span data-ttu-id="39cc8-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="39cc8-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="39cc8-118">\<NodeId, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="39cc8-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="39cc8-119">Chave primária (apenas NodeId é suficiente para processamento).</span><span class="sxs-lookup"><span data-stu-id="39cc8-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="39cc8-120">NodeId</span><span class="sxs-lookup"><span data-stu-id="39cc8-120">nodeID</span></span>  <br/> |<span data-ttu-id="39cc8-121">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="39cc8-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="39cc8-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="39cc8-122">See also</span></span>

[<span data-ttu-id="39cc8-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="39cc8-123">tblChat</span></span>](tblchat.md)
