---
title: Gerenciar contas de recursos no Teams
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
ms.reviewer: jastark, wasseemh
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
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
ms.openlocfilehash: 21824c360e26e568ae47a9729960fca01a100ae8
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51094241"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="82eff-103">Gerenciar contas de recursos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="82eff-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="82eff-104">Uma conta de recurso é um objeto de usuário desabilitado no Azure AD e pode ser usada para representar recursos em geral.</span><span class="sxs-lookup"><span data-stu-id="82eff-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="82eff-105">Por exemplo, uma conta de recurso pode ser usada no Exchange para representar salas de conferência e permitir que elas tenham um número de telefone e um calendário.</span><span class="sxs-lookup"><span data-stu-id="82eff-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="82eff-106">Uma conta de recurso pode ser usada no Microsoft 365 ou local usando o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="82eff-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="82eff-107">No Microsoft Teams, uma conta de recurso é necessária para cada atendimento automático ou fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="82eff-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="82eff-108">Contas de recursos também podem ser atribuídas a números de telefone de serviço.</span><span class="sxs-lookup"><span data-stu-id="82eff-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="82eff-109">É assim que você atribui números de telefone a atendimentos automáticos e filas de chamadas permitindo que chamadores de fora do Teams cheguem ao atendimento automático ou fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="82eff-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="82eff-110">Este artigo aborda como criar contas de recursos e a preparar para uso com atendedores automáticos e filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="82eff-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="82eff-111">Antes de iniciar os procedimentos neste artigo, verifique se você fez o seguinte:</span><span class="sxs-lookup"><span data-stu-id="82eff-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="82eff-112">Obter licenças de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="82eff-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="82eff-113">Obter números de serviço</span><span class="sxs-lookup"><span data-stu-id="82eff-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="82eff-114">Obter licenças de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="82eff-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="82eff-115">Cada conta de recurso requer uma licença para trabalhar com atendimentos automáticos e filas de chamada.</span><span class="sxs-lookup"><span data-stu-id="82eff-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="82eff-116">Você pode usar uma licença gratuita do *Microsoft 365 Phone System - Virtual User.*</span><span class="sxs-lookup"><span data-stu-id="82eff-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="82eff-117">Para obter essas licenças, consulte [Licença de usuário virtual](teams-add-on-licensing/virtual-user.md).</span><span class="sxs-lookup"><span data-stu-id="82eff-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="82eff-118">Abrangemos como atribuir a licença a uma conta de recurso posteriormente neste artigo.</span><span class="sxs-lookup"><span data-stu-id="82eff-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="82eff-119">Para obter a licença de Usuário Virtual, no Centro de administração do Microsoft 365, acesse Cobrança De  >    >  **assinaturas** de complemento de serviços de compra e role até o final - você verá Sistema de Telefonia - Licença de Usuário *Virtual.*</span><span class="sxs-lookup"><span data-stu-id="82eff-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="82eff-120">Selecione **Comprar agora**.</span><span class="sxs-lookup"><span data-stu-id="82eff-120">Select **Buy now**.</span></span> <span data-ttu-id="82eff-121">Há um custo zero, mas você ainda precisa seguir estas etapas para adquirir a licença.</span><span class="sxs-lookup"><span data-stu-id="82eff-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="82eff-122">Obter números de serviço</span><span class="sxs-lookup"><span data-stu-id="82eff-122">Obtain service numbers</span></span>

<span data-ttu-id="82eff-123">Os números de serviço são opcionais para os atendimentos automáticos e filas de chamada, no entanto, você precisará de pelo menos um número de serviço para que os chamadores cheguem ao seu atendimento automático e à configuração da fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="82eff-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="82eff-124">Para qualquer atendente automático ou fila de chamada que você deseja acessar diretamente por um número de serviço, você deve ter uma conta de recurso com um número de serviço associado.</span><span class="sxs-lookup"><span data-stu-id="82eff-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="82eff-125">As contas de recursos podem usar números de serviço de tarifação gratuita ou gratuita.</span><span class="sxs-lookup"><span data-stu-id="82eff-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="82eff-126">Você pode solicitar novos números ou portar números existentes de outra operadora.</span><span class="sxs-lookup"><span data-stu-id="82eff-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="82eff-127">Para obter novos números de serviço, consulte [Obter números de telefone de serviço](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="82eff-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="82eff-128">Para por um número de outra operadora, consulte [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="82eff-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="82eff-129">Criar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="82eff-129">Create a resource account</span></span>

<span data-ttu-id="82eff-130">Você pode criar uma conta de recurso no centro de administração do Teams.</span><span class="sxs-lookup"><span data-stu-id="82eff-130">You can create a resource account in the Teams admin center.</span></span>

![Captura de tela da interface do usuário adicionar conta de recurso](media/resource-account-add.png)

1. <span data-ttu-id="82eff-132">No centro de administração do Teams, expanda **configurações** em toda a organização e clique em **Contas de recursos.**</span><span class="sxs-lookup"><span data-stu-id="82eff-132">In the Teams admin center, expand **Org-wide settings**, and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="82eff-133">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="82eff-133">Click **Add**.</span></span>

3. <span data-ttu-id="82eff-134">No painel **Adicionar conta de** recurso, preencha **Nome** de exibição, Nome de **usuário** e tipo de conta **de recurso**.</span><span class="sxs-lookup"><span data-stu-id="82eff-134">In the **Add resource account** pane, fill out **Display name**, **Username**, and the **Resource account type**.</span></span> <span data-ttu-id="82eff-135">O tipo de conta de recurso pode ser **o Atendimento Automático** ou Fila de Chamada, dependendo de como você pretende usar essa conta de recurso. </span><span class="sxs-lookup"><span data-stu-id="82eff-135">The resource account type can be either **Auto attendant** or **Call queue**, depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="82eff-136">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82eff-136">Click **Save**.</span></span>

![Captura de tela de uma lista de contas de recursos](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="82eff-138">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="82eff-138">Assign a license</span></span>

<span data-ttu-id="82eff-139">Para cada conta de recurso, você deve atribuir uma licença do Sistema de Telefonia *do Microsoft 365 - Licença de* Usuário Virtual ou Sistema *de* Telefonia.</span><span class="sxs-lookup"><span data-stu-id="82eff-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Captura de tela da interface do usuário atribuir licenças no centro de administração do Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="82eff-141">No Centro de administração do Microsoft 365, clique na conta de recurso à qual você deseja atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="82eff-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="82eff-142">Na guia **Licenças e Aplicativos,** em **Licenças,** selecione Sistema de Telefonia do **Microsoft 365 - Usuário Virtual**.</span><span class="sxs-lookup"><span data-stu-id="82eff-142">On the **Licenses and Apps** tab, under **Licenses**, select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="82eff-143">Clique **em Salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="82eff-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="82eff-144">Atribuir um número de serviço</span><span class="sxs-lookup"><span data-stu-id="82eff-144">Assign a service number</span></span>

<span data-ttu-id="82eff-145">Se você estiver planejando usar a conta de recurso com um atendimento automático ou fila de chamada que exija um número de serviço, atribua um número à conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="82eff-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![Captura de tela da interface do usuário atribuir número de serviço](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="82eff-147">No Centro de administração  do Teams, na página Contas de recursos, selecione a conta de recurso à qual você deseja atribuir um número de serviço e clique em **Atribuir/desatribuição.**</span><span class="sxs-lookup"><span data-stu-id="82eff-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="82eff-148">No menu **suspenso Tipo de** número de telefone, escolha o tipo de número que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="82eff-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="82eff-149">Na caixa **Número de telefone atribuído,** pesquise o número que deseja usar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="82eff-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="82eff-150">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="82eff-150">Click **Save**.</span></span>


<span data-ttu-id="82eff-151">Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, você precisa usar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="82eff-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="82eff-152">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="82eff-152">Next steps</span></span>

<span data-ttu-id="82eff-153">Depois de concluir a configuração da conta de recurso e atribuir um número de serviço, se necessário, você estará pronto para usar a conta de recurso com um atendimento automático ou fila de chamada.</span><span class="sxs-lookup"><span data-stu-id="82eff-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="82eff-154">Consulte as seguintes referências:</span><span class="sxs-lookup"><span data-stu-id="82eff-154">See the following references:</span></span>

 - [<span data-ttu-id="82eff-155">Atendimento automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="82eff-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="82eff-156">Fila de chamada na nuvem</span><span class="sxs-lookup"><span data-stu-id="82eff-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="82eff-157">Você pode editar a conta de recurso **Nome de exibição** e **tipo de** conta de recurso usando a **opção** Editar.</span><span class="sxs-lookup"><span data-stu-id="82eff-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="82eff-158">Clique **em Salvar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="82eff-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="82eff-159">Alterar uma conta de recurso existente para usar uma licença de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="82eff-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="82eff-160">Se você decidir alternar as licenças em  sua conta de recurso existente de uma licença do Sistema de Telefonia para uma licença de Usuário Virtual, precisará adquirir a licença de Usuário Virtual gratuita e, em seguida, seguir as etapas no Centro de administração do Microsoft 365 para [Mover](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription)usuários para uma assinatura diferente.</span><span class="sxs-lookup"><span data-stu-id="82eff-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="82eff-161">Sempre remova uma Licença completa do Sistema de Telefonia e atribua a licença de Usuário Virtual na mesma atividade de licença.</span><span class="sxs-lookup"><span data-stu-id="82eff-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="82eff-162">Se você remover a licença antiga, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta de recurso poderá não funcionar mais conforme esperado.</span><span class="sxs-lookup"><span data-stu-id="82eff-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="82eff-163">Se isso acontecer, recomendamos que você crie uma nova conta de recurso para a licença de Usuário Virtual e remova a conta de recurso quebrada.</span><span class="sxs-lookup"><span data-stu-id="82eff-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="82eff-164">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="82eff-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="82eff-165">Para contas de recursos ativas no Skype For Business Server 2019 que podem ser usadas com filas de chamadas na nuvem e atendentes automáticos na nuvem, consulte [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="82eff-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="82eff-166">Implementações híbridas (números instalados no Roteamento Direto) são configuradas usando o cmdlet [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) em um servidor local do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="82eff-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="82eff-167">As IDs do aplicativo que você precisa usar ao criar as instâncias do aplicativo são:</span><span class="sxs-lookup"><span data-stu-id="82eff-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="82eff-168">**Atendedor Automático:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="82eff-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="82eff-169">**Fila de Chamada:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="82eff-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="82eff-170">Se você quiser que a fila de chamadas ou o atendimento automático sejam pesquisáveis pelos usuários do Skype For Business Server 2019, crie suas contas de recursos no Skype For Business Server 2019, já que as contas de recursos online não são sincronizadas com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="82eff-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="82eff-171">Quando os registros SRV DNS para sipfederationtls são resolvidos no  Skype for Business Server 2019, as contas de recurso devem ser criadas no Skype For Business Server 2019 usando o shell de Gerenciamento SfB e sincronizadas com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="82eff-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="82eff-172">Para implementações híbridas com o Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="82eff-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="82eff-173">Atendedores automáticos do plano da nuvem</span><span class="sxs-lookup"><span data-stu-id="82eff-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="82eff-174">Planejar filas de chamadas da nuvem</span><span class="sxs-lookup"><span data-stu-id="82eff-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="82eff-175">Configurar contas de recursos no prem</span><span class="sxs-lookup"><span data-stu-id="82eff-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="82eff-176">Excluir uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="82eff-176">Delete a resource account</span></span>

<span data-ttu-id="82eff-177">Certifique-se de dissociar o número de telefone da conta de recurso antes de excluí-lo, para evitar que seu número de serviço seja travado no modo pendente.</span><span class="sxs-lookup"><span data-stu-id="82eff-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="82eff-178">Depois de fazer isso, você pode excluir a conta de recurso no Centro de administração do Microsoft 365, na guia Usuários.</span><span class="sxs-lookup"><span data-stu-id="82eff-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="82eff-179">Para desassociar um número de telefone de roteamento direto da conta de recurso, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="82eff-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```