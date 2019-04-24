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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212415"
---
# <a name="tblserveridentity"></a><span data-ttu-id="6f42e-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="6f42e-103">tblServerIdentity</span></span>
 
<span data-ttu-id="6f42e-104">o tblServerIdentity inclui os servidores de bate-papo ativas no pool Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="6f42e-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="6f42e-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="6f42e-105">**Columns**</span></span>

|<span data-ttu-id="6f42e-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6f42e-106">**Column**</span></span>|<span data-ttu-id="6f42e-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6f42e-107">**Type**</span></span>|<span data-ttu-id="6f42e-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6f42e-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6f42e-109">serverID</span><span class="sxs-lookup"><span data-stu-id="6f42e-109">serverID</span></span>  <br/> |<span data-ttu-id="6f42e-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6f42e-110">int, not null</span></span>  <br/> |<span data-ttu-id="6f42e-111">ID do servidor.</span><span class="sxs-lookup"><span data-stu-id="6f42e-111">Server ID.</span></span> <span data-ttu-id="6f42e-112">Corresponde à ID da instância do repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="6f42e-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="6f42e-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="6f42e-113">serverAddress</span></span>  <br/> |<span data-ttu-id="6f42e-114">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="6f42e-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="6f42e-115">Endereço do servidor usando o endereço do Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="6f42e-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="6f42e-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="6f42e-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="6f42e-117">datetime</span><span class="sxs-lookup"><span data-stu-id="6f42e-117">datetime</span></span>  <br/> |<span data-ttu-id="6f42e-118">A última vez em que o servidor de canal atualizou esta linha para fornecer evidências de que ele está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="6f42e-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="6f42e-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="6f42e-119">**Key**</span></span>

|<span data-ttu-id="6f42e-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6f42e-120">**Column**</span></span>|<span data-ttu-id="6f42e-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6f42e-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6f42e-122">serverID</span><span class="sxs-lookup"><span data-stu-id="6f42e-122">serverID</span></span>  <br/> |<span data-ttu-id="6f42e-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="6f42e-123">Primary key.</span></span>  <br/> |
   

