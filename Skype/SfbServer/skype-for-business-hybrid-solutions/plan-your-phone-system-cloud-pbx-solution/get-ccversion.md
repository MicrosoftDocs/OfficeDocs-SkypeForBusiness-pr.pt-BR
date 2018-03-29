---
title: Get-CcVersion
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
ms.openlocfilehash: 8391264603a73e3f594122dcdd2eb62b9ba19978
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="get-ccversion"></a><span data-ttu-id="6797d-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="6797d-104">Get-CcVersion</span></span>
 
<span data-ttu-id="6797d-105">Retorna a versão do dispositivo do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6797d-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="6797d-106">O Get-CCVersion só pode ser usado no computador host do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6797d-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="6797d-107">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="6797d-107">Detailed Description</span></span>

<span data-ttu-id="6797d-108">Retorna a versão do aparelho de conector de nuvem, com base em scripts do PowerShell instalados, arquivos no diretório aparelho e as máquinas virtuais implantadas em um servidor host.</span><span class="sxs-lookup"><span data-stu-id="6797d-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="6797d-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6797d-109">Parameters</span></span>

|<span data-ttu-id="6797d-110">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="6797d-110">**Parameter**</span></span>|<span data-ttu-id="6797d-111">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="6797d-111">**Required**</span></span>|<span data-ttu-id="6797d-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6797d-112">**Type**</span></span>|<span data-ttu-id="6797d-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6797d-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6797d-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="6797d-114">VersionType</span></span>  <br/> |<span data-ttu-id="6797d-115">Opcional</span><span class="sxs-lookup"><span data-stu-id="6797d-115">Optional</span></span>  <br/> |<span data-ttu-id="6797d-116">System. String</span><span class="sxs-lookup"><span data-stu-id="6797d-116">System.String</span></span>  <br/> |<span data-ttu-id="6797d-117">Tipo de versão.</span><span class="sxs-lookup"><span data-stu-id="6797d-117">Type of version.</span></span> <span data-ttu-id="6797d-118">O valor do parâmetro pode ser RunningScripts, RunningBits, BackupBits ou todos.</span><span class="sxs-lookup"><span data-stu-id="6797d-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="6797d-119">O valor padrão é RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="6797d-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="6797d-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6797d-120">Examples</span></span>
<span data-ttu-id="6797d-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6797d-121"></span></span>

### <a name="example-1"></a><span data-ttu-id="6797d-122">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="6797d-122">Example 1</span></span>

<span data-ttu-id="6797d-123">O exemplo a seguir mostra a versão do conector de nuvem do script atualmente em execução no seu console aberto do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6797d-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="6797d-124">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="6797d-124">Example 2</span></span>

<span data-ttu-id="6797d-125">O exemplo a seguir mostra a versão do conector de nuvem de binários implantado para as máquinas virtuais em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="6797d-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="6797d-126">Você pode ver a versão nos nomes das máquinas virtuais em execução no Hyper-v Manager:</span><span class="sxs-lookup"><span data-stu-id="6797d-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="6797d-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="6797d-127">Input Types</span></span>
<span data-ttu-id="6797d-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6797d-128"></span></span>

<span data-ttu-id="6797d-129">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6797d-129">None.</span></span> <span data-ttu-id="6797d-130">O cmdlet Get-CcVersion não aceita entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="6797d-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6797d-131">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="6797d-131">Return Types</span></span>
<span data-ttu-id="6797d-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6797d-132"></span></span>

<span data-ttu-id="6797d-133">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6797d-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6797d-134">Consulte também</span><span class="sxs-lookup"><span data-stu-id="6797d-134">See also</span></span>
<span data-ttu-id="6797d-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6797d-135"></span></span>

<span data-ttu-id="6797d-136">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6797d-136">None.</span></span>
  

