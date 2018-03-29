---
title: Export-CcConfigurationSampleFile
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: O cmdlet Export-CcConfigurationSampleFile exporta um arquivo (.ini) de configuração de amostra do Skype for Business Cloud Connector Edition para o diretório de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo para usar na implantação.
ms.openlocfilehash: f91b9c7eb8ade4e5edcf1c83c5ddef205e0f3721
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="4b5e8-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="4b5e8-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="4b5e8-p102">O cmdlet Export-CcConfigurationSampleFile exporta um arquivo (.ini) de configuração de amostra do Skype for Business Cloud Connector Edition para o diretório de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo para usar na implantação.</span><span class="sxs-lookup"><span data-stu-id="4b5e8-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="4b5e8-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1 e 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="4b5e8-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="4b5e8-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="4b5e8-108">Parameters</span></span>

<span data-ttu-id="4b5e8-109">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4b5e8-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="4b5e8-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4b5e8-110">Examples</span></span>
<span data-ttu-id="4b5e8-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="4b5e8-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="4b5e8-112">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="4b5e8-112">Example 1</span></span>

<span data-ttu-id="4b5e8-113">O exemplo a seguir baixa um arquivo de configuração de amostra do site da Microsoft e grava-os para o diretório appliance do aparelho de conector de nuvem:</span><span class="sxs-lookup"><span data-stu-id="4b5e8-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="4b5e8-114">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="4b5e8-114">Detailed Description</span></span>
<span data-ttu-id="4b5e8-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="4b5e8-115"></span></span>

<span data-ttu-id="4b5e8-116">A versão atual do conector de nuvem exige que você forneça vários parâmetros no arquivo. ini; Por exemplo, parâmetros como os endereços IP de máquinas virtuais para os componentes do conector de nuvem, nomes de componente, os parâmetros de gateway e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="4b5e8-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="4b5e8-117">Esse cmdlet, quando executado na máquina host do conector de nuvem, baixa um arquivo. ini de exemplo com exemplos de configuração do site da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4b5e8-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="4b5e8-118">O cmdlet grava o arquivo para o diretório appliance do aparelho de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="4b5e8-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="4b5e8-119">Esse diretório é especificado usando o cmdlet Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="4b5e8-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="4b5e8-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="4b5e8-120">Input Types</span></span>
<span data-ttu-id="4b5e8-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4b5e8-121"></span></span>

<span data-ttu-id="4b5e8-p104">Nenhum. O cmdlet Export-CcConfigurationSampleFile não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="4b5e8-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="4b5e8-124">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="4b5e8-124">Return Types</span></span>
<span data-ttu-id="4b5e8-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4b5e8-125"></span></span>

<span data-ttu-id="4b5e8-126">Nenhum</span><span class="sxs-lookup"><span data-stu-id="4b5e8-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="4b5e8-127">Consulte também</span><span class="sxs-lookup"><span data-stu-id="4b5e8-127">See also</span></span>
<span data-ttu-id="4b5e8-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="4b5e8-128"></span></span>

[<span data-ttu-id="4b5e8-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="4b5e8-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

