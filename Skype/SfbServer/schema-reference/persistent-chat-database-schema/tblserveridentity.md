---
title: tblServerIdentity
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
ms.openlocfilehash: 445021bb486d418011ea21dd32c0339e11b4d17a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblserveridentity"></a><span data-ttu-id="b62ca-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="b62ca-103">tblServerIdentity</span></span>
 
<span data-ttu-id="b62ca-104">o tblServerIdentity inclui os servidores de bate-papo ativas no pool Persistent Chat Server.</span><span class="sxs-lookup"><span data-stu-id="b62ca-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="b62ca-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="b62ca-105">**Columns**</span></span>

|<span data-ttu-id="b62ca-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b62ca-106">**Column**</span></span>|<span data-ttu-id="b62ca-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b62ca-107">**Type**</span></span>|<span data-ttu-id="b62ca-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b62ca-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b62ca-109">serverID</span><span class="sxs-lookup"><span data-stu-id="b62ca-109">serverID</span></span>  <br/> |<span data-ttu-id="b62ca-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="b62ca-110">int, not null</span></span>  <br/> |<span data-ttu-id="b62ca-111">ID do servidor.</span><span class="sxs-lookup"><span data-stu-id="b62ca-111">Server ID.</span></span> <span data-ttu-id="b62ca-112">Corresponde à ID da instância do repositório de gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="b62ca-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="b62ca-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="b62ca-113">serverAddress</span></span>  <br/> |<span data-ttu-id="b62ca-114">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="b62ca-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="b62ca-115">Endereço do servidor usando o endereço do Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="b62ca-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="b62ca-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="b62ca-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="b62ca-117">datetime</span><span class="sxs-lookup"><span data-stu-id="b62ca-117">datetime</span></span>  <br/> |<span data-ttu-id="b62ca-118">A última vez em que o servidor de canal atualizou esta linha para fornecer evidências de que ele está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="b62ca-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="b62ca-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b62ca-119">**Key**</span></span>

|<span data-ttu-id="b62ca-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b62ca-120">**Column**</span></span>|<span data-ttu-id="b62ca-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b62ca-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b62ca-122">serverID</span><span class="sxs-lookup"><span data-stu-id="b62ca-122">serverID</span></span>  <br/> |<span data-ttu-id="b62ca-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="b62ca-123">Primary key.</span></span>  <br/> |
   

