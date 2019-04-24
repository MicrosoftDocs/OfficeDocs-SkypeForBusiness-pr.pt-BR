---
title: Tabela ErrorDef no Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer. Cada registro é um tipo de erro.
ms.openlocfilehash: cec601dad24dda522477bfcd7b1e80d0efc45799
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213106"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="fe74f-104">Tabela ErrorDef no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="fe74f-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="fe74f-105">A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer.</span><span class="sxs-lookup"><span data-stu-id="fe74f-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="fe74f-106">Cada registro é um tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="fe74f-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="fe74f-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="fe74f-107">**Column**</span></span>|<span data-ttu-id="fe74f-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="fe74f-108">**Data Type**</span></span>|<span data-ttu-id="fe74f-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="fe74f-109">**Key/Index**</span></span>|<span data-ttu-id="fe74f-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="fe74f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fe74f-111">**Identificação de erro**</span><span class="sxs-lookup"><span data-stu-id="fe74f-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="fe74f-112">int</span><span class="sxs-lookup"><span data-stu-id="fe74f-112">int</span></span>  <br/> |<span data-ttu-id="fe74f-113">Primária</span><span class="sxs-lookup"><span data-stu-id="fe74f-113">Primary</span></span>  <br/> |<span data-ttu-id="fe74f-114">Número de identificação exclusivo que identifica esse tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="fe74f-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="fe74f-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="fe74f-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="fe74f-116">int</span><span class="sxs-lookup"><span data-stu-id="fe74f-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="fe74f-117">Código de resposta SIP padrão associado a esse erro.</span><span class="sxs-lookup"><span data-stu-id="fe74f-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="fe74f-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="fe74f-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="fe74f-119">int</span><span class="sxs-lookup"><span data-stu-id="fe74f-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="fe74f-120">ID de diagnóstico da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="fe74f-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="fe74f-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="fe74f-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="fe74f-122">Int</span><span class="sxs-lookup"><span data-stu-id="fe74f-122">Int</span></span>  <br/> |<span data-ttu-id="fe74f-123">Externa</span><span class="sxs-lookup"><span data-stu-id="fe74f-123">Foreign</span></span>  <br/> |<span data-ttu-id="fe74f-124">Tipo da chamada.</span><span class="sxs-lookup"><span data-stu-id="fe74f-124">Type of the call.</span></span> <span data-ttu-id="fe74f-125">Consulte a [tabela CallType Skype para Business Server 2015](calltype.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="fe74f-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="fe74f-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="fe74f-126">**RequestType**</span></span> <br/> |<span data-ttu-id="fe74f-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="fe74f-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="fe74f-128">Tipo de solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="fe74f-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="fe74f-129">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fe74f-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="fe74f-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="fe74f-130">**ContentType**</span></span> <br/> |<span data-ttu-id="fe74f-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="fe74f-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="fe74f-132">Tipo de conteúdo da solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="fe74f-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="fe74f-133">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="fe74f-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

