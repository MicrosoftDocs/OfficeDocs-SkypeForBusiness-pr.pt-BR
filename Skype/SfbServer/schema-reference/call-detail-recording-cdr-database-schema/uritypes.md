---
title: Tabela UriTypes
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 77c4dfae-1b29-4e81-ba05-609e61643998
description: A tabela UriTypes contém os diferentes tipos de URI (Uniform resource identifier) monitorados no Skype for Business Server 2015.
ms.openlocfilehash: 622384086dbd1031633b70758cdcea600ad31d43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831681"
---
# <a name="uritypes-table"></a><span data-ttu-id="c7b36-103">Tabela UriTypes</span><span class="sxs-lookup"><span data-stu-id="c7b36-103">UriTypes table</span></span>
 
<span data-ttu-id="c7b36-104">A tabela UriTypes contém os diferentes tipos de URI (Uniform resource identifier) monitorados no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="c7b36-104">The UriTypes Table contains the different URI (Uniform resource identifier) types monitored in Skype for Business Server 2015.</span></span>

<span data-ttu-id="c7b36-105">Quando o BANCO DE CDR é criado, dois registros para representar PhoneUri e UserUri são criados e os registros criados depois disso são atribuídos dinamicamente a UriTypeId.</span><span class="sxs-lookup"><span data-stu-id="c7b36-105">When the CDR DB is created, two records to represent PhoneUri and UserUri are created, and records created after that are dynamically assigned UriTypeId.</span></span> 
  
|<span data-ttu-id="c7b36-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c7b36-106">**Column**</span></span>|<span data-ttu-id="c7b36-107">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c7b36-107">**Data Type**</span></span>|<span data-ttu-id="c7b36-108">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="c7b36-108">**Key/Index**</span></span>|<span data-ttu-id="c7b36-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="c7b36-109">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c7b36-110">**UriTypeId**</span><span class="sxs-lookup"><span data-stu-id="c7b36-110">**UriTypeId**</span></span> <br/> |<span data-ttu-id="c7b36-111">tinyint</span><span class="sxs-lookup"><span data-stu-id="c7b36-111">tinyint</span></span>  <br/> |<span data-ttu-id="c7b36-112">Primário</span><span class="sxs-lookup"><span data-stu-id="c7b36-112">Primary</span></span>  <br/> |<span data-ttu-id="c7b36-113">Identificador exclusivo atribuído a um tipo de URI.</span><span class="sxs-lookup"><span data-stu-id="c7b36-113">Unique identifier assigned to a URI type.</span></span>  <br/> <span data-ttu-id="c7b36-114">Valores possíveis - 0 a 255</span><span class="sxs-lookup"><span data-stu-id="c7b36-114">Possible values - 0 to 255</span></span> |
|<span data-ttu-id="c7b36-115">**UriType**</span><span class="sxs-lookup"><span data-stu-id="c7b36-115">**UriType**</span></span> <br/> |<span data-ttu-id="c7b36-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="c7b36-116">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="c7b36-117">Descrições de tipos de URI diferentes.</span><span class="sxs-lookup"><span data-stu-id="c7b36-117">Descriptions of the different URI types.</span></span> <span data-ttu-id="c7b36-118">Os seguintes valores são pré-atribuídos:</span><span class="sxs-lookup"><span data-stu-id="c7b36-118">The following values are pre-assigned:</span></span> <br/>  <span data-ttu-id="c7b36-119">1 - Uri de Telefone</span><span class="sxs-lookup"><span data-stu-id="c7b36-119">1 - Phone Uri</span></span> <br/>  <span data-ttu-id="c7b36-120">0 - Uri do Usuário</span><span class="sxs-lookup"><span data-stu-id="c7b36-120">0 - User Uri</span></span> <br/> <br/>  <span data-ttu-id="c7b36-121">Outros tipos possíveis incluem:</span><span class="sxs-lookup"><span data-stu-id="c7b36-121">Other possible types include:</span></span> <br/><span data-ttu-id="c7b36-122">conf:applicationsharing</span><span class="sxs-lookup"><span data-stu-id="c7b36-122">conf:applicationsharing</span></span> <br/> <span data-ttu-id="c7b36-123">conf:audio-video</span><span class="sxs-lookup"><span data-stu-id="c7b36-123">conf:audio-video</span></span><br/> <span data-ttu-id="c7b36-124">conf:chat</span><span class="sxs-lookup"><span data-stu-id="c7b36-124">conf:chat</span></span><br/>    <span data-ttu-id="c7b36-125">conf:focus</span><span class="sxs-lookup"><span data-stu-id="c7b36-125">conf:focus</span></span><br/>   <span data-ttu-id="c7b36-126">mras</span><span class="sxs-lookup"><span data-stu-id="c7b36-126">mras</span></span><br/>
