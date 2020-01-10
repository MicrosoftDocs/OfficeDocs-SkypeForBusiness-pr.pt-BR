---
title: Uninstall-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 2/23/2018
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: 'O cmdlet Uninstall-CcAppliance cancela a instalação do dispositivo  em execução do Skype for Business Cloud Connector Edition no servidor host. '
ms.openlocfilehash: f37c3092103832c9efd3b24d2efbedf00e8f54ac
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003141"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="0386b-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0386b-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="0386b-104">O cmdlet Uninstall-CcAppliance cancela a instalação do dispositivo  em execução do Skype for Business Cloud Connector Edition no servidor host. </span><span class="sxs-lookup"><span data-stu-id="0386b-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="0386b-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="0386b-105">Examples</span></span>
<span data-ttu-id="0386b-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="0386b-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="0386b-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="0386b-107">Example 1</span></span>

<span data-ttu-id="0386b-108">O exemplo a seguir esvazia e desinstala o dispositivo do conector de nuvem do servidor host:</span><span class="sxs-lookup"><span data-stu-id="0386b-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="0386b-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="0386b-109">Example 2</span></span>

<span data-ttu-id="0386b-110">O próximo exemplo drena e forçosamente desinstala o dispositivo de conector de nuvem em execução no servidor host, mesmo que o processo de descarga falhasse:</span><span class="sxs-lookup"><span data-stu-id="0386b-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="0386b-111">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="0386b-111">Example 3</span></span>

<span data-ttu-id="0386b-112">O próximo exemplo desinstala uma versão de backup do conector de nuvem sem a confirmação do usuário:</span><span class="sxs-lookup"><span data-stu-id="0386b-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="0386b-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="0386b-113">Detailed Description</span></span>
<span data-ttu-id="0386b-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0386b-114"></span></span>

<span data-ttu-id="0386b-115">Se você estiver desinstalando a versão atual do conector de nuvem, os serviços de descarga serão executados primeiro no servidor de mediação e no servidor de borda para que as chamadas simultâneas sejam concluídas antes da desinstalação das máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="0386b-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="0386b-116">Se você estiver desinstalando uma versão do backup, os esvaziamento não será executado.</span><span class="sxs-lookup"><span data-stu-id="0386b-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="0386b-117">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="0386b-117">Parameters</span></span>
<span data-ttu-id="0386b-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="0386b-118"></span></span>

|<span data-ttu-id="0386b-119">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="0386b-119">**Parameter**</span></span>|<span data-ttu-id="0386b-120">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="0386b-120">**Required**</span></span>|<span data-ttu-id="0386b-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0386b-121">**Type**</span></span>|<span data-ttu-id="0386b-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0386b-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="0386b-123">Versão</span><span class="sxs-lookup"><span data-stu-id="0386b-123">Version</span></span> <br/> | <span data-ttu-id="0386b-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="0386b-124">Optional</span></span> <br/> |<span data-ttu-id="0386b-125">System.String</span><span class="sxs-lookup"><span data-stu-id="0386b-125">System.String</span></span>  <br/> | <span data-ttu-id="0386b-126">A versão do conector de nuvem que será desinstalada do servidor host.</span><span class="sxs-lookup"><span data-stu-id="0386b-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="0386b-127">Se não for especificado, desinstale a versão atual em execução.</span><span class="sxs-lookup"><span data-stu-id="0386b-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="0386b-128">Forçar</span><span class="sxs-lookup"><span data-stu-id="0386b-128">Force</span></span>  <br/> |<span data-ttu-id="0386b-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="0386b-129">Optional</span></span>  <br/> |<span data-ttu-id="0386b-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0386b-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0386b-p103">Se você estiver desinstalando a versão atual em execução, tente esvaziar os servidores no Servidor de Mediação e do Servidor de Borda antes de desinstalar as máquinas virtuais. Se você especificar o comutador "Forçar", mesmo se os serviços de esvaziamento falharem, as máquinas virtuais serão desinstaladas. Este parâmetro é usado somente para desinstalar a versão atual em execução.</span><span class="sxs-lookup"><span data-stu-id="0386b-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="0386b-134">Confirmar</span><span class="sxs-lookup"><span data-stu-id="0386b-134">Confirm</span></span>  <br/> |<span data-ttu-id="0386b-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="0386b-135">Optional</span></span>  <br/> |<span data-ttu-id="0386b-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="0386b-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="0386b-137">Solicite confirmação do usuário para desinstalar as máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="0386b-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="0386b-138">O valor padrão é TRUE.</span><span class="sxs-lookup"><span data-stu-id="0386b-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="0386b-139">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="0386b-139">Input Types</span></span>
<span data-ttu-id="0386b-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0386b-140"></span></span>

<span data-ttu-id="0386b-p105">Nenhum. O cmdlet Uninstall-CcAppliance não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="0386b-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="0386b-143">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="0386b-143">Return Types</span></span>
<span data-ttu-id="0386b-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0386b-144"></span></span>

<span data-ttu-id="0386b-145">Nenhum</span><span class="sxs-lookup"><span data-stu-id="0386b-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="0386b-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0386b-146">See also</span></span>
<span data-ttu-id="0386b-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="0386b-147"></span></span>

[<span data-ttu-id="0386b-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0386b-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="0386b-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0386b-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="0386b-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0386b-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="0386b-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="0386b-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

