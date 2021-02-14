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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7d370abd-0c01-4490-88a1-55b42e51b663
description: Retorna a versão do dispositivo do Cloud Connector. Get-CCVersion pode ser usado somente no computador host do Cloud Connector.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799841"
---
# <a name="get-ccversion"></a><span data-ttu-id="638c0-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="638c0-104">Get-CcVersion</span></span>
 
<span data-ttu-id="638c0-105">Retorna a versão do dispositivo do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="638c0-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="638c0-106">Get-CCVersion pode ser usado somente no computador host do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="638c0-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="638c0-107">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="638c0-107">Detailed Description</span></span>

<span data-ttu-id="638c0-108">Retorna a versão do dispositivo do Cloud Connector com base nos scripts do PowerShell instalados, arquivos no diretório do Dispositivo e as máquinas virtuais implantadas no servidor host.</span><span class="sxs-lookup"><span data-stu-id="638c0-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="638c0-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="638c0-109">Parameters</span></span>

|<span data-ttu-id="638c0-110">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="638c0-110">**Parameter**</span></span>|<span data-ttu-id="638c0-111">**Required**</span><span class="sxs-lookup"><span data-stu-id="638c0-111">**Required**</span></span>|<span data-ttu-id="638c0-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="638c0-112">**Type**</span></span>|<span data-ttu-id="638c0-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="638c0-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="638c0-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="638c0-114">VersionType</span></span>  <br/> |<span data-ttu-id="638c0-115">Opcional</span><span class="sxs-lookup"><span data-stu-id="638c0-115">Optional</span></span>  <br/> |<span data-ttu-id="638c0-116">System.String</span><span class="sxs-lookup"><span data-stu-id="638c0-116">System.String</span></span>  <br/> |<span data-ttu-id="638c0-117">Tipo de versão.</span><span class="sxs-lookup"><span data-stu-id="638c0-117">Type of version.</span></span> <span data-ttu-id="638c0-118">O valor do parâmetro pode ser RunningScripts, RunningBits, BackupBits ou Todos.</span><span class="sxs-lookup"><span data-stu-id="638c0-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="638c0-119">O valor padrão é RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="638c0-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="638c0-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="638c0-120">Examples</span></span>
<span data-ttu-id="638c0-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="638c0-121"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="638c0-122">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="638c0-122">Example 1</span></span>

<span data-ttu-id="638c0-123">O exemplo a seguir mostra a versão do Cloud Connector do script em execução no seu console aberto do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="638c0-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="638c0-124">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="638c0-124">Example 2</span></span>

<span data-ttu-id="638c0-125">O exemplo a seguir mostra a versão do Cloud Connector dos binários atualmente em execução implantados nas máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="638c0-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="638c0-126">Você pode ver a versão nos nomes de máquina virtual em execução no Gerenciador do Hyper-v:</span><span class="sxs-lookup"><span data-stu-id="638c0-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="638c0-127">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="638c0-127">Input Types</span></span>
<span data-ttu-id="638c0-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="638c0-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="638c0-129">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="638c0-129">None.</span></span> <span data-ttu-id="638c0-130">O Get-CcVersion cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="638c0-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="638c0-131">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="638c0-131">Return Types</span></span>
<span data-ttu-id="638c0-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="638c0-132"><a name="Examples"> </a></span></span>

<span data-ttu-id="638c0-133">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="638c0-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="638c0-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="638c0-134">See also</span></span>
<span data-ttu-id="638c0-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="638c0-135"><a name="Examples"> </a></span></span>

<span data-ttu-id="638c0-136">Nenhum</span><span class="sxs-lookup"><span data-stu-id="638c0-136">None.</span></span>
  

