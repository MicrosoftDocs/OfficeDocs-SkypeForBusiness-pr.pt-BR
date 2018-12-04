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
ms.openlocfilehash: dc25eb68ee1b4069ba54133548f743ca45b73e16
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19505082"
---
# <a name="tbllastchatid"></a><span data-ttu-id="89aa4-103">tblLastChatId</span><span class="sxs-lookup"><span data-stu-id="89aa4-103">tblLastChatId</span></span>
 
<span data-ttu-id="89aa4-104">tblLastChatId inclui a última ID de chat que foi gerada (e usada na tabela tblChat) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="89aa4-104">tblLastChatId contains the last chat ID that was generated (and used in the tblChat table) for each user.</span></span>
  
<span data-ttu-id="89aa4-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="89aa4-105">**Columns**</span></span>

|<span data-ttu-id="89aa4-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="89aa4-106">**Column**</span></span>|<span data-ttu-id="89aa4-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="89aa4-107">**Type**</span></span>|<span data-ttu-id="89aa4-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="89aa4-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89aa4-109">nodeID</span><span class="sxs-lookup"><span data-stu-id="89aa4-109">nodeID</span></span>  <br/> |<span data-ttu-id="89aa4-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="89aa4-110">int, not null</span></span>  <br/> |<span data-ttu-id="89aa4-111">ID do nó (somente tipo sala de chat).</span><span class="sxs-lookup"><span data-stu-id="89aa4-111">Node ID (chat room-type only).</span></span>  <br/> |
|<span data-ttu-id="89aa4-112">lastChatID</span><span class="sxs-lookup"><span data-stu-id="89aa4-112">lastChatID</span></span>  <br/> |<span data-ttu-id="89aa4-113">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="89aa4-113">bigint, not null</span></span>  <br/> |<span data-ttu-id="89aa4-114">Último ID de chat usado.</span><span class="sxs-lookup"><span data-stu-id="89aa4-114">Last used chat ID.</span></span>  <br/> |
   
<span data-ttu-id="89aa4-115">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="89aa4-115">**Keys**</span></span>

|<span data-ttu-id="89aa4-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="89aa4-116">**Column**</span></span>|<span data-ttu-id="89aa4-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="89aa4-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="89aa4-118">\<nodeID, lastChatID\></span><span class="sxs-lookup"><span data-stu-id="89aa4-118">\<nodeID, lastChatID\></span></span>  <br/> |<span data-ttu-id="89aa4-119">Chave primária (apenas o nodeID é suficiente para o processamento).</span><span class="sxs-lookup"><span data-stu-id="89aa4-119">Primary key (just nodeID is sufficient for processing).</span></span>  <br/> |
|<span data-ttu-id="89aa4-120">nodeID</span><span class="sxs-lookup"><span data-stu-id="89aa4-120">nodeID</span></span>  <br/> |<span data-ttu-id="89aa4-121">Chave estrangeira com pesquisa na tabela Tblnode.</span><span class="sxs-lookup"><span data-stu-id="89aa4-121">Foreign key with lookup in tblNode.nodeID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="89aa4-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="89aa4-122">See also</span></span>

[<span data-ttu-id="89aa4-123">tblChat</span><span class="sxs-lookup"><span data-stu-id="89aa4-123">tblChat</span></span>](tblchat.md)