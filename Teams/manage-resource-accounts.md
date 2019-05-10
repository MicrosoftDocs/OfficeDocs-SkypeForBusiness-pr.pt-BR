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
ms.openlocfilehash: dea4a154e25c719ddabc572ba26ddb7d25c43d71
ms.sourcegitcommit: c997490cf7239d07e2fd52a4b03bec464b3d192b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/09/2019
ms.locfileid: "33835414"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="86113-103">Gerenciar contas de recursos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86113-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="86113-104">Uma conta de recurso é também conhecido como um objeto de usuário desabilitadas no Windows Azure Active Directory e pode ser usada para representar os recursos em geral.</span><span class="sxs-lookup"><span data-stu-id="86113-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="86113-105">No Exchange pode ser usada para representar a salas de conferência, por exemplo e permitir que eles tiverem um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="86113-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="86113-106">Uma conta de recurso pode ser hospedada no Microsoft 365 ou no local usando Skype para Business server, e essas contas são criadas usando comandos do Powershell.</span><span class="sxs-lookup"><span data-stu-id="86113-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="86113-107">No Microsoft Teams ou Skype para Business Online, cada fila de chamada ou automático attendant é necessária para ter uma conta de recurso associado.</span><span class="sxs-lookup"><span data-stu-id="86113-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="86113-108">Se uma conta de recurso precisa de um número de telefone atribuído dependem o uso pretendido da fila chamada associado ou atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="86113-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="86113-109">Consulte os artigos sobre filas de chamada e vinculados na parte inferior deste artigo antes de atribuir um número de telefone a uma conta de recurso de atendedores automáticos de um.</span><span class="sxs-lookup"><span data-stu-id="86113-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="86113-110">Este artigo se aplica ao Microsoft Teams e Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="86113-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="86113-111">Pré-requisitos para atribuir um número de telefone a uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="86113-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="86113-112">Para começar é importante se lembrar de algumas coisas:</span><span class="sxs-lookup"><span data-stu-id="86113-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="86113-113">Uma fila de chamada e o atendente automático é necessário ter uma conta de recurso associado.</span><span class="sxs-lookup"><span data-stu-id="86113-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="86113-114">Consulte [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) para obter detalhes sobre as contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="86113-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="86113-115">Se você planeja atribua um número de roteamento direto, você precisará adquirir e atribuir as seguintes licenças às suas contas de recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico\).</span><span class="sxs-lookup"><span data-stu-id="86113-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="86113-116">Se você estiver atribuindo um número de serviço da Microsoft em vez disso, você precisará adquirir e atribuir as seguintes licenças à sua conta do recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico e um plano de chamar\).</span><span class="sxs-lookup"><span data-stu-id="86113-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>
- <span data-ttu-id="86113-117">Você só precisa licenciar as contas de recursos com um número de telefone atribuído a eles.</span><span class="sxs-lookup"><span data-stu-id="86113-117">You only need to license the resource accounts with a phone number assigned to them.</span></span> <span data-ttu-id="86113-118">Em uma fila de chamada e atendente automático aninhados, você não precisará licenciar o restante dos atendedores automáticos ou chamada filas se eles não tiverem números de telefone associados a eles</span><span class="sxs-lookup"><span data-stu-id="86113-118">In a nested auto attendant or call queue, you do not need to license the rest of the auto attendants or call queues if they do not have phone numbers associated with them</span></span>

> [!NOTE] 
> <span data-ttu-id="86113-119">Números de serviço de roteamento direto para filas de chamada e atendedor automático é suportado para usuários do Microsoft Teams e operadores somente.</span><span class="sxs-lookup"><span data-stu-id="86113-119">Direct Routing service numbers for auto attendant and call queues is supported for Microsoft Teams users and agents only.</span></span>

> [!NOTE] 
> <span data-ttu-id="86113-120">Microsoft está trabalhando em um modelo de licenciamento apropriado para aplicativos como atendedores automáticos de nuvem e filas de chamada, para agora você precisa usar o modelo de licenciamento por usuário.</span><span class="sxs-lookup"><span data-stu-id="86113-120">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="86113-121">Para redirecionar chamadas para pessoas na sua organização que estiverem Online, eles devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem chamando de planos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="86113-121">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="86113-122">Consulte [as equipes da Microsoft atribuir licenças](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="86113-122">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="86113-123">Para habilitá-los para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="86113-123">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="86113-124">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="86113-124">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="86113-125">Você pode atribuir um número de híbrido de roteamento direto à sua conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="86113-125">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="86113-126">Para obter detalhes, consulte [Planejar roteamento direto](direct-routing-plan.md) .</span><span class="sxs-lookup"><span data-stu-id="86113-126">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="86113-127">Para planos de chamada da Microsoft, você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou duas portas de outro provedor de serviços para uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="86113-127">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="86113-128">Para obter e usar números gratuitos de serviço, você precisará configurar créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="86113-128">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="86113-129">Números de telefone do usuário (assinante) não podem ser atribuídos a uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="86113-129">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="86113-130">Apenas os números de telefone gratuitos ou tarifas do serviço podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="86113-130">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="86113-131">Para atribuir um número de telefone a uma conta de recurso, você precisará obter ou porta sua chamada Tarifada existente ou serviço gratuito números.</span><span class="sxs-lookup"><span data-stu-id="86113-131">To assign a phone number to a resource account, you will need to get or port your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="86113-132">Após você fazer a chamada Tarifada ou números de telefone gratuitos de serviço, eles serão exibidas no **Centro de administração do Microsoft equipes** > **voz** > **números de telefone**e a disposição de **tipo de número** listado listada como **serviço - gratuito**.</span><span class="sxs-lookup"><span data-stu-id="86113-132">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="86113-133">Para obter seus números de serviço, consulte [Getting números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) ou se você deseja transferir um número existente de serviço, consulte [números de telefone de transferência para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="86113-133">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="86113-134">Se você estiver fora dos Estados Unidos, você não pode usar o Centro de administração do Microsoft Teams para obter os números de serviço.</span><span class="sxs-lookup"><span data-stu-id="86113-134">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="86113-135">Vá para [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo de fora dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="86113-135">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-microsoft-teams-admin-center"></a><span data-ttu-id="86113-136">Criar uma conta de recurso no Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86113-136">Create a resource account in Microsoft Teams admin center</span></span>

<span data-ttu-id="86113-137">No Centro de administração do Microsoft Teams, navegue até **configurações de toda a organização** > **contas de recurso**.</span><span class="sxs-lookup"><span data-stu-id="86113-137">In Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**.</span></span> 

![asd](media/r-a-master.png)

![número 1](media/sfbcallout1.png)

<span data-ttu-id="86113-140">Para criar um novo recurso conta, clique em **+ nova conta**.</span><span class="sxs-lookup"><span data-stu-id="86113-140">To create a new resource account click **+ New account**.</span></span> <span data-ttu-id="86113-141">Na janela pop-up, preencha o nome para exibição e o nome de usuário para a conta do recurso (o nome de domínio deve preencher automaticamente), em seguida, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="86113-141">In the pop-up, fill out the display name and user name for the resource account (the domain name should populate automatically) then click **Save**.</span></span>

![conta do recurso](media/res-acct.png)

<span data-ttu-id="86113-143">Em seguida, você precisará aplicar uma licença para a conta do recurso, conforme descrito em [Atribuir licenças aos usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span><span class="sxs-lookup"><span data-stu-id="86113-143">Next, you will  need to apply a license to the resource account, as described in [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide)</span></span>

<span data-ttu-id="86113-144">![número 3](media/sfbcallout3.png) depois que você criou a conta do recurso e atribuído a licença, você pode clicar em **Cancelar atribuir/atribuição** para atribuir um número de serviço chamando planejar para a conta do recurso ou atribuir a conta do recurso a uma fila de chamada e atendente automático já existe.</span><span class="sxs-lookup"><span data-stu-id="86113-144">![number 3](media/sfbcallout3.png) Once you've created the resource account and assigned the license, you can click on **Assign/Unassign** to assign a Calling Plan service number to the resource account, or assign the resource account to an auto attendant or call queue that already exists.</span></span> <span data-ttu-id="86113-145">Atribuindo um número de roteamento direto pode ser feita usando apenas o Cmdlets.</span><span class="sxs-lookup"><span data-stu-id="86113-145">Assigning a direct routing number can be done using Cmdlets only.</span></span> <span data-ttu-id="86113-146">Se sua fila de chamada ou atendedor automático precisa ser criado, você pode vincular a conta do recurso enquanto você criá-lo.</span><span class="sxs-lookup"><span data-stu-id="86113-146">If your call queue or auto attendant still needs to be created, you can link the resource account while you create it.</span></span> <span data-ttu-id="86113-147">Clique em **Salvar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="86113-147">Click **Save** when you are done.</span></span>

![atribuir a conta de recurso](media/r-a-assign.png)

<span data-ttu-id="86113-149">![número 2](media/sfbcallout2.png) você pode editar o nome de exibição da conta de recurso usando a opção de **Editar** .</span><span class="sxs-lookup"><span data-stu-id="86113-149">![number 2](media/sfbcallout2.png) You can edit the resource account display name using the **Edit** option.</span></span>  <span data-ttu-id="86113-150">Clique em **Salvar** quando terminar.</span><span class="sxs-lookup"><span data-stu-id="86113-150">Click **Save** when you are done.</span></span>
<span data-ttu-id="86113-151">![Editar a conta do recurso](media/r-a-edit.png)</span><span class="sxs-lookup"><span data-stu-id="86113-151">![edit resource account](media/r-a-edit.png)</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="86113-152">Criar uma conta de recurso no Powershell</span><span class="sxs-lookup"><span data-stu-id="86113-152">Create a resource account in Powershell</span></span>

<span data-ttu-id="86113-153">Para planos de chamada da Microsoft, você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou duas portas de outro provedor de serviços para uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="86113-153">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or ported from another service provider to a resource account.</span></span> <span data-ttu-id="86113-154">Para obter e usar números gratuitos de serviço, você precisará configurar créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="86113-154">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

<span data-ttu-id="86113-155">Dependendo se a sua conta do recurso está localizada online ou no local, você precisará conectar-se ao prompt do Powershell apropriado com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="86113-155">Depending on whether your resource account is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span> 
- <span data-ttu-id="86113-156">O Powershell seguinte exemplos de cmdlet presumem que a conta do recurso hospedada online usando [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) para criar uma conta de recurso hospedada online.</span><span class="sxs-lookup"><span data-stu-id="86113-156">The following Powershell cmdlet examples presume the resource account is homed online using [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to create a resource account that is homed online.</span></span>

- <span data-ttu-id="86113-157">Para o recurso contas hospedados no local no Skype para Business Server 2019 que pode ser usado com filas de chamada de nuvem e atendedores automáticos de nuvem, consulte [Configurar filas de chamada de nuvem](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) ou [Configurar atendentes automáticos da nuvem](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md).</span><span class="sxs-lookup"><span data-stu-id="86113-157">For resource accounts homed on-premises in Skype For Business Server 2019 that can be used with Cloud Call Queues and Cloud Auto Attendants, see [Configure Cloud Call Queues](/skypeforbusiness/SfbHybrid/hybrid/configure-call-queue.md) or [Configure Cloud Auto Attendants](/skypeforbusiness/SfbHybrid/hybrid/configure-cloud-auto-attendant.md).</span></span> <span data-ttu-id="86113-158">Implementações híbridas (os números hospedados no roteamento direto) usará [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="86113-158">Hybrid implementations (numbers homed on Direct Routing) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps).</span></span>

<span data-ttu-id="86113-159">O aplicativo IDs que você precisa usar durante a criação do aplicativo instâncias são:</span><span class="sxs-lookup"><span data-stu-id="86113-159">The application ID's that you need to use while creating the application instances are:</span></span>
- <span data-ttu-id="86113-160">**Atendedor automático:** ce933385-9390-45d1-9512-c8d228074e07</span><span class="sxs-lookup"><span data-stu-id="86113-160">**Auto Attendant:** ce933385-9390-45d1-9512-c8d228074e07</span></span>
- <span data-ttu-id="86113-161">**Chamada fila:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span><span class="sxs-lookup"><span data-stu-id="86113-161">**Call Queue:** 11cd3e2e-fccb-42ad-ad00-878b93575e07</span></span>

> [!NOTE]
> <span data-ttu-id="86113-162">Se você deseja que a fila chamada ou a ser pesquisada pelos usuários no local atendedor automático, você deve criar seu recurso contas no local, desde que as contas de recursos online não são sincronizadas para baixo até o Active Directory.</span><span class="sxs-lookup"><span data-stu-id="86113-162">If you want the call queue or auto attendant to be searchable by on-premise users, you should create your resource accounts on-premise, since online resource accounts are not synced down to Active Directory.</span></span>

1. <span data-ttu-id="86113-163">Para criar uma conta de recurso online para usar com um uso de auto attendant, o comando a seguir.</span><span class="sxs-lookup"><span data-stu-id="86113-163">To create a resource account online for use with an auto attendant, use the following command.</span></span>  

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
```

2. <span data-ttu-id="86113-164">Não será capaz de usar a conta do recurso até que você aplique uma licença a ela.</span><span class="sxs-lookup"><span data-stu-id="86113-164">You will not be able to use the resource account until you apply a license to it.</span></span> <span data-ttu-id="86113-165">Como aplicar uma licença a uma conta no Centro de administração do O365, consulte [Atribuir licenças aos usuários no Office 365 para empresas](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) , bem como [Atribuir Skype para licenças de negócios](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span><span class="sxs-lookup"><span data-stu-id="86113-165">For how to apply a license to an account in the O365 admin center, see [Assign licenses to users in Office 365 for business](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users?view=o365-worldwide#assign-licenses-to-one-user) as well as [Assign Skype for Business licenses](https://docs.microsoft.com/en-us/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses).</span></span>

3. <span data-ttu-id="86113-166">(Opcional) Depois que a licença correta é aplicada à conta de recurso, você pode definir um número de telefone para a conta do recurso conforme mostrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="86113-166">(Optional) Once the correct license is applied to the resource account you can  set a phone number to the resource account as shown below.</span></span> <span data-ttu-id="86113-167">Nem todas as contas de recursos exigirá um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="86113-167">Not all resource accounts will require a phone number.</span></span> <span data-ttu-id="86113-168">Se você não aplicou uma licença para a conta do recurso, a atribuição de número de telefone falhará.</span><span class="sxs-lookup"><span data-stu-id="86113-168">If you did not apply a license to the resource account, the phone number assignment will fail.</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity testra1@contoso.com
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber +14255550100
```

<span data-ttu-id="86113-169">Consulte [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) para obter mais detalhes sobre esse comando.</span><span class="sxs-lookup"><span data-stu-id="86113-169">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="86113-170">É mais fácil definir o número de telefone online usando o Centro de administração do Microsoft Teams, conforme descrito anteriormente.</span><span class="sxs-lookup"><span data-stu-id="86113-170">It's easiest to set the online phone number using the Microsoft Teams admin center, as described previously.</span></span>

## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="86113-171">Gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="86113-171">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="86113-172">Para gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams, vá para **configurações de toda a organização**  > **contas de recurso**, selecione a conta do recurso que você precisa alterar as configurações para e clique no botão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="86113-172">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="86113-173">na tela **Editar a conta do recurso** , você poderá alterar essas configurações:</span><span class="sxs-lookup"><span data-stu-id="86113-173">in the **Edit resource account** screen, you will be able to change these settings:</span></span>

- <span data-ttu-id="86113-174">**Nome para exibição** para a conta</span><span class="sxs-lookup"><span data-stu-id="86113-174">**Display name** for the account</span></span>
- <span data-ttu-id="86113-175">Chamada de fila ou que usa a conta do atendedor automático</span><span class="sxs-lookup"><span data-stu-id="86113-175">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="86113-176">Número de telefone atribuído à conta</span><span class="sxs-lookup"><span data-stu-id="86113-176">Phone number assigned to the account</span></span>

<span data-ttu-id="86113-177">Quando terminar, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="86113-177">When finished, click on **Save**.</span></span>

## <a name="delete-a-resource-account"></a><span data-ttu-id="86113-178">Excluir uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="86113-178">Delete a resource account</span></span>

<span data-ttu-id="86113-179">Verifique se que você o dissocia o número de telefone da conta do recurso antes de excluí-lo, para evitar o recebimento de seu número de serviço preso no pendentes modo.</span><span class="sxs-lookup"><span data-stu-id="86113-179">Make sure you dissociate the telephone number from the resource account before deleting it, to avoid getting your service number stuck in pending mode.</span></span> <span data-ttu-id="86113-180">Você pode fazer isso usando o commandlet a seguir:</span><span class="sxs-lookup"><span data-stu-id="86113-180">You can do that using the following commandlet:</span></span> 

``` Powershell
Set-csonlinevoiceapplicationinstance -identity <Resource Account oid> -TelephoneNumber $null
```
                
<span data-ttu-id="86113-181">Depois que você fizer isso, você pode excluir a conta do recurso do portal de administração do O365, na guia usuários.</span><span class="sxs-lookup"><span data-stu-id="86113-181">Once you do that, you can delete the resource account from the O365 admin portal, under Users tab.</span></span>


## <a name="related-information"></a><span data-ttu-id="86113-182">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="86113-182">Related Information</span></span>

<span data-ttu-id="86113-183">Para implementações que são híbrida com Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="86113-183">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="86113-184">Atendedores automáticos do plano da nuvem</span><span class="sxs-lookup"><span data-stu-id="86113-184">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="86113-185">Configurar os atendedores automáticos da nuvem</span><span class="sxs-lookup"><span data-stu-id="86113-185">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="86113-186">Para implementações em equipes ou Skype para Business Online:</span><span class="sxs-lookup"><span data-stu-id="86113-186">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="86113-187">Quais são os atendedores automáticos do Cloud?</span><span class="sxs-lookup"><span data-stu-id="86113-187">What are Cloud auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="86113-188">Configurar um atendedor automático do Cloud</span><span class="sxs-lookup"><span data-stu-id="86113-188">Set up a Cloud auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="86113-189">Exemplo de pequenas empresas - Configurar um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="86113-189">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="86113-190">Criar uma fila de chamada do Cloud</span><span class="sxs-lookup"><span data-stu-id="86113-190">Create a Cloud call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="86113-191">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="86113-191">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="86113-192">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="86113-192">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
