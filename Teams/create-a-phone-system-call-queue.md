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
description: Saiba como configurar o sistema telefônico para filas de chamadas em nuvem para dar a você uma saudação organizacional, música em espera e redirecionar chamadas para agentes de chamadas em listas de distribuição e grupos de segurança. Você também pode definir o tamanho máximo da fila, o tempo limite e as opções de tratamento de chamadas.
ms.openlocfilehash: 63dc71d6fad4fa82e1a335b20612e60c3b56ac91
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34281943"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="b9b0d-104">Criar uma fila de chamada do Cloud</span><span class="sxs-lookup"><span data-stu-id="b9b0d-104">Create a Cloud call queue</span></span>

<span data-ttu-id="b9b0d-105">As filas de chamadas na nuvem incluem Saudações que são usadas quando alguém liga para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de Pesquisar o próximo agente de chamada disponível para lidar com a chamada enquanto as pessoas que chamam são ouvindo música em espera.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-105">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="b9b0d-106">Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="b9b0d-107">As filas de chamadas na nuvem podem fornecer:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-107">Cloud call queues can provide:</span></span>
  
- <span data-ttu-id="b9b0d-108">Uma saudação organizacional.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-108">An organizational greeting.</span></span>
- <span data-ttu-id="b9b0d-109">Música enquanto as pessoas estão aguardando a espera.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="b9b0d-110">Redirecionamento de chamadas para agentes de chamada em listas de distribuição habilitadas por email e grupos de segurança.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="b9b0d-111">Como fazer configurações para tamanho máximo, tempo limite e opções de tratamento de chamadas na fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="b9b0d-112">Quando alguém liga para um número de telefone associado a uma fila de chamadas por meio de uma [conta de recurso](manage-resource-accounts.md), ele ouvirá primeiro uma saudação (se houver alguma configuração) e, em seguida, será colocado na fila e aguardará o próximo agente de chamada disponível.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="b9b0d-113">A pessoa que está ligando ouvirá música enquanto eles estiverem em espera, e as chamadas serão oferecidas aos agentes de chamadas em ordem *primeiro a entrar, primeiro a sair* (FIFO).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="b9b0d-114">Todas as chamadas em espera na fila serão distribuídas usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-114">All calls waiting in the queue will be distributed using one of the following methods:</span></span>
  
- <span data-ttu-id="b9b0d-115">Com o roteamento de atendedor, a primeira chamada na fila tocará todos os agentes ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="b9b0d-116">Com o roteamento serial, a primeira chamada na fila tocará em todos os agentes de chamadas, um por um.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
- <span data-ttu-id="b9b0d-117">Com o rodízio, o roteamento de chamadas recebidas é balanceado para que cada agente de chamadas obtenha o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-117">With round robin, routing of incoming calls is balanced so that each call agent will get the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9b0d-118">Os agentes de chamada que estiverem **offline**, definiram sua presença como **não incomodar** ou optaram pela fila de chamadas não serão chamados.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-118">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="b9b0d-119">Somente uma notificação de chamada de entrada (para a chamada no início da fila) ao mesmo tempo será enviada para os agentes de chamada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-119">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="b9b0d-120">Depois que um agente aceitar a chamada, a próxima chamada de entrada na fila começará a tocar nos agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-120">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="b9b0d-121">Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-121">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="b9b0d-122">Etapa 1-Introdução</span><span class="sxs-lookup"><span data-stu-id="b9b0d-122">Step 1 - Get started</span></span>

<span data-ttu-id="b9b0d-123">Para começar a usar filas de chamadas, é importante lembrar-se de algumas coisas:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-123">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="b9b0d-124">Uma fila de chamadas é necessária para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-124">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="b9b0d-125">Consulte [gerenciar contas de recursos no Teams](manage-resource-accounts.md) para obter detalhes sobre contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-125">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="b9b0d-126">Se você planeja atribuir um número de roteamento direto, será necessário adquirir e atribuir as seguintes licenças às contas \(do recurso Office 365 Enterprise E1, E3 ou E5 com o complemento do sistema telefônico.\)</span><span class="sxs-lookup"><span data-stu-id="b9b0d-126">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="b9b0d-127">Se estiver atribuindo um número de serviço da Microsoft, você precisará adquirir e atribuir as seguintes licenças à sua conta \(de recurso Office 365 Enterprise E1, E3 ou e5, com o complemento do sistema de telefonia e um plano\)de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-127">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="b9b0d-128">Você só precisa licenciar as contas de recursos com um número de telefone atribuído a ela.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-128">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="b9b0d-129">Em um atendedor automático aninhado ou fila de chamadas, você não precisa licenciar o restante dos atendedores automáticos ou filas de chamadas se eles não tiverem números de telefone associados a eles.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-129">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them.</span></span> 

> [!NOTE] 
> <span data-ttu-id="b9b0d-130">Os números do serviço de roteamento direto para atendedor automático e filas de chamadas são suportados somente para usuários e agentes do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-130">Direct Routing service numbers for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE] 
> <span data-ttu-id="b9b0d-131">A Microsoft está trabalhando em um modelo de licenciamento sem custo para aplicativos como atendedores automáticos da nuvem e filas de chamadas, por ora, você precisa usar o modelo de licenciamento do usuário.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-131">Microsoft is working on a cost-free licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!NOTE]
> <span data-ttu-id="b9b0d-132">Para redirecionar chamadas para pessoas em sua organização que estão online, elas devem ter uma licença do **sistema de telefonia** e estar habilitadas para o Enterprise Voice ou ter planos de chamadas do Office 365.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-132">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="b9b0d-133">Consulte [atribuir licenças do Skype for Business](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-133">See  [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="b9b0d-134">Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-134">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="b9b0d-135">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="b9b0d-135">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="b9b0d-136">Para saber mais sobre os planos de chamada do Office 365, consulte [sistema telefônico e planos de chamada](calling-plan-landing-page.md) e [planos de chamadas do Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-136">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="b9b0d-137">Você só pode atribuir números de telefone de serviço de chamada tarifada e gratuita que você recebeu no **centro de administração do Microsoft Teams** ou transferido de outro provedor de serviços para filas de chamadas na nuvem.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-137">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Cloud call queues.</span></span> <span data-ttu-id="b9b0d-138">Para obter e usar números de serviço de chamada gratuita, você precisa configurar créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-138">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9b0d-139">Os números de telefone do usuário (assinante) não podem ser atribuídos a filas de chamadas-somente números de telefone de serviço de chamada tarifada ou de chamada gratuita podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-139">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="b9b0d-140">Quando você está distribuindo as chamadas recebidas de uma fila de chamadas em nuvem, esses clientes têm suporte para agentes de chamada:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-140">When you are distributing the incoming calls from a Cloud call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="b9b0d-141">Cliente de área de trabalho do Skype for Business 2016 (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="b9b0d-141">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="b9b0d-142">Lync desktop cliente 2013 (versões do 32 e do 64 bits)</span><span class="sxs-lookup"><span data-stu-id="b9b0d-142">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="b9b0d-143">Todos os modelos de telefone IP com suporte para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-143">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="b9b0d-144">Consulte [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-144">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="b9b0d-145">Cliente Skype for Business para Mac (versão 16.8.196 e posterior)</span><span class="sxs-lookup"><span data-stu-id="b9b0d-145">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="b9b0d-146">Cliente Skype for Business Android (versão 6.16.0.9 e posterior)</span><span class="sxs-lookup"><span data-stu-id="b9b0d-146">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="b9b0d-147">Cliente Skype for Business (versão 6.16.0 e posterior) do iPhone</span><span class="sxs-lookup"><span data-stu-id="b9b0d-147">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="b9b0d-148">Cliente Skype for Business para iPad (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="b9b0d-148">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="b9b0d-149">Microsoft Teams Windows Client (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="b9b0d-149">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="b9b0d-150">Cliente Mac do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9b0d-150">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="b9b0d-151">Aplicativo iPhone do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9b0d-151">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="b9b0d-152">Aplicativo Android do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9b0d-152">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="b9b0d-153">Etapa 2-como receber ou transferir números de telefone de serviço de chamada tarifada ou gratuita</span><span class="sxs-lookup"><span data-stu-id="b9b0d-153">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="b9b0d-154">Antes de você poder criar e configurar as filas de chamada, será necessário receber ou transferir os números de serviço de chamada gratuita ou tarifada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-154">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="b9b0d-155">Depois de obter os números de telefone de serviço de chamada tarifada ou gratuita, eles serão exibidos no **Centro** > de administração do Microsoft Teams para**números de telefone**de**voz** > , e o **tipo de número** listado será listado como **serviço-chamada gratuita**.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-155">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="b9b0d-156">Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-156">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9b0d-157">Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter números de serviço.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-157">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="b9b0d-158">Vá para [gerenciar números de telefone de sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez de ver como fazer isso de fora dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-158">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="b9b0d-159">Se você também estiver configurando atendedores automáticos, talvez seja necessário atribuir apenas um número de telefone à conta principal do recurso do atendedor automático e, em seguida, fazer chamadores diretos para a sua fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-159">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="b9b0d-160">Se esse for o caso, a fila de chamadas precisará ser criada antes que você possa criar uma opção no atendedor automático que seleciona a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-160">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="b9b0d-161">Etapa 3-criar uma nova fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="b9b0d-161">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="b9b0d-162">Todas as filas de chamadas são necessárias para ter uma [conta de recurso](manage-resource-accounts.md)associada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-162">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="b9b0d-163">Você deve criar a conta do recurso primeiro, então você pode associá-la à fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-163">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="b9b0d-164">Usar o centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b9b0d-164">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="b9b0d-165">No **centro de administração do Microsoft Teams**, filas de**chamadas**de **voz** >  e clique em **+ Adicionar novo**:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-165">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="b9b0d-166">Definir o nome de exibição da fila de chamadas e a conta do recurso</span><span class="sxs-lookup"><span data-stu-id="b9b0d-166">Set the call queue display name and resource account</span></span>

![Configurar uma fila de chamadas.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="b9b0d-168">![Número 1](media/sfbcallout1.png)
**nome** Insira um nome de exibição descritivo para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-168">![Number 1](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="b9b0d-169">Isso é necessário e pode conter até 64 caracteres, incluindo espaços.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-169">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="b9b0d-170">Esse nome será exibido na notificação para a chamada recebida.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-170">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="b9b0d-172">**Adicionar contas** Selecione uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-172">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="b9b0d-173">A conta do recurso pode ou não estar associada a um número de telefone de chamada tarifada ou gratuita do serviço para a fila de chamadas, mas cada fila de chamadas exige uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-173">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="b9b0d-174">Se não houver uma lista, você precisará obter números de serviço e atribuí-los a uma conta de recurso antes de poder criar esta fila de chamadas, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-174">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="b9b0d-175">Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-175">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> <span data-ttu-id="b9b0d-176">Você precisará criar uma conta de recurso, conforme descrito em [gerenciar contas de recursos no Teams](manage-resource-accounts.md) , se quiser que a fila de chamadas tenha um número de telefone associado.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-176">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="b9b0d-177">Se quiser ou precisar atribuir um **domínio** , você pode fazê-lo atribuindo-o à conta do recurso para a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-177">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="b9b0d-178">Definir a saudação e a música jogadas enquanto em espera</span><span class="sxs-lookup"><span data-stu-id="b9b0d-178">Set the greeting and music played while on hold</span></span>

![Configurar uma fila de chamadas.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="b9b0d-181">\*\*\*\* A saudação é opcional.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-181">**Greeting** is optional.</span></span> <span data-ttu-id="b9b0d-182">Esta é a saudação que é reproduzida para as pessoas que ligarem para o número da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-182">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="b9b0d-183">Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. WMA).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-183">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="b9b0d-185">**Música em espera** Você pode usar a música padrão em espera fornecida com a fila de chamadas ou pode carregar um arquivo de áudio nos formatos. wav, MP3 ou. WMA para usar como sua música personalizada em espera.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-185">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="b9b0d-186">Selecionar as opções de atendimento de chamada</span><span class="sxs-lookup"><span data-stu-id="b9b0d-186">Select the call answering options</span></span>

![Mostra as opções do método de distribuição de chamadas](media/5d249515-d532-4af2-90da-011404028b89.png)

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="b9b0d-189">Você pode selecionar até 200 agentes de chamadas pertencentes a listas ou grupos de endereçamento especificados.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-189">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="b9b0d-190">Os agentes de chamadas devem ser:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-190">Call agents must be either:</span></span>

- <span data-ttu-id="b9b0d-191">Um usuário online com uma licença do **sistema de telefonia** e habilitado para o Enterprise Voice ou com um plano de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-191">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="b9b0d-192">Para redirecionar chamadas para pessoas em sua organização que estão online, elas devem ter uma licença do **sistema de telefonia** e estar habilitadas para o Enterprise Voice ou ter um plano de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-192">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="b9b0d-193">Consulte [atribuir licenças do Skype for Business](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-193">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

 <span data-ttu-id="b9b0d-194">Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-194">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="b9b0d-195">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="b9b0d-195">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="b9b0d-196">Usuários online com uma licença do **sistema telefônico** e um plano de chamada que são adicionados a um grupo do Office 365, uma lista de distribuição habilitada para email ou um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-196">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="b9b0d-197">Pode levar até 3 horas para um novo agente adicionado para uma lista de distribuição ou um grupo de segurança para começar a receber chamadas de uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-197">It might take up to 3 hours for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="b9b0d-198">Uma lista de distribuição ou um grupo de segurança recém-criado pode levar até 48 horas para se tornar disponível para ser usado com filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-198">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="b9b0d-199">Os grupos do Office 365 recém-criados estão disponíveis quase que imediatamente.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-199">Newly created Office 365 Groups are available almost immediately.</span></span>

![Configurar filas de chamadas.](media/skype-for-business-add-agents-to-call-queue.png)

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="b9b0d-202">**Método de roteamento** Você pode escolher o **atendedor**, a **série**ou o **rodízio** para o método de distribuição da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-202">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="b9b0d-203">Todas as filas de chamadas novas e existentes terão o roteamento de atendedor selecionado por padrão.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-203">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="b9b0d-204">Quando o roteamento do atendente for usado, a primeira chamada na fila tocará todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-204">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="b9b0d-205">O primeiro agente de chamadas para atender a chamada recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-205">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="b9b0d-206">O **Roteamento** de atendedor faz com que a primeira chamada na fila toque em todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-206">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="b9b0d-207">O primeiro agente de chamadas para atender a chamada recebe a chamada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-207">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="b9b0d-208">**Roteamento em série** as chamadas recebidas entrarão em contato com os agentes, um por um, começando do início da lista de agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-208">**Serial routing** incoming calls will ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="b9b0d-209">Os agentes não podem ser ordenados na lista agente de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-209">Agents cannot be ordered within the call agent list.</span></span> <span data-ttu-id="b9b0d-210">Se um agente ignorar ou não atender a chamada, a chamada tocará o próximo agente na lista e experimentará todos os agentes, um por vez, até que ele seja retirado ou expire em espera na fila.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-210">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="b9b0d-211">O roteamento serial vai ignorar os agentes que estiverem **offline**, definir sua presença como **não incomodar**ou optar por \*\*\*\* não receber chamadas desta fila.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-211">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="b9b0d-212">O direcionamento de **rodízio** equilibra a circulação de chamadas de entrada para que cada agente de chamadas receba o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-212">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="b9b0d-213">Isso pode ser muito desejável em um ambiente de vendas de entrada para garantir uma oportunidade igual entre todos os agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-213">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="b9b0d-214">Selecionar uma opção de cancelamento de agente</span><span class="sxs-lookup"><span data-stu-id="b9b0d-214">Select an agent opt out option</span></span>

![Mostra a caixa de seleção cancelar agente](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="b9b0d-217">**Opção** de cancelamento de agente Você pode optar por permitir que os agentes da fila de chamadas recusem a fazer chamadas de uma fila específica selecionando a **opção Cancelar**cancelamento do agente.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-217">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="b9b0d-218">Habilitar essa opção permite que todos os agentes nesta fila sejam iniciados ou parem de receber chamadas desta fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-218">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="b9b0d-219">Você pode revogar o privilégio de cancelamento de agente a qualquer momento desmarcando a caixa de seleção, fazendo com que os agentes se tornem automaticamente para esta fila de novo (a configuração padrão para todos os agentes).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-219">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="b9b0d-220">Para acessar a opção de recusa, os agentes podem fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-220">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="b9b0d-221">Abra **as opções** no cliente do Skype for Business da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-221">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="b9b0d-222">Na guia **encaminhamento de chamadas** , clique no link **Editar configurações online** .</span><span class="sxs-lookup"><span data-stu-id="b9b0d-222">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="b9b0d-223">Na página Configurações do usuário, clique em **filas de chamadas**e desmarque as caixas de seleção de todas as filas para as quais deseja sair.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-223">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b9b0d-224">Os agentes que usam aplicativos ou pontos de extremidade diferentes da área de trabalho do Skype for Business podem acessar a opção recusar no [https://aka.ms/cqsettings](https://aka.ms/cqsettings)portal de configurações do usuário.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-224">Agents using apps or endpoints other than Skype for Business Desktop can access the opt out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="b9b0d-225">![Configuração de](media/sfbcallout2.png)
**alerta do agente** número 2</span><span class="sxs-lookup"><span data-stu-id="b9b0d-225">![Number 2](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="b9b0d-226">Isso define a duração de um agente sendo notificado sobre uma chamada antes que os métodos de roteamento serial ou Round Robin se movam para o próximo agente.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-226">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="b9b0d-227">A configuração padrão é 30 segundos, mas pode ser definida por até 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-227">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="b9b0d-228">Configurar o estouro de chamadas e as opções de controle de tempo limite</span><span class="sxs-lookup"><span data-stu-id="b9b0d-228">Set the call overflow and timeout handling options</span></span>

![Configurar uma fila de chamadas.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="b9b0d-231">**Máximo de chamadas na fila** Use esta configuração para definir o número máximo de chamadas que podem esperar na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-231">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="b9b0d-232">O padrão é 50, mas pode variar de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-232">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="b9b0d-233">Quando esse limite for atingido, a chamada será manipulada da mesma forma que você definiu **quando a configuração número máximo de chamadas é atingida** abaixo.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-233">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="b9b0d-235">**Quando o número máximo de chamadas for atingido** Quando a fila de chamadas atinge seu tamanho máximo (definido usando o **máximo de chamadas na** configuração de fila), você pode escolher o que acontece com as novas chamadas recebidas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-235">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="b9b0d-236">**Desconectar** A chamada será desconectada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-236">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="b9b0d-237">**Redirecionar para** Ao escolher essa opção, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-237">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="b9b0d-238">**Pessoa em sua empresa** Um usuário online com uma licença do **sistema de telefonia** e estar habilitado para o Enterprise Voice ou ter um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-238">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="b9b0d-239">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-239">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="b9b0d-240">Para fazer isso, selecione uma **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-240">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="b9b0d-241">Para saber mais sobre o licenciamento necessário para correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-241">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="b9b0d-242">**Aplicativo de voz** Selecione o nome de uma fila de chamadas ou o atendedor automático que já foi criado.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-242">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="b9b0d-244">**Tempo limite de chamada: tempo máximo de espera** Você também pode decidir quanto tempo uma chamada pode ficar em espera na fila antes de expirar e precisar ser redirecionada ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-244">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="b9b0d-245">Onde será redirecionado é baseado em como você define a configuração **quando uma chamada atinge o tempo limite** .</span><span class="sxs-lookup"><span data-stu-id="b9b0d-245">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="b9b0d-246">Você pode definir uma hora de 0 a 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-246">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="b9b0d-247">O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-247">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="b9b0d-248">Isso permite que você manipule o fluxo de chamadas com granularidade mais fina.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-248">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="b9b0d-249">Por exemplo, você pode especificar que as chamadas não atendidas por um agente dentro de 30 segundos vão para um atendedor automático de pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-249">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="b9b0d-251">**Quando a chamada** expira Quando a chamada atingir o limite que você definiu no **tempo em que uma chamada pode esperar na configuração de fila** , você pode escolher o que acontecerá com esta chamada:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-251">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="b9b0d-252">**Desconectar** A chamada será desconectada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-252">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="b9b0d-253">**Redirecionar esta chamada para** Ao escolher esta opção, você terá as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-253">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="b9b0d-254">**Pessoa em sua empresa** Um usuário online com uma licença do **sistema de telefonia** e estar habilitado para o Enterprise Voice ou ter planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-254">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="b9b0d-255">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-255">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="b9b0d-256">Para fazer isso, selecione uma **pessoa em sua empresa** e defina esta pessoa para que as chamadas sejam encaminhadas diretamente para o correio de voz.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-256">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="b9b0d-257">Para saber mais sobre o licenciamento necessário para correio de voz, consulte [Configurar correio de voz na nuvem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-257">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="b9b0d-258">**Aplicativo de voz** Selecione o nome de uma fila de chamadas ou o atendedor automático que já foi criado.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-258">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="b9b0d-259">Alterar a identificação de chamada de um usuário para chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="b9b0d-259">Changing a user's Caller ID for outbound calls</span></span> 

<span data-ttu-id="b9b0d-260">Você pode proteger a identidade de um usuário alterando a identificação de chamadas para chamadas de saída para uma fila de chamadas, atendedor automático ou qualquer número de serviço, em vez disso, criando uma política usando o cmdlet **New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="b9b0d-260">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="b9b0d-261">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-261">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="b9b0d-262">Em seguida, aplique a política ao usuário usando o cmdlet **Grant-CallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="b9b0d-262">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="b9b0d-263">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-263">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="b9b0d-264">Você pode obter mais informações sobre como fazer alterações nas configurações de identificação de chamada em sua organização no artigo [como a identificação de chamadas pode ser usada em sua organização](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="b9b0d-264">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="b9b0d-265">Deseja saber mais?</span><span class="sxs-lookup"><span data-stu-id="b9b0d-265">Want to know more?</span></span>

<span data-ttu-id="b9b0d-266">Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-266">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="b9b0d-267">Cmdlets da fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="b9b0d-267">Call queue cmdlets</span></span>

<span data-ttu-id="b9b0d-268">Estes são os cmdlets necessários para gerenciar uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-268">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="b9b0d-269">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b9b0d-269">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="b9b0d-270">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b9b0d-270">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="b9b0d-271">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b9b0d-271">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="b9b0d-272">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="b9b0d-272">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="b9b0d-273">Mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9b0d-273">More about Windows PowerShell</span></span>

- <span data-ttu-id="b9b0d-274">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-274">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="b9b0d-275">Com o Windows PowerShell, você pode gerenciar o Office 365 e o Microsoft Teams usando um único ponto de administração que pode simplificar seu trabalho diário, quando você tem várias tarefas para fazer.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-275">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="b9b0d-276">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-276">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="b9b0d-277">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b9b0d-277">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="b9b0d-278">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="b9b0d-278">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="b9b0d-279">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Microsoft Teams, como quando você está definindo alterações de vários usuários de uma vez.</span><span class="sxs-lookup"><span data-stu-id="b9b0d-279">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="b9b0d-280">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="b9b0d-280">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="b9b0d-281">Gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9b0d-281">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="b9b0d-282">Configurar seu computador para o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="b9b0d-282">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="b9b0d-283">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="b9b0d-283">Related topics</span></span>

[<span data-ttu-id="b9b0d-284">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="b9b0d-284">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="b9b0d-285">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="b9b0d-285">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="b9b0d-286">Disponibilidade de audioconferência e planos de chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="b9b0d-286">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="b9b0d-287">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="b9b0d-287">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
