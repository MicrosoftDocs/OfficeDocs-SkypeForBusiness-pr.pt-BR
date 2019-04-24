---
title: Stop-CcLogging
ms.reviewer: ''
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
ms.openlocfilehash: eaccde49421cd22e32b23b89d8b5ea42dd073912
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32250629"
---
# <a name="stop-cclogging"></a><span data-ttu-id="39826-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="39826-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="39826-104">O cmdlet Stop-CcLogging para de gerar logs de chamadas de entrada e de saída para o dispositivo do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="39826-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="39826-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="39826-105">Examples</span></span>
<span data-ttu-id="39826-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="39826-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="39826-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="39826-107">Example 1</span></span>

<span data-ttu-id="39826-108">O exemplo seguinte para de gerar logs de chamadas de entrada e de saída: </span><span class="sxs-lookup"><span data-stu-id="39826-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="39826-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="39826-109">Example 2</span></span>

<span data-ttu-id="39826-110">O exemplo seguinte para de gerar logs de chamadas de entrada e de saída e limpa os arquivos em cache:</span><span class="sxs-lookup"><span data-stu-id="39826-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="39826-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="39826-111">Detailed Description</span></span>
<span data-ttu-id="39826-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="39826-112"></span></span>

<span data-ttu-id="39826-113">O cmdlet Stop-CcLogging para de registrar em log as chamadas de entrada e de saída em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="39826-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="39826-114">Por padrão, o registro em log para automaticamente depois de quatro horas.</span><span class="sxs-lookup"><span data-stu-id="39826-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="39826-115">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="39826-115">Parameters</span></span>
<span data-ttu-id="39826-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="39826-116"></span></span>

|<span data-ttu-id="39826-117">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="39826-117">**Parameter**</span></span>|<span data-ttu-id="39826-118">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="39826-118">**Required**</span></span>|<span data-ttu-id="39826-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="39826-119">**Type**</span></span>|<span data-ttu-id="39826-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="39826-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="39826-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="39826-121">RemoveCache</span></span> <br/> | <span data-ttu-id="39826-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="39826-122">Optional</span></span> <br/> | <span data-ttu-id="39826-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="39826-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="39826-124">Remove o registro em log de arquivos em cache. </span><span class="sxs-lookup"><span data-stu-id="39826-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="39826-125">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="39826-125">Input Types</span></span>
<span data-ttu-id="39826-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="39826-126"></span></span>

<span data-ttu-id="39826-p102">Nenhum. O cmdlet Stop-CcLogging não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="39826-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="39826-129">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="39826-129">Return Types</span></span>
<span data-ttu-id="39826-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="39826-130"></span></span>

<span data-ttu-id="39826-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="39826-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="39826-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="39826-132">See also</span></span>
<span data-ttu-id="39826-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="39826-133"></span></span>

[<span data-ttu-id="39826-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="39826-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="39826-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="39826-135">Start-CcLogging</span></span>](start-cclogging.md)
  

