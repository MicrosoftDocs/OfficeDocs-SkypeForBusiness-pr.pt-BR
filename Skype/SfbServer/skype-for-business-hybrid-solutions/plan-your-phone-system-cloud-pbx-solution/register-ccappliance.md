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
description: O cmdlet Register-CcAppliance registra as informações do dispositivo para um site PSTN em uma configuração de locatário online. Um dispositivo deve ser registrado antes de ele poder ser implantado e gerenciado pelo serviço de gerenciamento do Skype for Business Cloud Connector Edition.
ms.openlocfilehash: a94f9d7189f4872fcee2439afd2b210933f8bb06
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824297"
---
# <a name="register-ccappliance"></a><span data-ttu-id="557fc-104">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="557fc-104">Register-CcAppliance</span></span>
 
<span data-ttu-id="557fc-105">O cmdlet Register-CcAppliance registra as informações do dispositivo para um site PSTN em uma configuração de locatário online.</span><span class="sxs-lookup"><span data-stu-id="557fc-105">The Register-CcAppliance cmdlet registers appliance information to a PSTN site in an online tenant configuration.</span></span> <span data-ttu-id="557fc-106">Um dispositivo deve ser registrado antes de ele poder ser implantado e gerenciado pelo serviço de gerenciamento do Skype for Business Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="557fc-106">An appliance must be registered before it can be deployed and managed by the Skype for Business Cloud Connector Edition management service.</span></span>
  
```powershell
Register-CcAppliance [[-SiteName] <string>] [[-ApplianceName] <string>] [-Local]
```

## <a name="examples"></a><span data-ttu-id="557fc-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="557fc-107">Examples</span></span>
<span data-ttu-id="557fc-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="557fc-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="557fc-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="557fc-109">Example 1</span></span>

<span data-ttu-id="557fc-110">O seguinte exemplo registra as informações atuais do dispositivo para uma configuração de locatário online:</span><span class="sxs-lookup"><span data-stu-id="557fc-110">The following example registers the current appliance information to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="557fc-111">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="557fc-111">Example 2</span></span>

<span data-ttu-id="557fc-112">O exemplo a seguir verifica a configuração para registro local sem conexão com uma configuração de locatário online:</span><span class="sxs-lookup"><span data-stu-id="557fc-112">The next example checks configuration for registration locally without connecting to an online tenant configuration:</span></span>
  
```powershell
Register-CcAppliance -Local
```

### <a name="example-3"></a><span data-ttu-id="557fc-113">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="557fc-113">Example 3</span></span>

<span data-ttu-id="557fc-114">O exemplo a seguir registra o dispositivo atual com o nome e "Appliance1" para o site PSTN "Site1":</span><span class="sxs-lookup"><span data-stu-id="557fc-114">The next example registers the current appliance with the name "Appliance1" to the PSTN site "Site1":</span></span>
  
```powershell
Register-CcAppliance -SiteName Site1 -ApplianceName Appliance1
```

## <a name="detailed-description"></a><span data-ttu-id="557fc-115">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="557fc-115">Detailed Description</span></span>
<span data-ttu-id="557fc-116"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="557fc-116"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="557fc-117">Você precisa fornecer o nome e a senha da conta do administrador do locatário.</span><span class="sxs-lookup"><span data-stu-id="557fc-117">You must provide the tenant admin account name and password.</span></span> <span data-ttu-id="557fc-118">Use a conta que você criou para o gerenciamento online do Cloud Connector.</span><span class="sxs-lookup"><span data-stu-id="557fc-118">Use the account you have created for Cloud Connector online management.</span></span> 
  
<span data-ttu-id="557fc-119">Na versão 1.4.2 e versões anteriores, siga as instruções para fornecer a senha do certificado externo, a senha de administrador do modo de segurança, a senha de administrador do domínio e a senha do administrador da VM.</span><span class="sxs-lookup"><span data-stu-id="557fc-119">In release 1.4.2 and earlier, follow the instructions to provide the external certificate password, safe mode admin password, domain admin password, and VM admin password.</span></span> 
  
<span data-ttu-id="557fc-120">Na versão 2.0 e posteriores, siga as instruções para fornecer a senha do certificado externo, a senha do CceService e a senha do CABackupFile.</span><span class="sxs-lookup"><span data-stu-id="557fc-120">In release 2.0 and later, follow the instructions to provide the external certificate password, CceService password and CABackupFile password.</span></span>
  
<span data-ttu-id="557fc-121">No final do registro, reinicie o serviço de gerenciamento do conector de nuvem e faça logon na conta serviços como CceService.</span><span class="sxs-lookup"><span data-stu-id="557fc-121">At the end of registration, restart the Cloud Connector management service and log on to the services as CceService account.</span></span>
  
<span data-ttu-id="557fc-p104">O SiteName combinado com o FQDN externo do Servidor de Borda no arquivo do CloudConnector.ini é considerado uma identidade do site PSTN. Se o SiteName ou o FQDN externo do Servidor de Borda não tiver sido usado para registrar um site, um novo site será criado para este dispositivo em uma configuração de locatário online. Se uma identidade do site PSTN for localizada, um site PSTN usará esta identidade e o dispositivo será registrado para este site PSTN. </span><span class="sxs-lookup"><span data-stu-id="557fc-p104">SiteName combined with the Edge Server external FQDN in the CloudConnector.ini file is considered a PSTN site identity. If neither the SiteName nor the Edge Server external FQDN has been used to register a site, a new site will be created for this appliance in an online tenant configuration. If a PSTN site identity is found, a PSTN site will use this identity and the appliance will be registered to this PSTN site.</span></span> 
  
<span data-ttu-id="557fc-125">Na seguinte situação, o cmdlet falhará e indicará que o Site1 já foi registrado: </span><span class="sxs-lookup"><span data-stu-id="557fc-125">In the following situation, the cmdlet will fail and indicate that Site1 is already registered:</span></span> 
  
- <span data-ttu-id="557fc-126">O SiteName é o Site1 e o FQDN externo do Servidor da Borda é edgserver1.contoso.com. </span><span class="sxs-lookup"><span data-stu-id="557fc-126">SiteName is Site1 and the Edge Server external FQDN is edgserver1.contoso.com.</span></span> 
    
- <span data-ttu-id="557fc-127">Um site PSTN cujo SiteName é o Site1 e o FQDN externo do Servidor da Borda é o edgserver1.contoso.com.</span><span class="sxs-lookup"><span data-stu-id="557fc-127">A PSTN site whose SiteName is Site1 and Edge Server external FQDN is edgserver.contoso.com.</span></span>
    
- <span data-ttu-id="557fc-128">Um site PSTN cujo SiteName é o NewSite e o FQDN externo do Servidor da Borda é o edgserver1.contoso.com foi registrado. </span><span class="sxs-lookup"><span data-stu-id="557fc-128">A PSTN site whose SiteName is NewSite and Edge Server external FQDN is edgserver1.contoso.com has been registered.</span></span> 
    
<span data-ttu-id="557fc-p105">O ApplianceName combinado com o FQDN do Servidor de Mediação no arquivo do CloudConnector.ini é considerado uma identidade do dispositivo. Se o ApplianceName ou o FQDN do Servidor de Mediação não tiver sido usado para registrar um dispositivo, um novo dispositivo será criado na configuração de locatário online. Se o dispositivo já estiver registrado, o cmdlet falhará.</span><span class="sxs-lookup"><span data-stu-id="557fc-p105">ApplianceName combined with the Mediation Server FQDN in CloudConnector.ini file is considered an Appliance Identity. If neither the ApplianceName nor the Mediation Server FQDN has been used to register an appliance, a new appliance will be created in the online tenant configuration. If the appliance is already registered, the cmdlet will fail.</span></span>
  
<span data-ttu-id="557fc-132">Na seguinte situação, o cmdlet falhará e indicará que o dispositivo já foi registrado: </span><span class="sxs-lookup"><span data-stu-id="557fc-132">In the following situation, the cmdlet will fail and indicate that the appliance is already registered:</span></span> 
  
- <span data-ttu-id="557fc-133">O ApplianceName é o Appliance1 e o FQDN do servidor de mediação é ms1.vdomain.com.</span><span class="sxs-lookup"><span data-stu-id="557fc-133">ApplianceName is Appliance1 and Mediation server FQDN is ms1.vdomain.com.</span></span>
    
- <span data-ttu-id="557fc-134">No site PSTN atual, se um dispositivo cujo nome Appliance1 e o FQDN do Servidor de Mediação for ms.vdomain.com ou um dispositivo cujo nome NewAppliance e o FQDN do Servidor de Mediação for ms1.vdomain.com tiver sido registrado.</span><span class="sxs-lookup"><span data-stu-id="557fc-134">In the current PSTN site, if an appliance whose name Appliance1 and Mediation Server FQDN is ms.vdomain.com or an appliance whose name NewAppliance and Mediation server FQDN is ms1.vdomain.com has been registered.</span></span>
    
## <a name="parameters"></a><span data-ttu-id="557fc-135">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="557fc-135">Parameters</span></span>
<span data-ttu-id="557fc-136"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="557fc-136"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="557fc-137">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="557fc-137">**Parameter**</span></span>|<span data-ttu-id="557fc-138">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="557fc-138">**Required**</span></span>|<span data-ttu-id="557fc-139">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="557fc-139">**Type**</span></span>|<span data-ttu-id="557fc-140">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="557fc-140">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="557fc-141">SiteName</span><span class="sxs-lookup"><span data-stu-id="557fc-141">SiteName</span></span>  <br/> |<span data-ttu-id="557fc-142">Opcional </span><span class="sxs-lookup"><span data-stu-id="557fc-142">Optional</span></span>  <br/> |<span data-ttu-id="557fc-143">System.String</span><span class="sxs-lookup"><span data-stu-id="557fc-143">System.String</span></span>  <br/> |<span data-ttu-id="557fc-p106">O nome do site PSTN com o qual o dispositivo foi registrado. O valor padrão é o SiteName no arquivo CloudConnector.ini.</span><span class="sxs-lookup"><span data-stu-id="557fc-p106">PSTN site name to which the appliance is registered. Default value is SiteName value in the CloudConnector.ini file.</span></span>  <br/> |
|<span data-ttu-id="557fc-146">ApplianceName</span><span class="sxs-lookup"><span data-stu-id="557fc-146">ApplianceName</span></span>  <br/> |<span data-ttu-id="557fc-147">Opcional </span><span class="sxs-lookup"><span data-stu-id="557fc-147">Optional</span></span>  <br/> |<span data-ttu-id="557fc-148">System.String</span><span class="sxs-lookup"><span data-stu-id="557fc-148">System.String</span></span>  <br/> |<span data-ttu-id="557fc-p107">Nome do dispositivo padrão. O valor padrão é o nome do computador do servidor host.</span><span class="sxs-lookup"><span data-stu-id="557fc-p107">Name of the current appliance. Default value is the computer name of the host server.</span></span>  <br/> |
|<span data-ttu-id="557fc-151">Local</span><span class="sxs-lookup"><span data-stu-id="557fc-151">Local</span></span>  <br/> |<span data-ttu-id="557fc-152">Opcional</span><span class="sxs-lookup"><span data-stu-id="557fc-152">Optional</span></span>  <br/> |<span data-ttu-id="557fc-153">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="557fc-153">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="557fc-154">Verifique as configurações para registro local sem conexão com a configuração de locatário online.</span><span class="sxs-lookup"><span data-stu-id="557fc-154">Check configurations for registration locally without connecting to online tenant configuration.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="557fc-155">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="557fc-155">Input Types</span></span>
<span data-ttu-id="557fc-156"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="557fc-156"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="557fc-p108">Nenhum. O cmdlet Register-CcAppliance não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="557fc-p108">None. The Register-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="557fc-159">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="557fc-159">Return Types</span></span>
<span data-ttu-id="557fc-160"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="557fc-160"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="557fc-161">Nenhum</span><span class="sxs-lookup"><span data-stu-id="557fc-161">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="557fc-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="557fc-162">See also</span></span>
<span data-ttu-id="557fc-163"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="557fc-163"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="557fc-164">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="557fc-164">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="557fc-165">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="557fc-165">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="557fc-166">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="557fc-166">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="557fc-167">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="557fc-167">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

