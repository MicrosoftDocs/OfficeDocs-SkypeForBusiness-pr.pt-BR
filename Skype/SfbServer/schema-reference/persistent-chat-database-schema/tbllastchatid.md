---
title: tblLastChatId
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
ms.openlocfilehash: 3208ada77643957295f9894cb58187c2b4bc7493
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884926"
---
# <a name="tbllastchatid"></a><span data-ttu-id="07b8b-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="07b8b-103">tblLastChatId</span></span>
 
<span data-ttu-id="07b8b-104">tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="07b8b-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="07b8b-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="07b8b-105">**Columns**</span></span>

|<span data-ttu-id="07b8b-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="07b8b-106">**Column**</span></span>|<span data-ttu-id="07b8b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="07b8b-107">**Type**</span></span>|<span data-ttu-id="07b8b-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="07b8b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="07b8b-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="07b8b-109">nodeID</span></span>  <br/> |<span data-ttu-id="07b8b-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="07b8b-110">int, not null</span></span>  <br/> |<span data-ttu-id="07b8b-111">ID do nó (somente tipo sala de chat).</span><span class="sxs-lookup"><span data-stu-id="07b8b-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="07b8b-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="07b8b-112">lastChatID</span></span>  <br/> |<span data-ttu-id="07b8b-113">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="07b8b-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="07b8b-114">Último ID de chat usado.</span><span class="sxs-lookup"><span data-stu-id="07b8b-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="07b8b-115">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="07b8b-115">**Keys**</span></span>

|<span data-ttu-id="07b8b-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="07b8b-116">**Column**</span></span>|<span data-ttu-id="07b8b-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="07b8b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="07b8b-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="07b8b-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="07b8b-119">Chave primária (apenas o nodeID é suficiente para o processamento).</span><span class="sxs-lookup"><span data-stu-id="07b8b-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="07b8b-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="07b8b-120">nodeID</span></span>  <br/> |<span data-ttu-id="07b8b-121">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="07b8b-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="07b8b-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="07b8b-122">See also</span></span>

[<span data-ttu-id="07b8b-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="07b8b-123">tblChat</span></span>](tblchat.md)
