---
title: Publish-CcAppliance
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 3/31/2017
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: 'O cmdlet Publish-CcAppliance obtém informações sobre alta disponibilidade da configuração do locatário online e depois as publica para o dispositivo do Skype for Business Cloud Connector Edition no servidor host. '
ms.openlocfilehash: da9135f669cb5b8cbe127295b20d82fd1632a3d3
ms.sourcegitcommit: fe274303510d07a90b506bfa050c669accef0476
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2020
ms.locfileid: "41003081"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="6f0d8-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="6f0d8-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="6f0d8-104">O cmdlet Publish-CcAppliance obtém informações sobre alta disponibilidade da configuração do locatário online e depois as publica para o dispositivo do Skype for Business Cloud Connector Edition no servidor host. </span><span class="sxs-lookup"><span data-stu-id="6f0d8-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="6f0d8-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6f0d8-105">Parameters</span></span>

<span data-ttu-id="6f0d8-106">Nenhum</span><span class="sxs-lookup"><span data-stu-id="6f0d8-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="6f0d8-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6f0d8-107">Examples</span></span>
<span data-ttu-id="6f0d8-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="6f0d8-108"></span></span>

### <a name="example-1"></a><span data-ttu-id="6f0d8-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="6f0d8-109">Example 1</span></span>

<span data-ttu-id="6f0d8-110">O exemplo a seguir obtém informações de alta disponibilidade da configuração do locatário online e a publica no dispositivo do conector de nuvem no servidor host:</span><span class="sxs-lookup"><span data-stu-id="6f0d8-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="6f0d8-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="6f0d8-111">Detailed Description</span></span>
<span data-ttu-id="6f0d8-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="6f0d8-112"></span></span>

<span data-ttu-id="6f0d8-p101">As informações sobre alta disponibilidade contêm os FQDNs do Servidor de Mediação e endereços IP do site PSTN. Os novos registros do DNS A são adicionados ao Servidor AD para os endereços de IP do Servidor de Mediação. Os novos itens de topologia são atualizados para o Repositório de Gerenciamento Central para os FQDNs do Servidor de Mediação e endereços IP. </span><span class="sxs-lookup"><span data-stu-id="6f0d8-p101">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site. New DNS A records are added to the AD Server for Mediation Server IP addresses. New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="6f0d8-116">Tipos de entrada</span><span class="sxs-lookup"><span data-stu-id="6f0d8-116">Input Types</span></span>
<span data-ttu-id="6f0d8-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f0d8-117"></span></span>

<span data-ttu-id="6f0d8-118">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="6f0d8-118">None.</span></span> <span data-ttu-id="6f0d8-119">O cmdlet Publish-CcAppliance não aceita a entrada por pipeline.</span><span class="sxs-lookup"><span data-stu-id="6f0d8-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="6f0d8-120">Tipos de retorno</span><span class="sxs-lookup"><span data-stu-id="6f0d8-120">Return Types</span></span>
<span data-ttu-id="6f0d8-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f0d8-121"></span></span>

<span data-ttu-id="6f0d8-122">Nenhum </span><span class="sxs-lookup"><span data-stu-id="6f0d8-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="6f0d8-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f0d8-123">See also</span></span>
<span data-ttu-id="6f0d8-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="6f0d8-124"></span></span>

[<span data-ttu-id="6f0d8-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="6f0d8-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="6f0d8-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="6f0d8-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="6f0d8-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="6f0d8-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="6f0d8-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="6f0d8-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

