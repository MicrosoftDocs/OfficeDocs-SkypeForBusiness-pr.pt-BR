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
- M365-voice
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.callqueues.overview"
ms.custom:
- Phone System
description: Saiba como configurar o sistema telefônico para filas de chamadas em nuvem com o Microsoft Teams.
ms.openlocfilehash: fc7cc9558036d30d388a279ac155fe6382e611a8
ms.sourcegitcommit: 100ba1409bf0af58e4430877c1d29622d793d23f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2019
ms.locfileid: "37925092"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="bb3e3-103">Criar uma fila de chamada do Cloud</span><span class="sxs-lookup"><span data-stu-id="bb3e3-103">Create a Cloud call queue</span></span>

<span data-ttu-id="bb3e3-104">As filas de chamadas na nuvem podem fornecer:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="bb3e3-105">Uma mensagem de saudação.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-105">A greeting message.</span></span>
- <span data-ttu-id="bb3e3-106">Música enquanto as pessoas estão aguardando a espera.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="bb3e3-107">Redirecionar chamadas para agentes de chamada em listas de distribuição habilitadas por email e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="bb3e3-108">Configuração de parâmetros diferentes, como tamanho máximo da fila, tempo limite e opções de tratamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="bb3e3-109">Você pode associar um número de telefone a uma fila de chamadas usando uma [conta de recurso](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-109">You would associate a phone number to a call queue using a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="bb3e3-110">Uma fila de chamadas pode ser discada diretamente ou acessada por uma seleção em um atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-110">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="bb3e3-111">O chamador ouve música enquanto ela está em espera, e a chamada se conecta aos agentes de chamada em ordem *primeiro a entrar, primeiro a sair* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-111">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="bb3e3-112">Todas as chamadas na fila são enviadas aos agentes por um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-112">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="bb3e3-113">Com o roteamento de atendedor, a primeira chamada na fila toca todos os agentes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-113">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="bb3e3-114">Com o roteamento serial, a primeira chamada na fila toca todos os agentes de chamada um por vez.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-114">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="bb3e3-115">Com o rodízio, o roteamento de chamadas recebidas é balanceado para que cada agente de chamadas obtenha o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-115">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb3e3-116">Os agentes de chamada que estiverem **offline**, definiram sua presença como **não incomodar** ou recusaram a fila de chamadas não receberão chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-116">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="bb3e3-117">Apenas uma notificação de chamada de entrada (para a chamada no início da fila) ao mesmo tempo vai para os agentes de chamada.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-117">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="bb3e3-118">Depois que um agente aceitar a chamada, a próxima chamada de entrada na fila começará a tocar nos agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-118">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e3-119">Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-119">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="bb3e3-120">Etapa 1-Introdução</span><span class="sxs-lookup"><span data-stu-id="bb3e3-120">Step 1 — Get started</span></span>

<span data-ttu-id="bb3e3-121">Para começar a usar filas de chamadas, é importante lembrar-se de algumas coisas:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-121">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="bb3e3-122">Uma fila de chamadas é necessária para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-122">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="bb3e3-123">Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter detalhes sobre contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-123">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="bb3e3-124">Ao atribuir um número de telefone a uma conta de recurso, agora você pode usar a [licença de usuário virtual](teams-add-on-licensing/virtual-user.md)de sistema telefônico sem custo.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-124">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="bb3e3-125">O sistema telefônico permite números de telefone no nível organizacional para uso com serviços de atendedor automático de baixo custo e fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-125">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e3-126">Os números do serviço de roteamento direto para filas de chamadas têm suporte somente para usuários e agentes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-126">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e3-127">Para redirecionar chamadas para pessoas em sua organização que estão online, elas devem ter uma licença do **sistema de telefonia** e estar habilitadas para o Enterprise Voice ou ter planos de chamadas do Office 365.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-127">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="bb3e3-128">Consulte [atribuir licenças do Skype for Business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-128">See [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="bb3e3-129">Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="bb3e3-130">Por exemplo, executar:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="bb3e3-130">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="bb3e3-131">Para saber mais sobre os planos de chamada do Office 365, consulte [sistema telefônico e planos de chamada](calling-plan-landing-page.md) e [planos de chamadas do Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-131">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="bb3e3-132">Você só pode atribuir filas de chamadas em nuvem e números de telefone de serviço de chamada gratuita que você recebeu no **centro de administração do Microsoft Teams** ou transferido de outro provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-132">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="bb3e3-133">Créditos de comunicações são necessários para números de serviço de chamada gratuita.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-133">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb3e3-134">Os números de telefone do usuário (assinante) não podem ser atribuídos a filas de chamadas-somente números de telefone de serviço de chamada tarifada ou de chamada gratuita podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="bb3e3-135">Os seguintes clientes têm suporte para agentes de chamada associados a uma fila de chamadas em nuvem:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-135">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="bb3e3-136">Cliente de área de trabalho do Skype for Business 2016 (versões de 32 bits e de 64 bits)</span><span class="sxs-lookup"><span data-stu-id="bb3e3-136">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="bb3e3-137">Lync desktop cliente 2013 (versões de 32 bits e de 64 bits)</span><span class="sxs-lookup"><span data-stu-id="bb3e3-137">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="bb3e3-138">Todos os modelos de telefone IP com suporte para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-138">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="bb3e3-139">Consulte [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-139">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="bb3e3-140">Cliente Skype for Business para Mac (versão 16.8.196 e posterior)</span><span class="sxs-lookup"><span data-stu-id="bb3e3-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="bb3e3-141">Cliente Skype for Business Android (versão 6.16.0.9 e posterior)</span><span class="sxs-lookup"><span data-stu-id="bb3e3-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="bb3e3-142">Cliente Skype for Business (versão 6.16.0 e posterior) do iPhone</span><span class="sxs-lookup"><span data-stu-id="bb3e3-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="bb3e3-143">Cliente Skype for Business para iPad (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="bb3e3-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="bb3e3-144">Microsoft Teams Windows Client (versões de 32 bits e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="bb3e3-144">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="bb3e3-145">Cliente Mac do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bb3e3-145">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="bb3e3-146">Aplicativo iPhone do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bb3e3-146">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="bb3e3-147">Aplicativo Android do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bb3e3-147">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb3e3-148">As filas de chamadas atribuídas a um número de roteamento direto não oferecerão suporte para clientes do Skype for Business, clientes do Lync ou telefones IP do Skype for Business como agentes.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-148">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span> 

## <a name="step-2--getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="bb3e3-149">Etapa 2: obter ou transferir números de telefone de serviço de chamada tarifada ou gratuita</span><span class="sxs-lookup"><span data-stu-id="bb3e3-149">Step 2 — Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="bb3e3-150">Antes de criar e configurar suas filas de chamadas, você precisa obter ou transferir seus números de serviço de chamada tarifada ou chamada gratuitas existentes.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-150">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="bb3e3-151">Depois de obter os números\*\*\*\* > **de telefone de** > serviço de chamada tarifada ou gratuita, eles aparecerão no centro de administração do centro > de **Administração do Microsoft Teams\*\*\*\*, e**o **tipo de número** será listado como **Serviço — chamada gratuita**.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Legacy Portal** > **Voice** > **Phone numbers**, and the **Number type** will be listed as **Service — Toll-Free**.</span></span> <span data-ttu-id="bb3e3-152">Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e3-153">Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter números de serviço.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="bb3e3-154">Vá para [gerenciar números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez de ver como fazer isso de fora dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="bb3e3-155">Ao configurar vários atendedores automáticos, você pode atribuir apenas um número de telefone à conta principal do recurso do atendedor automático, que pode direcionar os chamadores para suas filas de chamadas ou atendedores automáticos aninhados.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-155">When setting up multiple auto attendants you may only assign a phone number to the main auto attendant's resource account, which can direct callers to your call queues or nested auto attendants.</span></span> <span data-ttu-id="bb3e3-156">Nessas situações, crie todos os atendedores automáticos e filas de chamadas em seu sistema sem atribuir opções de discagem e, em seguida, edite as configurações mais tarde.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-156">In those situations, you create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="bb3e3-157">Isso é necessário porque você não tem permissão para criar uma opção de vinculação a uma fila de chamadas ou atendedor automático que ainda não existe.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-157">This is necessary because you aren't allowed to create an option linking to a call queue or auto attendant that does not yet exist.</span></span>

## <a name="step-3--create-a-new-call-queue"></a><span data-ttu-id="bb3e3-158">Etapa 3 — criar uma nova fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="bb3e3-158">Step 3 — Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="bb3e3-159">Todas as filas de chamadas são necessárias para ter uma [conta de recurso](manage-resource-accounts.md)associada.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-159">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="bb3e3-160">Você deve criar a conta do recurso primeiro, então você pode associá-la à fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-160">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="bb3e3-161">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="bb3e3-161">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="bb3e3-162">No **centro de administração do Microsoft Teams**,**filas de chamadas**de **voz** > e clique em **+ Adicionar novo**:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-162">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="bb3e3-163">Definir o nome de exibição da fila de chamadas e a conta do recurso</span><span class="sxs-lookup"><span data-stu-id="bb3e3-163">Set the call queue display name and resource account</span></span>

![Captura de tela de uma nova fila de chamadas com textos explicativos numerados](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="bb3e3-165">![Ícone do número 1, fazendo referência a um texto explicativo no](media/sfbcallout1.png)
**nome** anterior da captura de tela Insira um nome de exibição descritivo para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-165">![Icon of the number 1, referencing a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="bb3e3-166">Esse nome é necessário e pode conter até 64 caracteres, incluindo espaços.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-166">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="bb3e3-167">Esse nome será exibido na notificação para a chamada recebida.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-167">This name is displayed in the notification for the incoming call.</span></span>

* * *

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="bb3e3-169">**Adicionar contas** Selecione uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-169">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="bb3e3-170">A conta do recurso pode ou não estar associada a um número de telefone de chamada tarifada ou gratuita do serviço para a fila de chamadas, mas cada fila de chamadas exige uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-170">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="bb3e3-171">Se não houver uma lista, você precisará obter números de serviço e atribuí-los a uma conta de recurso antes de poder criar esta fila de chamadas, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-171">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="bb3e3-172">Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-172">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="bb3e3-173">Crie uma conta de recurso, conforme descrito em [gerenciar contas de recursos no Teams](manage-resource-accounts.md) , se quiser que a fila de chamadas tenha um número de telefone associado.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-173">You create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="bb3e3-174">Se quiser ou precisar atribuir um **domínio** , você pode fazê-lo atribuindo-o à conta do recurso para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-174">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="bb3e3-175">Definir a saudação e a música jogadas enquanto em espera</span><span class="sxs-lookup"><span data-stu-id="bb3e3-175">Set the greeting and music played while on hold</span></span>

![captura de tela das opções de saudação e música com textos explicativos numerados](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="bb3e3-178">A **saudação** é opcional.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-178">**Greeting** is optional.</span></span> <span data-ttu-id="bb3e3-179">Esta é a saudação que é reproduzida para as pessoas que ligarem para o número da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-179">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="bb3e3-180">Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. WMA).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-180">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="bb3e3-182">**Música em espera** Você pode usar a música padrão em espera fornecida com a fila de chamadas ou pode carregar um arquivo de áudio nos formatos. wav, MP3 ou. WMA para usar como sua música personalizada em espera.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-182">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="bb3e3-183">Selecionar as opções de atendimento de chamada</span><span class="sxs-lookup"><span data-stu-id="bb3e3-183">Select the call answering options</span></span>

![Captura de tela das opções de atendimento de chamadas, com textos explicativos numerados](media/5d249515-d532-4af2-90da-011404028b89.png)

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="bb3e3-186">Você pode selecionar até 200 agentes de chamada que pertencem a qualquer uma das seguintes listas de endereçamento ou grupos:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-186">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="bb3e3-187">Grupo do Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e3-187">Office 365 group</span></span>
- <span data-ttu-id="bb3e3-188">Grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="bb3e3-188">Security group</span></span>
- <span data-ttu-id="bb3e3-189">Lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="bb3e3-189">Distribution list</span></span>

<span data-ttu-id="bb3e3-190">Os agentes de chamada selecionados devem ser um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-190">Call agents selected must be one of the following:</span></span> 

- <span data-ttu-id="bb3e3-191">Usuários online com uma licença do sistema telefônico e Enterprise Voice habilitadas</span><span class="sxs-lookup"><span data-stu-id="bb3e3-191">Online users with a Phone System license and Enterprise Voice enabled</span></span> 
- <span data-ttu-id="bb3e3-192">Usuários online com um plano de chamada</span><span class="sxs-lookup"><span data-stu-id="bb3e3-192">Online users with a  Calling Plan</span></span>
- <span data-ttu-id="bb3e3-193">Usuários locais do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="bb3e3-193">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="bb3e3-194">Isso também se aplica se você quiser redirecionar chamadas para as pessoas em sua organização que estão online.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-194">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="bb3e3-195">Esses indivíduos devem ter uma licença do **sistema telefônico** e o Enterprise Voice habilitados **ou** ter um plano de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-195">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="bb3e3-196">Para obter mais informações, consulte [atribuir licenças do Skype for Business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [atribuir licenças do Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)ou [qual plano de chamada é ideal para você?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="bb3e3-196">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="bb3e3-197">Para habilitar um agente para Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-197">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="bb3e3-198">Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="bb3e3-198">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="bb3e3-199">Usuários com uma licença do **sistema telefônico** ou um plano de chamadas que são adicionados a um grupo do Office 365; uma lista de distribuição habilitada para email; ou um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-199">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="bb3e3-200">Pode levar até três horas para um agente recém-adicionado em uma lista de distribuição ou um grupo de segurança para começar a receber chamadas de uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-200">It might take up to three hours for a newly added agent in a distribution list, or a security group, to start receiving calls from a call queue.</span></span> <span data-ttu-id="bb3e3-201">Uma lista de distribuição ou um grupo de segurança recém-criado pode levar até 48 horas para se tornar disponível para ser usado com filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-201">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="bb3e3-202">Os grupos do Office 365 recém-criados estão disponíveis quase que imediatamente.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-202">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="bb3e3-203">Se seus agentes estiverem usando o aplicativo Microsoft Teams para fazer chamadas na fila de chamadas, eles precisarão estar no modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-203">If your agents are using Microsoft Teams App to take call queue calls, they need to be in TeamsOnly mode.</span></span>

![Captura de tela do painel Adicionar agentes de chamada](media/skype-for-business-add-agents-to-call-queue.png)

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="bb3e3-206">**Método de roteamento** Você pode escolher o **atendedor**, a **série**ou o **rodízio** para o método de distribuição da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-206">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="bb3e3-207">Todas as filas de chamadas novas e existentes terão o roteamento de atendedor selecionado por padrão.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-207">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="bb3e3-208">Quando o roteamento do atendente é usado, a primeira chamada na fila toca em todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-208">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="bb3e3-209">O primeiro agente de chamadas para atender a chamada recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-209">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="bb3e3-210">O **Roteamento de atendedor** faz com que a primeira chamada na fila toque em todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-210">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="bb3e3-211">O primeiro agente de chamadas para atender a chamada recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-211">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="bb3e3-212">**Roteamento serial** as chamadas recebidas para os agentes de chamada um por um, começando do início da lista de agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-212">**Serial routing** incoming calls ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="bb3e3-213">Os agentes não podem ser ordenados na lista agente de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-213">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="bb3e3-214">Se um agente ignorar ou não atender a chamada, a chamada tocará o próximo agente na lista e experimentará todos os agentes, um por vez, até que ele seja retirado ou expire em espera na fila.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-214">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="bb3e3-215">O roteamento serial vai ignorar os agentes que estiverem **offline**, definir sua presença como **não incomodar** **ou optar por** não receber chamadas desta fila.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-215">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="bb3e3-216">O direcionamento de **rodízio** equilibra a circulação de chamadas de entrada para que cada agente de chamadas obtenha o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-216">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="bb3e3-217">Isso pode ser desejável em um ambiente de vendas de entrada para garantir uma oportunidade igual entre todos os agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-217">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="bb3e3-218">Selecionar uma opção de cancelamento de agente</span><span class="sxs-lookup"><span data-stu-id="bb3e3-218">Select an agent opt-out option</span></span>

![Captura de tela de opções de cancelamento de agente com textos explicativos numerados](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="bb3e3-221">O **agente pode optar por não receber chamadas** Você pode optar por permitir que os agentes da fila de chamadas optem por fazer chamadas de uma determinada fila habilitando esta opção.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-221">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="bb3e3-222">Habilitar essa opção permite que todos os agentes nesta fila sejam iniciados ou parem de receber chamadas desta fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-222">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="bb3e3-223">Você pode revogar o privilégio de cancelamento de agente a qualquer momento desmarcando a caixa de seleção, fazendo com que os agentes se tornem automaticamente para esta fila de novo (a configuração padrão para todos os agentes).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-223">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="bb3e3-224">Para acessar a opção de recusa, os agentes podem fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-224">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="bb3e3-225">Abra **as opções** no cliente do Skype for Business da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-225">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="bb3e3-226">Na guia **encaminhamento de chamadas** , clique no link **Editar configurações online** .</span><span class="sxs-lookup"><span data-stu-id="bb3e3-226">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="bb3e3-227">Na página Configurações do usuário, clique em **filas de chamadas**e desmarque as caixas de seleção das filas das quais deseja recusar.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-227">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt-out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="bb3e3-228">Os agentes que usam aplicativos ou pontos de extremidade diferentes da área de trabalho do Skype for Business podem acessar a opção de cancelamento no portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings)de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-228">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="bb3e3-229">![Ícone do número 2, fazendo referência a um texto explicativo na](media/sfbcallout2.png)
**configuração de alerta** anterior do agente de captura de tela</span><span class="sxs-lookup"><span data-stu-id="bb3e3-229">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="bb3e3-230">Isso define a duração de um agente sendo notificado sobre uma chamada antes que os métodos de roteamento serial ou Round Robin se movam para o próximo agente.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-230">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="bb3e3-231">A configuração padrão é 30 segundos, mas pode ser definida por até 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-231">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="bb3e3-232">Configurar o estouro de chamadas e as opções de controle de tempo limite</span><span class="sxs-lookup"><span data-stu-id="bb3e3-232">Set the call overflow and timeout handling options</span></span>

![Captura de tela das opções de tratamento de estouro com textos explicativos numerados](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="bb3e3-235">**Máximo de chamadas na fila** Use esta configuração para definir o número máximo de chamadas que podem esperar na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-235">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="bb3e3-236">O padrão é 50, mas pode variar de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-236">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="bb3e3-237">Quando esse limite for atingido, a chamada será manipulada da maneira que você definiu **quando a configuração número máximo de chamadas for atingida** abaixo.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-237">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="bb3e3-239">**Quando o número máximo de chamadas for atingido** Quando a fila de chamadas atinge seu tamanho máximo (definido usando o **máximo de chamadas na** configuração de fila), você pode escolher o que acontece com as novas chamadas recebidas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-239">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="bb3e3-240">**Desconectar** A chamada está desconectada.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-240">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="bb3e3-241">**Redirecionar para** Ao escolher essa opção, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-241">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="bb3e3-242">**Pessoa em sua empresa** Um usuário online com uma licença do **sistema de telefonia** e estar habilitado para o Enterprise Voice ou ter um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-242">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="bb3e3-243">Você pode configurá-lo para que o chamador possa ser enviado para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-243">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="bb3e3-244">Para fazer isso, selecione uma **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-244">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="bb3e3-245">Para saber mais sobre as licenças necessárias para correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-245">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="bb3e3-246">**Aplicativo de voz** Selecione o nome de uma conta de recurso associada a uma fila de chamadas ou atendedor automático que já foi criado.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-246">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![Ícone do número 3, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout3.png)

<span data-ttu-id="bb3e3-248">**Tempo limite de chamada: tempo máximo de espera** Você também pode decidir quanto tempo uma chamada pode ficar em espera na fila antes de expirar e precisar ser redirecionada ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-248">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="bb3e3-249">O local em que é redirecionado é baseado em como você define a configuração **quando uma chamada atinge o tempo limite** .</span><span class="sxs-lookup"><span data-stu-id="bb3e3-249">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="bb3e3-250">Você pode definir uma hora de 0 a 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-250">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="bb3e3-251">O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-251">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="bb3e3-252">Isso permite que você manipule o fluxo de chamadas com granularidade mais fina.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-252">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="bb3e3-253">Por exemplo, você pode especificar que as chamadas não atendidas por um agente dentro de 30 segundos vão para um atendedor automático de pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-253">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Ícone do número 4, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout4.png)

<span data-ttu-id="bb3e3-255">**Quando a chamada** expira Quando a chamada atingir o limite que você definiu no **tempo em que uma chamada pode esperar na configuração de fila** , você pode escolher o que acontecerá com esta chamada:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-255">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="bb3e3-256">**Desconectar** A chamada está desconectada.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-256">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="bb3e3-257">**Redirecionar esta chamada para** Ao escolher esta opção, você tem estas opções:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-257">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="bb3e3-258">**Pessoa em sua empresa** Um usuário online com uma licença do **sistema de telefonia** e estar habilitado para o Enterprise Voice ou ter planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-258">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="bb3e3-259">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-259">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="bb3e3-260">Para fazer isso, selecione uma **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-260">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="bb3e3-261">Para saber mais sobre o licenciamento necessário para correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-261">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="bb3e3-262">**Aplicativo de voz** Selecione o nome de uma conta de recurso associada a uma fila de chamadas ou atendedor automático que já foi criado.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-262">**Voice application** Select the name of a resource account associated with either a call queue or auto attendant that has already been created.</span></span>

## <a name="change-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="bb3e3-263">Alterar a identificação de chamada de um usuário para chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="bb3e3-263">Change a user's Caller ID for outbound calls</span></span>

<span data-ttu-id="bb3e3-264">Você pode proteger a identidade de um usuário alterando a identificação de chamadas para chamadas de saída para uma fila de chamadas, atendedor automático ou qualquer número de serviço, em vez disso, usando o cmdlet **New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="bb3e3-264">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="bb3e3-265">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-265">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="bb3e3-266">Em seguida, aplique a política ao usuário usando o cmdlet **Grant-CallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="bb3e3-266">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="bb3e3-267">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-267">To do this, run:</span></span>

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="bb3e3-268">Você pode obter mais informações sobre como definir as configurações de identificação de chamadas em sua organização no artigo [como a identificação de chamadas pode ser usada em sua organização](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="bb3e3-268">You can get more information on how to set caller ID settings in your organization in the article [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="bb3e3-269">Cmdlets da fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="bb3e3-269">Call queue cmdlets</span></span>

<span data-ttu-id="bb3e3-270">Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-270">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="bb3e3-271">Estes são os cmdlets que você usa para gerenciar uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-271">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="bb3e3-272">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="bb3e3-272">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="bb3e3-273">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="bb3e3-273">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="bb3e3-274">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="bb3e3-274">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="bb3e3-275">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="bb3e3-275">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="bb3e3-276">Mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb3e3-276">More about Windows PowerShell</span></span>

- <span data-ttu-id="bb3e3-277">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-277">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="bb3e3-278">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Microsoft Teams com um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-278">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="bb3e3-279">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-279">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="bb3e3-280">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="bb3e3-280">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="bb3e3-281">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e3-281">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="bb3e3-282">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o centro de administração do Microsoft Teams, como, por exemplo, quando você está realizando alterações de vários usuários de uma vez.</span><span class="sxs-lookup"><span data-stu-id="bb3e3-282">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="bb3e3-283">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="bb3e3-283">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="bb3e3-284">Gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb3e3-284">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="bb3e3-285">Configurar seu computador para o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb3e3-285">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="bb3e3-286">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="bb3e3-286">Related topics</span></span>

[<span data-ttu-id="bb3e3-287">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="bb3e3-287">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="bb3e3-288">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="bb3e3-288">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="bb3e3-289">Disponibilidade de Audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="bb3e3-289">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="bb3e3-290">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="bb3e3-290">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
