---
title: Criar uma fila de chamadas
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Saiba como configurar o sistema telefônico para filas de chamadas em nuvem com o Microsoft Teams.
ms.openlocfilehash: b512d674a705c332213456ea639a015e15b51c2d
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394593"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="c0fc8-103">Criar uma fila de chamada do Cloud</span><span class="sxs-lookup"><span data-stu-id="c0fc8-103">Create a Cloud call queue</span></span>

<span data-ttu-id="c0fc8-104">As filas de chamadas na nuvem são um serviço que executa uma saudação para as chamadas dos clientes antes de colocá-las em uma fila durante a pesquisa entre um conjunto predefinido de agentes para atender a essas chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-104">Cloud call queues are a service that play a greeting to customer calls before placing them in a queue while searching among a pre-defined set of agents to answer these calls.</span></span> <span data-ttu-id="c0fc8-105">Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-105">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="c0fc8-106">As filas de chamadas na nuvem podem fornecer:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-106">Cloud call queues can provide:</span></span>
  
- <span data-ttu-id="c0fc8-107">Uma mensagem de saudação.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-107">A greeting message.</span></span>
- <span data-ttu-id="c0fc8-108">Música enquanto as pessoas estão aguardando a espera.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-108">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="c0fc8-109">Redirecionamento de chamadas para agentes de chamada em listas de distribuição habilitadas por email e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-109">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="c0fc8-110">Configurações diferentes parâmetros, como tamanho máximo da fila, tempo limite e opções de tratamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-110">Settings different parameters such as queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="c0fc8-111">Quando alguém liga para um número de telefone associado a uma fila de chamadas por meio de uma [conta de recurso](manage-resource-accounts.md), ele ouvirá primeiro uma saudação (se houver alguma configuração) e, em seguida, será colocado na fila e aguardará o próximo agente de chamada disponível.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-111">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="c0fc8-112">A pessoa que está ligando ouvirá música enquanto eles estiverem em espera, e as chamadas serão oferecidas aos agentes de chamadas em ordem *primeiro a entrar, primeiro a sair* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="c0fc8-112">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="c0fc8-113">Todas as chamadas em espera na fila serão distribuídas usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-113">All calls waiting in the queue will be distributed using one of the following methods:</span></span>
  
- <span data-ttu-id="c0fc8-114">Com o roteamento de atendedor, a primeira chamada na fila tocará todos os agentes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-114">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="c0fc8-115">Com o roteamento serial, a primeira chamada na fila tocará em todos os agentes de chamadas, um por um.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-115">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
- <span data-ttu-id="c0fc8-116">Com o rodízio, o roteamento de chamadas recebidas é balanceado para que cada agente de chamadas obtenha o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-116">With round robin, routing of incoming calls is balanced so that each call agent will get the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0fc8-117">Os agentes de chamada que estiverem **offline**, definiram sua presença como **não incomodar** ou recusaram a fila de chamadas não receberão chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>
  
- <span data-ttu-id="c0fc8-118">Somente uma notificação de chamada de entrada (para a chamada no início da fila) ao mesmo tempo será enviada para os agentes de chamada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="c0fc8-119">Depois que um agente aceitar a chamada, a próxima chamada de entrada na fila começará a tocar nos agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="c0fc8-120">Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="c0fc8-121">Etapa 1-Introdução</span><span class="sxs-lookup"><span data-stu-id="c0fc8-121">Step 1 - Get started</span></span>

<span data-ttu-id="c0fc8-122">Para começar a usar filas de chamadas, é importante lembrar-se de algumas coisas:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-122">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="c0fc8-123">Uma fila de chamadas é necessária para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="c0fc8-124">Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter detalhes sobre contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="c0fc8-125">Se você planeja atribuir um número de telefone à sua fila de chamadas, é necessário adquirir e atribuir uma das seguintes licenças às suas contas de recursos:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-125">If you plan to assign a phone number to your call queue, you need to acquire and assign one of the following licenses to your resource accounts:</span></span>
    - <span data-ttu-id="c0fc8-126">Office 365 Enterprise E1 ou E3 com sistema telefônico adicionado</span><span class="sxs-lookup"><span data-stu-id="c0fc8-126">Office 365 Enterprise E1 or E3 with Phone System added</span></span>
    - <span data-ttu-id="c0fc8-127">Office 365 Enterprise E5 que inclui sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="c0fc8-127">Office 365 Enterprise E5 which includes Phone System</span></span>
- <span data-ttu-id="c0fc8-128">Você só precisa licenciar as contas de recursos com um número de telefone atribuído a ela.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-128">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="c0fc8-129">Em uma fila de chamadas aninhada, você não precisa licenciar o restante das filas de chamadas se elas não tiverem números de telefone associados a elas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-129">In a nested call queue, you do not need to license the rest of the call queues if they do not have phone numbers associated with them.</span></span>

> [!NOTE]
> <span data-ttu-id="c0fc8-130">Os números do serviço de roteamento direto para filas de chamadas têm suporte somente para usuários e agentes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-130">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="c0fc8-131">A Microsoft está trabalhando em um modelo de licenciamento sem custo para aplicativos como atendedores automáticos da nuvem e filas de chamadas, por ora, você precisa usar o modelo de licenciamento do usuário.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-131">Microsoft is working on a cost-free licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!NOTE]
> <span data-ttu-id="c0fc8-132">Para redirecionar chamadas para pessoas em sua organização que estão online, elas devem ter uma licença do **sistema de telefonia** e estar habilitadas para o Enterprise Voice ou ter planos de chamadas do Office 365.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-132">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="c0fc8-133">Consulte [atribuir licenças do Skype for Business](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="c0fc8-133">See  [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="c0fc8-134">Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-134">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c0fc8-135">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c0fc8-135">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="c0fc8-136">Para saber mais sobre os planos de chamada do Office 365, consulte [sistema telefônico e planos de chamada](calling-plan-landing-page.md) e [planos de chamadas do Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c0fc8-136">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="c0fc8-137">Você só pode atribuir números de telefone de serviço de chamada tarifada e gratuita que você recebeu no **centro de administração do Microsoft Teams** ou transferido de outro provedor de serviços para filas de chamadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-137">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Cloud call queues.</span></span> <span data-ttu-id="c0fc8-138">Para obter e usar números de serviço de chamada gratuita, você precisa configurar créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-138">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0fc8-139">Os números de telefone do usuário (assinante) não podem ser atribuídos a filas de chamadas-somente números de telefone de serviço de chamada tarifada ou de chamada gratuita podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-139">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="c0fc8-140">Quando você está distribuindo as chamadas recebidas de uma fila de chamadas em nuvem, esses clientes têm suporte para agentes de chamada:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-140">When you are distributing the incoming calls from a Cloud call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="c0fc8-141">Cliente de área de trabalho do Skype for Business 2016 (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c0fc8-141">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="c0fc8-142">Lync desktop cliente 2013 (versões do 32 e do 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c0fc8-142">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="c0fc8-143">Todos os modelos de telefone IP com suporte para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-143">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="c0fc8-144">Consulte [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="c0fc8-144">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="c0fc8-145">Cliente Skype for Business para Mac (versão 16.8.196 e posterior)</span><span class="sxs-lookup"><span data-stu-id="c0fc8-145">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="c0fc8-146">Cliente Skype for Business Android (versão 6.16.0.9 e posterior)</span><span class="sxs-lookup"><span data-stu-id="c0fc8-146">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="c0fc8-147">Cliente Skype for Business (versão 6.16.0 e posterior) do iPhone</span><span class="sxs-lookup"><span data-stu-id="c0fc8-147">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c0fc8-148">Cliente Skype for Business para iPad (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="c0fc8-148">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="c0fc8-149">Microsoft Teams Windows Client (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="c0fc8-149">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="c0fc8-150">Cliente Mac do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0fc8-150">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="c0fc8-151">Aplicativo iPhone do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0fc8-151">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="c0fc8-152">Aplicativo Android do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0fc8-152">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="c0fc8-153">Etapa 2-como receber ou transferir números de telefone de serviço de chamada tarifada ou gratuita</span><span class="sxs-lookup"><span data-stu-id="c0fc8-153">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="c0fc8-154">Antes de você poder criar e configurar as filas de chamada, será necessário receber ou transferir os números de serviço de chamada gratuita ou tarifada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-154">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="c0fc8-155">Depois de obter os números de\*\*\*\* > telefone de serviço de chamada tarifada ou gratuita, eles aparecerão no centro de **Administração do centro** > de administração do Microsoft Teams para**números de telefone**de**voz** > e o tipo de **número** listado será listado como **serviço-chamada gratuita**.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-155">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Legacy Portal** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="c0fc8-156">Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="c0fc8-156">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c0fc8-157">Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter números de serviço.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-157">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="c0fc8-158">Vá para [gerenciar números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez de ver como fazer isso de fora dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-158">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="c0fc8-159">Se você também estiver configurando atendedores automáticos, talvez seja necessário atribuir apenas um número de telefone à conta principal do recurso do atendedor automático e, em seguida, fazer chamadores diretos para a sua fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-159">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="c0fc8-160">Se esse for o caso, a fila de chamadas precisará ser criada antes que você possa criar uma opção no atendedor automático que seleciona a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-160">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="c0fc8-161">Etapa 3-criar uma nova fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="c0fc8-161">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="c0fc8-162">Todas as filas de chamadas são necessárias para ter uma [conta de recurso](manage-resource-accounts.md)associada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-162">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="c0fc8-163">Você deve criar a conta do recurso primeiro, então você pode associá-la à fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-163">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="c0fc8-164">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c0fc8-164">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="c0fc8-165">No **centro de administração do Microsoft Teams**, filas de**chamadas**de **voz** >  e clique em **+ Adicionar novo**:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-165">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="c0fc8-166">Definir o nome de exibição da fila de chamadas e a conta do recurso</span><span class="sxs-lookup"><span data-stu-id="c0fc8-166">Set the call queue display name and resource account</span></span>

![Captura de tela de uma nova fila de chamadas com textos explicativos numerados](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="c0fc8-168">![Ícone do número 1, fazendo referência a um texto explicativo no](media/sfbcallout1.png)
**nome** anterior da captura de tela Insira um nome de exibição descritivo para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-168">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="c0fc8-169">Isso é necessário e pode conter até 64 caracteres, incluindo espaços.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-169">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="c0fc8-170">Esse nome será exibido na notificação para a chamada recebida.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-170">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="c0fc8-172">**Adicionar contas** Selecione uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-172">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="c0fc8-173">A conta do recurso pode ou não estar associada a um número de telefone de chamada tarifada ou gratuita do serviço para a fila de chamadas, mas cada fila de chamadas exige uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-173">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="c0fc8-174">Se não houver uma lista, você precisará obter números de serviço e atribuí-los a uma conta de recurso antes de poder criar esta fila de chamadas, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-174">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="c0fc8-175">Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="c0fc8-175">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="c0fc8-176">Você precisará criar uma conta de recurso, conforme descrito em [gerenciar contas de recursos no Teams](manage-resource-accounts.md) , se quiser que a fila de chamadas tenha um número de telefone associado.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-176">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="c0fc8-177">Se quiser ou precisar atribuir um **domínio** , você pode fazê-lo atribuindo-o à conta do recurso para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-177">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="c0fc8-178">Definir a saudação e a música jogadas enquanto em espera</span><span class="sxs-lookup"><span data-stu-id="c0fc8-178">Set the greeting and music played while on hold</span></span>

![Captura de tela das opções de saudação e música com textos explicativos numerados](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="c0fc8-181">\*\*\*\* A saudação é opcional.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-181">**Greeting** is optional.</span></span> <span data-ttu-id="c0fc8-182">Esta é a saudação que é reproduzida para as pessoas que ligarem para o número da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-182">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="c0fc8-183">Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. WMA).</span><span class="sxs-lookup"><span data-stu-id="c0fc8-183">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="c0fc8-185">**Música em espera** Você pode usar a música padrão em espera fornecida com a fila de chamadas ou pode carregar um arquivo de áudio nos formatos. wav, MP3 ou. WMA para usar como sua música personalizada em espera.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-185">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="c0fc8-186">Selecionar as opções de atendimento de chamada</span><span class="sxs-lookup"><span data-stu-id="c0fc8-186">Select the call answering options</span></span>

![Captura de tela das opções de atendimento de chamadas, com textos explicativos numerados](media/5d249515-d532-4af2-90da-011404028b89.png)

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="c0fc8-189">Você pode selecionar até 200 agentes de chamada que pertencem a qualquer uma das seguintes listas de endereçamento ou grupos:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-189">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="c0fc8-190">Grupo do Office 365</span><span class="sxs-lookup"><span data-stu-id="c0fc8-190">Office 365 group</span></span>
- <span data-ttu-id="c0fc8-191">Grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="c0fc8-191">Security group</span></span>
- <span data-ttu-id="c0fc8-192">Lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="c0fc8-192">Distribution list</span></span>

<span data-ttu-id="c0fc8-193">Os agentes de chamada \*\*\*\* selecionados devem ser usuários online com uma licença do **sistema telefônico** e o Enterprise Voice habilitados **ou** ter um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-193">Call agents selected must  **either** be online users with a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="c0fc8-194">Isso também se aplica se você quiser redirecionar chamadas para as pessoas em sua organização que estão online.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-194">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="c0fc8-195">Esses indivíduos devem ter uma licença do **sistema telefônico** e o Enterprise Voice habilitados **ou** ter um plano de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-195">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="c0fc8-196">Para obter mais informações, consulte [atribuir licenças do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [atribuir licenças do Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)ou [qual plano de chamada é ideal para você?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="c0fc8-196">For more information see [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="c0fc8-197">Para habilitar um agente para Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-197">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="c0fc8-198">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="c0fc8-198">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="c0fc8-199">Usuários online com uma licença do **sistema telefônico** ou um plano de chamadas que são adicionados a um grupo do Office 365; uma lista de distribuição habilitada para email; ou um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-199">Online users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="c0fc8-200">Pode levar até três horas para um agente recém-adicionado em uma lista de distribuição ou um grupo de segurança para começar a receber chamadas de uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-200">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="c0fc8-201">Uma lista de distribuição ou um grupo de segurança recém-criado pode levar até 48 horas para se tornar disponível para ser usado com filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-201">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="c0fc8-202">Os grupos do Office 365 recém-criados estão disponíveis quase que imediatamente.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-202">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="c0fc8-203">Se seus agentes estiverem usando o aplicativo Microsoft Teams para receber chamadas na fila de chamadas, eles precisarão estar no modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-203">If your agents are using Microsoft Teams App to receive call queue calls, they need to be in TeamsOnly mode.</span></span>

![Captura de tela do painel Adicionar agentes de chamada](media/skype-for-business-add-agents-to-call-queue.png)

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="c0fc8-206">**Método de roteamento** Você pode escolher o **atendedor**, a **série**ou o **rodízio** para o método de distribuição da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-206">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="c0fc8-207">Todas as filas de chamadas novas e existentes terão o roteamento de atendedor selecionado por padrão.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-207">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="c0fc8-208">Quando o roteamento do atendente for usado, a primeira chamada na fila tocará todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-208">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="c0fc8-209">O primeiro agente de chamadas para atender a chamada recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-209">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="c0fc8-210">O **Roteamento** de atendedor faz com que a primeira chamada na fila toque em todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-210">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="c0fc8-211">O primeiro agente de chamadas para atender a chamada recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-211">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="c0fc8-212">**Roteamento em série** as chamadas recebidas entrarão em contato com os agentes, um por um, começando do início da lista de agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-212">**Serial routing** incoming calls will ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="c0fc8-213">Os agentes não podem ser ordenados na lista agente de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-213">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="c0fc8-214">Se um agente ignorar ou não atender a chamada, a chamada tocará o próximo agente na lista e experimentará todos os agentes, um por vez, até que ele seja retirado ou expire em espera na fila.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-214">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="c0fc8-215">O roteamento serial vai ignorar os agentes que estiverem **offline**, definir sua presença como **não incomodar**ou optar por \*\*\*\* não receber chamadas desta fila.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-215">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="c0fc8-216">O direcionamento de **rodízio** equilibra a circulação de chamadas de entrada para que cada agente de chamadas receba o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-216">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="c0fc8-217">Isso pode ser muito desejável em um ambiente de vendas de entrada para garantir uma oportunidade igual entre todos os agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-217">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="c0fc8-218">Selecionar uma opção de cancelamento de agente</span><span class="sxs-lookup"><span data-stu-id="c0fc8-218">Select an agent opt out option</span></span>

![Captura de tela de opções de cancelamento de agente com textos explicativos numerados](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="c0fc8-221">**Opção** de cancelamento de agente Você pode optar por permitir que os agentes da fila de chamadas recusem a fazer chamadas de uma fila específica selecionando a **opção Cancelar**cancelamento do agente.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-221">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="c0fc8-222">Habilitar essa opção permite que todos os agentes nesta fila sejam iniciados ou parem de receber chamadas desta fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-222">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="c0fc8-223">Você pode revogar o privilégio de cancelamento de agente a qualquer momento desmarcando a caixa de seleção, fazendo com que os agentes se tornem automaticamente para esta fila de novo (a configuração padrão para todos os agentes).</span><span class="sxs-lookup"><span data-stu-id="c0fc8-223">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="c0fc8-224">Para acessar a opção de recusa, os agentes podem fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-224">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="c0fc8-225">Abra **as opções** no cliente do Skype for Business da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-225">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="c0fc8-226">Na guia **encaminhamento de chamadas** , clique no link **Editar configurações online** .</span><span class="sxs-lookup"><span data-stu-id="c0fc8-226">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="c0fc8-227">Na página Configurações do usuário, clique em **filas de chamadas**e desmarque as caixas de seleção de todas as filas para as quais deseja sair.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-227">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c0fc8-228">Os agentes que usam aplicativos ou pontos de extremidade diferentes da área de trabalho do Skype for Business podem acessar a opção recusar no [https://aka.ms/cqsettings](https://aka.ms/cqsettings)portal de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-228">Agents using apps or endpoints other than Skype for Business Desktop can access the opt out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="c0fc8-229">![Ícone do número 2, fazendo referência a um texto explicativo na](media/sfbcallout2.png)
**configuração de alerta** anterior do agente de captura de tela</span><span class="sxs-lookup"><span data-stu-id="c0fc8-229">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="c0fc8-230">Isso define a duração de um agente sendo notificado sobre uma chamada antes que os métodos de roteamento serial ou Round Robin se movam para o próximo agente.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-230">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="c0fc8-231">A configuração padrão é 30 segundos, mas pode ser definida por até 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-231">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="c0fc8-232">Configurar o estouro de chamadas e as opções de controle de tempo limite</span><span class="sxs-lookup"><span data-stu-id="c0fc8-232">Set the call overflow and timeout handling options</span></span>

![Captura de tela das opções de tratamento de estouro, com textos explicativos numerados](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="c0fc8-235">**Máximo de chamadas na fila** Use esta configuração para definir o número máximo de chamadas que podem esperar na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-235">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="c0fc8-236">O padrão é 50, mas pode variar de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-236">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="c0fc8-237">Quando esse limite for atingido, a chamada será manipulada da mesma forma que você definiu **quando a configuração número máximo de chamadas é atingida** abaixo.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-237">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="c0fc8-239">**Quando o número máximo de chamadas for atingido** Quando a fila de chamadas atinge seu tamanho máximo (definido usando o **máximo de chamadas na** configuração de fila), você pode escolher o que acontece com as novas chamadas recebidas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-239">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="c0fc8-240">**Desconectar** A chamada será desconectada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-240">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="c0fc8-241">**Redirecionar para** Ao escolher essa opção, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-241">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="c0fc8-242">**Pessoa em sua empresa** Um usuário online com uma licença do **sistema de telefonia** e estar habilitado para o Enterprise Voice ou ter um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-242">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="c0fc8-243">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-243">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="c0fc8-244">Para fazer isso, selecione uma **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-244">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c0fc8-245">Para saber mais sobre o licenciamento necessário para correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c0fc8-245">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="c0fc8-246">**Aplicativo de voz** Selecione o nome de uma fila de chamadas ou o atendedor automático que já foi criado.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-246">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Ícone do número 3, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout3.png)

<span data-ttu-id="c0fc8-248">**Tempo limite de chamada: tempo máximo de espera** Você também pode decidir quanto tempo uma chamada pode ficar em espera na fila antes de expirar e precisar ser redirecionada ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-248">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="c0fc8-249">Onde será redirecionado é baseado em como você define a configuração **quando uma chamada atinge o tempo limite** .</span><span class="sxs-lookup"><span data-stu-id="c0fc8-249">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="c0fc8-250">Você pode definir uma hora de 0 a 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-250">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="c0fc8-251">O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-251">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="c0fc8-252">Isso permite que você manipule o fluxo de chamadas com granularidade mais fina.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-252">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="c0fc8-253">Por exemplo, você pode especificar que as chamadas não atendidas por um agente dentro de 30 segundos vão para um atendedor automático de pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-253">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Ícone do número 4, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout4.png)

<span data-ttu-id="c0fc8-255">**Quando a chamada** expira Quando a chamada atingir o limite que você definiu no **tempo em que uma chamada pode esperar na configuração de fila** , você pode escolher o que acontecerá com esta chamada:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-255">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="c0fc8-256">**Desconectar** A chamada será desconectada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-256">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="c0fc8-257">**Redirecionar esta chamada para** Ao escolher esta opção, você terá as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-257">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="c0fc8-258">**Pessoa em sua empresa** Um usuário online com uma licença do **sistema de telefonia** e estar habilitado para o Enterprise Voice ou ter planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-258">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="c0fc8-259">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-259">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="c0fc8-260">Para fazer isso, selecione uma **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-260">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="c0fc8-261">Para saber mais sobre o licenciamento necessário para correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="c0fc8-261">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="c0fc8-262">**Aplicativo de voz** Selecione o nome de uma fila de chamadas ou o atendedor automático que já foi criado.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-262">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="c0fc8-263">Alterar a identificação de chamada de um usuário para chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="c0fc8-263">Changing a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="c0fc8-264">Você pode proteger a identidade de um usuário alterando a identificação de chamadas para chamadas de saída para uma fila de chamadas, atendedor automático ou qualquer número de serviço, em vez disso, criando uma política usando o cmdlet **New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="c0fc8-264">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="c0fc8-265">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-265">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="c0fc8-266">Em seguida, aplique a política ao usuário usando o cmdlet **Grant-CallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="c0fc8-266">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="c0fc8-267">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-267">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="c0fc8-268">Você pode obter mais informações sobre como fazer alterações nas configurações de identificação de chamada em sua organização no artigo [como a identificação de chamadas pode ser usada em sua organização](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="c0fc8-268">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="c0fc8-269">Cmdlets da fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="c0fc8-269">Call queue cmdlets</span></span>

<span data-ttu-id="c0fc8-270">Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-270">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="c0fc8-271">Estes são os cmdlets necessários para gerenciar uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-271">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="c0fc8-272">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c0fc8-272">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c0fc8-273">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c0fc8-273">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c0fc8-274">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c0fc8-274">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="c0fc8-275">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="c0fc8-275">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="c0fc8-276">Mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0fc8-276">More about Windows PowerShell</span></span>

- <span data-ttu-id="c0fc8-277">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-277">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="c0fc8-278">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Microsoft Teams usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-278">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="c0fc8-279">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-279">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="c0fc8-280">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c0fc8-280">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="c0fc8-281">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="c0fc8-281">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="c0fc8-282">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft Teams, como quando você está definindo alterações de vários usuários de uma vez.</span><span class="sxs-lookup"><span data-stu-id="c0fc8-282">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="c0fc8-283">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="c0fc8-283">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="c0fc8-284">Gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0fc8-284">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="c0fc8-285">Configurar seu computador para o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c0fc8-285">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="c0fc8-286">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="c0fc8-286">Related topics</span></span>

[<span data-ttu-id="c0fc8-287">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="c0fc8-287">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="c0fc8-288">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="c0fc8-288">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="c0fc8-289">Disponibilidade de audioconferência e planos de chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="c0fc8-289">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="c0fc8-290">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="c0fc8-290">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
