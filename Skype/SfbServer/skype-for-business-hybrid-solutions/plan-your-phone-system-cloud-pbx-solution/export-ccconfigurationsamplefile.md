---
title: Export-CcConfigurationSampleFile
ms.reviewer: ''
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
ms.openlocfilehash: 3154ff3492899de244c3033e4e35345132d04f20
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233985"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="f2579-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="f2579-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="f2579-p102">O cmdlet Export-CcConfigurationSampleFile exporta um arquivo (.ini) de configuração de amostra do Skype for Business Cloud Connector Edition para o diretório de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo para usar na implantação.</span><span class="sxs-lookup"><span data-stu-id="f2579-p102">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance. You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="f2579-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1 e 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="f2579-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="f2579-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="f2579-108">Parameters</span></span>

<span data-ttu-id="f2579-109">Nenhum</span><span class="sxs-lookup"><span data-stu-id="f2579-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="f2579-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f2579-110">Examples</span></span>
<span data-ttu-id="f2579-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="f2579-111"></span></span>

### <a name="example-1"></a><span data-ttu-id="f2579-112">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="f2579-112">Example 1</span></span>

<span data-ttu-id="f2579-113">O exemplo a seguir baixa um arquivo de configuração de amostra do site da Microsoft e grava-os para o diretório appliance do aparelho de conector de nuvem:</span><span class="sxs-lookup"><span data-stu-id="f2579-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="f2579-114">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="f2579-114">Detailed Description</span></span>
<span data-ttu-id="f2579-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="f2579-115"></span></span>

<span data-ttu-id="f2579-116">A versão atual do conector de nuvem exige que você forneça vários parâmetros no arquivo. ini; Por exemplo, parâmetros como os endereços IP de máquinas virtuais para os componentes do conector de nuvem, nomes de componente, os parâmetros de gateway e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="f2579-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="f2579-117">Esse cmdlet, quando executado na máquina host do conector de nuvem, baixa um arquivo. ini de exemplo com exemplos de configuração do site da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f2579-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="f2579-118">O cmdlet grava o arquivo para o diretório appliance do aparelho de conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="f2579-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="f2579-119">Esse diretório é especificado usando o cmdlet Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="f2579-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="f2579-120">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="f2579-120">Input Types</span></span>
<span data-ttu-id="f2579-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f2579-121"></span></span>

<span data-ttu-id="f2579-p104">Nenhum. O cmdlet Export-CcConfigurationSampleFile não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="f2579-p104">None. The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="f2579-124">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="f2579-124">Return Types</span></span>
<span data-ttu-id="f2579-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f2579-125"></span></span>

<span data-ttu-id="f2579-126">Nenhum </span><span class="sxs-lookup"><span data-stu-id="f2579-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="f2579-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f2579-127">See also</span></span>
<span data-ttu-id="f2579-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="f2579-128"></span></span>

[<span data-ttu-id="f2579-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="f2579-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

