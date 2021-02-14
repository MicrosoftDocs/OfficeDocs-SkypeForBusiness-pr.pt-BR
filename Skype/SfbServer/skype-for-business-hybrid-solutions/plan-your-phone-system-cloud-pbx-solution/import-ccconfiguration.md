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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 461361a0-9aa9-469d-ace0-dc70b95cd4a3
description: Importa a configuração do Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do Cloud Connector.
ms.openlocfilehash: 626ba52d4d67f99dd67d3d1f91d26d6e6d03f95e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799851"
---
# <a name="import-ccconfiguration"></a><span data-ttu-id="47aea-103">Import-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="47aea-103">Import-CcConfiguration</span></span>
 
<span data-ttu-id="47aea-104">Importa a configuração do Skype for Business Cloud Connector Edition de um arquivo local para o servidor host do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="47aea-104">Imports the Skype for Business Cloud Connector Edition configuration from a local file to the Cloud Connector host server.</span></span>
  
```powershell
Import-CcConfiguration [-Force] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="47aea-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="47aea-105">Examples</span></span>
<span data-ttu-id="47aea-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47aea-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="47aea-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="47aea-107">Example 1</span></span>

<span data-ttu-id="47aea-108">O exemplo a seguir copia o CloudConnector.ini do diretório de dispositivos da instância do Cloud Connector para o diretório %SystemDrive%\ProgramData\CloudConnector:</span><span class="sxs-lookup"><span data-stu-id="47aea-108">The following example copies the CloudConnector.ini from the appliance directory of the Cloud Connector instance to %SystemDrive%\ProgramData\CloudConnector directory:</span></span>
  
```powershell
Import-CcConfiguration
```

## <a name="detailed-description"></a><span data-ttu-id="47aea-109">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="47aea-109">Detailed Description</span></span>
<span data-ttu-id="47aea-110"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47aea-110"><a name="Examples"> </a></span></span>

<span data-ttu-id="47aea-111">Este cmdlet copia o CloudConnector.ini do diretório de dispositivos do dispositivo do Cloud Connector para o diretório %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="47aea-111">This cmdlet copies the CloudConnector.ini from the appliance directory of the Cloud Connector appliance to the %SystemDrive%\ProgramData\CloudConnector directory.</span></span> <span data-ttu-id="47aea-112">O diretório de dispositivos é especificado usando o Set-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="47aea-112">The appliance directory is specified by using the Set-CcApplianceDirectory cmdlet.</span></span> <span data-ttu-id="47aea-113">O cmdlet substituirá qualquer arquivo existente em %SystemDrive%\ProgramData\CloudConnector.</span><span class="sxs-lookup"><span data-stu-id="47aea-113">The cmdlet will overwrite any existing file in %SystemDrive%\ProgramData\CloudConnector.</span></span> <span data-ttu-id="47aea-114">Este comando se aplica à versão 2.0.1 e posterior do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="47aea-114">This command applies to Cloud Connector Edition version 2.0.1 and later.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="47aea-115">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="47aea-115">Parameters</span></span>
<span data-ttu-id="47aea-116"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47aea-116"><a name="Examples"> </a></span></span>

|<span data-ttu-id="47aea-117">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="47aea-117">**Parameter**</span></span>|<span data-ttu-id="47aea-118">**Required**</span><span class="sxs-lookup"><span data-stu-id="47aea-118">**Required**</span></span>|<span data-ttu-id="47aea-119">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="47aea-119">**Type**</span></span>|<span data-ttu-id="47aea-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="47aea-120">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="47aea-121">Force</span><span class="sxs-lookup"><span data-stu-id="47aea-121">Force</span></span>  <br/> |<span data-ttu-id="47aea-122">Opcional</span><span class="sxs-lookup"><span data-stu-id="47aea-122">Optional</span></span>  <br/> |<span data-ttu-id="47aea-123">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="47aea-123">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="47aea-124">Substituir o arquivo existente em %SystemDrive%\ProgramData\CloudConnector sem notificação.</span><span class="sxs-lookup"><span data-stu-id="47aea-124">Overwrite existing file in %SystemDrive%\ProgramData\CloudConnector without notification.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="47aea-125">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="47aea-125">Input Types</span></span>
<span data-ttu-id="47aea-126"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47aea-126"><a name="Examples"> </a></span></span>

<span data-ttu-id="47aea-127">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="47aea-127">None.</span></span> <span data-ttu-id="47aea-128">O Import-CcConfiguration cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="47aea-128">The Import-CcConfiguration cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="47aea-129">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="47aea-129">Return Types</span></span>
<span data-ttu-id="47aea-130"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47aea-130"><a name="Examples"> </a></span></span>

<span data-ttu-id="47aea-131">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="47aea-131">None.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="47aea-132">Confira também</span><span class="sxs-lookup"><span data-stu-id="47aea-132">See also</span></span>
<span data-ttu-id="47aea-133"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="47aea-133"><a name="Examples"> </a></span></span>

<span data-ttu-id="47aea-134">Export-CcConfiguration</span><span class="sxs-lookup"><span data-stu-id="47aea-134">Export-CcConfiguration</span></span>
  

