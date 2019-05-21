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
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
ms.openlocfilehash: f14d8090fd3252d88ef747de93a987f51870a63b
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295395"
---
# <a name="tbllastchatid"></a><span data-ttu-id="537f5-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="537f5-103">tblLastChatId</span></span>
 
<span data-ttu-id="537f5-104">tblLastChatId contém a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="537f5-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="537f5-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="537f5-105">**Columns**</span></span>

|<span data-ttu-id="537f5-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="537f5-106">**Column**</span></span>|<span data-ttu-id="537f5-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="537f5-107">**Type**</span></span>|<span data-ttu-id="537f5-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="537f5-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="537f5-109">NodeId</span><span class="sxs-lookup"><span data-stu-id="537f5-109">nodeID</span></span>  <br/> |<span data-ttu-id="537f5-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="537f5-110">int, not null</span></span>  <br/> |<span data-ttu-id="537f5-111">ID do nó (somente sala de chat-tipo).</span><span class="sxs-lookup"><span data-stu-id="537f5-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="537f5-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="537f5-112">lastChatID</span></span>  <br/> |<span data-ttu-id="537f5-113">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="537f5-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="537f5-114">ID do Chat usado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="537f5-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="537f5-115">**As**</span><span class="sxs-lookup"><span data-stu-id="537f5-115">**Keys**</span></span>

|<span data-ttu-id="537f5-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="537f5-116">**Column**</span></span>|<span data-ttu-id="537f5-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="537f5-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="537f5-118">\<NodeId, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="537f5-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="537f5-119">Chave primária (apenas NodeId é suficiente para processamento).</span><span class="sxs-lookup"><span data-stu-id="537f5-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="537f5-120">NodeId</span><span class="sxs-lookup"><span data-stu-id="537f5-120">nodeID</span></span>  <br/> |<span data-ttu-id="537f5-121">Chave estrangeira com Lookup na tabela tblNode. NodeId.</span><span class="sxs-lookup"><span data-stu-id="537f5-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="537f5-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="537f5-122">See also</span></span>

[<span data-ttu-id="537f5-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="537f5-123">tblChat</span></span>](tblchat.md)
