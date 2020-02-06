---
title: Switch-CcVersion
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
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: 'O cmdlet Switch-CcVersion desconecta o dispositivo em execução e alterna para um dispositivo recentemente implantado ou de backup. '
ms.openlocfilehash: 31dbb841caae51de0accedf081fa576ec378044b
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824145"
---
# <a name="switch-ccversion"></a><span data-ttu-id="2f815-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="2f815-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="2f815-104">O cmdlet Switch-CcVersion desconecta o dispositivo em execução e alterna para um dispositivo recentemente implantado ou de backup. </span><span class="sxs-lookup"><span data-stu-id="2f815-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="2f815-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2f815-105">Examples</span></span>
<span data-ttu-id="2f815-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="2f815-106"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="2f815-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="2f815-107">Example 1</span></span>

<span data-ttu-id="2f815-108">O exemplo a seguir drena os serviços do dispositivo em execução no momento e, em seguida, alterna para um dispositivo recentemente implantado ou de backup:</span><span class="sxs-lookup"><span data-stu-id="2f815-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="2f815-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="2f815-109">Example 2</span></span>

<span data-ttu-id="2f815-110">O próximo exemplo drena os serviços do dispositivo em execução no momento e interrompe os serviços  compulsoriamente, quando a drenagem dos serviços falha.</span><span class="sxs-lookup"><span data-stu-id="2f815-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="2f815-111">O comando, então, alterna para um dispositivo implantado recentemente ou de backup:</span><span class="sxs-lookup"><span data-stu-id="2f815-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="2f815-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="2f815-112">Detailed Description</span></span>
<span data-ttu-id="2f815-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2f815-113"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="2f815-114">O cmdlet switch-CcVersion esvazia os serviços do conector de nuvem no servidor de mediação e no servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="2f815-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="2f815-115">Todas as chamadas em execução serão concluídas, mas o dispositivo rejeitará novas chamadas.</span><span class="sxs-lookup"><span data-stu-id="2f815-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="2f815-116">Depois de drenar, o cmdlet desconecta o dispositivo em execução das redes corporativas e de Internet, desliga todas as máquinas virtuais pertencentes ao dispositivo, e então conecta o dispositivo de backup às redes corporativas e de Internet.</span><span class="sxs-lookup"><span data-stu-id="2f815-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="2f815-117">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="2f815-117">Parameters</span></span>
<span data-ttu-id="2f815-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="2f815-118"><a name="DetailedDescription"> </a></span></span>

|<span data-ttu-id="2f815-119">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="2f815-119">**Parameter**</span></span>|<span data-ttu-id="2f815-120">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="2f815-120">**Required**</span></span>|<span data-ttu-id="2f815-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2f815-121">**Type**</span></span>|<span data-ttu-id="2f815-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2f815-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="2f815-123">Forçar</span><span class="sxs-lookup"><span data-stu-id="2f815-123">Force</span></span> <br/> | <span data-ttu-id="2f815-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="2f815-124">Optional</span></span> <br/> |<span data-ttu-id="2f815-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="2f815-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="2f815-126"> Interrompe compulsoriamente os serviços, quando a drenagem dos serviços falha.</span><span class="sxs-lookup"><span data-stu-id="2f815-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="2f815-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="2f815-127">Input Types</span></span>
<span data-ttu-id="2f815-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2f815-128"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="2f815-129">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2f815-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="2f815-130">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="2f815-130">Return Types</span></span>
<span data-ttu-id="2f815-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2f815-131"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2f815-132">Nenhum </span><span class="sxs-lookup"><span data-stu-id="2f815-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="2f815-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="2f815-133">See also</span></span>
<span data-ttu-id="2f815-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="2f815-134"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="2f815-135">Nenhum</span><span class="sxs-lookup"><span data-stu-id="2f815-135">None</span></span>
  

