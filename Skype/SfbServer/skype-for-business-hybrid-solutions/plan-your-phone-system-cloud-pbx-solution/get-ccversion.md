---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Retorna a versão do dispositivo do Cloud Connector. O Get-CCVersion só pode ser usado no computador host do Cloud Connector.
ms.openlocfilehash: a7d50bbcd01dc80fe3e2202286c1adc1b5d5f9bd
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003341"
---
# <a name="get-ccversion"></a><span data-ttu-id="52976-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="52976-104">Get-CcVersion</span></span>
 
<span data-ttu-id="52976-p102">Retorna a versão do dispositivo do Cloud Connector. O Get-CCVersion só pode ser usado no computador host do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="52976-p102">Returns the version of the Cloud Connector appliance. Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="52976-107">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="52976-107">Detailed Description</span></span>

<span data-ttu-id="52976-108">Retorna a versão do aparelho do conector de nuvem com base em scripts do PowerShell instalados, arquivos no diretório de aplicativos e máquinas virtuais implantadas no servidor host.</span><span class="sxs-lookup"><span data-stu-id="52976-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="52976-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="52976-109">Parameters</span></span>

|<span data-ttu-id="52976-110">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="52976-110">**Parameter**</span></span>|<span data-ttu-id="52976-111">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="52976-111">**Required**</span></span>|<span data-ttu-id="52976-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="52976-112">**Type**</span></span>|<span data-ttu-id="52976-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="52976-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="52976-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="52976-114">VersionType</span></span>  <br/> |<span data-ttu-id="52976-115">Opcional</span><span class="sxs-lookup"><span data-stu-id="52976-115">Optional</span></span>  <br/> |<span data-ttu-id="52976-116">System.String</span><span class="sxs-lookup"><span data-stu-id="52976-116">System.String</span></span>  <br/> |<span data-ttu-id="52976-p103">Tipo de versão. O valor do parâmetro pode ser RunningScripts, RunningBits, BackupBits ou todos. O valor padrão é RunningScripts. </span><span class="sxs-lookup"><span data-stu-id="52976-p103">Type of version. Value of parameter can be RunningScripts, RunningBits, BackupBits or All. Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="52976-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="52976-120">Examples</span></span>
<span data-ttu-id="52976-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="52976-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="52976-122">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="52976-122">Example 1</span></span>

<span data-ttu-id="52976-123">O exemplo a seguir mostra a versão do conector de nuvem do script em execução no momento no console do PowerShell aberto:</span><span class="sxs-lookup"><span data-stu-id="52976-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="52976-124">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="52976-124">Example 2</span></span>

<span data-ttu-id="52976-125">O exemplo a seguir mostra a versão do conector de nuvem dos binários em execução implantados nas máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="52976-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="52976-126">Você pode ver a versão nos nomes das máquinas virtuais em execução no Hyper-v Manager:</span><span class="sxs-lookup"><span data-stu-id="52976-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="52976-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="52976-127">Input Types</span></span>
<span data-ttu-id="52976-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="52976-128"></span></span>

<span data-ttu-id="52976-p105">Nenhum. O cmdlet Get-CcVersion não aceita entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="52976-p105">None. The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="52976-131">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="52976-131">Return Types</span></span>
<span data-ttu-id="52976-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="52976-132"></span></span>

<span data-ttu-id="52976-133">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="52976-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="52976-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="52976-134">See also</span></span>
<span data-ttu-id="52976-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="52976-135"></span></span>

<span data-ttu-id="52976-136">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="52976-136">None.</span></span>
  

