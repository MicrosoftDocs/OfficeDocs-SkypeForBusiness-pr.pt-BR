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
localization_priority: Normal
ms.assetid: 8f16d8ea-8161-4b07-9c79-d57e786b3e78
description: O cmdlet Get-CcApplianceLogDirectory mostra o diretório atual em que os logs do dispositivo do Skype for Business Cloud Connector Edition são armazenados.
ms.openlocfilehash: a8b7e1b13302bec27c2fe784804f8f43fe2e023c
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003391"
---
# <a name="get-ccappliancelogdirectory"></a><span data-ttu-id="2c1a5-103">Get-CcApplianceLogDirectory</span><span class="sxs-lookup"><span data-stu-id="2c1a5-103">Get-CcApplianceLogDirectory</span></span>
 
<span data-ttu-id="2c1a5-104">O cmdlet Get-CcApplianceLogDirectory mostra o diretório atual em que os logs do dispositivo do Skype for Business Cloud Connector Edition são armazenados.</span><span class="sxs-lookup"><span data-stu-id="2c1a5-104">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Skype for Business Cloud Connector Edition appliance are stored.</span></span>
  
<span data-ttu-id="2c1a5-105">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="2c1a5-105">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="parameters"></a><span data-ttu-id="2c1a5-106">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2c1a5-106">Parameters</span></span>

<span data-ttu-id="2c1a5-107">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2c1a5-107">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="2c1a5-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2c1a5-108">Examples</span></span>
<span data-ttu-id="2c1a5-109"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1a5-109"></span></span>

### <a name="example-1"></a><span data-ttu-id="2c1a5-110">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="2c1a5-110">Example 1</span></span>

<span data-ttu-id="2c1a5-111">O exemplo a seguir mostra a pasta atual em que os logs do aplicativo do conector de nuvem atual são armazenados:</span><span class="sxs-lookup"><span data-stu-id="2c1a5-111">The following example shows the current folder where logs for the current appliance of Cloud Connector are stored:</span></span>
  
```powershell
Get-CcApplianceLogDirectory
```

## <a name="detailed-description"></a><span data-ttu-id="2c1a5-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="2c1a5-112">Detailed Description</span></span>
<span data-ttu-id="2c1a5-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1a5-113"></span></span>

<span data-ttu-id="2c1a5-114">O cmdlet Get-CcApplianceLogDirectory mostra o diretório atual em que os logs para um aparelho de conector de nuvem são armazenados.</span><span class="sxs-lookup"><span data-stu-id="2c1a5-114">The Get-CcApplianceLogDirectory cmdlet shows the current directory where logs for a Cloud Connector appliance are stored.</span></span> <span data-ttu-id="2c1a5-115">A pasta padrão é C:\Users\%USERPROFILE%\CloudConnector\ApplianceRoot\Logs.</span><span class="sxs-lookup"><span data-stu-id="2c1a5-115">The default folder is C:\Users\%userprofile%\CloudConnector\ApplianceRoot\Logs.</span></span> 
  
<span data-ttu-id="2c1a5-116">Você pode alterar o diretório usando o cmdlet Set-CcApplianceDirectory. </span><span class="sxs-lookup"><span data-stu-id="2c1a5-116">You can change the directory by using the Set-CcApplianceDirectory cmdlet.</span></span> 
  
<span data-ttu-id="2c1a5-117">Observação: não há cmdlet que altere somente o local da pasta de log sem alterar o diretório do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2c1a5-117">Note: There is no cmdlet that changes only the log folder location without changing the appliance directory.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="2c1a5-118">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="2c1a5-118">Input Types</span></span>
<span data-ttu-id="2c1a5-119"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1a5-119"></span></span>

<span data-ttu-id="2c1a5-p102">Nenhum. O cmdlet Get-CcApplianceLogDirectory não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="2c1a5-p102">None. The Get-CcApplianceLogDirectory cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2c1a5-122">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="2c1a5-122">Return Types</span></span>
<span data-ttu-id="2c1a5-123"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1a5-123"></span></span>

<span data-ttu-id="2c1a5-124">Este comando retorna um caminho de arquivo.</span><span class="sxs-lookup"><span data-stu-id="2c1a5-124">This command returns a file path.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2c1a5-125">Consulte também</span><span class="sxs-lookup"><span data-stu-id="2c1a5-125">See also</span></span>
<span data-ttu-id="2c1a5-126"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2c1a5-126"></span></span>

[<span data-ttu-id="2c1a5-127">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="2c1a5-127">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

