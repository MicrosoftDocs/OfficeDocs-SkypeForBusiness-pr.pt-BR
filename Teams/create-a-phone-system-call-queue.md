---
title: Criar uma fila de chamada do Sistema de Telefonia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: phans, wasseemh
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Adm_Skype4B_Online
- Strat_SB_PSTN
- M365-voice
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: Learn how to set up phone system for Office 365 (Cloud PBX) call queues to give you an organizational greeting, music on hold, and redirecting calls to call agents in distribution lists and security groups. You can also set the maximum queue size, time out, and call handling options.
ms.openlocfilehash: 59054c1d73e002065db00ff1045ed8453fafa929
ms.sourcegitcommit: 59eda0c17ff39a3e6632810391d78bbadc214419
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/01/2019
ms.locfileid: "30351686"
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="1f5ed-104">Criar uma fila de chamada do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="1f5ed-104">Create a Phone System call queue</span></span>

<span data-ttu-id="1f5ed-105">Telefonema de sistema filas incluem saudações que são usadas quando alguém chama um número de telefone para sua organização, a capacidade de colocar automaticamente as chamadas em espera e a capacidade de pesquisar para o próximo operador chamada disponíveis lidar com a chamada enquanto as pessoas que chamada está escutando a música em espera.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-105">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="1f5ed-106">Você pode criar uma fila de chamadas única ou múltiplas para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="1f5ed-107">As filas de chamadas do Sistema de Telefonia oferecem:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="1f5ed-108">Uma saudação organizacional.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-108">An organizational greeting.</span></span>
- <span data-ttu-id="1f5ed-109">Música enquanto a pessoa estiver aguardando em espera.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-109">Music while people are waiting on hold.</span></span>
- <span data-ttu-id="1f5ed-110">Redirecionando de chamadas para operadores em listas de distribuição habilitado para email e grupos de segurança de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
- <span data-ttu-id="1f5ed-111">Criação de configurações para o tamanho máximo da fila de chamada, tempo limite e opções de manipulação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>

<span data-ttu-id="1f5ed-112">Quando alguém chama para um número de telefone que está associado uma fila de espera de chamada através da [conta do recurso](manage-resource-accounts.md), ele ouvirá uma saudação primeiro (se qualquer um estiver configurado) e, em seguida, eles serão colocados na fila e aguarde o próximo operador de chamada disponível.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-112">When someone calls in to a phone number that is associated  with a call queue via a [resource account](manage-resource-accounts.md), they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="1f5ed-113">A pessoa chamando em ouvirá música enquanto eles estão em espera aguardando e as chamadas serão oferecidas aos operadores na ordem *Primeiro na, primeiro Out* (FIFO) chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in *First In, First Out* (FIFO) order.</span></span>
  
<span data-ttu-id="1f5ed-114">Aguardando na fila de todas as chamadas serão distribuídas usando um modo de roteamento attendant ou o modo serial de roteamento:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="1f5ed-115">Com o Atendedor de roteamento, a primeira chamada na fila tocarão todos os operadores ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
- <span data-ttu-id="1f5ed-116">Com o encaminhamento em série, a primeira chamada da fila chama todos os agentes, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f5ed-117">Agentes de chamada que estão **Offline**, definiram sua presença como **Não incomodar** ou optaram por não serem incluídos na fila de chamadas e, portanto, não serão chamados.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="1f5ed-118">Somente uma notificação de chamada de entrada (para a chamada no início da fila) de cada vez será enviada para os agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
- <span data-ttu-id="1f5ed-119">Depois que um agente aceita a chamada, a próxima chamada de entrada na fila começará a tocar para os agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>

> [!NOTE]
> <span data-ttu-id="1f5ed-120">Este artigo se aplica ao Microsoft Teams e Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-120">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="step-1---getting-started"></a><span data-ttu-id="1f5ed-121">Etapa 1 - Introdução</span><span class="sxs-lookup"><span data-stu-id="1f5ed-121">Step 1 - Getting started</span></span>

<span data-ttu-id="1f5ed-122">Para começar a usar as filas de chamadas, é importante lembrar-se de que:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-122">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="1f5ed-123">Sua organização deve ter (no mínimo), uma licença Enterprise E3 plus **Sistema telefônico** ou uma licença Enterprise E5.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-123">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license.</span></span> <span data-ttu-id="1f5ed-124">O número de licenças de usuário do **Sistema telefônico** atribuídos afeta o número de números de serviço que estão disponíveis para serem usados para as filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-124">The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues.</span></span> <span data-ttu-id="1f5ed-125">O número de filas de chamada, que você pode ter é dependente do número de licenças de **Sistema telefônico** e **Conferência de áudio** que são atribuídas em sua organização.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-125">The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization.</span></span> <span data-ttu-id="1f5ed-126">Para saber mais sobre o licenciamento, consulte [Skype para licenciamento de complemento de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-126">To learn more about licensing, see [Skype for Business and Microsoft Teams add-on licensing](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f5ed-127">Para redirecionar chamadas para pessoas na sua organização que estiverem Online, eles devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem chamando de planos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-127">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="1f5ed-128">Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-128">See  [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span> <span data-ttu-id="1f5ed-129">Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-129">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="1f5ed-130">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="1f5ed-130">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="1f5ed-131">Para saber mais sobre os Planos de Chamadas do Office 365, consulte [O que são os Planos de Chamadas do Office 365?](what-are-calling-plans-in-office-365.md) e [Planos de Chamadas para Office 365](calling-plans-for-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-131">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](what-are-calling-plans-in-office-365.md) and [Calling Plans for Office 365](calling-plans-for-office-365.md).</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f5ed-132">Usuários hospedados no local usando o Lync Server 2010 não são suportados como uma fila de chamada agentes.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-132">Users hosted on-premises using Lync Server 2010 aren't supported as a call queue Agents.</span></span>
  
- <span data-ttu-id="1f5ed-133">Você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou transferidos do outro provedor de serviços para as filas de chamada do sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-133">You can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to Phone System call queues.</span></span> <span data-ttu-id="1f5ed-134">Para obter e usar números de serviço gratuitos, você precisa configurar Créditos de Comunicações.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-134">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f5ed-135">[!OBSERVAçãO] Os números de telefone (assinante) não podem ser atribuídos às filas de chamada  somente números de telefone de serviço chamadas gratuitas ou tarifas podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-135">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span>
  
- <span data-ttu-id="1f5ed-136">Quando você estiver distribuindo as chamadas de entrada de uma fila de espera de chamada de sistema telefônico, esses clientes são suportados para os agentes de chamada:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-136">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>

  - <span data-ttu-id="1f5ed-137">Cliente de desktop Skype for Business 2016 (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="1f5ed-137">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="1f5ed-138">Cliente de desktop Lync 2013 (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="1f5ed-138">Lync desktop client 2013 (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="1f5ed-139">Todos os modelos de telefone IP, suportados for Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-139">All IP phone models supported for Microsoft Teams.</span></span> <span data-ttu-id="1f5ed-140">Consulte [Obter telefones para o Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-140">See [Getting phones for Skype for Business Online](/skypeforbusiness/what-is-phone-system-in-office-365/getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>

  - <span data-ttu-id="1f5ed-141">Cliente Mac do Skype for Business (versão 16.8.196 e posterior)</span><span class="sxs-lookup"><span data-stu-id="1f5ed-141">Mac Skype for Business Client (version 16.8.196 and later)</span></span>

  - <span data-ttu-id="1f5ed-142">Cliente Android do Skype for Business (versão 6.16.0.9 e posterior)</span><span class="sxs-lookup"><span data-stu-id="1f5ed-142">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>

  - <span data-ttu-id="1f5ed-143">Cliente iPhone do Skype for Business (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="1f5ed-143">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="1f5ed-144">Cliente iPad do Skype for Business (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="1f5ed-144">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="1f5ed-145">Cliente do Windows para Microsoft Teams (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="1f5ed-145">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="1f5ed-146">Cliente Mac para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f5ed-146">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="1f5ed-147">Aplicativo do Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="1f5ed-147">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="1f5ed-148">Aplicativo do Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="1f5ed-148">Microsoft Teams Android app</span></span>

## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="1f5ed-149">Etapa 2 - Como adquirir e transferir números de telefone de serviço de chamada gratuita ou tarifada</span><span class="sxs-lookup"><span data-stu-id="1f5ed-149">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="1f5ed-150">Antes de você poder criar e configurar as filas de chamada, será necessário receber ou transferir os números de serviço de chamada gratuita ou tarifada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-150">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="1f5ed-151">Após você fazer a chamada Tarifada ou números de telefone gratuitos de serviço, eles serão exibidas no **Centro de administração do Microsoft equipes** > **voz** > **números de telefone**e a disposição de **tipo de número** listado listada como **serviço - gratuito**.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-151">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="1f5ed-152">Para obter seus números de serviço, consulte [Getting números de telefone de serviço](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) ou se você deseja transferir um número existente de serviço, consulte [números de telefone de transferência para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-152">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1f5ed-153">Se você estiver fora dos Estados Unidos, você não pode usar o Centro de administração do Microsoft Teams para obter os números de serviço.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-153">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="1f5ed-154">Vá para [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo de fora dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-154">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

<span data-ttu-id="1f5ed-155">Se você estiver configurando atendedores automáticos, você só pode precisar atribuir um número de telefone a conta do recurso do atendedor automático principal e faça com que ele chamadores diretos para sua fila de espera de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-155">If you are also setting up auto attendants, you may only need to assign a phone number to the main auto attendant's resource account, and then have it direct callers to your call queue.</span></span> <span data-ttu-id="1f5ed-156">Se for esse o caso, a fila chamada precisará ser criados antes que você pode criar uma opção no atendedor automático que seleciona a fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-156">If that's the case, the call queue will need to be created before you can create an option in the auto attendant that selects the call queue.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="1f5ed-157">Etapa 3: criar uma nova fila de chamada</span><span class="sxs-lookup"><span data-stu-id="1f5ed-157">Step 3 - Create a new call queue</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1f5ed-158">Cada fila de chamada é necessário ter uma [conta do recurso](manage-resource-accounts.md)de associada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-158">Every call queue is required to have an associated [resource account](manage-resource-accounts.md).</span></span> <span data-ttu-id="1f5ed-159">Você deve criar a conta do recurso primeiro, depois você pode associá-lo à fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-159">You must create the resource account first, then you can associate it to the call queue.</span></span>

### <a name="using-the-microsoft-teams-admin-center"></a><span data-ttu-id="1f5ed-160">Usando o Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f5ed-160">Using the Microsoft Teams admin center</span></span>

<span data-ttu-id="1f5ed-161">No **Centro de administração de equipes da Microsoft**, **voz** >  **filas de chamada**, clique em **+ Adicionar novo**:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-161">In the **Microsoft Teams admin center**, **Voice** >  **Call queues**, then click **+ Add new**:</span></span>

### <a name="set-the-call-queue-display-name-and-resource-account"></a><span data-ttu-id="1f5ed-162">Definir a conta de recursos e o nome de exibição do fila chamada</span><span class="sxs-lookup"><span data-stu-id="1f5ed-162">Set the call queue display name and resource account</span></span>

![Setting up a call queue.](media/37ecc300-a108-4294-8463-fce570dfce72.png)

* * *

<span data-ttu-id="1f5ed-164">![Número 1](media/sfbcallout1.png)
**Name** Insira um nome de exibição descritivo para a fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-164">![Number 1](media/sfbcallout1.png)
**Name** Enter a descriptive display name for the call queue.</span></span> <span data-ttu-id="1f5ed-165">Esse nome é obrigatório e pode conter até 64 caracteres, incluindo espaços.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-165">This is required and can contain up to 64 characters, including spaces.</span></span>

 <span data-ttu-id="1f5ed-166">Esse nome será exibido na notificação da chamada de entrada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-166">This name will be displayed in the notification for the incoming call.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="1f5ed-168">**Adicionar contas** Selecione uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-168">**Add Accounts** Select a resource account.</span></span> <span data-ttu-id="1f5ed-169">A conta do recurso pode ou não ser associada a um tarifas do serviço ou o número de telefone gratuitos para a fila de chamada, mas cada fila de chamada exige uma conta de recurso associado.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-169">The resource account may or may not be associated with a service toll or toll-free phone number for the call queue, but each call queue requires an associated resource account.</span></span>

<span data-ttu-id="1f5ed-170">Se não existem quaisquer listado, você precisa obter os números de serviço e atribuí-las a uma conta de recursos antes de criar essa fila de espera de chamada, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-170">If there aren't any listed, you need to get service numbers and assign them to a Resource account before you can create this call queue, as described earlier.</span></span> <span data-ttu-id="1f5ed-171">Para obter seus números de serviço, consulte [Getting números de telefone de serviço](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-171">To get your service numbers, see [Getting service phone numbers](/skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md).</span></span> <span data-ttu-id="1f5ed-172">Você precisará criar uma conta de recurso, conforme descrito em [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) se quiser que sua fila de chamada para ter um número de telefone associados.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-172">You'll need to create a resource account as described in [Manage resource accounts in Teams](manage-resource-accounts.md) if you want your call queue to have an associated phone number.</span></span>

> [!NOTE]
> <span data-ttu-id="1f5ed-173">Se você quer ou precisa atribuir um **domínio** você faria isso atribuindo-o para a conta do recurso para a fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-173">If you want or need to assign a **Domain** you would do so by assigning it to the resource account for the call queue.</span></span>

### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="1f5ed-174">Definir a saudação e a música reproduzida durante a espera</span><span class="sxs-lookup"><span data-stu-id="1f5ed-174">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](media/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="1f5ed-177">**Saudação** é opcional.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-177">**Greeting** is optional.</span></span> <span data-ttu-id="1f5ed-178">Esta é a saudação que será reproduzida para as pessoas que a chamada para o número de chamada da fila.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-178">This is the greeting that is played for people who call in to the call queue number.</span></span>

<span data-ttu-id="1f5ed-179">Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. wma).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-179">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="1f5ed-181">**Música de espera** Você pode usar o padrão de música em espera fornecida com a fila chamada ou você pode carregar um arquivo de áudio nos formatos. wav, mp3 ou. wma a ser usado como sua música personalizada em espera.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-181">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span>

* * *

### <a name="select-the-call-answering-options"></a><span data-ttu-id="1f5ed-182">Selecione as opções de atendimento de chamadas</span><span class="sxs-lookup"><span data-stu-id="1f5ed-182">Select the call answering options</span></span>

![Mostra as opções de métodos de distribuição de chamadas](media/5d249515-d532-4af2-90da-011404028b89.png)

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="1f5ed-185">Você pode selecionar até 200 agentes de chamada pertencentes a listas de mala direta especificadas ou grupos.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-185">You can select up to 200 call agents belonging to specified mailing lists or groups.</span></span> <span data-ttu-id="1f5ed-186">Agentes de chamada devem ser:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-186">Call agents must be either:</span></span>

- <span data-ttu-id="1f5ed-187">Um usuário Online com uma licença de **Sistema de Telefonia** e habilitados para o Enterprise Voice ou com um Plano de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-187">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1f5ed-188">Para redirecionar chamadas para pessoas na sua organização que estiverem Online, ele devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem um plano de chamar.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-188">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="1f5ed-189">Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-189">See [Assign Skype for Business and Microsoft Teams licenses](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md).</span></span>

 <span data-ttu-id="1f5ed-190">Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-190">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="1f5ed-191">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="1f5ed-191">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

- <span data-ttu-id="1f5ed-192">Usuários online com uma licença de **Sistema de Telefonia** e um Plano de Chamadas que são adicionados a um grupo do Office 365, uma lista de distribuição habilitada para e-mails ou um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-192">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group.</span></span> <span data-ttu-id="1f5ed-193">Poderá demorar até 30 minutos para que um novo agente adicionado a uma lista de distribuição ou um grupo de segurança comece a receber chamadas de uma fila.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-193">It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue.</span></span> <span data-ttu-id="1f5ed-194">Um grupo de segurança ou de lista de distribuição recém-criado pode levar até 48 horas para se tornar disponível para ser usado com filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-194">A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues.</span></span> <span data-ttu-id="1f5ed-195">Grupos recém-criados do Office 365 ficam disponíveis quase que imediatamente.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-195">Newly created Office 365 Groups are available almost immediately.</span></span>

  > [!NOTE]
  > <span data-ttu-id="1f5ed-196">Usuários hospedados no local usando o Lync Server 2010 não são suportados.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-196">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>

![Set up call queues.](media/skype-for-business-add-agents-to-call-queue.png)

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="1f5ed-199">**Método de roteamento** Você pode escolher o **Attendant**, **Serial**ou **Round Robin** para seu método de distribuição de fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-199">**Routing method** You can choose either **Attendant**,  **Serial**, or **Round Robin** for your call queue distribution method.</span></span> <span data-ttu-id="1f5ed-200">Todas as filas de chamadas novas e existentes terão encaminhamento para o atendedor como padrão.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-200">All new and existing call queues will have attendant routing selected by default.</span></span> <span data-ttu-id="1f5ed-201">Quando o roteamento attendant é usado, a primeira chamada na fila tocarão todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-201">When attendant routing is used, the first call in the queue will ring all of the call agents at the same time.</span></span> <span data-ttu-id="1f5ed-202">O agente de chamada primeiro para atender a chamada obtém a chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-202">The first call agent to pick up the call gets the call.</span></span>

- <span data-ttu-id="1f5ed-203">**Roteamento Attendant** faz com que a primeira chamada na fila para ligar para todos os agentes de chamada ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-203">**Attendant routing** causes the first call in the queue to ring all call agents at the same time.</span></span> <span data-ttu-id="1f5ed-204">O agente de chamada primeiro para atender a chamada obtém a chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-204">The first call agent to pick up the call gets the call.</span></span>
- <span data-ttu-id="1f5ed-205">**Roteamento em série** faz com que as chamadas recebidas toquem agentes de chamada um por um, começando do início da lista de agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-205">**Serial routing** causes incoming calls to ring call agents one by one, starting from the beginning of the call agent list.</span></span> <span data-ttu-id="1f5ed-206">Se um agente ignora ou não atende uma chamada, ela passa para o próximo operador da lista, tentando cada agente, um por um, até que seja atendida ou exceda o tempo de espera na fila.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-206">If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>
  > [!NOTE]
  > <span data-ttu-id="1f5ed-207">O encaminhamento em série ignora agentes que estão **Offline**, com a presença definida como **Não incomodar** ou que **recusaram** receber chamadas da fila de espera.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-207">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span>
- <span data-ttu-id="1f5ed-208">**Rodízio** equilibra o roteamento de chamadas de entrada, de modo que cada agente de chamada receberá o mesmo número de chamadas da fila.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-208">**Round robin** balances routing of incoming calls so that each call agent will get the same number of calls from the queue.</span></span> <span data-ttu-id="1f5ed-209">Isso pode ser muito desejável em um ambiente de venda de entrada para garantir a oportunidade de igual entre todos os agentes de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-209">This may be very desirable in an inbound sales environment to assure equal opportunity among all the call agents.</span></span>

### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="1f5ed-210">Selecionar uma opção de recusa do agente</span><span class="sxs-lookup"><span data-stu-id="1f5ed-210">Select an agent opt out option</span></span>

![Exibe a caixa de seleção de recusa para o agente](media/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="1f5ed-213">**Opção de recusa do agente** Você pode optar por permitir que os agentes se recusem a receber chamadas de uma determinada fila selecionando a **Opção de recusa do agente**.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-213">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>

<span data-ttu-id="1f5ed-214">A habilitação dessa opção permite que todos os agentes na fila de espera para iniciar ou parar de receber chamadas dessa fila de espera de chamada em serão.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-214">Enabling this option allows all agents in this queue to start or stop receiving calls from this call queue at will.</span></span> <span data-ttu-id="1f5ed-215">Você pode revogar os privilégios de recusa do agente a qualquer momento desmarcando a caixa de seleção, o que faz com que eles automaticamente aceitem participar da fila novamente (configuração padrão para todos os agentes).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-215">You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).</span></span>

<span data-ttu-id="1f5ed-216">Para acessar a opção de recusa, os agentes podem:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-216">To access the opt-out option, agents can do the following:</span></span>

 1. <span data-ttu-id="1f5ed-217">Abrir as **Opções** no cliente Skype for Business na área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-217">Open **Options** in their desktop Skype for Business client.</span></span>
 2. <span data-ttu-id="1f5ed-218">Na guia **Encaminhamento de chamadas**, clicar no link **Editar configurações online**.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-218">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="1f5ed-219">Na página de configurações do usuário, clicar em **Filas de Chamadas**e desmarcar as caixas de seleção de todas as filas que desejam recusar.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-219">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>

    > [!NOTE]
    > <span data-ttu-id="1f5ed-220">Agentes que usam clientes Mac, móveis ou do Lync 2013 ou usuários Hybrid Voice hospedados no local usando o servidor Skype for Business 2015, podem ir em [https://aka.ms/cqsettings](https://aka.ms/cqsettings) para acessar a opção de recusa.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-220">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>

<span data-ttu-id="1f5ed-221">![Número 2](media/sfbcallout2.png)
**configuração de alerta de operador**</span><span class="sxs-lookup"><span data-stu-id="1f5ed-221">![Number 2](media/sfbcallout2.png)
**Agent Alert setting**</span></span>

<span data-ttu-id="1f5ed-222">Isso define a duração de um operador que sejam notificado de uma chamada antes da série ou os métodos de roteamento Round Robin mova para o próximo operador.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-222">This defines the duration of an agent being notified of a call before the Serial or Round Robin routing methods move to the next agent.</span></span>

<span data-ttu-id="1f5ed-223">A configuração padrão é 30 segundos, mas ela pode ser definida por até 3 minutos.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-223">The default setting is 30 seconds, but it can be set for up to 3 minutes.</span></span>

* * *

### <a name="set-the-call-overflow-and-timeout-handling-options"></a><span data-ttu-id="1f5ed-224">Definir o excesso de chamada e o tempo limite opções de tratamento</span><span class="sxs-lookup"><span data-stu-id="1f5ed-224">Set the call overflow and timeout handling options</span></span>

![Set up a call queue.](media/3f018734-16fe-458b-827d-71fc25155cde.png)
  
* * *

![Número 1](media/sfbcallout1.png)

<span data-ttu-id="1f5ed-227">**Máximo de chamadas na fila** Use isso para definir o tempo máximo que as chamadas podem esperar na fila ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-227">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time.</span></span> <span data-ttu-id="1f5ed-228">O valor padrão é 50, mas ela pode variar de 0 a 200.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-228">The default is 50, but it can range from 0 to 200.</span></span> <span data-ttu-id="1f5ed-229">Quando esse limite for alcançado, a chamada será tratada da forma como você definiu na configuração **Quando o número máximo de chamadas é alcançado** abaixo.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-229">When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>

* * *

![Número 2](media/sfbcallout2.png)

<span data-ttu-id="1f5ed-231">**Quando o número máximo de chamadas é atingido** Quando a fila chamada atinge seu tamanho máximo (definido usando a configuração **máximo de chamadas na fila** ), você pode escolher o que acontece às novas chamadas de entrada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-231">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>

- <span data-ttu-id="1f5ed-232">**Desconectar** A chamada será desconectada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-232">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="1f5ed-233">**Redirecionar para** Quando você escolhe essa opção, selecione uma destas opções:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-233">**Redirect to** When you choose this, select one of the following:</span></span>

  - <span data-ttu-id="1f5ed-234">**Pessoa na sua empresa** Um usuário Online com uma licença de **Sistema telefônico** e ser habilitado para o Enterprise Voice ou ter um plano de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-234">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan.</span></span> <span data-ttu-id="1f5ed-235">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-235">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="1f5ed-236">Para fazer isso, selecione uma **pessoa na sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-236">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="1f5ed-237">Para saber sobre o licenciamento necessário para a caixa postal, consulte [Configurar caixa postal do Sistema de Telefonia](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-237">To learn about licensing required for voicemail, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>

    > [!Note]
    > <span data-ttu-id="1f5ed-238">Usuários hospedados no local usando o Lync Server 2010 não são suportados.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-238">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>
  - <span data-ttu-id="1f5ed-239">**Aplicativo de voz** Selecione o nome de qualquer um uma fila de espera de chamada ou que já tenha sido criado atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-239">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

* * *

![Número 3](media/sfbcallout3.png)

<span data-ttu-id="1f5ed-241">**Tempo limite de chamada: tempo de espera máximo** Você também pode decidir quanto tempo uma chamada pode ser em espera na fila antes ele expire e precisa ser redirecionados ou desconectada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-241">**Call Timeout: maximum wait time** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected.</span></span> <span data-ttu-id="1f5ed-242">Para onde ela será direcionada dependerá da configuração da opção **Quando uma chamada atinge o tempo limite.**</span><span class="sxs-lookup"><span data-stu-id="1f5ed-242">Where it will be redirected is based on how you set the **When a call times out** setting.</span></span> <span data-ttu-id="1f5ed-243">Você pode definir um período de 0 a 45 minutos.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-243">You can set a time from 0 to 45 minutes.</span></span>

<span data-ttu-id="1f5ed-244">O valor de tempo limite pode ser definido em segundos, em intervalos de 15 segundos.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-244">The timeout value can be set in seconds, at 15-second intervals.</span></span> <span data-ttu-id="1f5ed-245">Isso permite que você administre o fluxo de chamadas com mais precisão.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-245">This allows you to manipulate the call flow with finer granularity.</span></span> <span data-ttu-id="1f5ed-246">Por exemplo, você pode especificar que todas as chamadas não respondidas por um agente dentro de 30 segundos ir para um atendedor automático de pesquisa de diretório.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-246">For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search auto attendant.</span></span>

![Número 4](media/sfbcallout4.png)

<span data-ttu-id="1f5ed-248">**Quando a chamada esgota** Quando a chamada alcança o limite definido na configuração de **quanto tempo uma chamada pode esperar na fila** , você pode escolher o que acontece com essa chamada:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-248">**When call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>

- <span data-ttu-id="1f5ed-249">**Desconectar** A chamada será desconectada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-249">**Disconnect** The call will be disconnected.</span></span>
- <span data-ttu-id="1f5ed-250">**Redirecionar essa chamada para** Quando você escolhe essa opção, você terá estas opções:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-250">**Redirect this call to** When you choose this, you will have these options:</span></span>
  - <span data-ttu-id="1f5ed-251">**Pessoa na sua empresa** Um usuário Online com uma licença de **Sistema telefônico** e ser habilitado para o Enterprise Voice ou ter planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-251">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans.</span></span> <span data-ttu-id="1f5ed-252">Você pode configurá-lo para que o chamador possa ser enviado para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-252">You can set it up so the person calling in can be sent to voicemail.</span></span> <span data-ttu-id="1f5ed-253">Para fazer isso, selecione uma **pessoa na sua empresa** e defina essa pessoa para que suas chamadas encaminhadas diretamente para a caixa postal.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-253">To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail.</span></span>

  <span data-ttu-id="1f5ed-254">Para saber sobre o licenciamento necessário para a caixa postal, consulte [Configurar caixa postal do Sistema de Telefonia](set-up-phone-system-voicemail.md).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-254">To learn about licensing required for voicemail, see [Set up Phone System voicemail](set-up-phone-system-voicemail.md).</span></span>

    > [!Note]
    > <span data-ttu-id="1f5ed-255">Usuários hospedados no local usando o Lync Server 2010 não são suportados.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-255">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>

  - <span data-ttu-id="1f5ed-256">**Aplicativo de voz** Selecione o nome de qualquer um uma fila de espera de chamada ou que já tenha sido criado atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-256">**Voice application** Select the name of either a call queue or auto attendant that has already been created.</span></span>

## <a name="changing-a-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="1f5ed-257">Alterar a ID de chamadas de um usuário para ser um número de telefone da chamada de uma fila</span><span class="sxs-lookup"><span data-stu-id="1f5ed-257">Changing a user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="1f5ed-258">Você pode proteger a identidade de um usuário alterando a identificação de chamadas dele para chamadas de saída para uma fila de chamadas criando uma política com o cmdlet **New-CallingLineIdentity**.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-258">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>

<span data-ttu-id="1f5ed-259">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-259">To do this, run:</span></span>

``` Powershell
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="1f5ed-260">Então, aplique a política ao usuário usando o cmdlet **Grant-CallingLineIdentity**.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-260">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet.</span></span> <span data-ttu-id="1f5ed-261">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-261">To do this, run:</span></span>
  
``` Powershell
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="1f5ed-262">Você pode obter mais informações sobre como fazer alterações nas configurações de ID de chamador em sua organização no artigo [como ID do chamador pode ser usado na sua organização](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="1f5ed-262">You can get more information on how to make changes to caller ID settings in your organization in the article [How can caller ID be used in your organization](/skypeforbusiness/what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="1f5ed-263">Deseja saber mais?</span><span class="sxs-lookup"><span data-stu-id="1f5ed-263">Want to know more?</span></span>

<span data-ttu-id="1f5ed-264">Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-264">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="1f5ed-265">Cmdlets da fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="1f5ed-265">Call queue cmdlets</span></span>

<span data-ttu-id="1f5ed-266">Veja os cmdlets necessários para gerenciar uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-266">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="1f5ed-267">New-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="1f5ed-267">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)

- [<span data-ttu-id="1f5ed-268">Set-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="1f5ed-268">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)

- [<span data-ttu-id="1f5ed-269">Get-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="1f5ed-269">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)

- [<span data-ttu-id="1f5ed-270">Remove-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="1f5ed-270">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)

### <a name="more-about-windows-powershell"></a><span data-ttu-id="1f5ed-271">Mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f5ed-271">More about Windows PowerShell</span></span>

- <span data-ttu-id="1f5ed-272">O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-272">Windows PowerShell is all about managing users and what users are allowed or not allowed to do.</span></span> <span data-ttu-id="1f5ed-273">Com o Windows PowerShell, você pode gerenciar o Office 365 e Microsoft Teams usando um único ponto de administração que pode simplificar o seu trabalho diário, quando você tem várias tarefas fazer.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-273">With Windows PowerShell, you can manage Office 365 and Microsoft Teams using a single point of administration that can simplify your daily work, when you have multiple tasks to do.</span></span> <span data-ttu-id="1f5ed-274">Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-274">To get started with Windows PowerShell, see these topics:</span></span>

  - [<span data-ttu-id="1f5ed-275">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="1f5ed-275">An introduction to Windows PowerShell and Skype for Business Online</span></span>](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [<span data-ttu-id="1f5ed-276">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="1f5ed-276">Why you need to use Office 365 PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/why-you-need-to-use-office-365-powershell)

- <span data-ttu-id="1f5ed-277">Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Microsoft Teams, como quando você estiver fazendo alterações de configuração de muitos usuários de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="1f5ed-277">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Microsoft Teams admin center such as when you are making setting changes for many users at one time.</span></span> <span data-ttu-id="1f5ed-278">Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="1f5ed-278">Learn about these advantages in the following topics:</span></span>

  - [<span data-ttu-id="1f5ed-279">Gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f5ed-279">Manage Office 365 with Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/office365/enterprise/powershell/manage-office-365-with-office-365-powershell)

  - [<span data-ttu-id="1f5ed-280">Configurar seu computador para o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f5ed-280">Set up your computer for Windows PowerShell</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

## <a name="related-topics"></a><span data-ttu-id="1f5ed-281">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="1f5ed-281">Related topics</span></span>

[<span data-ttu-id="1f5ed-282">Veja aqui o que você obtém com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="1f5ed-282">Here's what you get with Phone System in Office 365</span></span>](here-s-what-you-get-with-phone-system.md)

[<span data-ttu-id="1f5ed-283">Obter números de telefones de serviço</span><span class="sxs-lookup"><span data-stu-id="1f5ed-283">Getting service phone numbers</span></span>](/Skypeforbusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers.md)

[<span data-ttu-id="1f5ed-284">Disponibilidade de Audioconferência e Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="1f5ed-284">Country and region availability for Audio Conferencing and Calling Plans</span></span>](country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans.md)

[<span data-ttu-id="1f5ed-285">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="1f5ed-285">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
