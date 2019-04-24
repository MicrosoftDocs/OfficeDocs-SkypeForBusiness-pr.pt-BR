---
title: Get-CcApplianceLogDirectory
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: O cmdlet Get-CcApplianceLogDirectory mostra o diretório atual em que os logs do dispositivo do Skype for Business Cloud Connector Edition são armazenados.
ms.openlocfilehash: d1298454bb347356718fdf24d6761acfea1b71b1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233949"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="a5436-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="a5436-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="a5436-104">O cmdlet Get-CcApplianceLogDirectory mostra o diretório atual em que os logs do dispositivo do Skype for Business Cloud Connector Edition são armazenados.</span><span class="sxs-lookup"><span data-stu-id="a5436-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="a5436-105">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="a5436-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="a5436-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a5436-106">Parameters</span></span>

<span data-ttu-id="a5436-107">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a5436-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="a5436-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a5436-108">Examples</span></span>
<span data-ttu-id="a5436-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a5436-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="a5436-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="a5436-110">Example 1</span></span>

<span data-ttu-id="a5436-111">O exemplo a seguir mostra a pasta atual, onde os logs para o aparelho atual do conector de nuvem são armazenados:</span><span class="sxs-lookup"><span data-stu-id="a5436-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="a5436-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="a5436-112">Detailed Description</span></span>
<span data-ttu-id="a5436-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a5436-113"></span></span>

<span data-ttu-id="a5436-114">O cmdlet Get-CcApplianceLogDirectory mostra o diretório atual, onde os logs para um aparelho de conector de nuvem são armazenados.</span><span class="sxs-lookup"><span data-stu-id="a5436-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="a5436-115">A pasta padrão é C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="a5436-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="a5436-116">Você pode alterar o diretório usando o cmdlet Set-CcApplianceDirectory. </span><span class="sxs-lookup"><span data-stu-id="a5436-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="a5436-117">Observação: não há cmdlet que altere somente o local da pasta de log sem alterar o diretório do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="a5436-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="a5436-118">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="a5436-118">Input Types</span></span>
<span data-ttu-id="a5436-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a5436-119"></span></span>

<span data-ttu-id="a5436-p102">Nenhum. O cmdlet Get-CcApplianceLogDirectory não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="a5436-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="a5436-122">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="a5436-122">Return Types</span></span>
<span data-ttu-id="a5436-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a5436-123"></span></span>

<span data-ttu-id="a5436-124">Este comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="a5436-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a5436-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="a5436-125">See also</span></span>
<span data-ttu-id="a5436-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a5436-126"></span></span>

[<span data-ttu-id="a5436-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="a5436-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

