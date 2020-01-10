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
localization_priority: Normal
ms.assetid: 95e37b13-525b-4690-be32-839312e4ffe3
description: 'O cmdlet Switch-CcVersion desconecta o dispositivo em execução e alterna para um dispositivo recentemente implantado ou de backup. '
ms.openlocfilehash: 157d1b677cc6c63d7707c9e1633cd8b6e3ad5927
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003151"
---
# <a name="switch-ccversion"></a><span data-ttu-id="ea676-103">Switch-CcVersion</span><span class="sxs-lookup"><span data-stu-id="ea676-103">Switch-CcVersion</span></span>
 
<span data-ttu-id="ea676-104">O cmdlet Switch-CcVersion desconecta o dispositivo em execução e alterna para um dispositivo recentemente implantado ou de backup. </span><span class="sxs-lookup"><span data-stu-id="ea676-104">The Switch-CcVersion cmdlet disconnects the running appliance and switches to a newly deployed or backup appliance.</span></span> 
  
```powershell
Switch-CcVersion [-Force]
```

## <a name="examples"></a><span data-ttu-id="ea676-105">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ea676-105">Examples</span></span>
<span data-ttu-id="ea676-106"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="ea676-106"></span></span>

### <a name="example-1"></a><span data-ttu-id="ea676-107">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="ea676-107">Example 1</span></span>

<span data-ttu-id="ea676-108">O exemplo a seguir drena os serviços do dispositivo em execução no momento e, em seguida, alterna para um dispositivo recentemente implantado ou de backup:</span><span class="sxs-lookup"><span data-stu-id="ea676-108">The following example drains the services of the current running appliance, and then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion
```

### <a name="example-2"></a><span data-ttu-id="ea676-109">Exemplo 2</span><span class="sxs-lookup"><span data-stu-id="ea676-109">Example 2</span></span>

<span data-ttu-id="ea676-110">O próximo exemplo drena os serviços do dispositivo em execução no momento e interrompe os serviços  compulsoriamente, quando a drenagem dos serviços falha.</span><span class="sxs-lookup"><span data-stu-id="ea676-110">The next example drains the services of the current running appliance, and stops services forcibly if draining the services fails.</span></span> <span data-ttu-id="ea676-111">O comando, então, alterna para um dispositivo implantado recentemente ou de backup:</span><span class="sxs-lookup"><span data-stu-id="ea676-111">The command then switches to a newly deployed or backup appliance:</span></span>
  
```powershell
Switch-CcVersion -Force
```

## <a name="detailed-description"></a><span data-ttu-id="ea676-112">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="ea676-112">Detailed Description</span></span>
<span data-ttu-id="ea676-113"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ea676-113"></span></span>

<span data-ttu-id="ea676-114">O cmdlet switch-CcVersion esvazia os serviços do conector de nuvem no servidor de mediação e no servidor de borda.</span><span class="sxs-lookup"><span data-stu-id="ea676-114">The Switch-CcVersion cmdlet drains the Cloud Connector services on the Mediation Server and Edge Server.</span></span> <span data-ttu-id="ea676-115">Todas as chamadas em execução serão concluídas, mas o dispositivo rejeitará novas chamadas.</span><span class="sxs-lookup"><span data-stu-id="ea676-115">All running calls will be completed, but the appliance will reject any new calls.</span></span> <span data-ttu-id="ea676-116">Depois de drenar, o cmdlet desconecta o dispositivo em execução das redes corporativas e de Internet, desliga todas as máquinas virtuais pertencentes ao dispositivo, e então conecta o dispositivo de backup às redes corporativas e de Internet.</span><span class="sxs-lookup"><span data-stu-id="ea676-116">After draining, the cmdlet disconnects the running appliance from the corporate and Internet networks, turns off all the virtual machines belonging to the appliance, and then connects the backup appliance to the corporate and Internet networks.</span></span>
  
## <a name="parameters"></a><span data-ttu-id="ea676-117">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="ea676-117">Parameters</span></span>
<span data-ttu-id="ea676-118"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="ea676-118"></span></span>

|<span data-ttu-id="ea676-119">**Parâmetro**</span><span class="sxs-lookup"><span data-stu-id="ea676-119">**Parameter**</span></span>|<span data-ttu-id="ea676-120">**Obrigatório**</span><span class="sxs-lookup"><span data-stu-id="ea676-120">**Required**</span></span>|<span data-ttu-id="ea676-121">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="ea676-121">**Type**</span></span>|<span data-ttu-id="ea676-122">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="ea676-122">**Description**</span></span>|
|:-----|:-----|:-----|:-----|
| <span data-ttu-id="ea676-123">Forçar</span><span class="sxs-lookup"><span data-stu-id="ea676-123">Force</span></span> <br/> | <span data-ttu-id="ea676-124">Opcional</span><span class="sxs-lookup"><span data-stu-id="ea676-124">Optional</span></span> <br/> |<span data-ttu-id="ea676-125">System.Management.Automation.SwitchParameter</span><span class="sxs-lookup"><span data-stu-id="ea676-125">System.Management.Automation.SwitchParameter</span></span>  <br/> | <span data-ttu-id="ea676-126"> Interrompe compulsoriamente os serviços, quando a drenagem dos serviços falha.</span><span class="sxs-lookup"><span data-stu-id="ea676-126">Stops services forcibly if draining the services fails.</span></span> <br/> |
   
## <a name="input-types"></a><span data-ttu-id="ea676-127">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="ea676-127">Input Types</span></span>
<span data-ttu-id="ea676-128"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ea676-128"></span></span>

<span data-ttu-id="ea676-129">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ea676-129">None</span></span>
  
## <a name="return-types"></a><span data-ttu-id="ea676-130">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="ea676-130">Return Types</span></span>
<span data-ttu-id="ea676-131"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ea676-131"></span></span>

<span data-ttu-id="ea676-132">Nenhum </span><span class="sxs-lookup"><span data-stu-id="ea676-132">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="ea676-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ea676-133">See also</span></span>
<span data-ttu-id="ea676-134"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="ea676-134"></span></span>

<span data-ttu-id="ea676-135">Nenhum</span><span class="sxs-lookup"><span data-stu-id="ea676-135">None</span></span>
  

