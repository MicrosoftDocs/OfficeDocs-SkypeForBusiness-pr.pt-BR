---
title: Register-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 7/18/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 01eed3c5-af68-4db7-90b3-d28ebe7ffef1
description: O Register-CcAppliance cmdlet registra as informações do dispositivo em um site PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado antes que possa ser implantado e gerenciado pelo serviço de gerenciamento do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824297"
---
# <a name="register-ccappliance"></a><span data-ttu-id="57b9c-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="57b9c-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="57b9c-105">O Register-CcAppliance cmdlet registra as informações do dispositivo em um site PSTN em uma configuração de locatário online.</span><span class="sxs-lookup"><span data-stu-id="57b9c-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="57b9c-106">Um dispositivo deve ser registrado antes que possa ser implantado e gerenciado pelo serviço de gerenciamento do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="57b9c-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="57b9c-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="57b9c-107">Examples</span></span>
<span data-ttu-id="57b9c-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="57b9c-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="57b9c-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="57b9c-109">Example 1</span></span>

<span data-ttu-id="57b9c-110">O exemplo a seguir registra as informações atuais do dispositivo para uma configuração de locatário online:</span><span class="sxs-lookup"><span data-stu-id="57b9c-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="57b9c-111">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="57b9c-111">Example 2</span></span>

<span data-ttu-id="57b9c-112">O próximo exemplo verifica a configuração do registro localmente sem se conectar a uma configuração de locatário online:</span><span class="sxs-lookup"><span data-stu-id="57b9c-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="57b9c-113">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="57b9c-113">Example 3</span></span>

<span data-ttu-id="57b9c-114">O próximo exemplo registra o dispositivo atual com o nome "Appliance1" no site PSTN "Site1":</span><span class="sxs-lookup"><span data-stu-id="57b9c-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="57b9c-115">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="57b9c-115">Detailed Description</span></span>
<span data-ttu-id="57b9c-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="57b9c-116"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="57b9c-117">Você deve fornecer o nome e a senha da conta de administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="57b9c-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="57b9c-118">Use a conta que você criou para o gerenciamento online do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="57b9c-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="57b9c-119">Na versão 1.4.2 e anteriores, siga as instruções para fornecer a senha do certificado externo, a senha do administrador do modo de segurança, a senha do administrador do domínio e a senha do administrador da VM.</span><span class="sxs-lookup"><span data-stu-id="57b9c-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="57b9c-120">Na versão 2.0 e posteriores, siga as instruções para fornecer a senha do certificado externo, a senha do CceService e a senha do CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="57b9c-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="57b9c-121">No final do registro, reinicie o serviço de gerenciamento do Cloud Connector e faça logon nos serviços como conta do CceService.</span><span class="sxs-lookup"><span data-stu-id="57b9c-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="57b9c-122">SiteName combinado com o FQDN externo do Servidor de Borda no arquivo CloudConnector.ini é considerado uma identidade de site PSTN.</span><span class="sxs-lookup"><span data-stu-id="57b9c-122">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity.</span></span> <span data-ttu-id="57b9c-123">Se o SiteName ou o FQDN externo do Servidor de Borda não tiver sido usado para registrar um site, um novo site será criado para esse dispositivo em uma configuração de locatário online.</span><span class="sxs-lookup"><span data-stu-id="57b9c-123">If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration.</span></span> <span data-ttu-id="57b9c-124">Se uma identidade de site PSTN for encontrada, um site PSTN usará essa identidade e o dispositivo será registrado nesse site PSTN.</span><span class="sxs-lookup"><span data-stu-id="57b9c-124">If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="57b9c-125">Na seguinte situação, o cmdlet falhará e indicará que o Site1 já está registrado:</span><span class="sxs-lookup"><span data-stu-id="57b9c-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="57b9c-126">SiteName é o Site1 e o FQDN externo do Servidor de Borda edgserver1.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="57b9c-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="57b9c-127">Um site PSTN cujo SiteName é Site1 e o FQDN externo do Servidor de Borda é edgserver.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="57b9c-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="57b9c-128">Um site PSTN cujo SiteName é NewSite e o FQDN externo do Servidor de Borda edgserver1.contoso.com foi registrado.</span><span class="sxs-lookup"><span data-stu-id="57b9c-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="57b9c-129">ApplianceName combinado com o FQDN do Servidor de Mediação CloudConnector.ini arquivo é considerado uma Identidade do Dispositivo.</span><span class="sxs-lookup"><span data-stu-id="57b9c-129">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity.</span></span> <span data-ttu-id="57b9c-130">Se o ApplianceName ou o FQDN do Servidor de Mediação não tiver sido usado para registrar um dispositivo, um novo dispositivo será criado na configuração de locatário online.</span><span class="sxs-lookup"><span data-stu-id="57b9c-130">If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration.</span></span> <span data-ttu-id="57b9c-131">Se o dispositivo já estiver registrado, o cmdlet falhará.</span><span class="sxs-lookup"><span data-stu-id="57b9c-131">If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="57b9c-132">Na seguinte situação, o cmdlet falhará e indicará que o dispositivo já está registrado:</span><span class="sxs-lookup"><span data-stu-id="57b9c-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="57b9c-133">ApplianceName é Appliance1 e o FQDN do servidor de Mediação ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="57b9c-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="57b9c-134">No site PSTN atual, se um dispositivo cujo nome Appliance1 e FQDN do Servidor de Mediação for ms.vdomain.com ou um dispositivo cujo nome For NewAppliance e FQDN do servidor de Mediação ms1.vdomain.com tiver sido registrado.</span><span class="sxs-lookup"><span data-stu-id="57b9c-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="57b9c-135">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="57b9c-135">Parameters</span></span>
<span data-ttu-id="57b9c-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="57b9c-136"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="57b9c-137">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="57b9c-137">**Parameter**</span></span>|<span data-ttu-id="57b9c-138">**Required**</span><span class="sxs-lookup"><span data-stu-id="57b9c-138">**Required**</span></span>|<span data-ttu-id="57b9c-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="57b9c-139">**Type**</span></span>|<span data-ttu-id="57b9c-140">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="57b9c-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="57b9c-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="57b9c-141">SiteName</span></span>  <br/> |<span data-ttu-id="57b9c-142">Opcional</span><span class="sxs-lookup"><span data-stu-id="57b9c-142">Optional</span></span>  <br/> |<span data-ttu-id="57b9c-143">System.String</span><span class="sxs-lookup"><span data-stu-id="57b9c-143">System.String</span></span>  <br/> |<span data-ttu-id="57b9c-144">Nome do site PSTN no qual o dispositivo está registrado.</span><span class="sxs-lookup"><span data-stu-id="57b9c-144">PSTN site name to which the appliance is registered.</span></span> <span data-ttu-id="57b9c-145">O valor padrão é SiteName no arquivo CloudConnector.ini arquivo.</span><span class="sxs-lookup"><span data-stu-id="57b9c-145">Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="57b9c-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="57b9c-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="57b9c-147">Opcional</span><span class="sxs-lookup"><span data-stu-id="57b9c-147">Optional</span></span>  <br/> |<span data-ttu-id="57b9c-148">System.String</span><span class="sxs-lookup"><span data-stu-id="57b9c-148">System.String</span></span>  <br/> |<span data-ttu-id="57b9c-149">Nome do dispositivo atual.</span><span class="sxs-lookup"><span data-stu-id="57b9c-149">Name of the current appliance.</span></span> <span data-ttu-id="57b9c-150">O valor padrão é o nome do computador do servidor host.</span><span class="sxs-lookup"><span data-stu-id="57b9c-150">Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="57b9c-151">Local</span><span class="sxs-lookup"><span data-stu-id="57b9c-151">Local</span></span>  <br/> |<span data-ttu-id="57b9c-152">Opcional</span><span class="sxs-lookup"><span data-stu-id="57b9c-152">Optional</span></span>  <br/> |<span data-ttu-id="57b9c-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="57b9c-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="57b9c-154">Verifique as configurações de registro localmente sem se conectar à configuração de locatário online.</span><span class="sxs-lookup"><span data-stu-id="57b9c-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="57b9c-155">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="57b9c-155">Input Types</span></span>
<span data-ttu-id="57b9c-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="57b9c-156"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="57b9c-157">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="57b9c-157">None.</span></span> <span data-ttu-id="57b9c-158">O Register-CcAppliance cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="57b9c-158">The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="57b9c-159">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="57b9c-159">Return Types</span></span>
<span data-ttu-id="57b9c-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="57b9c-160"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="57b9c-161">Nenhum</span><span class="sxs-lookup"><span data-stu-id="57b9c-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="57b9c-162">Confira também</span><span class="sxs-lookup"><span data-stu-id="57b9c-162">See also</span></span>
<span data-ttu-id="57b9c-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="57b9c-163"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="57b9c-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="57b9c-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="57b9c-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="57b9c-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="57b9c-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="57b9c-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="57b9c-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="57b9c-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

