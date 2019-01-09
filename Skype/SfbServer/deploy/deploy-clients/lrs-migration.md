---
title: Migrar dispositivos de sistema do Lync sala ao sistema de sala Skype versão 2
ms.author: jambirk
author: jambirk
ms.reviewer: sohailta
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ''
description: Leia este tópico para saber como migrar dispositivos de sistema do Lync sala para usar o software do sistema de sala Skype v2.
ms.openlocfilehash: b2d748a37e7e060e19d0708b6979f9254af13682
ms.sourcegitcommit: 454ded73af5854d7b81a3b996702a6464b3fc313
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/09/2019
ms.locfileid: "27772900"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="ed1de-103">Migrar dispositivos de sistema de sala do Lync (LRS) para o sistema de sala Skype v2</span><span class="sxs-lookup"><span data-stu-id="ed1de-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="ed1de-104">Dispositivos de sistema de sala do Lync (LRS) com o software do sistema de sala do Skype versão 1 (v1 SRS) atingiu o [fim do suporte em 9 de outubro de 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span><span class="sxs-lookup"><span data-stu-id="ed1de-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="ed1de-105">Isso significa que o software do Skype sala sistemas v1 não são mais receberá quaisquer atualizações de produto ou correções mais.</span><span class="sxs-lookup"><span data-stu-id="ed1de-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="ed1de-106">Clientes com dispositivos de sistema do Lync sala usando o software do sistema de sala Skype v1 recomenda-se para atualizar seus dispositivos para o sistema de sala Skype v2 (versão 2 SRS).</span><span class="sxs-lookup"><span data-stu-id="ed1de-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="ed1de-107">Software Skype sala sistema versão 2 (v2 SRS) funciona com Microsoft Teams além do Skype para Business Server e Online services para reuniões e chamadas em todos os dispositivos do SRS v2 suportados.</span><span class="sxs-lookup"><span data-stu-id="ed1de-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="ed1de-108">Seus dispositivos existentes **podem** continuar a funciona depois que o suporte a fim de software do sistema de sala Skype v1.</span><span class="sxs-lookup"><span data-stu-id="ed1de-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="ed1de-109">No entanto, se esse software acessa um bug de software que precisa Microsoft para liberar uma correção, ela não será suportada.</span><span class="sxs-lookup"><span data-stu-id="ed1de-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="ed1de-110">V1 SRS usa o protocolo TLS 1.0 / 1.1 que será preterido pela Microsoft no futuro.</span><span class="sxs-lookup"><span data-stu-id="ed1de-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in future.</span></span> <span data-ttu-id="ed1de-111">Você pode aprender mais sobre [Preparando para TLS 1.0/1.1 preterir](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="ed1de-111">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> <span data-ttu-id="ed1de-112">Skype sala sistema V2 está adicionando suporte a TLS 1.2 e continuará inserido antigas 31 de outubro de 2018.</span><span class="sxs-lookup"><span data-stu-id="ed1de-112">Skype Room System V2 is adding support for TLS 1.2 and will continue to work past October 31, 2018.</span></span> <span data-ttu-id="ed1de-113">Skype para negócios nos clientes do local não deve desabilitar o TLS 1.0/1.1 que suportem a annouces Skype sala sistema V2 para TLS 1.2 independentemente diretrizes gerais sobre preterir TLS 1.0/1.1.</span><span class="sxs-lookup"><span data-stu-id="ed1de-113">Skype for Business on premise customers should not disable TLS 1.0/1.1 until Skype Room System V2 annouces support for TLS 1.2 regardless of general guidelines on TLS 1.0/1.1 deprecation.</span></span>

## <a name="which-devices-are-affected"></a><span data-ttu-id="ed1de-114">Quais dispositivos são afetados?</span><span class="sxs-lookup"><span data-stu-id="ed1de-114">Which devices are affected?</span></span>
<span data-ttu-id="ed1de-115">Aqui está uma lista dos dispositivos que são afetados por essa alteração:</span><span class="sxs-lookup"><span data-stu-id="ed1de-115">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="ed1de-116">Sistemas de sala inteligentes</span><span class="sxs-lookup"><span data-stu-id="ed1de-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="ed1de-117">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="ed1de-117">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="ed1de-118">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="ed1de-118">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="ed1de-119">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="ed1de-119">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="ed1de-120">Opções de atualização</span><span class="sxs-lookup"><span data-stu-id="ed1de-120">Upgrade options</span></span>
<span data-ttu-id="ed1de-121">Há várias opções para atualizar o Lync sistemas de sala para a próxima geração de sistemas de sala Skype (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="ed1de-121">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="ed1de-122">Programa de trade-in de hardware Crestron</span><span class="sxs-lookup"><span data-stu-id="ed1de-122">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="ed1de-123">Crestron fornecerá uma atualização para o [sistema Crestron SR](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) ou equivalente para todos os clientes do sistema de sala do Lync não-Crestron.</span><span class="sxs-lookup"><span data-stu-id="ed1de-123">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="ed1de-124">Ver os detalhes deste programa [aqui](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, --> [email](mailto:lrsupgrade@crestron.com) suporte Crestron LRS.</span><span class="sxs-lookup"><span data-stu-id="ed1de-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-upgrade-to-srs-v2"></a><span data-ttu-id="ed1de-125">Atualização de Crestron RL2 para V2 SRS</span><span class="sxs-lookup"><span data-stu-id="ed1de-125">Crestron RL2 upgrade to SRS V2</span></span>
<span data-ttu-id="ed1de-126">Os clientes existentes do Crestron RL2 (também conhecido como Crestron RL200) podem adquirir um kit de atualização para atualizar RL2 atual para RL3 usando um para um custo mínimo por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="ed1de-126">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="ed1de-127">Ver os detalhes deste programa [aqui](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span><span class="sxs-lookup"><span data-stu-id="ed1de-127">See details of this program [here](https://crestron.com/en-US/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span> 


### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="ed1de-128">Atualização de sistemas de sala inteligente</span><span class="sxs-lookup"><span data-stu-id="ed1de-128">SMART Room Systems upgrade</span></span> 
<span data-ttu-id="ed1de-129">Para clientes inteligentes LRS, além de Crestron programa de trade-in de hardware, o Microsoft e inteligente também estão trabalhando em fornecendo uma solução para atualizar para o sistema de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="ed1de-129">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="ed1de-130">Essa atualização será fornecida pelo Inc de tecnologias inteligentes. Consulte mais informações sobre esta [aqui](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span><span class="sxs-lookup"><span data-stu-id="ed1de-130">This upgrade will be provided by SMART Technologies Inc. Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>

<!--  
For later 
### Do-It-Yourself
A Do-It-Yourself option is also available for customers with upgrade to Windows 10 and Skype Room Systems v2 software. Windows 10 Enterprise Licenses are available through [approved resellers](https://www.microsoft.com/en-us/Licensing/how-to-buy/how-to-buy.aspx) and Skype Room System V2 software will be available through this guide. 
 
  
To use this option however, customers must additionaly buy a [Logitech Screen Share](https://www.logitech.com/en-us/product/screen-share) adapter. Microsoft will provide instructions on how to use this adapter with Skype Room System v2 software. 


Look for upgrade instructions on this page shortly. 
  
### Summary of upgrade options
This table lists summary of all available options for existing LRS devices:
<!--  For later 
| Upgrade Option | SMART Room Systems | Crestron RL2 | Polycom CX8000 | Crestron RL |
|:--- |:--- |:--- |:--- |:--- |
|**Crestron hardware </br>Trade-in program**|Available|Available|Available|Available|
|**Crestron RL3**|Not Available|Available|Not Available|Not Available|
|**Do-It-Yourself**|Available|Not Available|Not Available|Not Available|
| | | | | |
-->

## <a name="what-should-you-do"></a><span data-ttu-id="ed1de-131">O que você deve fazer?</span><span class="sxs-lookup"><span data-stu-id="ed1de-131">What should you do?</span></span>
<span data-ttu-id="ed1de-132">Recomendamos que você planeja atualizar dispositivos de sistema do Lync sala para sistemas de sala Skype v2 antes de preterir TLS 1.0/1.1 usando as opções de atualização mencionadas acima.</span><span class="sxs-lookup"><span data-stu-id="ed1de-132">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="ed1de-133">Além disso, você também pode considerar a substituição de dispositivos existentes com novos dispositivos certificados para o SRS v2.</span><span class="sxs-lookup"><span data-stu-id="ed1de-133">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="ed1de-134">Consulte [dispositivos de sala](https://aka.ms/roomdevices) para obter detalhes e também dar uma olhada em [sistemas de sala Skype v2 requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="ed1de-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="ed1de-135">Funcionalidade de toque e whiteboard ainda não é suportada no sistema de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="ed1de-135">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="ed1de-136">Suporte de toque e quadro de comunicações está no registro acumulado para o sistema de sala Skype v2 e será adicionado em CY2019 de S1.</span><span class="sxs-lookup"><span data-stu-id="ed1de-136">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>

> [!NOTE]
> <span data-ttu-id="ed1de-137">Skype sala sistema V2 software atualmente não suporta protocolo TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="ed1de-137">Skype Room System V2 software currently does not support TLS 1.2 protocol.</span></span> <span data-ttu-id="ed1de-138">Suporte a TLS 1.2 está sendo trabalhado e será concluído antes de preterir TLS 1.0/1.1.</span><span class="sxs-lookup"><span data-stu-id="ed1de-138">TLS 1.2 support is being worked on and will be completed before TLS 1.0/1.1 deprecation.</span></span> <span data-ttu-id="ed1de-139">Os clientes upgradging para SRS v2 não verá qualquer impacto de TLS 1.0/1.1 preterir em dispositivos de sala executando a versão mais recente do SRS v2 app.</span><span class="sxs-lookup"><span data-stu-id="ed1de-139">Customers upgradging to SRS v2 will not see any impact of TLS 1.0/1.1 deprecation on Room devices running latest version of SRS v2 app.</span></span> <span data-ttu-id="ed1de-140">Skype para negócios nos clientes do local não deve desabilitar o TLS 1.0/1.1 que suportem a annouces Skype sala sistema V2 para TLS 1.2.</span><span class="sxs-lookup"><span data-stu-id="ed1de-140">Skype for Business on premise customers should not disable TLS 1.0/1.1 until Skype Room System V2 annouces support for TLS 1.2.</span></span> 
