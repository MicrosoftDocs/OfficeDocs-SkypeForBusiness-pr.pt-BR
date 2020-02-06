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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 5411c9bc-b0b3-41fc-8b7e-fa71cccd770b
description: tblServerIdentity contém os servidores de chat ativos no pool do servidor de chat persistente.
ms.openlocfilehash: 4f6389f21c35da914b4943a279d8d485b6ec1eae
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41812269"
---
# <a name="tblserveridentity"></a><span data-ttu-id="9dfad-103">tblServerIdentity</span><span class="sxs-lookup"><span data-stu-id="9dfad-103">tblServerIdentity</span></span>
 
<span data-ttu-id="9dfad-104">tblServerIdentity contém os servidores de chat ativos no pool do servidor de chat persistente.</span><span class="sxs-lookup"><span data-stu-id="9dfad-104">tblServerIdentity contains the active chat servers in the Persistent Chat Server pool.</span></span>
  
<span data-ttu-id="9dfad-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="9dfad-105">**Columns**</span></span>

|<span data-ttu-id="9dfad-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9dfad-106">**Column**</span></span>|<span data-ttu-id="9dfad-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9dfad-107">**Type**</span></span>|<span data-ttu-id="9dfad-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9dfad-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9dfad-109">serverID</span><span class="sxs-lookup"><span data-stu-id="9dfad-109">serverID</span></span>  <br/> |<span data-ttu-id="9dfad-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="9dfad-110">int, not null</span></span>  <br/> |<span data-ttu-id="9dfad-111">ID do servidor.</span><span class="sxs-lookup"><span data-stu-id="9dfad-111">Server ID.</span></span> <span data-ttu-id="9dfad-112">Corresponde à ID da instância do repositório de gerenciamento central.</span><span class="sxs-lookup"><span data-stu-id="9dfad-112">Corresponds to the instance ID from Central Management store.</span></span>  <br/> |
|<span data-ttu-id="9dfad-113">a</span><span class="sxs-lookup"><span data-stu-id="9dfad-113">serverAddress</span></span>  <br/> |<span data-ttu-id="9dfad-114">nvarchar (256), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="9dfad-114">nvarchar (256), not null</span></span>  <br/> |<span data-ttu-id="9dfad-115">Endereço do servidor usando o endereço do Windows Communication Foundation.</span><span class="sxs-lookup"><span data-stu-id="9dfad-115">Server address using the Windows Communication Foundation address.</span></span>  <br/> |
|<span data-ttu-id="9dfad-116">serverLastPingTime</span><span class="sxs-lookup"><span data-stu-id="9dfad-116">serverLastPingTime</span></span>  <br/> |<span data-ttu-id="9dfad-117">datetime</span><span class="sxs-lookup"><span data-stu-id="9dfad-117">datetime</span></span>  <br/> |<span data-ttu-id="9dfad-118">A última vez em que o servidor de canal atualizou essa linha para dar evidências de que esteja em execução.</span><span class="sxs-lookup"><span data-stu-id="9dfad-118">The latest time that the Channel Server updated this row to give evidence that it is running.</span></span>  <br/> |
   
<span data-ttu-id="9dfad-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="9dfad-119">**Key**</span></span>

|<span data-ttu-id="9dfad-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9dfad-120">**Column**</span></span>|<span data-ttu-id="9dfad-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9dfad-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9dfad-122">serverID</span><span class="sxs-lookup"><span data-stu-id="9dfad-122">serverID</span></span>  <br/> |<span data-ttu-id="9dfad-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="9dfad-123">Primary key.</span></span>  <br/> |
   

