---
title: Tabela UriTypes
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: A tabela UriTypes contém os diferentes tipos de URI (Uniform Resource Identifier) monitorados no Skype for Business Server 2015.
ms.openlocfilehash: 5ad8e1d0432aff3278f897fbe82d3759ad3c95e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295745"
---
# <a name="uritypes-table"></a><span data-ttu-id="36f32-103">Tabela UriTypes</span><span class="sxs-lookup"><span data-stu-id="36f32-103">UriTypes table</span></span>
 
<span data-ttu-id="36f32-104">A tabela UriTypes contém os diferentes tipos de URI (Uniform Resource Identifier) monitorados no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="36f32-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="36f32-105">Quando o banco de banco de CDR é criado, dois registros para representar PhoneUri e UserUri são criados, e os registros criados após esse UriTypeId são atribuídos dinamicamente.</span><span class="sxs-lookup"><span data-stu-id="36f32-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="36f32-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="36f32-106">**Column**</span></span>|<span data-ttu-id="36f32-107">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="36f32-107">**Data Type**</span></span>|<span data-ttu-id="36f32-108">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="36f32-108">**Key/Index**</span></span>|<span data-ttu-id="36f32-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="36f32-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="36f32-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="36f32-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="36f32-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="36f32-111">tinyint</span></span>  <br/> |<span data-ttu-id="36f32-112">Primária</span><span class="sxs-lookup"><span data-stu-id="36f32-112">Primary</span></span>  <br/> |<span data-ttu-id="36f32-113">Identificador exclusivo atribuído a um tipo de URI.</span><span class="sxs-lookup"><span data-stu-id="36f32-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="36f32-114">Valores possíveis de 0 a 255</span><span class="sxs-lookup"><span data-stu-id="36f32-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="36f32-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="36f32-115">**UriType**</span></span> <br/> |<span data-ttu-id="36f32-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="36f32-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="36f32-117">Descrições dos diferentes tipos de URI.</span><span class="sxs-lookup"><span data-stu-id="36f32-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="36f32-118">Os seguintes valores são predefinidos:</span><span class="sxs-lookup"><span data-stu-id="36f32-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="36f32-119">1-URI do telefone</span><span class="sxs-lookup"><span data-stu-id="36f32-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="36f32-120">0-URI do usuário</span><span class="sxs-lookup"><span data-stu-id="36f32-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="36f32-121">Outros tipos possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="36f32-121">Other possible types include:</span></span> <br/><span data-ttu-id="36f32-122">conf: applicationsharing</span><span class="sxs-lookup"><span data-stu-id="36f32-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="36f32-123">conf: áudio-vídeo</span><span class="sxs-lookup"><span data-stu-id="36f32-123">conf:audio-video</span></span><br/> <span data-ttu-id="36f32-124">conf: chat</span><span class="sxs-lookup"><span data-stu-id="36f32-124">conf:chat</span></span><br/>    <span data-ttu-id="36f32-125">conf: foco</span><span class="sxs-lookup"><span data-stu-id="36f32-125">conf:focus</span></span><br/>   <span data-ttu-id="36f32-126">mras</span><span class="sxs-lookup"><span data-stu-id="36f32-126">mras</span></span><br/>
