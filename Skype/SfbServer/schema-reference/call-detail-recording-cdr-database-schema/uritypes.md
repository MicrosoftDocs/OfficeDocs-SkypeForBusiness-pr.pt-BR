---
title: Tabela UriTypes
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
ms.openlocfilehash: e21fe7d88c64acf57ad8d318a755b7fa6c73c1c2
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19570055"
---
# <a name="uritypes-table"></a><span data-ttu-id="ede42-103">Tabela UriTypes</span><span class="sxs-lookup"><span data-stu-id="ede42-103">UriTypes table</span></span>
 
<span data-ttu-id="ede42-104">A tabela UriTypes Table contém os diferentes tipos URI (Uniform resource identifier) monitorados no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ede42-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="ede42-105">Quando o CDR DB é criado, dois registros para representar PhoneUri e UserUri são criados e outros</span><span class="sxs-lookup"><span data-stu-id="ede42-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and others</span></span> 
  
|<span data-ttu-id="ede42-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ede42-106">**Column**</span></span>|<span data-ttu-id="ede42-107">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ede42-107">**Data Type**</span></span>|<span data-ttu-id="ede42-108">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="ede42-108">**Key/Index**</span></span>|<span data-ttu-id="ede42-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="ede42-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ede42-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="ede42-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="ede42-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="ede42-111">tinyint</span></span>  <br/> |<span data-ttu-id="ede42-112">Primária</span><span class="sxs-lookup"><span data-stu-id="ede42-112">Primary</span></span>  <br/> |<span data-ttu-id="ede42-113">Identificador exclusivo atribuído a um tipo de URI.</span><span class="sxs-lookup"><span data-stu-id="ede42-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="ede42-114">Valores possíveis - 0 a 255</span><span class="sxs-lookup"><span data-stu-id="ede42-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="ede42-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="ede42-115">**UriType**</span></span> <br/> |<span data-ttu-id="ede42-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ede42-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="ede42-117">Descrições dos diferentes tipos de URI.</span><span class="sxs-lookup"><span data-stu-id="ede42-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="ede42-118">Os seguintes valores são atribuídos previamente:</span><span class="sxs-lookup"><span data-stu-id="ede42-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="ede42-119">1 - Uri do telefone</span><span class="sxs-lookup"><span data-stu-id="ede42-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="ede42-120">0 - Uri do usuário</span><span class="sxs-lookup"><span data-stu-id="ede42-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="ede42-121">Outros tipos possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="ede42-121">Other possible types include:</span></span> <br/><span data-ttu-id="ede42-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="ede42-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="ede42-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="ede42-123">conf:audio-video</span></span><br/> <span data-ttu-id="ede42-124">conf:Chat</span><span class="sxs-lookup"><span data-stu-id="ede42-124">conf:chat</span></span><br/>    <span data-ttu-id="ede42-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="ede42-125">conf:focus</span></span><br/>   <span data-ttu-id="ede42-126">mras</span><span class="sxs-lookup"><span data-stu-id="ede42-126">mras</span></span><br/>