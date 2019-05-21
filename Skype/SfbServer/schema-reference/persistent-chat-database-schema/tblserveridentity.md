---
title: tblServerIdentity
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contém os servidores de chat ativos no pool do servidor de chat persistente.
ms.openlocfilehash: b35960bd1deef5470724f580bce2375b2e034cb9
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295185"
---
# <a name="tblserveridentity"></a><span data-ttu-id="d27ff-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="d27ff-103">tblServerIdentity</span></span>
 
<span data-ttu-id="d27ff-104">tblServerIdentity contém os servidores de chat ativos no pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="d27ff-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="d27ff-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d27ff-105">**Columns**</span></span>

|<span data-ttu-id="d27ff-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d27ff-106">**Column**</span></span>|<span data-ttu-id="d27ff-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d27ff-107">**Type**</span></span>|<span data-ttu-id="d27ff-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d27ff-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d27ff-109">serverID</span><span class="sxs-lookup"><span data-stu-id="d27ff-109">serverID</span></span>  <br/> |<span data-ttu-id="d27ff-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d27ff-110">int, not null</span></span>  <br/> |<span data-ttu-id="d27ff-111">ID do servidor.</span><span class="sxs-lookup"><span data-stu-id="d27ff-111">Server ID.</span></span> <span data-ttu-id="d27ff-112">Corresponde à ID da instância do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="d27ff-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="d27ff-113">a</span><span class="sxs-lookup"><span data-stu-id="d27ff-113">serverAddress</span></span>  <br/> |<span data-ttu-id="d27ff-114">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="d27ff-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="d27ff-115">Endereço do servidor usando o endereço do Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="d27ff-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="d27ff-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="d27ff-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="d27ff-117">datetime</span><span class="sxs-lookup"><span data-stu-id="d27ff-117">datetime</span></span>  <br/> |<span data-ttu-id="d27ff-118">A última vez em que o servidor de canal atualizou essa linha para dar evidências de que esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="d27ff-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="d27ff-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="d27ff-119">**Key**</span></span>

|<span data-ttu-id="d27ff-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d27ff-120">**Column**</span></span>|<span data-ttu-id="d27ff-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d27ff-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="d27ff-122">serverID</span><span class="sxs-lookup"><span data-stu-id="d27ff-122">serverID</span></span>  <br/> |<span data-ttu-id="d27ff-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="d27ff-123">Primary key.</span></span>  <br/> |
   

