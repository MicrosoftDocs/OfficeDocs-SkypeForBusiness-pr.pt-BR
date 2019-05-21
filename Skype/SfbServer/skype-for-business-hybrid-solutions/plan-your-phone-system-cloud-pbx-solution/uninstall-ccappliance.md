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
ms.openlocfilehash: 337c5c489846facb1da3c177cac7a965d7550ae5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34286891"
---
# <a name="uninstall-ccappliance"></a><span data-ttu-id="196d7-103">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="196d7-103">Uninstall-CcAppliance</span></span>
 
<span data-ttu-id="196d7-104">O cmdlet Uninstall-CcAppliance cancela a instalação do dispositivo  em execução do Skype for Business Cloud Connector Edition no servidor host. </span><span class="sxs-lookup"><span data-stu-id="196d7-104">The Uninstall-CcAppliance cmdlet uninstalls the running Skype for Business Cloud Connector Edition appliance from the host server.</span></span> 
  
```
Uninstall-CcAppliance [-Version <string>] [-Force] [-Confirm <bool>] [<CommonParameters>]
```

## <a name="examples"></a><span data-ttu-id="196d7-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="196d7-105">Examples</span></span>
<span data-ttu-id="196d7-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="196d7-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="196d7-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="196d7-107">Example 1</span></span>

<span data-ttu-id="196d7-108">O exemplo a seguir esvazia e desinstala o dispositivo do conector de nuvem do servidor host:</span><span class="sxs-lookup"><span data-stu-id="196d7-108">The following example drains and uninstalls the Cloud Connector appliance from the host server:</span></span>
  
```
Uninstall-CcAppliance
```

### <a name="example-2"></a><span data-ttu-id="196d7-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="196d7-109">Example 2</span></span>

<span data-ttu-id="196d7-110">O próximo exemplo drena e forçosamente desinstala o dispositivo de conector de nuvem em execução no servidor host, mesmo que o processo de descarga falhasse:</span><span class="sxs-lookup"><span data-stu-id="196d7-110">The next example drains and forcibly uninstalls the running Cloud Connector appliance on the host server even if the drain process failed:</span></span>
  
```
Uninstall-CcAppliance -Force
```

### <a name="example-3"></a><span data-ttu-id="196d7-111">Exemplo 3</span><span class="sxs-lookup"><span data-stu-id="196d7-111">Example 3</span></span>

<span data-ttu-id="196d7-112">O próximo exemplo desinstala uma versão de backup do conector de nuvem sem a confirmação do usuário:</span><span class="sxs-lookup"><span data-stu-id="196d7-112">The next example uninstalls a Cloud Connector backup version without the user's confirmation:</span></span>
  
```
Uninstall-CcAppliance -Version 1.3.8 -Confirm:$false
```

## <a name="detailed-description"></a><span data-ttu-id="196d7-113">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="196d7-113">Detailed Description</span></span>
<span data-ttu-id="196d7-114"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="196d7-114"></span></span>

<span data-ttu-id="196d7-115">Se você estiver desinstalando a versão atual do conector de nuvem, os serviços de descarga serão executados primeiro no servidor de mediação e no servidor de borda para que as chamadas simultâneas sejam concluídas antes da desinstalação das máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="196d7-115">If you are uninstalling the current running version of Cloud Connector, drain services are first run on the Mediation Server and Edge Server to let concurrent calls finish before uninstalling the virtual machines.</span></span> <span data-ttu-id="196d7-116">Se você estiver desinstalando uma versão do backup, os esvaziamento não será executado.</span><span class="sxs-lookup"><span data-stu-id="196d7-116">If you are uninstalling a backup version, draining is not performed.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="196d7-117">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="196d7-117">Parameters</span></span>
<span data-ttu-id="196d7-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="196d7-118"></span></span>

|<span data-ttu-id="196d7-119">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="196d7-119">**Parameter**</span></span>|<span data-ttu-id="196d7-120">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="196d7-120">**Required**</span></span>|<span data-ttu-id="196d7-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="196d7-121">**Type**</span></span>|<span data-ttu-id="196d7-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="196d7-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="196d7-123">Versão</span><span class="sxs-lookup"><span data-stu-id="196d7-123">Version</span></span> <br/> | <span data-ttu-id="196d7-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="196d7-124">Optional</span></span> <br/> |<span data-ttu-id="196d7-125">System.String</span><span class="sxs-lookup"><span data-stu-id="196d7-125">System.String</span></span>  <br/> | <span data-ttu-id="196d7-126">A versão do conector de nuvem que será desinstalada do servidor host.</span><span class="sxs-lookup"><span data-stu-id="196d7-126">The version of Cloud Connector that will be uninstalled from the host server.</span></span> <span data-ttu-id="196d7-127">Se não for especificado, desinstale a versão atual em execução.</span><span class="sxs-lookup"><span data-stu-id="196d7-127">If not specified, uninstall the current running version.</span></span> <br/> |
|<span data-ttu-id="196d7-128">Forçar</span><span class="sxs-lookup"><span data-stu-id="196d7-128">Force</span></span>  <br/> |<span data-ttu-id="196d7-129">Opcional</span><span class="sxs-lookup"><span data-stu-id="196d7-129">Optional</span></span>  <br/> |<span data-ttu-id="196d7-130">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="196d7-130">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="196d7-p103">Se você estiver desinstalando a versão atual em execução, tente esvaziar os servidores no Servidor de Mediação e do Servidor de Borda antes de desinstalar as máquinas virtuais. Se você especificar o comutador "Forçar", mesmo se os serviços de esvaziamento falharem, as máquinas virtuais serão desinstaladas. Este parâmetro é usado somente para desinstalar a versão atual em execução.</span><span class="sxs-lookup"><span data-stu-id="196d7-p103">If uninstalling the current running version, attempt to drain servers on Mediation Server and Edge Server before uninstalling the virtual machines. If you specify the "Force" switch, even if the drain services fail, the virtual machines will be uninstalled. This parameter is only used to uninstall the current running version.</span></span>  <br/> |
|<span data-ttu-id="196d7-134">Confirmar</span><span class="sxs-lookup"><span data-stu-id="196d7-134">Confirm</span></span>  <br/> |<span data-ttu-id="196d7-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="196d7-135">Optional</span></span>  <br/> |<span data-ttu-id="196d7-136">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="196d7-136">System.Management.Automation.SwitchParameter</span></span>  <br/> |<span data-ttu-id="196d7-137">Solicite confirmação do usuário para desinstalar as máquinas virtuais.</span><span class="sxs-lookup"><span data-stu-id="196d7-137">Ask user's confirmation to uninstall the virtual machines.</span></span> <span data-ttu-id="196d7-138">O valor padrão é TRUE.</span><span class="sxs-lookup"><span data-stu-id="196d7-138">Default value is TRUE.</span></span>  <br/> |
   
## <a name="input-types"></a><span data-ttu-id="196d7-139">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="196d7-139">Input Types</span></span>
<span data-ttu-id="196d7-140"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="196d7-140"></span></span>

<span data-ttu-id="196d7-p105">Nenhum. O cmdlet Uninstall-CcAppliance não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="196d7-p105">None. The Uninstall-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="196d7-143">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="196d7-143">Return Types</span></span>
<span data-ttu-id="196d7-144"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="196d7-144"></span></span>

<span data-ttu-id="196d7-145">Nenhum</span><span class="sxs-lookup"><span data-stu-id="196d7-145">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="196d7-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="196d7-146">See also</span></span>
<span data-ttu-id="196d7-147"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="196d7-147"></span></span>

[<span data-ttu-id="196d7-148">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="196d7-148">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="196d7-149">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="196d7-149">Publish-CcAppliance</span></span>](publish-ccappliance.md)
  
[<span data-ttu-id="196d7-150">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="196d7-150">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="196d7-151">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="196d7-151">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

