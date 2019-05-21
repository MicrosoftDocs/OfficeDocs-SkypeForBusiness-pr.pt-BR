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
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: O cmdlet Unregister-CcAppliance cancela o registro do dispositivo do Skype for Business Cloud Connector Edition atual a partir de um site PSTN na configuração online do locatário.
ms.openlocfilehash: fafe374371cd01b2ec7c67ade89dd2a905e16d18
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286870"
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="2f068-103">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="2f068-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="2f068-104">O cmdlet Unregister-CcAppliance cancela o registro do dispositivo do Skype for Business Cloud Connector Edition atual a partir de um site PSTN na configuração online do locatário.</span><span class="sxs-lookup"><span data-stu-id="2f068-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="2f068-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2f068-105">Examples</span></span>
<span data-ttu-id="2f068-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2f068-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="2f068-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="2f068-107">Example 1</span></span>

<span data-ttu-id="2f068-108">O seguinte exemplo cancela o registro do dispositivo atual da configuração de locatário online:</span><span class="sxs-lookup"><span data-stu-id="2f068-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="2f068-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="2f068-109">Example 2</span></span>

<span data-ttu-id="2f068-110">O exemplo seguinte verifica a configuração para cancelar o registro local sem conexão com uma configuração de locatário online:</span><span class="sxs-lookup"><span data-stu-id="2f068-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="2f068-111">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="2f068-111">Example 3</span></span>

<span data-ttu-id="2f068-112">O exemplo a seguir cancela o registro o dispositivo atual com o nome "Appliance1" para o site PSTN "Site1":</span><span class="sxs-lookup"><span data-stu-id="2f068-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="2f068-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="2f068-113">Detailed Description</span></span>
<span data-ttu-id="2f068-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2f068-114"></span></span>

<span data-ttu-id="2f068-p101">Similar ao cmdlet Register-CcAppliance, o SiteName combinado com o FQDN externo do Servidor de Borda no arquivo CloudConnector.ini é considerado uma identidade do site PSTN. Da mesma forma, o ApplianceName combinado com o FQDN do Servidor de Mediação no arquivo do CloudConnector.ini é considerado uma identidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="2f068-p101">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="2f068-117">Depois que o dispositivo estiver cancelado, reinicie o serviço de gerenciamento do Cloud Connector e faça logon como a conta NetworkService.</span><span class="sxs-lookup"><span data-stu-id="2f068-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2f068-118">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2f068-118">Parameters</span></span>
<span data-ttu-id="2f068-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2f068-119"></span></span>

|<span data-ttu-id="2f068-120">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="2f068-120">**Parameter**</span></span>|<span data-ttu-id="2f068-121">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="2f068-121">**Required**</span></span>|<span data-ttu-id="2f068-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2f068-122">**Type**</span></span>|<span data-ttu-id="2f068-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2f068-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2f068-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="2f068-124">SiteName</span></span> <br/> |<span data-ttu-id="2f068-125">Opcional </span><span class="sxs-lookup"><span data-stu-id="2f068-125">Optional</span></span>  <br/> |<span data-ttu-id="2f068-126">System.String</span><span class="sxs-lookup"><span data-stu-id="2f068-126">System.String</span></span>  <br/> |<span data-ttu-id="2f068-p102">O nome do site PSTN onde o dispositivo foi registrado. O valor padrão é o SiteName no arquivo CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="2f068-p102">PSTN site name where the appliance is registered. Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="2f068-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="2f068-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="2f068-130">Opcional </span><span class="sxs-lookup"><span data-stu-id="2f068-130">Optional</span></span>  <br/> |<span data-ttu-id="2f068-131">System.String</span><span class="sxs-lookup"><span data-stu-id="2f068-131">System.String</span></span>  <br/> |<span data-ttu-id="2f068-p103">Nome do dispositivo padrão. O valor padrão é o nome do computador do servidor host.</span><span class="sxs-lookup"><span data-stu-id="2f068-p103">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="2f068-134">Local</span><span class="sxs-lookup"><span data-stu-id="2f068-134">Local</span></span>  <br/> |<span data-ttu-id="2f068-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="2f068-135">Optional</span></span>  <br/> |<span data-ttu-id="2f068-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="2f068-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="2f068-137">Verifique a configuração do registro localmente sem conectar-se a uma configuração de locatário online.</span><span class="sxs-lookup"><span data-stu-id="2f068-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2f068-138">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="2f068-138">Input Types</span></span>
<span data-ttu-id="2f068-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2f068-139"></span></span>

<span data-ttu-id="2f068-p104">Nenhum. O cmdlet Unregister-CcAppliance não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="2f068-p104">None. The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2f068-142">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="2f068-142">Return Types</span></span>
<span data-ttu-id="2f068-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2f068-143"></span></span>

<span data-ttu-id="2f068-144">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2f068-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f068-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f068-145">See also</span></span>
<span data-ttu-id="2f068-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2f068-146"></span></span>

[<span data-ttu-id="2f068-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="2f068-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="2f068-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="2f068-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="2f068-149">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="2f068-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="2f068-150">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="2f068-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

