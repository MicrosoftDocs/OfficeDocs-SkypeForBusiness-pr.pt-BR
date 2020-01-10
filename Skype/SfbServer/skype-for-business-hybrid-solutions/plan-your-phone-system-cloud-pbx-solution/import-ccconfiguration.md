---
title: Import-CcConfiguration
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 10/11/2017
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa a configuração do Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do conector da nuvem.
ms.openlocfilehash: c72a72351ecb6936832bc5d6a2493c5fa8dfe324
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003331"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="500d5-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="500d5-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="500d5-104">Importa a configuração do Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do conector da nuvem.</span><span class="sxs-lookup"><span data-stu-id="500d5-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="500d5-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="500d5-105">Examples</span></span>
<span data-ttu-id="500d5-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="500d5-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="500d5-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="500d5-107">Example 1</span></span>

<span data-ttu-id="500d5-108">O exemplo a seguir copia o CloudConnector. ini do diretório do aplicativo da instância do conector de nuvem para o diretório%SystemDrive%\ProgramData\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="500d5-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="500d5-109">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="500d5-109">Detailed Description</span></span>
<span data-ttu-id="500d5-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="500d5-110"></span></span>

<span data-ttu-id="500d5-111">Esse cmdlet copia o CloudConnector. ini do diretório do aparelho do aparelho do conector de nuvem para o diretório%SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="500d5-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="500d5-112">Esse diretório é especificado usando o cmdlet Set-CcApplianceDirectory.</span><span class="sxs-lookup"><span data-stu-id="500d5-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="500d5-113">O cmdlet substituirá qualquer arquivo existente no%SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="500d5-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="500d5-114">Este comando se aplica à versão 2.0.1 e posterior do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="500d5-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="500d5-115">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="500d5-115">Parameters</span></span>
<span data-ttu-id="500d5-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="500d5-116"></span></span>

|<span data-ttu-id="500d5-117">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="500d5-117">**Parameter**</span></span>|<span data-ttu-id="500d5-118">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="500d5-118">**Required**</span></span>|<span data-ttu-id="500d5-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="500d5-119">**Type**</span></span>|<span data-ttu-id="500d5-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="500d5-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="500d5-121">Forçar</span><span class="sxs-lookup"><span data-stu-id="500d5-121">Force</span></span>  <br/> |<span data-ttu-id="500d5-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="500d5-122">Optional</span></span>  <br/> |<span data-ttu-id="500d5-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="500d5-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="500d5-124">Substituir o arquivo existente no%SystemDrive%\ProgramData\CloudConnector sem notificação.</span><span class="sxs-lookup"><span data-stu-id="500d5-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="500d5-125">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="500d5-125">Input Types</span></span>
<span data-ttu-id="500d5-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="500d5-126"></span></span>

<span data-ttu-id="500d5-127">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="500d5-127">None.</span></span> <span data-ttu-id="500d5-128">O cmdlet Import-CcConfiguration não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="500d5-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="500d5-129">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="500d5-129">Return Types</span></span>
<span data-ttu-id="500d5-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="500d5-130"></span></span>

<span data-ttu-id="500d5-131">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="500d5-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="500d5-132">Consulte também</span><span class="sxs-lookup"><span data-stu-id="500d5-132">See also</span></span>
<span data-ttu-id="500d5-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="500d5-133"></span></span>

<span data-ttu-id="500d5-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="500d5-134">Export-CcConfiguration</span></span>
  

