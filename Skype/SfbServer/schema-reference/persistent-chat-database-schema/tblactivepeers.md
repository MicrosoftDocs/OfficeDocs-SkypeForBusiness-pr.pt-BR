---
title: tblActivePeers
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b50c3f4a-bab6-4cb9-b40e-016cf1a9c607
description: A tblActivePeers contém as conexões ponto a ponto atuais entre Servidores de Canal.
ms.openlocfilehash: befba4086a78281fbfbec1e270b7c8e3f8174752
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49812931"
---
# <a name="tblactivepeers"></a><span data-ttu-id="59843-103">tblActivePeers</span><span class="sxs-lookup"><span data-stu-id="59843-103">tblActivePeers</span></span>
 
<span data-ttu-id="59843-104">A tblActivePeers contém as conexões ponto a ponto atuais entre Servidores de Canal.</span><span class="sxs-lookup"><span data-stu-id="59843-104">tblActivePeers contains the current peer-to-peer connections between chat services.</span></span>
  
<span data-ttu-id="59843-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="59843-105">**Columns**</span></span>

|<span data-ttu-id="59843-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="59843-106">**Column**</span></span>|<span data-ttu-id="59843-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="59843-107">**Type**</span></span>|<span data-ttu-id="59843-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="59843-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="59843-109">aplServerID</span><span class="sxs-lookup"><span data-stu-id="59843-109">aplServerID</span></span>  <br/> |<span data-ttu-id="59843-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="59843-110">int, not null</span></span>  <br/> |<span data-ttu-id="59843-111">ID do servidor que postou a entrada.</span><span class="sxs-lookup"><span data-stu-id="59843-111">ID of the server that posted the entry.</span></span>  <br/> |
|<span data-ttu-id="59843-112">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="59843-112">aplPeerID</span></span>  <br/> |<span data-ttu-id="59843-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="59843-113">int, not null</span></span>  <br/> |<span data-ttu-id="59843-114">ID do ponto ao qual o servidor de postagem está conectado.</span><span class="sxs-lookup"><span data-stu-id="59843-114">ID of the peer that the posting server is connected to.</span></span>  <br/> |
   
<span data-ttu-id="59843-115">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="59843-115">**Keys**</span></span>

|<span data-ttu-id="59843-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="59843-116">**Column**</span></span>|<span data-ttu-id="59843-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="59843-117">**Description**</span></span>|
|:-----|:-----|
|\<aplServerID, aplPeerID\>  <br/> |<span data-ttu-id="59843-118">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="59843-118">Primary key.</span></span>  <br/> |
|<span data-ttu-id="59843-119">aplServerID</span><span class="sxs-lookup"><span data-stu-id="59843-119">aplServerID</span></span>  <br/> |<span data-ttu-id="59843-120">Chave estrangeira com pesquisa na tabela tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="59843-120">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
|<span data-ttu-id="59843-121">aplPeerID</span><span class="sxs-lookup"><span data-stu-id="59843-121">aplPeerID</span></span>  <br/> |<span data-ttu-id="59843-122">Chave estrangeira com pesquisa na tabela tblServerIdentity.serverID.</span><span class="sxs-lookup"><span data-stu-id="59843-122">Foreign key with lookup in tblServerIdentity.serverID table.</span></span>  <br/> |
   

