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
ms.openlocfilehash: dc5800d6231245be1b562dbedef44608232f04c1
ms.sourcegitcommit: 58fec9aebd80029e1f1e71376efe222f9abf707e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/08/2019
ms.locfileid: "31517099"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="3f6ce-103">Gerenciar políticas de configuração de aplicativo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3f6ce-103">Manage app setup policies in Microsoft Teams</span></span>

[!INCLUDE [preview-feature](includes/preview-feature.md)]

<span data-ttu-id="3f6ce-104">Como um administrador, você pode usar políticas de configuração de aplicativo para personalizar o Microsoft Teams para destacar os aplicativos que são mais importantes para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-104">As an admin, you can use app setup policies to customize Microsoft Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="3f6ce-105">Você escolher os aplicativos para fixar e definir a ordem em que aparecem.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-105">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="3f6ce-106">Políticas de configuração de aplicativo permitem que você demonstrem aplicativos que precisam de usuários em sua organização, incluindo aquelas criadas por terceiros ou por desenvolvedores em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-106">App setup policies let you showcase apps that users in your organization need, including ones built by third parties or by developers in your organization.</span></span> <span data-ttu-id="3f6ce-107">Você também pode usar políticas de configuração de aplicativo para gerenciar recursos internos como aparecem.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-107">You can also use app setup policies to manage how built-in features appear.</span></span>

<span data-ttu-id="3f6ce-108">Aplicativos são fixados a barra de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-108">Apps are pinned to the app bar.</span></span> <span data-ttu-id="3f6ce-109">Esta é a barra na lateral direita do cliente de desktop equipes e na parte inferior dos clientes móveis equipes (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="3f6ce-109">This is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span> 

|<span data-ttu-id="3f6ce-110">Cliente de desktop de equipes</span><span class="sxs-lookup"><span data-stu-id="3f6ce-110">Teams desktop client</span></span>  |<span data-ttu-id="3f6ce-111">Cliente móvel de equipes</span><span class="sxs-lookup"><span data-stu-id="3f6ce-111">Teams mobile client</span></span> |
|---------|---------|
|![App-Setup-Policies-Desktop-App-Bar.PNG](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![App-Setup-Policies-Mobile-App-Bar.PNG](media/app-setup-policies-mobile-app-bar.png)      |

<span data-ttu-id="3f6ce-114">Você gerenciar políticas de configuração de aplicativo no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-114">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="3f6ce-115">Você pode usar a política global de (padrão de toda a organização) ou como criar políticas personalizadas e atribuí-las aos usuários.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-115">You can use the global (Org-wide default) policy or create custom policies and assign them to users.</span></span> <span data-ttu-id="3f6ce-116">Usuários em sua organização receberá automaticamente a política global, a menos que você criar e atribuir uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-116">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span>

<span data-ttu-id="3f6ce-117">Você pode editar as configurações na política global para incluir os aplicativos que você deseja.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-117">You can edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="3f6ce-118">Se você desejar personalizar equipes para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-118">If you want to customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![instalação-App-policies.png](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="3f6ce-120">Se um usuário é atribuído a uma política personalizada, essa política se aplica ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-120">If a user is assigned a custom policy, that policy applies to the user.</span></span> <span data-ttu-id="3f6ce-121">Se um usuário não for atribuído a uma política personalizada, a política global se aplica ao usuário.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-121">If a user isn't assigned a custom policy, the global policy applies to the user.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="3f6ce-122">Criar uma política de instalação do aplicativo personalizado</span><span class="sxs-lookup"><span data-stu-id="3f6ce-122">Create a custom app setup policy</span></span>

<span data-ttu-id="3f6ce-123">Você pode usar o Centro de administração do Microsoft Teams para criar uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-123">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="3f6ce-124">No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes apps** > **políticas de instalação**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-124">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="3f6ce-125">Selecione **nova política**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-125">Select **New policy**.</span></span>
3. <span data-ttu-id="3f6ce-126">Insira um nome descritivo para a política e, em seguida, clique em **Adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-126">Enter a descriptive name for the policy, and then click **Add apps**.</span></span>
4. <span data-ttu-id="3f6ce-127">Ativar ou desativar **Permitir carregamento aplicativos personalizados**, dependendo se você deseja permitir que os usuários carregar os aplicativos personalizados para equipes.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-127">Turn on or turn off **Allow uploading custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span>
5. <span data-ttu-id="3f6ce-128">No painel **Adicionar fixados apps** , pesquise os aplicativos que você deseja adicionar e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-128">In the **Add pinned apps** pane, search for the apps you want to add, and then click **Add**.</span></span> <span data-ttu-id="3f6ce-129">Você também pode filtrar apps pela política de permissão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-129">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="3f6ce-130">Quando você tiver escolhido sua lista de aplicativos, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-130">When you've chosen your list of apps, click **Add**.</span></span>

     ![App-instalação-políticas-adicionar-apps.png](media/app-setup-policies-add-apps.png)

6. <span data-ttu-id="3f6ce-132">Organize os aplicativos na ordem que você deseja que eles aparecem em equipes e clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-132">Arrange the apps in the order that you want them to appear in Teams, and then click **Save**.</span></span>

    ![App-Setup-Policies-New-Policy-Setup.PNG](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="3f6ce-134">Editar uma política de instalação de aplicativo</span><span class="sxs-lookup"><span data-stu-id="3f6ce-134">Edit an app setup policy</span></span>

<span data-ttu-id="3f6ce-135">Você pode usar o Centro de administração do Microsoft Teams para editar uma política, incluindo a política global de (padrão de toda a organização) e políticas personalizadas que você criar.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-135">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="3f6ce-136">No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **equipes apps** > **políticas de instalação**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-136">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="3f6ce-137">Selecione a política que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-137">Select the policy you want to edit.</span></span> 
3. <span data-ttu-id="3f6ce-138">A partir daqui, faça as alterações que você deseja.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-138">From here, make the changes that you want.</span></span> <span data-ttu-id="3f6ce-139">Você pode adicionar, remover e alterar a ordem dos aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-139">You can add, remove, and change the order of apps.</span></span>
4. <span data-ttu-id="3f6ce-140">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-140">Click **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="3f6ce-141">Atribuir uma política de instalação do aplicativo personalizado aos usuários</span><span class="sxs-lookup"><span data-stu-id="3f6ce-141">Assign a custom app setup policy to users</span></span>

<span data-ttu-id="3f6ce-142">Você pode usar o Centro de administração do Microsoft Teams atribuir uma política personalizada para usuários individuais ou o Skype para o módulo de PowerShell de negócios para atribuir uma política personalizada para grupos de usuários, como um grupo de segurança ou grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-142">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module  to assign a custom policy to groups of users, such as a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="3f6ce-143">É recomendável usar o PowerShell somente para atribuir políticas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-143">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="3f6ce-144">Use o Centro de administração do Microsoft Teams para criar, editar e gerenciar políticas.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-144">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-individual-users"></a><span data-ttu-id="3f6ce-145">Atribuir uma política de instalação do aplicativo personalizado para usuários individuais</span><span class="sxs-lookup"><span data-stu-id="3f6ce-145">Assign a custom app setup policy to individual users</span></span>

1. <span data-ttu-id="3f6ce-146">No painel de navegação à esquerda do Centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-146">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click  the user.</span></span>
2. <span data-ttu-id="3f6ce-147">Ao lado de **políticas atribuído**, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-147">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="3f6ce-148">Em **política de instalação do aplicativo de equipes**, selecione a política de instalação do aplicativo que deseja atribuir e escolha **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-148">Under **Teams App Setup policy**, select the app setup policy you want to assign, and then choose **Save**.</span></span>

    ![App-instalação-políticas-atribuir-policy.png](media/app-setup-policies-assign-policy.png)

<span data-ttu-id="3f6ce-150">Você também pode atribuir uma política de instalação do aplicativo para um ou mais usuários da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="3f6ce-150">You can also assign an app setup policy to one or more users as follows:</span></span>

1. <span data-ttu-id="3f6ce-151">Vá para **o Centro de administração do Microsoft equipes** > **apps equipes** > **políticas de instalação**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-151">Go to **Microsoft Teams admin center** > **Teams apps** > **Setup policies**.</span></span>
2. <span data-ttu-id="3f6ce-152">Selecione a política clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-152">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="3f6ce-153">Selecione **Gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-153">Select **Manage users**.</span></span>
4. <span data-ttu-id="3f6ce-154">No painel de **Gerenciar usuários** , procure o usuário pelo nome de exibição ou nome de usuário, selecione o nome e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-154">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="3f6ce-155">Repita essa etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-155">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="3f6ce-156">Quando terminar de adicionar usuários, selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-156">When you are finished adding users, select **Save**.</span></span>

### <a name="assign-a-custom-app-setup-policy-to-users-in-a-group"></a><span data-ttu-id="3f6ce-157">Atribuir uma política de instalação do aplicativo personalizado aos usuários em um grupo</span><span class="sxs-lookup"><span data-stu-id="3f6ce-157">Assign a custom app setup policy to users in a group</span></span>

<span data-ttu-id="3f6ce-158">Convém atribuir uma política de instalação do aplicativo personalizado a vários usuários que você identificou.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-158">You may want to assign a custom app setup policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="3f6ce-159">Por exemplo, convém atribuir uma política a todos os usuários em um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-159">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="3f6ce-160">Você pode fazer isso Estabelecendo conexão com o Azure Active Directory PowerShell para o módulo de gráfico e do Skype para o módulo de PowerShell de negócios.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-160">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="3f6ce-161">Para obter mais informações sobre como usar o PowerShell para gerenciar equipes, consulte [Visão geral do PowerShell equipes](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="3f6ce-161">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="3f6ce-162">Neste exemplo, nós atribuímos uma política de instalação do aplicativo personalizado chamada HR App instalação política a todos os usuários no grupo Contoso Pharmaceuticals RH Project.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-162">In this example, we assign a custom app setup policy called HR App Setup Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="3f6ce-163">Certificar-se de que você primeiro conecte-se para o Windows Azure Active Directory PowerShell para o módulo de gráfico e Skype para o módulo de PowerShell de negócios seguindo as etapas em [conectar-se a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="3f6ce-163">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="3f6ce-164">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-164">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="3f6ce-165">Obtenha os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-165">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="3f6ce-166">Atribua a todos os usuários no grupo a uma política de instalação de aplicativo específico.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-166">Assign all users in the group to a particular app setup policy.</span></span> <span data-ttu-id="3f6ce-167">Neste exemplo, é política de instalação de aplicativo de RH.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-167">In this example, it's HR App Setup Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppSetupPolicy -PolicyName "HR App Setup Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="3f6ce-168">Dependendo do número de membros no grupo, este comando pode levar alguns minutos para executar.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-168">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="3f6ce-169">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="3f6ce-169">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="3f6ce-170">Como trabalhar com políticas de configuração de aplicativo</span><span class="sxs-lookup"><span data-stu-id="3f6ce-170">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="3f6ce-171">Quais políticas de configuração de aplicativo interno são incluídas no Centro de administração do Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="3f6ce-171">What built-in app setup policies are included in the Microsoft Teams admin center?</span></span>

- <span data-ttu-id="3f6ce-172">**Global (toda a organização padrão)**: esta política padrão se aplica a todos os usuários em sua organização, a menos que você atribua outra política.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-172">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="3f6ce-173">Edite a política global para aplicativos de pin que são mais importantes para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-173">Edit the global policy to pin apps that are most important for your users.</span></span>
- <span data-ttu-id="3f6ce-174">**FirstLineWorker**: esta diretiva é para trabalhadores de firstline.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-174">**FirstLineWorker**: This policy is for firstline workers.</span></span> <span data-ttu-id="3f6ce-175">Você pode atribuí-lo aos trabalhadores firstline em sua organização.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-175">You can assign it to firstline workers in your organization.</span></span> <span data-ttu-id="3f6ce-176">É importante saber que, como políticas personalizadas que você criar, você precisa atribuir a política aos usuários para que as configurações estejam ativos.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-176">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="3f6ce-177">Para obter mais informações, vá para a seção [atribuir uma política de instalação do aplicativo personalizado para os usuários](#assign-a-custom-app-setup-policy-to-users) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-177">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="3f6ce-178">Por que não é possível encontrar um aplicativo no painel Adicionar aplicativos fixados?</span><span class="sxs-lookup"><span data-stu-id="3f6ce-178">Why can't I find an app in the Add pinned apps pane?</span></span>

<span data-ttu-id="3f6ce-179">Nem todos os aplicativos podem ser fixados equipes por meio de uma política de instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-179">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="3f6ce-180">Alguns aplicativos podem não suportar essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-180">Some apps may not support this functionality.</span></span> <span data-ttu-id="3f6ce-181">Para localizar aplicativos que podem ser fixados, procure o aplicativo no painel **Adicionar fixados apps** .</span><span class="sxs-lookup"><span data-stu-id="3f6ce-181">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="3f6ce-182">Guias que têm um escopo pessoal (guias estáticos) e bots podem ser fixados o cliente de desktop equipes e esses aplicativos estão disponíveis no painel **Adicionar fixados apps** .</span><span class="sxs-lookup"><span data-stu-id="3f6ce-182">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="3f6ce-183">Tenha em mente que app store equipes lista todos os aplicativos de equipes, enquanto o painel de **Adicionar fixado apps** inclui apenas os aplicativos que podem ser fixados equipes através de uma diretiva.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-183">Keep in mind that the Teams app store lists all Teams apps whereas the **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span> 

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="3f6ce-184">Sou um equipes de Admin de educação. O que é necessário saber sobre políticas de configuração de aplicativo em equipes educacional?</span><span class="sxs-lookup"><span data-stu-id="3f6ce-184">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education?</span></span>

<span data-ttu-id="3f6ce-185">O aplicativo de chamada não está disponível em equipes educacional.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-185">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="3f6ce-186">Quando você cria uma nova política de instalação do aplicativo personalizado, o aplicativo de chamada é exibido na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-186">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="3f6ce-187">No entanto, o aplicativo não está vinculado aos clientes de equipes e equipes para usuários de educação não verá o aplicativo de chamadas em equipes.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-187">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span> 

#### <a name="how-many-apps-can-be-added-to-a-policy"></a><span data-ttu-id="3f6ce-188">Quantos aplicativos podem ser adicionados a uma política?</span><span class="sxs-lookup"><span data-stu-id="3f6ce-188">How many apps can be added to a policy?</span></span>

<span data-ttu-id="3f6ce-189">Um mínimo de dois aplicativos deve ser vinculado aos clientes móveis equipes (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="3f6ce-189">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="3f6ce-190">Se uma diretiva tiver menos de dois aplicativos, os clientes móveis não irão refletir as configurações de política e em vez disso continuarão usando a configuração existente.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-190">If a policy has less than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="3f6ce-191">Quanto tempo leva para que as alterações de diretiva entrem em vigor?</span><span class="sxs-lookup"><span data-stu-id="3f6ce-191">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="3f6ce-192">Após editar a política global ou atribuir uma política, pode demorar até 24 horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-192">After you edit the global policy or assign a policy, it can take up to 24 hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="3f6ce-193">Experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="3f6ce-193">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="3f6ce-194">Como os usuários podem ver todos os seus aplicativos fixados em equipes?</span><span class="sxs-lookup"><span data-stu-id="3f6ce-194">How can users see all their pinned apps in Teams?</span></span>

<span data-ttu-id="3f6ce-195">Para exibir todos os aplicativos que são vinculados para um usuário, os usuários podem ter que fazer o seguinte, dependendo do número de aplicativos instalados e o tamanho da janela de cliente suas equipes.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-195">To view all apps that are pinned for a user, users may have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="3f6ce-196">Cliente de desktop de equipes</span><span class="sxs-lookup"><span data-stu-id="3f6ce-196">Teams desktop client</span></span> |<span data-ttu-id="3f6ce-197">Cliente móvel de equipes</span><span class="sxs-lookup"><span data-stu-id="3f6ce-197">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="3f6ce-198">Na barra de aplicativos, na lateral direita equipes, clique em **… Aplicativos mais**.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-198">In the app bar on the side of Teams, click **... More apps**.</span></span>| <span data-ttu-id="3f6ce-199">Na barra de aplicativos, na parte inferior da equipes, passe para cima.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-199">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![App-Setup-Policies-Desktop-more-Apps.PNG](media/app-setup-policies-desktop-more-apps.png)<br>   |![App-Setup-Policies-Mobile-more-Apps.PNG](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="3f6ce-202">O que é necessário saber sobre a experiência de equipes móvel?</span><span class="sxs-lookup"><span data-stu-id="3f6ce-202">What do I need to know about the Teams mobile experience?</span></span>

<span data-ttu-id="3f6ce-203">Os clientes móveis equipes (iOS e Android) atualmente não há suporte para aplicativos de pessoais com estáticos guias.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-203">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="3f6ce-204">Dependendo de aplicativos definidos na política, aplicativos vinculados ao cliente de desktop do equipes podem não aparecer nos clientes móveis equipes.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-204">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="3f6ce-205">Pessoais bots ainda aparecerão no bate-papo em clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-205">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="3f6ce-206">Com os clientes móveis de equipes, os usuários verão apps equipes de núcleo como atividade, Chat e equipes e você pode fixar alguns aplicativos primários da Microsoft, como mudanças.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-206">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="3f6ce-207">Podem usuários alterar a ordem dos aplicativos fixados através de uma diretiva?</span><span class="sxs-lookup"><span data-stu-id="3f6ce-207">Can users change the order of apps pinned through a policy?</span></span>

<span data-ttu-id="3f6ce-208">Atualmente, os usuários podem alterar a ordem dos seus aplicativos fixados em clientes móveis de equipes, mas não nos clientes de área de trabalho ou web equipes.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-208">Currently, users can change the order of their pinned apps on Teams mobile clients but not on the Teams desktop or web clients.</span></span> 

### <a name="custom-teams-apps"></a><span data-ttu-id="3f6ce-209">Aplicativos personalizados de equipes</span><span class="sxs-lookup"><span data-stu-id="3f6ce-209">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="3f6ce-210">Minha organização criado um aplicativo personalizado de equipes e publicá-lo, como AppSource ou o catálogo de aplicativos do inquilino, mas o ícone de aplicativo não será exibido como esperado quando o aplicativo é vinculado à barra de aplicativos em equipes.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-210">My organization built a custom Teams app and published it, either to AppSource or the Tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="3f6ce-211">Como corrigi-lo?</span><span class="sxs-lookup"><span data-stu-id="3f6ce-211">How do I fix it?</span></span> 

<span data-ttu-id="3f6ce-212">Certifique-se de que você siga as diretrizes de logotipo antes de enviar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="3f6ce-212">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="3f6ce-213">Para saber mais, consulte a [lista de verificação para envio de painel do vendedor](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span><span class="sxs-lookup"><span data-stu-id="3f6ce-213">To learn more, see [Checklist for Seller Dashboard submission](https://docs.microsoft.com/microsoftteams/platform/publishing/office-store-checklist).</span></span> 

 ## <a name="related-topics"></a><span data-ttu-id="3f6ce-214">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="3f6ce-214">Related topics</span></span>
- [<span data-ttu-id="3f6ce-215">Configurações de administração para aplicativos no Teams</span><span class="sxs-lookup"><span data-stu-id="3f6ce-215">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="3f6ce-216">Gerenciar políticas de permissões de aplicativo no Teams</span><span class="sxs-lookup"><span data-stu-id="3f6ce-216">Manage app permission policies in Teams</span></span>](teams-app-permission-policies.md)
- [<span data-ttu-id="3f6ce-217">Gerenciar políticas de aplicativo personalizado e as configurações no Teams</span><span class="sxs-lookup"><span data-stu-id="3f6ce-217">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
- [<span data-ttu-id="3f6ce-218">Publicar um aplicativo para o catálogo de aplicativos do locatário do cliente equipes</span><span class="sxs-lookup"><span data-stu-id="3f6ce-218">Publish an app to the Tenant Apps Catalog from the Teams client</span></span>](tenant-apps-catalog-teams.md)
