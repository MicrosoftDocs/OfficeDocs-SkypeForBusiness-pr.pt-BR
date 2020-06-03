---
title: Gerenciar contas de recursos no Teams
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
- seo-marvel-apr2020
description: Neste artigo, você aprenderá a criar, editar e gerenciar contas de recursos no Microsoft Teams.
ms.openlocfilehash: 1ea9d4ebd6cbbb93646555787a04ab5b5516be03
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44512879"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="8c443-103">Gerenciar contas de recursos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c443-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="8c443-104">Uma conta de recurso também é conhecida como *objeto de usuário desabilitado* no Azure AD e pode ser usada para representar recursos em geral.</span><span class="sxs-lookup"><span data-stu-id="8c443-104">A resource account is also known as a *disabled user object* in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="8c443-105">No Exchange, ele pode ser usado para representar salas de conferência, por exemplo, e permitir que elas tenham um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="8c443-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="8c443-106">Uma conta de recurso pode ser hospedada no Microsoft 365 ou em instalações locais usando o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8c443-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="8c443-107">No Microsoft Teams ou no Skype for Business Online, cada fila de chamadas do sistema de telefone ou atendedor automático é necessário para ter pelo menos uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="8c443-107">In Microsoft Teams or Skype for Business Online, each Phone System call queue or auto attendant is required to have at least one associated resource account.</span></span> <span data-ttu-id="8c443-108">Se uma conta de recurso precisa de um número de telefone atribuído dependerá do uso pretendido da fila de chamadas ou do atendedor automático associado, conforme mostrado no diagrama a seguir.</span><span class="sxs-lookup"><span data-stu-id="8c443-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant, as shown in the following diagram.</span></span> <span data-ttu-id="8c443-109">Você também pode consultar os artigos sobre filas de chamadas e atendedores automáticos vinculados na parte inferior deste artigo antes de atribuir um número de telefone a uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="8c443-109">You can also refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

![exemplo de contas de recursos e licenças de usuário](media/resource-account.png)

> [!NOTE]
> <span data-ttu-id="8c443-111">Este artigo se aplica ao Microsoft Teams e ao Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="8c443-111">This article applies to both Microsoft Teams and Skype for Business Online.</span></span> <span data-ttu-id="8c443-112">Para contas de recursos hospedadas no Skype for Business Server 2019, consulte [Configurar contas de recursos](/SkypeForBusiness/hybrid/configure-onprem-ra).</span><span class="sxs-lookup"><span data-stu-id="8c443-112">For resource accounts homed on Skype for Business Server 2019, see [Configure resource accounts](/SkypeForBusiness/hybrid/configure-onprem-ra).</span></span>

## <a name="assign-a-phone-number-to-a-phone-system-call-queue"></a><span data-ttu-id="8c443-113">Atribuir um número de telefone a uma fila de chamadas do sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="8c443-113">Assign a phone number to a Phone System call queue</span></span>

<span data-ttu-id="8c443-114">Se sua organização já estiver usando pelo menos uma licença do sistema de telefonia, para atribuir um número de telefone a uma fila de chamadas do sistema telefônico, o processo será:</span><span class="sxs-lookup"><span data-stu-id="8c443-114">If your organization is already using at least one Phone System license, to assign a phone number to a Phone System call queue the process is:</span></span>

1. <span data-ttu-id="8c443-115">Obter um número de serviço.</span><span class="sxs-lookup"><span data-stu-id="8c443-115">Obtain a service number.</span></span>
2. <span data-ttu-id="8c443-116">Obter um sistema telefônico gratuito- [licença de usuário virtual](teams-add-on-licensing/virtual-user.md) ou uma licença do sistema de telefonia paga para uso com a conta do recurso ou uma licença do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="8c443-116">Obtain a free Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or a paid Phone System license to use with the resource account or a Phone System license.</span></span>
3. <span data-ttu-id="8c443-117">Criar a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="8c443-117">Create the resource account.</span></span> <span data-ttu-id="8c443-118">Um atendedor automático ou fila de chamadas é necessário para ter uma conta de recurso associada.</span><span class="sxs-lookup"><span data-stu-id="8c443-118">An auto attendant or call queue is required to have an associated resource account.</span></span>
4. <span data-ttu-id="8c443-119">Atribua o sistema telefônico ou um sistema telefônico-licença de usuário virtual para a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="8c443-119">Assign the Phone System or a Phone System - Virtual user license to the resource account.</span></span>
5. <span data-ttu-id="8c443-120">Atribua um número de telefone de serviço à conta de recurso à qual você acabou de atribuir licenças.</span><span class="sxs-lookup"><span data-stu-id="8c443-120">Assign a service phone number to the resource account you just assigned licenses to.</span></span>
6. <span data-ttu-id="8c443-121">Criar uma fila de chamadas do sistema telefônico ou um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="8c443-121">Create a Phone System call queue or auto attendant</span></span>
7. <span data-ttu-id="8c443-122">Vincule a conta do recurso a uma fila de chamadas ou atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="8c443-122">Link the resource account with a call queue or auto attendant.</span></span>

<!-- Auto attendants created after November 1st, 2019 also create a new resource account that is associated with the auto attendant. If a phone number is applied to the auto attendant's resource account,  a Phone System - Virtual user license is applied to the resource account if one is available. -->

<span data-ttu-id="8c443-123">Se o atendedor automático ou a fila de chamadas estiverem aninhados em um atendedor automático de nível superior, a conta do recurso associado só precisará de um número de telefone se você quiser vários pontos de entrada na estrutura de atendedores automáticos e filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8c443-123">If the auto attendant or call queue is nested under a top level auto attendant, the associated resource account only needs a phone number if you want multiple points of entry into the structure of auto attendants and call queues.</span></span>

<span data-ttu-id="8c443-124">Para redirecionar chamadas para as pessoas em sua organização que estão online, elas devem ter uma licença de **sistema telefônico** e estar habilitadas para o Enterprise Voice ou ter planos de chamada do Office 365.</span><span class="sxs-lookup"><span data-stu-id="8c443-124">To redirect calls to people in your organization who are homed Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="8c443-125">Consulte [atribuir licenças de Complementos do Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="8c443-125">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md).</span></span> <span data-ttu-id="8c443-126">Para habilitá-las para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8c443-126">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="8c443-127">Por exemplo, executar:`Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="8c443-127">For example run: `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>

> [!WARNING]
> <span data-ttu-id="8c443-128">Para evitar problemas com a conta do recurso, siga estas etapas nesta ordem.</span><span class="sxs-lookup"><span data-stu-id="8c443-128">In order to avoid problems with the resource account, follow these steps in this order.</span></span>

<span data-ttu-id="8c443-129">Se a fila de chamadas do sistema de telefonia ou o atendedor automático que você está criando for aninhado e não precisar de um número de telefone, o processo será:</span><span class="sxs-lookup"><span data-stu-id="8c443-129">If the Phone System call queue or auto attendant you're creating will be nested and won't need a phone number, the process is:</span></span>

1. <span data-ttu-id="8c443-130">Criar a conta do recurso</span><span class="sxs-lookup"><span data-stu-id="8c443-130">Create the resource account</span></span>
2. <span data-ttu-id="8c443-131">Criar uma fila de chamadas do sistema telefônico ou um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="8c443-131">Create a Phone System call queue or auto attendant</span></span>
3. <span data-ttu-id="8c443-132">Associar a conta de recurso a uma fila de chamadas do sistema telefônico ou atendedor automático</span><span class="sxs-lookup"><span data-stu-id="8c443-132">Associate the resource account with a Phone System call queue or auto attendant</span></span>

### <a name="create-a-resource-account-with-a-phone-number"></a><span data-ttu-id="8c443-133">Criar uma conta de recurso com um número de telefone</span><span class="sxs-lookup"><span data-stu-id="8c443-133">Create a resource account with a phone number</span></span>

<span data-ttu-id="8c443-134"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="8c443-134"><a name="phonenumber"> </a></span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c443-135">Um número de telefone não é atribuído diretamente ao atendedor automático ou à fila de chamadas, mas sim à conta de recurso associada ao atendedor automático ou à fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8c443-135">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>

<span data-ttu-id="8c443-136">Um atendedor automático de nível superior ou fila de chamadas exigirá que um número de telefone esteja vinculado ao atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="8c443-136">A top-level auto attendant or call queue will require a phone number be linked to its auto attendant.</span></span> <span data-ttu-id="8c443-137">Para criar uma conta de recurso que usa um número de telefone, o processo é:</span><span class="sxs-lookup"><span data-stu-id="8c443-137">To create a resource account that uses a phone number, the process is:</span></span>

1. <span data-ttu-id="8c443-138">Porta ou obter um número de serviço de chamada tarifada ou gratuita.</span><span class="sxs-lookup"><span data-stu-id="8c443-138">Port or get a toll or toll-free service number.</span></span> <span data-ttu-id="8c443-139">O número não pode ser atribuído a outros serviços de voz ou contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="8c443-139">The number can't be assigned to any other voice services or resource accounts.</span></span>

   <span data-ttu-id="8c443-140">Antes de atribuir um número de telefone a uma conta de recurso, você precisa obter ou portar seus números de serviço de chamada tarifada ou chamada gratuitas existentes.</span><span class="sxs-lookup"><span data-stu-id="8c443-140">Before you assign a phone number to a resource account, you need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="8c443-141">Depois de obter os números de telefone de serviço de chamada tarifada ou gratuita, eles aparecem no **centro de administração do centro de administração do Microsoft Teams**  >  **Voice**  >  **Phone numbers**, e o **tipo de número** será listado como **serviço-chamada gratuita**.</span><span class="sxs-lookup"><span data-stu-id="8c443-141">After you get the toll or toll-free service phone numbers, they show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type**  will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="8c443-142">Para obter seus números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md) ou se você quiser transferir um número de serviço existente, consulte [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="8c443-142">To get your service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md) or if you want to transfer an existing service number, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

   <span data-ttu-id="8c443-143">Se você estiver atribuindo um número de telefone a uma conta de recurso, agora poderá usar a licença de usuário virtual do sistema de telefone sem custo.</span><span class="sxs-lookup"><span data-stu-id="8c443-143">If you are assigning a phone number to a resource account you can now use the cost-free Phone System Virtual User license.</span></span> <span data-ttu-id="8c443-144">Isso fornece recursos do sistema telefônico para números de telefone no nível organizacional e permite criar atendedores automáticos e recursos da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8c443-144">This provides Phone System capabilities to phone numbers at the organizational level, and allows you to create auto attendant and call queue capabilities.</span></span>

2. <span data-ttu-id="8c443-145">Obter uma licença de usuário virtual do sistema telefônico ou uma licença normal do sistema de telefonia.</span><span class="sxs-lookup"><span data-stu-id="8c443-145">Obtain a Phone System Virtual User license or a regular Phone System license.</span></span>

   <span data-ttu-id="8c443-146">Para obter a licença de usuário virtual, no centro de administração do Microsoft 365, **Billing**acesse  >  **Purchase services**  >  **assinaturas complementares** de serviços de compra de cobrança e role até o fim-você verá a licença "sistema de telefonia-usuário virtual".</span><span class="sxs-lookup"><span data-stu-id="8c443-146">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see "Phone System - Virtual User" license.</span></span> <span data-ttu-id="8c443-147">Selecione **comprar agora**.</span><span class="sxs-lookup"><span data-stu-id="8c443-147">Select **Buy now**.</span></span> <span data-ttu-id="8c443-148">Há um custo zero, mas você ainda precisa seguir estas etapas para adquirir a licença.</span><span class="sxs-lookup"><span data-stu-id="8c443-148">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>
3. <span data-ttu-id="8c443-149">Criar uma nova conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="8c443-149">Create a new resource account.</span></span> <span data-ttu-id="8c443-150">Consulte [criar uma conta de recurso no centro de administração do Microsoft Teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) ou [criar uma conta de recurso no PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="8c443-150">See [Create a resource account in the Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>
4. <span data-ttu-id="8c443-151">Atribuir um sistema telefônico- [licença de usuário virtual](teams-add-on-licensing/virtual-user.md) ou licença do sistema de telefonia à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="8c443-151">Assign a Phone System - [Virtual User license](teams-add-on-licensing/virtual-user.md) or Phone System License to the resource account.</span></span> <span data-ttu-id="8c443-152">Consulte [atribuir licenças de Complementos do Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) e [atribuir licenças aos usuários](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span><span class="sxs-lookup"><span data-stu-id="8c443-152">See [Assign Microsoft Teams add-on licenses](teams-add-on-licensing/assign-teams-add-on-licenses.md) and [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).</span></span>
5. <span data-ttu-id="8c443-153">Atribua o número de serviço à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="8c443-153">Assign the service number to the resource account.</span></span> <span data-ttu-id="8c443-154">Consulte [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="8c443-154">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>
6. <span data-ttu-id="8c443-155">Configure um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="8c443-155">Set up one of the following:</span></span>
   - [<span data-ttu-id="8c443-156">Atendedor automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="8c443-156">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="8c443-157">Fila de chamadas em nuvem</span><span class="sxs-lookup"><span data-stu-id="8c443-157">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
7. <span data-ttu-id="8c443-158">Vincule a conta do recurso ao atendedor automático ou à fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8c443-158">Link the resource account to the auto attendant or call queue.</span></span> <span data-ttu-id="8c443-159">Ver [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services)</span><span class="sxs-lookup"><span data-stu-id="8c443-159">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services)</span></span>

<span data-ttu-id="8c443-160">Quando você cria uma conta de recurso durante a criação de um atendedor automático, as licenças são aplicadas automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8c443-160">When you create a resource account while creating an auto attendant, the licenses are applied automatically.</span></span>

### <a name="create-a-resource-account-without-a-phone-number"></a><span data-ttu-id="8c443-161">Criar uma conta de recurso sem um número de telefone</span><span class="sxs-lookup"><span data-stu-id="8c443-161">Create a resource account without a phone number</span></span>

<span data-ttu-id="8c443-162">Um atendedor automático aninhado ou fila de chamadas exigir uma conta de recurso, mas, em muitos casos, a conta de recurso correspondente não precisará de um número de telefone e do licenciamento necessário para dar suporte a um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="8c443-162">A nested auto attendant or call queue will require a resource account, but in many cases the corresponding resource account will not need a phone number and the licensing required to support a phone number.</span></span> <span data-ttu-id="8c443-163">A criação de uma conta de recurso que não precisa de um número de telefone exigiria a execução das seguintes tarefas na seguinte ordem:</span><span class="sxs-lookup"><span data-stu-id="8c443-163">Creating a resource account that does not need a phone number would require performing the following tasks in the following order:</span></span>

1. <span data-ttu-id="8c443-164">Criar uma nova conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="8c443-164">Create a new resource account.</span></span> <span data-ttu-id="8c443-165">Consulte [criar uma conta de recurso no centro de administração do Microsoft Teams](#create-a-resource-account-in-the-microsoft-teams-admin-center) ou [criar uma conta de recurso no PowerShell](#create-a-resource-account-in-powershell).</span><span class="sxs-lookup"><span data-stu-id="8c443-165">See [Create a resource account in Microsoft Teams admin center](#create-a-resource-account-in-the-microsoft-teams-admin-center) or [Create a resource account in Powershell](#create-a-resource-account-in-powershell).</span></span>
2. <span data-ttu-id="8c443-166">Configure um dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="8c443-166">Set up one of the following:</span></span>
   - [<span data-ttu-id="8c443-167">Atendedor automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="8c443-167">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)
   - [<span data-ttu-id="8c443-168">Fila de chamadas em nuvem</span><span class="sxs-lookup"><span data-stu-id="8c443-168">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)
3. <span data-ttu-id="8c443-169">Atribua a conta de recurso à fila de chamadas ou ao atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="8c443-169">Assign the resource account to the call queue or auto attendant.</span></span> <span data-ttu-id="8c443-170">Consulte [atribuir/cancelar a atribuição de números de telefone e serviços](#assignunassign-phone-numbers-and-services).</span><span class="sxs-lookup"><span data-stu-id="8c443-170">See [Assign/Unassign phone numbers and services](#assignunassign-phone-numbers-and-services).</span></span>


## <a name="create-a-resource-account-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="8c443-171">Criar uma conta de recurso no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c443-171">Create a resource account in the Microsoft Teams admin center</span></span>

<span data-ttu-id="8c443-172">Depois de comprar uma licença do sistema de telefonia, na navegação à esquerda do centro de administração do Microsoft Teams, vá para contas de recursos de **configurações de toda a organização**  >  **Resource accounts**.</span><span class="sxs-lookup"><span data-stu-id="8c443-172">After you've bought a Phone System license, in the left navigation of the Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**.</span></span>

![Captura de tela da página contas do recurso](media/r-a-master.png)

![Ícone do número 1, fazendo referência a um texto explicativo na captura de tela anterior](media/teamscallout1.png)

<span data-ttu-id="8c443-175">Para criar uma nova conta de recurso, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="8c443-175">To create a new resource account, click **Add**.</span></span> <span data-ttu-id="8c443-176">No painel **adicionar conta do recurso** , preencha o **nome para exibição**, o nome de **usuário** (o nome do domínio deve ser preenchido automaticamente) e o tipo de **conta de recurso** para a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="8c443-176">In the **Add resource account** pane, fill out **Display name**, **Username** (the domain name should populate automatically), and **Resource account type** for the resource account.</span></span> <span data-ttu-id="8c443-177">O tipo de conta de recurso pode ser o **atendedor automático** ou a **fila de chamadas**, dependendo do aplicativo que você pretende associar à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="8c443-177">The resource account type can be either **Auto attendant** or **Call queue**, depending on the app you intend to associate to the resource account.</span></span> <span data-ttu-id="8c443-178">Quando estiver pronto, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="8c443-178">When you're ready, click **Save**.</span></span>

![Captura de tela das opções da nova conta do recurso](media/res-acct.png)

<span data-ttu-id="8c443-180"><a name="enablesignin"> </a></span><span class="sxs-lookup"><span data-stu-id="8c443-180"><a name="enablesignin"> </a></span></span>

<span data-ttu-id="8c443-181">Quando você cria uma conta de recurso, a conexão é bloqueada para a conta.</span><span class="sxs-lookup"><span data-stu-id="8c443-181">When you create a resource account, sign in is blocked for the account.</span></span> <span data-ttu-id="8c443-182">Você verá uma faixa na parte superior do painel que diz que a conta do recurso não pode ser carregada.</span><span class="sxs-lookup"><span data-stu-id="8c443-182">You'll see a banner at the top of the pane that says the resource account can't be loaded.</span></span> <span data-ttu-id="8c443-183">Você deve desbloquear o login para a conta do recurso no centro de administração do Microsoft 365 para que a conta do recurso tenha permissão para entrar.</span><span class="sxs-lookup"><span data-stu-id="8c443-183">You have to unblock sign in for the resource account in the Microsoft 365 admin center so that the resource account is allowed to sign in.</span></span> <span data-ttu-id="8c443-184">Para fazer isso, no centro de administração do 365 da Microsoft, vá para **usuários**, procure e selecione a conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="8c443-184">To do this, in the Microsoft 365 admin center, go to **Users**, search for, and then select the resource account.</span></span> <span data-ttu-id="8c443-185">Na parte superior do painel sob o nome para exibição, clique em **desbloquear este usuário?**, desmarque a caixa de seleção **bloquear o usuário para entrar** e clique em **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="8c443-185">At the top of the pane under the display name, click **Unblock this user?**, clear the **Block this user from signing in** check box, and then click **Save changes**.</span></span>

![Captura de tela da opção desbloquear este usuário](media/res-acct-unblock.png)

<span data-ttu-id="8c443-187">Depois de fazer isso, você verá "entrar permitido" sob o nome para exibição.</span><span class="sxs-lookup"><span data-stu-id="8c443-187">After you do this, you'll see "Sign in allowed" under the display name.</span></span> 

![Captura de tela da mensagem de entrada permitida](media/res-acct-sign-in-allowed.png)

<span data-ttu-id="8c443-189">Em seguida, aplique uma licença para a conta do recurso no centro de administração do Microsoft 365, conforme descrito em [atribuir licenças aos usuários](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide).</span><span class="sxs-lookup"><span data-stu-id="8c443-189">Next, apply a license to the resource account in the Microsoft 365 admin center, as described in [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users?view=o365-worldwide).</span></span>

### <a name="edit-resource-account"></a><span data-ttu-id="8c443-190">Editar conta do recurso</span><span class="sxs-lookup"><span data-stu-id="8c443-190">Edit resource account</span></span> 

<span data-ttu-id="8c443-191">![Ícone do número 2, fazendo referência a um texto explicativo na captura de tela anterior, ](media/teamscallout2.png) você pode editar o **nome para exibição** da conta do recurso e o tipo de **conta do recurso** usando a opção **Editar** .</span><span class="sxs-lookup"><span data-stu-id="8c443-191">![Icon of the number 2, referencing a callout in the previous screenshot](media/teamscallout2.png) You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="8c443-192">Clique em **salvar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="8c443-192">Click **Save** when you are done.</span></span>

![Captura de tela da opção Editar conta de recurso](media/r-a-edit.png)

<span data-ttu-id="8c443-194"><a name="phonenumber"> </a></span><span class="sxs-lookup"><span data-stu-id="8c443-194"><a name="phonenumber"> </a></span></span>

### <a name="assignunassign-phone-numbers-and-services"></a><span data-ttu-id="8c443-195">Atribuir/cancelar a atribuição de números de telefone e serviços</span><span class="sxs-lookup"><span data-stu-id="8c443-195">Assign/unassign phone numbers and services</span></span>

<span data-ttu-id="8c443-196">![Ícone do número 3, fazendo referência a um texto explicativo na captura de tela anterior ](media/teamscallout3.png) depois de criar a conta do recurso e atribuir a licença, você pode clicar em **atribuir/Cancelar atribuição** para atribuir um número de serviço para a conta do recurso, definir o tipo de número de telefone ou atribuir a conta de recurso a um atendedor automático específico ou fila de chamadas que já existe.</span><span class="sxs-lookup"><span data-stu-id="8c443-196">![Icon of the number 3, referencing a callout in the previous screenshot](media/teamscallout3.png) After you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a service number to the resource account, set the phone number type, or assign the resource account to a specific auto attendant or call queue that already exists.</span></span> <span data-ttu-id="8c443-197">Só é possível fazer a atribuição de um número de roteamento direto usando cmdlets.</span><span class="sxs-lookup"><span data-stu-id="8c443-197">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="8c443-198">Se você ainda não criou a fila de chamadas ou o atendedor automático, será possível associá-lo à conta do recurso, deixe o campo em branco.</span><span class="sxs-lookup"><span data-stu-id="8c443-198">If you haven't yet created the  call queue or auto attendant you will associate to the resource account,leave that field blank.</span></span> <span data-ttu-id="8c443-199">Você pode vincular a conta do recurso enquanto a cria.</span><span class="sxs-lookup"><span data-stu-id="8c443-199">You can link the resource account while you create it.</span></span> <span data-ttu-id="8c443-200">Clique em **salvar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="8c443-200">Click **Save** when you are done.</span></span>

<span data-ttu-id="8c443-201">As opções para o **tipo de número de telefone** são:</span><span class="sxs-lookup"><span data-stu-id="8c443-201">Options for the **Phone number type** are:</span></span>

- <span data-ttu-id="8c443-202">Nenhum</span><span class="sxs-lookup"><span data-stu-id="8c443-202">None</span></span>
- <span data-ttu-id="8c443-203">Online</span><span class="sxs-lookup"><span data-stu-id="8c443-203">Online</span></span>
- <span data-ttu-id="8c443-204">Chamada gratuita</span><span class="sxs-lookup"><span data-stu-id="8c443-204">Toll-free</span></span>
- <span data-ttu-id="8c443-205">Local</span><span class="sxs-lookup"><span data-stu-id="8c443-205">On-premises</span></span>

![Captura de tela das opções atribuir/Cancelar atribuição](media/r-a-assign.png)

<span data-ttu-id="8c443-207">Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, você precisará usar o PowerShell, confira a seção a seguir.</span><span class="sxs-lookup"><span data-stu-id="8c443-207">To assign a direct routing or hybrid number to a resource account you will need to use PowerShell, see the following section.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c443-208">Se a sua conta de recurso não tiver uma licença válida, uma verificação interna causará uma falha quando você tentar atribuir o número de telefone à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="8c443-208">If your resource account doesn't have a valid license, an internal check will cause a failure when you try to assign the phone number to the resource account.</span></span> <span data-ttu-id="8c443-209">Você não poderá atribuir o número ou associar a conta do recurso a uma fila de chamadas ou atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="8c443-209">You won't be able to assign the number or associate the resource account with a call queue or auto attendant.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8c443-210">Um número de telefone não é atribuído diretamente ao atendedor automático ou à fila de chamadas, mas sim à conta de recurso associada ao atendedor automático ou à fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="8c443-210">A phone number is not assigned directly to the auto attendant or call queue, but rather to the resource account associated to the auto attendant or call queue.</span></span>



## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="8c443-211">Alterar uma conta de recurso existente para usar uma licença de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="8c443-211">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="8c443-212">Se você decidir mudar as licenças de sua conta de recurso existente de uma licença do sistema telefônico para uma licença de usuário virtual, será necessário adquirir a licença de usuário virtual gratuita e, em seguida, seguir as etapas no centro de administração do Microsoft 365 para [mover os usuários para uma assinatura diferente](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="8c443-212">If you decide to switch the licenses on your existing resource account from a Phone System license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide#move-users-to-a-different-subscription).</span></span> 

> [!WARNING]
> <span data-ttu-id="8c443-213">Sempre remova uma licença completa do sistema de telefonia e atribua a licença de usuário virtual na mesma atividade de licença.</span><span class="sxs-lookup"><span data-stu-id="8c443-213">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="8c443-214">Se você remover a antiga licença, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta do recurso talvez não funcione mais como esperado.</span><span class="sxs-lookup"><span data-stu-id="8c443-214">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="8c443-215">Se isso acontecer, recomendamos que você crie uma nova conta de recurso para a licença de usuário virtual e remova a conta de recurso quebrada.</span><span class="sxs-lookup"><span data-stu-id="8c443-215">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span> 

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="8c443-216">Criar uma conta de recurso no PowerShell</span><span class="sxs-lookup"><span data-stu-id="8c443-216">Create a resource account in Powershell</span></span>

<span data-ttu-id="8c443-217">Dependendo de se a sua conta de recurso estiver localizada online ou no Skype for Business Server 2019, você precisará se conectar ao prompt apropriado do PowerShell com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="8c443-217">Depending on whether your resource account is located online or on Skype for Business Server 2019, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="8c443-218">Os exemplos dos seguintes cmdlets do PowerShell mostram a criação de uma conta de recurso hospedada online usando [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="8c443-218">The following Powershell cmdlet examples show creating a resource account homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps).</span></span> 

- <span data-ttu-id="8c443-219">Para contas de recursos hospedadas no Skype for Business Server 2019 que podem ser usadas com filas de chamadas em nuvem e atendedores automáticos na nuvem, consulte [planejar filas de chamadas na](/SkypeforBusiness/hybrid/plan-call-queue) nuvem ou reportar [atendedores automáticos da nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="8c443-219">For resource accounts homed on Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="8c443-220">As implementações híbridas (números hospedados no roteamento direto) são configuradas usando o cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) em um servidor local do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="8c443-220">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="8c443-221">A identificação do aplicativo que você precisa usar ao criar as instâncias do aplicativo são:</span><span class="sxs-lookup"><span data-stu-id="8c443-221">The application ID's that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="8c443-222">**Atendedor automático:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="8c443-222">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="8c443-223">**Fila de chamadas:** 11cd3e2e-fccb-42AD-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="8c443-223">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="8c443-224">Se quiser que a fila de chamadas ou o atendedor automático seja pesquisável pelos usuários do Skype for Business Server 2019, você deve criar suas contas de recursos no Skype for Business Server 2019, pois as contas de recursos online não são sincronizadas com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="8c443-224">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="8c443-225">Quando os registros SRV DNS para sipfederationtls são resolvidos para o Skype for Business Server 2019, as contas de recursos **devem** ser criadas no Skype for business Server 2019 usando o Shell de gerenciamento SfB e sincronizadas com o Azure ad online.</span><span class="sxs-lookup"><span data-stu-id="8c443-225">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to online Azure AD.</span></span>

 

1. <span data-ttu-id="8c443-226">Para criar uma conta de recurso online para uso com um atendedor automático, use o seguinte comando:</span><span class="sxs-lookup"><span data-stu-id="8c443-226">To create a resource account online for use with an auto attendant, use the following command:</span></span>

    ``` Powershell
    New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId "ce933385-9390-45d1-9512-c8d228074e07" -DisplayName "Resource account 1"
    ```

2. <span data-ttu-id="8c443-227">Você não poderá usar a conta do recurso antes de aplicar uma licença a ele.</span><span class="sxs-lookup"><span data-stu-id="8c443-227">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="8c443-228">Para saber como aplicar uma licença a uma conta no centro de administração do Microsoft 365, consulte [atribuir licenças a usuários](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) e [atribuir licenças do Skype for Business](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="8c443-228">For how to apply a license to an account in the Microsoft 365 admin center, see [Assign licenses to users](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users) and [Assign Skype for Business licenses](https://docs.microsoft.com/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="8c443-229">Adicionais Após a licença correta ser aplicada à conta do recurso, você pode atribuir um número de telefone à conta do recurso, como mostrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="8c443-229">(Optional) After the correct license is applied to the resource account, you can assign a phone number to the resource account as shown below.</span></span> <span data-ttu-id="8c443-230">Nem todas as contas do recurso precisarão de um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="8c443-230">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="8c443-231">Se você não aplicou uma licença à conta do recurso, a atribuição de número de telefone falhará.</span><span class="sxs-lookup"><span data-stu-id="8c443-231">If you didn't apply a license to the resource account, the phone number assignment will fail.</span></span>

   ``` Powershell
   Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com -TelephoneNumber +14255550100
   Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
   ```

   <span data-ttu-id="8c443-232">Consulte [set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) para obter mais detalhes sobre este comando.</span><span class="sxs-lookup"><span data-stu-id="8c443-232">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

   > [!NOTE]
   > <span data-ttu-id="8c443-233">É mais fácil definir o número de telefone online usando o centro de administração do Microsoft Teams, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="8c443-233">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

   <span data-ttu-id="8c443-234">Para atribuir um número de telefone de roteamento direto a uma conta de recurso (em equipe no Microsoft Teams ou no Skype for Business Server 2019), use o cmdlet a seguir para o Skype for Business online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="8c443-234">To assign a direct routing phone number to a resource account (homed either in Microsoft Teams or Skype For Business Server 2019), use the following cmdlet for Skype for Business Online Powershell:</span></span>

   ``` Powershell
   Set-CsOnlineApplicationInstance -Identity appinstance01@contoso.com -OnpremPhoneNumber +14250000000
   ```

## <a name="manage-resource-account-settings-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="8c443-235">Gerenciar as configurações da conta do recurso no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8c443-235">Manage resource account settings in the Microsoft Teams admin center</span></span>

<span data-ttu-id="8c443-236">Para gerenciar as configurações da conta do recurso no centro de administração do Microsoft Teams, vá para contas de recursos de **configurações de toda**  >  **Resource accounts**a organização, selecione a conta do recurso para o qual você precisa alterar as configurações e clique em **Editar**.</span><span class="sxs-lookup"><span data-stu-id="8c443-236">To manage resource account settings in Microsoft Teams admin center, go to **Org-wide settings** > **Resource accounts**, select the resource account you need to change settings for, and then click **Edit**.</span></span> <span data-ttu-id="8c443-237">No painel **Editar conta de recurso** , você pode alterar estas configurações:</span><span class="sxs-lookup"><span data-stu-id="8c443-237">On the **Edit resource account** pane, you can change these settings:</span></span>

- <span data-ttu-id="8c443-238">**Nome para exibição** da conta</span><span class="sxs-lookup"><span data-stu-id="8c443-238">**Display name** for the account</span></span>
- <span data-ttu-id="8c443-239">Fila de chamadas ou atendedor automático que usa a conta</span><span class="sxs-lookup"><span data-stu-id="8c443-239">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="8c443-240">Número de telefone atribuído à conta</span><span class="sxs-lookup"><span data-stu-id="8c443-240">Phone number assigned to the account</span></span>

<span data-ttu-id="8c443-241">Quando terminar, clique em **salvar**.</span><span class="sxs-lookup"><span data-stu-id="8c443-241">When finished, click **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="8c443-242">Excluir uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="8c443-242">Delete a resource account</span></span>

<span data-ttu-id="8c443-243">Certifique-se de dissociar o número de telefone da conta do recurso antes de excluí-lo para evitar que o número do seu serviço fique preso no modo pendente.</span><span class="sxs-lookup"><span data-stu-id="8c443-243">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="8c443-244">Você pode fazer isso usando o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8c443-244">You can do that using the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity <Resource Account oid> -TelephoneNumber $null
```

<span data-ttu-id="8c443-245">Depois de fazer isso, você pode excluir a conta do recurso no centro de administração do Microsoft 365, na guia usuários.</span><span class="sxs-lookup"><span data-stu-id="8c443-245">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="8c443-246">Para desassociar um número de telefone de roteamento direto da conta do recurso, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="8c443-246">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

``` Powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```

## <a name="troubleshooting"></a><span data-ttu-id="8c443-247">Solução de problemas</span><span class="sxs-lookup"><span data-stu-id="8c443-247">Troubleshooting</span></span>

<span data-ttu-id="8c443-248">Caso não veja o número de telefone atribuído à conta do recurso no centro de administração do Teams e não consiga atribuir o número a partir daí, verifique o seguinte:</span><span class="sxs-lookup"><span data-stu-id="8c443-248">In case you do not see the phone number assigned to the resource account on the Teams Admin Center and you are unable to assign the number from there, please check the following:</span></span>

``` Powershell
Get-MsolUser -UserPrincipalName "username@contoso.com"| fl objectID,department
```

<span data-ttu-id="8c443-249">Se o atributo Department exibir o ponto de extremidade do aplicativo Skype for Business, execute o cmdlet abaixo:</span><span class="sxs-lookup"><span data-stu-id="8c443-249">If the department attribute displays Skype for Business Application Endpoint please run the cmdlet below:</span></span>

``` Powershell
Set-MsolUser -ObjectId -Department "Microsoft Communication Application Instance"
```

> [!NOTE]
> <span data-ttu-id="8c443-250">Atualize a página da Web do centro de administração do teams depois de executar o cmldet, e você deve poder atribuir o número corretamente.</span><span class="sxs-lookup"><span data-stu-id="8c443-250">Refresh the Teams Admin center webpage after running the cmldet, and you should be able to assign the number correctly.</span></span>

## <a name="related-information"></a><span data-ttu-id="8c443-251">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="8c443-251">Related Information</span></span>

<span data-ttu-id="8c443-252">Para implementações híbridas com o Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="8c443-252">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="8c443-253">Atendedores automáticos do plano da nuvem</span><span class="sxs-lookup"><span data-stu-id="8c443-253">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="8c443-254">Planejar filas de chamadas da nuvem</span><span class="sxs-lookup"><span data-stu-id="8c443-254">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="8c443-255">Configurar contas de recurso local</span><span class="sxs-lookup"><span data-stu-id="8c443-255">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


<span data-ttu-id="8c443-256">Para implementações do teams ou do Skype for Business Online:</span><span class="sxs-lookup"><span data-stu-id="8c443-256">For implementations in Teams or Skype for Business Online:</span></span>

   [<span data-ttu-id="8c443-257">Quais são os atendedores automáticos do Cloud?</span><span class="sxs-lookup"><span data-stu-id="8c443-257">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

   [<span data-ttu-id="8c443-258">Configurar um atendedor automático do Cloud</span><span class="sxs-lookup"><span data-stu-id="8c443-258">Set up a Cloud auto attendant</span></span>](/microsoftteams/create-a-phone-system-auto-attendant)

   [<span data-ttu-id="8c443-259">Exemplo de pequenas empresas - Configurar um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="8c443-259">Small business example - Set up an auto attendant</span></span>](/microsoftteams/tutorial-org-aa)

   [<span data-ttu-id="8c443-260">Criar uma fila de chamada do Cloud</span><span class="sxs-lookup"><span data-stu-id="8c443-260">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="8c443-261">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="8c443-261">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="8c443-262">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="8c443-262">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)

[<span data-ttu-id="8c443-263">New-CsOnlineApplicationInstanceAssociation</span><span class="sxs-lookup"><span data-stu-id="8c443-263">New-CsOnlineApplicationInstanceAssociation</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstanceassociation?view=skype-ps)

[<span data-ttu-id="8c443-264">Sistema telefônico-licença de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="8c443-264">Phone System - Virtual User license</span></span>](teams-add-on-licensing/virtual-user.md)
