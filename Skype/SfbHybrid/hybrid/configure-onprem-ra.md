---
title: Configurar uma conta de recurso no Skype for Business Server 2019
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: wasseemh
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: ''
description: configurar uma conta de recurso para o Skype for Business Server 2019.
ms.openlocfilehash: 33211f7dcd56e402167a3c810343947d4dfe0954
ms.sourcegitcommit: 868db85f0126e8f56d711ea590ad44acce8f96f6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/03/2019
ms.locfileid: "36160402"
---
# <a name="configure-resource-accounts"></a><span data-ttu-id="de63e-103">Configurar contas de recurso</span><span class="sxs-lookup"><span data-stu-id="de63e-103">Configure resource accounts</span></span>

<span data-ttu-id="de63e-104">As implementações híbridas do Skype for Business Server 2019 usam apenas serviços em nuvem fornecidos pelo sistema de telefonia para Unificação de mensagens e não se integram ao Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="de63e-104">Skype for Business Server 2019 hybrid implementations only use Cloud services provided by Phone System for unified messaging and do not integrate with Exchange Online.</span></span> <span data-ttu-id="de63e-105">No Skype for Business Server 2019, agora você pode usar as filas de chamadas de nuvem e atendedores automáticos descritos [aqui, o que você obtém com o sistema de telefonia no Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span><span class="sxs-lookup"><span data-stu-id="de63e-105">In Skype for Business Server 2019 you are now able to use the Cloud call queues and auto attendants described in [Here's what you get with Phone System in Office 365](/MicrosoftTeams/here-s-what-you-get-with-phone-system).</span></span>

<span data-ttu-id="de63e-106">Para usar esses serviços de sistema de telefonia com o Skype for Business Server 2019, você precisará criar contas de recurso que atuam como pontos de extremidade de aplicativo e podem ter números de telefone atribuídos e usar o centro de administração do teams online para configurar a fila de chamadas ou atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="de63e-106">To use these Phone System services with Skype for Business Server 2019, you will need to create resource accounts that act as application endpoints and can be assigned phone numbers, then use the online Teams admin center to configure the call queue or auto attendant.</span></span> <span data-ttu-id="de63e-107">Essa conta de recurso pode ser hospedada online (Confira [gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) para criar contas de recursos hospedadas online) ou local, conforme descrito neste artigo.</span><span class="sxs-lookup"><span data-stu-id="de63e-107">This resource account can be homed online (see [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) to create resource accounts homed online) or on premise as described in this article.</span></span> <span data-ttu-id="de63e-108">Normalmente, você terá vários nós de serviço de sistema de telefonia, sendo que cada um deles é mapeado para contas de recursos, que podem estar hospedados online ou no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="de63e-108">Typically you will have multiple Phone System service nodes, each of which is mapped to a resource accounts, which can be homed online or in Skype for Business Server 2019.</span></span>

<span data-ttu-id="de63e-109">Se você tiver um atendedor automático de UM do Exchange e um sistema de fila de chamadas, antes de mudar para o Exchange Server 2019 ou Exchange Online, será necessário registrar manualmente os detalhes conforme descrito abaixo e implementar um sistema completamente novo usando o centro de administração do Microsoft Teams .</span><span class="sxs-lookup"><span data-stu-id="de63e-109">If you have an existing Exchange UM auto attendant and call queue system, before you switch to Exchange Server 2019 or Exchange online you will need to manually record the details as described below and then implement a completely new system using the Teams admin center.</span></span>

## <a name="overview"></a><span data-ttu-id="de63e-110">Visão geral</span><span class="sxs-lookup"><span data-stu-id="de63e-110">Overview</span></span>

<span data-ttu-id="de63e-111">Se o seu serviço de sistema de telefonia precisa de um número de serviço, as várias dependências podem ser atendidas na seguinte sequência:</span><span class="sxs-lookup"><span data-stu-id="de63e-111">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="de63e-112">Obter um número de serviço</span><span class="sxs-lookup"><span data-stu-id="de63e-112">Obtain a service number</span></span>
2. <span data-ttu-id="de63e-113">Comprar uma licença do sistema de telefonia</span><span class="sxs-lookup"><span data-stu-id="de63e-113">Buy a Phone System license</span></span>
3. <span data-ttu-id="de63e-114">Criar a conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="de63e-114">Create the resource account.</span></span> <span data-ttu-id="de63e-115">Um atendedor automático ou fila de chamada é necessário para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="de63e-115">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="de63e-116">Aguardar uma sincronização do Active Directory entre online e local</span><span class="sxs-lookup"><span data-stu-id="de63e-116">Wait for an active directory sync between online and on premise</span></span>
5. <span data-ttu-id="de63e-117">Atribua a licença do sistema de telefonia à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="de63e-117">Assign the Phone System license to the resource account.</span></span>
6. <span data-ttu-id="de63e-118">Atribuir um número de serviço à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="de63e-118">Assign a service number to the resource account.</span></span>
7. <span data-ttu-id="de63e-119">Criar um serviço de sistema de telefonia (uma fila de chamadas ou atendedor automático)</span><span class="sxs-lookup"><span data-stu-id="de63e-119">Create a Phone System service (a call queue or auto attendant)</span></span>
8. <span data-ttu-id="de63e-120">Associar a conta de recurso a um serviço: (New-CsApplicationInstanceAssociation)</span><span class="sxs-lookup"><span data-stu-id="de63e-120">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="de63e-121">Se o atendedor automático ou a fila de chamadas estiverem aninhados em um atendedor automático de nível superior, a conta de recurso associada só precisará de um número de telefone se você quiser vários pontos de entrada na estrutura de atendedores automáticos e filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="de63e-121">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="de63e-122">Para redirecionar as chamadas para pessoas em sua organização que estão hospedadas online, elas devem ter uma licença de **sistema de telefonia** e estar habilitadas para o Enterprise Voice ou ter planos de chamadas do Office 365.</span><span class="sxs-lookup"><span data-stu-id="de63e-122">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="de63e-123">Consulte [atribuir licenças do Microsoft Teams](/MicrosoftTeams/assign-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="de63e-123">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses).</span></span> <span data-ttu-id="de63e-124">Para habilitá-los para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="de63e-124">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="de63e-125">Por exemplo, execute:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="de63e-125">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="de63e-126">Se o serviço de sistema de telefonia que você está criando será aninhado e não precisará de um número de telefone, o processo será:</span><span class="sxs-lookup"><span data-stu-id="de63e-126">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="de63e-127">Criar a conta de recurso</span><span class="sxs-lookup"><span data-stu-id="de63e-127">Create the resource account</span></span>  
2. <span data-ttu-id="de63e-128">Aguardar uma sincronização do Active Directory entre online e local</span><span class="sxs-lookup"><span data-stu-id="de63e-128">Wait for an active directory sync between online and on premise</span></span>
3. <span data-ttu-id="de63e-129">Criar um serviço de sistema de telefonia</span><span class="sxs-lookup"><span data-stu-id="de63e-129">Create a Phone System service</span></span>
4. <span data-ttu-id="de63e-130">Associar a conta de recurso a um serviço de sistema de telefonia</span><span class="sxs-lookup"><span data-stu-id="de63e-130">Associate the resource account with a Phone System service</span></span>

## <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="de63e-131">Criar uma conta de recurso com um número de telefone</span><span class="sxs-lookup"><span data-stu-id="de63e-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="de63e-132">A criação de uma conta de recurso que usa um número de telefone precisaria executar as seguintes tarefas na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="de63e-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="de63e-133">Porta ou obter um número de serviço de chamada tarifada ou gratuita.</span><span class="sxs-lookup"><span data-stu-id="de63e-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="de63e-134">O número não pode ser atribuído a nenhum outro serviço de voz ou contas de recurso.</span><span class="sxs-lookup"><span data-stu-id="de63e-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="de63e-135">Antes de atribuir um número de telefone a uma conta de recurso, você precisará obter ou portar os números de serviço de chamada gratuita ou tarifada existentes.</span><span class="sxs-lookup"><span data-stu-id="de63e-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="de63e-136">Após obter os números de telefone de serviço de chamada tarifada ou gratuita, eles serão exibidos nos**números de telefone**de**voz** > do **Centro** > de administração do Microsoft Teams e o **tipo de número** listado será listado como **serviço de chamada**gratuita.</span><span class="sxs-lookup"><span data-stu-id="de63e-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="de63e-137">Para obter seus números de serviço, consulte [obter números de telefone de serviço](/MicrosoftTeams/getting-service-phone-numbers) ou se você deseja transferir um número de serviço existente, consulte [transferir números de telefone para o Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="de63e-137">To get your service numbers, see [Getting service phone numbers](/MicrosoftTeams/getting-service-phone-numbers) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](/MicrosoftTeams/transfer-phone-numbers-to-office-365).</span></span>

   <span data-ttu-id="de63e-138">Se você estiver fora dos Estados Unidos, não poderá usar o centro de administração do Microsoft Teams para obter os números de serviço.</span><span class="sxs-lookup"><span data-stu-id="de63e-138">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="de63e-139">Vá para [gerenciar números de telefone para sua organização](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) em vez de ver como fazer isso fora dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="de63e-139">Go to [Manage phone numbers for your organization](/MicrosoftTeams/manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization) instead to see how to do it from the outside of the United States.</span></span>

2. <span data-ttu-id="de63e-140">Comprar uma licença do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="de63e-140">Buy a Phone System license.</span></span> <span data-ttu-id="de63e-141">Confira:</span><span class="sxs-lookup"><span data-stu-id="de63e-141">See:</span></span>  
   - [<span data-ttu-id="de63e-142">Office 365 Enterprise E1 e E3</span><span class="sxs-lookup"><span data-stu-id="de63e-142">Office 365 Enterprise E1 and E3</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e1-e3)
   - [<span data-ttu-id="de63e-143">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="de63e-143">Office 365 Enterprise E5</span></span>](/MicrosoftTeams/teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing)
   - [<span data-ttu-id="de63e-144">Software comercial do Office 365 Enterprise e5</span><span class="sxs-lookup"><span data-stu-id="de63e-144">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="de63e-145">Crie uma conta de recurso local executando o `New-CsHybridApplicationEndpoint` cmdlet para cada serviço de sistema de telefonia e dê a cada um deles um nome, endereço SIP e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="de63e-145">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@contoso.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="de63e-146">Consulte [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.</span><span class="sxs-lookup"><span data-stu-id="de63e-146">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

4. <span data-ttu-id="de63e-147">Opcion Depois que suas contas de recursos são criadas, você pode aguardar que o AD seja sincronizado entre online e local, ou forçar uma sincronização e prosseguir para a configuração online de serviços do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="de63e-147">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="de63e-148">Para forçar uma sincronização, você deve executar o seguinte comando no computador que está executando o AAD Connect (se você ainda não tiver feito isso, `import-module adsync` você precisará carregar para executar o comando):</span><span class="sxs-lookup"><span data-stu-id="de63e-148">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="de63e-149">Consulte [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obter mais detalhes sobre este comando.</span><span class="sxs-lookup"><span data-stu-id="de63e-149">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

5. <span data-ttu-id="de63e-150">Atribua a licença do sistema de telefonia à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="de63e-150">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="de63e-151">Consulte [atribuir licenças do Microsoft Teams](/MicrosoftTeams/assign-teams-licenses) e [atribuir licenças a um usuário](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="de63e-151">See [Assign Microsoft Teams licenses](/MicrosoftTeams/assign-teams-licenses) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>

    <span data-ttu-id="de63e-152">Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença de usuário virtual do sistema de telefonia livre de custo.</span><span class="sxs-lookup"><span data-stu-id="de63e-152">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="de63e-153">Isso fornece recursos do sistema de telefonia para números de telefone no nível organizacional e permite que você crie recursos de atendedor automático e fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="de63e-153">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>


6. <span data-ttu-id="de63e-154">Atribua o número de serviço à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="de63e-154">Assign the service number to the resource account.</span></span> <span data-ttu-id="de63e-155">Use o `Set-CsHybridApplicationEndpoint` comando para atribuir um número de telefone (com a opção-LineURI) à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="de63e-155">Use the `Set-CsHybridApplicationEndpoint` command to a assign a phone number (with the -LineURI option) to the resource account.</span></span>

    ``` Powershell
    Set-CsHybridApplicationEndpoint -Identity appinstance01@contoso.com -LineURI tel:+14255550100
    ```

    <span data-ttu-id="de63e-156">Consulte [set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.</span><span class="sxs-lookup"><span data-stu-id="de63e-156">See [Set-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/set-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

    <span data-ttu-id="de63e-157">Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="de63e-157">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

<span data-ttu-id="de63e-158">A conta do recurso precisará de um número de telefone atribuído se ele for atribuído a um atendedor automático de nível superior ou a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="de63e-158">The resource account will need an assigned phone number if it will be assigned to a top level auto attendant or call queue.</span></span> <span data-ttu-id="de63e-159">Os números de telefone do usuário (assinante) não podem ser atribuídos a uma conta de recurso, somente os números de telefone de chamada tarifada ou gratuita de serviço podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="de63e-159">User (subscriber) phone numbers can't be assigned to a resource account, only service toll or toll-free phone numbers can be used.</span></span>

    You can assign a Direct Routing Hybrid number to your resource account.  See [Plan Direct Routing](direct-routing-plan) for details.

    > [!NOTE]
    > Direct Routing service numbers assigned to resource accounts for auto attendant and call queues are supported for Microsoft Teams users and agents only.

    > [!NOTE]
    > Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.

7. <span data-ttu-id="de63e-160">Crie o serviço do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="de63e-160">Create the Phone system service.</span></span> <span data-ttu-id="de63e-161">Confira um dos procedimentos a seguir:</span><span class="sxs-lookup"><span data-stu-id="de63e-161">See one of the following:</span></span>

   - [<span data-ttu-id="de63e-162">Configurar um atendedor automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="de63e-162">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="de63e-163">Criar uma fila de chamada em nuvem</span><span class="sxs-lookup"><span data-stu-id="de63e-163">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  

8. <span data-ttu-id="de63e-164">Associe a conta de recurso ao serviço de sistema de telefonia escolhido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="de63e-164">Associate the resource account with the Phone system service you chose previously.</span></span>

<span data-ttu-id="de63e-165">Um exemplo de uma implementação de pequena empresa está disponível no [exemplo de pequena empresa-configurar um atendedor automático e um](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) [exemplo de pequena empresa-configurar uma fila de chamadas](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span><span class="sxs-lookup"><span data-stu-id="de63e-165">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="de63e-166">Criar uma conta de recurso sem um número de telefone</span><span class="sxs-lookup"><span data-stu-id="de63e-166">Create a resource account without a phone number</span></span>

<span data-ttu-id="de63e-167">Esta seção discute a criação de uma conta de recurso que está hospedada no local.</span><span class="sxs-lookup"><span data-stu-id="de63e-167">This section discusses creating a resource account that is homed on premise.</span></span> <span data-ttu-id="de63e-168">A criação de uma conta de recurso que está hospedada online é abordada em [gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span><span class="sxs-lookup"><span data-stu-id="de63e-168">Creating a resource account that is homed online is discussed at [Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts).</span></span>

<span data-ttu-id="de63e-169">Essas etapas são necessárias se você estiver criando um sistema de serviço de sistema de telefonia novo, ou reconstruindo a estrutura originalmente criada no UM do Exchange.</span><span class="sxs-lookup"><span data-stu-id="de63e-169">These steps are necessary whether you are creating a brand new Phone System service system, or rebuilding structure originally created in Exchange UM.</span></span>

<span data-ttu-id="de63e-170">Faça logon no servidor front-end do Skype for Business e execute os seguintes cmdlets do PowerShell:</span><span class="sxs-lookup"><span data-stu-id="de63e-170">Log in to the Skype for Business front end server and run the following PowerShell cmdlets:</span></span>

1. <span data-ttu-id="de63e-171">Crie uma conta de recurso local executando o `New-CsHybridApplicationEndpoint` cmdlet para cada serviço de sistema de telefonia e dê a cada um deles um nome, endereço SIP e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="de63e-171">Create an on-premises resource account by running the `New-CsHybridApplicationEndpoint` cmdlet for each Phone System service, and give each one a name, sip address, and so on.</span></span>

    ``` Powershell
    New-CsHybridApplicationEndpoint -DisplayName appinstance01 -SipAddress sip:appinstance01@litwareinc.com -OU "ou=Redmond,dc=litwareinc,dc=com"
    ```

    <span data-ttu-id="de63e-172">Consulte [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para obter mais detalhes sobre este comando.</span><span class="sxs-lookup"><span data-stu-id="de63e-172">See [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) for more details on this command.</span></span>

2. <span data-ttu-id="de63e-173">Opcion Depois que suas contas de recursos são criadas, você pode aguardar que o AD seja sincronizado entre online e local, ou forçar uma sincronização e prosseguir para a configuração online de serviços do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="de63e-173">(Optional) Once your resource accounts are created, you can either wait for AD to sync between online and on premise, or force a sync and proceed to online configuration of Phone System services.</span></span> <span data-ttu-id="de63e-174">Para forçar uma sincronização, você deve executar o seguinte comando no computador que está executando o AAD Connect (se você ainda não tiver feito isso, `import-module adsync` você precisará carregar para executar o comando):</span><span class="sxs-lookup"><span data-stu-id="de63e-174">To force a sync you would run the following command on the computer running AAD Connect (if you haven't done so already you would need to load `import-module adsync` to run the command):</span></span>

    ``` Powershell
    Start-ADSyncSyncCycle -PolicyType Delta
    ```

    <span data-ttu-id="de63e-175">Consulte [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) para obter mais detalhes sobre este comando.</span><span class="sxs-lookup"><span data-stu-id="de63e-175">See [Start-ADSyncSyncCycle](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnectsync-feature-scheduler) for more details on this command.</span></span>

3. <span data-ttu-id="de63e-176">Crie o serviço do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="de63e-176">Create the Phone system service.</span></span> <span data-ttu-id="de63e-177">Confira um dos procedimentos a seguir:</span><span class="sxs-lookup"><span data-stu-id="de63e-177">See one of the following:</span></span>
   - [<span data-ttu-id="de63e-178">Configurar um atendedor automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="de63e-178">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)
   - [<span data-ttu-id="de63e-179">Criar uma fila de chamada em nuvem</span><span class="sxs-lookup"><span data-stu-id="de63e-179">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)  
4. <span data-ttu-id="de63e-180">Associe a conta de recurso e o serviço de sistema de telefonia escolhido anteriormente.</span><span class="sxs-lookup"><span data-stu-id="de63e-180">Associate the resource account and the Phone System service you chose previously.</span></span>

<span data-ttu-id="de63e-181">Um exemplo de uma implementação de pequena empresa está disponível no [exemplo de pequena empresa-configurar um atendedor automático e um](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) [exemplo de pequena empresa-configurar uma fila de chamadas](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span><span class="sxs-lookup"><span data-stu-id="de63e-181">An example of a small business implementation is available in  [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) and [Small business example - Set up a call queue](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-cq.yml).</span></span>

## <a name="test-the-implementation"></a><span data-ttu-id="de63e-182">Testar a implementação</span><span class="sxs-lookup"><span data-stu-id="de63e-182">Test the implementation</span></span>

<span data-ttu-id="de63e-183">A melhor maneira de testar a implementação é chamar o número configurado para um serviço de sistema de telefonia e conectar-se a um dos agentes ou menus.</span><span class="sxs-lookup"><span data-stu-id="de63e-183">The best way to test the implementation is to call the number configured for a Phone System service and connect to one of the agents or menus.</span></span> <span data-ttu-id="de63e-184">Você também pode colocar rapidamente uma chamada de teste usando o **botão testar** no painel de ações do centro de administração.</span><span class="sxs-lookup"><span data-stu-id="de63e-184">You can also quickly place a test call by using the **Test button** in the admin center Action pane.</span></span> <span data-ttu-id="de63e-185">Se você deseja fazer alterações em um serviço de sistema de telefonia, selecione-o e, no painel de ações, clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="de63e-185">If you want to make changes to a Phone System service, select it and then in the Action pane click **Edit**.</span></span>

## <a name="moving-an-exchange-um-auto-attendant-or-call-queue-to-phone-system"></a><span data-ttu-id="de63e-186">Mover um atendedor automático ou fila de chamadas do UM do Exchange para o sistema de telefonia</span><span class="sxs-lookup"><span data-stu-id="de63e-186">Moving an Exchange UM auto attendant or call queue to Phone System</span></span>

<span data-ttu-id="de63e-187">A migração do Exchange UM para o sistema de telefonia exigirá a recriação da fila de chamadas e da estrutura de atendedor automático, não há suporte para migrar diretamente de um para o outro.</span><span class="sxs-lookup"><span data-stu-id="de63e-187">Migration from Exchange UM to Phone System will require recreating the call queue and auto attendant structure, directly migrating from one to the other is not supported.</span></span> <span data-ttu-id="de63e-188">Para reimplementar um conjunto de filas de chamadas e atendedores automáticos:</span><span class="sxs-lookup"><span data-stu-id="de63e-188">To re-implement a set of call queues and auto attendants:</span></span>

1. <span data-ttu-id="de63e-189">Obtenha uma lista de todos os atendedores automáticos e filas de chamadas do UM do Exchange executando o seguinte comando no sistema do Exchange 2013 ou 2016 enquanto estiver conectado como administrador:</span><span class="sxs-lookup"><span data-stu-id="de63e-189">Get a list of all Exchange UM auto attendants and call queues by running the following command on the Exchange 2013 or 2016 system while logged in as admin:</span></span>

    ``` Powershell
    Get-UMAutoAttendant | Format-List
    ```

2. <span data-ttu-id="de63e-190">Para cada fila de chamadas ou atendedor automático de UM do Exchange listado, observe seu lugar na estrutura, as configurações e Obtenha cópias de arquivos de som ou texto para fala associados (o GUID na saída será o nome de uma pasta onde os arquivos estão armazenados).</span><span class="sxs-lookup"><span data-stu-id="de63e-190">For each listed Exchange UM call queue or auto attendant, note its place in the structure, settings, and get copies of associated sound or text-to-speech files (the guid in the output will be the name of a folder where the files are stored).</span></span> <span data-ttu-id="de63e-191">Você pode obter estes detalhes executando o comando:</span><span class="sxs-lookup"><span data-stu-id="de63e-191">You can get these details by running the command:</span></span>

    ``` Powershell
    Get-UMAutoAttendant -Identity MyUMAutoAttendant
    ```

    <span data-ttu-id="de63e-192">Consulte [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) para obter mais detalhes sobre este comando.</span><span class="sxs-lookup"><span data-stu-id="de63e-192">See [Get-UMAutoAttendant](https://docs.microsoft.com/powershell/module/exchange/unified-messaging/get-umautoattendant?view=exchange-ps) for more details on this command.</span></span> <span data-ttu-id="de63e-193">Uma lista completa de opções que talvez você precise capturar é em [membros do UMAutoAttendant](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) , mas as opções mais importantes a serem anotadas são:</span><span class="sxs-lookup"><span data-stu-id="de63e-193">A complete list of options you might need to capture is at [UMAutoAttendant members](https://msdn.microsoft.com/library/microsoft.exchange.data.directory.systemconfiguration.umautoattendant_members.aspx) but the most important options to note down are:</span></span>

    - <span data-ttu-id="de63e-194">Horário comercial</span><span class="sxs-lookup"><span data-stu-id="de63e-194">Business hours</span></span>
    - <span data-ttu-id="de63e-195">Horário não comercial</span><span class="sxs-lookup"><span data-stu-id="de63e-195">Non-business hours</span></span>
    - <span data-ttu-id="de63e-196">Idioma</span><span class="sxs-lookup"><span data-stu-id="de63e-196">Language</span></span>
    - <span data-ttu-id="de63e-197">Agendamento de Feriado</span><span class="sxs-lookup"><span data-stu-id="de63e-197">Holiday schedule</span></span>

3. <span data-ttu-id="de63e-198">Crie novos pontos de extremidade locais, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="de63e-198">Create new on-premises endpoints as previously described.</span></span>
   <span data-ttu-id="de63e-199">Atribua o atendedor automático de nível superior um número temporário para fins de teste.</span><span class="sxs-lookup"><span data-stu-id="de63e-199">Assign the top-level auto attendant a temporary number for testing purposes.</span></span>

4. <span data-ttu-id="de63e-200">Configure um serviço de sistema de telefonia que usa os pontos de extremidade conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="de63e-200">Configure a Phone system service that uses the endpoints as previously described.</span></span>

   <span data-ttu-id="de63e-201">Você pode achar útil usar os exercícios no tutorial intitulado [Small Business example-configurar um atendedor automático](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) para criar um mapa lógico das hierarquias em seu antigo sistema de um do Exchange.</span><span class="sxs-lookup"><span data-stu-id="de63e-201">You may find it useful to use the exercises in the tutorial titled [Small business example - Set up an auto attendant](/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa.yml) to create a logical map of the hierarchies in your old Exchange UM system.</span></span>
5. <span data-ttu-id="de63e-202">Teste o serviço do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="de63e-202">Test the Phone System service.</span></span>
6. <span data-ttu-id="de63e-203">Reatribua o número de telefone vinculado à fila de chamadas da UM do Exchange ou ao atendedor automático ao serviço do sistema de telefonia correspondente.</span><span class="sxs-lookup"><span data-stu-id="de63e-203">Reassign the phone number linked to the Exchange UM call queue or auto attendant to the corresponding Phone system service.</span></span>  

   <span data-ttu-id="de63e-204">Neste ponto, se você já tiver migrado UM caixa postal de UM, você deve estar em uma posição para migrar para o Exchange Server 2019.</span><span class="sxs-lookup"><span data-stu-id="de63e-204">At this point, if you have already migrated UM Voicemail, you should be in a position to migrate to Exchange Server 2019.</span></span>

## <a name="see-also"></a><span data-ttu-id="de63e-205">Confira também</span><span class="sxs-lookup"><span data-stu-id="de63e-205">See Also</span></span>

[<span data-ttu-id="de63e-206">Criar uma fila de chamada em nuvem</span><span class="sxs-lookup"><span data-stu-id="de63e-206">Create a Cloud call queue</span></span>](/MicrosoftTeams/create-a-phone-system-call-queue)

[<span data-ttu-id="de63e-207">O que são atendedores automáticos de nuvem?</span><span class="sxs-lookup"><span data-stu-id="de63e-207">What are Cloud auto attendants?</span></span>](/MicrosoftTeams/what-are-phone-system-auto-attendants)

[<span data-ttu-id="de63e-208">Configurar um atendedor automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="de63e-208">Set up a Cloud auto attendant</span></span>](/MicrosoftTeams/create-a-phone-system-auto-attendant)  

[<span data-ttu-id="de63e-209">Planejar atendedores automáticos de nuvem</span><span class="sxs-lookup"><span data-stu-id="de63e-209">Plan Cloud auto attendants</span></span>](plan-cloud-auto-attendant.md)

[<span data-ttu-id="de63e-210">Planejar filas de chamada em nuvem</span><span class="sxs-lookup"><span data-stu-id="de63e-210">Plan Cloud call queues</span></span>](plan-call-queue.md)

[<span data-ttu-id="de63e-211">Planejar o serviço de caixa postal na nuvem para usuários locais</span><span class="sxs-lookup"><span data-stu-id="de63e-211">Plan Cloud Voicemail service for on-premises users</span></span>](plan-cloud-voicemail.md)

[<span data-ttu-id="de63e-212">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="de63e-212">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="de63e-213">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="de63e-213">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

<span data-ttu-id="de63e-214">[Gerenciar contas de recursos no Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(para criar contas de recursos hospedadas online\)</span><span class="sxs-lookup"><span data-stu-id="de63e-214">[Manage resource accounts in Microsoft Teams](/MicrosoftTeams/manage-resource-accounts) - \(to create resource accounts homed online\)</span></span>
