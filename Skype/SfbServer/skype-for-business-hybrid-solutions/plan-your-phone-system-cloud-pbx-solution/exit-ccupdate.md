---
title: Exit-CcUpdate
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 'O cmdlet Exit-CcUpdate sai do modo de manutenção de atualização no servidor host do Skype for Business Cloud Connector Edition.  '
ms.openlocfilehash: f7b913fd6aaa77a18df66fd86a36d5d4838f69d4
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="exit-ccupdate"></a><span data-ttu-id="047b6-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="047b6-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="047b6-104">O cmdlet Exit-CcUpdate sai do modo de manutenção de atualização no servidor host do Skype for Business Cloud Connector Edition.  </span><span class="sxs-lookup"><span data-stu-id="047b6-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="047b6-105">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1 e 1.4.2. </span><span class="sxs-lookup"><span data-stu-id="047b6-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="047b6-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="047b6-106">Parameters</span></span>

<span data-ttu-id="047b6-107">Nenhum</span><span class="sxs-lookup"><span data-stu-id="047b6-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="047b6-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="047b6-108">Examples</span></span>
<span data-ttu-id="047b6-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="047b6-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="047b6-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="047b6-110">Example 1</span></span>

<span data-ttu-id="047b6-111">O comando a seguir coloca o dispositivo novamente no modo de produção: </span><span class="sxs-lookup"><span data-stu-id="047b6-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="047b6-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="047b6-112">Detailed Description</span></span>
<span data-ttu-id="047b6-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="047b6-113"></span></span>

<span data-ttu-id="047b6-114">Se você tiver dispositivos que foram colocados no modo de manutenção especificando o cmdlet Enter-CcUpdate, o cmdlet Exit-CcUpdate os colocará novamente no modo de produção.  </span><span class="sxs-lookup"><span data-stu-id="047b6-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="047b6-115">Para obter mais informações sobre como colocar os dispositivos no modo de manutenção, veja Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="047b6-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="047b6-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="047b6-116">Input Types</span></span>
<span data-ttu-id="047b6-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="047b6-117"></span></span>

<span data-ttu-id="047b6-p101">Nenhum. O cmdlet Exit-CCUpdate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="047b6-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="047b6-120">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="047b6-120">Return Types</span></span>
<span data-ttu-id="047b6-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="047b6-121"></span></span>

<span data-ttu-id="047b6-122">Nenhum</span><span class="sxs-lookup"><span data-stu-id="047b6-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="047b6-123">Consulte também</span><span class="sxs-lookup"><span data-stu-id="047b6-123">See also</span></span>
<span data-ttu-id="047b6-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="047b6-124"></span></span>

[<span data-ttu-id="047b6-125">Insira-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="047b6-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

