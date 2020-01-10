---
title: Start-CcLogging
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 01b62253-2aaf-43ed-9d63-804e31edc522
description: 'O cmdlet Start-CcLogging para de gerar logs de chamadas de entrada e de saída para o dispositivo do Skype for Business Cloud Connector Edition. '
ms.openlocfilehash: 2064fa4efd730812b5073821784ff5c524056341
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003171"
---
# <a name="start-cclogging"></a><span data-ttu-id="e1127-103">Start-CcLogging</span><span class="sxs-lookup"><span data-stu-id="e1127-103">Start-CcLogging</span></span>
 
<span data-ttu-id="e1127-104">O cmdlet Start-CcLogging para de gerar logs de chamadas de entrada e de saída para o dispositivo do Skype for Business Cloud Connector Edition. </span><span class="sxs-lookup"><span data-stu-id="e1127-104">The Start-CcLogging cmdlet generates the incoming and outgoing call log for a Skype for Business Cloud Connector Edition appliance.</span></span> 
  
```powershell
Start-CcLogging
```

## <a name="parameters"></a><span data-ttu-id="e1127-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="e1127-105">Parameters</span></span>

<span data-ttu-id="e1127-106">Nenhum</span><span class="sxs-lookup"><span data-stu-id="e1127-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="e1127-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e1127-107">Examples</span></span>
<span data-ttu-id="e1127-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="e1127-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="e1127-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="e1127-109">Example 1</span></span>

<span data-ttu-id="e1127-110">O exemplo seguinte gera logs de chamadas de entrada e de saída:</span><span class="sxs-lookup"><span data-stu-id="e1127-110">The following example generates the incoming and outgoing call log:</span></span>
  
```powershell
Start-CcLogging
```

## <a name="detailed-description"></a><span data-ttu-id="e1127-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="e1127-111">Detailed Description</span></span>
<span data-ttu-id="e1127-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="e1127-112"></span></span>

<span data-ttu-id="e1127-113">O cmdlet Start-CcLogging fornece uma maneira para os administradores começarem a registrar chamadas de entrada e de saída em um aparelho de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="e1127-113">The Start-CcLogging cmdlet provides a way for administrators to begin logging incoming and outgoing calls on a Cloud Connector appliance.</span></span> <span data-ttu-id="e1127-114">Por padrão, o registro em log para automaticamente depois de quatro horas.</span><span class="sxs-lookup"><span data-stu-id="e1127-114">By default, logging will automatically stop after four hours.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="e1127-115">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="e1127-115">Input Types</span></span>
<span data-ttu-id="e1127-116"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e1127-116"></span></span>

<span data-ttu-id="e1127-p102">Nenhum. O cmdlet Start-CcLogging não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="e1127-p102">None. The Start-CcLogging cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="e1127-119">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="e1127-119">Return Types</span></span>
<span data-ttu-id="e1127-120"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e1127-120"></span></span>

<span data-ttu-id="e1127-121">Nenhum </span><span class="sxs-lookup"><span data-stu-id="e1127-121">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e1127-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e1127-122">See also</span></span>
<span data-ttu-id="e1127-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="e1127-123"></span></span>

[<span data-ttu-id="e1127-124">Search-CcLog</span><span class="sxs-lookup"><span data-stu-id="e1127-124">Search-CcLog</span></span>](search-cclog.md)
  
[<span data-ttu-id="e1127-125">Stop-CcLogging</span><span class="sxs-lookup"><span data-stu-id="e1127-125">Stop-CcLogging</span></span>](stop-cclogging.md)
  

