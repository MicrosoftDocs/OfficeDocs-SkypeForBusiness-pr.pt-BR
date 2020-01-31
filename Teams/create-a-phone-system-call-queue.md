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
ms.openlocfilehash: c33baabdce8366ed9a4027c0b1e030f54eef543b
ms.sourcegitcommit: 43a17ce6fea3951719b55bfbda03c500cef4816c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41620004"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="24004-103">Criar uma fila de chamada do Cloud</span><span class="sxs-lookup"><span data-stu-id="24004-103">Create a Cloud call queue</span></span>

<span data-ttu-id="24004-104">As filas de chamadas na nuvem podem fornecer:</span><span class="sxs-lookup"><span data-stu-id="24004-104">Cloud call queues can provide:</span></span>

- <span data-ttu-id="24004-105">Uma mensagem de saudação.</span><span class="sxs-lookup"><span data-stu-id="24004-105">A greeting message.</span></span>
- <span data-ttu-id="24004-106">Música enquanto as pessoas estão aguardando a espera.</span><span class="sxs-lookup"><span data-stu-id="24004-106">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="24004-107">Redirecionar chamadas para agentes de chamada em listas de distribuição habilitadas por email e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="24004-107">Redirecting calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="24004-108">Configuração de parâmetros diferentes, como tamanho máximo da fila, tempo limite e opções de tratamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-108">Setting different parameters such as queue maximum size, timeout, and call handling options.</span></span>
- <span data-ttu-id="24004-109">Caixa postal compartilhada para chamadores deixar uma mensagem para uma organização.</span><span class="sxs-lookup"><span data-stu-id="24004-109">Shared voicemail for callers to leave a message for an organization.</span></span>

<span data-ttu-id="24004-110">Você não associa diretamente um número de telefone a uma fila de chamadas, em vez disso, o número de telefone está associado a uma [conta do recurso](manage-resource-accounts.md).</span><span class="sxs-lookup"><span data-stu-id="24004-110">You don't directly associate a phone number to a call queue, instead the phone number is associated to a [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="24004-111">Uma fila de chamadas pode ser discada diretamente ou acessada por uma seleção em um atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="24004-111">A call queue can be dialed directly or accessed by a selection on an auto attendant.</span></span>

<span data-ttu-id="24004-112">O chamador ouve música enquanto ela está em espera, e a chamada se conecta aos agentes de chamada em ordem *primeiro a entrar, primeiro a sair* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="24004-112">The caller hears music while they are on hold, and the call connects to the call agents in *First In, First Out* (FIFO) order.</span></span>

<span data-ttu-id="24004-113">Todas as chamadas na fila são enviadas aos agentes por um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="24004-113">All calls in the queue are sent to agents by one of the following methods:</span></span>

- <span data-ttu-id="24004-114">Com o roteamento de atendedor, a primeira chamada na fila toca todos os agentes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="24004-114">With attendant routing, the first call in the queue  rings all agents at the same time.</span></span>
- <span data-ttu-id="24004-115">Com o roteamento serial, a primeira chamada na fila toca todos os agentes de chamada um por vez.</span><span class="sxs-lookup"><span data-stu-id="24004-115">With serial routing, the first call in the queue rings all call agents one by one.</span></span>
- <span data-ttu-id="24004-116">Com o rodízio, o roteamento de chamadas recebidas é balanceado para que cada agente de chamadas obtenha o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="24004-116">With round robin, routing of incoming calls is balanced so that each call agent gets the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="24004-117">Os agentes de chamada que estiverem **offline**, definiram sua presença como **não incomodar** ou recusaram a fila de chamadas não receberão chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue will not recieve calls.</span></span>

- <span data-ttu-id="24004-118">Apenas uma notificação de chamada de entrada (para a chamada no início da fila) ao mesmo tempo vai para os agentes de chamada.</span><span class="sxs-lookup"><span data-stu-id="24004-118">Only one incoming call notification (for the call at the head of the queue) at a time goes to the call agents.</span></span>
- <span data-ttu-id="24004-119">Depois que um agente aceitar a chamada, a próxima chamada de entrada na fila começará a tocar nos agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="24004-120">Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="24004-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1--get-started"></a><span data-ttu-id="24004-121">Etapa 1-Introdução</span><span class="sxs-lookup"><span data-stu-id="24004-121">Step 1 — Get started</span></span>

<span data-ttu-id="24004-122">Para começar a usar filas de chamadas, é importante lembrar-se de algumas coisas:</span><span class="sxs-lookup"><span data-stu-id="24004-122">To get started using call queues, it's important to remember a few things:</span></span>

- <span data-ttu-id="24004-123">Uma fila de chamadas é necessária para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="24004-123">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="24004-124">Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter detalhes sobre contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="24004-124">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="24004-125">Ao atribuir um número de telefone a uma conta de recurso, agora você pode usar a [licença de usuário virtual](teams-add-on-licensing/virtual-user.md)de sistema telefônico sem custo.</span><span class="sxs-lookup"><span data-stu-id="24004-125">When you assign a phone number to a resource account, you can now use the cost-free Phone System [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span> <span data-ttu-id="24004-126">O sistema telefônico permite números de telefone no nível organizacional para uso com serviços de atendedor automático de baixo custo e fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-126">Phone System allows phone numbers at the organizational level for use with low-cost auto attendant and call queue services.</span></span>

> [!NOTE]
> <span data-ttu-id="24004-127">Os números do serviço de roteamento direto para filas de chamadas têm suporte somente para usuários e agentes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="24004-127">Direct Routing service numbers for call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE]
> <span data-ttu-id="24004-128">Para redirecionar chamadas para pessoas em sua organização que estão online, elas devem ter uma licença do **sistema de telefonia** e estar habilitadas para o Enterprise Voice ou ter planos de chamadas do Office 365.</span><span class="sxs-lookup"><span data-stu-id="24004-128">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="24004-129">Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="24004-129">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="24004-130">Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24004-130">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="24004-131">Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="24004-131">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="24004-132">Para saber mais sobre os planos de chamada do Office 365, consulte [sistema telefônico e planos de chamada](calling-plan-landing-page.md) e [planos de chamadas do Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="24004-132">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="24004-133">Você só pode atribuir filas de chamadas em nuvem e números de telefone de serviço de chamada gratuita que você recebeu no **centro de administração do Microsoft Teams** ou transferido de outro provedor de serviços.</span><span class="sxs-lookup"><span data-stu-id="24004-133">You can only assign Cloud call queues toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider.</span></span> <span data-ttu-id="24004-134">Créditos de comunicações são necessários para números de serviço de chamada gratuita.</span><span class="sxs-lookup"><span data-stu-id="24004-134">Communications Credits are required for toll-free service numbers.</span></span>

    > [!NOTE]
    > <span data-ttu-id="24004-135">Os números de telefone do usuário (assinante) não podem ser atribuídos a filas de chamadas-somente números de telefone de serviço de chamada tarifada ou de chamada gratuita podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="24004-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>

- <span data-ttu-id="24004-136">Os seguintes clientes têm suporte para agentes de chamada associados a uma fila de chamadas em nuvem:</span><span class="sxs-lookup"><span data-stu-id="24004-136">The following clients are supported for call agents associated to a Cloud call queue:</span></span>

  - <span data-ttu-id="24004-137">Cliente de área de trabalho do Skype for Business 2016 (versões de 32 bits e de 64 bits)</span><span class="sxs-lookup"><span data-stu-id="24004-137">Skype for Business desktop client 2016 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="24004-138">Lync desktop cliente 2013 (versões de 32 bits e de 64 bits)</span><span class="sxs-lookup"><span data-stu-id="24004-138">Lync desktop client 2013 (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="24004-139">Todos os modelos de telefone IP com suporte para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="24004-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="24004-140">Consulte [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="24004-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="24004-141">Cliente Skype for Business para Mac (versão 16.8.196 e posterior)</span><span class="sxs-lookup"><span data-stu-id="24004-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="24004-142">Cliente Skype for Business Android (versão 6.16.0.9 e posterior)</span><span class="sxs-lookup"><span data-stu-id="24004-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="24004-143">Cliente Skype for Business (versão 6.16.0 e posterior) do iPhone</span><span class="sxs-lookup"><span data-stu-id="24004-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="24004-144">Cliente Skype for Business para iPad (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="24004-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="24004-145">Microsoft Teams Windows Client (versões de 32 bits e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="24004-145">Microsoft Teams Windows client (32-bit and 64-bit versions)</span></span>

  - <span data-ttu-id="24004-146">Cliente Mac do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24004-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="24004-147">Aplicativo iPhone do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24004-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="24004-148">Aplicativo Android do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24004-148">Microsoft Teams Android app</span></span>

    > [!NOTE]
    > <span data-ttu-id="24004-149">As filas de chamadas atribuídas a um número de roteamento direto não oferecerão suporte para clientes do Skype for Business, clientes do Lync ou telefones IP do Skype for Business como agentes.</span><span class="sxs-lookup"><span data-stu-id="24004-149">Call queues that are assigned a direct routing number will not support Skype for Business clients, Lync clients, or Skype for Business IP Phones as agents.</span></span>

## <a name="step-2--get-or-transfer-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="24004-150">Etapa 2: obter ou transferir números de telefone de serviço de chamada tarifada ou gratuita</span><span class="sxs-lookup"><span data-stu-id="24004-150">Step 2 — Get or transfer toll or toll-free service phone numbers</span></span>

<span data-ttu-id="24004-151">Antes de criar e configurar suas filas de chamadas, você precisa obter ou transferir seus números de serviço de chamada tarifada ou chamada gratuitas existentes.</span><span class="sxs-lookup"><span data-stu-id="24004-151">Before you can create and set up your call queues, you need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="24004-152">Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="24004-152">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span> <span data-ttu-id="24004-153">Depois de obter os números de telefone de serviço de chamada tarifada ou gratuita, eles aparecerão nos**números de telefone**de**voz** > do centro > de **Administração do Microsoft Teams**.</span><span class="sxs-lookup"><span data-stu-id="24004-153">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**.</span></span> <span data-ttu-id="24004-154">Números de chamada gratuita serão listados com um **tipo** de serviço de número **: gratuito**.</span><span class="sxs-lookup"><span data-stu-id="24004-154">Toll free numbers will be listed with a **Number type** of **Service — Toll-Free**.</span></span>

> [!NOTE]
> <span data-ttu-id="24004-155">Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter números de serviço.</span><span class="sxs-lookup"><span data-stu-id="24004-155">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="24004-156">Vá para [gerenciar números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez de ver como fazer isso de fora dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="24004-156">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="24004-157">Ao configurar vários atendedores automáticos, você normalmente atribuiria um número de telefone à conta principal do recurso do atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="24004-157">When you set up multiple auto attendants, you would usually assign a phone number to the main auto attendant's resource account.</span></span> <span data-ttu-id="24004-158">As contas de recursos associadas a atendedores automáticos aninhados ou filas de chamadas geralmente não são necessárias para números de telefone.</span><span class="sxs-lookup"><span data-stu-id="24004-158">Resource accounts associated to nested auto attendants or call queues often don't need phone numbers.</span></span> <span data-ttu-id="24004-159">Esse atendedor automático pode direcionar os chamadores para suas filas de chamadas ou atendedores automáticos aninhados, mesmo que eles não tenham um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="24004-159">That auto attendant can direct callers to your call queues or nested auto attendants even if they don't have a phone number.</span></span> <span data-ttu-id="24004-160">Nessas situações, você pode criar todos os atendedores automáticos e filas de chamadas em seu sistema sem atribuir opções de discagem e, em seguida, editar as configurações mais tarde.</span><span class="sxs-lookup"><span data-stu-id="24004-160">In those situations, you can create all auto attendants and call queues in your system without assigning dialpad options, and then edit the settings later.</span></span> <span data-ttu-id="24004-161">Uma fila de chamadas ou atendedor automático deve existir para defini-lo como uma opção de menu.</span><span class="sxs-lookup"><span data-stu-id="24004-161">A call queue or auto attendant must exist to set it as a menu option.</span></span>

## <a name="step-3--create-a-call-queue"></a><span data-ttu-id="24004-162">Etapa 3 — criar uma fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="24004-162">Step 3 — Create a call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="24004-163">Todas as filas de chamadas são necessárias para ter uma [conta de recurso](manage-resource-accounts.md)associada.</span><span class="sxs-lookup"><span data-stu-id="24004-163">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="24004-164">Você deve criar a conta do recurso primeiro, então você pode associá-la à fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-164">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="use-the-microsoft-teams-admin-center"></a><span data-ttu-id="24004-165">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="24004-165">Use the Microsoft Teams admin center</span></span>

<span data-ttu-id="24004-166">No **centro de administração do Microsoft Teams**,**filas de chamadas**de **voz** > e clique em **+ Adicionar novo**:</span><span class="sxs-lookup"><span data-stu-id="24004-166">In the **Microsoft Teams admin center**, **Voice** > **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-display-name-and-resource-account"></a><span data-ttu-id="24004-167">Definir o nome para exibição e a conta do recurso</span><span class="sxs-lookup"><span data-stu-id="24004-167">Set the display name and resource account</span></span>

![Captura de tela de uma nova fila de chamadas com textos explicativos numerados](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="24004-169">![O ícone do número 1 faz referência a um texto explicativo no](media/sfbcallout1.png)
**nome** anterior da captura de tela digite um nome de exibição descritivo para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-169">![Icon of the number 1, references a callout in the previous screenshot](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="24004-170">Esse nome é necessário e pode conter até 64 caracteres, incluindo espaços.</span><span class="sxs-lookup"><span data-stu-id="24004-170">This name is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="24004-171">Esse nome será exibido na notificação para a chamada recebida.</span><span class="sxs-lookup"><span data-stu-id="24004-171">This name is displayed in the notification for the incoming call.</span></span>

* * *

![O ícone do número 2 faz referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="24004-173">**Adicionar contas** Selecione uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="24004-173">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="24004-174">Todas as filas de chamadas são necessárias para ter uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="24004-174">All call queues are required to have a resource account.</span></span> <span data-ttu-id="24004-175">Não é necessário ter contas de recursos para ter um número de telefone de chamada tarifada ou gratuita do serviço.</span><span class="sxs-lookup"><span data-stu-id="24004-175">Resource accounts aren't required to have a service toll or toll-free phone number.</span></span>

<span data-ttu-id="24004-176">Se não houver lista, obtenha números de serviço e atribua-os a uma conta de recurso antes de criar a fila de chamadas, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="24004-176">If there aren't any listed,  get service numbers and assign them to a Resource account before you create the call queue, as described earlier.</span></span> <span data-ttu-id="24004-177">Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="24004-177">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span> <span data-ttu-id="24004-178">Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter informações específicas sobre como atribuir um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="24004-178">See [Manage resource accounts in Teams](manage-resource-accounts.md) for specifics on how to assign a phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="24004-179">Se você quiser ou precisar atribuir um **domínio** , ele será atribuído à conta do recurso para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-179">If you want or need to assign a **Domain** you would  assign it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="24004-180">Definir a saudação e a música jogadas enquanto em espera</span><span class="sxs-lookup"><span data-stu-id="24004-180">Set the greeting and music played while on hold</span></span>

![captura de tela das opções de saudação e música com textos explicativos numerados](media/1d395a93-7cab-4178-9295-12d5379e20de.png)

* * *

![O ícone do número 1 faz referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="24004-183">**Mensagem** de saudação opcional reproduzida para as pessoas que chamam o número da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-183">**Greeting** the optional greeting played for people who call the call queue number.</span></span>

<span data-ttu-id="24004-184">Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. WMA).</span><span class="sxs-lookup"><span data-stu-id="24004-184">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![O ícone do número 2 faz referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="24004-186">**Música em espera** Você pode usar a música padrão em espera fornecida com a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-186">**Music on hold** You can use the default Music on Hold provided with the call queue.</span></span> <span data-ttu-id="24004-187">Você também pode carregar um arquivo de áudio nos formatos. wav, MP3 ou. WMA para usar como sua música personalizada em espera.</span><span class="sxs-lookup"><span data-stu-id="24004-187">You can also upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="24004-188">Selecionar as opções de atendimento de chamada</span><span class="sxs-lookup"><span data-stu-id="24004-188">Select the call answering options</span></span>

![Captura de tela das opções de atendimento de chamadas](media/5d249515-d532-4af2-90da-011404028b89.png) 

![O ícone do número 1 faz referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="24004-191">Para adicionar agentes individuais diretamente, sem adicioná-los a um grupo, clique em **Adicionar usuários**.</span><span class="sxs-lookup"><span data-stu-id="24004-191">To add individual agents directly, without adding them to a group, click **Add users**.</span></span> <span data-ttu-id="24004-192">Coloque agentes individuais na ordem em que você deseja que eles recebam a chamada.</span><span class="sxs-lookup"><span data-stu-id="24004-192">Put individual agents in the order in which you want them to receive the call.</span></span> <span data-ttu-id="24004-193">Você pode adicionar até 20 agentes individuais (para adicionar mais de 20, colocá-los em um grupo).</span><span class="sxs-lookup"><span data-stu-id="24004-193">You can add up to 20 individual agents (to add more than 20, put them in a group).</span></span>

<span data-ttu-id="24004-194">As chamadas são roteadas primeiro para agentes individuais e depois para os agentes em grupos.</span><span class="sxs-lookup"><span data-stu-id="24004-194">Calls are routed first to individual agents, then to the agents in groups.</span></span> 

<span data-ttu-id="24004-195">Você pode selecionar até 200 agentes de chamada que pertencem a qualquer uma das seguintes listas de endereçamento ou grupos:</span><span class="sxs-lookup"><span data-stu-id="24004-195">You can select up to 200 call agents who belong to any of the following mailing lists or groups:</span></span>

- <span data-ttu-id="24004-196">Grupo do Office 365</span><span class="sxs-lookup"><span data-stu-id="24004-196">Office 365 group</span></span>
- <span data-ttu-id="24004-197">Grupo de segurança</span><span class="sxs-lookup"><span data-stu-id="24004-197">Security group</span></span>
- <span data-ttu-id="24004-198">Lista de distribuição</span><span class="sxs-lookup"><span data-stu-id="24004-198">Distribution list</span></span>

<span data-ttu-id="24004-199">Os agentes de chamada selecionados devem ser:</span><span class="sxs-lookup"><span data-stu-id="24004-199">Call agents selected must be:</span></span> 

- <span data-ttu-id="24004-200">Usuários online com uma licença do sistema telefônico e Enterprise Voice habilitadas</span><span class="sxs-lookup"><span data-stu-id="24004-200">Online users with a Phone System license and Enterprise Voice enabled</span></span> 
- <span data-ttu-id="24004-201">Usuários online com um plano de chamada</span><span class="sxs-lookup"><span data-stu-id="24004-201">Online users with a Calling Plan</span></span>
- <span data-ttu-id="24004-202">Usuários locais do Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="24004-202">On-premises Skype for Business Server users</span></span>

  > [!NOTE]
  > <span data-ttu-id="24004-203">Isso também se aplica se você quiser redirecionar chamadas para as pessoas em sua organização que estão online.</span><span class="sxs-lookup"><span data-stu-id="24004-203">This also applies if you want to redirect calls to people in your organization who are online.</span></span> <span data-ttu-id="24004-204">Esses indivíduos devem ter uma licença do **sistema telefônico** e o Enterprise Voice habilitados **ou** ter um plano de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-204">These individuals must have a **Phone System** license and Enterprise Voice enabled **or** have a Calling Plan.</span></span> <span data-ttu-id="24004-205">Para obter mais informações, consulte [atribuir licenças do Skype for Business](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [atribuir licenças do Microsoft Teams](https://docs.microsoft.com/microsoftteams/assign-teams-licenses)ou [qual plano de chamada é ideal para você?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span><span class="sxs-lookup"><span data-stu-id="24004-205">For more information, see [Assign Skype for Business licenses](/Skype/SfbOnline/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md), [Assign Microsoft Teams licenses](https://docs.microsoft.com/microsoftteams/assign-teams-licenses), or [Which Calling Plan is right for you?](https://docs.microsoft.com/microsoftteams/calling-plan-landing-page)</span></span>

 <span data-ttu-id="24004-206">Para habilitar um agente para Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="24004-206">To enable an agent for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="24004-207">Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="24004-207">For example, run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="24004-208">Usuários com uma licença do **sistema telefônico** ou um plano de chamadas que são adicionados a um grupo do Office 365; uma lista de distribuição habilitada para email; ou um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="24004-208">Users with a **Phone System** license or a Calling Plan that are added to either an Office 365 Group; a mail-enabled Distribution List; or a Security Group.</span></span> <span data-ttu-id="24004-209">Quando você adiciona um agente em uma lista de distribuição ou um grupo de segurança como um agente de fila de chamada, pode levar até três horas para que a primeira chamada seja recebida.</span><span class="sxs-lookup"><span data-stu-id="24004-209">When you add an agent in a distribution list or a security group as a call queue agent, it can take up to three hours for the first call to arrive.</span></span> <span data-ttu-id="24004-210">Uma lista de distribuição ou um grupo de segurança recém-criado pode levar até 48 horas para se tornar disponível para ser usado com filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-210">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="24004-211">Os grupos do Office 365 recém-criados estão disponíveis quase que imediatamente.</span><span class="sxs-lookup"><span data-stu-id="24004-211">Newly created Office 365 Groups are available almost immediately.</span></span>

- <span data-ttu-id="24004-212">Se seus agentes estiverem usando o aplicativo Microsoft Teams para chamadas da fila de chamadas, eles precisarão estar no modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="24004-212">If your agents are using the Microsoft Teams App for call queue calls, they need to be in TeamsOnly mode.</span></span>

![Captura de tela do painel Adicionar agentes de chamada](media/skype-for-business-add-agents-to-call-queue.png)

![O ícone do número 2 faz referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="24004-215">**Método de roteamento** Você pode escolher o **atendedor**, a **série**ou o **rodízio** como o método de distribuição.</span><span class="sxs-lookup"><span data-stu-id="24004-215">**Routing method** You can choose either **Attendant**, **Serial**, or **Round Robin** as the distribution method.</span></span> <span data-ttu-id="24004-216">Todas as filas de chamadas novas e existentes têm roteamento de atendedor selecionado por padrão.</span><span class="sxs-lookup"><span data-stu-id="24004-216">All new and existing call queues have attendant routing selected by default.</span></span> <span data-ttu-id="24004-217">Quando o roteamento do atendente é usado, a primeira chamada na fila toca em todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="24004-217">When attendant routing is used, the first call in the queue rings all call agents at the same time.</span></span> <span data-ttu-id="24004-218">O primeiro agente de chamadas para atender a chamada recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="24004-218">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="24004-219">O **Roteamento de atendedor** faz com que a primeira chamada na fila toque em todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="24004-219">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="24004-220">O primeiro agente de chamadas para atender a chamada recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="24004-220">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="24004-221">**Roteamento serial** as chamadas recebidas entram em contato com todos os agentes de chamada, um por um, do início da lista de agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-221">**Serial routing** incoming calls ring all call agents one by one, from the beginning of the call agent list.</span></span> <span data-ttu-id="24004-222">Os agentes não podem ser solicitados na lista agente de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-222">Agents can't be ordered within the call agent list.</span></span> <span data-ttu-id="24004-223">Se um agente ignorar ou não atender a chamada, a chamada tocará no próximo agente e experimentará todos os agentes até que ele seja retirado ou expirado.</span><span class="sxs-lookup"><span data-stu-id="24004-223">If an agent dismisses or does not pick up a call, the call will ring the next agent and will try all agents until it is picked up or times out.</span></span>
  > [!NOTE]
  > <span data-ttu-id="24004-224">Com o roteamento serial, para agentes que estiverem **offline** ou que definiram sua presença como **não incomodar**, a chamada será roteada para esses usuários e não poderá conectar o usuário indisponível, o roteamento para o próximo agente na lista de agentes.</span><span class="sxs-lookup"><span data-stu-id="24004-224">With Serial routing, for agents who are **Offline** or have set their presence to **Do not Disturb**, the call will be routed to those users and fail to connect unavailable user, the routing to the next agent in the agent list.</span></span> <span data-ttu-id="24004-225">Isso não acontecerá se o agente **optar** por não receber chamadas da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-225">This is not the case if the agent has **opted out** of getting calls from the call queue.</span></span> <span data-ttu-id="24004-226">Para reduzir o intervalo de tempo que os roteiros de chamadas para o próximo agente na linha, o tempo de alerta do agente pode ser reduzido.</span><span class="sxs-lookup"><span data-stu-id="24004-226">To reduce the time interval the call routes to next agent in line, Agent Alert time can be decreased.</span></span>
- <span data-ttu-id="24004-227">O direcionamento de **rodízio** equilibra a circulação de chamadas de entrada para que cada agente de chamadas obtenha o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="24004-227">**Round robin** balances routing of incoming calls so that each call agent gets the same number of calls from the queue.</span></span> <span data-ttu-id="24004-228">Isso pode ser desejável em um ambiente de vendas de entrada para garantir uma oportunidade igual entre todos os agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-228">This may be desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="24004-229">Selecionar uma opção de cancelamento de agente</span><span class="sxs-lookup"><span data-stu-id="24004-229">Select an agent opt-out option</span></span>

![Captura de tela de opções de cancelamento de agente com textos explicativos numerados](media/99279eff-db61-4acf-9b62-64be84b6414b.png)

* * *

![O ícone do número 1 faz referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="24004-232">O **agente pode optar por não receber chamadas** Você pode optar por permitir que os agentes da fila de chamadas optem por fazer chamadas de uma determinada fila habilitando esta opção.</span><span class="sxs-lookup"><span data-stu-id="24004-232">**Agent can opt out of getting calls** You can choose to allow call queue agents to opt-out of taking calls from a particular queue by enabling this option.</span></span>

<span data-ttu-id="24004-233">Habilitar essa opção permite que todos os agentes nesta fila sejam iniciados ou parem de receber chamadas desta fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-233">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="24004-234">Você pode revogar o privilégio de cancelamento de agente a qualquer momento desmarcando a caixa de seleção, fazendo com que os agentes se tornem automaticamente para esta fila de novo (a configuração padrão para todos os agentes).</span><span class="sxs-lookup"><span data-stu-id="24004-234">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="24004-235">Para acessar a opção de recusa, os agentes podem:</span><span class="sxs-lookup"><span data-stu-id="24004-235">To access the opt-out option, agents can:</span></span>

 1. <span data-ttu-id="24004-236">Abra **as opções** no cliente do Skype for Business da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="24004-236">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="24004-237">Na guia **encaminhamento de chamadas** , clique no link **Editar configurações online** .</span><span class="sxs-lookup"><span data-stu-id="24004-237">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="24004-238">Na página Configurações do usuário, clique em **filas de chamadas**e desmarque as caixas de seleção para recusar as filas.</span><span class="sxs-lookup"><span data-stu-id="24004-238">On the user settings page, click **Call Queues**, and then clear the check boxes to opt-out of queues.</span></span>

    > [!NOTE]
    > <span data-ttu-id="24004-239">Os agentes que usam aplicativos ou pontos de extremidade diferentes da área de trabalho do Skype for Business podem acessar a opção de cancelamento no portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings)de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="24004-239">Agents using apps or endpoints other than Skype for Business Desktop can access the opt-out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>
    >
    > <span data-ttu-id="24004-240">Se os agentes estiverem em clientes da área de trabalho do Microsoft Teams, eles poderão se recusar usando as configurações de chamada.</span><span class="sxs-lookup"><span data-stu-id="24004-240">If the agents are in Microsoft Teams desktop clients, then they can opt-out by using the Call Settings.</span></span> 

![O ícone do número 2 faz referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="24004-242">**Configuração de alerta do agente**</span><span class="sxs-lookup"><span data-stu-id="24004-242">**Agent Alert setting**</span></span>

<span data-ttu-id="24004-243">Isso define a duração de um agente sendo notificado sobre uma chamada antes que os métodos de roteamento serial ou Round Robin se movam para o próximo agente.</span><span class="sxs-lookup"><span data-stu-id="24004-243">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="24004-244">A configuração padrão é 30 segundos, mas pode ser definida por até 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="24004-244">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="24004-245">Configurar o estouro de chamadas e as opções de controle de tempo limite</span><span class="sxs-lookup"><span data-stu-id="24004-245">Set the call overflow and timeout handling options</span></span>

![Captura de tela das opções de tratamento de estouro com textos explicativos numerados](media/3f018734-16fe-458b-827d-71fc25155cde.png)

* * *

![O ícone do número 1 faz referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="24004-248">**Máximo de chamadas na fila** Use esta configuração para definir o número máximo de chamadas que podem esperar na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="24004-248">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="24004-249">O padrão é 50, mas pode variar de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="24004-249">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="24004-250">Quando esse limite for atingido, a chamada será manipulada da maneira que você definiu **quando a configuração número máximo de chamadas for atingida** abaixo.</span><span class="sxs-lookup"><span data-stu-id="24004-250">When this limit is reached, the call is handled in the way you set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![O ícone do número 2 faz referência a um texto explicativo na captura de tela anterior](media/sfbcallout2.png)

<span data-ttu-id="24004-252">**Quando o número máximo de chamadas for atingido** Quando a fila de chamadas atinge seu tamanho máximo (definido usando o **máximo de chamadas na** configuração de fila), você pode escolher o que acontece com as novas chamadas recebidas.</span><span class="sxs-lookup"><span data-stu-id="24004-252">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="24004-253">**Desconectar** A chamada está desconectada.</span><span class="sxs-lookup"><span data-stu-id="24004-253">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="24004-254">**Redirecionar para** Ao escolher essa opção, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="24004-254">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="24004-255">**Pessoa em sua empresa** Um usuário online com uma licença do **sistema de telefonia** e estar habilitado para o Enterprise Voice ou ter um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="24004-255">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="24004-256">Você pode configurá-lo para que o chamador possa ser enviado para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="24004-256">You can set it up so the caller can be sent to voicemail.</span></span> <span data-ttu-id="24004-257">Para fazer isso, selecione uma **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="24004-257">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="24004-258">Para saber mais sobre as licenças necessárias para correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="24004-258">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="24004-259">**Aplicativo de voz** Selecione o nome de uma conta de recurso associada a uma fila de chamadas ou atendedor automático que já foi criado.</span><span class="sxs-lookup"><span data-stu-id="24004-259">**Voice application** Select the name of a resource account associated to either a call queue or auto attendant that has already been created.</span></span>

* * *

![O ícone do número 3 faz referência a um texto explicativo na captura de tela anterior](media/sfbcallout3.png)

<span data-ttu-id="24004-261">**Tempo limite de chamada: tempo máximo de espera** Você também pode decidir quanto tempo uma chamada pode ficar em espera na fila antes de expirar e precisar ser redirecionada ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="24004-261">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="24004-262">O local em que é redirecionado é baseado em como você define a configuração **quando uma chamada atinge o tempo limite** .</span><span class="sxs-lookup"><span data-stu-id="24004-262">Where it is redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="24004-263">Você pode definir uma hora de 0 a 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="24004-263">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="24004-264">O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="24004-264">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="24004-265">Isso permite que você manipule o fluxo de chamadas com granularidade mais fina.</span><span class="sxs-lookup"><span data-stu-id="24004-265">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="24004-266">Por exemplo, você pode especificar que as chamadas não atendidas por um agente dentro de 30 segundos vão para um atendedor automático de pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="24004-266">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![O ícone do número 4 faz referência a um texto explicativo na captura de tela anterior](media/sfbcallout4.png)

<span data-ttu-id="24004-268">**Quando a chamada** expira Quando a chamada atingir o limite que você definiu no tempo em que **uma chamada pode esperar na configuração de fila** , você pode escolher o que acontecerá com a chamada:</span><span class="sxs-lookup"><span data-stu-id="24004-268">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to the call:</span></span>

- <span data-ttu-id="24004-269">**Desconectar** A chamada está desconectada.</span><span class="sxs-lookup"><span data-stu-id="24004-269">**Disconnect** The call is disconnected.</span></span>
- <span data-ttu-id="24004-270">**Redirecionar esta chamada para** Ao escolher esta opção, você tem estas opções:</span><span class="sxs-lookup"><span data-stu-id="24004-270">**Redirect this call to** When you choose this, you have these options:</span></span>
  - <span data-ttu-id="24004-271">**Pessoa em sua empresa** Um usuário online com uma licença do **sistema de telefonia** e estar habilitado para o Enterprise Voice ou ter planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="24004-271">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="24004-272">Para configurá-lo para que a pessoa que está ligando possa ser enviada para o correio de voz, selecione uma **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="24004-272">To set it up so the person calling in can be sent to voicemail, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="24004-273">Para saber mais sobre as licenças necessárias para correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="24004-273">To learn about licenses required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="24004-274">**Aplicativo de voz** Selecione o nome de uma conta de recurso associada a uma fila de chamadas ou atendedor automático que você já criou.</span><span class="sxs-lookup"><span data-stu-id="24004-274">**Voice app** Select the name of a resource account associated with either a call queue or auto attendant that you already created.</span></span>

## <a name="change-caller-id-for-outbound-calls"></a><span data-ttu-id="24004-275">Alterar a identificação de chamada para chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="24004-275">Change Caller ID for outbound calls</span></span>

<span data-ttu-id="24004-276">Para proteger a identidade de um agente de chamada, altere a identificação de chamadas para chamadas de saída para uma fila de chamadas, atendedor automático ou qualquer número de serviço com o cmdlet **New-CsCallingLineIdentity** , como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="24004-276">To protect a call agent's identity, change their caller ID for outbound calls to a call queue, auto attendant, or any service number with the **New-CsCallingLineIdentity** cmdlet as in the following example:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="24004-277">Em seguida, aplique a política ao usuário com o cmdlet **Grant-CallingLineIdentity** como no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="24004-277">Then apply the policy to the user with the **Grant-CallingLineIdentity** cmdlet as in the following example:</span></span> 

``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="24004-278">Para obter mais informações, consulte [como a identificação de chamadas pode ser usada em sua organização](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="24004-278">For more information, see [How can caller ID be used in your organization](/microsoftteams/how-can-caller-id-be-used-in-your-organization).</span></span>

## <a name="call-queue-cmdlets"></a><span data-ttu-id="24004-279">Cmdlets da fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="24004-279">Call queue cmdlets</span></span>

<span data-ttu-id="24004-280">Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-280">You can also use Windows PowerShell to create and set up call queues.</span></span> <span data-ttu-id="24004-281">Estes são os cmdlets que você usa para gerenciar uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="24004-281">Here are the cmdlets that you use to manage a call queue.</span></span>

- [<span data-ttu-id="24004-282">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="24004-282">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="24004-283">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="24004-283">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="24004-284">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="24004-284">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="24004-285">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="24004-285">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="24004-286">Mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="24004-286">More about Windows PowerShell</span></span>

- <span data-ttu-id="24004-287">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="24004-287">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="24004-288">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Microsoft Teams com um único ponto de administração.</span><span class="sxs-lookup"><span data-stu-id="24004-288">With Windows PowerShell, you can manage Office 365 and Microsoft Teams with a single point of administration.</span></span> <span data-ttu-id="24004-289">Isso pode simplificar o seu trabalho diário, quando você tem várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="24004-289">It can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="24004-290">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="24004-290">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="24004-291">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="24004-291">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="24004-292">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="24004-292">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="24004-293">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o centro de administração do Microsoft Teams quando você faz alterações para muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="24004-293">Windows PowerShell has many advantages in speed, simplicity, and productivity over the Microsoft Teams admin center when you make changes for many users at once.</span></span> <span data-ttu-id="24004-294">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="24004-294">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="24004-295">Gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="24004-295">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="24004-296">Configurar o computador para o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="24004-296">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="24004-297">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="24004-297">Related topics</span></span>

[<span data-ttu-id="24004-298">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="24004-298">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="24004-299">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="24004-299">Getting service phone numbers</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="24004-300">Disponibilidade de Audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="24004-300">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="24004-301">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="24004-301">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
