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
ms.openlocfilehash: b24538e73d236da2c7ee9e889b7cd117a3c931b0
ms.sourcegitcommit: 4266c1fbd8557bf2bf65447557ee8d597f90ccd3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2019
ms.locfileid: "31012951"
---
# <a name="manage-resource-accounts-in-microsoft-teams"></a><span data-ttu-id="f47a2-103">Gerenciar contas de recursos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f47a2-103">Manage resource accounts in Microsoft Teams</span></span>

<span data-ttu-id="f47a2-104">Uma conta de recurso é também conhecido como um objeto de usuário desabilitadas no Windows Azure Active Directory e pode ser usada para representar os recursos em geral.</span><span class="sxs-lookup"><span data-stu-id="f47a2-104">A resource account is also known as a disabled user object in Azure Active Directory, and can be used to represent resources in general.</span></span> <span data-ttu-id="f47a2-105">No Exchange pode ser usada para representar a salas de conferência, por exemplo e permitir que eles tiverem um número de telefone.</span><span class="sxs-lookup"><span data-stu-id="f47a2-105">In Exchange it might be used to represent conference rooms, for example, and allow them to have a phone number.</span></span> <span data-ttu-id="f47a2-106">Uma conta de recurso pode ser hospedada no Microsoft 365 ou no local usando Skype para Business server, e essas contas são criadas usando comandos do Powershell.</span><span class="sxs-lookup"><span data-stu-id="f47a2-106">A resource account can be homed in Microsoft 365 or on premises using Skype for Business server, and these accounts are created using Powershell commands.</span></span>

<span data-ttu-id="f47a2-107">No Microsoft Teams ou Skype para Business Online, cada fila de chamada ou automático attendant é necessária para ter uma conta de recurso associado.</span><span class="sxs-lookup"><span data-stu-id="f47a2-107">In Microsoft Teams or Skype for Business Online, each call queue or auto attendant is required to have an associated resource account.</span></span> <span data-ttu-id="f47a2-108">Se uma conta de recurso precisa de um número de telefone atribuído dependem o uso pretendido da fila chamada associado ou atendedor automático.</span><span class="sxs-lookup"><span data-stu-id="f47a2-108">Whether a resource account needs an assigned phone number will depend on the intended use of the associated call queue or auto attendant.</span></span> <span data-ttu-id="f47a2-109">Consulte os artigos sobre filas de chamada e vinculados na parte inferior deste artigo antes de atribuir um número de telefone a uma conta de recurso de atendedores automáticos de um.</span><span class="sxs-lookup"><span data-stu-id="f47a2-109">Refer to the articles on call queues and auto attendants linked at the bottom of this article before assigning a phone number to a resource account.</span></span>

> [!NOTE]
> <span data-ttu-id="f47a2-110">Este artigo se aplica ao Microsoft Teams e Skype para Business Online.</span><span class="sxs-lookup"><span data-stu-id="f47a2-110">This article applies to both Microsoft Teams and Skype for Business Online.</span></span>

## <a name="prerequisites-to-assign-a-phone-number-to-a-resource-account"></a><span data-ttu-id="f47a2-111">Pré-requisitos para atribuir um número de telefone a uma conta de recurso</span><span class="sxs-lookup"><span data-stu-id="f47a2-111">Prerequisites to assign a phone number to a resource account</span></span>

<span data-ttu-id="f47a2-112">Para começar é importante se lembrar de algumas coisas:</span><span class="sxs-lookup"><span data-stu-id="f47a2-112">To get started it's important to remember a few things:</span></span>
  
- <span data-ttu-id="f47a2-113">Uma fila de chamada e o atendente automático é necessário ter uma conta de recurso associado.</span><span class="sxs-lookup"><span data-stu-id="f47a2-113">An auto attendant or call queue is required to have an associated resource account.</span></span> <span data-ttu-id="f47a2-114">Consulte [Gerenciar contas de recursos em equipes](manage-resource-accounts.md) para obter detalhes sobre as contas de recursos.</span><span class="sxs-lookup"><span data-stu-id="f47a2-114">See [Manage resource accounts in Teams](manage-resource-accounts.md) for details on resource accounts.</span></span>
- <span data-ttu-id="f47a2-115">Se você planeja atribua um número de roteamento direto, você precisará adquirir e atribuir as seguintes licenças às suas contas de recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico\).</span><span class="sxs-lookup"><span data-stu-id="f47a2-115">If you plan to assign a Direct Routing number, you need to acquire and assign the following licenses to your resource accounts \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on\).</span></span>
- <span data-ttu-id="f47a2-116">Se você estiver atribuindo um número de serviço da Microsoft em vez disso, você precisará adquirir e atribuir as seguintes licenças à sua conta do recurso \(Office 365 Enterprise E1, E3 ou E5, com o complemento de sistema telefônico e um plano de chamar\).</span><span class="sxs-lookup"><span data-stu-id="f47a2-116">If you are assigning a Microsoft service number instead, you need to acquire and assign the following licenses to your resource account \(Office 365 Enterprise E1, E3 or E5, with the Phone System add-on and a Calling Plan\).</span></span>

> [!NOTE] 
> <span data-ttu-id="f47a2-117">Microsoft está trabalhando em um modelo de licenciamento apropriado para aplicativos como atendedores automáticos de nuvem e filas de chamada, para agora você precisa usar o modelo de licenciamento por usuário.</span><span class="sxs-lookup"><span data-stu-id="f47a2-117">Microsoft is working on an appropriate licensing model for applications such as Cloud auto attendants and call queues, for now you need to use the user-licensing model.</span></span>
    
> [!NOTE]
> <span data-ttu-id="f47a2-118">Para redirecionar chamadas para pessoas na sua organização que estiverem Online, eles devem ter uma licença de **Sistema telefônico** e ser habilitados para o Enterprise Voice ou tem chamando de planos do Office 365.</span><span class="sxs-lookup"><span data-stu-id="f47a2-118">To redirect calls to people in your organization who are Online, they must have a **Phone System** license and be enabled for Enterprise Voice or have Office 365 Calling Plans.</span></span> <span data-ttu-id="f47a2-119">Consulte [as equipes da Microsoft atribuir licenças](assign-teams-licenses.md).</span><span class="sxs-lookup"><span data-stu-id="f47a2-119">See [Assign Microsoft Teams licenses](assign-teams-licenses.md).</span></span> <span data-ttu-id="f47a2-120">Para habilitá-los para o Enterprise Voice, você pode usar o Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="f47a2-120">To enable them for Enterprise Voice, you can use Windows PowerShell.</span></span> <span data-ttu-id="f47a2-121">Por exemplo, execute:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span><span class="sxs-lookup"><span data-stu-id="f47a2-121">For example run:  `Set-CsUser -identity "Amos Marble" -EnterpriseVoiceEnabled $true`</span></span>
  
- <span data-ttu-id="f47a2-122">Você pode atribuir um número de híbrido de roteamento direto à sua conta do recurso.</span><span class="sxs-lookup"><span data-stu-id="f47a2-122">You can assign a Direct Routing Hybrid number to your resource account.</span></span>  <span data-ttu-id="f47a2-123">Para obter detalhes, consulte [Planejar roteamento direto](direct-routing-plan.md) .</span><span class="sxs-lookup"><span data-stu-id="f47a2-123">See [Plan Direct Routing](direct-routing-plan.md) for details.</span></span>
- <span data-ttu-id="f47a2-124">Para planos de chamada da Microsoft, você só pode atribuir Chamada Tarifada e números de telefone de chamada gratuita do serviço que você obteve no **Centro de administração de equipes da Microsoft** ou transferidos do outro provedor de serviços para uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="f47a2-124">For Microsoft calling plans, you can only assign toll and toll-free service phone numbers that you got in the **Microsoft Teams admin center** or transferred from another service provider to a resource account.</span></span> <span data-ttu-id="f47a2-125">Para obter e usar números gratuitos de serviço, você precisará configurar créditos de comunicações.</span><span class="sxs-lookup"><span data-stu-id="f47a2-125">To get and use toll-free service numbers, you need to set up Communications Credits.</span></span>

> [!NOTE]
> <span data-ttu-id="f47a2-126">Números de telefone do usuário (assinante) não podem ser atribuídos a uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="f47a2-126">User (subscriber) phone numbers can't be assigned to a resource account.</span></span> <span data-ttu-id="f47a2-127">Apenas os números de telefone gratuitos ou tarifas do serviço podem ser usados.</span><span class="sxs-lookup"><span data-stu-id="f47a2-127">Only service toll or toll-free phone numbers can be used.</span></span>

<span data-ttu-id="f47a2-128">Para atribuir um número de telefone a uma conta de recurso, você precisará obter ou transferir sua chamada Tarifada existente ou serviço gratuito números.</span><span class="sxs-lookup"><span data-stu-id="f47a2-128">To assign a phone number to a resource account, you will need to get or transfer your existing toll or toll-free service numbers.</span></span> <span data-ttu-id="f47a2-129">Após você fazer a chamada Tarifada ou números de telefone gratuitos de serviço, eles serão exibidas no **Centro de administração do Microsoft equipes** > **voz** > **números de telefone**e a disposição de **tipo de número** listado listada como **serviço - gratuito**.</span><span class="sxs-lookup"><span data-stu-id="f47a2-129">After you get the toll or toll-free service phone numbers, they will show up in **Microsoft Teams admin center** > **Voice** > **Phone numbers**, and the **Number type** listed will be listed as **Service - Toll-Free**.</span></span> <span data-ttu-id="f47a2-130">Para obter seus números de serviço, consulte [Getting números de telefone de serviço](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) ou se você deseja transferir um número existente de serviço, consulte [números de telefone de transferência para o Office 365](transfer-phone-numbers-to-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="f47a2-130">To get your service numbers, see [Getting service phone numbers](https://docs.microsoft.com/SkypeForBusiness/what-is-phone-system-in-office-365/getting-service-phone-numbers?toc=/MicrosoftTeams/toc.json&bc=/microsoftteams/breadcrumb/toc.json) or if you want to transfer an existing service number, see [Transfer phone numbers to Office 365](transfer-phone-numbers-to-office-365.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="f47a2-131">Se você estiver fora dos Estados Unidos, você não pode usar o Centro de administração do Microsoft Teams para obter os números de serviço.</span><span class="sxs-lookup"><span data-stu-id="f47a2-131">If you are outside the United States, you can't use the Microsoft Teams admin center to get service numbers.</span></span> <span data-ttu-id="f47a2-132">Vá para [gerenciar números de telefone para sua organização](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) em vez disso, para ver como fazê-lo de fora dos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="f47a2-132">Go to [Manage phone numbers for your organization](manage-phone-numbers-for-your-organization/manage-phone-numbers-for-your-organization.md) instead to see how to do it from the outside of the United States.</span></span>

## <a name="create-a-resource-account-in-admin-center"></a><span data-ttu-id="f47a2-133">Criar uma conta de recurso no Centro de administração</span><span class="sxs-lookup"><span data-stu-id="f47a2-133">Create a resource account in admin center</span></span>

<span data-ttu-id="f47a2-134">Para criar uma conta de recurso no Centro de administração do Microsoft Teams, vá para **configurações de toda a organização** > **contas de recurso**, clique em **+ Adicionar**e preencher o nome para exibição, nome de usuário, e em seguida, selecione o nome de domínio e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f47a2-134">To create a resource account  in Microsoft Teams admin center, navigate to **Org-wide settings** > **Resource accounts**, click **+ Add**, and fill out the display name, user name, then select the domain name and click **Save**.</span></span>

<span data-ttu-id="f47a2-135">Para aplicar uma licença para a conta do recurso, navegue até a guia de usuários do Centro de administração do O365.</span><span class="sxs-lookup"><span data-stu-id="f47a2-135">To apply a license to the resource account, navigate to the O365 Admin Center users tab.</span></span>

## <a name="create-a-resource-account-in-powershell"></a><span data-ttu-id="f47a2-136">Criar uma conta de recurso no Powershell</span><span class="sxs-lookup"><span data-stu-id="f47a2-136">Create a resource account in Powershell</span></span>

 <span data-ttu-id="f47a2-137">Crie uma conta de recurso executando o cmdlet do Powershell apropriado, conforme necessário (para uma ou mais contas de recursos) e dê um nome a cada um deles e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="f47a2-137">You would create a resource account by running the appropriate Powershell cmdlet as needed (for one or more resource accounts), and give each one a name and so on.</span></span> <span data-ttu-id="f47a2-138">No momento, não há nenhuma opção para a criação de uma conta de recurso no Centro de administração do Microsoft Teams, mas você pode editar os números de telefone e alterar as chamada fila ou automático attendant as atribuições para uma conta de recurso.</span><span class="sxs-lookup"><span data-stu-id="f47a2-138">There is currently no option for creating a resource account in the Microsoft Teams admin center, but you can edit phone numbers and change the call queue or auto attendant assignments for a resource account.</span></span>

<span data-ttu-id="f47a2-139">Dependendo se o seu número de telefone está localizado online ou no local, você precisará conectar-se ao prompt do Powershell apropriado com privilégios de administrador.</span><span class="sxs-lookup"><span data-stu-id="f47a2-139">Depending on whether your phone number is located online or on premises, you would need to connect to the appropriate Powershell prompt with Admin privileges.</span></span>

- <span data-ttu-id="f47a2-140">Implementações híbridas (os números de números hospedados no roteamento direto, OPCH e CCE) usará [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) para criar uma conta de recurso hospedada no local.</span><span class="sxs-lookup"><span data-stu-id="f47a2-140">Hybrid implementations (numbers numbers homed on Direct Routing, OPCH and CCE) will use [New-CsHybridApplicationEndpoint](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps) to create a resource account that is homed on premises.</span></span>  
- <span data-ttu-id="f47a2-141">Somente online implementações usará [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) ter uma conta de recurso hospedada online.</span><span class="sxs-lookup"><span data-stu-id="f47a2-141">Online only implementations will use [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-CsOnlineApplicationInstance?view=skype-ps) to have a resource account that is homed online.</span></span>

<span data-ttu-id="f47a2-142">Este é um exemplo de ambiente on-line de criação de uma conta de recurso:</span><span class="sxs-lookup"><span data-stu-id="f47a2-142">The following is an online environment example of creating a resource account:</span></span>

``` Powershell
New-CsOnlineApplicationInstance -UserPrincipalName testra1@contoso.com -ApplicationId “ce933385-9390-45d1-9512-c8d228074e07” -DisplayName "Resource account 1"
$resacct=Get-MsolUser -UserPrincipalName testra1@contoso.com
```

<span data-ttu-id="f47a2-143">Consulte [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) para obter mais detalhes sobre esse comando.</span><span class="sxs-lookup"><span data-stu-id="f47a2-143">See [New-CsOnlineApplicationInstance](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps) for more details on this command.</span></span>

> [!NOTE]
> <span data-ttu-id="f47a2-144">É mais fácil definir o número de telefone online usando o Centro de administração do Microsoft Teams, conforme descrito na próxima seção.</span><span class="sxs-lookup"><span data-stu-id="f47a2-144">It's easiest to set the online phone number using the Microsoft Teams admin center, as described in the next section.</span></span> <span data-ttu-id="f47a2-145">Você também pode usar o `Set-CsOnlineVoiceApplicationInstance` comando para uma atribuir um número de telefone para a conta do recurso após sua criação inicial conforme mostrado:</span><span class="sxs-lookup"><span data-stu-id="f47a2-145">You can also use the `Set-CsOnlineVoiceApplicationInstance` command to a assign a phone number to the resource account after its initial creation as shown:</span></span>

``` Powershell
Set-CsOnlineVoiceApplicationInstance -Identity $resacct.ObjectId
 -TelephoneNumber +14255550100
Get-CsOnlineTelephoneNumber -TelephoneNumber 19294450177
```

<span data-ttu-id="f47a2-146">Se você não aplicar uma licença ao criar a conta do recurso a atribuição de número de telefone falhará.</span><span class="sxs-lookup"><span data-stu-id="f47a2-146">If you do not apply a license while creating the resource account the phone number assignment will fail.</span></span> 

<span data-ttu-id="f47a2-147">Consulte [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) para obter mais detalhes sobre esse comando.</span><span class="sxs-lookup"><span data-stu-id="f47a2-147">See [Set-CsOnlineVoiceApplicationInstance](https://docs.microsoft.com/powershell/module/skype/set-csonlinevoiceapplicationinstance?view=skype-ps) for more details on this command.</span></span>



## <a name="manage-resource-account-settings-in-microsoft-teams-admin-center"></a><span data-ttu-id="f47a2-148">Gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f47a2-148">Manage Resource account settings in Microsoft Teams admin center</span></span>

<span data-ttu-id="f47a2-149">Para gerenciar configurações de conta do recurso no Centro de administração do Microsoft Teams, vá para **configurações de toda a organização**  > **contas de recurso**, selecione a conta do recurso que você precisa alterar as configurações para e clique no botão **Editar** .</span><span class="sxs-lookup"><span data-stu-id="f47a2-149">To manage Resource account settings in Microsoft Teams admin center, navigate to **Org-wide settings**  > **Resource accounts**, select the resource account you need to change settings for, and then click on the **Edit** button.</span></span> <span data-ttu-id="f47a2-150">na tela **Editar a conta do recurso** , você poderá alterar a:</span><span class="sxs-lookup"><span data-stu-id="f47a2-150">in the **Edit resource account** screen, you will be able to change the:</span></span>

- <span data-ttu-id="f47a2-151">**Nome para exibição** para a conta</span><span class="sxs-lookup"><span data-stu-id="f47a2-151">**Display name** for the account</span></span>
- <span data-ttu-id="f47a2-152">Chamada de fila ou que usa a conta do atendedor automático</span><span class="sxs-lookup"><span data-stu-id="f47a2-152">Call queue or auto attendant that uses the account</span></span>
- <span data-ttu-id="f47a2-153">Número de telefone atribuído à conta</span><span class="sxs-lookup"><span data-stu-id="f47a2-153">Phone number assigned to the account</span></span>

<span data-ttu-id="f47a2-154">Quando terminar, clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="f47a2-154">When finished, click on **Save**.</span></span>

## <a name="related-information"></a><span data-ttu-id="f47a2-155">Informações relacionadas</span><span class="sxs-lookup"><span data-stu-id="f47a2-155">Related Information</span></span>

<span data-ttu-id="f47a2-156">Para implementações que são híbrida com Skype para Business Server:</span><span class="sxs-lookup"><span data-stu-id="f47a2-156">For implementations that are hybrid with Skype for Business Server:</span></span>

[<span data-ttu-id="f47a2-157">Atendedores automáticos do plano da nuvem</span><span class="sxs-lookup"><span data-stu-id="f47a2-157">Plan Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/plan-cloud-auto-attendant)

[<span data-ttu-id="f47a2-158">Configurar os atendedores automáticos da nuvem</span><span class="sxs-lookup"><span data-stu-id="f47a2-158">Configure Cloud auto attendants</span></span>](/SkypeForBusiness/hybrid/configure-cloud-auto-attendant)

<span data-ttu-id="f47a2-159">Para implementações em equipes ou Skype para Business Online:</span><span class="sxs-lookup"><span data-stu-id="f47a2-159">For implementations in Teams or Skype for Business Online:</span></span>

[<span data-ttu-id="f47a2-160">O que são atendedores automáticos do Sistema de Telefonia?</span><span class="sxs-lookup"><span data-stu-id="f47a2-160">What are Phone System auto attendants?</span></span>](what-are-phone-system-auto-attendants.md)

[<span data-ttu-id="f47a2-161">Configurar os atendedores automáticos do Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="f47a2-161">Set up a Phone System auto attendant</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/set-up-a-phone-system-auto-attendant)

[<span data-ttu-id="f47a2-162">Exemplo de pequena empresa - Configurar um atendedor automático</span><span class="sxs-lookup"><span data-stu-id="f47a2-162">Small business example - Set up an auto attendant</span></span>](https://docs.microsoft.com/en-us/SkypeForBusiness/what-is-phone-system-in-office-365/tutorial-org-aa)

[<span data-ttu-id="f47a2-163">Criar uma fila de chamada no Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="f47a2-163">Create a Phone System call queue</span></span>](/SkypeForBusiness/what-is-phone-system-in-office-365/create-a-phone-system-call-queue)

[<span data-ttu-id="f47a2-164">New-CsHybridApplicationEndpoint</span><span class="sxs-lookup"><span data-stu-id="f47a2-164">New-CsHybridApplicationEndpoint</span></span>](https://docs.microsoft.com/powershell/module/skype/new-cshybridapplicationendpoint?view=skype-ps)

[<span data-ttu-id="f47a2-165">New-CsOnlineApplicationInstance</span><span class="sxs-lookup"><span data-stu-id="f47a2-165">New-CsOnlineApplicationInstance</span></span>](https://docs.microsoft.com/powershell/module/skype/new-csonlineapplicationinstance?view=skype-ps)
