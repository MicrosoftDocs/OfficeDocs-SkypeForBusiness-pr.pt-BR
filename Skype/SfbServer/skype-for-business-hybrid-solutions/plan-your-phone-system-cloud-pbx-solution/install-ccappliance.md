---
title: Install-CcAppliance
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 385453cd-3a96-4837-8bb4-513aa97a256b
description: 'O cmdlet Install-CcAppliance instala o dispositivo do Skype for Business Cloud Connector Edition — incluindo as máquinas virtuais do AD, do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda — no servidor host. '
ms.openlocfilehash: a3717e510ccadaa930d50573f067888780f7dce5
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="install-ccappliance"></a><span data-ttu-id="d46fd-103">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d46fd-103">Install-CcAppliance</span></span>
 
<span data-ttu-id="d46fd-104">O cmdlet Install-CcAppliance instala o dispositivo do Skype for Business Cloud Connector Edition — incluindo as máquinas virtuais do AD, do Repositório de Gerenciamento Central, do Servidor de Mediação e do Servidor de Borda — no servidor host. </span><span class="sxs-lookup"><span data-stu-id="d46fd-104">The Install-CcAppliance cmdlet installs the Skype for Business Cloud Connector Edition appliance—including the AD, Central Management Store, Mediation Server, and Edge Server virtual machines—on the host server.</span></span> 
  
```
Install-CcAppliance [-Steps <array>] [-SkipExistingObjects] [-Upgrade] [-UpdateAllCredentials] [<CommonParameters>]
Install-CcAppliance [-Steps <array>] [-PrepareOnly]  [<CommonParameters>]
Install-CcAppliance [-ShowStepsOnly]  [<CommonParameters>]

```

## <a name="examples"></a><span data-ttu-id="d46fd-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d46fd-105">Examples</span></span>
<span data-ttu-id="d46fd-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="d46fd-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="d46fd-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="d46fd-107">Example 1</span></span>

<span data-ttu-id="d46fd-108">O exemplo a seguir instala um novo dispositivo de conector de nuvem no servidor host:</span><span class="sxs-lookup"><span data-stu-id="d46fd-108">The following example installs a new Cloud Connector appliance on the host server:</span></span>
  
```
Install-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="d46fd-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="d46fd-109">Example 2</span></span>

<span data-ttu-id="d46fd-110">O exemplo a seguir atualiza o conector de nuvem para a versão mais recente:</span><span class="sxs-lookup"><span data-stu-id="d46fd-110">The following example upgrades Cloud Connector to the latest version:</span></span>
  
```
Install-CcAppliance -Upgrade
```

### <a name="example-3"></a><span data-ttu-id="d46fd-111">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="d46fd-111">Example 3</span></span>

<span data-ttu-id="d46fd-112">O exemplo a seguir remove todas as credenciais de nuvem conector armazenados em cache no servidor host, solicita ao usuário para especificar todas as informações de credencial novamente e em seguida, instala o conector de nuvem:</span><span class="sxs-lookup"><span data-stu-id="d46fd-112">The following example removes all Cloud Connector credentials cached on the host server, prompts the user to specify all credential information again, and then installs Cloud Connector:</span></span>
  
```
Install-CcAppliance -UpdateAllCredentials
```

### <a name="example-4"></a><span data-ttu-id="d46fd-113">Exemplo 4</span><span class="sxs-lookup"><span data-stu-id="d46fd-113">Example 4</span></span>

<span data-ttu-id="d46fd-114">O seguinte exemplo exibe todas as etapas de implantação no console do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d46fd-114">The following example displays all deployment steps in the PowerShell console:</span></span>
  
```
Install-CcAppliance -ShowStepsOnly
```

<span data-ttu-id="d46fd-115">O parâmetro -ShowStepsOnly é apenas para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="d46fd-115">The -ShowStepsOnly parameter is for troubleshooting only.</span></span>
  
### <a name="example-5"></a><span data-ttu-id="d46fd-116">Exemplo 5</span><span class="sxs-lookup"><span data-stu-id="d46fd-116">Example 5</span></span>

<span data-ttu-id="d46fd-117">O exemplo seguinte gera arquivos de configuração para cada etapa de implantação no servidor host.</span><span class="sxs-lookup"><span data-stu-id="d46fd-117">The following example generates configuration files for each deployment step on the host server.</span></span> <span data-ttu-id="d46fd-118">Arquivos de configuração são salvas o \<ApplianceRoot\>\Instances\\< versão\>-default\ExportedConfig pasta no servidor host:</span><span class="sxs-lookup"><span data-stu-id="d46fd-118">Configuration files are saved to the \<ApplianceRoot\>\Instances\\<Version\>-default\ExportedConfig folder on the host server:</span></span>
  
```
Install-CcAppliance -PrepareOnly
```

<span data-ttu-id="d46fd-119">Para determinar a raiz do dispositivo, execute o cmdlet Get-CcApplianceDirectory. </span><span class="sxs-lookup"><span data-stu-id="d46fd-119">To determine the appliance root, run the Get-CcApplianceDirectory cmdlet.</span></span> 
  
### <a name="example-6"></a><span data-ttu-id="d46fd-120">Exemplo 6</span><span class="sxs-lookup"><span data-stu-id="d46fd-120">Example 6</span></span>

<span data-ttu-id="d46fd-p102">No exemplo seguinte, o Cloud Connector executa as etapas de implantação 1, 2 e 3 para criar comutadores virtuais, criar uma máquina virtual do AD e instalar o serviço do domínio no servidor AD. Ele pula a etapa se ela já tiver sido executada:</span><span class="sxs-lookup"><span data-stu-id="d46fd-p102">In the following example, Cloud Connector runs deployment steps 1, 2, and 3 to create virtual switches, create an AD virtual machine, and install the domain service on the AD server. It skips the step if the step has already been executed:</span></span>
  
```
Install-CcAppliance -Steps @(1,2,3) -SkipExistingObjects
```

<span data-ttu-id="d46fd-123">O parâmetro SkipExistingObjects deve ser usado em conjunto com o parâmetro Steps.</span><span class="sxs-lookup"><span data-stu-id="d46fd-123">The SkipExistingObjects parameter must be used in conjunction with the Steps parameter.</span></span>
  
> [!NOTE]
> <span data-ttu-id="d46fd-124">O parâmetro Steps é apenas para solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="d46fd-124">The Steps parameter is for troubleshooting purposes only.</span></span> <span data-ttu-id="d46fd-125">Não use este parâmetro para implantar um dispositivo ou para atualizar um dispositivo que está em serviço.</span><span class="sxs-lookup"><span data-stu-id="d46fd-125">Do not use this parameter to deploy an appliance or to upgrade an appliance that is in service.</span></span> 
  
<span data-ttu-id="d46fd-126">Para determinar as etapas da implantação, execute o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="d46fd-126">To determine the steps of the deployment, run the following command:</span></span>
  
<span data-ttu-id="d46fd-127">Install-CcAppliance - ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="d46fd-127">Install-CcAppliance -ShowStepsOnly</span></span>
  
## <a name="detailed-description"></a><span data-ttu-id="d46fd-128">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="d46fd-128">Detailed Description</span></span>
<span data-ttu-id="d46fd-129"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d46fd-129"></span></span>

<span data-ttu-id="d46fd-130">O cmdlet Install-CcAppliance é usado para implantar o conector de nuvem para um novo aparelho ou atualizar um aparelho existente para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="d46fd-130">The Install-CcAppliance cmdlet is used to deploy Cloud Connector to a new appliance or to upgrade an existing appliance to the latest version.</span></span>
  
<span data-ttu-id="d46fd-131">Se você tiver um novo aplicativo, certifique-se de ler o tópico Preparar seu ambiente para o Cloud Connector primeiro, executar o cmdlet Register-CcAppliance para registrar o dispositivo e depois executar o cmdlet Install-CcAppliance.</span><span class="sxs-lookup"><span data-stu-id="d46fd-131">If you have a new appliance, be sure to read Prepare your environment for Cloud Connector first, run the Register-CcAppliance cmdlet to register the appliance, and then run the Install-CcAppliance cmdlet.</span></span> <span data-ttu-id="d46fd-132">Para obter mais informações, consulte [implantar um único site no conector de nuvem](deploy-a-single-site-in-cloud-connector.md) e [implantar vários sites em nuvem de conector](deploy-multiple-sites-in-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="d46fd-132">For more information, see [Deploy a single site in Cloud Connector](deploy-a-single-site-in-cloud-connector.md) and [Deploy multiple sites in Cloud Connector](deploy-multiple-sites-in-cloud-connector.md).</span></span> 
  
<span data-ttu-id="d46fd-133">Se você tiver uma implantação existente do conector de nuvem e você deseja atualizar, siga as instruções [de atualização para uma nova versão do conector de nuvem](upgrade-to-a-new-version-of-cloud-connector.md).</span><span class="sxs-lookup"><span data-stu-id="d46fd-133">If you have an existing deployment of Cloud Connector and you want to upgrade, please follow the instructions in [Upgrade to a new version of Cloud Connector](upgrade-to-a-new-version-of-cloud-connector.md).</span></span>
  
## <a name="parameters"></a><span data-ttu-id="d46fd-134">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="d46fd-134">Parameters</span></span>
<span data-ttu-id="d46fd-135"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="d46fd-135"></span></span>

|<span data-ttu-id="d46fd-136">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="d46fd-136">**Parameter**</span></span>|<span data-ttu-id="d46fd-137">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="d46fd-137">**Required**</span></span>|<span data-ttu-id="d46fd-138">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d46fd-138">**Type**</span></span>|<span data-ttu-id="d46fd-139">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d46fd-139">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="d46fd-140">PrepareOnly</span><span class="sxs-lookup"><span data-stu-id="d46fd-140">PrepareOnly</span></span>  <br/> |<span data-ttu-id="d46fd-141">Opcional</span><span class="sxs-lookup"><span data-stu-id="d46fd-141">Optional</span></span>  <br/> |<span data-ttu-id="d46fd-142">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d46fd-142">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="d46fd-p105"> Gerar arquivos de configuração para cada etapa da implantação. Este parâmetro tem a finalidade exclusiva de solução de problemas. </span><span class="sxs-lookup"><span data-stu-id="d46fd-p105">Generate configuration files for each deployment step. This parameter is for troubleshooting only.</span></span> <br/> |
|<span data-ttu-id="d46fd-145">ShowStepsOnly</span><span class="sxs-lookup"><span data-stu-id="d46fd-145">ShowStepsOnly</span></span>  <br/> |<span data-ttu-id="d46fd-146">Opcional</span><span class="sxs-lookup"><span data-stu-id="d46fd-146">Optional</span></span>  <br/> |<span data-ttu-id="d46fd-147">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d46fd-147">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d46fd-p106">Exibir apenas os nomes das etapas de implantação. Este parâmetro tem a finalidade exclusiva de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="d46fd-p106">Display deployment step names only. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="d46fd-150">SkipExistingObjects</span><span class="sxs-lookup"><span data-stu-id="d46fd-150">SkipExistingObjects</span></span>  <br/> |<span data-ttu-id="d46fd-151">Opcional</span><span class="sxs-lookup"><span data-stu-id="d46fd-151">Optional</span></span>  <br/> |<span data-ttu-id="d46fd-152">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d46fd-152">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d46fd-p107">Este parâmetro deve ser usado em conjunto com o parâmetro Steps. Este parâmetro tem a finalidade exclusiva de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="d46fd-p107">This parameter must be used in conjunction with the Steps parameter. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="d46fd-155">Etapas</span><span class="sxs-lookup"><span data-stu-id="d46fd-155">Steps</span></span>  <br/> |<span data-ttu-id="d46fd-156">Opcional</span><span class="sxs-lookup"><span data-stu-id="d46fd-156">Optional</span></span>  <br/> |<span data-ttu-id="d46fd-157">System. Array</span><span class="sxs-lookup"><span data-stu-id="d46fd-157">System.Array</span></span>  <br/> |<span data-ttu-id="d46fd-p108">Executar as etapas de implantação. Este parâmetro tem a finalidade exclusiva de solução de problemas.</span><span class="sxs-lookup"><span data-stu-id="d46fd-p108">Run the deployment steps. This parameter is for troubleshooting only.</span></span>  <br/> |
|<span data-ttu-id="d46fd-160">Atualizar</span><span class="sxs-lookup"><span data-stu-id="d46fd-160">Upgrade</span></span>  <br/> |<span data-ttu-id="d46fd-161">Opcional</span><span class="sxs-lookup"><span data-stu-id="d46fd-161">Optional</span></span>  <br/> |<span data-ttu-id="d46fd-162">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d46fd-162">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d46fd-163">Atualizar o Cloud Connector existente para a versão mais recente.</span><span class="sxs-lookup"><span data-stu-id="d46fd-163">Upgrade existing Cloud Connector to the latest version.</span></span>  <br/> |
|<span data-ttu-id="d46fd-164">UpdateAllCredentials</span><span class="sxs-lookup"><span data-stu-id="d46fd-164">UpdateAllCredentials</span></span>  <br/> |<span data-ttu-id="d46fd-165">Opcional</span><span class="sxs-lookup"><span data-stu-id="d46fd-165">Optional</span></span>  <br/> |<span data-ttu-id="d46fd-166">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="d46fd-166">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="d46fd-167">Remova todas as credenciais de nuvem conector no cache.</span><span class="sxs-lookup"><span data-stu-id="d46fd-167">Remove all Cloud Connector credentials in the cache.</span></span> <span data-ttu-id="d46fd-168">Pedir para o usuário especificar as informações das novas credenciais para a instalação.</span><span class="sxs-lookup"><span data-stu-id="d46fd-168">Prompt the user to specify new credential information for the installation.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="d46fd-169">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="d46fd-169">Input Types</span></span>
<span data-ttu-id="d46fd-170"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d46fd-170"></span></span>

<span data-ttu-id="d46fd-p110">Nenhum. O cmdlet Install-CcAppliance não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="d46fd-p110">None. The Install-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="d46fd-173">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="d46fd-173">Return Types</span></span>
<span data-ttu-id="d46fd-174"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d46fd-174"></span></span>

<span data-ttu-id="d46fd-175">Nenhum</span><span class="sxs-lookup"><span data-stu-id="d46fd-175">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="d46fd-176">Consulte também</span><span class="sxs-lookup"><span data-stu-id="d46fd-176">See also</span></span>
<span data-ttu-id="d46fd-177"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="d46fd-177"></span></span>

[<span data-ttu-id="d46fd-178">Publicar-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d46fd-178">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="d46fd-179">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d46fd-179">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="d46fd-180">Cancelar o registro de CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d46fd-180">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  
[<span data-ttu-id="d46fd-181">Desinstalar-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="d46fd-181">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  

