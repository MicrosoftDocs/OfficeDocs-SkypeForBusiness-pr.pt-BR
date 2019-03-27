---
title: Tabela UriTypes
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: A tabela UriTypes Table contém os diferentes tipos URI (Uniform resource identifier) monitorados no Skype para Business Server 2015.
ms.openlocfilehash: cb9c131901a322f9d22c8d29aa52a73dc27c9ea1
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899642"
---
# <a name="uritypes-table"></a><span data-ttu-id="d35ea-103">Tabela UriTypes</span><span class="sxs-lookup"><span data-stu-id="d35ea-103">UriTypes table</span></span>
 
<span data-ttu-id="d35ea-104">A tabela UriTypes Table contém os diferentes tipos URI (Uniform resource identifier) monitorados no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="d35ea-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="d35ea-105">Quando o CDR DB é criado, dois registros para representar PhoneUri e UserUri são criados e registros criados depois que são atribuídas dinamicamente UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="d35ea-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="d35ea-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d35ea-106">**Column**</span></span>|<span data-ttu-id="d35ea-107">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="d35ea-107">**Data Type**</span></span>|<span data-ttu-id="d35ea-108">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="d35ea-108">**Key/Index**</span></span>|<span data-ttu-id="d35ea-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="d35ea-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d35ea-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="d35ea-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="d35ea-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="d35ea-111">tinyint</span></span>  <br/> |<span data-ttu-id="d35ea-112">Primária</span><span class="sxs-lookup"><span data-stu-id="d35ea-112">Primary</span></span>  <br/> |<span data-ttu-id="d35ea-113">Identificador exclusivo atribuído a um tipo de URI.</span><span class="sxs-lookup"><span data-stu-id="d35ea-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="d35ea-114">Valores possíveis - 0 a 255</span><span class="sxs-lookup"><span data-stu-id="d35ea-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="d35ea-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="d35ea-115">**UriType**</span></span> <br/> |<span data-ttu-id="d35ea-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="d35ea-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="d35ea-117">Descrições dos diferentes tipos de URI.</span><span class="sxs-lookup"><span data-stu-id="d35ea-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="d35ea-118">Os seguintes valores são atribuídos previamente:</span><span class="sxs-lookup"><span data-stu-id="d35ea-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="d35ea-119">1 - Uri do telefone</span><span class="sxs-lookup"><span data-stu-id="d35ea-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="d35ea-120">0 - Uri do usuário</span><span class="sxs-lookup"><span data-stu-id="d35ea-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="d35ea-121">Outros tipos possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="d35ea-121">Other possible types include:</span></span> <br/><span data-ttu-id="d35ea-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="d35ea-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="d35ea-123">conf:Audio-vídeo</span><span class="sxs-lookup"><span data-stu-id="d35ea-123">conf:audio-video</span></span><br/> <span data-ttu-id="d35ea-124">conf:Chat</span><span class="sxs-lookup"><span data-stu-id="d35ea-124">conf:chat</span></span><br/>    <span data-ttu-id="d35ea-125">conf:Focus</span><span class="sxs-lookup"><span data-stu-id="d35ea-125">conf:focus</span></span><br/>   <span data-ttu-id="d35ea-126">mras</span><span class="sxs-lookup"><span data-stu-id="d35ea-126">mras</span></span><br/>
