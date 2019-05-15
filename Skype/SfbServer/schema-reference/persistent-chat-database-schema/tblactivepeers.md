---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: a tblActivePeers contém as conexões ponto a ponto atuais entre os serviços de bate-papo.
ms.openlocfilehash: 7d7f995b878d6e47878636bee6f9c16ac142352e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929872"
---
# <a name="tblactivepeers"></a><span data-ttu-id="51f6b-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="51f6b-103">tblActivePeers</span></span>
 
<span data-ttu-id="51f6b-104">a tblActivePeers contém as conexões ponto a ponto atuais entre os serviços de bate-papo.</span><span class="sxs-lookup"><span data-stu-id="51f6b-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="51f6b-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="51f6b-105">**Columns**</span></span>

|<span data-ttu-id="51f6b-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="51f6b-106">**Column**</span></span>|<span data-ttu-id="51f6b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="51f6b-107">**Type**</span></span>|<span data-ttu-id="51f6b-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="51f6b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="51f6b-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="51f6b-109">aplServerID</span></span>  <br/> |<span data-ttu-id="51f6b-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="51f6b-110">int, not null</span></span>  <br/> |<span data-ttu-id="51f6b-111">ID do servidor que postou a entrada.</span><span class="sxs-lookup"><span data-stu-id="51f6b-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="51f6b-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="51f6b-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="51f6b-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="51f6b-113">int, not null</span></span>  <br/> |<span data-ttu-id="51f6b-114">ID do ponto ao qual o servidor de postagem está conectado.</span><span class="sxs-lookup"><span data-stu-id="51f6b-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="51f6b-115">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="51f6b-115">**Keys**</span></span>

|<span data-ttu-id="51f6b-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="51f6b-116">**Column**</span></span>|<span data-ttu-id="51f6b-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="51f6b-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="51f6b-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="51f6b-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="51f6b-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="51f6b-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="51f6b-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="51f6b-120">aplServerID</span></span>  <br/> |<span data-ttu-id="51f6b-121">Chave estrangeira com pesquisa na tabela Tblserveridentity.</span><span class="sxs-lookup"><span data-stu-id="51f6b-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="51f6b-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="51f6b-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="51f6b-123">Chave estrangeira com pesquisa na tabela Tblserveridentity.</span><span class="sxs-lookup"><span data-stu-id="51f6b-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

