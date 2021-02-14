---
title: Unregister-CcAppliance
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
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: O Unregister-CcAppliance o cmdlet não tem o registro do dispositivo atual do Skype for Business Cloud Connector Edition de um site PSTN na configuração de locatário online.
ms.openlocfilehash: 84a25321b6affda6b8783c40baa18a91b5b95ef5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824125"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="d2f3f-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d2f3f-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="d2f3f-104">O Unregister-CcAppliance o cmdlet não tem o registro do dispositivo atual do Skype for Business Cloud Connector Edition de um site PSTN na configuração de locatário online.</span><span class="sxs-lookup"><span data-stu-id="d2f3f-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```powershell
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="d2f3f-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d2f3f-105">Examples</span></span>
<span data-ttu-id="d2f3f-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d2f3f-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="d2f3f-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="d2f3f-107">Example 1</span></span>

<span data-ttu-id="d2f3f-108">O exemplo a seguir não registrou um dispositivo atual da configuração de locatário online:</span><span class="sxs-lookup"><span data-stu-id="d2f3f-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="d2f3f-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="d2f3f-109">Example 2</span></span>

<span data-ttu-id="d2f3f-110">O próximo exemplo verifica a configuração para o registro local sem se conectar à configuração de locatário online:</span><span class="sxs-lookup"><span data-stu-id="d2f3f-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```powershell
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="d2f3f-111">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="d2f3f-111">Example 3</span></span>

<span data-ttu-id="d2f3f-112">O próximo exemplo desastana o registro do dispositivo atual com o nome "Appliance1" para o site PSTN "Site1":</span><span class="sxs-lookup"><span data-stu-id="d2f3f-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```powershell
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="d2f3f-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="d2f3f-113">Detailed Description</span></span>
<span data-ttu-id="d2f3f-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d2f3f-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="d2f3f-115">Semelhante ao cmdlet Register-CcAppliance, o SiteName combinado com o FQDN externo do Servidor de Borda no arquivo CloudConnector.ini é considerado uma identidade de site PSTN.</span><span class="sxs-lookup"><span data-stu-id="d2f3f-115">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="d2f3f-116">Da mesma forma, ApplianceName combinado com o FQDN do Servidor de Mediação no arquivo CloudConnector.ini é considerado uma identidade de dispositivo.</span><span class="sxs-lookup"><span data-stu-id="d2f3f-116">Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="d2f3f-117">Após o registro do dispositivo, reinicie o serviço de gerenciamento do Cloud Connector e faça logon como a conta NetworkService.</span><span class="sxs-lookup"><span data-stu-id="d2f3f-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d2f3f-118">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d2f3f-118">Parameters</span></span>
<span data-ttu-id="d2f3f-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d2f3f-119"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="d2f3f-120">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="d2f3f-120">**Parameter**</span></span>|<span data-ttu-id="d2f3f-121">**Required**</span><span class="sxs-lookup"><span data-stu-id="d2f3f-121">**Required**</span></span>|<span data-ttu-id="d2f3f-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d2f3f-122">**Type**</span></span>|<span data-ttu-id="d2f3f-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d2f3f-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="d2f3f-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="d2f3f-124">SiteName</span></span> <br/> |<span data-ttu-id="d2f3f-125">Opcional</span><span class="sxs-lookup"><span data-stu-id="d2f3f-125">Optional</span></span>  <br/> |<span data-ttu-id="d2f3f-126">System.String</span><span class="sxs-lookup"><span data-stu-id="d2f3f-126">System.String</span></span>  <br/> |<span data-ttu-id="d2f3f-127">Nome do site PSTN em que o dispositivo está registrado.</span><span class="sxs-lookup"><span data-stu-id="d2f3f-127">PSTN site name where the appliance is registered.</span></span> <span data-ttu-id="d2f3f-128">O valor padrão é SiteName no CloudConnector.ini arquivo.</span><span class="sxs-lookup"><span data-stu-id="d2f3f-128">Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="d2f3f-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="d2f3f-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="d2f3f-130">Opcional</span><span class="sxs-lookup"><span data-stu-id="d2f3f-130">Optional</span></span>  <br/> |<span data-ttu-id="d2f3f-131">System.String</span><span class="sxs-lookup"><span data-stu-id="d2f3f-131">System.String</span></span>  <br/> |<span data-ttu-id="d2f3f-132">Nome do dispositivo atual.</span><span class="sxs-lookup"><span data-stu-id="d2f3f-132">Name of the current appliance.</span></span> <span data-ttu-id="d2f3f-133">O valor padrão é o nome do computador do servidor host.</span><span class="sxs-lookup"><span data-stu-id="d2f3f-133">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="d2f3f-134">Local</span><span class="sxs-lookup"><span data-stu-id="d2f3f-134">Local</span></span>  <br/> |<span data-ttu-id="d2f3f-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="d2f3f-135">Optional</span></span>  <br/> |<span data-ttu-id="d2f3f-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d2f3f-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d2f3f-137">Verifique a configuração do registro localmente sem se conectar a uma configuração de locatário online.</span><span class="sxs-lookup"><span data-stu-id="d2f3f-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d2f3f-138">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="d2f3f-138">Input Types</span></span>
<span data-ttu-id="d2f3f-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d2f3f-139"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="d2f3f-140">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="d2f3f-140">None.</span></span> <span data-ttu-id="d2f3f-141">O Unregister-CcAppliance cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="d2f3f-141">The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d2f3f-142">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="d2f3f-142">Return Types</span></span>
<span data-ttu-id="d2f3f-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d2f3f-143"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="d2f3f-144">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d2f3f-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d2f3f-145">Confira também</span><span class="sxs-lookup"><span data-stu-id="d2f3f-145">See also</span></span>
<span data-ttu-id="d2f3f-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d2f3f-146"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="d2f3f-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d2f3f-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="d2f3f-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d2f3f-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="d2f3f-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d2f3f-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="d2f3f-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d2f3f-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

