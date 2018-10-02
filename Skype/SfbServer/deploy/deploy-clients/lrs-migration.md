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
ms.openlocfilehash: 18cc3f954480a000bfe962e0a4b461e05568479b
ms.sourcegitcommit: 6447a3aa060452c8d6879524cd6a56aecf33b152
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/01/2018
ms.locfileid: "25354001"
---
# <a name="migrate-lync-room-system-lrs-devices-to-skype-room-system-v2"></a><span data-ttu-id="e4086-103">Migrar dispositivos de sistema de sala do Lync (LRS) para o sistema de sala Skype v2</span><span class="sxs-lookup"><span data-stu-id="e4086-103">Migrate Lync Room System (LRS) devices to Skype Room System v2</span></span> 
<span data-ttu-id="e4086-104">Dispositivos de sistema de sala do Lync (LRS) com o software do sistema de sala do Skype versão 1 (v1 SRS) alcançará o [fim do suporte em 9 de outubro de 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span><span class="sxs-lookup"><span data-stu-id="e4086-104">Lync Room System (LRS) devices with Skype Room System Version 1 (SRS v1) software will reach [end of support on October 9, 2018](https://support.microsoft.com/en-us/help/4043450/products-reaching-end-of-support-for-2018).</span></span> <span data-ttu-id="e4086-105">Isso significa que o software do Skype sala sistemas v1 não obterá quaisquer atualizações de produto ou correções após essa data.</span><span class="sxs-lookup"><span data-stu-id="e4086-105">This means Skype Room Systems v1 software will not get any product updates or fixes after this date.</span></span> <span data-ttu-id="e4086-106">Clientes com dispositivos de sistema do Lync sala usando o software do sistema de sala Skype v1 recomenda-se para atualizar seus dispositivos para o sistema de sala Skype v2 (versão 2 SRS).</span><span class="sxs-lookup"><span data-stu-id="e4086-106">Customers with Lync Room System devices using Skype Room System v1 software are advised to upgrade their devices to Skype Room System version 2 (SRS v2).</span></span>

<span data-ttu-id="e4086-107">Software Skype sala sistema versão 2 (v2 SRS) funciona com Microsoft Teams além do Skype para Business Server e Online services para reuniões e chamadas em todos os dispositivos do SRS v2 suportados.</span><span class="sxs-lookup"><span data-stu-id="e4086-107">Skype Room System Version 2 (SRS v2) software works with Microsoft Teams in addition to Skype for Business Server and Online services for meetings and calling on all SRS v2 supported devices.</span></span>

<span data-ttu-id="e4086-108">Seus dispositivos existentes **podem** continuam a funcionar após o término do oferecem suporte de software do sistema de sala Skype v1 até que este software acessa um bug de software que precisa Microsoft para liberar uma correção, ou pode ter um caso onde um protocolo de comunicação existente é usado pelo sistema de sala do Skype v1 software altera ou não é mais suportado.</span><span class="sxs-lookup"><span data-stu-id="e4086-108">Your existing devices **may** continue to work after the end of Skype Room System v1 software suppor until this software hits a software bug that needs Microsoft to release a fix, or may have a case where an existing communication protocol used by Skype Room System v1 software changes or is no longer supported.</span></span> <span data-ttu-id="e4086-109">Uma dessas alterações conhecida é preterir de TLS 1.0 / 1.1 no Microsoft Office 365.</span><span class="sxs-lookup"><span data-stu-id="e4086-109">One such known change is deprecation of TLS 1.0/ 1.1 in Microsoft Office 365.</span></span> <span data-ttu-id="e4086-110">Você pode aprender mais sobre [Preparando para TLS 1.0/1.1 preterir](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span><span class="sxs-lookup"><span data-stu-id="e4086-110">You can learn more about [Preparing for TLS 1.0/1.1 Deprecation](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/bc-p/223608).</span></span>  

## <a name="which-devices-are-affected"></a><span data-ttu-id="e4086-111">Quais dispositivos são afetados?</span><span class="sxs-lookup"><span data-stu-id="e4086-111">Which devices are affected?</span></span>
<span data-ttu-id="e4086-112">Aqui está uma lista dos dispositivos que são afetados por essa alteração:</span><span class="sxs-lookup"><span data-stu-id="e4086-112">Here is the list of the devices that are affected by this change:</span></span>
- [<span data-ttu-id="e4086-113">Sistemas de sala inteligentes</span><span class="sxs-lookup"><span data-stu-id="e4086-113">SMART Room systems</span></span>](https://smartkapp.com/products/smart-room-systems)
- [<span data-ttu-id="e4086-114">Crestron RL2</span><span class="sxs-lookup"><span data-stu-id="e4086-114">Crestron RL2</span></span>](https://www.crestron.com/en-US/Products/Featured-Solutions/Crestron-RL-2)
- [<span data-ttu-id="e4086-115">Polycom CX8000</span><span class="sxs-lookup"><span data-stu-id="e4086-115">Polycom CX8000</span></span>](http://www.polycom.com/products-services/products-for-microsoft/skype-for-business/cx8000.html)
- <span data-ttu-id="e4086-116">Crestron RL</span><span class="sxs-lookup"><span data-stu-id="e4086-116">Crestron RL</span></span>

## <a name="upgrade-options"></a><span data-ttu-id="e4086-117">Opções de atualização</span><span class="sxs-lookup"><span data-stu-id="e4086-117">Upgrade options</span></span>
<span data-ttu-id="e4086-118">Há várias opções para atualizar o Lync sistemas de sala para a próxima geração de sistemas de sala Skype (SRS v2).</span><span class="sxs-lookup"><span data-stu-id="e4086-118">There are multiple options for upgrading Lync Room Systems to the next generation of Skype Room Systems (SRS v2).</span></span>

### <a name="crestron-hardware-trade-in-program"></a><span data-ttu-id="e4086-119">Programa de trade-in de hardware Crestron</span><span class="sxs-lookup"><span data-stu-id="e4086-119">Crestron hardware Trade-in program</span></span>
<span data-ttu-id="e4086-120">Crestron fornecerá uma atualização para o [sistema Crestron SR](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) ou equivalente para todos os clientes do sistema de sala do Lync não-Crestron.</span><span class="sxs-lookup"><span data-stu-id="e4086-120">Crestron will provide an upgrade to the [Crestron SR system](https://www.crestron.com/en-us/products/featured-solutions/crestron-sr) or equivalent for all Non-Crestron Lync Room System customers.</span></span> <span data-ttu-id="e4086-121">Ver os detalhes deste programa [aqui](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, --> [email](mailto:lrsupgrade@crestron.com) suporte Crestron LRS.</span><span class="sxs-lookup"><span data-stu-id="e4086-121">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="crestron-rl2-to-rl3"></a><span data-ttu-id="e4086-122">Crestron RL2 para RL3</span><span class="sxs-lookup"><span data-stu-id="e4086-122">Crestron RL2 to RL3</span></span>
<span data-ttu-id="e4086-123">Os clientes existentes do Crestron RL2 (também conhecido como Crestron RL200) podem adquirir um pacote de atualização para atualizar RL2 atual para RL3 usando um para um custo mínimo por dispositivo.</span><span class="sxs-lookup"><span data-stu-id="e4086-123">Existing Crestron RL2 (also referred to as Crestron RL200) customers can acquire an upgrade package to upgrade current RL2 to RL3 using a for a minimal cost per device.</span></span> <span data-ttu-id="e4086-124">Ver os detalhes deste programa [aqui](https://support.crestron.com/app/answers/answer_view/a_id/1000220) ou <!-- For details, --> [email](mailto:lrsupgrade@crestron.com) suporte Crestron LRS.</span><span class="sxs-lookup"><span data-stu-id="e4086-124">See details of this program [here](https://support.crestron.com/app/answers/answer_view/a_id/1000220) or <!-- For details, -->[email](mailto:lrsupgrade@crestron.com) Crestron LRS support.</span></span>  


### <a name="smart-room-systems-upgrade--diy-program"></a><span data-ttu-id="e4086-125">Sistemas de sala inteligente programa atualização & DIY</span><span class="sxs-lookup"><span data-stu-id="e4086-125">SMART Room Systems upgrade & DIY program</span></span>
<span data-ttu-id="e4086-126">Para clientes inteligentes LRS, além de Crestron programa de trade-in de hardware, o Microsoft e inteligente também estão trabalhando em fornecendo uma solução para atualizar para o sistema de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="e4086-126">For SMART LRS customers, apart from Crestron hardware trade-in program, Microsoft and SMART are also working on providing a solution to upgrade to Skype Room System v2.</span></span> <span data-ttu-id="e4086-127">Microsoft também está testando uma solução DIY para clientes inteligentes LRS.</span><span class="sxs-lookup"><span data-stu-id="e4086-127">Microsoft is also testing a DIY solution for SMART LRS customers.</span></span> <span data-ttu-id="e4086-128">Para obter mais detalhes desses programas serão fornecidas nesta página em de 2018 inicial de outubro.</span><span class="sxs-lookup"><span data-stu-id="e4086-128">More details of these programs will be provided on this page in early October 2018.</span></span> <span data-ttu-id="e4086-129">Verifique se a procurar atualizações nessas opções de atualização.</span><span class="sxs-lookup"><span data-stu-id="e4086-129">Please make sure to check back for updates on these upgrade options.</span></span>

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

## <a name="what-should-you-do"></a><span data-ttu-id="e4086-130">O que você deve fazer?</span><span class="sxs-lookup"><span data-stu-id="e4086-130">What should you do?</span></span>
<span data-ttu-id="e4086-131">Recomendamos que você planeja atualizar dispositivos de sistema do Lync sala para sistemas de sala Skype v2 antes de preterir TLS 1.0/1.1 usando as opções de atualização mencionadas acima.</span><span class="sxs-lookup"><span data-stu-id="e4086-131">We recommend you plan to update Lync Room System devices to Skype Room Systems v2 before TLS 1.0/1.1 deprecation using upgrade options mentioned above.</span></span> <span data-ttu-id="e4086-132">Além disso, você também pode considerar a substituição de dispositivos existentes com novos dispositivos certificados para o SRS v2.</span><span class="sxs-lookup"><span data-stu-id="e4086-132">Additionally, you may also consider replacing existing devices with new devices certified for SRS v2.</span></span> <span data-ttu-id="e4086-133">Consulte [dispositivos de sala](https://aka.ms/roomdevices) para obter detalhes e também dar uma olhada em [sistemas de sala Skype v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span><span class="sxs-lookup"><span data-stu-id="e4086-133">See [Room devices](https://aka.ms/roomdevices) for details and also take a look at [Skype Room Systems v2 requirements](https://docs.microsoft.com/en-us/skypeforbusiness/plan-your-deployment/clients-and-devices/requirements).</span></span>  

> [!NOTE]
> <span data-ttu-id="e4086-134">Funcionalidade de toque e whiteboard ainda não é suportada no sistema de sala Skype v2.</span><span class="sxs-lookup"><span data-stu-id="e4086-134">Touch and whiteboard functionality is not yet supported in Skype Room System v2.</span></span> <span data-ttu-id="e4086-135">Suporte de toque e quadro de comunicações está no registro acumulado para o sistema de sala Skype v2 e será adicionado em CY2019 de S1.</span><span class="sxs-lookup"><span data-stu-id="e4086-135">Touch and whiteboard support is in the backlog for Skype Room System v2 and will be added in H1 CY2019.</span></span>
