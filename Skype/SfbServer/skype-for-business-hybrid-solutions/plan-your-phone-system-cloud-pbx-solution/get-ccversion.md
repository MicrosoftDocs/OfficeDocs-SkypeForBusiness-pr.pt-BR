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
description: Retorna a versão do dispositivo do Cloud Connector. Get-CCVersion só pode ser usado no computador host do Cloud Connector.
ms.openlocfilehash: 706b480c2f8e277b7f41fe28e88cc062fea6603a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799841"
---
# <a name="get-ccversion"></a><span data-ttu-id="6bec8-104">Get-CcVersion</span><span class="sxs-lookup"><span data-stu-id="6bec8-104">Get-CcVersion</span></span>
 
<span data-ttu-id="6bec8-105">Retorna a versão do dispositivo do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6bec8-105">Returns the version of the Cloud Connector appliance.</span></span> <span data-ttu-id="6bec8-106">Get-CCVersion só pode ser usado no computador host do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="6bec8-106">Get-CCVersion can only be used on the host machine of Cloud Connector.</span></span>
  
```powershell
Get-CcVersion [[-VersionType] <String>] [<CommonParameters>]
```

## <a name="detailed-description"></a><span data-ttu-id="6bec8-107">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="6bec8-107">Detailed Description</span></span>

<span data-ttu-id="6bec8-108">Retorna a versão do dispositivo do Cloud Connector com base em scripts do PowerShell instalados, arquivos no diretório do dispositivo e as máquinas virtuais implantadas no servidor host.</span><span class="sxs-lookup"><span data-stu-id="6bec8-108">Returns the version of the Cloud Connector appliance based on PowerShell scripts installed, files in the Appliance directory, and the virtual machines deployed on host server.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="6bec8-109">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6bec8-109">Parameters</span></span>

|<span data-ttu-id="6bec8-110">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="6bec8-110">**Parameter**</span></span>|<span data-ttu-id="6bec8-111">**Required**</span><span class="sxs-lookup"><span data-stu-id="6bec8-111">**Required**</span></span>|<span data-ttu-id="6bec8-112">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6bec8-112">**Type**</span></span>|<span data-ttu-id="6bec8-113">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6bec8-113">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6bec8-114">VersionType</span><span class="sxs-lookup"><span data-stu-id="6bec8-114">VersionType</span></span>  <br/> |<span data-ttu-id="6bec8-115">Opcional</span><span class="sxs-lookup"><span data-stu-id="6bec8-115">Optional</span></span>  <br/> |<span data-ttu-id="6bec8-116">System. String</span><span class="sxs-lookup"><span data-stu-id="6bec8-116">System.String</span></span>  <br/> |<span data-ttu-id="6bec8-117">Tipo de versão.</span><span class="sxs-lookup"><span data-stu-id="6bec8-117">Type of version.</span></span> <span data-ttu-id="6bec8-118">O valor do parâmetro pode ser RunningScripts, RunningBits, BackupBits ou ALL.</span><span class="sxs-lookup"><span data-stu-id="6bec8-118">Value of parameter can be RunningScripts, RunningBits, BackupBits or All.</span></span> <span data-ttu-id="6bec8-119">O valor padrão é RunningScripts.</span><span class="sxs-lookup"><span data-stu-id="6bec8-119">Default value is RunningScripts.</span></span>  <br/> |
   
## <a name="examples"></a><span data-ttu-id="6bec8-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6bec8-120">Examples</span></span>
<span data-ttu-id="6bec8-121"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6bec8-121"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="6bec8-122">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="6bec8-122">Example 1</span></span>

<span data-ttu-id="6bec8-123">O exemplo a seguir mostra a versão do Cloud Connector do script em execução no momento no console aberto do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="6bec8-123">The following example shows the Cloud Connector version of the currently running script in your open PowerShell console:</span></span>
  
```powershell
Get-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="6bec8-124">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="6bec8-124">Example 2</span></span>

<span data-ttu-id="6bec8-125">O exemplo a seguir mostra a versão do Cloud Connector dos binários atualmente em execução implantados para as máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="6bec8-125">The following example shows the Cloud Connector version of the currently running binaries deployed to the virtual machines.</span></span> <span data-ttu-id="6bec8-126">Você pode ver a versão nos nomes da máquina virtual em execução no Gerenciador do Hyper-v:</span><span class="sxs-lookup"><span data-stu-id="6bec8-126">You can see the version in the running virtual machine names in Hyper-v Manager:</span></span>
  
```powershell
Get-CCVersion -VersionType RunningBits
```

## <a name="input-types"></a><span data-ttu-id="6bec8-127">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="6bec8-127">Input Types</span></span>
<span data-ttu-id="6bec8-128"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6bec8-128"><a name="Examples"> </a></span></span>

<span data-ttu-id="6bec8-129">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6bec8-129">None.</span></span> <span data-ttu-id="6bec8-130">O cmdlet Get-CcVersion não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="6bec8-130">The Get-CcVersion cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6bec8-131">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="6bec8-131">Return Types</span></span>
<span data-ttu-id="6bec8-132"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6bec8-132"><a name="Examples"> </a></span></span>

<span data-ttu-id="6bec8-133">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6bec8-133">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6bec8-134">Confira também</span><span class="sxs-lookup"><span data-stu-id="6bec8-134">See also</span></span>
<span data-ttu-id="6bec8-135"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6bec8-135"><a name="Examples"> </a></span></span>

<span data-ttu-id="6bec8-136">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6bec8-136">None.</span></span>
  

