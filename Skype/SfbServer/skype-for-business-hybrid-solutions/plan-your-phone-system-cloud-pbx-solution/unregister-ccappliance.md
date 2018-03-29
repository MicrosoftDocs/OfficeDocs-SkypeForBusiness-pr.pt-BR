---
title: Cancelar o registro de CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3d516e65-fb9b-4a0b-8296-969fc9eda334
description: O cmdlet Unregister-CcAppliance cancela o registro do dispositivo do Skype for Business Cloud Connector Edition atual a partir de um site PSTN na configuração online do locatário.
ms.openlocfilehash: 21bd0a7dffc6a395f829af68a61dfd7523d2c09a
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="unregister-ccappliance"></a><span data-ttu-id="36aba-103">Cancelar o registro de CcAppliance</span><span class="sxs-lookup"><span data-stu-id="36aba-103">Unregister-CcAppliance</span></span>
 
<span data-ttu-id="36aba-104">O cmdlet Unregister-CcAppliance cancela o registro do dispositivo do Skype for Business Cloud Connector Edition atual a partir de um site PSTN na configuração online do locatário.</span><span class="sxs-lookup"><span data-stu-id="36aba-104">The Unregister-CcAppliance cmdlet unregisters the current Skype for Business Cloud Connector Edition appliance from a PSTN site in the online tenant configuration.</span></span>
  
```
Unregister-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="36aba-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="36aba-105">Examples</span></span>
<span data-ttu-id="36aba-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="36aba-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="36aba-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="36aba-107">Example 1</span></span>

<span data-ttu-id="36aba-108">O seguinte exemplo cancela o registro do dispositivo atual da configuração de locatário online:</span><span class="sxs-lookup"><span data-stu-id="36aba-108">The following example unregisters a current appliance from the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="36aba-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="36aba-109">Example 2</span></span>

<span data-ttu-id="36aba-110">O exemplo seguinte verifica a configuração para cancelar o registro local sem conexão com uma configuração de locatário online:</span><span class="sxs-lookup"><span data-stu-id="36aba-110">The next example checks the configuration for unregistering locally without connecting to the online tenant configuration:</span></span>
  
```
Unregister-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="36aba-111">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="36aba-111">Example 3</span></span>

<span data-ttu-id="36aba-112">O exemplo a seguir cancela o registro o dispositivo atual com o nome "Appliance1" para o site PSTN "Site1":</span><span class="sxs-lookup"><span data-stu-id="36aba-112">The next example unregisters the current appliance with the name "Appliance1" to PSTN site "Site1":</span></span>
  
```
Unregister-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="36aba-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="36aba-113">Detailed Description</span></span>
<span data-ttu-id="36aba-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="36aba-114"></span></span>

<span data-ttu-id="36aba-p101">Similar ao cmdlet Register-CcAppliance, o SiteName combinado com o FQDN externo do Servidor de Borda no arquivo CloudConnector.ini é considerado uma identidade do site PSTN. Da mesma forma, o ApplianceName combinado com o FQDN do Servidor de Mediação no arquivo do CloudConnector.ini é considerado uma identidade do dispositivo.</span><span class="sxs-lookup"><span data-stu-id="36aba-p101">Similar to the Register-CcAppliance cmdlet, SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. Likewise, ApplianceName combined with the Mediation Server FQDN in the CloudConnector.ini file is considered an appliance identity.</span></span>
  
<span data-ttu-id="36aba-117">Após o aparelho não registrado, reinicie o serviço de gerenciamento do conector de nuvem e faça logon como a conta NetworkService.</span><span class="sxs-lookup"><span data-stu-id="36aba-117">After the appliance is unregistered, restart the Cloud Connector management service and log on as the NetworkService account.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="36aba-118">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="36aba-118">Parameters</span></span>
<span data-ttu-id="36aba-119"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="36aba-119"></span></span>

|<span data-ttu-id="36aba-120">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="36aba-120">**Parameter**</span></span>|<span data-ttu-id="36aba-121">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="36aba-121">**Required**</span></span>|<span data-ttu-id="36aba-122">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="36aba-122">**Type**</span></span>|<span data-ttu-id="36aba-123">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="36aba-123">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="36aba-124">SiteName</span><span class="sxs-lookup"><span data-stu-id="36aba-124">SiteName</span></span> <br/> |<span data-ttu-id="36aba-125">Opcional</span><span class="sxs-lookup"><span data-stu-id="36aba-125">Optional</span></span>  <br/> |<span data-ttu-id="36aba-126">System. String</span><span class="sxs-lookup"><span data-stu-id="36aba-126">System.String</span></span>  <br/> |<span data-ttu-id="36aba-p102">O nome do site PSTN onde o dispositivo foi registrado. O valor padrão é o SiteName no arquivo CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="36aba-p102">PSTN site name where the appliance is registered. Default value is SiteName value in CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="36aba-129">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="36aba-129">ApplianceName</span></span>  <br/> |<span data-ttu-id="36aba-130">Opcional</span><span class="sxs-lookup"><span data-stu-id="36aba-130">Optional</span></span>  <br/> |<span data-ttu-id="36aba-131">System. String</span><span class="sxs-lookup"><span data-stu-id="36aba-131">System.String</span></span>  <br/> |<span data-ttu-id="36aba-p103">Nome do dispositivo padrão. O valor padrão é o nome do computador do servidor host.</span><span class="sxs-lookup"><span data-stu-id="36aba-p103">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="36aba-134">Local</span><span class="sxs-lookup"><span data-stu-id="36aba-134">Local</span></span>  <br/> |<span data-ttu-id="36aba-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="36aba-135">Optional</span></span>  <br/> |<span data-ttu-id="36aba-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="36aba-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="36aba-137">Verifique a configuração do registro localmente sem conectar-se a uma configuração de locatário online.</span><span class="sxs-lookup"><span data-stu-id="36aba-137">Check configuration for registration locally without connecting to an online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="36aba-138">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="36aba-138">Input Types</span></span>
<span data-ttu-id="36aba-139"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="36aba-139"></span></span>

<span data-ttu-id="36aba-p104">Nenhum. O cmdlet Unregister-CcAppliance não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="36aba-p104">None. The Unregister-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="36aba-142">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="36aba-142">Return Types</span></span>
<span data-ttu-id="36aba-143"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="36aba-143"></span></span>

<span data-ttu-id="36aba-144">Nenhum</span><span class="sxs-lookup"><span data-stu-id="36aba-144">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="36aba-145">Consulte também</span><span class="sxs-lookup"><span data-stu-id="36aba-145">See also</span></span>
<span data-ttu-id="36aba-146"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="36aba-146"></span></span>

[<span data-ttu-id="36aba-147">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="36aba-147">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="36aba-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="36aba-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="36aba-149">Desinstalar-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="36aba-149">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="36aba-150">Publicar-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="36aba-150">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  

