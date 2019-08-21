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
ms.openlocfilehash: 0a53b68af411ad7085ef3abf6e978565f9ea18f0
ms.sourcegitcommit: d4e69d46de564c445feb855cbee55954a7063bba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/21/2019
ms.locfileid: "36483556"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="269f8-103">Gerenciar contas de recursos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="269f8-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="269f8-104">Uma conta de recurso também é conhecida como *objeto de usuário desabilitado* no Azure AD e pode ser usada para representar recursos em geral.</span><span class="sxs-lookup"><span data-stu-id="269f8-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="269f8-105">No Exchange, ele pode ser usado para representar salas de conferência, por exemplo, e permitir que elas tenham um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="269f8-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="269f8-106">Uma conta de recurso pode ser hospedada no Microsoft 365 ou em instalações locais usando o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="269f8-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="269f8-107">No Microsoft Teams ou no Skype for Business Online, cada fila de chamadas do sistema de telefone ou atendedor automático é necessário para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="269f8-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="269f8-108">Se uma conta de recurso precisa de um número de telefone atribuído dependerá do uso pretendido da fila de chamadas ou do atendedor automático associado, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="269f8-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="269f8-109">Você também pode consultar os artigos sobre filas de chamadas e atendedores automáticos vinculados na parte inferior deste artigo antes de atribuir um número de telefone a uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="269f8-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![exemplo de contas de recursos e licenças de usuário](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="269f8-111">Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="269f8-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="269f8-112">Para contas de recursos hospedadas no Skype for Business Server 2019, consulte [Configurar contas de recursos](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="269f8-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>


## <a name="overview"></a><span data-ttu-id="269f8-113">Visão geral</span><span class="sxs-lookup"><span data-stu-id="269f8-113">Overview</span></span>

<span data-ttu-id="269f8-114">Se sua organização já estiver usando pelo menos uma licença do sistema de telefonia, para atribuir um número de telefone a uma fila de chamadas do sistema telefônico ou atendedor automático, o processo será:</span><span class="sxs-lookup"><span data-stu-id="269f8-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue or auto attendant the process is:</span></span>

1. <span data-ttu-id="269f8-115">Obter um número de serviço.</span><span class="sxs-lookup"><span data-stu-id="269f8-115">Obtain a service number.</span></span>
2. <span data-ttu-id="269f8-116">Obter um sistema telefônico gratuito- [licença de usuário virtual](teams-add-on-licensing/virtual-user.md) ou uma licença do sistema de telefonia paga para uso com a conta do recurso ou uma licença do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="269f8-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="269f8-117">Criar a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="269f8-117">Create the resource account.</span></span> <span data-ttu-id="269f8-118">Um atendedor automático ou fila de chamadas é necessário para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="269f8-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="269f8-119">Atribua o sistema telefônico ou um sistema telefônico-licença de usuário virtual para a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="269f8-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="269f8-120">Atribua um número de telefone de serviço à conta de recurso à qual você acabou de atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="269f8-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span> 
6. <span data-ttu-id="269f8-121">Criar uma fila de chamadas do sistema telefônico ou um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="269f8-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="269f8-122">Vincule a conta do recurso a uma fila de chamadas ou atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="269f8-122">Link the resource account with a call queue or auto attendant.</span></span>

<span data-ttu-id="269f8-123">Se o atendedor automático ou a fila de chamadas estiverem aninhados em um atendedor automático de nível superior, a conta do recurso associado só precisará de um número de telefone se você quiser vários pontos de entrada na estrutura de atendedores automáticos e filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="269f8-123">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="269f8-124">Para redirecionar chamadas para as pessoas em sua organização que estão online, elas devem ter uma licença de **sistema telefônico** e estar habilitadas para o Enterprise Voice ou ter planos de chamada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="269f8-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="269f8-125">Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="269f8-125">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="269f8-126">Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="269f8-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="269f8-127">Por exemplo, executar:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="269f8-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="269f8-128">Para evitar problemas com a conta do recurso, siga estas etapas nesta ordem.</span><span class="sxs-lookup"><span data-stu-id="269f8-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="269f8-129">Se a fila de chamadas do sistema de telefonia ou o atendedor automático que você está criando for aninhado e não precisar de um número de telefone, o processo será:</span><span class="sxs-lookup"><span data-stu-id="269f8-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="269f8-130">Criar a conta do recurso</span><span class="sxs-lookup"><span data-stu-id="269f8-130">Create the resource account</span></span> 
2. <span data-ttu-id="269f8-131">Criar uma fila de chamadas do sistema telefônico ou um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="269f8-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="269f8-132">Associar a conta de recurso a uma fila de chamadas do sistema telefônico ou atendedor automático</span><span class="sxs-lookup"><span data-stu-id="269f8-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="269f8-133">Criar uma conta de recurso com um número de telefone</span><span class="sxs-lookup"><span data-stu-id="269f8-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="269f8-134">Um atendedor automático de nível superior ou fila de chamadas exigirá que um número de telefone esteja vinculado ao atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="269f8-134">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="269f8-135">Para criar uma conta de recurso que usa um número de telefone, o processo é:</span><span class="sxs-lookup"><span data-stu-id="269f8-135">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="269f8-136">Porta ou obter um número de serviço de chamada tarifada ou gratuita.</span><span class="sxs-lookup"><span data-stu-id="269f8-136">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="269f8-137">O número não pode ser atribuído a outros serviços de voz ou contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="269f8-137">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="269f8-138">Antes de atribuir um número de telefone a uma conta de recurso, você precisa obter ou portar seus números de serviço de chamada tarifada ou chamada gratuitas existentes.</span><span class="sxs-lookup"><span data-stu-id="269f8-138">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="269f8-139">Depois de obter os números de telefone de serviço de chamada tarifada ou gratuita, eles aparecem\*\*\*\* > \*\*\*\* no centro de **Administração do centro** > de administração do Microsoft Teams, e o **tipo de número** será listado como **serviço-chamada gratuita**.</span><span class="sxs-lookup"><span data-stu-id="269f8-139">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="269f8-140">Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="269f8-140">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>

   <span data-ttu-id="269f8-141">Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença de usuário virtual do sistema de telefone sem custo.</span><span class="sxs-lookup"><span data-stu-id="269f8-141">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="269f8-142">Isso fornece recursos do sistema telefônico para números de telefone no nível organizacional e permite criar atendedores automáticos e recursos da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="269f8-142">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="269f8-143">Obter uma licença de usuário virtual do sistema telefônico ou uma licença normal do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="269f8-143">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span> 

   <span data-ttu-id="269f8-144">Para obter a licença de usuário virtual, a partir do centro de administração do Microsoft 365, acesse**assinaturas complementares** de**Serviços** > de compra de **cobrança** > e role até o fim-você verá a licença "sistema de telefonia-usuário virtual".</span><span class="sxs-lookup"><span data-stu-id="269f8-144">To get the Virtual User license, starting from the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="269f8-145">Selecione **comprar agora**.</span><span class="sxs-lookup"><span data-stu-id="269f8-145">Select **Buy now**.</span></span> <span data-ttu-id="269f8-146">Há um custo zero, mas você ainda precisa seguir estas etapas para adquirir a licença.</span><span class="sxs-lookup"><span data-stu-id="269f8-146">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="269f8-147">Criar uma nova conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="269f8-147">Create a new resource account.</span></span> <span data-ttu-id="269f8-148">Consulte [criar uma conta de recurso no centro de administração do Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [criar uma conta de recurso no PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="269f8-148">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
4. <span data-ttu-id="269f8-149">Atribuir um sistema telefônico- [licença de usuário virtual](teams-add-on-licensing/virtual-user.md) ou licença do sistema de telefonia à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="269f8-149">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="269f8-150">Consulte [atribuir licenças do Microsoft Teams](assign-teams-licenses.md) e [atribuir licenças a um usuário](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span><span class="sxs-lookup"><span data-stu-id="269f8-150">See [Assign Microsoft Teams licenses](assign-teams-licenses.md) and [Assign licenses to one user](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#assign-licenses-to-one-user).</span></span>
5. <span data-ttu-id="269f8-151">Atribua o número de serviço à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="269f8-151">Assign the service number to the resource account.</span></span> <span data-ttu-id="269f8-152">Consulte [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="269f8-152">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="269f8-153">Configure um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="269f8-153">Set up one of the following:</span></span>
   - [<span data-ttu-id="269f8-154">Atendedor automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="269f8-154">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="269f8-155">Fila de chamadas em nuvem</span><span class="sxs-lookup"><span data-stu-id="269f8-155">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="269f8-156">Vincule a conta do recurso ao atendedor automático ou à fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="269f8-156">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="269f8-157">Ver [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="269f8-157">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="269f8-158">Criar uma conta de recurso sem um número de telefone</span><span class="sxs-lookup"><span data-stu-id="269f8-158">Create a resource account without a phone number</span></span>

<span data-ttu-id="269f8-159">Um atendedor automático aninhado ou fila de chamadas exigir uma conta de recurso, mas, em muitos casos, a conta de recurso correspondente não precisará de um número de telefone e do licenciamento necessário para dar suporte a um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="269f8-159">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="269f8-160">A criação de uma conta de recurso que não precisa de um número de telefone exigiria a execução das seguintes tarefas na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="269f8-160">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="269f8-161">Criar uma nova conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="269f8-161">Create a new resource account.</span></span> <span data-ttu-id="269f8-162">Consulte [criar uma conta de recurso no centro de administração do Microsoft Teams](#create-a-resource-account-in-microsoft-teams-admin-center) ou [criar uma conta de recurso no PowerShell](#create-a-resource-account-in-powershell)</span><span class="sxs-lookup"><span data-stu-id="269f8-162">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell)</span></span>
2. <span data-ttu-id="269f8-163">Configure um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="269f8-163">Set up one of the following:</span></span>
   - [<span data-ttu-id="269f8-164">Atendedor automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="269f8-164">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="269f8-165">Fila de chamadas em nuvem</span><span class="sxs-lookup"><span data-stu-id="269f8-165">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="269f8-166">Atribua a conta de recurso à fila de chamadas ou ao atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="269f8-166">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="269f8-167">Ver [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="269f8-167">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>


## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="269f8-168">Criar uma conta de recurso no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="269f8-168">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="269f8-169">Depois de comprar uma licença do sistema telefônico, use o centro de administração do Microsoft Teams para acessar as > **contas de recursos** **das configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="269f8-169">After you've bought a Phone System license, using Microsoft Teams admin center navigate to **Org-wide settings** > **Resource accounts**.</span></span>

![Captura de tela da página contas do recurso](media/r-a-master.png)

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/sfbcallout1.png)

<span data-ttu-id="269f8-172">Para criar uma nova conta de recurso, clique em **+ nova conta**.</span><span class="sxs-lookup"><span data-stu-id="269f8-172">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="269f8-173">No pop-up, preencha o nome para exibição e o nome de usuário da conta do recurso (o nome do domínio deve ser preenchido automaticamente) e clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="269f8-173">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![Captura de tela das opções da nova conta do recurso](media/res-acct.png)

<span data-ttu-id="269f8-175">Em seguida, aplique uma licença para a conta do recurso no centro de administração do O365, conforme descrito em [atribuir licenças a usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="269f8-175">Next, apply a license to the resource account in the O365 Admin center, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

### <a name="edit-resource-account-name"></a><span data-ttu-id="269f8-176">Editar nome da conta do recurso</span><span class="sxs-lookup"><span data-stu-id="269f8-176">Edit resource account name</span></span>

<span data-ttu-id="269f8-177">![Ícone do número 2, fazendo referência a um texto explicativo na](media/sfbcallout2.png) captura de tela anterior, você pode editar o nome de exibição da conta do recurso usando a opção **Editar** .</span><span class="sxs-lookup"><span data-stu-id="269f8-177">![Icon of the number 2, referencing a callout in the previous screenshot](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span> <span data-ttu-id="269f8-178">Clique em **salvar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="269f8-178">Click **Save** when you are done.</span></span>
<span data-ttu-id="269f8-179">![Captura de tela da opção Editar conta de recurso](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="269f8-179">![Screenshot of the Edit resource account option](media/r-a-edit.png)</span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="269f8-180">Atribuir/cancelar a atribuição de números de telefone e serviços</span><span class="sxs-lookup"><span data-stu-id="269f8-180">Assign/Unassign phone numbers and services</span></span>

<span data-ttu-id="269f8-181">![Ícone do número 3, fazendo referência a um texto explicativo na](media/sfbcallout3.png) captura de tela anterior depois de criar a conta do recurso e atribuir a licença, você pode clicar em **atribuir/Cancelar atribuição** para atribuir um número de serviço para a conta do recurso ou atribuir o recurso conta em um atendedor automático ou em uma fila de chamadas que já existe.</span><span class="sxs-lookup"><span data-stu-id="269f8-181">![Icon of the number 3, referencing a callout in the previous screenshot](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="269f8-182">Só é possível fazer a atribuição de um número de roteamento direto usando cmdlets.</span><span class="sxs-lookup"><span data-stu-id="269f8-182">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="269f8-183">Se a fila de chamadas ou o atendedor automático ainda precisar ser criado, você poderá vincular a conta do recurso enquanto a cria.</span><span class="sxs-lookup"><span data-stu-id="269f8-183">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="269f8-184">Clique em **salvar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="269f8-184">Click **Save** when you are done.</span></span>

<span data-ttu-id="269f8-185">Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, você precisará usar o PowerShell, confira a seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="269f8-185">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="269f8-186">Se a sua conta de recurso não tiver uma licença válida, uma verificação interna causará uma falha quando você tentar atribuir o número de telefone à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="269f8-186">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="269f8-187">Você não poderá atribuir o número ou associar a conta do recurso a uma fila de chamadas ou atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="269f8-187">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

![Captura de tela das opções atribuir/Cancelar atribuição](media/r-a-assign.png)

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="269f8-189">Alterar uma conta de recurso existente para usar uma licença de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="269f8-189">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="269f8-190">Se você decidir mudar as licenças de sua conta de recurso existente de uma licença do sistema telefônico para uma licença de usuário virtual, será necessário adquirir a licença de usuário virtual gratuita e, em seguida, seguir as etapas vinculadas no centro de administração do Microsoft 365 para [mover os usuários para um assinatura diferente](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="269f8-190">If you decide to switch the licenses on your existing resource account from a Phone system license to a Virtual User license, you'll need to acquire the free Virtual User license, then follow the linked steps in the Microsoft 365 Admin center to [Move users to a different subscription](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="269f8-191">Sempre remova uma licença completa do sistema de telefonia e atribua a licença de usuário virtual na mesma atividade de licença.</span><span class="sxs-lookup"><span data-stu-id="269f8-191">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="269f8-192">Se você remover a antiga licença, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta do recurso talvez não funcione mais como esperado.</span><span class="sxs-lookup"><span data-stu-id="269f8-192">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="269f8-193">Se isso acontecer, recomendamos que você crie uma nova conta de recurso para a licença de usuário virtual e remova a conta de recurso quebrada.</span><span class="sxs-lookup"><span data-stu-id="269f8-193">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="269f8-194">Criar uma conta de recurso no PowerShell</span><span class="sxs-lookup"><span data-stu-id="269f8-194">Create a resource account in Powershell</span></span>

<span data-ttu-id="269f8-195">Dependendo de se a sua conta de recurso está localizada online ou no local, você precisa se conectar ao prompt apropriado do PowerShell com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="269f8-195">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="269f8-196">Os exemplos dos seguintes cmdlets do PowerShell presumem que a conta do recurso seja hospedada online usando [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para criar uma conta de recurso que está hospedada online.</span><span class="sxs-lookup"><span data-stu-id="269f8-196">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="269f8-197">Para contas de recursos hospedadas localmente no Skype for Business Server 2019 que podem ser usadas com filas de chamadas em nuvem e atendedores automáticos na nuvem, consulte [configurar filas de chamadas em nuvem](/skypeforbusiness/hybrid/configure-call-queue.md) ou [Configurar atendedores automáticos da nuvem](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="269f8-197">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="269f8-198">As implementações híbridas (números hospedados no roteamento direto) usarão [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="269f8-198">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="269f8-199">A identificação do aplicativo que você precisa usar ao criar as instâncias do aplicativo são:</span><span class="sxs-lookup"><span data-stu-id="269f8-199">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="269f8-200">**Atendedor automático:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="269f8-200">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="269f8-201">**Fila de chamadas:** 11cd3e2e-fccb-42AD-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="269f8-201">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="269f8-202">Se quiser que a fila de chamadas ou o atendedor automático seja pesquisado por usuários locais, você deve criar suas contas de recursos no local, pois as contas de recursos online não são sincronizadas com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="269f8-202">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="269f8-203">Para criar uma conta de recurso online para uso com um atendedor automático, use o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="269f8-203">To create a resource account online for use with an auto attendant, use the following command.</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="269f8-204">Você não poderá usar a conta do recurso antes de aplicar uma licença a ele.</span><span class="sxs-lookup"><span data-stu-id="269f8-204">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="269f8-205">Para saber como aplicar uma licença a uma conta no centro de administração do O365, consulte [atribuir licenças a usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) e [atribuir licenças do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="269f8-205">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="269f8-206">Adicionais Depois que a licença correta for aplicada à conta do recurso, você poderá definir um número de telefone para a conta do recurso, como mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="269f8-206">(Optional) Once the correct license is applied to the resource account you can set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="269f8-207">Nem todas as contas do recurso precisarão de um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="269f8-207">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="269f8-208">Se você não aplicou uma licença à conta do recurso, a atribuição de número de telefone falhará.</span><span class="sxs-lookup"><span data-stu-id="269f8-208">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="269f8-209">Consulte [set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) para obter mais detalhes sobre este comando.</span><span class="sxs-lookup"><span data-stu-id="269f8-209">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="269f8-210">É mais fácil definir o número de telefone online usando o centro de administração do Microsoft Teams, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="269f8-210">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

<span data-ttu-id="269f8-211">Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="269f8-211">To assign a direct routing or hybrid number to a resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
```

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="269f8-212">Gerenciar as configurações da conta do recurso no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="269f8-212">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="269f8-213">Para gerenciar as configurações da conta do recurso no centro de administração do Microsoft Teams, navegue até > **contas de recursos**de **configurações de toda a organização**, selecione a conta do recurso para o qual você precisa alterar as configurações e clique no botão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="269f8-213">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="269f8-214">na tela **Editar conta do recurso** , você poderá alterar estas configurações:</span><span class="sxs-lookup"><span data-stu-id="269f8-214">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="269f8-215">**Nome para exibição** da conta</span><span class="sxs-lookup"><span data-stu-id="269f8-215">**Display name** for the account</span></span>
- <span data-ttu-id="269f8-216">Fila de chamadas ou atendedor automático que usa a conta</span><span class="sxs-lookup"><span data-stu-id="269f8-216">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="269f8-217">Número de telefone atribuído à conta</span><span class="sxs-lookup"><span data-stu-id="269f8-217">Phone number assigned to the account</span></span>

<span data-ttu-id="269f8-218">Quando terminar, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="269f8-218">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="269f8-219">Excluir uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="269f8-219">Delete a resource account</span></span>

<span data-ttu-id="269f8-220">Certifique-se de dissociar o número de telefone da conta do recurso antes de excluí-lo para evitar que o número do seu serviço fique preso no modo pendente.</span><span class="sxs-lookup"><span data-stu-id="269f8-220">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="269f8-221">Você pode fazer isso usando o commandlet a seguir:</span><span class="sxs-lookup"><span data-stu-id="269f8-221">You can do that using the following commandlet:</span></span>

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="269f8-222">Depois de fazer isso, você pode excluir a conta do recurso do portal de administração do O365, na guia usuários.</span><span class="sxs-lookup"><span data-stu-id="269f8-222">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>

<span data-ttu-id="269f8-223">Para desassociar um número de telefone de roteamento direto da conta do recurso, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="269f8-223">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="269f8-224">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="269f8-224">Troubleshooting</span></span>

<span data-ttu-id="269f8-225">Caso não veja o número de telefone atribuído à conta do recurso no centro de administração do Teams e não consiga atribuir o número a partir daí, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="269f8-225">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="269f8-226">Se o atributo Department exibir o ponto de extremidade do aplicativo Skype for Business, execute o cmdlet abaixo:</span><span class="sxs-lookup"><span data-stu-id="269f8-226">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below :</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="269f8-227">Atualize a página da Web do centro de administração do teams depois de executar o cmldet, e você deve poder atribuir o número corretamente.</span><span class="sxs-lookup"><span data-stu-id="269f8-227">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="269f8-228">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="269f8-228">Related Information</span></span>

<span data-ttu-id="269f8-229">Para implementações híbridas com o Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="269f8-229">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="269f8-230">Atendedores automáticos do plano da nuvem</span><span class="sxs-lookup"><span data-stu-id="269f8-230">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="269f8-231">Planejar filas de chamadas da nuvem</span><span class="sxs-lookup"><span data-stu-id="269f8-231">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="269f8-232">Configurar contas de recurso local</span><span class="sxs-lookup"><span data-stu-id="269f8-232">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="269f8-233">Para implementações do teams ou do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="269f8-233">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="269f8-234">Quais são os atendedores automáticos do Cloud?</span><span class="sxs-lookup"><span data-stu-id="269f8-234">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="269f8-235">Configurar um atendedor automático do Cloud</span><span class="sxs-lookup"><span data-stu-id="269f8-235">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="269f8-236">Exemplo de pequenas empresas - Configurar um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="269f8-236">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="269f8-237">Criar uma fila de chamada do Cloud</span><span class="sxs-lookup"><span data-stu-id="269f8-237">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="269f8-238">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="269f8-238">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="269f8-239">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="269f8-239">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="269f8-240">Sistema telefônico-licença de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="269f8-240">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
