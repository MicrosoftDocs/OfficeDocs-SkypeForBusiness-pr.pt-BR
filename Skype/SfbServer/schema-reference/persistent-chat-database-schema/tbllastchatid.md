---
title: tblLastChatId
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
ms.openlocfilehash: 4a22dc9ba1c2dbe15ae0a24de6e4f347a62deaee
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastchatid"></a><span data-ttu-id="bf918-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="bf918-103">tblLastChatId</span></span>
 
<span data-ttu-id="bf918-104">tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="bf918-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="bf918-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="bf918-105">**Columns**</span></span>

|<span data-ttu-id="bf918-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="bf918-106">**Column**</span></span>|<span data-ttu-id="bf918-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="bf918-107">**Type**</span></span>|<span data-ttu-id="bf918-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="bf918-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="bf918-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="bf918-109">nodeID</span></span>  <br/> |<span data-ttu-id="bf918-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="bf918-110">int, not null</span></span>  <br/> |<span data-ttu-id="bf918-111">ID do nó (somente tipo sala de chat).</span><span class="sxs-lookup"><span data-stu-id="bf918-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="bf918-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="bf918-112">lastChatID</span></span>  <br/> |<span data-ttu-id="bf918-113">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="bf918-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="bf918-114">Último ID de chat usado.</span><span class="sxs-lookup"><span data-stu-id="bf918-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="bf918-115">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="bf918-115">**Keys**</span></span>

|<span data-ttu-id="bf918-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="bf918-116">**Column**</span></span>|<span data-ttu-id="bf918-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="bf918-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="bf918-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="bf918-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="bf918-119">Chave primária (apenas o nodeID é suficiente para o processamento).</span><span class="sxs-lookup"><span data-stu-id="bf918-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="bf918-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="bf918-120">nodeID</span></span>  <br/> |<span data-ttu-id="bf918-121">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="bf918-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="bf918-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="bf918-122">See also</span></span>

#### 

[<span data-ttu-id="bf918-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="bf918-123">tblChat</span></span>](tblchat.md)

