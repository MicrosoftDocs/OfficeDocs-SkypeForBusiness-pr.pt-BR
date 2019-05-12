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
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Saiba como configurar o sistema de telefone para filas de chamada de nuvem para proporcionar um organizacional saudação, música de espera e redirecionando chamadas para chamar agentes em listas de distribuição e grupos de segurança. Você também pode definir o tamanho máximo da fila, o tempo limite e opções de manipulação de chamada.
ms.openlocfilehash: 844ea569da6f59def0ee4df7739456c1f10e7dff
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902867"
---
# <a name="create-a-cloud-call-queue"></a><span data-ttu-id="eed40-104">Criar uma fila de chamada do Cloud</span><span class="sxs-lookup"><span data-stu-id="eed40-104">Create a Cloud call queue</span></span>

<span data-ttu-id="eed40-105">Filas de chamada de nuvem incluem saudações que são usadas quando alguém ligar para um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar para o próximo operador chamada disponíveis lidar com a chamada enquanto as pessoas que são de chamada escutando música em espera.</span><span class="sxs-lookup"><span data-stu-id="eed40-105">Cloud call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="eed40-106">Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="eed40-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="eed40-107">Filas de chamada de nuvem podem fornecer:</span><span class="sxs-lookup"><span data-stu-id="eed40-107">Cloud call queues can provide:</span></span>
  
- <span data-ttu-id="eed40-108">Uma saudação organizacional.</span><span class="sxs-lookup"><span data-stu-id="eed40-108">An organizational greeting.</span></span>
- <span data-ttu-id="eed40-109">Música enquanto as pessoas estão aguardando espera.</span><span class="sxs-lookup"><span data-stu-id="eed40-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="eed40-110">Redirecionando de chamadas para operadores em listas de distribuição habilitado para email e grupos de segurança de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="eed40-111">Criação de configurações para o tamanho máximo da fila de chamada, tempo limite e opções de manipulação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="eed40-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="eed40-112">Quando alguém chama para um número de telefone que está associado uma fila de espera de chamada através da [conta do recurso](manage-resource-accounts.md), ele ouvirá uma saudação primeiro (se qualquer um estiver configurado) e, em seguida, eles serão colocados na fila e aguarde o próximo operador de chamada disponível.</span><span class="sxs-lookup"><span data-stu-id="eed40-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="eed40-113">A pessoa chamando em ouvirá música enquanto eles estão em espera aguardando e as chamadas serão oferecidas aos operadores na ordem *Primeiro na, primeiro Out* (FIFO) chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="eed40-114">Aguardando na fila de todas as chamadas serão distribuídas usando um dos seguintes métodos:</span><span class="sxs-lookup"><span data-stu-id="eed40-114">All calls waiting in the queue will be distributed using one of the following methods:</span></span>
  
- <span data-ttu-id="eed40-115">Com o Atendedor de roteamento, a primeira chamada na fila tocarão todos os operadores ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="eed40-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="eed40-116">Com o roteamento em série, a primeira chamada na fila tocarão todos os agentes de chamada um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="eed40-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
- <span data-ttu-id="eed40-117">Com o rodízio, roteamento de chamadas de entrada é balanceado para que cada agente de chamada receberá o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="eed40-117">With round robin, routing of incoming calls is balanced so that each call agent will get the same number of calls from the queue.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eed40-118">Agentes de chamada que estão **Offline**, tem definido sua presença como **Não incomodar** ou tem decidido para fora da fila de chamada não serão chamados.</span><span class="sxs-lookup"><span data-stu-id="eed40-118">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="eed40-119">Somente uma notificação de chamada recebida (para a chamada no topo da fila) ao mesmo tempo será enviada para os operadores de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-119">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="eed40-120">Depois que um agente de chamada aceita a chamada, a próxima chamada de entrada na fila será iniciado toques agentes de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-120">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="eed40-121">Este artigo se aplica ao Microsoft Teams e Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="eed40-121">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---get-started"></a><span data-ttu-id="eed40-122">Etapa 1 - Introdução</span><span class="sxs-lookup"><span data-stu-id="eed40-122">Step 1 - Get started</span></span>

<span data-ttu-id="eed40-123">Para começar a usar as filas de chamada, é importante lembrar algumas coisas:</span><span class="sxs-lookup"><span data-stu-id="eed40-123">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="eed40-124">Uma fila de espera de chamada é necessário ter uma conta de recurso associado.</span><span class="sxs-lookup"><span data-stu-id="eed40-124">A call queue is required to have an associated resource account.</span></span> <span data-ttu-id="eed40-125">Consulte [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) para obter detalhes sobre as contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="eed40-125">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="eed40-126">Se você planeja atribua um número de roteamento direto, você precisará adquirir e atribuir as seguintes licenças às suas contas de recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico\).</span><span class="sxs-lookup"><span data-stu-id="eed40-126">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="eed40-127">Se você estiver atribuindo um número de serviço da Microsoft em vez disso, você precisará adquirir e atribuir as seguintes licenças à sua conta do recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico e um plano de chamar\).</span><span class="sxs-lookup"><span data-stu-id="eed40-127">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="eed40-128">Você só precisa licenciar as contas de recursos com um número de telefone atribuído a eles.</span><span class="sxs-lookup"><span data-stu-id="eed40-128">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="eed40-129">Em uma fila de chamada e atendente automático aninhados, você não precisará licenciar o restante dos atendedores automáticos ou chamada filas se eles não tiverem números de telefone associados a eles.</span><span class="sxs-lookup"><span data-stu-id="eed40-129">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them.</span></span> 

> [!NOTE] 
> <span data-ttu-id="eed40-130">Números de serviço de roteamento diretos para filas de chamada e atendedor automático são suportados para os usuários do Microsoft Teams e operadores somente.</span><span class="sxs-lookup"><span data-stu-id="eed40-130">Direct Routing service numbers for auto attendant and call queues are supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE] 
> <span data-ttu-id="eed40-131">Microsoft está trabalhando em um modelo de licenciamento apropriado para aplicativos como atendedores automáticos de nuvem e filas de chamada, para agora você precisa usar o modelo de licenciamento por usuário.</span><span class="sxs-lookup"><span data-stu-id="eed40-131">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>

> [!NOTE]
> <span data-ttu-id="eed40-132">Para redirecionar chamadas para pessoas na sua organização que estiverem Online, eles devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem chamando de planos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="eed40-132">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="eed40-133">Consulte [Atribuir Skype para licenças de negócios](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) ou [equipes da Microsoft atribuir licenças](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="eed40-133">See  [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="eed40-134">Para habilitá-los para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eed40-134">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="eed40-135">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="eed40-135">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="eed40-136">Para saber mais sobre a chamada de planos do Office 365, consulte [sistema telefônico e chamar planos](calling-plan-landing-page.md) e [Chamar planos do Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="eed40-136">To learn more about Office 365 Calling Plans, see [Phone System and Calling Plans](calling-plan-landing-page.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

- <span data-ttu-id="eed40-137">Você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou transferidos do outro provedor de serviços para as filas de chamada de nuvem.</span><span class="sxs-lookup"><span data-stu-id="eed40-137">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Cloud call queues.</span></span> <span data-ttu-id="eed40-138">Para obter e usar números gratuitos de serviço, você precisará configurar créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="eed40-138">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eed40-139">Números de telefone do usuário (assinante) não podem ser atribuídos a chamada filas-apenas tarifas de serviço ou números de telefone gratuitos podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="eed40-139">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="eed40-140">Quando você estiver distribuindo as chamadas de entrada de uma fila de chamada de nuvem, esses clientes são suportados para os agentes de chamada:</span><span class="sxs-lookup"><span data-stu-id="eed40-140">When you are distributing the incoming calls from a Cloud call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="eed40-141">Skype para o cliente de desktop de negócios 2016 (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="eed40-141">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="eed40-142">Cliente de desktop do Lync 2013 (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="eed40-142">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="eed40-143">Todos os modelos de telefone IP, suportados for Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="eed40-143">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="eed40-144">Consulte [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="eed40-144">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online).</span></span>

  - <span data-ttu-id="eed40-145">Mac Skype para Business Client (versão 16.8.196 e posterior)</span><span class="sxs-lookup"><span data-stu-id="eed40-145">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="eed40-146">Skype Android para Business Client (versão 6.16.0.9 e posterior)</span><span class="sxs-lookup"><span data-stu-id="eed40-146">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="eed40-147">iPhone Skype para Business Client (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="eed40-147">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="eed40-148">iPad Skype para Business Client (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="eed40-148">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="eed40-149">Cliente do Microsoft Windows de equipes (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="eed40-149">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="eed40-150">Cliente do Microsoft equipes Mac</span><span class="sxs-lookup"><span data-stu-id="eed40-150">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="eed40-151">Microsoft Teams iPhone app</span><span class="sxs-lookup"><span data-stu-id="eed40-151">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="eed40-152">App Android de equipes da Microsoft</span><span class="sxs-lookup"><span data-stu-id="eed40-152">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="eed40-153">Etapa 2: obtendo ou transferência de Chamada Tarifada ou números de telefone de chamada gratuita do serviço</span><span class="sxs-lookup"><span data-stu-id="eed40-153">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="eed40-154">Antes de você poder criar e configurar as filas de chamada, será necessário receber ou transferir os números de serviço de chamada gratuita ou tarifada.</span><span class="sxs-lookup"><span data-stu-id="eed40-154">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="eed40-155">Após você fazer a chamada Tarifada ou números de telefone gratuitos de serviço, eles serão exibidas no **Centro de administração do Microsoft equipes** > **voz** > **números de telefone**e a disposição de **tipo de número** listado listada como **serviço - gratuito**.</span><span class="sxs-lookup"><span data-stu-id="eed40-155">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="eed40-156">Para obter seus números de serviço, consulte [Getting números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) ou se você deseja transferir um número existente de serviço, consulte [números de telefone de transferência para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="eed40-156">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="eed40-157">Se você estiver fora dos Estados Unidos, você não pode usar o Centro de administração do Microsoft Teams para obter os números de serviço.</span><span class="sxs-lookup"><span data-stu-id="eed40-157">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="eed40-158">Vá para [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo de fora dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="eed40-158">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="eed40-159">Se você estiver configurando atendedores automáticos, você só pode precisar atribuir um número de telefone a conta do recurso do atendedor automático principal e faça com que ele chamadores diretos para sua fila de espera de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-159">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="eed40-160">Se for esse o caso, a fila chamada precisará ser criados antes que você pode criar uma opção no atendedor automático que seleciona a fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-160">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="eed40-161">Etapa 3: criar uma nova fila de chamada</span><span class="sxs-lookup"><span data-stu-id="eed40-161">Step 3 - Create a new call queue</span></span>

[!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

> [!IMPORTANT]
> <span data-ttu-id="eed40-162">Cada fila de chamada é necessário ter uma [conta do recurso](manage-resource-accounts.md)de associada.</span><span class="sxs-lookup"><span data-stu-id="eed40-162">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="eed40-163">Você deve criar a conta do recurso primeiro, depois você pode associá-lo à fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-163">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="eed40-164">Usando o Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="eed40-164">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="eed40-165">No **Centro de administração de equipes da Microsoft**, **voz** >  **filas de chamada**, clique em **+ Adicionar novo**:</span><span class="sxs-lookup"><span data-stu-id="eed40-165">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="eed40-166">Definir a conta de recursos e o nome de exibição do fila chamada</span><span class="sxs-lookup"><span data-stu-id="eed40-166">Set the call queue display name and resource account</span></span>

![Configurando uma fila de espera de chamada.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="eed40-168">![Número 1](media/sfbcallout1.png)
**Name** Insira um nome de exibição descritivo para a fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-168">![Number 1](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="eed40-169">Isso é necessário e pode conter até 64 caracteres, incluindo espaços.</span><span class="sxs-lookup"><span data-stu-id="eed40-169">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="eed40-170">Esse nome será exibido na notificação para a chamada de entrada.</span><span class="sxs-lookup"><span data-stu-id="eed40-170">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="eed40-172">**Adicionar contas** Selecione uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="eed40-172">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="eed40-173">A conta do recurso pode ou não ser associada a um tarifas do serviço ou o número de telefone gratuitos para a fila de chamada, mas cada fila de chamada exige uma conta de recurso associado.</span><span class="sxs-lookup"><span data-stu-id="eed40-173">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="eed40-174">Se não existem quaisquer listado, você precisa obter os números de serviço e atribuí-las a uma conta de recursos antes de criar essa fila de espera de chamada, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="eed40-174">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="eed40-175">Para obter seus números de serviço, consulte [Getting números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span><span class="sxs-lookup"><span data-stu-id="eed40-175">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json).</span></span> <span data-ttu-id="eed40-176">Você precisará criar uma conta de recurso, conforme descrito em [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) se quiser que sua fila de chamada para ter um número de telefone associados.</span><span class="sxs-lookup"><span data-stu-id="eed40-176">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="eed40-177">Se você quer ou precisa atribuir um **domínio** você faria isso atribuindo-o para a conta do recurso para a fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-177">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="eed40-178">Definir a saudação e música tocado enquanto estiver em espera</span><span class="sxs-lookup"><span data-stu-id="eed40-178">Set the greeting and music played while on hold</span></span>

![Configurando uma fila de espera de chamada.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="eed40-181">**Saudação** é opcional.</span><span class="sxs-lookup"><span data-stu-id="eed40-181">**Greeting** is optional.</span></span> <span data-ttu-id="eed40-182">Esta é a saudação que será reproduzida para as pessoas que a chamada para o número de chamada da fila.</span><span class="sxs-lookup"><span data-stu-id="eed40-182">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="eed40-183">Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. wma).</span><span class="sxs-lookup"><span data-stu-id="eed40-183">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="eed40-185">**Música de espera** Você pode usar o padrão de música em espera fornecida com a fila chamada ou você pode carregar um arquivo de áudio nos formatos. wav, mp3 ou. wma a ser usado como sua música personalizada em espera.</span><span class="sxs-lookup"><span data-stu-id="eed40-185">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="eed40-186">Selecione as opções de atendimento de chamadas</span><span class="sxs-lookup"><span data-stu-id="eed40-186">Select the call answering options</span></span>

![Mostra a chamada opções de método de distribuição](media/5d249515-d532-4af2-90da-011404028b89.png)

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="eed40-189">Você pode selecionar até 200 agentes de chamada pertencentes a listas de mala direta especificadas ou grupos.</span><span class="sxs-lookup"><span data-stu-id="eed40-189">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="eed40-190">Agentes de chamada devem ser:</span><span class="sxs-lookup"><span data-stu-id="eed40-190">Call agents must be either:</span></span>

- <span data-ttu-id="eed40-191">Um usuário Online com uma licença de **Sistema telefônico** e habilitados para o Enterprise Voice ou com um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-191">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="eed40-192">Para redirecionar chamadas para pessoas na sua organização que estiverem Online, ele devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem um plano de chamar.</span><span class="sxs-lookup"><span data-stu-id="eed40-192">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="eed40-193">Consulte [Atribuir Skype para licenças de negócios](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [equipes da Microsoft atribuir licenças](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="eed40-193">See [Assign Skype for Business licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) or [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span>

 <span data-ttu-id="eed40-194">Para habilitá-los para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="eed40-194">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="eed40-195">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="eed40-195">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="eed40-196">Usuários online com uma licença de **Sistema telefônico** e um plano de chamada que são adicionados a um grupo do Office 365, uma lista de distribuição habilitado para email ou um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="eed40-196">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="eed40-197">Poderá demorar até 30 minutos para um novo operador adicionado para uma lista de distribuição ou um grupo de segurança para começar a receber chamadas de uma fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-197">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="eed40-198">Um grupo de segurança ou de lista de distribuição recém-criado pode levar até 48 horas para se tornar disponível para ser usado com filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-198">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="eed40-199">Recém-criadas grupos do Office 365 estão disponíveis quase imediatamente.</span><span class="sxs-lookup"><span data-stu-id="eed40-199">Newly created Office 365 Groups are available almost immediately.</span></span>

![Configure filas de chamada.](media/skype-for-business-add-agents-to-call-queue.png)

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="eed40-202">**Método de roteamento** Você pode escolher o **Attendant**, **Serial**ou **Round Robin** para seu método de distribuição de fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-202">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="eed40-203">Todas as filas de chamada novas e existentes terão roteamento attendant selecionada por padrão.</span><span class="sxs-lookup"><span data-stu-id="eed40-203">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="eed40-204">Quando o roteamento attendant é usado, a primeira chamada na fila tocarão todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="eed40-204">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="eed40-205">O agente de chamada primeiro para atender a chamada obtém a chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-205">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="eed40-206">**Roteamento Attendant** faz com que a primeira chamada na fila para ligar para todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="eed40-206">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="eed40-207">O agente de chamada primeiro para atender a chamada obtém a chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-207">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="eed40-208">**Roteamento em série** faz com que as chamadas recebidas toquem agentes de chamada um por um, começando do início da lista de agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="eed40-208">**Serial routing** causes incoming calls to ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="eed40-209">Se um operador descarta ou não atender uma chamada, a chamada tocará o próximo operador na lista e tentará todos os operadores gradativamente até que ele é buscado ou tempos de espera na fila.</span><span class="sxs-lookup"><span data-stu-id="eed40-209">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="eed40-210">Roteamento em série irá ignorar os operadores que estão **Offline**, tem definido sua presença como **Não incomodar**ou tem **retirado** de obtenção de chamadas da fila de espera.</span><span class="sxs-lookup"><span data-stu-id="eed40-210">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="eed40-211">**Rodízio** equilibra o roteamento de chamadas de entrada, de modo que cada agente de chamada receberá o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="eed40-211">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="eed40-212">Isso pode ser muito desejável em um ambiente de venda de entrada para garantir a oportunidade de igual entre todos os agentes de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-212">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="eed40-213">Selecione um operador rejeitar opção</span><span class="sxs-lookup"><span data-stu-id="eed40-213">Select an agent opt out option</span></span>

![Caixa de seleção mostra o agente rejeitar](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="eed40-216">**Agente rejeitar opção** Você pode optar por permitir que os agentes de fila de chamada recusar aproveitando chamadas a partir de uma determinada fila, selecionando a **Opção rejeitar agente**.</span><span class="sxs-lookup"><span data-stu-id="eed40-216">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="eed40-217">A habilitação dessa opção permite que todos os agentes na fila de espera para iniciar ou parar de receber chamadas dessa fila de espera de chamada em serão.</span><span class="sxs-lookup"><span data-stu-id="eed40-217">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="eed40-218">Você pode revogar os privilégios do operador recusar a qualquer momento, desmarcando a caixa de seleção, causando a se tornar aceitos automaticamente para essa fila novamente (configuração padrão para todos os agentes) agentes.</span><span class="sxs-lookup"><span data-stu-id="eed40-218">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="eed40-219">Para acessar a opção de recusar, operadores podem fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="eed40-219">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="eed40-220">Abrir **Opções** seu Skype da área de trabalho para o cliente de negócios.</span><span class="sxs-lookup"><span data-stu-id="eed40-220">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="eed40-221">Na guia **Encaminhamento de chamadas** , clique no link **Editar configurações online** .</span><span class="sxs-lookup"><span data-stu-id="eed40-221">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="eed40-222">Na página de configurações do usuário, clique em **Chamar filas**e desmarque as caixas de seleção para qualquer filas para o qual deseja rejeitar.</span><span class="sxs-lookup"><span data-stu-id="eed40-222">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="eed40-223">Agentes usando aplicativos ou pontos de extremidade diferente do Skype para Desktop de negócios pode acessar o consentimento check-out de opção do portal de configurações do usuário [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span><span class="sxs-lookup"><span data-stu-id="eed40-223">Agents using apps or endpoints other than Skype for Business Desktop can access the opt out option from the user settings portal [https://aka.ms/cqsettings](https://aka.ms/cqsettings).</span></span>

<span data-ttu-id="eed40-224">![Número 2](media/sfbcallout2.png)
**configuração de alerta de operador**</span><span class="sxs-lookup"><span data-stu-id="eed40-224">![Number 2](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="eed40-225">Isso define a duração de um operador que sejam notificado de uma chamada antes da série ou os métodos de roteamento Round Robin mova para o próximo operador.</span><span class="sxs-lookup"><span data-stu-id="eed40-225">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="eed40-226">A configuração padrão é 30 segundos, mas ela pode ser definida por até 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="eed40-226">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="eed40-227">Definir o excesso de chamada e o tempo limite opções de tratamento</span><span class="sxs-lookup"><span data-stu-id="eed40-227">Set the call overflow and timeout handling options</span></span>

![Configure uma fila de espera de chamada.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="eed40-230">**Máximo de chamadas na fila** Use esta opção para definir o máximo de chamadas que pode esperar na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="eed40-230">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="eed40-231">O valor padrão é 50, mas ela pode variar de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="eed40-231">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="eed40-232">Quando esse limite for atingido, a chamada será tratada de forma que você definiu na configuração **quando o número máximo de chamadas é atingido** abaixo.</span><span class="sxs-lookup"><span data-stu-id="eed40-232">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="eed40-234">**Quando o número máximo de chamadas é atingido** Quando a fila chamada atinge seu tamanho máximo (definido usando a configuração **máximo de chamadas na fila** ), você pode escolher o que acontece às novas chamadas de entrada.</span><span class="sxs-lookup"><span data-stu-id="eed40-234">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="eed40-235">**Desconectar** A chamada será desconectada.</span><span class="sxs-lookup"><span data-stu-id="eed40-235">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="eed40-236">**Redirecionar para** Quando você escolhe essa opção, selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="eed40-236">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="eed40-237">**Pessoa na sua empresa** Um usuário Online com uma licença de **Sistema telefônico** e ser habilitado para o Enterprise Voice ou ter um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-237">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="eed40-238">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="eed40-238">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="eed40-239">Para fazer isso, selecione uma **pessoa na sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="eed40-239">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="eed40-240">Para saber sobre o licenciamento necessários para a caixa postal, consulte [Configure a caixa postal de nuvem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="eed40-240">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="eed40-241">**Aplicativo de voz** Selecione o nome de qualquer um uma fila de espera de chamada ou que já tenha sido criado atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="eed40-241">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="eed40-243">**Tempo limite de chamada: tempo de espera máximo** Você também pode decidir quanto tempo uma chamada pode ser em espera na fila antes ele expire e precisa ser redirecionados ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="eed40-243">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="eed40-244">Onde ele será redirecionado baseia-se em como você pode definir a configuração **quando uma chamada expire** .</span><span class="sxs-lookup"><span data-stu-id="eed40-244">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="eed40-245">Você pode definir um tempo de 0 a 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="eed40-245">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="eed40-246">O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="eed40-246">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="eed40-247">Isso permite que você manipule o fluxo de chamadas com granularidade menor.</span><span class="sxs-lookup"><span data-stu-id="eed40-247">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="eed40-248">Por exemplo, você pode especificar que todas as chamadas não respondidas por um agente dentro de 30 segundos ir para um atendedor automático de pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="eed40-248">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="eed40-250">**Quando a chamada esgota** Quando a chamada alcança o limite definido na configuração de **quanto tempo uma chamada pode esperar na fila** , você pode escolher o que acontece com essa chamada:</span><span class="sxs-lookup"><span data-stu-id="eed40-250">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="eed40-251">**Desconectar** A chamada será desconectada.</span><span class="sxs-lookup"><span data-stu-id="eed40-251">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="eed40-252">**Redirecionar essa chamada para** Quando você escolhe essa opção, você terá estas opções:</span><span class="sxs-lookup"><span data-stu-id="eed40-252">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="eed40-253">**Pessoa na sua empresa** Um usuário Online com uma licença de **Sistema telefônico** e ser habilitado para o Enterprise Voice ou ter planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-253">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="eed40-254">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="eed40-254">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="eed40-255">Para fazer isso, selecione uma **pessoa na sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="eed40-255">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="eed40-256">Para saber sobre o licenciamento necessários para a caixa postal, consulte [Configure a caixa postal de nuvem](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="eed40-256">To learn about licensing required for voicemail, see [Set up Cloud Voicemail](set-up-phone-system-voicemail.md).</span></span>

  - <span data-ttu-id="eed40-257">**Aplicativo de voz** Selecione o nome de qualquer um uma fila de espera de chamada ou que já tenha sido criado atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="eed40-257">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-for-outbound-calls"></a><span data-ttu-id="eed40-258">Alterando o ID do usuário chamador para chamadas de saída</span><span class="sxs-lookup"><span data-stu-id="eed40-258">Changing a user's Caller ID for outbound calls</span></span> 

<span data-ttu-id="eed40-259">Você pode proteger a identidade de um usuário, alterando seu ID do chamador para chamadas de saída para uma fila de espera de chamada, atendedor automático ou qualquer número de serviço em vez disso, criando uma política utilizando o cmdlet **New-CsCallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="eed40-259">You can protect a user's identity by changing their caller ID for outbound calls to a call queue, auto attendant, or any service number instead by creating a policy using the **New-CsCallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="eed40-260">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="eed40-260">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="eed40-261">Aplica a política ao usuário usando o cmdlet **Grant-CallingLineIdentity** .</span><span class="sxs-lookup"><span data-stu-id="eed40-261">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="eed40-262">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="eed40-262">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="eed40-263">Você pode obter mais informações sobre como fazer alterações nas configurações de ID de chamador em sua organização no artigo [como ID do chamador pode ser usado na sua organização](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).</span><span class="sxs-lookup"><span data-stu-id="eed40-263">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="eed40-264">Deseja saber mais?</span><span class="sxs-lookup"><span data-stu-id="eed40-264">Want to know more?</span></span>

<span data-ttu-id="eed40-265">Você também pode usar o Windows PowerShell para criar e configurar filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-265">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="eed40-266">Cmdlets de fila de chamada</span><span class="sxs-lookup"><span data-stu-id="eed40-266">Call queue cmdlets</span></span>

<span data-ttu-id="eed40-267">Aqui estão os cmdlets que você precisa para gerenciar uma fila de espera de chamada.</span><span class="sxs-lookup"><span data-stu-id="eed40-267">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="eed40-268">New-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="eed40-268">New-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/new-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="eed40-269">Set-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="eed40-269">Set-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/set-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="eed40-270">Get-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="eed40-270">Get-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/get-CsCallQueue?view=skype-ps)

- [<span data-ttu-id="eed40-271">Remove-CsCallQueue</span><span class="sxs-lookup"><span data-stu-id="eed40-271">Remove-CsCallQueue</span></span>](https://docs.microsoft.com/powershell/module/skype/remove-CsCallQueue?view=skype-ps)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="eed40-272">Mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eed40-272">More about Windows PowerShell</span></span>

- <span data-ttu-id="eed40-273">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="eed40-273">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="eed40-274">Com o Windows PowerShell, você pode gerenciar o Office 365 e Microsoft Teams usando um único ponto de administração que pode simplificar o seu trabalho diário, quando você tem várias tarefas fazer.</span><span class="sxs-lookup"><span data-stu-id="eed40-274">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="eed40-275">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="eed40-275">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="eed40-276">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="eed40-276">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="eed40-277">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="eed40-277">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="eed40-278">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Microsoft Teams, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="eed40-278">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="eed40-279">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="eed40-279">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="eed40-280">Gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eed40-280">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="eed40-281">Configurar seu computador para o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="eed40-281">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="eed40-282">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="eed40-282">Related topics</span></span>

[<span data-ttu-id="eed40-283">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="eed40-283">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="eed40-284">Obter números de telefone de serviço</span><span class="sxs-lookup"><span data-stu-id="eed40-284">Getting service phone numbers</span></span>](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json)

[<span data-ttu-id="eed40-285">Disponibilidade de audioconferência e planos de chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="eed40-285">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="eed40-286">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="eed40-286">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
