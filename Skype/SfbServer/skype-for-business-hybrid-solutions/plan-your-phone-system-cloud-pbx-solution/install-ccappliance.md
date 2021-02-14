---
title: Install-CcAppliance
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
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: O cmdlet Install-CcAppliance instala o dispositivo do Skype for Business Cloud Connector Edition , incluindo as máquinas virtuais do AD, do Armazenamento central, do Servidor de Mediação e do Servidor de Borda, no servidor host.
ms.openlocfilehash: fe1fab785e2681614f27035714b6ddead22b8707
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41799871"
---
# <a name="install-ccappliance"></a><span data-ttu-id="16730-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="16730-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="16730-104">O cmdlet Install-CcAppliance instala o dispositivo do Skype for Business Cloud Connector Edition , incluindo as máquinas virtuais do AD, do Armazenamento central, do Servidor de Mediação e do Servidor de Borda, no servidor host.</span><span class="sxs-lookup"><span data-stu-id="16730-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```powershell
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="16730-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="16730-105">Examples</span></span>
<span data-ttu-id="16730-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="16730-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="16730-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="16730-107">Example 1</span></span>

<span data-ttu-id="16730-108">O exemplo a seguir instala um novo dispositivo do Cloud Connector no servidor host:</span><span class="sxs-lookup"><span data-stu-id="16730-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```powershell
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="16730-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="16730-109">Example 2</span></span>

<span data-ttu-id="16730-110">O exemplo a seguir atualiza o Cloud Connector para a versão mais recente:</span><span class="sxs-lookup"><span data-stu-id="16730-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```powershell
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="16730-111">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="16730-111">Example 3</span></span>

<span data-ttu-id="16730-112">O exemplo a seguir remove todas as credenciais do Cloud Connector armazenadas em cache no servidor host, solicita que o usuário especifique todas as informações de credencial novamente e, em seguida, instala o Cloud Connector:</span><span class="sxs-lookup"><span data-stu-id="16730-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```powershell
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="16730-113">Exemplo 4</span><span class="sxs-lookup"><span data-stu-id="16730-113">Example 4</span></span>

<span data-ttu-id="16730-114">O exemplo a seguir exibe todas as etapas de implantação no console do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="16730-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```powershell
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="16730-115">O parâmetro -ShowStepsOnly é apenas para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="16730-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="16730-116">Exemplo 5</span><span class="sxs-lookup"><span data-stu-id="16730-116">Example 5</span></span>

<span data-ttu-id="16730-117">O exemplo a seguir gera arquivos de configuração para cada etapa de implantação no servidor host.</span><span class="sxs-lookup"><span data-stu-id="16730-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="16730-118">Os arquivos de configuração são salvos \< na pasta ApplianceRoot \> \Instances \\<Version \> -default\ExportedConfig no servidor host:</span><span class="sxs-lookup"><span data-stu-id="16730-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```powershell
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="16730-119">Para determinar a raiz do dispositivo, execute o Get-CcApplianceDirectory cmdlet.</span><span class="sxs-lookup"><span data-stu-id="16730-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="16730-120">Exemplo 6</span><span class="sxs-lookup"><span data-stu-id="16730-120">Example 6</span></span>

<span data-ttu-id="16730-121">No exemplo a seguir, o Cloud Connector executa as etapas de implantação 1, 2 e 3 para criar comutadores virtuais, criar uma máquina virtual do AD e instalar o serviço de domínio no servidor do AD.</span><span class="sxs-lookup"><span data-stu-id="16730-121">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server.</span></span> <span data-ttu-id="16730-122">Ela ignorará a etapa se a etapa já tiver sido executada:</span><span class="sxs-lookup"><span data-stu-id="16730-122">It skips the step if the step has already been executed:</span></span>
  
```powershell
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="16730-123">O parâmetro SkipExistingObjects deve ser usado em conjunto com o parâmetro Steps.</span><span class="sxs-lookup"><span data-stu-id="16730-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="16730-124">O parâmetro Steps é apenas para fins de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="16730-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="16730-125">Não use esse parâmetro para implantar um dispositivo ou atualizar um dispositivo que está em serviço.</span><span class="sxs-lookup"><span data-stu-id="16730-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="16730-126">Para determinar as etapas da implantação, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="16730-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="16730-127">Install-CcAppliance -ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="16730-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="16730-128">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="16730-128">Detailed Description</span></span>
<span data-ttu-id="16730-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="16730-129"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="16730-130">O Install-CcAppliance cmdlet é usado para implantar o Cloud Connector em um novo dispositivo ou para atualizar um dispositivo existente para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="16730-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="16730-131">Se você tiver um novo dispositivo, certifique-se de ler Preparar seu ambiente para o Cloud Connector primeiro, execute o cmdlet Register-CcAppliance para registrar o dispositivo e, em seguida, execute o cmdlet Install-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="16730-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="16730-132">Para obter mais informações, [consulte Implantar um único site no Cloud Connector](deploy-a-single-site-in-cloud-connector.md) e implantar vários sites no Cloud [Connector.](deploy-multiple-sites-in-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="16730-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="16730-133">Se você tiver uma implantação existente do Cloud Connector e quiser atualizar, siga as instruções em Atualizar para uma nova versão [do Cloud Connector.](upgrade-to-a-new-version-of-cloud-connector.md)</span><span class="sxs-lookup"><span data-stu-id="16730-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="16730-134">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="16730-134">Parameters</span></span>
<span data-ttu-id="16730-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="16730-135"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="16730-136">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="16730-136">**Parameter**</span></span>|<span data-ttu-id="16730-137">**Required**</span><span class="sxs-lookup"><span data-stu-id="16730-137">**Required**</span></span>|<span data-ttu-id="16730-138">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="16730-138">**Type**</span></span>|<span data-ttu-id="16730-139">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="16730-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="16730-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="16730-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="16730-141">Opcional</span><span class="sxs-lookup"><span data-stu-id="16730-141">Optional</span></span>  <br/> |<span data-ttu-id="16730-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="16730-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="16730-143">Gere arquivos de configuração para cada etapa de implantação.</span><span class="sxs-lookup"><span data-stu-id="16730-143">Generate configuration files for each deployment step.</span></span> <span data-ttu-id="16730-144">Este parâmetro é apenas para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="16730-144">This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="16730-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="16730-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="16730-146">Opcional</span><span class="sxs-lookup"><span data-stu-id="16730-146">Optional</span></span>  <br/> |<span data-ttu-id="16730-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="16730-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="16730-148">Exibir apenas nomes de etapas de implantação.</span><span class="sxs-lookup"><span data-stu-id="16730-148">Display deployment step names only.</span></span> <span data-ttu-id="16730-149">Este parâmetro é apenas para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="16730-149">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="16730-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="16730-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="16730-151">Opcional</span><span class="sxs-lookup"><span data-stu-id="16730-151">Optional</span></span>  <br/> |<span data-ttu-id="16730-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="16730-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="16730-153">Esse parâmetro deve ser usado em conjunto com o parâmetro Steps.</span><span class="sxs-lookup"><span data-stu-id="16730-153">This parameter must be used in conjunction with the Steps parameter.</span></span> <span data-ttu-id="16730-154">Este parâmetro é apenas para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="16730-154">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="16730-155">Etapas</span><span class="sxs-lookup"><span data-stu-id="16730-155">Steps</span></span>  <br/> |<span data-ttu-id="16730-156">Opcional</span><span class="sxs-lookup"><span data-stu-id="16730-156">Optional</span></span>  <br/> |<span data-ttu-id="16730-157">System.Array</span><span class="sxs-lookup"><span data-stu-id="16730-157">System.Array</span></span>  <br/> |<span data-ttu-id="16730-158">Execute as etapas de implantação.</span><span class="sxs-lookup"><span data-stu-id="16730-158">Run the deployment steps.</span></span> <span data-ttu-id="16730-159">Este parâmetro é apenas para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="16730-159">This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="16730-160">Atualizar</span><span class="sxs-lookup"><span data-stu-id="16730-160">Upgrade</span></span>  <br/> |<span data-ttu-id="16730-161">Opcional</span><span class="sxs-lookup"><span data-stu-id="16730-161">Optional</span></span>  <br/> |<span data-ttu-id="16730-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="16730-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="16730-163">Atualize o Cloud Connector existente para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="16730-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="16730-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="16730-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="16730-165">Opcional</span><span class="sxs-lookup"><span data-stu-id="16730-165">Optional</span></span>  <br/> |<span data-ttu-id="16730-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="16730-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="16730-167">Remova todas as credenciais do Cloud Connector no cache.</span><span class="sxs-lookup"><span data-stu-id="16730-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="16730-168">Solicitar que o usuário especifique novas informações de credencial para a instalação.</span><span class="sxs-lookup"><span data-stu-id="16730-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="16730-169">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="16730-169">Input Types</span></span>
<span data-ttu-id="16730-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="16730-170"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="16730-171">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="16730-171">None.</span></span> <span data-ttu-id="16730-172">O Install-CcAppliance cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="16730-172">The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="16730-173">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="16730-173">Return Types</span></span>
<span data-ttu-id="16730-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="16730-174"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="16730-175">Nenhum</span><span class="sxs-lookup"><span data-stu-id="16730-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="16730-176">Confira também</span><span class="sxs-lookup"><span data-stu-id="16730-176">See also</span></span>
<span data-ttu-id="16730-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="16730-177"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="16730-178">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="16730-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="16730-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="16730-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="16730-180">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="16730-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="16730-181">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="16730-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

