---
title: Tabela ErrorDef no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer. Cada registro é um tipo de erro.
ms.openlocfilehash: c6157bb62df47b8fcb1cd158605c5a357e623adf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296277"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="c7afb-104">Tabela ErrorDef no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="c7afb-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="c7afb-105">A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer.</span><span class="sxs-lookup"><span data-stu-id="c7afb-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="c7afb-106">Cada registro é um tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="c7afb-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="c7afb-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c7afb-107">**Column**</span></span>|<span data-ttu-id="c7afb-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="c7afb-108">**Data Type**</span></span>|<span data-ttu-id="c7afb-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="c7afb-109">**Key/Index**</span></span>|<span data-ttu-id="c7afb-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="c7afb-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="c7afb-111">**ErrorID**</span><span class="sxs-lookup"><span data-stu-id="c7afb-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="c7afb-112">int</span><span class="sxs-lookup"><span data-stu-id="c7afb-112">int</span></span>  <br/> |<span data-ttu-id="c7afb-113">Primária</span><span class="sxs-lookup"><span data-stu-id="c7afb-113">Primary</span></span>  <br/> |<span data-ttu-id="c7afb-114">Número de identificação exclusivo que identifica esse tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="c7afb-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="c7afb-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="c7afb-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="c7afb-116">int</span><span class="sxs-lookup"><span data-stu-id="c7afb-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="c7afb-117">Código de resposta SIP padrão associado a esse erro.</span><span class="sxs-lookup"><span data-stu-id="c7afb-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="c7afb-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="c7afb-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="c7afb-119">int</span><span class="sxs-lookup"><span data-stu-id="c7afb-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="c7afb-120">IDENTIFICAÇÃO do diagnóstico da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c7afb-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="c7afb-121">**Callid**</span><span class="sxs-lookup"><span data-stu-id="c7afb-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="c7afb-122">Núm</span><span class="sxs-lookup"><span data-stu-id="c7afb-122">Int</span></span>  <br/> |<span data-ttu-id="c7afb-123">Exterior</span><span class="sxs-lookup"><span data-stu-id="c7afb-123">Foreign</span></span>  <br/> |<span data-ttu-id="c7afb-124">Tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="c7afb-124">Type of the call.</span></span> <span data-ttu-id="c7afb-125">Consulte a [tabela CallType no Skype for Business Server 2015](calltype.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c7afb-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="c7afb-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="c7afb-126">**RequestType**</span></span> <br/> |<span data-ttu-id="c7afb-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="c7afb-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="c7afb-128">Tipo de solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="c7afb-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="c7afb-129">Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7afb-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="c7afb-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="c7afb-130">**ContentType**</span></span> <br/> |<span data-ttu-id="c7afb-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="c7afb-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="c7afb-132">Tipo de conteúdo da solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="c7afb-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="c7afb-133">Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="c7afb-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

