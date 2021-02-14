---
title: Get-CcApplianceLogDirectory
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
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: O Get-CcApplianceLogDirectory cmdlet mostra o diretório atual onde os logs de um dispositivo do Skype for Business Cloud Connector Edition são armazenados.
ms.openlocfilehash: 284846bbc305d76602ae1e2f065fcdd571c9deb2
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41800821"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="1143c-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="1143c-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="1143c-104">O Get-CcApplianceLogDirectory cmdlet mostra o diretório atual onde os logs de um dispositivo do Skype for Business Cloud Connector Edition são armazenados.</span><span class="sxs-lookup"><span data-stu-id="1143c-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="1143c-105">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="1143c-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="1143c-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="1143c-106">Parameters</span></span>

<span data-ttu-id="1143c-107">Nenhum</span><span class="sxs-lookup"><span data-stu-id="1143c-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="1143c-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1143c-108">Examples</span></span>
<span data-ttu-id="1143c-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="1143c-109"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="1143c-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="1143c-110">Example 1</span></span>

<span data-ttu-id="1143c-111">O exemplo a seguir mostra a pasta atual onde os logs do dispositivo atual do Cloud Connector estão armazenados:</span><span class="sxs-lookup"><span data-stu-id="1143c-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="1143c-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="1143c-112">Detailed Description</span></span>
<span data-ttu-id="1143c-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="1143c-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="1143c-114">O Get-CcApplianceLogDirectory cmdlet mostra o diretório atual onde os logs de um dispositivo do Cloud Connector estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="1143c-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="1143c-115">A pasta padrão é C:\Users \% userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="1143c-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="1143c-116">Você pode alterar o diretório usando o Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="1143c-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="1143c-117">Observação: não há cmdlet que altera apenas o local da pasta de log sem alterar o diretório do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="1143c-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="1143c-118">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="1143c-118">Input Types</span></span>
<span data-ttu-id="1143c-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1143c-119"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="1143c-120">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="1143c-120">None.</span></span> <span data-ttu-id="1143c-121">O Get-CcApplianceLogDirectory cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="1143c-121">The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="1143c-122">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="1143c-122">Return Types</span></span>
<span data-ttu-id="1143c-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1143c-123"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="1143c-124">Este comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="1143c-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1143c-125">Confira também</span><span class="sxs-lookup"><span data-stu-id="1143c-125">See also</span></span>
<span data-ttu-id="1143c-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="1143c-126"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="1143c-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="1143c-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

