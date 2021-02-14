---
title: Export-CcConfigurationSampleFile
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
ms.assetid: 0aaacc05-3430-4579-acbf-d7c7670c3864
description: O cmdlet Export-CcConfigurationSampleFile exporta um arquivo de configuração de exemplo (.ini) do Skype for Business Cloud Connector Edition para o diretório de dispositivos de um dispositivo do Cloud Connector. Você pode modificar e renomear o arquivo a ser usado para sua implantação.
ms.openlocfilehash: a29a3db8e77ee239263d015bd7a3efcf4f3f7c5c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41801001"
---
# <a name="export-ccconfigurationsamplefile"></a><span data-ttu-id="a5549-104">Export-CcConfigurationSampleFile</span><span class="sxs-lookup"><span data-stu-id="a5549-104">Export-CcConfigurationSampleFile</span></span>
 
<span data-ttu-id="a5549-105">O cmdlet Export-CcConfigurationSampleFile exporta um arquivo de configuração de exemplo (.ini) do Skype for Business Cloud Connector Edition para o diretório de dispositivos de um dispositivo do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a5549-105">The Export-CcConfigurationSampleFile cmdlet exports a Skype for Business Cloud Connector Edition sample configuration file (.ini) to the appliance directory of a Cloud Connector appliance.</span></span> <span data-ttu-id="a5549-106">Você pode modificar e renomear o arquivo a ser usado para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="a5549-106">You can modify and rename the file to use for your deployment.</span></span>
  
<span data-ttu-id="a5549-107">Este cmdlet se aplica ao Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span><span class="sxs-lookup"><span data-stu-id="a5549-107">This cmdlet applies to Skype for Business Cloud Connector Edition 1.4.1, 1.4.2.</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="parameters"></a><span data-ttu-id="a5549-108">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="a5549-108">Parameters</span></span>

<span data-ttu-id="a5549-109">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a5549-109">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="a5549-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a5549-110">Examples</span></span>
<span data-ttu-id="a5549-111"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="a5549-111"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="a5549-112">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="a5549-112">Example 1</span></span>

<span data-ttu-id="a5549-113">O exemplo a seguir baixa um arquivo de configuração de exemplo do site da Microsoft e o grava no diretório de dispositivos do dispositivo do Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="a5549-113">The following example downloads a sample configuration file from the Microsoft site and writes it to the appliance directory of the Cloud Connector appliance:</span></span>
  
```powershell
Export-CcConfigurationSampleFile
```

## <a name="detailed-description"></a><span data-ttu-id="a5549-114">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="a5549-114">Detailed Description</span></span>
<span data-ttu-id="a5549-115"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="a5549-115"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="a5549-116">A versão atual do Cloud Connector exige que você forneça vários parâmetros no arquivo .ini; por exemplo, parâmetros como os endereços IP de máquinas virtuais para os componentes do Cloud Connector, nomes de componentes, parâmetros de gateway e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="a5549-116">The current version of Cloud Connector requires you to provide several parameters in the .ini file; for example, parameters such as the IP addresses of virtual machines for the Cloud Connector components, component names, gateway parameters, and so on.</span></span>
  
<span data-ttu-id="a5549-117">Este cmdlet, quando executado no computador host do Cloud Connector, baixa um arquivo .ini de exemplo com exemplos de configuração do site da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a5549-117">This cmdlet, when run on the host machine of Cloud Connector, downloads a sample .ini file with configuration examples from the Microsoft site.</span></span> <span data-ttu-id="a5549-118">O cmdlet grava o arquivo no diretório de dispositivos do dispositivo do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="a5549-118">The cmdlet writes the file to the appliance directory of the Cloud Connector appliance.</span></span> <span data-ttu-id="a5549-119">O diretório do dispositivo é especificado usando o Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="a5549-119">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span>
  
## <a name="input-types"></a><span data-ttu-id="a5549-120">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="a5549-120">Input Types</span></span>
<span data-ttu-id="a5549-121"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a5549-121"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="a5549-122">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="a5549-122">None.</span></span> <span data-ttu-id="a5549-123">O Export-CcConfigurationSampleFile cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="a5549-123">The Export-CcConfigurationSampleFile cmdlet does not accept pipelined input.</span></span> 
  
## <a name="return-types"></a><span data-ttu-id="a5549-124">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="a5549-124">Return Types</span></span>
<span data-ttu-id="a5549-125"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a5549-125"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="a5549-126">Nenhum</span><span class="sxs-lookup"><span data-stu-id="a5549-126">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="a5549-127">Confira também</span><span class="sxs-lookup"><span data-stu-id="a5549-127">See also</span></span>
<span data-ttu-id="a5549-128"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="a5549-128"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="a5549-129">Set-CcApplianceDirectory</span><span class="sxs-lookup"><span data-stu-id="a5549-129">Set-CcApplianceDirectory</span></span>](set-ccappliancedirectory.md)
  

