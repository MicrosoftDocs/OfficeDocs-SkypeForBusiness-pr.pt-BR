---
title: Stop-CcLogging
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: fee9eda7-ad15-40d2-b9fe-21c5462d3309
description: O cmdlet Stop-CcLogging para de gerar logs de chamadas de entrada e de saída para o dispositivo do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: abecc5acc6a454b2965fbf79caadb23f2256e4cd
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="stop-cclogging"></a><span data-ttu-id="b0e44-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="b0e44-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="b0e44-104">O cmdlet Stop-CcLogging para de gerar logs de chamadas de entrada e de saída para o dispositivo do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="b0e44-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="b0e44-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="b0e44-105">Examples</span></span>
<span data-ttu-id="b0e44-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="b0e44-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="b0e44-107">Example 1</span></span>

<span data-ttu-id="b0e44-108">O exemplo seguinte para de gerar logs de chamadas de entrada e de saída: </span><span class="sxs-lookup"><span data-stu-id="b0e44-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="b0e44-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="b0e44-109">Example 2</span></span>

<span data-ttu-id="b0e44-110">O exemplo seguinte para de gerar logs de chamadas de entrada e de saída e limpa os arquivos em cache:</span><span class="sxs-lookup"><span data-stu-id="b0e44-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="b0e44-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="b0e44-111">Detailed Description</span></span>
<span data-ttu-id="b0e44-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-112"></span></span>

<span data-ttu-id="b0e44-p101">O cmdlet Stop-CcLogging para de registrar em log as chamadas de entrada e de saída em um dispositivo. Por padrão, o registro em log para automaticamente depois de quatro horas.</span><span class="sxs-lookup"><span data-stu-id="b0e44-p101">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance. By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="b0e44-115">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="b0e44-115">Parameters</span></span>
<span data-ttu-id="b0e44-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-116"></span></span>

|<span data-ttu-id="b0e44-117">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="b0e44-117">**Parameter**</span></span>|<span data-ttu-id="b0e44-118">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="b0e44-118">**Required**</span></span>|<span data-ttu-id="b0e44-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b0e44-119">**Type**</span></span>|<span data-ttu-id="b0e44-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b0e44-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="b0e44-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="b0e44-121">RemoveCache</span></span> <br/> | <span data-ttu-id="b0e44-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="b0e44-122">Optional</span></span> <br/> | <span data-ttu-id="b0e44-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="b0e44-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="b0e44-124">Remove o registro em log de arquivos em cache. </span><span class="sxs-lookup"><span data-stu-id="b0e44-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="b0e44-125">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="b0e44-125">Input Types</span></span>
<span data-ttu-id="b0e44-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-126"></span></span>

<span data-ttu-id="b0e44-p102">Nenhum. O cmdlet Stop-CcLogging não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="b0e44-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="b0e44-129">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="b0e44-129">Return Types</span></span>
<span data-ttu-id="b0e44-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-130"></span></span>

<span data-ttu-id="b0e44-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="b0e44-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b0e44-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="b0e44-132">See also</span></span>
<span data-ttu-id="b0e44-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="b0e44-133"></span></span>

[<span data-ttu-id="b0e44-134">CcLog de pesquisa</span><span class="sxs-lookup"><span data-stu-id="b0e44-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="b0e44-135">Iniciar-CcLogging</span><span class="sxs-lookup"><span data-stu-id="b0e44-135">Start-CcLogging</span></span>](start-cclogging.md)
  

