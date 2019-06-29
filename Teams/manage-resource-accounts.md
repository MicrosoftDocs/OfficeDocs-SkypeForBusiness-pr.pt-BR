---
title: Gerenciar contas de recursos no Teams
ms.author: jambirk
author: jambirk
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Saiba mais sobre como gerenciar contas de recursos no Microsoft Teams
ms.openlocfilehash: 4dcb9327efba7be70628ad71a90734940fc3317e
ms.sourcegitcommit: 016beacc8b64eaeeaefb641360dd9bb8d2191c4a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/29/2019
ms.locfileid: "35394496"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="0f981-103">Gerenciar contas de recursos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0f981-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="0f981-104">Uma conta de recurso também é conhecida como objeto de usuário desabilitado no Azure Active Directory e pode ser usada para representar recursos em geral.</span><span class="sxs-lookup"><span data-stu-id="0f981-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="0f981-105">No Exchange, ele pode ser usado para representar salas de conferência, por exemplo, e permitir que elas tenham um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="0f981-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="0f981-106">Uma conta de recurso pode ser hospedada no Microsoft 365 ou em instalações locais usando o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0f981-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="0f981-107">No Microsoft Teams ou no Skype for Business Online, cada fila de chamadas ou atendedor automático é necessário para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="0f981-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="0f981-108">Se uma conta de recurso precisa de um número de telefone atribuído dependerá do uso pretendido da fila de chamadas ou do atendedor automático associado.</span><span class="sxs-lookup"><span data-stu-id="0f981-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="0f981-109">Consulte os artigos sobre filas de chamadas e atendedores automáticos vinculados na parte inferior deste artigo antes de atribuir um número de telefone a uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="0f981-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="0f981-110">Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="0f981-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="0f981-111">Para contas de recursos hospedadas no Skype for Business Server 2019, consulte [Configurar contas de recursos](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="0f981-111">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="overview"></a><span data-ttu-id="0f981-112">Visão geral</span><span class="sxs-lookup"><span data-stu-id="0f981-112">Overview</span></span>

<span data-ttu-id="0f981-113">Se o seu serviço de sistema telefônico precisará de um número de serviço, as várias dependências podem ser atendidas na seguinte sequência:</span><span class="sxs-lookup"><span data-stu-id="0f981-113">If your Phone System service will need a service number, the various dependencies can be met in the following sequence:</span></span>

1. <span data-ttu-id="0f981-114">Obter um número de serviço</span><span class="sxs-lookup"><span data-stu-id="0f981-114">Obtain a service number</span></span>
2. <span data-ttu-id="0f981-115">Comprar uma licença do sistema de telefonia (Office 365 Enterprise E1 ou E3 com o sistema telefônico adicionado ou o Office 365 Enterprise E5 que inclui o sistema telefônico)</span><span class="sxs-lookup"><span data-stu-id="0f981-115">Buy a Phone System license (Office 365 Enterprise E1 or E3 with Phone System added, or Office 365 Enterprise E5 which includes Phone System)</span></span>
3. <span data-ttu-id="0f981-116">Criar a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="0f981-116">Create the resource account.</span></span> <span data-ttu-id="0f981-117">Um atendedor automático ou fila de chamadas é necessário para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="0f981-117">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="0f981-118">Atribua a licença do sistema de telefone à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="0f981-118">Assign the Phone System license to the resource account.</span></span>
5. <span data-ttu-id="0f981-119">Atribuir um número de telefone à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="0f981-119">Assign a phone number to the resource account.</span></span>
6. <span data-ttu-id="0f981-120">Criar um serviço do sistema telefônico (uma fila de chamadas ou um atendedor automático)</span><span class="sxs-lookup"><span data-stu-id="0f981-120">Create a Phone System service (a call queue or auto attendant)</span></span>
7. <span data-ttu-id="0f981-121">Associar a conta de recurso a um serviço: (novo-CsApplicationInstanceAssociation)</span><span class="sxs-lookup"><span data-stu-id="0f981-121">Associate the resource account with a service: (New-CsApplicationInstanceAssociation)</span></span>

<span data-ttu-id="0f981-122">Se o atendedor automático ou a fila de chamadas estiverem aninhados em um atendedor automático de nível superior, a conta do recurso associado só precisará de um número de telefone se você quiser vários pontos de entrada na estrutura de atendedores automáticos e filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="0f981-122">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="0f981-123">Para redirecionar chamadas para as pessoas em sua organização que estão online, elas devem ter uma licença de **sistema telefônico** e estar habilitadas para o Enterprise Voice ou ter planos de chamada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="0f981-123">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="0f981-124">Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="0f981-124">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="0f981-125">Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0f981-125">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="0f981-126">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="0f981-126">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

<span data-ttu-id="0f981-127">Se o serviço do sistema telefônico que você está criando for aninhado e não precisar de um número de telefone, o processo será:</span><span class="sxs-lookup"><span data-stu-id="0f981-127">If the Phone system service you're creating will be nested and will not need a phone number, the process is:</span></span>

1. <span data-ttu-id="0f981-128">Criar a conta do recurso</span><span class="sxs-lookup"><span data-stu-id="0f981-128">Create the resource account</span></span>  
2. <span data-ttu-id="0f981-129">Criar um serviço do sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="0f981-129">Create a Phone System service</span></span>
3. <span data-ttu-id="0f981-130">Associar a conta de recurso a um serviço de sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="0f981-130">Associate the resource account with a Phone System service</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="0f981-131">Criar uma conta de recurso com um número de telefone</span><span class="sxs-lookup"><span data-stu-id="0f981-131">Create a resource account with a phone number</span></span>

<span data-ttu-id="0f981-132">A criação de uma conta de recurso que usa um número de telefone exigiria a execução das seguintes tarefas na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="0f981-132">Creating a resource account that uses a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="0f981-133">Porta ou obter um número de serviço de chamada tarifada ou gratuita.</span><span class="sxs-lookup"><span data-stu-id="0f981-133">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="0f981-134">O número não pode ser atribuído a outros serviços de voz ou contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="0f981-134">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="0f981-135">Antes de atribuir um número de telefone a uma conta de recurso, você precisará adquirir ou portar seus números de serviço de chamada tarifada ou chamada gratuitas existentes.</span><span class="sxs-lookup"><span data-stu-id="0f981-135">Before you assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="0f981-136">Depois de obter os números de telefone de serviço de chamada tarifada ou gratuita, eles serão exibidos no **Centro** > de administração do Microsoft Teams para**números de telefone**de**voz** > , e o **tipo de número** listado será listado como **serviço-chamada gratuita**.</span><span class="sxs-lookup"><span data-stu-id="0f981-136">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="0f981-137">Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="0f981-137">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

2. <span data-ttu-id="0f981-138">Comprar uma licença do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="0f981-138">Buy a Phone System license.</span></span> <span data-ttu-id="0f981-139">Vejam</span><span class="sxs-lookup"><span data-stu-id="0f981-139">See:</span></span>  
   - [<span data-ttu-id="0f981-140">Office 365 Enterprise E1 e E3</span><span class="sxs-lookup"><span data-stu-id="0f981-140">Office 365 Enterprise E1 and E3</span></span>](teams-add-on-licensing/office-365-enterprise-e1-e3.md)
   - [<span data-ttu-id="0f981-141">Office 365 Enterprise E5</span><span class="sxs-lookup"><span data-stu-id="0f981-141">Office 365 Enterprise E5</span></span>](teams-add-on-licensing/office-365-enterprise-e5-with-audio-conferencing.md)
   - [<span data-ttu-id="0f981-142">Office 365 Enterprise E5 software para empresas</span><span class="sxs-lookup"><span data-stu-id="0f981-142">Office 365 Enterprise E5 Business Software</span></span>](https://products.office.com/business/office-365-enterprise-e5-business-software)

3. <span data-ttu-id="0f981-143">Criar uma nova conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="0f981-143">Create a new resource account.</span></span> <span data-ttu-id="0f981-144">Consulte [criar uma conta de recurso no centro de administração do Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [criar uma conta de recurso no PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="0f981-144">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="0f981-145">Atribua a licença do sistema de telefone à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="0f981-145">Assign the Phone System license to the resource account.</span></span> <span data-ttu-id="0f981-146">Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md) e [atribuir licenças a um usuário](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="0f981-146">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="0f981-147">Atribua o número de serviço à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="0f981-147">Assign the service number to the resource account.</span></span> <span data-ttu-id="0f981-148">Consulte [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="0f981-148">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="0f981-149">Configure um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="0f981-149">Set up one of the following:</span></span>
   - [<span data-ttu-id="0f981-150">Atendedor automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="0f981-150">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="0f981-151">Fila de chamadas em nuvem</span><span class="sxs-lookup"><span data-stu-id="0f981-151">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="0f981-152">Atribua a conta de recurso ao serviço.</span><span class="sxs-lookup"><span data-stu-id="0f981-152">Assign the resource account to the service.</span></span> <span data-ttu-id="0f981-153">Ver [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="0f981-153">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="0f981-154">Criar uma conta de recurso sem um número de telefone</span><span class="sxs-lookup"><span data-stu-id="0f981-154">Create a resource account without a phone number</span></span>

<span data-ttu-id="0f981-155">A criação de uma conta de recurso que não precisa de um número de telefone exigiria a execução das seguintes tarefas na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="0f981-155">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="0f981-156">Criar uma nova conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="0f981-156">Create a new resource account.</span></span> <span data-ttu-id="0f981-157">Consulte [criar uma conta de recurso no centro de administração do Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [criar uma conta de recurso no PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="0f981-157">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="0f981-158">Configure um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="0f981-158">Set up one of the following:</span></span>
   - [<span data-ttu-id="0f981-159">Atendedor automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="0f981-159">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="0f981-160">Fila de chamadas em nuvem</span><span class="sxs-lookup"><span data-stu-id="0f981-160">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="0f981-161">Atribua a conta de recurso ao serviço.</span><span class="sxs-lookup"><span data-stu-id="0f981-161">Assign the resource account to the service.</span></span> <span data-ttu-id="0f981-162">Ver [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="0f981-162">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="0f981-163">Criar uma conta de recurso no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0f981-163">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="0f981-164">Depois de comprar uma licença do sistema de telefonia e um plano de chamada usando o centro de administração do Microsoft Teams, navegue até > **contas de recursos**de **configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="0f981-164">After you've bought a Phone System license and a Calling Plan, using Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Captura de tela da página contas do recurso](media/r-a-master.png)

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="0f981-167">Para criar uma nova conta de recurso, clique em **+ nova conta**.</span><span class="sxs-lookup"><span data-stu-id="0f981-167">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="0f981-168">No pop-up, preencha o nome para exibição e o nome de usuário da conta do recurso (o nome do domínio deve ser preenchido automaticamente) e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="0f981-168">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Captura de tela das opções da nova conta do recurso](media/res-acct.png)

<span data-ttu-id="0f981-170">Em seguida, aplique uma licença para a conta do recurso no centro de administração do O365, conforme descrito em [atribuir licenças a usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="0f981-170">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="0f981-171">Editar nome da conta do recurso</span><span class="sxs-lookup"><span data-stu-id="0f981-171">Edit resource account name</span></span>

<span data-ttu-id="0f981-172">![Ícone do número 2, fazendo referência a um texto explicativo na](media/sfbcallout2.png) captura de tela anterior, você pode editar o nome de exibição da conta do recurso usando a opção **Editar** .</span><span class="sxs-lookup"><span data-stu-id="0f981-172">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="0f981-173">Clique em **salvar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="0f981-173">Click **Save** when you are done.</span></span>
<span data-ttu-id="0f981-174">![Captura de tela da opção Editar conta de recurso](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="0f981-174">![Screen shot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="0f981-175">Atribuir/cancelar a atribuição de números de telefone e serviços</span><span class="sxs-lookup"><span data-stu-id="0f981-175">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="0f981-176">![Ícone do número 3, fazendo referência a um texto explicativo na](media/sfbcallout3.png) captura de tela anterior depois de criar a conta do recurso e atribuir a licença, você pode clicar em **atribuir/Cancelar atribuição** para atribuir um número de serviço para a conta do recurso ou atribuir o recurso conta em um atendedor automático ou em uma fila de chamadas que já existe.</span><span class="sxs-lookup"><span data-stu-id="0f981-176">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="0f981-177">Só é possível fazer a atribuição de um número de roteamento direto usando cmdlets.</span><span class="sxs-lookup"><span data-stu-id="0f981-177">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="0f981-178">Se a fila de chamadas ou o atendedor automático ainda precisar ser criado, você poderá vincular a conta do recurso enquanto a cria.</span><span class="sxs-lookup"><span data-stu-id="0f981-178">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="0f981-179">Clique em **salvar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="0f981-179">Click **Save** when you are done.</span></span>

<span data-ttu-id="0f981-180">Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, você precisará usar o PowerShell, confira a seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="0f981-180">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="0f981-181">Se o seu locatário não tiver uma licença do sistema de telefonia, uma verificação interna causará uma falha quando você tentar atribuir o número de telefone à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="0f981-181">If your tenant doesn't have a Phone System license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="0f981-182">Você não poderá atribuir o número ou associar a conta do recurso a um serviço.</span><span class="sxs-lookup"><span data-stu-id="0f981-182">You won't be able to assign the number or associate the resource account with a service.</span></span>

![Captura de tela das opções atribuir/Cancelar atribuição](media/r-a-assign.png)

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="0f981-184">Criar uma conta de recurso no PowerShell</span><span class="sxs-lookup"><span data-stu-id="0f981-184">Create a resource account in Powershell</span></span>

<span data-ttu-id="0f981-185">Dependendo de se a sua conta de recurso está localizada online ou no local, você precisa se conectar ao prompt apropriado do PowerShell com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="0f981-185">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="0f981-186">Os exemplos dos seguintes cmdlets do PowerShell presumem que a conta do recurso seja hospedada online usando [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para criar uma conta de recurso que está hospedada online.</span><span class="sxs-lookup"><span data-stu-id="0f981-186">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="0f981-187">Para contas de recursos hospedadas localmente no Skype for Business Server 2019 que podem ser usadas com filas de chamadas em nuvem e atendedores automáticos na nuvem, consulte [configurar filas de chamadas em nuvem](/skypeforbusiness/hybrid/configure-call-queue.md) ou [Configurar atendedores automáticos da nuvem](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="0f981-187">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="0f981-188">As implementações híbridas (números hospedados no roteamento direto) usarão [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="0f981-188">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="0f981-189">A identificação do aplicativo que você precisa usar ao criar as instâncias do aplicativo são:</span><span class="sxs-lookup"><span data-stu-id="0f981-189">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="0f981-190">**Atendedor automático:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="0f981-190">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="0f981-191">**Fila de chamadas:** 11cd3e2e-fccb-42AD-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="0f981-191">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="0f981-192">Se quiser que a fila de chamadas ou o atendedor automático seja pesquisado por usuários locais, você deve criar suas contas de recursos no local, pois as contas de recursos online não são sincronizadas com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0f981-192">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="0f981-193">Para criar uma conta de recurso online para uso com um atendedor automático, use o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="0f981-193">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="0f981-194">Você não poderá usar a conta do recurso antes de aplicar uma licença a ele.</span><span class="sxs-lookup"><span data-stu-id="0f981-194">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="0f981-195">Para saber como aplicar uma licença a uma conta no centro de administração do O365, consulte [atribuir licenças a usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) e [atribuir licenças do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="0f981-195">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="0f981-196">Adicionais Depois que a licença correta for aplicada à conta do recurso, você poderá definir um número de telefone para a conta do recurso, como mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="0f981-196">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="0f981-197">Nem todas as contas do recurso precisarão de um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="0f981-197">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="0f981-198">Se você não aplicou uma licença à conta do recurso, a atribuição de número de telefone falhará.</span><span class="sxs-lookup"><span data-stu-id="0f981-198">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="0f981-199">Consulte [set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) para obter mais detalhes sobre este comando.</span><span class="sxs-lookup"><span data-stu-id="0f981-199">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="0f981-200">É mais fácil definir o número de telefone online usando o centro de administração do Microsoft Teams, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="0f981-200">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

<span data-ttu-id="0f981-201">Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0f981-201">To assign a direct routing or hybrid number to  a resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="0f981-202">Gerenciar as configurações da conta do recurso no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0f981-202">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="0f981-203">Para gerenciar as configurações da conta do recurso no centro de administração do Microsoft Teams, navegue até  > **contas de recursos**de **configurações de toda a organização**, selecione a conta do recurso para o qual você precisa alterar as configurações e clique no botão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="0f981-203">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="0f981-204">na tela **Editar conta do recurso** , você poderá alterar estas configurações:</span><span class="sxs-lookup"><span data-stu-id="0f981-204">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="0f981-205">**Nome para exibição** da conta</span><span class="sxs-lookup"><span data-stu-id="0f981-205">**Display name** for the account</span></span>
- <span data-ttu-id="0f981-206">Fila de chamadas ou atendedor automático que usa a conta</span><span class="sxs-lookup"><span data-stu-id="0f981-206">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="0f981-207">Número de telefone atribuído à conta</span><span class="sxs-lookup"><span data-stu-id="0f981-207">Phone number assigned to the account</span></span>

<span data-ttu-id="0f981-208">Quando terminar, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="0f981-208">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="0f981-209">Excluir uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="0f981-209">Delete a resource account</span></span>

<span data-ttu-id="0f981-210">Certifique-se de dissociar o número de telefone da conta do recurso antes de excluí-lo para evitar que o número do seu serviço fique preso no modo pendente.</span><span class="sxs-lookup"><span data-stu-id="0f981-210">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="0f981-211">Você pode fazer isso usando o commandlet a seguir:</span><span class="sxs-lookup"><span data-stu-id="0f981-211">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="0f981-212">Depois de fazer isso, você pode excluir a conta do recurso do portal de administração do O365, na guia usuários.</span><span class="sxs-lookup"><span data-stu-id="0f981-212">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="0f981-213">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="0f981-213">Troubleshooting</span></span>

<span data-ttu-id="0f981-214">Caso não veja o número de telefone atribuído à conta do recurso no centro de administração do Teams e não consiga atribuir o número a partir daí, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0f981-214">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="0f981-215">Se o atributo Department exibir o ponto de extremidade do aplicativo Skype for Business, execute o cmdlet abaixo:</span><span class="sxs-lookup"><span data-stu-id="0f981-215">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId  -Department "Microsoft Communication Application Instance"
```
> [!NOTE]
> <span data-ttu-id="0f981-216">Atualize a página da Web do centro de administração do teams depois de executar o cmldet, e você deve poder atribuir o número corretamente.</span><span class="sxs-lookup"><span data-stu-id="0f981-216">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="0f981-217">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="0f981-217">Related Information</span></span>

<span data-ttu-id="0f981-218">Para implementações híbridas com o Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="0f981-218">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="0f981-219">Atendedores automáticos do plano da nuvem</span><span class="sxs-lookup"><span data-stu-id="0f981-219">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="0f981-220">Configurar os atendedores automáticos da nuvem</span><span class="sxs-lookup"><span data-stu-id="0f981-220">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="0f981-221">Para implementações do teams ou do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="0f981-221">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="0f981-222">Quais são os atendedores automáticos do Cloud?</span><span class="sxs-lookup"><span data-stu-id="0f981-222">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="0f981-223">Configurar um atendedor automático do Cloud</span><span class="sxs-lookup"><span data-stu-id="0f981-223">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="0f981-224">Exemplo de pequenas empresas - Configurar um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="0f981-224">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

[<span data-ttu-id="0f981-225">Criar uma fila de chamada do Cloud</span><span class="sxs-lookup"><span data-stu-id="0f981-225">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="0f981-226">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="0f981-226">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="0f981-227">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="0f981-227">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
