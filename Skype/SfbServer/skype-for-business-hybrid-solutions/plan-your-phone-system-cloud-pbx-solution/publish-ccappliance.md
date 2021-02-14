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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e7d5b63e-ba7c-4757-8670-f96b2a91e646
description: O Publish-CcAppliance cmdlet obtém informações de alta disponibilidade da configuração de locatário online e as publica no dispositivo do Skype for Business Cloud Connector Edition no servidor host.
ms.openlocfilehash: 159247614733261cac4b3381e35d8dd297cf9a23
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41824307"
---
# <a name="publish-ccappliance"></a><span data-ttu-id="64ff0-103">Publish-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="64ff0-103">Publish-CcAppliance</span></span>
 
<span data-ttu-id="64ff0-104">O Publish-CcAppliance cmdlet obtém informações de alta disponibilidade da configuração de locatário online e as publica no dispositivo do Skype for Business Cloud Connector Edition no servidor host.</span><span class="sxs-lookup"><span data-stu-id="64ff0-104">The Publish-CcAppliance cmdlet gets high availability information from the online tenant configuration and publishes it to the Skype for Business Cloud Connector Edition appliance on the host server.</span></span> 
  
```powershell
Publish-CcAppliance
```

## <a name="parameters"></a><span data-ttu-id="64ff0-105">Parâmetros</span><span class="sxs-lookup"><span data-stu-id="64ff0-105">Parameters</span></span>

<span data-ttu-id="64ff0-106">Nenhum</span><span class="sxs-lookup"><span data-stu-id="64ff0-106">None</span></span>
  
## <a name="examples"></a><span data-ttu-id="64ff0-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="64ff0-107">Examples</span></span>
<span data-ttu-id="64ff0-108"><a name="Examples"> </a></span><span class="sxs-lookup"><span data-stu-id="64ff0-108"><a name="Examples"> </a></span></span>

### <a name="example-1"></a><span data-ttu-id="64ff0-109">Exemplo 1</span><span class="sxs-lookup"><span data-stu-id="64ff0-109">Example 1</span></span>

<span data-ttu-id="64ff0-110">O exemplo a seguir obtém informações de alta disponibilidade da configuração de locatário online e as publica no dispositivo do Cloud Connector no servidor host:</span><span class="sxs-lookup"><span data-stu-id="64ff0-110">The following example gets high availability information from the online tenant configuration and publishes it to the Cloud Connector appliance on the host server:</span></span>
  
```powershell
Publish-CcAppliance
```

## <a name="detailed-description"></a><span data-ttu-id="64ff0-111">Descrição detalhada</span><span class="sxs-lookup"><span data-stu-id="64ff0-111">Detailed Description</span></span>
<span data-ttu-id="64ff0-112"><a name="DetailedDescription"> </a></span><span class="sxs-lookup"><span data-stu-id="64ff0-112"><a name="DetailedDescription"> </a></span></span>

<span data-ttu-id="64ff0-113">As informações de alta disponibilidade contêm os FQDNs e endereços IP do Servidor de Mediação do site PSTN.</span><span class="sxs-lookup"><span data-stu-id="64ff0-113">High availability information contains the Mediation Server FQDNs and IP addresses of the PSTN site.</span></span> <span data-ttu-id="64ff0-114">Novos registros DNS A são adicionados ao Servidor AD para endereços IP do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="64ff0-114">New DNS A records are added to the AD Server for Mediation Server IP addresses.</span></span> <span data-ttu-id="64ff0-115">Novos itens de topologia são atualizados para o Armazenamento de Gerenciamento Central para os FQDNs e endereços IP do Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="64ff0-115">New topology items are updated to the Central Management Store for the Mediation Server FQDNs and IP addresses.</span></span> 
  
## <a name="input-types"></a><span data-ttu-id="64ff0-116">Tipos de Entrada</span><span class="sxs-lookup"><span data-stu-id="64ff0-116">Input Types</span></span>
<span data-ttu-id="64ff0-117"><a name="InputTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64ff0-117"><a name="InputTypes"> </a></span></span>

<span data-ttu-id="64ff0-118">Nenhum.</span><span class="sxs-lookup"><span data-stu-id="64ff0-118">None.</span></span> <span data-ttu-id="64ff0-119">O Publish-CcAppliance cmdlet não aceita entrada em pipeline.</span><span class="sxs-lookup"><span data-stu-id="64ff0-119">The Publish-CcAppliance cmdlet does not accept pipelined input.</span></span>
  
## <a name="return-types"></a><span data-ttu-id="64ff0-120">Tipos de Retorno</span><span class="sxs-lookup"><span data-stu-id="64ff0-120">Return Types</span></span>
<span data-ttu-id="64ff0-121"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64ff0-121"><a name="ReturnTypes"> </a></span></span>

<span data-ttu-id="64ff0-122">Nenhum</span><span class="sxs-lookup"><span data-stu-id="64ff0-122">None</span></span>
  
## <a name="see-also"></a><span data-ttu-id="64ff0-123">Confira também</span><span class="sxs-lookup"><span data-stu-id="64ff0-123">See also</span></span>
<span data-ttu-id="64ff0-124"><a name="ReturnTypes"> </a></span><span class="sxs-lookup"><span data-stu-id="64ff0-124"><a name="ReturnTypes"> </a></span></span>

[<span data-ttu-id="64ff0-125">Install-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="64ff0-125">Install-CcAppliance</span></span>](install-ccappliance.md)
  
[<span data-ttu-id="64ff0-126">Uninstall-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="64ff0-126">Uninstall-CcAppliance</span></span>](uninstall-ccappliance.md)
  
[<span data-ttu-id="64ff0-127">Register-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="64ff0-127">Register-CcAppliance</span></span>](register-ccappliance.md)
  
[<span data-ttu-id="64ff0-128">Unregister-CcAppliance</span><span class="sxs-lookup"><span data-stu-id="64ff0-128">Unregister-CcAppliance</span></span>](unregister-ccappliance.md)
  

