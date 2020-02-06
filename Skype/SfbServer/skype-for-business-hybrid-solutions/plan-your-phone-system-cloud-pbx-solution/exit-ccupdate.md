---
title: Exit-CcUpdate
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
ms.assetid: 463dce1e-fb60-487d-bcf1-69e7b03ecd14
description: 'O cmdlet Exit-CcUpdate sai do modo de manutenção de atualização no servidor host do Skype for Business Cloud Connector Edition.  '
ms.openlocfilehash: 315d6b7dccb6708901128bf8faa29a60f712e833
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801761"
---
# <a name="exit-ccupdate"></a><span data-ttu-id="8602b-103">Exit-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="8602b-103">Exit-CcUpdate</span></span>
 
<span data-ttu-id="8602b-104">O cmdlet Exit-CcUpdate sai do modo de manutenção de atualização no servidor host do Skype for Business Cloud Connector Edition.  </span><span class="sxs-lookup"><span data-stu-id="8602b-104">The Exit-CcUpdate cmdlet exits update maintenance mode on the Skype for Business Cloud Connector Edition host server.</span></span> 
  
<span data-ttu-id="8602b-105">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1 e 1.4.2. </span><span class="sxs-lookup"><span data-stu-id="8602b-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="parameters"></a><span data-ttu-id="8602b-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="8602b-106">Parameters</span></span>

<span data-ttu-id="8602b-107">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8602b-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="8602b-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="8602b-108">Examples</span></span>
<span data-ttu-id="8602b-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="8602b-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="8602b-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="8602b-110">Example 1</span></span>

<span data-ttu-id="8602b-111">O comando a seguir coloca o dispositivo novamente no modo de produção: </span><span class="sxs-lookup"><span data-stu-id="8602b-111">The following command puts the appliance on which it runs back into production mode:</span></span> 
  
```powershell
Exit-CcUpdate
```

## <a name="detailed-description"></a><span data-ttu-id="8602b-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="8602b-112">Detailed Description</span></span>
<span data-ttu-id="8602b-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="8602b-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="8602b-114">Se você tiver dispositivos que foram colocados no modo de manutenção especificando o cmdlet Enter-CcUpdate, o cmdlet Exit-CcUpdate os colocará novamente no modo de produção.  </span><span class="sxs-lookup"><span data-stu-id="8602b-114">If you have appliances that you have put in maintenance mode by specifying the Enter-CcUpdate cmdlet, the Exit-CcUpdate cmdlet will put these back into production mode.</span></span> 
  
<span data-ttu-id="8602b-115">Para obter mais informações sobre como colocar os dispositivos no modo de manutenção, veja Enter-CcUpdate.</span><span class="sxs-lookup"><span data-stu-id="8602b-115">For more information about putting appliances in maintenance mode, see Enter-CcUpdate.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="8602b-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="8602b-116">Input Types</span></span>
<span data-ttu-id="8602b-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8602b-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="8602b-p101">Nenhum. O cmdlet Exit-CCUpdate não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="8602b-p101">None. The Exit-CcUpdate cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="8602b-120">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="8602b-120">Return Types</span></span>
<span data-ttu-id="8602b-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8602b-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="8602b-122">Nenhum </span><span class="sxs-lookup"><span data-stu-id="8602b-122">None</span></span> 
  
## <a name="see-also"></a><span data-ttu-id="8602b-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8602b-123">See also</span></span>
<span data-ttu-id="8602b-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="8602b-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="8602b-125">Enter-CcUpdate</span><span class="sxs-lookup"><span data-stu-id="8602b-125">Enter-CcUpdate</span></span>](enter-ccupdate.md)
  

