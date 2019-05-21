---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: o tblActivePeers contém as conexões ponto-a-ponto atuais entre os serviços de chat.
ms.openlocfilehash: f45a04019cafc2304baf825b5000e96ca7a6cead
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295542"
---
# <a name="tblactivepeers"></a><span data-ttu-id="c9b52-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="c9b52-103">tblActivePeers</span></span>
 
<span data-ttu-id="c9b52-104">o tblActivePeers contém as conexões ponto-a-ponto atuais entre os serviços de chat.</span><span class="sxs-lookup"><span data-stu-id="c9b52-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="c9b52-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="c9b52-105">**Columns**</span></span>

|<span data-ttu-id="c9b52-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c9b52-106">**Column**</span></span>|<span data-ttu-id="c9b52-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c9b52-107">**Type**</span></span>|<span data-ttu-id="c9b52-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c9b52-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9b52-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="c9b52-109">aplServerID</span></span>  <br/> |<span data-ttu-id="c9b52-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="c9b52-110">int, not null</span></span>  <br/> |<span data-ttu-id="c9b52-111">ID do servidor que postou a entrada.</span><span class="sxs-lookup"><span data-stu-id="c9b52-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="c9b52-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="c9b52-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="c9b52-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="c9b52-113">int, not null</span></span>  <br/> |<span data-ttu-id="c9b52-114">ID do par ao qual o servidor de postagem está conectado.</span><span class="sxs-lookup"><span data-stu-id="c9b52-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="c9b52-115">**As**</span><span class="sxs-lookup"><span data-stu-id="c9b52-115">**Keys**</span></span>

|<span data-ttu-id="c9b52-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c9b52-116">**Column**</span></span>|<span data-ttu-id="c9b52-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c9b52-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9b52-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="c9b52-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="c9b52-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="c9b52-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c9b52-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="c9b52-120">aplServerID</span></span>  <br/> |<span data-ttu-id="c9b52-121">Chave estrangeira com Lookup na tabela tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="c9b52-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="c9b52-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="c9b52-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="c9b52-123">Chave estrangeira com Lookup na tabela tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="c9b52-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

