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
ms.openlocfilehash: 2a043b608dfe311003dea26acc8a0c236460fad5
ms.sourcegitcommit: 57fddb045f4a9df14cc421b1f6a228df91f334de
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49031017"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="0ac8a-103">Gerenciar contas de recursos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="0ac8a-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="0ac8a-104">Uma conta de recurso é um objeto de usuário desabilitado no Azure AD e pode ser usada para representar recursos em geral.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-104">A resource account is a disabled user object in Azure AD, and can be used to represent resources in general.</span></span> <span data-ttu-id="0ac8a-105">Por exemplo, uma conta de recurso pode ser usada no Exchange para representar salas de conferência e permitir que elas tenham um número de telefone e um calendário.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-105">For example, a resource account may be used in Exchange to represent conference rooms and allow them to have a phone number and calendar.</span></span> <span data-ttu-id="0ac8a-106">Uma conta de recurso pode ser hospedada no Microsoft 365 ou em instalações locais usando o Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business Server 2019.</span></span>

<span data-ttu-id="0ac8a-107">No Microsoft Teams, uma conta de recurso é necessária para cada atendedor automático ou fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-107">In Microsoft Teams, a resource account is required for each auto attendant or call queue.</span></span> <span data-ttu-id="0ac8a-108">As contas de recursos também podem ser atribuídas a números de telefone de serviço.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-108">Resource accounts may also be assigned service telephone numbers.</span></span> <span data-ttu-id="0ac8a-109">É assim que você atribui números de telefone a atendedores automáticos e filas de chamadas, permitindo que os chamadores de equipes externas atinjam o atendedor automático ou a fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-109">This is how you assign phone numbers to auto attendants and call queues allowing callers from outside Teams to reach the auto attendant or call queue.</span></span>

<span data-ttu-id="0ac8a-110">Este artigo aborda como criar contas de recursos e prepará-las para uso com atendedores automáticos e filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-110">This article covers how to create resource accounts and ready them for use with auto attendants and call queues.</span></span>

<span data-ttu-id="0ac8a-111">Antes de iniciar os procedimentos deste artigo, verifique se você fez o seguinte:</span><span class="sxs-lookup"><span data-stu-id="0ac8a-111">Before you start the procedures in this article, ensure you've done the following:</span></span>

- [<span data-ttu-id="0ac8a-112">Obter licenças de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="0ac8a-112">Obtain virtual user licenses</span></span>](#obtain-virtual-user-licenses)
- [<span data-ttu-id="0ac8a-113">Obter números de serviço</span><span class="sxs-lookup"><span data-stu-id="0ac8a-113">Obtain service numbers</span></span>](#obtain-service-numbers)

### <a name="obtain-virtual-user-licenses"></a><span data-ttu-id="0ac8a-114">Obter licenças de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="0ac8a-114">Obtain virtual user licenses</span></span>

<span data-ttu-id="0ac8a-115">Cada conta de recurso requer uma licença para funcionar com atendedores automáticos e filas de chamadas.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-115">Each resource account requires a license in order to work with auto attendants and call queues.</span></span> <span data-ttu-id="0ac8a-116">Você pode usar um *sistema telefônico gratuito Microsoft 365-licença de usuário virtual* .</span><span class="sxs-lookup"><span data-stu-id="0ac8a-116">You can use a free *Microsoft 365 Phone System - Virtual User* license.</span></span> <span data-ttu-id="0ac8a-117">Para obter essas licenças, consulte [licença de usuário virtual](teams-add-on-licensing/virtual-user.md).</span><span class="sxs-lookup"><span data-stu-id="0ac8a-117">To obtain these licenses, see [Virtual User license](teams-add-on-licensing/virtual-user.md).</span></span>

<span data-ttu-id="0ac8a-118">Nós abordamos como atribuir a licença a uma conta de recurso mais adiante neste artigo.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-118">We cover how to assign the license to a resource account later in this article.</span></span>

<span data-ttu-id="0ac8a-119">Para obter a licença de usuário virtual, no centro de administração do Microsoft 365, **Billing** acesse  >  **Purchase services**  >  **assinaturas complementares** de serviços de compra de cobrança e role até o fim-você verá *sistema telefônico-licença de usuário virtual* .</span><span class="sxs-lookup"><span data-stu-id="0ac8a-119">To get the Virtual User license, in the Microsoft 365 admin center, go to **Billing** > **Purchase services** > **Add-on subscriptions** and scroll to the end - you will see *Phone System - Virtual User* license.</span></span> <span data-ttu-id="0ac8a-120">Selecione **comprar agora**.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-120">Select **Buy now**.</span></span> <span data-ttu-id="0ac8a-121">Há um custo zero, mas você ainda precisa seguir estas etapas para adquirir a licença.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-121">There is a zero cost, but you still need to follow these steps to acquire the license.</span></span>

### <a name="obtain-service-numbers"></a><span data-ttu-id="0ac8a-122">Obter números de serviço</span><span class="sxs-lookup"><span data-stu-id="0ac8a-122">Obtain service numbers</span></span>

<span data-ttu-id="0ac8a-123">Os números de serviço são opcionais para atendedores automáticos e filas de chamadas, mas você precisará pelo menos um número de serviço para que os chamadores atinjam o atendedor automático e a configuração da fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-123">Service numbers are optional for auto attendants and call queues, however you will need at least one service number in order for callers to reach your auto attendant and call queue configuration.</span></span> <span data-ttu-id="0ac8a-124">Para qualquer atendedor automático ou fila de chamadas que você deseja que seja alcançável diretamente por um número de serviço, você deve ter uma conta de recurso com um número de serviço associado.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-124">For any auto attendant or call queue that you want to be reachable directly by a service number, you must have a resource account with an associated service number.</span></span>

<span data-ttu-id="0ac8a-125">As contas de recursos podem usar números de serviço de chamada tarifada ou gratuita.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-125">Resource accounts can use either toll or toll-free service numbers.</span></span> <span data-ttu-id="0ac8a-126">Você pode solicitar novos números ou portar números existentes de outra operadora.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-126">You can request new numbers or port existing numbers from another carrier.</span></span>

<span data-ttu-id="0ac8a-127">Para obter novos números de serviço, consulte [obtendo números de telefone de serviço](getting-service-phone-numbers.md).</span><span class="sxs-lookup"><span data-stu-id="0ac8a-127">To get new service numbers, see [Getting service phone numbers](getting-service-phone-numbers.md).</span></span>

<span data-ttu-id="0ac8a-128">Para portar um número de outra operadora, confira [transferir números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="0ac8a-128">To port a number from another carrier, see [Transfer phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>

## <a name="create-a-resource-account"></a><span data-ttu-id="0ac8a-129">Criar uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="0ac8a-129">Create a resource account</span></span>

<span data-ttu-id="0ac8a-130">Você pode criar uma conta de recurso no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-130">You can create a resource account in the Teams admin center.</span></span>

![Captura de tela da interface do usuário da conta adicionar recurso](media/resource-account-add.png)

1. <span data-ttu-id="0ac8a-132">No centro de administração do Teams, expanda **configurações de toda a organização** e clique em **contas de recursos**.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-132">In the Teams admin center, expand **Org-wide settings** , and then click **Resource accounts**.</span></span>

2. <span data-ttu-id="0ac8a-133">Clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-133">Click **Add**.</span></span>

3. <span data-ttu-id="0ac8a-134">No painel **adicionar conta do recurso** , preencha o **nome para exibição** , o nome de **usuário** e o tipo de **conta do recurso**.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-134">In the **Add resource account** pane, fill out **Display name** , **Username** , and the **Resource account type**.</span></span> <span data-ttu-id="0ac8a-135">O tipo de conta de recurso pode ser o **atendedor automático** ou a **fila de chamadas** , dependendo de como você pretende usar essa conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-135">The resource account type can be either **Auto attendant** or **Call queue** , depending how you intend to use this resource account.</span></span>

4. <span data-ttu-id="0ac8a-136">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-136">Click **Save**.</span></span>

![Captura de tela de uma lista de contas de recursos](media/resource-accounts-page.png)

## <a name="assign-a-license"></a><span data-ttu-id="0ac8a-138">Atribuir uma licença</span><span class="sxs-lookup"><span data-stu-id="0ac8a-138">Assign a license</span></span>

<span data-ttu-id="0ac8a-139">Para cada conta de recurso, você deve atribuir um *sistema telefônico Microsoft 365-licença de usuário virtual* ou licença do *sistema de telefonia* .</span><span class="sxs-lookup"><span data-stu-id="0ac8a-139">For each resource account, you must assign a *Microsoft 365 Phone System - Virtual User* license or *Phone System* license.</span></span>

![Captura de tela da interface do usuário de atribuir licenças no centro de administração do Microsoft 365](media/resource-account-assign-virtual-user-license.png)

1. <span data-ttu-id="0ac8a-141">No centro de administração do Microsoft 365, clique na conta de recurso à qual você deseja atribuir uma licença.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-141">In the Microsoft 365 admin center, click the resource account to which you want to assign a license.</span></span>

2. <span data-ttu-id="0ac8a-142">Na guia **licenças e aplicativos** , em **licenças** , selecione **sistema telefônico Microsoft 365-usuário virtual**.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-142">On the **Licenses and Apps** tab, under **Licenses** , select **Microsoft 365 Phone System - Virtual User**.</span></span>

3. <span data-ttu-id="0ac8a-143">Clique em **salvar alterações**.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-143">Click **Save changes**.</span></span>

## <a name="assign-a-service-number"></a><span data-ttu-id="0ac8a-144">Atribuir um número de serviço</span><span class="sxs-lookup"><span data-stu-id="0ac8a-144">Assign a service number</span></span>

<span data-ttu-id="0ac8a-145">Se você estiver planejando usar a conta do recurso com um atendedor automático ou uma fila de chamadas que exija um número de serviço, atribua um número à conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-145">If you're planning to use the resource account with an auto attendant or call queue that requires a service number, assign a number to the resource account.</span></span>

![Captura de tela da interface de usuário atribuir número de serviço](media/resource-account-assign-phone-number.png)

1. <span data-ttu-id="0ac8a-147">No centro de administração do Teams, na página **contas do recurso** , selecione a conta do recurso à qual você deseja atribuir um número de serviço e clique em **atribuir/Cancelar atribuição**.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-147">In the Teams admin center, on the **Resource accounts** page, select the resource account to which you want to assign a service number, and then click **Assign/unassign**.</span></span>

2. <span data-ttu-id="0ac8a-148">Na lista suspensa **tipo de número de telefone** , escolha o tipo de número que você deseja usar.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-148">In the **Phone number type** dropdown, choose the type of number that you want to use.</span></span>

3. <span data-ttu-id="0ac8a-149">Na caixa **número de telefone atribuído** , procure o número que deseja usar e clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-149">In the **Assigned phone number** box, search for the number you want to use and click **Add**.</span></span>

4. <span data-ttu-id="0ac8a-150">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-150">Click **Save**.</span></span>


<span data-ttu-id="0ac8a-151">Para atribuir um roteamento direto ou número híbrido a uma conta de recurso, você precisa usar o PowerShell:</span><span class="sxs-lookup"><span data-stu-id="0ac8a-151">To assign a direct routing or hybrid number to a resource account you need to use PowerShell:</span></span>

`Set-CsOnlineApplicationInstance -Identity aa-contoso_main@contoso64.net -OnpremPhoneNumber +19295550150`

## <a name="next-steps"></a><span data-ttu-id="0ac8a-152">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="0ac8a-152">Next steps</span></span>

<span data-ttu-id="0ac8a-153">Depois de concluir a configuração da conta do recurso e atribuir um número de serviço, se necessário, você estará pronto para usar a conta do recurso com um atendedor automático ou uma fila de chamadas.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-153">Once you've completed the resource account setup and assigning a service number if needed, you're ready to use the resource account with an auto attendant or call queue.</span></span>

<span data-ttu-id="0ac8a-154">Consulte as seguintes referências:</span><span class="sxs-lookup"><span data-stu-id="0ac8a-154">See the following references:</span></span>

 - [<span data-ttu-id="0ac8a-155">Atendedor automático na nuvem</span><span class="sxs-lookup"><span data-stu-id="0ac8a-155">Cloud auto attendant</span></span>](create-a-phone-system-auto-attendant.md)

 - [<span data-ttu-id="0ac8a-156">Fila de chamadas em nuvem</span><span class="sxs-lookup"><span data-stu-id="0ac8a-156">Cloud call queue</span></span>](create-a-phone-system-call-queue.md)

<span data-ttu-id="0ac8a-157">Você pode editar o nome para **exibição** da conta do recurso e o tipo de **conta do recurso** usando a opção **Editar** .</span><span class="sxs-lookup"><span data-stu-id="0ac8a-157">You can edit the resource account **Display name** and **Resource account** type using the **Edit** option.</span></span> <span data-ttu-id="0ac8a-158">Clique em **salvar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-158">Click **Save** when you are done.</span></span>

## <a name="change-an-existing-resource-account-to-use-a-virtual-user-license"></a><span data-ttu-id="0ac8a-159">Alterar uma conta de recurso existente para usar uma licença de usuário virtual</span><span class="sxs-lookup"><span data-stu-id="0ac8a-159">Change an existing resource account to use a Virtual User license</span></span>

<span data-ttu-id="0ac8a-160">Se você decidir mudar as licenças de sua conta de recurso existente de uma licença do **sistema telefônico** para uma licença de usuário virtual, será necessário adquirir a licença de usuário virtual gratuita e, em seguida, seguir as etapas no centro de administração do Microsoft 365 para [mover os usuários para uma assinatura diferente](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span><span class="sxs-lookup"><span data-stu-id="0ac8a-160">If you decide to switch the licenses on your existing resource account from a **Phone System** license to a Virtual User license, you'll need to acquire the free Virtual User license, and then follow the steps in the Microsoft 365 admin center to [Move users to a different subscription](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users#move-users-to-a-different-subscription).</span></span>

> [!WARNING]
> <span data-ttu-id="0ac8a-161">Sempre remova uma licença completa do sistema de telefonia e atribua a licença de usuário virtual na mesma atividade de licença.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-161">Always remove a full Phone System License and assign the Virtual User license in the same license activity.</span></span> <span data-ttu-id="0ac8a-162">Se você remover a antiga licença, salvar as alterações da conta, adicionar a nova licença e salvar as configurações da conta novamente, a conta do recurso talvez não funcione mais como esperado.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-162">If you remove the old license, save the account changes, add the new license, and then save the account settings again, the resource account may no longer function as expected.</span></span> <span data-ttu-id="0ac8a-163">Se isso acontecer, recomendamos que você crie uma nova conta de recurso para a licença de usuário virtual e remova a conta de recurso quebrada.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-163">If this happens, we recommend you create a new resource account for the Virtual User license and remove the broken resource account.</span></span>

## <a name="skype-for-business-server-2019"></a><span data-ttu-id="0ac8a-164">Skype for Business Server 2019</span><span class="sxs-lookup"><span data-stu-id="0ac8a-164">Skype For Business Server 2019</span></span>

<span data-ttu-id="0ac8a-165">Para contas de recursos hospedadas no Skype for Business Server 2019 que podem ser usadas com filas de chamadas em nuvem e atendedores automáticos na nuvem, consulte [planejar filas de chamadas na](/SkypeforBusiness/hybrid/plan-call-queue) nuvem ou reportar [atendedores automáticos da nuvem](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span><span class="sxs-lookup"><span data-stu-id="0ac8a-165">For resource accounts homed on Skype For Business Server 2019 that can be used with cloud call queues and cloud auto attendants, see [Plan Cloud call queues](/SkypeforBusiness/hybrid/plan-call-queue) or [Plan Cloud auto attendants](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant).</span></span> <span data-ttu-id="0ac8a-166">As implementações híbridas (números hospedados no roteamento direto) são configuradas usando o cmdlet [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) em um servidor local do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-166">Hybrid implementations (numbers homed on Direct Routing) are configured using the [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint) cmdlet on an on-premises Skype for Business Server 2019 server.</span></span>

<span data-ttu-id="0ac8a-167">As IDs de aplicativo que você precisa usar durante a criação das instâncias do aplicativo são:</span><span class="sxs-lookup"><span data-stu-id="0ac8a-167">The application IDs that you need to use while creating the application instances are:</span></span>

- <span data-ttu-id="0ac8a-168">**Atendedor automático:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="0ac8a-168">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="0ac8a-169">**Fila de chamadas:** 11cd3e2e-fccb-42AD-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="0ac8a-169">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="0ac8a-170">Se quiser que a fila de chamadas ou o atendedor automático seja pesquisável pelos usuários do Skype for Business Server 2019, você deve criar suas contas de recursos no Skype for Business Server 2019, pois as contas de recursos online não são sincronizadas com o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-170">If you want the call queue or auto attendant to be searchable by Skype For Business Server 2019 users, you should create your resource accounts on Skype For Business Server 2019, since online resource accounts are not synced down to Active Directory.</span></span> <span data-ttu-id="0ac8a-171">Quando os registros SRV DNS para sipfederationtls são resolvidos para o Skype for Business Server 2019, as contas de recursos **devem** ser criadas no Skype for business Server 2019 usando o Shell de gerenciamento SfB e sincronizadas com o Azure AD.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-171">When DNS SRV records for sipfederationtls resolve to Skype for Business Server 2019, then resource accounts **must** be created on Skype For Business Server 2019 using SfB Management shell and synchronized to Azure AD.</span></span>

<span data-ttu-id="0ac8a-172">Para implementações híbridas com o Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="0ac8a-172">For implementations that are hybrid with Skype for Business Server:</span></span>

   [<span data-ttu-id="0ac8a-173">Atendedores automáticos do plano da nuvem</span><span class="sxs-lookup"><span data-stu-id="0ac8a-173">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)
  
   [<span data-ttu-id="0ac8a-174">Planejar filas de chamadas da nuvem</span><span class="sxs-lookup"><span data-stu-id="0ac8a-174">Plan Cloud call queues</span></span>](/SkypeforBusiness/hybrid/plan-call-queue)
   
   [<span data-ttu-id="0ac8a-175">Configurar contas de recurso local</span><span class="sxs-lookup"><span data-stu-id="0ac8a-175">Configure on-prem resource accounts</span></span>](/SkypeForBusiness/hybrid/configure-onprem-ra)


## <a name="delete-a-resource-account"></a><span data-ttu-id="0ac8a-176">Excluir uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="0ac8a-176">Delete a resource account</span></span>

<span data-ttu-id="0ac8a-177">Certifique-se de dissociar o número de telefone da conta do recurso antes de excluí-lo para evitar que o número do seu serviço fique preso no modo pendente.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-177">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span>

<span data-ttu-id="0ac8a-178">Depois de fazer isso, você pode excluir a conta do recurso no centro de administração do Microsoft 365, na guia usuários.</span><span class="sxs-lookup"><span data-stu-id="0ac8a-178">After you do that, you can delete the resource account in the Microsoft 365 admin center, under the Users tab.</span></span>

<span data-ttu-id="0ac8a-179">Para desassociar um número de telefone de roteamento direto da conta do recurso, use o seguinte cmdlet:</span><span class="sxs-lookup"><span data-stu-id="0ac8a-179">To disassociate a direct routing telephone number from the resource account, use the following cmdlet:</span></span>

```powershell
Set-CsOnlineApplicationInstance -Identity  <Resource Account oid> -OnpremPhoneNumber ""
```
