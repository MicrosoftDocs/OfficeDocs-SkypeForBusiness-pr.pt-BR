---
title: tblActivePeers
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: a tblActivePeers contém as conexões ponto a ponto atuais entre os serviços de bate-papo.
ms.openlocfilehash: 5dc585a8db67c1bbdcc1c3933018b1296fd75484
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblactivepeers"></a><span data-ttu-id="feb5c-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="feb5c-103">tblActivePeers</span></span>
 
<span data-ttu-id="feb5c-104">a tblActivePeers contém as conexões ponto a ponto atuais entre os serviços de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="feb5c-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="feb5c-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="feb5c-105">**Columns**</span></span>

|<span data-ttu-id="feb5c-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="feb5c-106">**Column**</span></span>|<span data-ttu-id="feb5c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="feb5c-107">**Type**</span></span>|<span data-ttu-id="feb5c-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="feb5c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="feb5c-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="feb5c-109">aplServerID</span></span>  <br/> |<span data-ttu-id="feb5c-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="feb5c-110">int, not null</span></span>  <br/> |<span data-ttu-id="feb5c-111">ID do servidor que postou a entrada.</span><span class="sxs-lookup"><span data-stu-id="feb5c-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="feb5c-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="feb5c-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="feb5c-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="feb5c-113">int, not null</span></span>  <br/> |<span data-ttu-id="feb5c-114">ID do ponto ao qual o servidor de postagem está conectado.</span><span class="sxs-lookup"><span data-stu-id="feb5c-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="feb5c-115">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="feb5c-115">**Keys**</span></span>

|<span data-ttu-id="feb5c-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="feb5c-116">**Column**</span></span>|<span data-ttu-id="feb5c-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="feb5c-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="feb5c-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="feb5c-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="feb5c-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="feb5c-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="feb5c-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="feb5c-120">aplServerID</span></span>  <br/> |<span data-ttu-id="feb5c-121">Chave estrangeira com pesquisa na tabela Tblserveridentity.</span><span class="sxs-lookup"><span data-stu-id="feb5c-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="feb5c-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="feb5c-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="feb5c-123">Chave estrangeira com pesquisa na tabela Tblserveridentity.</span><span class="sxs-lookup"><span data-stu-id="feb5c-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

