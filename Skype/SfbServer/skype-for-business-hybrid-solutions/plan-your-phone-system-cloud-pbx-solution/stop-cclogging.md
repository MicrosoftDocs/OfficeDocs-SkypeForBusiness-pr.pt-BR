---
title: Stop-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: O Stop-CcLogging cmdlet para de gerar o log de chamadas de entrada e saída para um dispositivo do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824155"
---
# <a name="stop-cclogging"></a><span data-ttu-id="1db91-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="1db91-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="1db91-104">O Stop-CcLogging cmdlet para de gerar o log de chamadas de entrada e saída para um dispositivo do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="1db91-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="1db91-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1db91-105">Examples</span></span>
<span data-ttu-id="1db91-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1db91-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="1db91-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="1db91-107">Example 1</span></span>

<span data-ttu-id="1db91-108">O exemplo a seguir para de gerar o log de chamadas de entrada e saída:</span><span class="sxs-lookup"><span data-stu-id="1db91-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="1db91-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="1db91-109">Example 2</span></span>

<span data-ttu-id="1db91-110">O próximo exemplo para de gerar o log de chamadas de entrada e saída e limpa os arquivos de cache:</span><span class="sxs-lookup"><span data-stu-id="1db91-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="1db91-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="1db91-111">Detailed Description</span></span>
<span data-ttu-id="1db91-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1db91-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="1db91-113">O Stop-CcLogging cmdlet interrompe o registro em log de chamadas de entrada e saída em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1db91-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="1db91-114">Por padrão, o registro em log será automaticamente parar após quatro horas.</span><span class="sxs-lookup"><span data-stu-id="1db91-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="1db91-115">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1db91-115">Parameters</span></span>
<span data-ttu-id="1db91-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1db91-116"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="1db91-117">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="1db91-117">**Parameter**</span></span>|<span data-ttu-id="1db91-118">**Required**</span><span class="sxs-lookup"><span data-stu-id="1db91-118">**Required**</span></span>|<span data-ttu-id="1db91-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1db91-119">**Type**</span></span>|<span data-ttu-id="1db91-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1db91-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="1db91-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="1db91-121">RemoveCache</span></span> <br/> | <span data-ttu-id="1db91-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="1db91-122">Optional</span></span> <br/> | <span data-ttu-id="1db91-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="1db91-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="1db91-124">Remove os arquivos de cache de registro em log.</span><span class="sxs-lookup"><span data-stu-id="1db91-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="1db91-125">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="1db91-125">Input Types</span></span>
<span data-ttu-id="1db91-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1db91-126"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="1db91-127">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1db91-127">None.</span></span> <span data-ttu-id="1db91-128">O Stop-CcLogging cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="1db91-128">The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1db91-129">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="1db91-129">Return Types</span></span>
<span data-ttu-id="1db91-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1db91-130"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1db91-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1db91-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1db91-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="1db91-132">See also</span></span>
<span data-ttu-id="1db91-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1db91-133"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="1db91-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="1db91-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="1db91-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="1db91-135">Start-CcLogging</span></span>](start-cclogging.md)
  

