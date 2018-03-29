---
title: Import-CcConfiguration
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa o Skype para que a configuração do conector de nuvem Business Edition de um arquivo local para o servidor de host do conector de nuvem.
ms.openlocfilehash: 46f4099258ce4090fa23ec980801e55f7300895f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="3d4ce-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="3d4ce-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="3d4ce-104">Importa o Skype para que a configuração do conector de nuvem Business Edition de um arquivo local para o servidor de host do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="3d4ce-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```

Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="3d4ce-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3d4ce-105">Examples</span></span>
<span data-ttu-id="3d4ce-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d4ce-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="3d4ce-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="3d4ce-107">Example 1</span></span>

<span data-ttu-id="3d4ce-108">O exemplo a seguir copia o CloudConnector.ini do diretório de aparelho da instância do conector de nuvem para o diretório de %SystemDrive%\ProgramData\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="3d4ce-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="3d4ce-109">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="3d4ce-109">Detailed Description</span></span>
<span data-ttu-id="3d4ce-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d4ce-110"></span></span>

<span data-ttu-id="3d4ce-111">Este cmdlet copia o CloudConnector.ini do diretório appliance do aparelho de conector de nuvem para o diretório %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="3d4ce-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="3d4ce-112">Esse diretório é especificado usando o cmdlet Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="3d4ce-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="3d4ce-113">O cmdlet substituirá qualquer arquivo existente na pasta % SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="3d4ce-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="3d4ce-114">Este comando se aplica a nuvem conector Edition versão 2.0.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="3d4ce-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="3d4ce-115">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="3d4ce-115">Parameters</span></span>
<span data-ttu-id="3d4ce-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d4ce-116"></span></span>

|<span data-ttu-id="3d4ce-117">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="3d4ce-117">**Parameter**</span></span>|<span data-ttu-id="3d4ce-118">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="3d4ce-118">**Required**</span></span>|<span data-ttu-id="3d4ce-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3d4ce-119">**Type**</span></span>|<span data-ttu-id="3d4ce-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3d4ce-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3d4ce-121">Forçar</span><span class="sxs-lookup"><span data-stu-id="3d4ce-121">Force</span></span>  <br/> |<span data-ttu-id="3d4ce-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="3d4ce-122">Optional</span></span>  <br/> |<span data-ttu-id="3d4ce-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="3d4ce-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="3d4ce-124">Substitua arquivo existente no %SystemDrive%\ProgramData\CloudConnector sem notificação.</span><span class="sxs-lookup"><span data-stu-id="3d4ce-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="3d4ce-125">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="3d4ce-125">Input Types</span></span>
<span data-ttu-id="3d4ce-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d4ce-126"></span></span>

<span data-ttu-id="3d4ce-127">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3d4ce-127">None.</span></span> <span data-ttu-id="3d4ce-128">O cmdlet Import-CcConfiguration não aceita a entrada.</span><span class="sxs-lookup"><span data-stu-id="3d4ce-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="3d4ce-129">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="3d4ce-129">Return Types</span></span>
<span data-ttu-id="3d4ce-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d4ce-130"></span></span>

<span data-ttu-id="3d4ce-131">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="3d4ce-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="3d4ce-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="3d4ce-132">See also</span></span>
<span data-ttu-id="3d4ce-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="3d4ce-133"></span></span>

<span data-ttu-id="3d4ce-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="3d4ce-134">Export-CcConfiguration</span></span>
  

