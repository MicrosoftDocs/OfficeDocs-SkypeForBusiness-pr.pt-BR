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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: o tblActivePeers contém as conexões ponto-a-ponto atuais entre os serviços de chat.
ms.openlocfilehash: 4604c13dbff9565748dd59e5917a5c133bd71947
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814709"
---
# <a name="tblactivepeers"></a><span data-ttu-id="e1869-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="e1869-103">tblActivePeers</span></span>
 
<span data-ttu-id="e1869-104">o tblActivePeers contém as conexões ponto-a-ponto atuais entre os serviços de chat.</span><span class="sxs-lookup"><span data-stu-id="e1869-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="e1869-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="e1869-105">**Columns**</span></span>

|<span data-ttu-id="e1869-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e1869-106">**Column**</span></span>|<span data-ttu-id="e1869-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e1869-107">**Type**</span></span>|<span data-ttu-id="e1869-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e1869-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e1869-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="e1869-109">aplServerID</span></span>  <br/> |<span data-ttu-id="e1869-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="e1869-110">int, not null</span></span>  <br/> |<span data-ttu-id="e1869-111">ID do servidor que postou a entrada.</span><span class="sxs-lookup"><span data-stu-id="e1869-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="e1869-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="e1869-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="e1869-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="e1869-113">int, not null</span></span>  <br/> |<span data-ttu-id="e1869-114">ID do par ao qual o servidor de postagem está conectado.</span><span class="sxs-lookup"><span data-stu-id="e1869-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="e1869-115">**As**</span><span class="sxs-lookup"><span data-stu-id="e1869-115">**Keys**</span></span>

|<span data-ttu-id="e1869-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e1869-116">**Column**</span></span>|<span data-ttu-id="e1869-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e1869-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="e1869-118">\<aplServerID, aplPeerID\></span><span class="sxs-lookup"><span data-stu-id="e1869-118">\<aplServerID, aplPeerID\></span></span>  <br/> |<span data-ttu-id="e1869-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="e1869-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="e1869-120">aplServerID</span><span class="sxs-lookup"><span data-stu-id="e1869-120">aplServerID</span></span>  <br/> |<span data-ttu-id="e1869-121">Chave estrangeira com Lookup na tabela tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="e1869-121">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="e1869-122">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="e1869-122">aplPeerID</span></span>  <br/> |<span data-ttu-id="e1869-123">Chave estrangeira com Lookup na tabela tblServerIdentity. serverID.</span><span class="sxs-lookup"><span data-stu-id="e1869-123">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

