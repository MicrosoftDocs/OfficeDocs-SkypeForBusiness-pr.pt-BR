---
title: tblServerIdentity
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
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: TblServerIdentity contém os servidores de chat ativos no pool do Servidor de Chat Persistente.
ms.openlocfilehash: 7fa8c1b804432b3a9368785682f45e9ce8d7898e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831491"
---
# <a name="tblserveridentity"></a><span data-ttu-id="7e1a7-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="7e1a7-103">tblServerIdentity</span></span>
 
<span data-ttu-id="7e1a7-104">TblServerIdentity contém os servidores de chat ativos no pool do Servidor de Chat Persistente.</span><span class="sxs-lookup"><span data-stu-id="7e1a7-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="7e1a7-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="7e1a7-105">**Columns**</span></span>

|<span data-ttu-id="7e1a7-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7e1a7-106">**Column**</span></span>|<span data-ttu-id="7e1a7-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7e1a7-107">**Type**</span></span>|<span data-ttu-id="7e1a7-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7e1a7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7e1a7-109">serverID</span><span class="sxs-lookup"><span data-stu-id="7e1a7-109">serverID</span></span>  <br/> |<span data-ttu-id="7e1a7-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="7e1a7-110">int, not null</span></span>  <br/> |<span data-ttu-id="7e1a7-111">Identificação do Servidor.</span><span class="sxs-lookup"><span data-stu-id="7e1a7-111">Server ID.</span></span> <span data-ttu-id="7e1a7-112">Corresponde à ID da instância do armazenamento de Gerenciamento Central.</span><span class="sxs-lookup"><span data-stu-id="7e1a7-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="7e1a7-113">serverAddress</span><span class="sxs-lookup"><span data-stu-id="7e1a7-113">serverAddress</span></span>  <br/> |<span data-ttu-id="7e1a7-114">nvarchar (256), não nulo</span><span class="sxs-lookup"><span data-stu-id="7e1a7-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="7e1a7-115">Endereço do Servidor utilizando o endereço do Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="7e1a7-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="7e1a7-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="7e1a7-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="7e1a7-117">datetime</span><span class="sxs-lookup"><span data-stu-id="7e1a7-117">datetime</span></span>  <br/> |<span data-ttu-id="7e1a7-118">A última vez em que o Servidor de Canal atualizou esta linha para fornecer evidências de que está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="7e1a7-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="7e1a7-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="7e1a7-119">**Key**</span></span>

|<span data-ttu-id="7e1a7-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7e1a7-120">**Column**</span></span>|<span data-ttu-id="7e1a7-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7e1a7-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7e1a7-122">serverID</span><span class="sxs-lookup"><span data-stu-id="7e1a7-122">serverID</span></span>  <br/> |<span data-ttu-id="7e1a7-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="7e1a7-123">Primary key.</span></span>  <br/> |
   

