---
title: tblLastChatId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 17a4ffbe-cca9-4ec5-ae46-38a15274889a
description: tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.
ms.openlocfilehash: 9d19c6c873660683ff526eb144d74b6e8752bf80
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929963"
---
# <a name="tbllastchatid"></a><span data-ttu-id="0eb5a-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="0eb5a-103">tblLastChatId</span></span>
 
<span data-ttu-id="0eb5a-104">tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="0eb5a-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="0eb5a-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="0eb5a-105">**Columns**</span></span>

|<span data-ttu-id="0eb5a-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0eb5a-106">**Column**</span></span>|<span data-ttu-id="0eb5a-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0eb5a-107">**Type**</span></span>|<span data-ttu-id="0eb5a-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0eb5a-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0eb5a-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="0eb5a-109">nodeID</span></span>  <br/> |<span data-ttu-id="0eb5a-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="0eb5a-110">int, not null</span></span>  <br/> |<span data-ttu-id="0eb5a-111">ID do nó (somente tipo sala de chat).</span><span class="sxs-lookup"><span data-stu-id="0eb5a-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="0eb5a-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="0eb5a-112">lastChatID</span></span>  <br/> |<span data-ttu-id="0eb5a-113">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="0eb5a-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="0eb5a-114">Último ID de chat usado.</span><span class="sxs-lookup"><span data-stu-id="0eb5a-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="0eb5a-115">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="0eb5a-115">**Keys**</span></span>

|<span data-ttu-id="0eb5a-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0eb5a-116">**Column**</span></span>|<span data-ttu-id="0eb5a-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0eb5a-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0eb5a-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="0eb5a-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="0eb5a-119">Chave primária (apenas o nodeID é suficiente para o processamento).</span><span class="sxs-lookup"><span data-stu-id="0eb5a-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="0eb5a-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="0eb5a-120">nodeID</span></span>  <br/> |<span data-ttu-id="0eb5a-121">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="0eb5a-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="0eb5a-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="0eb5a-122">See also</span></span>

[<span data-ttu-id="0eb5a-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="0eb5a-123">tblChat</span></span>](tblchat.md)
