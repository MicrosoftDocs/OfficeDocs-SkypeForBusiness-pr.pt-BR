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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer. Cada registro é um tipo de erro.
ms.openlocfilehash: f686692bee334c0927b6e8342cfb7152b3e54f0c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815229"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="7a1c9-104">Tabela ErrorDef no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="7a1c9-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="7a1c9-105">A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer.</span><span class="sxs-lookup"><span data-stu-id="7a1c9-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="7a1c9-106">Cada registro é um tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="7a1c9-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="7a1c9-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7a1c9-107">**Column**</span></span>|<span data-ttu-id="7a1c9-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="7a1c9-108">**Data Type**</span></span>|<span data-ttu-id="7a1c9-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="7a1c9-109">**Key/Index**</span></span>|<span data-ttu-id="7a1c9-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="7a1c9-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7a1c9-111">**ErrorID**</span><span class="sxs-lookup"><span data-stu-id="7a1c9-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="7a1c9-112">int</span><span class="sxs-lookup"><span data-stu-id="7a1c9-112">int</span></span>  <br/> |<span data-ttu-id="7a1c9-113">Primária</span><span class="sxs-lookup"><span data-stu-id="7a1c9-113">Primary</span></span>  <br/> |<span data-ttu-id="7a1c9-114">Número de identificação exclusivo que identifica esse tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="7a1c9-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="7a1c9-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="7a1c9-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="7a1c9-116">int</span><span class="sxs-lookup"><span data-stu-id="7a1c9-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="7a1c9-117">Código de resposta SIP padrão associado a esse erro.</span><span class="sxs-lookup"><span data-stu-id="7a1c9-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="7a1c9-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="7a1c9-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="7a1c9-119">int</span><span class="sxs-lookup"><span data-stu-id="7a1c9-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="7a1c9-120">IDENTIFICAÇÃO do diagnóstico da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="7a1c9-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="7a1c9-121">**Callid**</span><span class="sxs-lookup"><span data-stu-id="7a1c9-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="7a1c9-122">Núm</span><span class="sxs-lookup"><span data-stu-id="7a1c9-122">Int</span></span>  <br/> |<span data-ttu-id="7a1c9-123">Exterior</span><span class="sxs-lookup"><span data-stu-id="7a1c9-123">Foreign</span></span>  <br/> |<span data-ttu-id="7a1c9-124">Tipo de chamada.</span><span class="sxs-lookup"><span data-stu-id="7a1c9-124">Type of the call.</span></span> <span data-ttu-id="7a1c9-125">Consulte a [tabela CallType no Skype for Business Server 2015](calltype.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="7a1c9-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="7a1c9-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="7a1c9-126">**RequestType**</span></span> <br/> |<span data-ttu-id="7a1c9-127">varbinary (33)</span><span class="sxs-lookup"><span data-stu-id="7a1c9-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="7a1c9-128">Tipo de solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="7a1c9-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="7a1c9-129">Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="7a1c9-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="7a1c9-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="7a1c9-130">**ContentType**</span></span> <br/> |<span data-ttu-id="7a1c9-131">varbinary (257)</span><span class="sxs-lookup"><span data-stu-id="7a1c9-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="7a1c9-132">Tipo de conteúdo da solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="7a1c9-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="7a1c9-133">Esses dados podem ser convertidos em um formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="7a1c9-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

