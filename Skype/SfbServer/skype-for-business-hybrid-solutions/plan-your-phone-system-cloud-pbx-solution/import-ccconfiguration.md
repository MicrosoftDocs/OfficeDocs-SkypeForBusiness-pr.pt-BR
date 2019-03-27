---
title: Import-CcConfiguration
ms.reviewer: ''
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
ms.openlocfilehash: 497568f45fad6b4363581785bf0be95eabfeaebf
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30896620"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="ad3e1-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="ad3e1-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="ad3e1-104">Importa o Skype para que a configuração do conector de nuvem Business Edition de um arquivo local para o servidor de host do conector de nuvem.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="ad3e1-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ad3e1-105">Examples</span></span>
<span data-ttu-id="ad3e1-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ad3e1-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="ad3e1-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="ad3e1-107">Example 1</span></span>

<span data-ttu-id="ad3e1-108">O exemplo a seguir copia o CloudConnector.ini do diretório de aparelho da instância do conector de nuvem para o diretório de %SystemDrive%\ProgramData\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="ad3e1-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="ad3e1-109">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="ad3e1-109">Detailed Description</span></span>
<span data-ttu-id="ad3e1-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ad3e1-110"></span></span>

<span data-ttu-id="ad3e1-111">Este cmdlet copia o CloudConnector.ini do diretório appliance do aparelho de conector de nuvem para o diretório %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="ad3e1-112">Esse diretório é especificado usando o cmdlet Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="ad3e1-113">O cmdlet substituirá qualquer arquivo existente na pasta % SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="ad3e1-114">Este comando se aplica a nuvem conector Edition versão 2.0.1 e posterior.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="ad3e1-115">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ad3e1-115">Parameters</span></span>
<span data-ttu-id="ad3e1-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ad3e1-116"></span></span>

|<span data-ttu-id="ad3e1-117">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="ad3e1-117">**Parameter**</span></span>|<span data-ttu-id="ad3e1-118">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="ad3e1-118">**Required**</span></span>|<span data-ttu-id="ad3e1-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ad3e1-119">**Type**</span></span>|<span data-ttu-id="ad3e1-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ad3e1-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="ad3e1-121">Forçar</span><span class="sxs-lookup"><span data-stu-id="ad3e1-121">Force</span></span>  <br/> |<span data-ttu-id="ad3e1-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="ad3e1-122">Optional</span></span>  <br/> |<span data-ttu-id="ad3e1-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="ad3e1-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="ad3e1-124">Substitua arquivo existente no %SystemDrive%\ProgramData\CloudConnector sem notificação.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ad3e1-125">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="ad3e1-125">Input Types</span></span>
<span data-ttu-id="ad3e1-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ad3e1-126"></span></span>

<span data-ttu-id="ad3e1-127">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-127">None.</span></span> <span data-ttu-id="ad3e1-128">O cmdlet Import-CcConfiguration não aceita a entrada.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ad3e1-129">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="ad3e1-129">Return Types</span></span>
<span data-ttu-id="ad3e1-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ad3e1-130"></span></span>

<span data-ttu-id="ad3e1-131">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="ad3e1-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ad3e1-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="ad3e1-132">See also</span></span>
<span data-ttu-id="ad3e1-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ad3e1-133"></span></span>

<span data-ttu-id="ad3e1-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="ad3e1-134">Export-CcConfiguration</span></span>
  

