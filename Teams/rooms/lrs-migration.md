---
title: Migrar dispositivos do Sistema de Salas do Lync para Salas do Microsoft Teams
ms.author: dstrome
author: dstrome
ms.reviewer: sohailta
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.service: msteams
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
ms.assetid: ''
description: Leia este tópico para saber como migrar dispositivos do Sistema de Salas do Lync para usar o software Salas do Microsoft Teams.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: d8da14f2d5f3ec75c6a9fb9c03a33d7e83cd1aed
ms.sourcegitcommit: 975f81d9e595dfb339550625d7cef8ad84449e20
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49662616"
---
# <a name="migrate-lync-room-system-lrs-devices-to-microsoft-teams-rooms"></a><span data-ttu-id="22b33-103">Migrar dispositivos do Lync Room System (LRS) para salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22b33-103">Migrate Lync Room System (LRS) devices to Microsoft Teams Rooms</span></span>

<span data-ttu-id="22b33-104">Os dispositivos Lync Room System (LRS) com o software Skype Room System versão 1 (SRS v1) chegaram ao fim do suporte em 9 de outubro de [2018.](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018)</span><span class="sxs-lookup"><span data-stu-id="22b33-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software has reached [end of support on October 9, 2018](https://support.microsoft.com/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="22b33-105">Isso significa que o software Sistemas de Salas Skype v1 não recebe mais atualizações ou correções de produtos.</span><span class="sxs-lookup"><span data-stu-id="22b33-105">This means Skype Room Systems v1 software will no longer get any product updates or fixes anymore.</span></span> <span data-ttu-id="22b33-106">Os clientes que usam os dispositivos do Sistema de Salas do Lync, usando o software Sistema de Salas do Skype v1, são aconselhados a atualizar os dispositivos nas Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22b33-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Microsoft Teams Rooms.</span></span>

<span data-ttu-id="22b33-107">O software Salas do Microsoft Teams funciona com o Microsoft Teams, além dos serviços Do Skype for Business Server e Online para reuniões e chamadas em todos os dispositivos com suporte nas Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22b33-107">Microsoft Teams Rooms software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all Microsoft Teams Rooms supported devices.</span></span>

<span data-ttu-id="22b33-108">Seus dispositivos **existentes podem** continuar a funcionar após o fim do suporte ao software Skype Room System v1.</span><span class="sxs-lookup"><span data-stu-id="22b33-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software support.</span></span> <span data-ttu-id="22b33-109">No entanto, se esse software atingir um bug de software que precisa que a Microsoft libere uma correção, ele não terá suporte.</span><span class="sxs-lookup"><span data-stu-id="22b33-109">However, if this software hits a software bug that needs Microsoft to release a fix, it will not be supported.</span></span> <span data-ttu-id="22b33-110">O SRS v1 usa tLS 1.0/ 1.1, que será preterido pela Microsoft no futuro.</span><span class="sxs-lookup"><span data-stu-id="22b33-110">SRS v1 uses TLS 1.0/ 1.1 which will be deprecated by Microsoft in the future.</span></span> <span data-ttu-id="22b33-111">Você pode saber mais sobre como se preparar para a [depreciação do TLS 1.0/1.1.](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608)</span><span class="sxs-lookup"><span data-stu-id="22b33-111">You can learn more about [preparing for TLS 1.0/1.1 deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span> 

## <a name="which-devices-are-affected"></a><span data-ttu-id="22b33-112">Quais dispositivos são afetados?</span><span class="sxs-lookup"><span data-stu-id="22b33-112">Which devices are affected?</span></span>

<span data-ttu-id="22b33-113">Aqui está a lista dos dispositivos afetados por essa alteração:</span><span class="sxs-lookup"><span data-stu-id="22b33-113">Here is the list of the devices that are affected by this change:</span></span>

- <span data-ttu-id="22b33-114">RL daÇanúm</span><span class="sxs-lookup"><span data-stu-id="22b33-114">Crestron RL</span></span>
- [<span data-ttu-id="22b33-115">RL2 DaL2</span><span class="sxs-lookup"><span data-stu-id="22b33-115">Crestron RL2</span></span>](https://www.crestron.com/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="22b33-116">Sistemas smart room</span><span class="sxs-lookup"><span data-stu-id="22b33-116">SMART Room systems</span></span>](https://support.smarttech.com/en/hardware/room-systems-skype)
- [<span data-ttu-id="22b33-117">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="22b33-117">Polycom CX8000</span></span>](https://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)

## <a name="upgrade-options"></a><span data-ttu-id="22b33-118">Opções de atualização</span><span class="sxs-lookup"><span data-stu-id="22b33-118">Upgrade options</span></span>

<span data-ttu-id="22b33-119">Há várias opções para atualizar o Lync Room Systems para a próxima geração de Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22b33-119">There are multiple options for upgrading Lync Room Systems to the next generation of Microsoft Teams Rooms.</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="22b33-120">Programa de trade-in de hardware DaÇanron</span><span class="sxs-lookup"><span data-stu-id="22b33-120">Crestron hardware Trade-in program</span></span>

<span data-ttu-id="22b33-121">A Seniorron fornecerá uma atualização para o sistema [Sr. DaÇanureron ou](https://www.crestron.com/products/featured-solutions/crestron-sr) equivalente para todos os clientes do Sistema de Sala Não-Autorron Lync (por exemplo, Smart ou Polycom LRS).</span><span class="sxs-lookup"><span data-stu-id="22b33-121">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers (e.g Smart or Polycom LRS).</span></span> <span data-ttu-id="22b33-122">Veja os detalhes deste programa [aqui](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou</span><span class="sxs-lookup"><span data-stu-id="22b33-122">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or</span></span> <!-- For details, --><span data-ttu-id="22b33-123">[email](mailto:lrsupgrade@crestron.com) Suporte a LRS da LRS DaÇanron.</span><span class="sxs-lookup"><span data-stu-id="22b33-123">[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  

### <a name="crestron-rl2-upgrade-to-microsoft-teams-rooms"></a><span data-ttu-id="22b33-124">Atualização da RL2 para Salas do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="22b33-124">Crestron RL2 upgrade to Microsoft Teams Rooms</span></span>

<span data-ttu-id="22b33-125">Os clientes existentes da Crestron RL2 (também conhecido como RL200 DaL200) podem adquirir um kit de atualização para atualizar RL2 para RL3 atual usando um custo mínimo por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="22b33-125">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade kit to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="22b33-126">Veja os detalhes deste programa [aqui.](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT)</span><span class="sxs-lookup"><span data-stu-id="22b33-126">See details of this program [here](https://crestron.com/Products/Workspace-Solutions/Unified-Communications/Crestron-RL-2/CCS-UC-250-KIT).</span></span>

### <a name="smart-room-systems-upgrade"></a><span data-ttu-id="22b33-127">Atualização do smart room systems</span><span class="sxs-lookup"><span data-stu-id="22b33-127">SMART Room Systems upgrade</span></span>

<span data-ttu-id="22b33-128">Para clientes smart LRS, além do programa de troca de hardware DaLron, o SMART também está trabalhando no fornecimento de uma solução para atualizar para salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22b33-128">For SMART LRS customers, apart from Crestron hardware trade-in program, SMART is also working on providing a solution to upgrade to Microsoft Teams Rooms.</span></span> <span data-ttu-id="22b33-129">Esta atualização será fornecida pela SMART Technologies Inc. para o cliente sob suporte do produto.</span><span class="sxs-lookup"><span data-stu-id="22b33-129">This upgrade will be provided by SMART Technologies Inc. to customer under product support.</span></span> <span data-ttu-id="22b33-130">Veja mais sobre isso [aqui.](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml)</span><span class="sxs-lookup"><span data-stu-id="22b33-130">Please see more about this [here](https://support.smarttech.com/docs/hardware/room-systems-skype/srs-skype-v2/en/about/default.cshtml).</span></span>


## <a name="what-should-you-do"></a><span data-ttu-id="22b33-131">O que você deve fazer?</span><span class="sxs-lookup"><span data-stu-id="22b33-131">What should you do?</span></span>

<span data-ttu-id="22b33-132">Recomendamos que você planeje atualizar os dispositivos do Sistema de Salas do Lync para salas do Microsoft Teams antes da depreciação do TLS 1.0/1.1 usando as opções de atualização mencionadas acima.</span><span class="sxs-lookup"><span data-stu-id="22b33-132">We recommend you plan to update Lync Room System devices to Microsoft Teams Rooms before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="22b33-133">Além disso, você também pode considerar substituir dispositivos existentes por novos dispositivos certificados para Salas do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="22b33-133">Additionally, you may also consider replacing existing devices with new devices certified for Microsoft Teams Rooms.</span></span> <span data-ttu-id="22b33-134">Consulte [os dispositivos de](https://aka.ms/roomdevices) sala para obter detalhes e também dê uma olhada nos requisitos de Salas do Microsoft [Teams.](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements)</span><span class="sxs-lookup"><span data-stu-id="22b33-134">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Microsoft Teams Rooms requirements](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  


> [!NOTE]
> <span data-ttu-id="22b33-135">O software Microsoft Teams Rooms oferece suporte ao protocolo TLS 1.2 a partir de 14 de dezembro de 2018 com a versão do aplicativo 4.0.64.0.</span><span class="sxs-lookup"><span data-stu-id="22b33-135">Microsoft Teams Rooms software supports the TLS 1.2 protocol as of December 14, 2018 with app version 4.0.64.0.</span></span> <span data-ttu-id="22b33-136">Para clientes locais, a habilitação da comunicação por meio do TLS 1.2 para Salas do Microsoft Teams requer a Atualização Cumulativa 9 (CU9) do Skype for Business Server 2015 ou a Atualização Cumulativa 1 (CU1) do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="22b33-136">For on-premises customers, enabling communication over TLS 1.2 for Microsoft Teams Rooms requires Skype for Business Server 2015 Cumulative Update 9 (CU9) or Skype for Business Server 2019 Cumulative Update 1 (CU1).</span></span> <span data-ttu-id="22b33-137">A alteração não deve afetar os clientes do Skype for Business Online, uma vez que as alterações do cliente estão em conformidade com o encaminhamento e com compatibilidade com compatibilidade.</span><span class="sxs-lookup"><span data-stu-id="22b33-137">The change should not affect Skype for Business Online customers as client changes are forward and backward compliant.</span></span>
