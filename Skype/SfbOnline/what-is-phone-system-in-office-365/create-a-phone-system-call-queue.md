---
title: Criar uma fila de chamadas do Sistema de Telefonia
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: makolomi
ms.topic: article
ms.assetid: 67ccda94-1210-43fb-a25b-7b9785f8a061
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Phone System
description: 'Saiba como configurar filas de chamadas para o Sistema de Telefonia do Office 365 (Cloud PBX) de modo a ter uma saudação da sua organização, música de espera e redirecionamento de chamadas para agentes em listas de distribuição e grupos de segurança. Você também pode definir o tamanho máximo da fila, o tempo limite e opções de administração de chamadas. '
ms.openlocfilehash: 1952d6d180f5b9662b1e598ceb9d0b8d230640c2
ms.sourcegitcommit: dd37c12a0312270955755ab2826adcfbae813790
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/04/2018
ms.locfileid: "25375145"
---
# <a name="create-a-phone-system-call-queue"></a><span data-ttu-id="4044a-104">Criar uma fila de chamadas do Sistema de Telefonia</span><span class="sxs-lookup"><span data-stu-id="4044a-104">Create a Phone System call queue</span></span>

<span data-ttu-id="4044a-105">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span><span class="sxs-lookup"><span data-stu-id="4044a-105">Phone System call queues include greetings that are used when someone calls in to a phone number for your organization, the ability to automatically put the calls on hold, and the ability to search for the next available call agent to handle the call while the people who call are listening to music on hold.</span></span> <span data-ttu-id="4044a-106">You can create single or multiple call queues for your organization.</span><span class="sxs-lookup"><span data-stu-id="4044a-106">You can create single or multiple call queues for your organization.</span></span>
  
<span data-ttu-id="4044a-107">As filas de chamadas do Sistema de Telefonia oferecem:</span><span class="sxs-lookup"><span data-stu-id="4044a-107">Phone System call queues can provide:</span></span>
  
- <span data-ttu-id="4044a-108">Uma saudação organizacional.</span><span class="sxs-lookup"><span data-stu-id="4044a-108">An organizational greeting.</span></span>
    
- <span data-ttu-id="4044a-109">Música enquanto a pessoa estiver aguardando em espera.</span><span class="sxs-lookup"><span data-stu-id="4044a-109">Music while people are waiting on hold.</span></span>
    
- <span data-ttu-id="4044a-110">Redirecionando de chamadas para operadores em listas de distribuição habilitado para email e grupos de segurança de chamada.</span><span class="sxs-lookup"><span data-stu-id="4044a-110">Redirecting of calls to call agents in mail-enabled distribution lists and security groups.</span></span>
    
- <span data-ttu-id="4044a-111">Criação de configurações para o tamanho máximo da fila de chamada, tempo limite e opções de manipulação de chamadas.</span><span class="sxs-lookup"><span data-stu-id="4044a-111">Making settings for call queue maximum size, timeout, and call handling options.</span></span>
    
<span data-ttu-id="4044a-112">When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span><span class="sxs-lookup"><span data-stu-id="4044a-112">When someone calls in to a phone number that is set up up with a call queue, they will hear a greeting first (if any is set up), and then they will be put in the queue and wait for the next available call agent.</span></span> <span data-ttu-id="4044a-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.</span><span class="sxs-lookup"><span data-stu-id="4044a-113">The person calling in will hear music while they are on hold waiting, and the calls will be offered to the call agents in the  *First In, First Out*  (FIFO) manner.</span></span>
  
<span data-ttu-id="4044a-114">Aguardando na fila de todas as chamadas serão distribuídas usando um modo de roteamento attendant ou o modo serial de roteamento:</span><span class="sxs-lookup"><span data-stu-id="4044a-114">All calls waiting in the queue will be distributed using an attendant routing mode or serial routing mode:</span></span>
  
- <span data-ttu-id="4044a-115">Com o Atendedor de roteamento, a primeira chamada na fila tocarão todos os operadores ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="4044a-115">With attendant routing, the first call in the queue will ring all agents at the same time.</span></span>
    
- <span data-ttu-id="4044a-116">Com o encaminhamento em série, a primeira chamada da fila chama todos os agentes, um de cada vez.</span><span class="sxs-lookup"><span data-stu-id="4044a-116">With serial routing, the first call in the queue will ring all call agents one by one.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4044a-117">Agentes de chamada que estão **Offline**, definiram sua presença como **Não incomodar** ou optaram por não serem incluídos na fila de chamadas e, portanto, não serão chamados.</span><span class="sxs-lookup"><span data-stu-id="4044a-117">Call agents who are **Offline**, have set their presence to **Do not Disturb,** or have opted out of the call queue won't be called.</span></span>
  
- <span data-ttu-id="4044a-118">Somente uma notificação de chamada de entrada (para a chamada no início da fila) de cada vez será enviada para os agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="4044a-118">Only one incoming call notification (for the call at the head of the queue) at a time will be sent to the call agents.</span></span>
    
- <span data-ttu-id="4044a-119">Depois que um agente aceita a chamada, a próxima chamada de entrada na fila começará a tocar para os agentes de chamadas.</span><span class="sxs-lookup"><span data-stu-id="4044a-119">After a call agent accepts the call, the next incoming call in the queue will start ringing call agents.</span></span>
    
## <a name="step-1---getting-started"></a><span data-ttu-id="4044a-120">Etapa 1 - Introdução</span><span class="sxs-lookup"><span data-stu-id="4044a-120">Step 1 - Getting started</span></span>

<span data-ttu-id="4044a-121">Para começar a usar as filas de chamadas, é importante lembrar-se de que:</span><span class="sxs-lookup"><span data-stu-id="4044a-121">To get started using call queues, it's important to remember a few things:</span></span>
  
- <span data-ttu-id="4044a-p104">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="4044a-p104">Your organization must have (at a minimum) an Enterprise E3 plus **Phone System** license or an Enterprise E5 license. The number of **Phone System** user licenses that are assigned affects the number of service numbers that are available to be used for call queues. The number of call queues you can have is dependent on the number of **Phone System** and **Audio Conferencing** licenses that are assigned in your organization. To learn more about licensing, go [here](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4044a-p105">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="4044a-p105">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="4044a-130">Para saber mais sobre os Planos de Chamadas do Office 365, consulte [O que são os Planos de Chamadas do Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) e [Planos de Chamadas para Office 365](/microsoftteams/calling-plans-for-office-365).</span><span class="sxs-lookup"><span data-stu-id="4044a-130">To learn more about Office 365 Calling Plans, see [What are Calling Plans in Office 365?](/microsoftteams/what-are-calling-plans-in-office-365) and [Calling Plans for Office 365](/microsoftteams/calling-plans-for-office-365).</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4044a-131">Usuários hospedados no local usando o Lync Server 2010 não são suportados como agentes de fila uma chamada.</span><span class="sxs-lookup"><span data-stu-id="4044a-131">Users hosted on-premises using Lync Server 2010 aren't supported as a Call Queue Agents.</span></span> 
  
- <span data-ttu-id="4044a-p106">You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.</span><span class="sxs-lookup"><span data-stu-id="4044a-p106">You can only assign toll and toll-free service phone numbers that you got in the **Skype for Business admin center** or transferred from another service provider to Phone System call queues. To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="4044a-134">[!OBSERVAçãO] Os números de telefone (assinante) não podem ser atribuídos às filas de chamada  somente números de telefone de serviço chamadas gratuitas ou tarifas podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="4044a-134">User (subscriber) phone numbers can't be assigned to call queues - only service toll or toll-free phone numbers can be used.</span></span> 
  
- <span data-ttu-id="4044a-135">Quando você estiver distribuindo as chamadas de entrada de uma fila de espera de chamada de sistema telefônico, esses clientes são suportados para os agentes de chamada:</span><span class="sxs-lookup"><span data-stu-id="4044a-135">When you are distributing the incoming calls from an Phone System call queue, these clients are supported for call agents:</span></span>
    
  - <span data-ttu-id="4044a-136">Cliente de desktop Skype for Business 2016 (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="4044a-136">Skype for Business desktop client 2016 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="4044a-137">Cliente de desktop Lync 2013 (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="4044a-137">Lync desktop client 2013 (32 and 64-bit versions)</span></span>
    
  - <span data-ttu-id="4044a-138">All IP phone models supported for Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="4044a-138">All IP phone models supported for Skype for Business Online.</span></span> <span data-ttu-id="4044a-139">See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span><span class="sxs-lookup"><span data-stu-id="4044a-139">See [Getting phones for Skype for Business Online](getting-phones-for-skype-for-business-online/getting-phones-for-skype-for-business-online.md).</span></span>
    
  - <span data-ttu-id="4044a-140">Cliente Mac do Skype for Business (versão 16.8.196 e posterior)</span><span class="sxs-lookup"><span data-stu-id="4044a-140">Mac Skype for Business Client (version 16.8.196 and later)</span></span> 
    
  - <span data-ttu-id="4044a-141">Cliente Android do Skype for Business (versão 6.16.0.9 e posterior)</span><span class="sxs-lookup"><span data-stu-id="4044a-141">Android Skype for Business Client (version 6.16.0.9 and later)</span></span>
    
  - <span data-ttu-id="4044a-142">Cliente iPhone do Skype for Business (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="4044a-142">iPhone Skype for Business Client (version 6.16.0 and later)</span></span>
    
  - <span data-ttu-id="4044a-143">Cliente iPad do Skype for Business (versão 6.16.0 e posterior)</span><span class="sxs-lookup"><span data-stu-id="4044a-143">iPad Skype for Business Client (version 6.16.0 and later)</span></span>

  - <span data-ttu-id="4044a-144">Cliente do Windows para Microsoft Teams (versões de 32 e 64 bits)</span><span class="sxs-lookup"><span data-stu-id="4044a-144">Microsoft Teams Windows client (32 and 64-bit versions)</span></span>

  - <span data-ttu-id="4044a-145">Cliente Mac para Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4044a-145">Microsoft Teams Mac client</span></span>

  - <span data-ttu-id="4044a-146">Aplicativo do Microsoft Teams para iPhone</span><span class="sxs-lookup"><span data-stu-id="4044a-146">Microsoft Teams iPhone app</span></span>

  - <span data-ttu-id="4044a-147">Aplicativo do Microsoft Teams para Android</span><span class="sxs-lookup"><span data-stu-id="4044a-147">Microsoft Teams Android app</span></span>
    
## <a name="step-2---getting-or-transferring-toll-or-toll-free-service-phone-numbers"></a><span data-ttu-id="4044a-148">Etapa 2 - Como adquirir e transferir números de telefone de serviço de chamada gratuita ou tarifada</span><span class="sxs-lookup"><span data-stu-id="4044a-148">Step 2 - Getting or transferring toll or toll-free service phone numbers</span></span>

<span data-ttu-id="4044a-p108">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="4044a-p108">Before you can create and set up your call queues, you will need to get or transfer your existing toll or toll-free service numbers. After you get the toll or toll-free service phone numbers, they will show up in **Skype for Business admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md) or if you want to transfer and existing service number, see [Transfer phone numbers to Office 365](/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4044a-p109">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span><span class="sxs-lookup"><span data-stu-id="4044a-p109">If you are outside the United States, you can't use the Skype for Business admin center to get service numbers. Go to [Manage phone numbers for your organization](/microsoftteams/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>
  
## <a name="step-3---create-a-new-call-queue"></a><span data-ttu-id="4044a-154">Etapa 3 - Criar uma nova fila de chamada</span><span class="sxs-lookup"><span data-stu-id="4044a-154">Step 3 - Create a new Call Queue</span></span>

<span data-ttu-id="4044a-155">![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**</span><span class="sxs-lookup"><span data-stu-id="4044a-155">![sfb-logo-30x30.png](../images/sfb-logo-30x30.png) **Using the Skype for Business admin center**</span></span>

<span data-ttu-id="4044a-156">No **Centro de administração do Skype for Business**, clique em **Encaminhamento de chamadas** > **Filas de chamadas** e clique em **Adicionar novas**:</span><span class="sxs-lookup"><span data-stu-id="4044a-156">In the **Skype for Business admin center**, click **Call routing** > **Call queues**, then click **Add new**:</span></span>
  
### <a name="set-the-call-queue-display-name-phone-number-and-domain-if-any"></a><span data-ttu-id="4044a-157">Definir o nome de exibição da fila de chamada, número de telefone e domínio (se houver)</span><span class="sxs-lookup"><span data-stu-id="4044a-157">Set the call queue display name, phone number and domain (if any)</span></span>

![Setting up a call queue.](../images/37ecc300-a108-4294-8463-fce570dfce72.png)
***
<span data-ttu-id="4044a-159">![Número 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="4044a-159">![Number 1](../images/sfbcallout1.png)</span></span><br/>
<span data-ttu-id="4044a-p110">**Nome** Digite um nome de exibição descritivo para a fila de chamadas. Esse nome é obrigatório e pode conter até 64 caracteres, incluindo espaços.</span><span class="sxs-lookup"><span data-stu-id="4044a-p110">**Name** Enter a descriptive display name for the call queue. This is required and can contain up to 64 characters, including spaces. </span></span><br/> <span data-ttu-id="4044a-162">Esse nome será exibido na notificação da chamada de entrada.</span><span class="sxs-lookup"><span data-stu-id="4044a-162">This name will be displayed in the notification for the incoming call.</span></span>
***
<span data-ttu-id="4044a-163">![Número 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="4044a-163">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="4044a-p111">**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. </span><span class="sxs-lookup"><span data-stu-id="4044a-p111">**Phone number** Select a service toll or toll-free phone number for the call queue. This is optional. </span></span><br/> <span data-ttu-id="4044a-p112">If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)</span><span class="sxs-lookup"><span data-stu-id="4044a-p112">If there aren't any listed, you need to get service numbers before you can create this call queue. To get your service numbers, see [Getting service phone numbers for Skype for Business and Microsoft Teams](getting-service-phone-numbers.md)</span></span>
***
<span data-ttu-id="4044a-168">![Número 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="4044a-168">![Number 3](../images/sfbcallout3.png)</span></span><br/><span data-ttu-id="4044a-p113">**Domínio** Se algum estiver disponível, escolha o domínio do Office 365 que você deseja usar. Ele só estará disponível ser você tiver mais de um domínio sendo usado com o Office 365. Se você tiver mais de um, deverá escolher o nome do domínio na lista. </span><span class="sxs-lookup"><span data-stu-id="4044a-p113">**Domain** If this is available, choose the Office 365 domain you want to use. This is only available if you have more than one domain being used with Office 365. If you have more than one, you must chose the domain name from the list. </span></span><br/> <span data-ttu-id="4044a-172">Por exemplo, você poderia ter um domínio como:  _contoso.com or redmond.contoso.com_.</span><span class="sxs-lookup"><span data-stu-id="4044a-172">For example, you could have a domain like:  _contoso.com or redmond.contoso.com_</span></span>
   
### <a name="set-the-greeting-and-music-played-while-on-hold"></a><span data-ttu-id="4044a-173">Definir a saudação e a música reproduzida durante a espera</span><span class="sxs-lookup"><span data-stu-id="4044a-173">Set the greeting and music played while on hold</span></span>

![Setting up a call queue.](../images/1d395a93-7cab-4178-9295-12d5379e20de.png)
  
***
<span data-ttu-id="4044a-175">![Número 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="4044a-175">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="4044a-p114">**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. </span><span class="sxs-lookup"><span data-stu-id="4044a-p114">**Greeting** is optional. This is the greeting that is played for people who call in to the call queue number. </span></span><br/> <span data-ttu-id="4044a-178">Você pode carregar um arquivo de áudio (formatos. wav,. mp3 ou. wma).</span><span class="sxs-lookup"><span data-stu-id="4044a-178">You can upload an audio file (.wav, .mp3, or .wma formats).</span></span>
***
<span data-ttu-id="4044a-179">![Número 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="4044a-179">![Number 2](../images/sfbcallout2.png)</span></span><br/><span data-ttu-id="4044a-180">**Música de espera** Você pode usar o padrão de música em espera fornecida com a fila chamada ou você pode carregar um arquivo de áudio nos formatos. wav, mp3 ou. wma a ser usado como sua música personalizada em espera.</span><span class="sxs-lookup"><span data-stu-id="4044a-180">**Music on hold** You can either use the default Music on Hold provided with the call queue, or you can upload an audio file in .wav, mp3, or .wma formats to use as your custom Music on Hold.</span></span> 
   

### <a name="select-the-call-distribution-method"></a><span data-ttu-id="4044a-181">Selecione o método de distribuição de chamadas</span><span class="sxs-lookup"><span data-stu-id="4044a-181">Select the call distribution method</span></span>

![Mostra as opções de métodos de distribuição de chamadas](../images/5d249515-d532-4af2-90da-011404028b89.png)
  
***
<span data-ttu-id="4044a-183">![Número 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="4044a-183">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="4044a-p115">**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. </span><span class="sxs-lookup"><span data-stu-id="4044a-p115">**Call distribution method** You can choose either **Attendant** or **Serial** for your call queue distribution method. All new and existing call queues will have attendant routing selected by default. To use serial routing, you must explicitly choose the **Serial** routing option in UI and cmdlets. </span></span><br/><br/> <span data-ttu-id="4044a-p116">When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span><span class="sxs-lookup"><span data-stu-id="4044a-p116">When serial routing is chosen and the call queue is saved, the calls from the queue will ring your agents one by one, starting from the beginning of the agent list. If an agent dismisses or does not pick up a call, the call will ring the next agent on the list and will try all agents one by one until it is picked up or times out waiting in the queue.</span></span>   

> [!NOTE]
> <span data-ttu-id="4044a-189">O encaminhamento em série ignora agentes que estão **Offline**, com a presença definida como **Não incomodar** ou que **recusaram** receber chamadas da fila de espera.</span><span class="sxs-lookup"><span data-stu-id="4044a-189">Serial routing will skip agents who are **Offline**, have set their presence to **Do not Disturb**, or have **opted out** of getting calls from this queue.</span></span> 
   
### <a name="select-an-agent-opt-out-option"></a><span data-ttu-id="4044a-190">Selecionar uma opção de recusa do agente</span><span class="sxs-lookup"><span data-stu-id="4044a-190">Select an agent opt out option</span></span>

![Exibe a caixa de seleção de recusa para o agente](../images/99279eff-db61-4acf-9b62-64be84b6414b.png)
  
***
<span data-ttu-id="4044a-192">![Número 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="4044a-192">![Number 1](../images/sfbcallout1.png)</span></span><br/><span data-ttu-id="4044a-193">**Opção de recusa do agente** Você pode optar por permitir que os agentes se recusem a receber chamadas de uma determinada fila selecionando a **Opção de recusa do agente**.</span><span class="sxs-lookup"><span data-stu-id="4044a-193">**Agent Opt out option** You can choose to allow call queue agents to opt out of taking calls from a particular queue by selecting **Agent Opt out option**.</span></span>  <br/> <span data-ttu-id="4044a-p117">Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  </span><span class="sxs-lookup"><span data-stu-id="4044a-p117">Enabling this option allows all agents in this queue to start or stop receiving call from this call queue at will. You can revoke the agent opt-out privilege at any time by clearing the check box, causing agents to become automatically opted in for this queue again (the default setting for all agents).  </span></span><br/><br/> <span data-ttu-id="4044a-196">Para acessar a opção de recusa, os agentes podem:</span><span class="sxs-lookup"><span data-stu-id="4044a-196">To access the opt-out option, agents can do the following:</span></span>
 1. <span data-ttu-id="4044a-197">Abrir as **Opções** no cliente Skype for Business na área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="4044a-197">Open **Options** in their desktop Skype for Business client.</span></span> 
 2. <span data-ttu-id="4044a-198">Na guia **Encaminhamento de chamadas**, clicar no link **Editar configurações online**.</span><span class="sxs-lookup"><span data-stu-id="4044a-198">On the **Call Forwarding** tab, click the **Edit settings online** link.</span></span>
 3. <span data-ttu-id="4044a-199">Na página de configurações do usuário, clicar em **Filas de Chamadas**e desmarcar as caixas de seleção de todas as filas que desejam recusar.</span><span class="sxs-lookup"><span data-stu-id="4044a-199">On the user settings page, click **Call Queues**, and then clear the check boxes for any queues for which they want to opt out.</span></span>
 
    > [!NOTE] 
    > <span data-ttu-id="4044a-200">Agentes que usam clientes Mac, móveis ou do Lync 2013 ou usuários Hybrid Voice hospedados no local usando o servidor Skype for Business 2015, podem ir em [https://aka.ms/cqsettings](https://aka.ms/cqsettings) para acessar a opção de recusa.</span><span class="sxs-lookup"><span data-stu-id="4044a-200">Agents using Mac, mobile, or Lync 2013 clients, or Hybrid Voice users who are hosted on-premises using Skype for Business 2015 server, can go to [https://aka.ms/cqsettings](https://aka.ms/cqsettings) to access the opt out option.</span></span>
   
### <a name="add-call-agents-to-a-call-queue"></a><span data-ttu-id="4044a-201">Adicionar agentes de chamada para uma fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="4044a-201">Add call agents to a call queue</span></span>

![Set up call queues.](../images/skype-for-business-add-agents-to-call-queue.png)
  
***
![Número 1](../images/sfbcallout1.png)<br/><br/><span data-ttu-id="4044a-204">Agentes de chamadas (máximo de 50) podem ser:</span><span class="sxs-lookup"><span data-stu-id="4044a-204">Call agents (50 maximum) can be:</span></span>
* <span data-ttu-id="4044a-205">Um usuário Online com uma licença de **Sistema de Telefonia** e habilitados para o Enterprise Voice ou com um Plano de Chamadas.</span><span class="sxs-lookup"><span data-stu-id="4044a-205">An Online user with a **Phone System** license and enabled for Enterprise Voice or with a Calling Plan.</span></span> <br/><br/> <span data-ttu-id="4044a-p118">**Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="4044a-p118">**Note:**  To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. See [Assign Skype for Business and Microsoft Teams licenses](../skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses.md). To enable them for Enterprise Voice, you can use Windows PowerShell. For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span> <br/><br/>
* <span data-ttu-id="4044a-p119">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. </span><span class="sxs-lookup"><span data-stu-id="4044a-p119">Online users with a **Phone System** license and a Calling Plan that are added to an Office 365 Group, a mail-enabled Distribution List, or a Security Group. It might take up to 30 minutes for a new agent added for a distribution list or a security group to start receiving calls from a call queue. A newly created distribution list or security group might take up to 48 hours to become available to be used with call queues. Newly created Office 365 Groups are available almost immediately. </span></span><br/> 

  > [!NOTE] 
  > <span data-ttu-id="4044a-214">Usuários hospedados no local usando o Lync Server 2010 não são suportados.</span><span class="sxs-lookup"><span data-stu-id="4044a-214">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span>           
   
### <a name="set-the-maximum-queue-size-and-maximum-wait-time"></a><span data-ttu-id="4044a-215">Definir o tamanho máximo da fila e o tempo máximo de espera</span><span class="sxs-lookup"><span data-stu-id="4044a-215">Set the maximum queue size and maximum wait time</span></span>

![Set up a call queue.](../images/3f018734-16fe-458b-827d-71fc25155cde.png)
  
***
<span data-ttu-id="4044a-217">![Número 1](../images/sfbcallout1.png)</span><span class="sxs-lookup"><span data-stu-id="4044a-217">![Number 1](../images/sfbcallout1.png)</span></span><br/><br/><span data-ttu-id="4044a-p120">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span><span class="sxs-lookup"><span data-stu-id="4044a-p120">**Maximum calls in the queue** Use this to set the maximum calls that can wait in the queue at the same time. The default is 50, but it can range from 0 to 200.When this limit is reached, the call will be handled in way you have set on the **When the maximum number of calls is reached** setting below.</span></span>
***
<span data-ttu-id="4044a-220">![Número 2](../images/sfbcallout2.png)</span><span class="sxs-lookup"><span data-stu-id="4044a-220">![Number 2](../images/sfbcallout2.png)</span></span><br/><br/><span data-ttu-id="4044a-221">**Quando o número máximo de chamadas é atingido** Quando a fila chamada atinge seu tamanho máximo (definido usando a configuração **máximo de chamadas na fila** ), você pode escolher o que acontece às novas chamadas de entrada.</span><span class="sxs-lookup"><span data-stu-id="4044a-221">**When the maximum number of calls is reached** When the call queue reaches its maximum size (set using the **Maximum calls in the queue** setting), you can choose what happens to new incoming calls.</span></span>
* <span data-ttu-id="4044a-222">**Desconectar com um sinal de ocupado** A chamada será desconectada.</span><span class="sxs-lookup"><span data-stu-id="4044a-222">**Disconnect with a busy signal** The call will be disconnected.</span></span>
* <span data-ttu-id="4044a-223">**Encaminhar essa chamada para** Quando você escolhe essa opção, você terá estas opções:</span><span class="sxs-lookup"><span data-stu-id="4044a-223">**Forward this call to** When you choose this, you will have these options:</span></span>
  * <span data-ttu-id="4044a-p121">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span><span class="sxs-lookup"><span data-stu-id="4044a-p121">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have a Calling Plan. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span></span><br/> <br/><span data-ttu-id="4044a-227">Para saber sobre o licenciamento necessário para a caixa postal, consulte [Configurar caixa postal do Sistema de Telefonia](/microsoftteams/set-up-phone-system-voicemail).</span><span class="sxs-lookup"><span data-stu-id="4044a-227">To learn about licensing required for voicemail, see [Set up Phone System voicemail](/microsoftteams/set-up-phone-system-voicemail).</span></span> 
     
    > [!Note]
    > <span data-ttu-id="4044a-228">Usuários hospedados no local usando o Lync Server 2010 não são suportados.</span><span class="sxs-lookup"><span data-stu-id="4044a-228">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>
     
  * <span data-ttu-id="4044a-229">**Fila de chamadas** Você já deve ter criado outra fila de espera de chamada, mas depois que você fizer isso, você pode selecionar essa fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="4044a-229">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
  * <span data-ttu-id="4044a-p122">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="4044a-p122">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
***
<span data-ttu-id="4044a-232">![Número 3](../images/sfbcallout3.png)</span><span class="sxs-lookup"><span data-stu-id="4044a-232">![Number 3](../images/sfbcallout3.png)</span></span><br/><br/><span data-ttu-id="4044a-p123">**Quanto tempo uma chamada pode esperar na fila** Você também pode decidir quanto tempo uma chamada pode ficar em espera na fila antes de seu tempo limite expirar e precisar ser redirecionada ou desconectada. Para onde ela será direcionada dependerá da configuração da opção **Quando uma chamada atinge o tempo limite.** Você pode definir um período de 0 a 45 minutos. </span><span class="sxs-lookup"><span data-stu-id="4044a-p123">**How long a call can wait in the queue** You can also decide how much time a call can be on hold in the queue before it times out and needs to be redirected or disconnected. Where it will be redirected is based on how you set the **When a call times out** setting. You can set a time from 0 to 45 minutes. </span></span><br/><br/> <span data-ttu-id="4044a-p124">The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant.</span><span class="sxs-lookup"><span data-stu-id="4044a-p124">The timeout value can be set in seconds, at 15-second intervals. This allows you to manipulate the call flow with finer granularity. For example, you could specify that any calls that are not answered by an agent within 30 seconds go to a Directory Search Auto Attendant.</span></span> 

***
<span data-ttu-id="4044a-239">![Número 4](../images/sfbcallout4.png)</span><span class="sxs-lookup"><span data-stu-id="4044a-239">![Number 4](../images/sfbcallout4.png)</span></span><br/><br/><span data-ttu-id="4044a-240">**Quando uma chamada atinge o tempo limite** Quando uma chamada atinge o tempo limite que você definiu na configuração **Por quanto tempo uma chamada pode esperar na fila**, é possível escolher o que acorrerá com essa chamada:</span><span class="sxs-lookup"><span data-stu-id="4044a-240">**When a call times out** When the call reaches the limit you set on the **How long a call can wait in the queue** setting, you can choose what happens to this call:</span></span>
* <span data-ttu-id="4044a-241">**Desconectar** A chamada será desconectada.</span><span class="sxs-lookup"><span data-stu-id="4044a-241">**Disconnect** The call will be disconnected.</span></span>
* <span data-ttu-id="4044a-242">**Encaminhar essa chamada para** Quando você escolhe essa opção, você terá estas opções:</span><span class="sxs-lookup"><span data-stu-id="4044a-242">**Forward this call to** When you choose this, you will have these options:</span></span>
  * <span data-ttu-id="4044a-p125">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span><span class="sxs-lookup"><span data-stu-id="4044a-p125">**Person in your company** An Online user with a **Phone System** license and be enabled for Enterprise Voice or have Calling Plans. You can set it up so the person calling in can be sent to voicemail. To do this, select a **Person in your company** and set this person to have their calls forwarded directly to voicemail. </span></span></br><br/>  <span data-ttu-id="4044a-246">Para saber sobre o licenciamento necessário para a caixa postal, consulte [Configurar caixa postal do Sistema de Telefonia](/microsoftteams/set-up-phone-system-voicemail).</span><span class="sxs-lookup"><span data-stu-id="4044a-246">To learn about licensing required for voicemail, see [Set up Phone System voicemail](/microsoftteams/set-up-phone-system-voicemail).</span></span> 

    > [!Note]
    > <span data-ttu-id="4044a-247">Usuários hospedados no local usando o Lync Server 2010 não são suportados.</span><span class="sxs-lookup"><span data-stu-id="4044a-247">Users hosted on-premises using Lync Server 2010 aren't supported.</span></span><br/>

  * <span data-ttu-id="4044a-248">**Fila de chamadas** Você já deve ter criado outra fila de espera de chamada, mas depois que você fizer isso, você pode selecionar essa fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="4044a-248">**Call Queue** You must have already created another call queue, but after you do, you can select that call queue.</span></span>
  * <span data-ttu-id="4044a-p126">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="4044a-p126">**Auto Attendant** You must have already created an auto attendant, but after you do, you can select that auto attendant. See [Set up a Phone System auto attendant](set-up-a-phone-system-auto-attendant.md).</span></span>
   
## <a name="changing-the-users-caller-id-to-be-a-call-queues-phone-number"></a><span data-ttu-id="4044a-251">Alterar a identificação de chamadas do usuário para um número de telefone de fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="4044a-251">Changing the user's Caller ID to be a call queue's phone number</span></span>

<span data-ttu-id="4044a-252">Você pode proteger a identidade de um usuário alterando a identificação de chamadas dele para chamadas de saída para uma fila de chamadas criando uma política com o cmdlet **New-CallingLineIdentity**.</span><span class="sxs-lookup"><span data-stu-id="4044a-252">You can protect a user's identity by changing their caller ID for the outbound calls to a call queue instead by creating a policy using the **New-CallingLineIdentity** cmdlet.</span></span>
  
<span data-ttu-id="4044a-253">Para fazer isso, execute:</span><span class="sxs-lookup"><span data-stu-id="4044a-253">To do this, run:</span></span>
  
```
New-CsCallingLineIdentity -Identity "UKSalesQueue" -CallingIdSubstitute "Service" -ServiceNumber 14258828080 -EnableUserOverride $False -Verbose
```

<span data-ttu-id="4044a-p127">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:</span><span class="sxs-lookup"><span data-stu-id="4044a-p127">Then apply the policy to the user using the **Grant-CallingLineIdentity** cmdlet. To do this, run:</span></span>
  
```
Grant-CsCallingLineIdentity -PolicyName UKSalesQueue -Identity "AmosMarble@contoso.com"
```

<span data-ttu-id="4044a-256">Você pode obter mais informações sobre como fazer alterações nas configurações de identificação de chamadas em sua organização [aqui](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span><span class="sxs-lookup"><span data-stu-id="4044a-256">You can get more information on how to make changes to caller ID settings in your organization [here](../what-are-calling-plans-in-office-365/how-can-caller-id-be-used-in-your-organization.md).</span></span>
  
## <a name="want-to-know-more"></a><span data-ttu-id="4044a-257">Deseja saber mais?</span><span class="sxs-lookup"><span data-stu-id="4044a-257">Want to know more?</span></span>

<span data-ttu-id="4044a-258">Você também pode usar o Windows PowerShell para criar e configurar filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="4044a-258">You can also use Windows PowerShell to create and set up call queues.</span></span>
  
### <a name="call-queue-cmdlets"></a><span data-ttu-id="4044a-259">Cmdlets da fila de chamadas</span><span class="sxs-lookup"><span data-stu-id="4044a-259">Call queue cmdlets</span></span>

<span data-ttu-id="4044a-260">Veja os cmdlets necessários para gerenciar uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="4044a-260">Here are the cmdlets that you need to manage a call queue.</span></span>
  
- [<span data-ttu-id="4044a-261">New-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="4044a-261">New-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796459.aspx)
    
- [<span data-ttu-id="4044a-262">Set-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="4044a-262">Set-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796457.aspx)
    
- [<span data-ttu-id="4044a-263">Get-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="4044a-263">Get-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796458.aspx)
    
- [<span data-ttu-id="4044a-264">Remove-CsHuntgroup</span><span class="sxs-lookup"><span data-stu-id="4044a-264">Remove-CsHuntgroup</span></span>](https://technet.microsoft.com/en-us/library/mt796456.aspx)
    
### <a name="more-about-windows-powershell"></a><span data-ttu-id="4044a-265">Mais sobre o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4044a-265">More about Windows PowerShell</span></span>

- <span data-ttu-id="4044a-p128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span><span class="sxs-lookup"><span data-stu-id="4044a-p128">Windows PowerShell is all about managing users and what users are allowed or not allowed to do. With Windows PowerShell, you can manage Office 365 and Skype for Business Online using a single point of administration that can simplify your daily work, when you have multiple tasks to do. To get started with Windows PowerShell, see these topics:</span></span>
    
  - [<span data-ttu-id="4044a-269">Uma introdução ao Windows PowerShell e ao Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4044a-269">An introduction to Windows PowerShell and Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [<span data-ttu-id="4044a-270">Por que você precisa usar o PowerShell do Office 365</span><span class="sxs-lookup"><span data-stu-id="4044a-270">Why you need to use Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- <span data-ttu-id="4044a-p129">O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:</span><span class="sxs-lookup"><span data-stu-id="4044a-p129">Windows PowerShell has many advantages in speed, simplicity, and productivity over only using the Office 365 admin center such as when you are making setting changes for many users at one time. Learn about these advantages in the following topics:</span></span>
    
  - [<span data-ttu-id="4044a-273">Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="4044a-273">Best ways to manage Office 365 with Windows PowerShell</span></span>](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [<span data-ttu-id="4044a-274">Usar o Windows PowerShell para gerenciar o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4044a-274">Using Windows PowerShell to manage Skype for Business Online</span></span>](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [<span data-ttu-id="4044a-275">Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="4044a-275">Using Windows PowerShell to do common Skype for Business Online management tasks</span></span>](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a><span data-ttu-id="4044a-276">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4044a-276">Related topics</span></span>
[<span data-ttu-id="4044a-277">Veja aqui o que é fornecido com o Sistema de Telefonia no Office 365</span><span class="sxs-lookup"><span data-stu-id="4044a-277">Here's what you get with Phone System in Office 365</span></span>](/MicrosoftTeams/here-s-what-you-get-with-phone-system)

[<span data-ttu-id="4044a-278">Obtendo números de telefone de serviço do Skype for Business e do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="4044a-278">Getting service phone numbers for Skype for Business and Microsoft Teams</span></span>](getting-service-phone-numbers.md)

[<span data-ttu-id="4044a-279">Disponibilidade da Audioconferência e dos Planos de Chamadas por país e região</span><span class="sxs-lookup"><span data-stu-id="4044a-279">Country and region availability for Audio Conferencing and Calling Plans</span></span>](/microsoftteams/country-and-region-availability-for-audio-conferencing-and-calling-plans/country-and-region-availability-for-audio-conferencing-and-calling-plans)

  
 
