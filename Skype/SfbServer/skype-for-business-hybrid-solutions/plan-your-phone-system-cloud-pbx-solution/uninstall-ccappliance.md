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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e1b3cdd7-08e9-41a6-843a-3b4baf886cd0
description: O Uninstall-CcAppliance cmdlet desinstala o dispositivo do Skype for Business Cloud Connector Edition em execução no servidor host.
ms.openlocfilehash: c92ad5c31e2e254e4f10511835b6cc9f60c7c43c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824135"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="cd2da-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="cd2da-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="cd2da-104">O Uninstall-CcAppliance cmdlet desinstala o dispositivo do Skype for Business Cloud Connector Edition em execução no servidor host.</span><span class="sxs-lookup"><span data-stu-id="cd2da-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```powershell
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="cd2da-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="cd2da-105">Examples</span></span>
<span data-ttu-id="cd2da-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="cd2da-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="cd2da-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="cd2da-107">Example 1</span></span>

<span data-ttu-id="cd2da-108">O exemplo a seguir esvazia e desinstala o dispositivo do Cloud Connector do servidor host:</span><span class="sxs-lookup"><span data-stu-id="cd2da-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```powershell
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="cd2da-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="cd2da-109">Example 2</span></span>

<span data-ttu-id="cd2da-110">O próximo exemplo esvazia e força a desinstalação do dispositivo do Cloud Connector em execução no servidor host, mesmo se o processo de esvaziamento falhar:</span><span class="sxs-lookup"><span data-stu-id="cd2da-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```powershell
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="cd2da-111">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="cd2da-111">Example 3</span></span>

<span data-ttu-id="cd2da-112">O próximo exemplo desinstala uma versão de backup do Cloud Connector sem a confirmação do usuário:</span><span class="sxs-lookup"><span data-stu-id="cd2da-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```powershell
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="cd2da-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="cd2da-113">Detailed Description</span></span>
<span data-ttu-id="cd2da-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cd2da-114"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="cd2da-115">Se você estiver desinstalando a versão atual em execução do Cloud Connector, os serviços de esvaziamento serão executados primeiro no Servidor de Mediação e no Servidor de Borda para permitir que as chamadas simultâneas sejam finalizada antes de desinstalar as máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="cd2da-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="cd2da-116">Se você estiver desinstalando uma versão de backup, a drenagem não será executada.</span><span class="sxs-lookup"><span data-stu-id="cd2da-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="cd2da-117">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="cd2da-117">Parameters</span></span>
<span data-ttu-id="cd2da-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="cd2da-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="cd2da-119">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="cd2da-119">**Parameter**</span></span>|<span data-ttu-id="cd2da-120">**Required**</span><span class="sxs-lookup"><span data-stu-id="cd2da-120">**Required**</span></span>|<span data-ttu-id="cd2da-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="cd2da-121">**Type**</span></span>|<span data-ttu-id="cd2da-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="cd2da-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="cd2da-123">Versão</span><span class="sxs-lookup"><span data-stu-id="cd2da-123">Version</span></span> <br/> | <span data-ttu-id="cd2da-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="cd2da-124">Optional</span></span> <br/> |<span data-ttu-id="cd2da-125">System.String</span><span class="sxs-lookup"><span data-stu-id="cd2da-125">System.String</span></span>  <br/> | <span data-ttu-id="cd2da-126">A versão do Cloud Connector que será desinstalada do servidor host.</span><span class="sxs-lookup"><span data-stu-id="cd2da-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="cd2da-127">Se não for especificado, desinstale a versão atual em execução.</span><span class="sxs-lookup"><span data-stu-id="cd2da-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="cd2da-128">Force</span><span class="sxs-lookup"><span data-stu-id="cd2da-128">Force</span></span>  <br/> |<span data-ttu-id="cd2da-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="cd2da-129">Optional</span></span>  <br/> |<span data-ttu-id="cd2da-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="cd2da-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="cd2da-131">Se estiver desinstalando a versão atual em execução, tente esvaziar os servidores no Servidor de Mediação e no Servidor de Borda antes de desinstalar as máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="cd2da-131">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines.</span></span> <span data-ttu-id="cd2da-132">Se você especificar a opção "Force", mesmo se os serviços de esvaziamento falharem, as máquinas virtuais serão desinstaladas.</span><span class="sxs-lookup"><span data-stu-id="cd2da-132">If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled.</span></span> <span data-ttu-id="cd2da-133">Esse parâmetro só é usado para desinstalar a versão atual em execução.</span><span class="sxs-lookup"><span data-stu-id="cd2da-133">This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="cd2da-134">Confirmar</span><span class="sxs-lookup"><span data-stu-id="cd2da-134">Confirm</span></span>  <br/> |<span data-ttu-id="cd2da-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="cd2da-135">Optional</span></span>  <br/> |<span data-ttu-id="cd2da-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="cd2da-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="cd2da-137">Peça confirmação ao usuário para desinstalar as máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="cd2da-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="cd2da-138">O valor padrão é TRUE.</span><span class="sxs-lookup"><span data-stu-id="cd2da-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="cd2da-139">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="cd2da-139">Input Types</span></span>
<span data-ttu-id="cd2da-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cd2da-140"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="cd2da-141">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="cd2da-141">None.</span></span> <span data-ttu-id="cd2da-142">O Uninstall-CcAppliance cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="cd2da-142">The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="cd2da-143">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="cd2da-143">Return Types</span></span>
<span data-ttu-id="cd2da-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cd2da-144"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="cd2da-145">Nenhum</span><span class="sxs-lookup"><span data-stu-id="cd2da-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="cd2da-146">Confira também</span><span class="sxs-lookup"><span data-stu-id="cd2da-146">See also</span></span>
<span data-ttu-id="cd2da-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="cd2da-147"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="cd2da-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="cd2da-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="cd2da-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="cd2da-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="cd2da-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="cd2da-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="cd2da-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="cd2da-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

