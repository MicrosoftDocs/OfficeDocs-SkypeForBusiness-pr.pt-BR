---
title: Get-CcVersion
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 6/30/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Retorna a versão do dispositivo do Cloud Connector. O Get-CCVersion só pode ser usado no computador host do Cloud Connector.
ms.openlocfilehash: 5e5428e53d53eec66bafa9eb566059ef1b5a5833
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32233754"
---
# <a name="get-ccversion"></a><span data-ttu-id="d87c3-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="d87c3-104">Get-CcVersion</span></span>
 
<span data-ttu-id="d87c3-p102">Retorna a versão do dispositivo do Cloud Connector. O Get-CCVersion só pode ser usado no computador host do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="d87c3-p102">Returns the version of the Cloud Connector appliance. Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="d87c3-107">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="d87c3-107">Detailed Description</span></span>

<span data-ttu-id="d87c3-108">Retorna a versão do aparelho de conector de nuvem, com base em scripts do PowerShell instalados, arquivos no diretório aparelho e as máquinas virtuais implantadas em um servidor host.</span><span class="sxs-lookup"><span data-stu-id="d87c3-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d87c3-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d87c3-109">Parameters</span></span>

|<span data-ttu-id="d87c3-110">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="d87c3-110">**Parameter**</span></span>|<span data-ttu-id="d87c3-111">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="d87c3-111">**Required**</span></span>|<span data-ttu-id="d87c3-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d87c3-112">**Type**</span></span>|<span data-ttu-id="d87c3-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d87c3-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d87c3-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="d87c3-114">VersionType</span></span>  <br/> |<span data-ttu-id="d87c3-115">Opcional</span><span class="sxs-lookup"><span data-stu-id="d87c3-115">Optional</span></span>  <br/> |<span data-ttu-id="d87c3-116">System.String</span><span class="sxs-lookup"><span data-stu-id="d87c3-116">System.String</span></span>  <br/> |<span data-ttu-id="d87c3-p103">Tipo de versão. O valor do parâmetro pode ser RunningScripts, RunningBits, BackupBits ou todos. O valor padrão é RunningScripts. </span><span class="sxs-lookup"><span data-stu-id="d87c3-p103">Type of version. Value of parameter can be RunningScripts, RunningBits, BackupBits or All. Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="d87c3-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d87c3-120">Examples</span></span>
<span data-ttu-id="d87c3-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d87c3-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="d87c3-122">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="d87c3-122">Example 1</span></span>

<span data-ttu-id="d87c3-123">O exemplo a seguir mostra a versão do conector de nuvem do script atualmente em execução no seu console aberto do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d87c3-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="d87c3-124">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="d87c3-124">Example 2</span></span>

<span data-ttu-id="d87c3-125">O exemplo a seguir mostra a versão do conector de nuvem de binários implantado para as máquinas virtuais em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="d87c3-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="d87c3-126">Você pode ver a versão nos nomes das máquinas virtuais em execução no Hyper-v Manager:</span><span class="sxs-lookup"><span data-stu-id="d87c3-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="d87c3-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="d87c3-127">Input Types</span></span>
<span data-ttu-id="d87c3-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d87c3-128"></span></span>

<span data-ttu-id="d87c3-p105">Nenhum. O cmdlet Get-CcVersion não aceita entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="d87c3-p105">None. The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d87c3-131">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="d87c3-131">Return Types</span></span>
<span data-ttu-id="d87c3-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d87c3-132"></span></span>

<span data-ttu-id="d87c3-133">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d87c3-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d87c3-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d87c3-134">See also</span></span>
<span data-ttu-id="d87c3-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d87c3-135"></span></span>

<span data-ttu-id="d87c3-136">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d87c3-136">None.</span></span>
  

