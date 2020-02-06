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
description: O cmdlet Stop-CcLogging para de gerar logs de chamadas de entrada e de saída para o dispositivo do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: 8a012e9b1a94c3698cc61da4326eb0ccbb27bca2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824155"
---
# <a name="stop-cclogging"></a><span data-ttu-id="426cb-103">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="426cb-103">Stop-CcLogging</span></span>
 
<span data-ttu-id="426cb-104">O cmdlet Stop-CcLogging para de gerar logs de chamadas de entrada e de saída para o dispositivo do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="426cb-104">The Stop-CcLogging cmdlet stops generating the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span>
  
```powershell
Stop-CcLogging [-RemoveCache]
```

## <a name="examples"></a><span data-ttu-id="426cb-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="426cb-105">Examples</span></span>
<span data-ttu-id="426cb-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="426cb-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="426cb-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="426cb-107">Example 1</span></span>

<span data-ttu-id="426cb-108">O exemplo seguinte para de gerar logs de chamadas de entrada e de saída: </span><span class="sxs-lookup"><span data-stu-id="426cb-108">The following example stops generating the incoming and outgoing call log:</span></span> 
  
```powershell
Stop-CcLogging
```

### <a name="example-2"></a><span data-ttu-id="426cb-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="426cb-109">Example 2</span></span>

<span data-ttu-id="426cb-110">O exemplo seguinte para de gerar logs de chamadas de entrada e de saída e limpa os arquivos em cache:</span><span class="sxs-lookup"><span data-stu-id="426cb-110">The next example stops generating the incoming and outgoing call log and cleans up the cache files:</span></span>
  
```powershell
Stop-CcLogging -RemoveCache
```

## <a name="detailed-description"></a><span data-ttu-id="426cb-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="426cb-111">Detailed Description</span></span>
<span data-ttu-id="426cb-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="426cb-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="426cb-113">O cmdlet Stop-CcLogging para de registrar em log as chamadas de entrada e de saída em um dispositivo.</span><span class="sxs-lookup"><span data-stu-id="426cb-113">The Stop-CcLogging cmdlet stops logging of incoming and outgoing calls on an appliance.</span></span> <span data-ttu-id="426cb-114">Por padrão, o registro em log para automaticamente depois de quatro horas.</span><span class="sxs-lookup"><span data-stu-id="426cb-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="426cb-115">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="426cb-115">Parameters</span></span>
<span data-ttu-id="426cb-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="426cb-116"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="426cb-117">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="426cb-117">**Parameter**</span></span>|<span data-ttu-id="426cb-118">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="426cb-118">**Required**</span></span>|<span data-ttu-id="426cb-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="426cb-119">**Type**</span></span>|<span data-ttu-id="426cb-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="426cb-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="426cb-121">RemoveCache</span><span class="sxs-lookup"><span data-stu-id="426cb-121">RemoveCache</span></span> <br/> | <span data-ttu-id="426cb-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="426cb-122">Optional</span></span> <br/> | <span data-ttu-id="426cb-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="426cb-123">System.Management.Automation.SwitchParameter</span></span> <br/> |<span data-ttu-id="426cb-124">Remove o registro em log de arquivos em cache. </span><span class="sxs-lookup"><span data-stu-id="426cb-124">Removes the logging cache files.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="426cb-125">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="426cb-125">Input Types</span></span>
<span data-ttu-id="426cb-126"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="426cb-126"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="426cb-p102">Nenhum. O cmdlet Stop-CcLogging não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="426cb-p102">None. The Stop-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="426cb-129">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="426cb-129">Return Types</span></span>
<span data-ttu-id="426cb-130"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="426cb-130"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="426cb-131">Nenhum</span><span class="sxs-lookup"><span data-stu-id="426cb-131">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="426cb-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="426cb-132">See also</span></span>
<span data-ttu-id="426cb-133"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="426cb-133"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="426cb-134">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="426cb-134">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="426cb-135">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="426cb-135">Start-CcLogging</span></span>](start-cclogging.md)
  

