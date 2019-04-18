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
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords:
- ms.teamsadmincenter.orgwidesettings.resourceaccounts.overview
description: Saiba mais sobre como gerenciar contas de recurso no Microsoft Teams
ms.openlocfilehash: e8d3da4938a5040972b3c4853434808ca7457c90
ms.sourcegitcommit: 6949c957224949ccc6f5958d3c84294d382ee405
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2019
ms.locfileid: "31914590"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="dca6d-103">Gerenciar contas de recursos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dca6d-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="dca6d-104">Uma conta de recurso é também conhecido como um objeto de usuário desabilitadas no Windows Azure Active Directory e pode ser usada para representar os recursos em geral.</span><span class="sxs-lookup"><span data-stu-id="dca6d-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="dca6d-105">No Exchange pode ser usada para representar a salas de conferência, por exemplo e permitir que eles tiverem um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="dca6d-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="dca6d-106">Uma conta de recurso pode ser hospedada no Microsoft 365 ou no local usando Skype para Business server, e essas contas são criadas usando comandos do Powershell.</span><span class="sxs-lookup"><span data-stu-id="dca6d-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="dca6d-107">No Microsoft Teams ou Skype para Business Online, cada fila de chamada ou automático attendant é necessária para ter uma conta de recurso associado.</span><span class="sxs-lookup"><span data-stu-id="dca6d-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="dca6d-108">Se uma conta de recurso precisa de um número de telefone atribuído dependem o uso pretendido da fila chamada associado ou atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="dca6d-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="dca6d-109">Consulte os artigos sobre filas de chamada e vinculados na parte inferior deste artigo antes de atribuir um número de telefone a uma conta de recurso de atendedores automáticos de um.</span><span class="sxs-lookup"><span data-stu-id="dca6d-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="dca6d-110">Este artigo se aplica ao Microsoft Teams e Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="dca6d-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="dca6d-111">Pré-requisitos para atribuir um número de telefone a uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="dca6d-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="dca6d-112">Para começar é importante se lembrar de algumas coisas:</span><span class="sxs-lookup"><span data-stu-id="dca6d-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="dca6d-113">Uma fila de chamada e o atendente automático é necessário ter uma conta de recurso associado.</span><span class="sxs-lookup"><span data-stu-id="dca6d-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="dca6d-114">Consulte [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) para obter detalhes sobre as contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="dca6d-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="dca6d-115">Se você planeja atribua um número de roteamento direto, você precisará adquirir e atribuir as seguintes licenças às suas contas de recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico\).</span><span class="sxs-lookup"><span data-stu-id="dca6d-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="dca6d-116">Se você estiver atribuindo um número de serviço da Microsoft em vez disso, você precisará adquirir e atribuir as seguintes licenças à sua conta do recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico e um plano de chamar\).</span><span class="sxs-lookup"><span data-stu-id="dca6d-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="dca6d-117">Você só precisa licenciar as contas de recursos com um número de telefone atribuído a eles.</span><span class="sxs-lookup"><span data-stu-id="dca6d-117">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="dca6d-118">Em uma fila de chamada e atendente automático aninhados, você não precisará licenciar o restante dos atendedores automáticos ou chamada filas se eles não tiverem números de telefone associados a eles</span><span class="sxs-lookup"><span data-stu-id="dca6d-118">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them</span></span>

> [!NOTE] 
> <span data-ttu-id="dca6d-119">Diretos números de serviço de roteamento para atendedor automático e filas de chamada é suportado para usuários de Teams da Microsoft e operadores somente no momento.</span><span class="sxs-lookup"><span data-stu-id="dca6d-119">Direct Routing service numbers for auto attendant and call queues is supported for Microsoft Teams users and agents only at the moment.</span></span>

> [!NOTE] 
> <span data-ttu-id="dca6d-120">Microsoft está trabalhando em um modelo de licenciamento apropriado para aplicativos como atendedores automáticos de nuvem e filas de chamada, para agora você precisa usar o modelo de licenciamento por usuário.</span><span class="sxs-lookup"><span data-stu-id="dca6d-120">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="dca6d-121">Para redirecionar chamadas para pessoas na sua organização que estiverem Online, eles devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem chamando de planos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="dca6d-121">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="dca6d-122">Consulte [as equipes da Microsoft atribuir licenças](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="dca6d-122">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="dca6d-123">Para habilitá-los para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="dca6d-123">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="dca6d-124">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="dca6d-124">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="dca6d-125">Você pode atribuir um número de híbrido de roteamento direto à sua conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="dca6d-125">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="dca6d-126">Para obter detalhes, consulte [Planejar roteamento direto](direct-routing-plan.md) .</span><span class="sxs-lookup"><span data-stu-id="dca6d-126">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="dca6d-127">Para planos de chamada da Microsoft, você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou duas portas de outro provedor de serviços para uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="dca6d-127">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="dca6d-128">Para obter e usar números gratuitos de serviço, você precisará configurar créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="dca6d-128">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="dca6d-129">Números de telefone do usuário (assinante) não podem ser atribuídos a uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="dca6d-129">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="dca6d-130">Apenas os números de telefone gratuitos ou tarifas do serviço podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="dca6d-130">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="dca6d-131">Para atribuir um número de telefone a uma conta de recurso, você precisará obter ou porta sua chamada Tarifada existente ou serviço gratuito números.</span><span class="sxs-lookup"><span data-stu-id="dca6d-131">To assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="dca6d-132">Após você fazer a chamada Tarifada ou números de telefone gratuitos de serviço, eles serão exibidas no **Centro de administração do Microsoft equipes** > **voz** > **números de telefone**e a disposição de **tipo de número** listado listada como **serviço - gratuito**.</span><span class="sxs-lookup"><span data-stu-id="dca6d-132">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="dca6d-133">Para obter seus números de serviço, consulte [Getting números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) ou se você deseja transferir um número existente de serviço, consulte [números de telefone de transferência para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="dca6d-133">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="dca6d-134">Se você estiver fora dos Estados Unidos, você não pode usar o Centro de administração do Microsoft Teams para obter os números de serviço.</span><span class="sxs-lookup"><span data-stu-id="dca6d-134">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="dca6d-135">Vá para [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo de fora dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="dca6d-135">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="dca6d-136">Criar uma conta de recurso no Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dca6d-136">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="dca6d-137">Para criar uma conta de recurso no Centro de administração do Microsoft Teams, vá para **configurações de toda a organização** > **contas de recurso**, clique em **+ Add**.</span><span class="sxs-lookup"><span data-stu-id="dca6d-137">To create a resource account  in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, then click **+ Add**.</span></span> <span data-ttu-id="dca6d-138">Na janela pop-up, preencha o nome para exibição e o nome de usuário para a conta do recurso (o nome de domínio deve preencher automaticamente), em seguida, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dca6d-138">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![conta do recurso](media/res-acct.png)

<span data-ttu-id="dca6d-140">Você também precisará aplicar uma licença para a conta do recurso, conforme descrito em [Atribuir licenças aos usuários no Office 365 para empresas](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="dca6d-140">You will also need to apply a license to the resource account, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/en-us/office365/admin/subscriptions-and-billing/assign-licenses-to-users?redirectSourcePath=%252farticle%252f997596b5-4173-4627-b915-36abac6786dc&view=o365-worldwide)</span></span>

<span data-ttu-id="dca6d-141">Depois que você criou a conta do recurso e atribuído a licença, você pode clicar em **Cancelar atribuir/atribuição** para atribuir um número de telefone para a conta do recurso, ou para atribuir a conta do recurso a uma fila de chamada e atendente automático.</span><span class="sxs-lookup"><span data-stu-id="dca6d-141">Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a phone number to the resource account, or to assign the resource account to an auto attendant or call queue.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="dca6d-142">Criar uma conta de recurso no Powershell</span><span class="sxs-lookup"><span data-stu-id="dca6d-142">Create a resource account in Powershell</span></span>

<span data-ttu-id="dca6d-143">Para planos de chamada da Microsoft, você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou duas portas de outro provedor de serviços para uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="dca6d-143">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="dca6d-144">Para obter e usar números gratuitos de serviço, você precisará configurar créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="dca6d-144">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

<span data-ttu-id="dca6d-145">Dependendo se o seu número de telefone está localizado online ou no local, você precisará conectar-se ao prompt do Powershell apropriado com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="dca6d-145">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>


- <span data-ttu-id="dca6d-146">Implementações híbridas (os números hospedados no roteamento direto) usará [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para criar uma conta de recurso hospedada no local.</span><span class="sxs-lookup"><span data-stu-id="dca6d-146">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="dca6d-147">Somente online implementações usará [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) ter uma conta de recurso hospedada online.</span><span class="sxs-lookup"><span data-stu-id="dca6d-147">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="dca6d-148">O exemplo a seguir é um exemplo de ambiente online da criação de conta do recurso com um atendedor automático ApplicationID.</span><span class="sxs-lookup"><span data-stu-id="dca6d-148">The following is an online environment example of creating resource account with an auto attendant ApplicationID.</span></span> <span data-ttu-id="dca6d-149">Para uma fila de espera de chamada, você pode usar o seguinte ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:</span><span class="sxs-lookup"><span data-stu-id="dca6d-149">For a call queue, you can use the following ApplicationID 11cd3e2e-fccb-42ad-ad00-878b93575e07:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="dca6d-150">Consulte [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) para obter mais detalhes sobre esse comando.</span><span class="sxs-lookup"><span data-stu-id="dca6d-150">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="dca6d-151">É mais fácil definir o número de telefone online usando o Centro de administração do Microsoft Teams, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="dca6d-151">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="dca6d-152">Você também pode usar o `Set-CsOnlineVoiceApplicationInstance` comando para uma atribuir um número de telefone para a conta do recurso após sua criação inicial conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="dca6d-152">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="dca6d-153">Se você não aplicar uma licença ao criar a conta do recurso a atribuição de número de telefone falhará.</span><span class="sxs-lookup"><span data-stu-id="dca6d-153">If you do not apply a license while creating the resource account the phone number assignment will fail.</span></span> 

<span data-ttu-id="dca6d-154">Consulte [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) para obter mais detalhes sobre esse comando.</span><span class="sxs-lookup"><span data-stu-id="dca6d-154">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>



## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="dca6d-155">Gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dca6d-155">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="dca6d-156">Para gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams, vá para **configurações de toda a organização**  > **contas de recurso**, selecione a conta do recurso que você precisa alterar as configurações para e clique no botão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="dca6d-156">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="dca6d-157">na tela **Editar a conta do recurso** , você poderá alterar a:</span><span class="sxs-lookup"><span data-stu-id="dca6d-157">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="dca6d-158">**Nome para exibição** para a conta</span><span class="sxs-lookup"><span data-stu-id="dca6d-158">**Display name** for the account</span></span>
- <span data-ttu-id="dca6d-159">Chamada de fila ou que usa a conta do atendedor automático</span><span class="sxs-lookup"><span data-stu-id="dca6d-159">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="dca6d-160">Número de telefone atribuído à conta</span><span class="sxs-lookup"><span data-stu-id="dca6d-160">Phone number assigned to the account</span></span>

<span data-ttu-id="dca6d-161">Quando terminar, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="dca6d-161">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="dca6d-162">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="dca6d-162">Related Information</span></span>

<span data-ttu-id="dca6d-163">Para implementações que são híbrida com Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="dca6d-163">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="dca6d-164">Atendedores automáticos do plano da nuvem</span><span class="sxs-lookup"><span data-stu-id="dca6d-164">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="dca6d-165">Configurar os atendedores automáticos da nuvem</span><span class="sxs-lookup"><span data-stu-id="dca6d-165">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="dca6d-166">Para implementações em equipes ou Skype para Business Online:</span><span class="sxs-lookup"><span data-stu-id="dca6d-166">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="dca6d-167">Cite atendedores automáticos de nuvem.</span><span class="sxs-lookup"><span data-stu-id="dca6d-167">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="dca6d-168">Configurar um atendedor automático de nuvem</span><span class="sxs-lookup"><span data-stu-id="dca6d-168">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="dca6d-169">Exemplo de pequenas empresas - Configurar um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="dca6d-169">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="dca6d-170">Criar uma fila de chamada de nuvem</span><span class="sxs-lookup"><span data-stu-id="dca6d-170">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="dca6d-171">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="dca6d-171">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="dca6d-172">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="dca6d-172">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
