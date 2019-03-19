---
title: Gerenciar políticas de configuração de aplicativo no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
ms.audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre as políticas de configuração de aplicativo no Microsoft Teams e como usá-los para aplicativos de pin para personalizar as equipes para usuários em sua organização.
f1keywords:
- ms.teamsadmincenter.apppolicies.setup
ms.openlocfilehash: 29fcd5541e4817a2c5880316bba33d7d55047444
ms.sourcegitcommit: 8e62025d630c511ffb0361b9643d46c762188102
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/19/2019
ms.locfileid: "30664744"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="cbc29-103">Gerenciar políticas de configuração de aplicativo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="cbc29-103">Manage app setup policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="cbc29-104">Como um administrador, você pode usar políticas de configuração de aplicativo para personalizar o Microsoft Teams para destacar os aplicativos que são mais importantes para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cbc29-104">As an admin, you can use app setup policies to customize Microsoft Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="cbc29-105">Você escolher os aplicativos para fixar e definir a ordem em que aparecem.</span><span class="sxs-lookup"><span data-stu-id="cbc29-105">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="cbc29-106">Políticas de configuração de aplicativo permitem que você demonstrem aplicativos que precisam de usuários em sua organização, incluindo aquelas criadas por terceiros ou por desenvolvedores em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cbc29-106">App setup policies let you showcase apps that users in your organization need, including ones built by third parties or by developers in your organization.</span></span> <span data-ttu-id="cbc29-107">Você também pode usar políticas de configuração de aplicativo para gerenciar recursos internos como aparecem.</span><span class="sxs-lookup"><span data-stu-id="cbc29-107">You can also use app setup policies to manage how built-in features appear.</span></span>

<span data-ttu-id="cbc29-108">Aplicativos são fixados a barra de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cbc29-108">Apps are pinned to the app bar.</span></span> <span data-ttu-id="cbc29-109">Esta é a barra na lateral direita do cliente de desktop equipes e na parte inferior dos clientes móveis equipes (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="cbc29-109">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span> 

|<span data-ttu-id="cbc29-110">Cliente de desktop de equipes</span><span class="sxs-lookup"><span data-stu-id="cbc29-110">Teams desktop client</span></span>  |<span data-ttu-id="cbc29-111">Cliente móvel de equipes</span><span class="sxs-lookup"><span data-stu-id="cbc29-111">Teams mobile client</span></span> |
|---------|---------|
|![App-Setup-Policies-Desktop-App-Bar.PNG](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![App-Setup-Policies-Mobile-App-Bar.PNG](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="cbc29-114">Você gerenciar políticas de configuração de aplicativo no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="cbc29-114">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="cbc29-115">Você pode usar a política global de (padrão de toda a organização) ou como criar políticas personalizadas e atribuí-las aos usuários.</span><span class="sxs-lookup"><span data-stu-id="cbc29-115">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="cbc29-116">Usuários em sua organização receberá automaticamente a política global, a menos que você criar e atribuir uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="cbc29-116">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="cbc29-117">Você pode editar as configurações na política global para incluir os aplicativos que você deseja.</span><span class="sxs-lookup"><span data-stu-id="cbc29-117">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="cbc29-118">Se você desejar personalizar equipes para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="cbc29-118">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![instalação-App-policies.png](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="cbc29-120">Se um usuário é atribuído a uma política personalizada, essa política se aplica ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cbc29-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="cbc29-121">Se um usuário não for atribuído a uma política personalizada, a política global se aplica ao usuário.</span><span class="sxs-lookup"><span data-stu-id="cbc29-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="cbc29-122">Criar uma política de instalação do aplicativo personalizado</span><span class="sxs-lookup"><span data-stu-id="cbc29-122">Create a custom app setup policy</span></span>

<span data-ttu-id="cbc29-123">Você pode usar o Centro de administração do Microsoft Teams para criar uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="cbc29-123">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="cbc29-124">No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes apps** > **políticas de instalação**.</span><span class="sxs-lookup"><span data-stu-id="cbc29-124">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="cbc29-125">Selecione **nova política**.</span><span class="sxs-lookup"><span data-stu-id="cbc29-125">Select **New policy**.</span></span>
3. <span data-ttu-id="cbc29-126">Insira um nome descritivo para a política e, em seguida, clique em **Adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="cbc29-126">Enter a descriptive name for the policy, and then click **Add apps**.</span></span>
4. <span data-ttu-id="cbc29-127">No painel **Adicionar fixados apps** , pesquise os aplicativos que você deseja adicionar e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cbc29-127">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="cbc29-128">Você também pode filtrar apps pela política de permissão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cbc29-128">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="cbc29-129">Quando você tiver escolhido sua lista de aplicativos, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="cbc29-129">When you've chosen your list of apps, click **Add**.</span></span>

     ![App-instalação-políticas-adicionar-apps.png](media/app-setup-policies-add-apps.png)

5. <span data-ttu-id="cbc29-131">Organize os aplicativos na ordem que você deseja que eles aparecem em equipes e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cbc29-131">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

    ![App-Setup-Policies-New-Policy-Setup.PNG](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="cbc29-133">Editar uma política de instalação de aplicativo</span><span class="sxs-lookup"><span data-stu-id="cbc29-133">Edit an app setup policy</span></span>

<span data-ttu-id="cbc29-134">Você pode usar o Centro de administração do Microsoft Teams para editar uma política, incluindo a política global de (padrão de toda a organização) e políticas personalizadas que você criar.</span><span class="sxs-lookup"><span data-stu-id="cbc29-134">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="cbc29-135">No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes apps** > **políticas de instalação**.</span><span class="sxs-lookup"><span data-stu-id="cbc29-135">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="cbc29-136">Selecione a política que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="cbc29-136">Select the policy you want to edit.</span></span> 
3. <span data-ttu-id="cbc29-137">A partir daqui, faça as alterações que você deseja.</span><span class="sxs-lookup"><span data-stu-id="cbc29-137">From here, make the changes that you want.</span></span> <span data-ttu-id="cbc29-138">Você pode adicionar, remover e alterar a ordem dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cbc29-138">You can add, remove, and change the order of apps.</span></span>
4. <span data-ttu-id="cbc29-139">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cbc29-139">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="cbc29-140">Atribuir uma política de instalação do aplicativo personalizado aos usuários</span><span class="sxs-lookup"><span data-stu-id="cbc29-140">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="cbc29-141">Você pode usar o Centro de administração do Microsoft Teams atribuir uma política personalizada para usuários individuais ou o Skype para o módulo de PowerShell de negócios para atribuir uma política personalizada para grupos de usuários, como um grupo de segurança ou grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="cbc29-141">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module  to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="cbc29-142">É recomendável usar o PowerShell somente para atribuir políticas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="cbc29-142">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="cbc29-143">Use o Centro de administração do Microsoft Teams para criar, editar e gerenciar políticas.</span><span class="sxs-lookup"><span data-stu-id="cbc29-143">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a><span data-ttu-id="cbc29-144">Atribuir uma política de instalação do aplicativo personalizado para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="cbc29-144">Assign a custom app setup policy to individual users</span></span>

1. <span data-ttu-id="cbc29-145">No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="cbc29-145">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="cbc29-146">Ao lado de **políticas atribuído**, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="cbc29-146">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="cbc29-147">Em **política de instalação do aplicativo de equipes**, selecione a política de instalação do aplicativo que deseja atribuir e escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="cbc29-147">Under **Teams App Setup policy**, select the app setup policy you want to assign, and then choose **Save**.</span></span>

    ![App-instalação-políticas-atribuir-policy.png](media/app-setup-policies-assign-policy.png)

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="cbc29-149">Atribuir uma política de instalação do aplicativo personalizado aos usuários em um grupo</span><span class="sxs-lookup"><span data-stu-id="cbc29-149">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="cbc29-150">Convém atribuir uma política de instalação do aplicativo personalizado a vários usuários que você identificou.</span><span class="sxs-lookup"><span data-stu-id="cbc29-150">You may want to assign a custom app setup policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="cbc29-151">Por exemplo, convém atribuir uma política a todos os usuários em um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="cbc29-151">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="cbc29-152">Você pode fazer isso Estabelecendo conexão com o Azure Active Directory PowerShell para o módulo de gráfico e do Skype para o módulo de PowerShell de negócios.</span><span class="sxs-lookup"><span data-stu-id="cbc29-152">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="cbc29-153">Para obter mais informações sobre como usar o PowerShell para gerenciar equipes, consulte [Visão geral do PowerShell equipes](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="cbc29-153">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="cbc29-154">Neste exemplo, nós atribuímos uma política de instalação do aplicativo personalizado chamada HR App instalação política a todos os usuários no grupo Contoso Pharmaceuticals RH Project.</span><span class="sxs-lookup"><span data-stu-id="cbc29-154">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="cbc29-155">Certificar-se de que você primeiro conecte-se para o Windows Azure Active Directory PowerShell para o módulo de gráfico e Skype para o módulo de PowerShell de negócios seguindo as etapas em [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="cbc29-155">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="cbc29-156">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="cbc29-156">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="cbc29-157">Obtenha os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="cbc29-157">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="cbc29-158">Atribua a todos os usuários no grupo a uma política de instalação de aplicativo específico.</span><span class="sxs-lookup"><span data-stu-id="cbc29-158">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="cbc29-159">Neste exemplo, é política de instalação de aplicativo de RH.</span><span class="sxs-lookup"><span data-stu-id="cbc29-159">In this example, it's HR App Setup Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="cbc29-160">Dependendo do número de membros no grupo, este comando pode levar alguns minutos para executar.</span><span class="sxs-lookup"><span data-stu-id="cbc29-160">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="cbc29-161">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="cbc29-161">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="cbc29-162">Como trabalhar com políticas de configuração de aplicativo</span><span class="sxs-lookup"><span data-stu-id="cbc29-162">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="cbc29-163">Quais políticas de configuração de aplicativo interno são incluídas no Centro de administração do Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="cbc29-163">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="cbc29-164">**Global (toda a organização padrão)**: esta política padrão se aplica a todos os usuários em sua organização, a menos que você atribua outra política.</span><span class="sxs-lookup"><span data-stu-id="cbc29-164">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="cbc29-165">Edite a política global para aplicativos de pin que são mais importantes para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="cbc29-165">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="cbc29-166">**FirstLineWorker**: esta diretiva é para trabalhadores de firstline.</span><span class="sxs-lookup"><span data-stu-id="cbc29-166">**FirstLineWorker**: This policy is for firstline workers.</span></span> <span data-ttu-id="cbc29-167">Você pode atribuí-lo aos trabalhadores firstline em sua organização.</span><span class="sxs-lookup"><span data-stu-id="cbc29-167">You can assign it to firstline workers in your organization.</span></span> <span data-ttu-id="cbc29-168">É importante saber que, como políticas personalizadas que você criar, você precisa atribuir a política aos usuários para que as configurações estejam ativos.</span><span class="sxs-lookup"><span data-stu-id="cbc29-168">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="cbc29-169">Para obter mais informações, vá para a seção [atribuir uma política de instalação do aplicativo personalizado para os usuários](#assign-a-custom-app-setup-policy-to-users) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="cbc29-169">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="cbc29-170">Por que não é possível encontrar um aplicativo no painel Adicionar aplicativos fixados?</span><span class="sxs-lookup"><span data-stu-id="cbc29-170">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="cbc29-171">Nem todos os aplicativos podem ser fixados equipes por meio de uma política de instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cbc29-171">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="cbc29-172">Alguns aplicativos podem não suportar essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="cbc29-172">Some apps may not support this functionality.</span></span> <span data-ttu-id="cbc29-173">Para localizar aplicativos que podem ser fixados, procure o aplicativo no painel **Adicionar fixados apps** .</span><span class="sxs-lookup"><span data-stu-id="cbc29-173">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="cbc29-174">Guias que têm um escopo pessoal (guias estáticos) e bots podem ser fixados o cliente de desktop equipes e esses aplicativos estão disponíveis no painel **Adicionar fixados apps** .</span><span class="sxs-lookup"><span data-stu-id="cbc29-174">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="cbc29-175">Tenha em mente que app store equipes lista todos os aplicativos de equipes, enquanto o painel de **Adicionar fixado apps** inclui apenas os aplicativos que podem ser fixados equipes através de uma diretiva.</span><span class="sxs-lookup"><span data-stu-id="cbc29-175">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="cbc29-176">Sou um equipes de Admin de educação. O que é necessário saber sobre políticas de configuração de aplicativo em equipes educacional?</span><span class="sxs-lookup"><span data-stu-id="cbc29-176">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="cbc29-177">O aplicativo de chamada não está disponível em equipes educacional.</span><span class="sxs-lookup"><span data-stu-id="cbc29-177">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="cbc29-178">Quando você cria uma nova política de instalação do aplicativo personalizado, o aplicativo de chamada é exibido na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="cbc29-178">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="cbc29-179">No entanto, o aplicativo não está vinculado aos clientes de equipes e equipes para usuários de educação não verá o aplicativo de chamadas em equipes.</span><span class="sxs-lookup"><span data-stu-id="cbc29-179">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span> 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a><span data-ttu-id="cbc29-180">Quantos aplicativos podem ser adicionados a uma política?</span><span class="sxs-lookup"><span data-stu-id="cbc29-180">How many apps can be added to a policy?</span></span>

<span data-ttu-id="cbc29-181">Um mínimo de dois aplicativos deve ser vinculado aos clientes móveis equipes (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="cbc29-181">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="cbc29-182">Se uma diretiva tiver menos de dois aplicativos, os clientes móveis não irão refletir as configurações de política e em vez disso continuarão usando a configuração existente.</span><span class="sxs-lookup"><span data-stu-id="cbc29-182">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="cbc29-183">Quanto tempo leva para que as alterações de diretiva entrem em vigor?</span><span class="sxs-lookup"><span data-stu-id="cbc29-183">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="cbc29-184">Após editar a política global ou atribuir uma política, pode demorar até 24 horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="cbc29-184">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="cbc29-185">Experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="cbc29-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="cbc29-186">Como os usuários podem ver todos os seus aplicativos fixados em equipes?</span><span class="sxs-lookup"><span data-stu-id="cbc29-186">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="cbc29-187">Para exibir todos os aplicativos que são vinculados para um usuário, os usuários podem ter que fazer o seguinte, dependendo do número de aplicativos instalados e o tamanho da janela de cliente suas equipes.</span><span class="sxs-lookup"><span data-stu-id="cbc29-187">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="cbc29-188">Cliente de desktop de equipes</span><span class="sxs-lookup"><span data-stu-id="cbc29-188">Teams desktop client</span></span> |<span data-ttu-id="cbc29-189">Cliente móvel de equipes</span><span class="sxs-lookup"><span data-stu-id="cbc29-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="cbc29-190">Na barra de aplicativos, na lateral direita equipes, clique em **… Aplicativos mais**.</span><span class="sxs-lookup"><span data-stu-id="cbc29-190">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="cbc29-191">Na barra de aplicativos, na parte inferior da equipes, passe para cima.</span><span class="sxs-lookup"><span data-stu-id="cbc29-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![App-Setup-Policies-Desktop-more-Apps.PNG](media/app-setup-policies-desktop-more-apps.png)<br>   |![App-Setup-Policies-Mobile-more-Apps.PNG](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="cbc29-194">O que é necessário saber sobre a experiência de equipes móvel?</span><span class="sxs-lookup"><span data-stu-id="cbc29-194">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="cbc29-195">Os clientes móveis equipes (iOS e Android) atualmente não há suporte para aplicativos de pessoais com estáticos guias.</span><span class="sxs-lookup"><span data-stu-id="cbc29-195">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="cbc29-196">Dependendo de aplicativos definidos na política, aplicativos vinculados ao cliente de desktop do equipes podem não aparecer nos clientes móveis equipes.</span><span class="sxs-lookup"><span data-stu-id="cbc29-196">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="cbc29-197">Pessoais bots ainda aparecerão no bate-papo em clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="cbc29-197">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="cbc29-198">Com os clientes móveis de equipes, os usuários verão apps equipes de núcleo como atividade, Chat e equipes e você pode fixar alguns aplicativos primários da Microsoft, como mudanças.</span><span class="sxs-lookup"><span data-stu-id="cbc29-198">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="cbc29-199">Podem usuários alterar a ordem dos aplicativos fixados através de uma diretiva?</span><span class="sxs-lookup"><span data-stu-id="cbc29-199">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="cbc29-200">Atualmente, os usuários podem alterar a ordem dos seus aplicativos fixados em clientes móveis de equipes, mas não nos clientes de área de trabalho ou web equipes.</span><span class="sxs-lookup"><span data-stu-id="cbc29-200">Currently, users can change the order of their pinned apps on Teams mobile clients but not on the Teams desktop or web clients.</span></span> 

### <a name="custom-teams-apps"></a><span data-ttu-id="cbc29-201">Aplicativos personalizados de equipes</span><span class="sxs-lookup"><span data-stu-id="cbc29-201">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="cbc29-202">Minha organização criado um aplicativo personalizado de equipes e publicá-lo, como AppSource ou o catálogo de aplicativos do inquilino, mas o ícone de aplicativo não será exibido como esperado quando o aplicativo é vinculado à barra de aplicativos em equipes.</span><span class="sxs-lookup"><span data-stu-id="cbc29-202">My organization built a custom Teams app and published it, either to AppSource or the Tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="cbc29-203">Como corrigi-lo?</span><span class="sxs-lookup"><span data-stu-id="cbc29-203">How do I fix it?</span></span> 

<span data-ttu-id="cbc29-204">Certifique-se de que você siga as diretrizes de logotipo antes de enviar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="cbc29-204">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="cbc29-205">Para saber mais, consulte a [lista de verificação para envio de painel do vendedor](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span><span class="sxs-lookup"><span data-stu-id="cbc29-205">To learn more, see [Checklist for Seller Dashboard submission](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span></span> 

 ## <a name="related-topics"></a><span data-ttu-id="cbc29-206">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="cbc29-206">Related topics</span></span>
- [<span data-ttu-id="cbc29-207">Configurações de administração para aplicativos no Teams</span><span class="sxs-lookup"><span data-stu-id="cbc29-207">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="cbc29-208">Gerenciar políticas de permissão de aplicativo em equipes</span><span class="sxs-lookup"><span data-stu-id="cbc29-208">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="cbc29-209">Gerenciar políticas de aplicativo personalizado e configurações no equipes</span><span class="sxs-lookup"><span data-stu-id="cbc29-209">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="cbc29-210">Publicar um aplicativo para o catálogo de aplicativos do locatário do cliente equipes</span><span class="sxs-lookup"><span data-stu-id="cbc29-210">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>](tenant-apps-catalog-teams.md)
