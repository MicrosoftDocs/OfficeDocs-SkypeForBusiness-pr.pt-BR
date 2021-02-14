---
title: Tabela ErrorDef no Skype for Business Server 2015
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
ms.assetid: 6acf3b86-da61-4923-9812-300db6f66dec
description: A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer. Cada registro é um tipo de erro.
ms.openlocfilehash: 50d7b76e1fc7edb53fbe0b299673b7281a394463
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821721"
---
# <a name="errordef-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9e284-104">Tabela ErrorDef no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9e284-104">ErrorDef table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9e284-105">A tabela ErrorDef armazena informações sobre cada tipo de erro que pode ocorrer.</span><span class="sxs-lookup"><span data-stu-id="9e284-105">The ErrorDef table stores information about each type of error that may occur.</span></span> <span data-ttu-id="9e284-106">Cada registro é um tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="9e284-106">Each record is one type of error.</span></span>
  
|<span data-ttu-id="9e284-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9e284-107">**Column**</span></span>|<span data-ttu-id="9e284-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9e284-108">**Data Type**</span></span>|<span data-ttu-id="9e284-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="9e284-109">**Key/Index**</span></span>|<span data-ttu-id="9e284-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="9e284-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9e284-111">**ErrorId**</span><span class="sxs-lookup"><span data-stu-id="9e284-111">**ErrorId**</span></span> <br/> |<span data-ttu-id="9e284-112">int</span><span class="sxs-lookup"><span data-stu-id="9e284-112">int</span></span>  <br/> |<span data-ttu-id="9e284-113">Primário</span><span class="sxs-lookup"><span data-stu-id="9e284-113">Primary</span></span>  <br/> |<span data-ttu-id="9e284-114">Número de identificação exclusivo que identifica esse tipo de erro.</span><span class="sxs-lookup"><span data-stu-id="9e284-114">Unique ID number identifying this type of error.</span></span>  <br/> |
|<span data-ttu-id="9e284-115">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="9e284-115">**ResponseCode**</span></span> <br/> |<span data-ttu-id="9e284-116">int</span><span class="sxs-lookup"><span data-stu-id="9e284-116">int</span></span>  <br/> | <br/> |<span data-ttu-id="9e284-117">Código de resposta SIP padrão associado a esse erro.</span><span class="sxs-lookup"><span data-stu-id="9e284-117">Standard SIP response code associated with this error.</span></span>  <br/> |
|<span data-ttu-id="9e284-118">**MsDiagId**</span><span class="sxs-lookup"><span data-stu-id="9e284-118">**MsDiagId**</span></span> <br/> |<span data-ttu-id="9e284-119">int</span><span class="sxs-lookup"><span data-stu-id="9e284-119">int</span></span>  <br/> | <br/> |<span data-ttu-id="9e284-120">ID de diagnóstico da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="9e284-120">Microsoft Diagnostic ID.</span></span>  <br/> |
|<span data-ttu-id="9e284-121">**CallTypeId**</span><span class="sxs-lookup"><span data-stu-id="9e284-121">**CallTypeId**</span></span> <br/> |<span data-ttu-id="9e284-122">Int</span><span class="sxs-lookup"><span data-stu-id="9e284-122">Int</span></span>  <br/> |<span data-ttu-id="9e284-123">Externo</span><span class="sxs-lookup"><span data-stu-id="9e284-123">Foreign</span></span>  <br/> |<span data-ttu-id="9e284-124">Tipo da chamada.</span><span class="sxs-lookup"><span data-stu-id="9e284-124">Type of the call.</span></span> <span data-ttu-id="9e284-125">Consulte a [tabela CallType no Skype for Business Server 2015](calltype.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="9e284-125">See the [CallType table in Skype for Business Server 2015](calltype.md) for more information.</span></span> <br/> |
|<span data-ttu-id="9e284-126">**RequestType**</span><span class="sxs-lookup"><span data-stu-id="9e284-126">**RequestType**</span></span> <br/> |<span data-ttu-id="9e284-127">varbinary(33)</span><span class="sxs-lookup"><span data-stu-id="9e284-127">varbinary(33)</span></span>  <br/> | <br/> |<span data-ttu-id="9e284-128">Tipo de solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="9e284-128">Type of request that failed.</span></span>  <br/> <span data-ttu-id="9e284-129">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9e284-129">This data can be converted to text format by using this syntax:</span></span>  <br/>  `cast(cast(RequestType as varbinary(max)) as varchar(max))` <br/> |
|<span data-ttu-id="9e284-130">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="9e284-130">**ContentType**</span></span> <br/> |<span data-ttu-id="9e284-131">varbinary(257)</span><span class="sxs-lookup"><span data-stu-id="9e284-131">varbinary(257)</span></span>  <br/> | <br/> |<span data-ttu-id="9e284-132">Tipo de conteúdo da solicitação que falhou.</span><span class="sxs-lookup"><span data-stu-id="9e284-132">Content type of the request that failed.</span></span>  <br/> <span data-ttu-id="9e284-133">Esses dados podem ser convertidos em formato de texto usando esta sintaxe:</span><span class="sxs-lookup"><span data-stu-id="9e284-133">This data can be converted to text format by using this syntaxt:</span></span>  <br/>  `cast(cast(ContentType as varbinary(max)) as varchar(max))` <br/> |
   

