---
title: tblActivePeers
ms.reviewer: ''
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
ms.openlocfilehash: e921d6faa4f7bcf3e3c6f6dc9859f4bd0db16bc5
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212674"
---
# <a name="tblactivepeers"></a><span data-ttu-id="222dd-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="222dd-103">tblActivePeers</span></span>
 
<span data-ttu-id="222dd-104">a tblActivePeers contém as conexões ponto a ponto atuais entre os serviços de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="222dd-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="222dd-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="222dd-105">**Columns**</span></span>

|<span data-ttu-id="222dd-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="222dd-106">**Column**</span></span>|<span data-ttu-id="222dd-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="222dd-107">**Type**</span></span>|<span data-ttu-id="222dd-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="222dd-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="222dd-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="222dd-109">aplServerID</span></span>  <br/> |<span data-ttu-id="222dd-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="222dd-110">int, not null</span></span>  <br/> |<span data-ttu-id="222dd-111">ID do servidor que postou a entrada.</span><span class="sxs-lookup"><span data-stu-id="222dd-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="222dd-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="222dd-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="222dd-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="222dd-113">int, not null</span></span>  <br/> |<span data-ttu-id="222dd-114">ID do ponto ao qual o servidor de postagem está conectado.</span><span class="sxs-lookup"><span data-stu-id="222dd-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="222dd-115">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="222dd-115">**Keys**</span></span>

|<span data-ttu-id="222dd-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="222dd-116">**Column**</span></span>|<span data-ttu-id="222dd-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="222dd-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="222dd-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="222dd-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="222dd-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="222dd-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="222dd-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="222dd-120">aplServerID</span></span>  <br/> |<span data-ttu-id="222dd-121">Chave estrangeira com pesquisa na tabela Tblserveridentity.</span><span class="sxs-lookup"><span data-stu-id="222dd-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="222dd-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="222dd-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="222dd-123">Chave estrangeira com pesquisa na tabela Tblserveridentity.</span><span class="sxs-lookup"><span data-stu-id="222dd-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

