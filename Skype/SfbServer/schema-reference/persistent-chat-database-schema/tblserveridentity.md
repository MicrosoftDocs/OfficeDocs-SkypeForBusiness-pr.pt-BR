---
title: tblServerIdentity
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: o tblServerIdentity inclui os servidores de bate-papo ativas no pool Persistent Chat Server.
ms.openlocfilehash: 1f9455e4c35a3bc6061c1d44ad10cbd4778c6c1f
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899523"
---
# <a name="tblserveridentity"></a><span data-ttu-id="1808d-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="1808d-103">tblServerIdentity</span></span>
 
<span data-ttu-id="1808d-104">o tblServerIdentity inclui os servidores de bate-papo ativas no pool Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="1808d-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="1808d-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="1808d-105">**Columns**</span></span>

|<span data-ttu-id="1808d-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="1808d-106">**Column**</span></span>|<span data-ttu-id="1808d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1808d-107">**Type**</span></span>|<span data-ttu-id="1808d-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1808d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1808d-109">serverID</span><span class="sxs-lookup"><span data-stu-id="1808d-109">serverID</span></span>  <br/> |<span data-ttu-id="1808d-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="1808d-110">int, not null</span></span>  <br/> |<span data-ttu-id="1808d-111">ID do servidor.</span><span class="sxs-lookup"><span data-stu-id="1808d-111">Server ID.</span></span> <span data-ttu-id="1808d-112">Corresponde à ID da instância do repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="1808d-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="1808d-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="1808d-113">serverAddress</span></span>  <br/> |<span data-ttu-id="1808d-114">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="1808d-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="1808d-115">Endereço do servidor usando o endereço do Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="1808d-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="1808d-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="1808d-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="1808d-117">datetime</span><span class="sxs-lookup"><span data-stu-id="1808d-117">datetime</span></span>  <br/> |<span data-ttu-id="1808d-118">A última vez em que o servidor de canal atualizou esta linha para fornecer evidências de que ele está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="1808d-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="1808d-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="1808d-119">**Key**</span></span>

|<span data-ttu-id="1808d-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="1808d-120">**Column**</span></span>|<span data-ttu-id="1808d-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1808d-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1808d-122">serverID</span><span class="sxs-lookup"><span data-stu-id="1808d-122">serverID</span></span>  <br/> |<span data-ttu-id="1808d-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="1808d-123">Primary key.</span></span>  <br/> |
   

