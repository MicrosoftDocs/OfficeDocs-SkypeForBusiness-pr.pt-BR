---
title: Gerenciar políticas de permissões de aplicativo no Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 3/18/2019
ms.reviewer: lajin
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Help
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: Saiba mais sobre as políticas de permissão do aplicativo no Microsoft Teams e como usá-las para controlar quais aplicativos estão disponíveis para os usuários em sua organização.
f1keywords:
- ms.teamsadmincenter.apppolicies.overview
ms.openlocfilehash: fac559fb492155af9953beb74c2fac1526f01432
ms.sourcegitcommit: 55da03c85237b43b848e7ff9b427304c2d9e568f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/04/2019
ms.locfileid: "34681917"
---
# <a name="manage-app-permission-policies-in-microsoft-teams"></a><span data-ttu-id="9dc56-103">Gerenciar políticas de permissões de aplicativo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="9dc56-103">Manage app permission policies in Microsoft Teams</span></span>

> [!INCLUDE [feature coming soon](includes/new-feature-coming-soon-article.md)]

> [!NOTE]
> <span data-ttu-id="9dc56-104">Para obter o método atual de gerenciamento de aplicativos no Microsoft Teams, consulte [gerenciar as configurações do Microsoft Teams para sua organização](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).</span><span class="sxs-lookup"><span data-stu-id="9dc56-104">For the current method of managing apps in Microsoft Teams, see [Manage Microsoft Teams settings for your organization](https://docs.microsoft.com/MicrosoftTeams/enable-features-office-365).</span></span>

<span data-ttu-id="9dc56-105">Como administrador, você pode usar políticas de permissão do aplicativo para controlar quais aplicativos estão disponíveis para os usuários do Microsoft Teams em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9dc56-105">As an admin, you can use app permission policies to control what apps are available to Microsoft Teams users in your organization.</span></span> <span data-ttu-id="9dc56-106">Você pode permitir ou bloquear todos os aplicativos ou aplicativos específicos publicados pela Microsoft, por terceiros e pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="9dc56-106">You can allow or block all apps or specific apps published by Microsoft, third-parties, and your organization.</span></span> <span data-ttu-id="9dc56-107">Quando você bloqueia um aplicativo, os usuários não podem instalá-lo na App Store do teams.</span><span class="sxs-lookup"><span data-stu-id="9dc56-107">When you block an app, users are unable to install it from the Teams app store.</span></span>

<span data-ttu-id="9dc56-108">Você gerencia políticas de permissão do aplicativo no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9dc56-108">You manage app permission policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="9dc56-109">Você pode aplicar as configurações de toda a organização, usar a política global (padrão para toda a organização) e criar e atribuir políticas personalizadas a usuários ou usuários individuais em um grupo.</span><span class="sxs-lookup"><span data-stu-id="9dc56-109">You can apply settings org-wide, use the global (Org-wide default) policy, and create and assign custom policies to individual users or users in a group.</span></span>  

![Captura de tela da política de permissão do aplicativo](media/app-permission-policies.png)

> [!NOTE]
> <span data-ttu-id="9dc56-111">Os usuários em sua organização receberão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="9dc56-111">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="9dc56-112">As configurações de aplicativo de toda a organização substituem a política global e quaisquer políticas personalizadas que você criar e atribuir aos usuários.</span><span class="sxs-lookup"><span data-stu-id="9dc56-112">Org-wide app settings override the global policy and any custom policies that you create and assign to users.</span></span>

<span data-ttu-id="9dc56-113">Digamos, por exemplo, que você queira bloquear todos os aplicativos de terceiros e permitir que aplicativos específicos da Microsoft para a equipe de RH em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9dc56-113">Say, for example, you want to block all third-party apps and allow specific apps from Microsoft for the HR team in your organization.</span></span> <span data-ttu-id="9dc56-114">Você criaria uma política personalizada denominada política de permissão do aplicativo HR, defini-la para bloquear e permitir os aplicativos desejados e, em seguida, atribuí-la aos usuários na equipe de RH.</span><span class="sxs-lookup"><span data-stu-id="9dc56-114">You would create a custom policy named HR App Permission Policy, set it to block and allow the apps that you want, and then assign it to users on the HR team.</span></span>

## <a name="manage-org-wide-app-settings"></a><span data-ttu-id="9dc56-115">Gerenciar configurações de aplicativo de toda a organização</span><span class="sxs-lookup"><span data-stu-id="9dc56-115">Manage org-wide app settings</span></span>

<span data-ttu-id="9dc56-116">Use as configurações de aplicativo de toda a organização para controlar quais aplicativos estão disponíveis em sua organização.</span><span class="sxs-lookup"><span data-stu-id="9dc56-116">Use org-wide app settings to control which apps are available across your organization.</span></span> <span data-ttu-id="9dc56-117">As configurações de aplicativo de toda a organização governam o comportamento para todos os usuários e substituem quaisquer outras políticas de permissão de aplicativo atribuídas aos usuários.</span><span class="sxs-lookup"><span data-stu-id="9dc56-117">Org-wide app settings govern the behavior for all users and override any other app permission policies assigned to users.</span></span> <span data-ttu-id="9dc56-118">As configurações de aplicativo de toda a organização entram em vigor imediatamente e você pode usá-las para controlar aplicativos mal-intencionados ou problemáticos.</span><span class="sxs-lookup"><span data-stu-id="9dc56-118">Org-wide app settings take effect immediately and you can use them to control malicious or problematic apps.</span></span>

1. <span data-ttu-id="9dc56-119">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de permissão**do **aplicativo** > Teams.</span><span class="sxs-lookup"><span data-stu-id="9dc56-119">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="9dc56-120">Selecione **configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-120">Select **Org-wide settings**.</span></span> <span data-ttu-id="9dc56-121">Em seguida, você pode definir as configurações desejadas no painel.</span><span class="sxs-lookup"><span data-stu-id="9dc56-121">You can then configure the settings you want in the panel.</span></span> 
<span data-ttu-id="9dc56-122">![Captura de tela das configurações do aplicativo de toda a organização](media/app-permission-policies-org-wide-settings.png)</span><span class="sxs-lookup"><span data-stu-id="9dc56-122">![Screen shot of org-wide app settings](media/app-permission-policies-org-wide-settings.png)</span></span>
3. <span data-ttu-id="9dc56-123">Em **aplicativos de terceiros**, desative ou ative essas configurações para controlar o acesso a aplicativos de terceiros:</span><span class="sxs-lookup"><span data-stu-id="9dc56-123">Under **Third-party apps**, turn off or turn on these settings to control access to third-party apps:</span></span>

    - <span data-ttu-id="9dc56-124">**Permitir aplicativos de terceiros no Teams**: controla se os usuários podem usar aplicativos de terceiros.</span><span class="sxs-lookup"><span data-stu-id="9dc56-124">**Allow third-party apps in Teams**: This controls whether users can use third-party apps.</span></span>
    - <span data-ttu-id="9dc56-125">**Permitir que todos os novos aplicativos de terceiros publicados na loja por padrão**: controlam se novos aplicativos de terceiros publicados na App App Store se tornam disponíveis automaticamente no Teams.</span><span class="sxs-lookup"><span data-stu-id="9dc56-125">**Allow any new third-party apps published to the store by default**: This controls whether new third-party apps that are published to the Teams app store become automatically available in Teams.</span></span> <span data-ttu-id="9dc56-126">Você só pode definir esta opção se permitir aplicativos de terceiros.</span><span class="sxs-lookup"><span data-stu-id="9dc56-126">You can only set this option if you allow third-party apps.</span></span>

4. <span data-ttu-id="9dc56-127">Em **aplicativos personalizados**, desative ou ative **permitir interação com aplicativos personalizados**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-127">Under **Custom apps**, turn off or turn on **Allow interaction with custom apps**.</span></span> <span data-ttu-id="9dc56-128">Esta configuração controla se os usuários podem interagir com aplicativos personalizados (Sideload).</span><span class="sxs-lookup"><span data-stu-id="9dc56-128">This setting controls whether users can interact with custom (sideloaded) apps.</span></span> <span data-ttu-id="9dc56-129">Tenha em mente que isso é diferente de permitir que os \*\* usuários carreguem aplicativos personalizados.</span><span class="sxs-lookup"><span data-stu-id="9dc56-129">Keep in mind that this is different from allowing users to *upload* custom apps.</span></span>
5. <span data-ttu-id="9dc56-130">Em **aplicativos bloqueados**, procure e adicione os aplicativos que você deseja bloquear em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="9dc56-130">Under **Blocked apps**, search for and add the apps that you want to block across your organization.</span></span> <span data-ttu-id="9dc56-131">Você pode escolher os aplicativos do catálogo de aplicativos do locatário ou da App Team Store.</span><span class="sxs-lookup"><span data-stu-id="9dc56-131">You can choose apps from the tenant app catalog or the Teams app store.</span></span>
6. <span data-ttu-id="9dc56-132">Clique em **salvar** para que as configurações de aplicativo de toda a organização entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="9dc56-132">Click **Save** for org-wide app settings to take effect.</span></span>

## <a name="create-a-custom-app-permission-policy"></a><span data-ttu-id="9dc56-133">Criar uma política de permissão de aplicativo personalizada</span><span class="sxs-lookup"><span data-stu-id="9dc56-133">Create a custom app permission policy</span></span>

<span data-ttu-id="9dc56-134">Se você quiser controlar os aplicativos que estão disponíveis para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas de permissão de aplicativo personalizadas.</span><span class="sxs-lookup"><span data-stu-id="9dc56-134">If you want to control the apps that are available for different groups of users in your organization, create and assign one or more custom app permission policies.</span></span> <span data-ttu-id="9dc56-135">Você pode criar e atribuir políticas personalizadas separadas com base em aplicativos que são publicados pela Microsoft, por terceiros ou por sua organização.</span><span class="sxs-lookup"><span data-stu-id="9dc56-135">You can create and assign separate custom policies based on whether apps are published by Microsoft, third-parties, or your organization.</span></span> <span data-ttu-id="9dc56-136">É importante saber que, após a criação de uma política personalizada, você não poderá alterá-la se os aplicativos de terceiros estiverem desabilitados nas configurações de toda a organização.</span><span class="sxs-lookup"><span data-stu-id="9dc56-136">It's important to know that after you create a custom policy, you can't change it if third-party apps are disabled in org-wide settings.</span></span> 

1. <span data-ttu-id="9dc56-137">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de permissão**do **aplicativo** > Teams.</span><span class="sxs-lookup"><span data-stu-id="9dc56-137">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="9dc56-138">Selecione **nova política**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-138">Select **New policy**.</span></span>
    <span data-ttu-id="9dc56-139">![Captura de tela da política de permissão de novo aplicativo](media/app-permission-policies-new-policy.png)</span><span class="sxs-lookup"><span data-stu-id="9dc56-139">![Screen shot of new app permission policy](media/app-permission-policies-new-policy.png)</span></span>
3. <span data-ttu-id="9dc56-140">Digite um nome descritivo para a política.</span><span class="sxs-lookup"><span data-stu-id="9dc56-140">Enter a descriptive name for the policy.</span></span>
4. <span data-ttu-id="9dc56-141">Em **aplicativos da Microsoft**, **aplicativos de terceiros**e **aplicativos**de locatários, selecione uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="9dc56-141">Under **Microsoft apps**, **Third-party apps**, and **Tenant apps**, select one of the following:</span></span>

    - <span data-ttu-id="9dc56-142">**Permitir todos os aplicativos**</span><span class="sxs-lookup"><span data-stu-id="9dc56-142">**Allow all apps**</span></span>
    - <span data-ttu-id="9dc56-143">**Permitir aplicativos específicos e bloquear todos os outros**</span><span class="sxs-lookup"><span data-stu-id="9dc56-143">**Allow specific apps and block all others**</span></span>
    - <span data-ttu-id="9dc56-144">**Bloquear aplicativos específicos e permitir todos os outros**</span><span class="sxs-lookup"><span data-stu-id="9dc56-144">**Block specific apps and allow all others**</span></span>
    - <span data-ttu-id="9dc56-145">**Bloquear todos os aplicativos**</span><span class="sxs-lookup"><span data-stu-id="9dc56-145">**Block all apps**</span></span>

5. <span data-ttu-id="9dc56-146">Se você selecionou **permitir aplicativos específicos e bloquear outras pessoas**, adicione os aplicativos que deseja permitir:</span><span class="sxs-lookup"><span data-stu-id="9dc56-146">If you selected **Allow specific apps and block others**, add the apps that you want to allow:</span></span>

    1. <span data-ttu-id="9dc56-147">Selecione **permitir aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-147">Select **Allow apps**.</span></span>
    1. <span data-ttu-id="9dc56-148">Procure os aplicativos que você deseja permitir e, em seguida, clique em **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-148">Search for the apps that you want to allow, and then click **Add**.</span></span> <span data-ttu-id="9dc56-149">Os resultados da pesquisa são filtrados para o fornecedor do aplicativo (**aplicativos da Microsoft**, **aplicativos**de terceiros ou **aplicativos locatários**).</span><span class="sxs-lookup"><span data-stu-id="9dc56-149">The search results are filtered to the app publisher (**Microsoft apps**, **Third-party apps**, or **Tenant apps**).</span></span>
    1. <span data-ttu-id="9dc56-150">Quando tiver escolhido a lista de aplicativos, clique em **permitir**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-150">When you've chosen the list of apps, click **Allow**.</span></span>

6. <span data-ttu-id="9dc56-151">Da mesma forma, se você selecionou **bloquear aplicativos específicos e permitir todos os outros**, procure e adicione os aplicativos que deseja bloquear.</span><span class="sxs-lookup"><span data-stu-id="9dc56-151">Similarly, if you selected **Block specific apps and allow all others**, search for and add the apps that you want to block.</span></span>
7. <span data-ttu-id="9dc56-152">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-152">Click **Save**.</span></span>

## <a name="edit-an-app-permission-policy"></a><span data-ttu-id="9dc56-153">Editar uma política de permissão do aplicativo</span><span class="sxs-lookup"><span data-stu-id="9dc56-153">Edit an app permission policy</span></span>

<span data-ttu-id="9dc56-154">Você pode usar o centro de administração do Microsoft Teams para editar uma política, incluindo a política global (padrão de toda a organização) e políticas personalizadas que você criar.</span><span class="sxs-lookup"><span data-stu-id="9dc56-154">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span> 

1. <span data-ttu-id="9dc56-155">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para**políticas de permissão**do **aplicativo** > Teams.</span><span class="sxs-lookup"><span data-stu-id="9dc56-155">In the left navigation of the Microsoft Teams admin center, go to **Teams app** > **Permission policies**.</span></span>
2. <span data-ttu-id="9dc56-156">Selecione a política que você deseja editar.</span><span class="sxs-lookup"><span data-stu-id="9dc56-156">Select the policy you want to edit.</span></span>
3. <span data-ttu-id="9dc56-157">Aqui, faça as alterações desejadas.</span><span class="sxs-lookup"><span data-stu-id="9dc56-157">From here, make the changes that you want.</span></span> <span data-ttu-id="9dc56-158">Você pode gerenciar as configurações com base no editor do aplicativo e adicionar e remover aplicativos com base na configuração permitir/bloquear.</span><span class="sxs-lookup"><span data-stu-id="9dc56-158">You can manage settings based on the app publisher and add and remove apps based on the allow/block setting.</span></span>
4. <span data-ttu-id="9dc56-159">Clique em **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-159">Click **Save**.</span></span>

## <a name="assign-a-custom-app-permission-policy-to-users"></a><span data-ttu-id="9dc56-160">Atribuir uma política de permissão de aplicativo personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="9dc56-160">Assign a custom app permission policy to users</span></span>

<span data-ttu-id="9dc56-161">Você pode usar o centro de administração do Microsoft Teams para atribuir uma política personalizada a usuários individuais ou o módulo do PowerShell do Skype for Business para atribuir uma política personalizada a vários usuários, como todos os usuários de um grupo de segurança ou grupo de distribuição.</span><span class="sxs-lookup"><span data-stu-id="9dc56-161">You can use the Microsoft Teams admin center to assign a custom policy to individual users or the Skype for Business PowerShell module to assign a custom policy to multiple users, such as all users in a security group or distribution group.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="9dc56-162">Recomendamos usar o PowerShell somente para atribuir políticas a usuários.</span><span class="sxs-lookup"><span data-stu-id="9dc56-162">We recommend using PowerShell only to assign policies to users.</span></span> <span data-ttu-id="9dc56-163">Use o centro de administração do Microsoft Teams para criar, editar e gerenciar políticas.</span><span class="sxs-lookup"><span data-stu-id="9dc56-163">Use the Microsoft Teams admin center to create, edit, and manage policies.</span></span>

### <a name="assign-a-custom-app-permission-policy-to-individual-users"></a><span data-ttu-id="9dc56-164">Atribuir uma política de permissão de aplicativo personalizada a usuários individuais</span><span class="sxs-lookup"><span data-stu-id="9dc56-164">Assign a custom app permission policy to individual users</span></span>

1. <span data-ttu-id="9dc56-165">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para **usuários**e, em seguida, clique no usuário.</span><span class="sxs-lookup"><span data-stu-id="9dc56-165">In the left navigation of the Microsoft Teams admin center, go to **Users**, and then click the user.</span></span>
2. <span data-ttu-id="9dc56-166">Ao lado de **políticas atribuídas**, escolha **Editar**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-166">Next to **Assigned policies**, choose **Edit**.</span></span>
3. <span data-ttu-id="9dc56-167">Em **política de permissão do aplicativo**, selecione a política de permissão do aplicativo que você deseja atribuir e, em seguida, escolha **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-167">Under **App permission policy**, select the app permission policy you want to assign, and then choose **Save**.</span></span>

    ![App-setup-Permission-Assign-Policy. png](media/app-permission-policies-assign-policy.png)

<span data-ttu-id="9dc56-169">Você também pode atribuir uma política de permissão do aplicativo a um ou mais usuários da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="9dc56-169">You can also assign an app permission policy to one or more users as follows:</span></span>

1. <span data-ttu-id="9dc56-170">Vá para**políticas de permissão**de**aplicativos** >  **do centro** > de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9dc56-170">Go to **Microsoft Teams admin center** > **Teams apps** > **Permission policies**.</span></span>
2. <span data-ttu-id="9dc56-171">Selecione a política clicando à esquerda do nome da política.</span><span class="sxs-lookup"><span data-stu-id="9dc56-171">Select the policy by clicking to the left of the policy name.</span></span>
3. <span data-ttu-id="9dc56-172">Selecione **gerenciar usuários**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-172">Select **Manage users**.</span></span>
4. <span data-ttu-id="9dc56-173">No painel **gerenciar usuários** , procure pelo usuário por nome para exibição ou por nome de usuário, selecione o nome e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-173">In the **Manage users** pane, search for the user by display name or by user name, select the name, and then select **Add**.</span></span> <span data-ttu-id="9dc56-174">Repita esta etapa para cada usuário que você deseja adicionar.</span><span class="sxs-lookup"><span data-stu-id="9dc56-174">Repeat this step for each user that you want to add.</span></span>
5. <span data-ttu-id="9dc56-175">Quando terminar de adicionar usuários, selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="9dc56-175">When you are finished adding users, select **Save**.</span></span>
 

### <a name="assign-a-custom-app-permission-policy-to-users-in-a-group"></a><span data-ttu-id="9dc56-176">Atribuir uma política de permissão de aplicativo personalizada a usuários em um grupo</span><span class="sxs-lookup"><span data-stu-id="9dc56-176">Assign a custom app permission policy to users in a group</span></span>

<span data-ttu-id="9dc56-177">Você pode querer atribuir uma política de permissão de aplicativo personalizada a vários usuários que você já tenha identificado.</span><span class="sxs-lookup"><span data-stu-id="9dc56-177">You may want to assign a custom app permission policy to multiple users that you’ve already identified.</span></span> <span data-ttu-id="9dc56-178">Por exemplo, você pode querer atribuir uma política a todos os usuários de um grupo de segurança.</span><span class="sxs-lookup"><span data-stu-id="9dc56-178">For example, you may want to assign a policy to all users in a security group.</span></span> <span data-ttu-id="9dc56-179">Você pode fazer isso conectando-se ao módulo do PowerShell do Azure Active Directory e ao módulo do PowerShell do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9dc56-179">You can do this by connecting to the Azure Active Directory PowerShell for Graph module and the Skype for Business PowerShell module.</span></span> <span data-ttu-id="9dc56-180">Para obter mais informações sobre como usar o PowerShell para gerenciar o Microsoft Teams, consulte [visão geral do teams PowerShell](teams-powershell-overview.md).</span><span class="sxs-lookup"><span data-stu-id="9dc56-180">For more information about using PowerShell to manage Teams, see [Teams PowerShell Overview](teams-powershell-overview.md).</span></span>

<span data-ttu-id="9dc56-181">Neste exemplo, atribuímos uma política de permissão de aplicativo personalizada chamada política de permissão do aplicativo HR a todos os usuários do grupo de projetos de RH da Contoso Pharmaceuticals.</span><span class="sxs-lookup"><span data-stu-id="9dc56-181">In this example, we assign a custom app permission policy called HR App Permission Policy to all users in the Contoso Pharmaceuticals HR Project group.</span></span>  

> [!NOTE]
> <span data-ttu-id="9dc56-182">Verifique se você se conectou primeiro ao módulo do PowerShell do Azure Active Directory e do módulo do PowerShell do Skype for Business seguindo as etapas em [conectar a todos os serviços do Office 365 em uma única janela do Windows PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span><span class="sxs-lookup"><span data-stu-id="9dc56-182">Make sure you first connect to the Azure Active Directory PowerShell for Graph module and Skype for Business PowerShell module by following the steps in [Connect to all Office 365 services in a single Windows PowerShell window](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-all-office-365-services-in-a-single-windows-powershell-window).</span></span>

<span data-ttu-id="9dc56-183">Obtenha o GroupObjectId do grupo específico.</span><span class="sxs-lookup"><span data-stu-id="9dc56-183">Get the GroupObjectId of the particular group.</span></span>
```
$group = Get-AzureADGroup -SearchString "Contoso Pharmaceuticals HR Project"
```
<span data-ttu-id="9dc56-184">Obter os membros do grupo especificado.</span><span class="sxs-lookup"><span data-stu-id="9dc56-184">Get the members of the specified group.</span></span>
```
$members = Get-AzureADGroupMember -ObjectId $group.ObjectId -All $true | Where-Object {$_.ObjectType -eq "User"}
```
<span data-ttu-id="9dc56-185">Atribua todos os usuários do grupo a uma política de permissão de aplicativo específica.</span><span class="sxs-lookup"><span data-stu-id="9dc56-185">Assign all users in the group to a particular app permission policy.</span></span> <span data-ttu-id="9dc56-186">Neste exemplo, a política de permissão do aplicativo em RH.</span><span class="sxs-lookup"><span data-stu-id="9dc56-186">In this example, it's HR App Permission Policy.</span></span>
```
$members | ForEach-Object { Grant-CsTeamsAppPermissionPolicy -PolicyName "HR App Permission Policy" -Identity $_.EmailAddress}
``` 
<span data-ttu-id="9dc56-187">Dependendo do número de membros do grupo, esse comando pode levar alguns minutos para ser executado.</span><span class="sxs-lookup"><span data-stu-id="9dc56-187">Depending on the number of members in the group, this command may take several minutes to execute.</span></span>

## <a name="faq"></a><span data-ttu-id="9dc56-188">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="9dc56-188">FAQ</span></span>

### <a name="working-with-app-permission-policies"></a><span data-ttu-id="9dc56-189">Trabalhando com políticas de permissão do aplicativo</span><span class="sxs-lookup"><span data-stu-id="9dc56-189">Working with app permission policies</span></span>

#### <a name="can-i-control-line-of-business-lob-apps"></a><span data-ttu-id="9dc56-190">Posso controlar os aplicativos de linha de negócios (LOB)?</span><span class="sxs-lookup"><span data-stu-id="9dc56-190">Can I control line of business (LOB) apps?</span></span>

<span data-ttu-id="9dc56-191">Sim, você pode usar políticas de permissão do aplicativo para controlar a distribuição e distribuição de aplicativos personalizados (LOB).</span><span class="sxs-lookup"><span data-stu-id="9dc56-191">Yes, you can use app permission policies to control the rollout and distribution of custom (LOB) apps.</span></span>

#### <a name="how-do-app-permission-policies-relate-to-pinned-apps-and-app-setup-policies"></a><span data-ttu-id="9dc56-192">Como as políticas de permissão do aplicativo se relacionam a aplicativos fixos e políticas de configuração de aplicativos?</span><span class="sxs-lookup"><span data-stu-id="9dc56-192">How do app permission policies relate to pinned apps and app setup policies?</span></span>

<span data-ttu-id="9dc56-193">Você pode usar as políticas de configuração do aplicativo em conjunto com políticas de permissão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="9dc56-193">You can use app setup policies together with app permission policies.</span></span> <span data-ttu-id="9dc56-194">Aplicativos pré-projetados são selecionados do conjunto de aplicativos habilitados para um usuário.</span><span class="sxs-lookup"><span data-stu-id="9dc56-194">Pre-pinned apps are selected from the set of enabled apps for a user.</span></span> <span data-ttu-id="9dc56-195">Além disso, se um usuário tiver uma política de permissão do aplicativo que bloqueie um aplicativo na política de configuração do aplicativo, esse aplicativo não aparecerá no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9dc56-195">Additionally, if a user has an app permission policy that blocks an app in their app setup policy, that app won't appear in Teams.</span></span>

#### <a name="can-i-use-app-permission-policies-to-restrict-uploading-custom-apps-also-known-as-sideloading"></a><span data-ttu-id="9dc56-196">Posso usar políticas de permissão do aplicativo para restringir o upload de aplicativos personalizados (também conhecidos como Sideload)?</span><span class="sxs-lookup"><span data-stu-id="9dc56-196">Can I use app permission policies to restrict uploading custom apps (also known as sideloading)?</span></span>

<span data-ttu-id="9dc56-197">Para saber mais sobre como restringir o upload de aplicativos personalizados, consulte [gerenciar configurações e políticas personalizadas do aplicativo no](teams-custom-app-policies-and-settings.md)Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9dc56-197">To learn more about how to restrict uploading custom apps, see [Manage custom app policies and settings in Teams](teams-custom-app-policies-and-settings.md).</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="9dc56-198">Quanto tempo leva para as alterações de política entrarem em vigor?</span><span class="sxs-lookup"><span data-stu-id="9dc56-198">How long does it take for policy changes to take effect?</span></span>

<span data-ttu-id="9dc56-199">Depois de editar a política global ou atribuir uma política aos usuários, pode levar até 24 horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="9dc56-199">After you edit the global policy or assign a policy to users, it can take up to 24 hours for changes to take effect.</span></span> <span data-ttu-id="9dc56-200">As configurações de aplicativo de toda a organização entram em vigor imediatamente.</span><span class="sxs-lookup"><span data-stu-id="9dc56-200">Org-wide app settings take effect immediately.</span></span>

#### <a name="does-blocking-an-app-apply-to-teams-mobile-clients"></a><span data-ttu-id="9dc56-201">Bloquear um aplicativo se aplica a clientes móveis do Microsoft Teams?</span><span class="sxs-lookup"><span data-stu-id="9dc56-201">Does blocking an app apply to Teams mobile clients?</span></span>

<span data-ttu-id="9dc56-202">Sim, quando você bloqueia um aplicativo, esse aplicativo é bloqueado em todos os clientes do teams.</span><span class="sxs-lookup"><span data-stu-id="9dc56-202">Yes, when you block an app, that app is blocked across all Teams clients.</span></span>  

### <a name="user-experience"></a><span data-ttu-id="9dc56-203">Experiência do usuário</span><span class="sxs-lookup"><span data-stu-id="9dc56-203">User experience</span></span>

#### <a name="what-does-a-user-experience-when-an-app-is-blocked"></a><span data-ttu-id="9dc56-204">O que uma experiência do usuário quando um aplicativo está bloqueado?</span><span class="sxs-lookup"><span data-stu-id="9dc56-204">What does a user experience when an app is blocked?</span></span>

<span data-ttu-id="9dc56-205">Os usuários não podem interagir com um aplicativo bloqueado ou com seus recursos, tais como bots, guias e extensões de mensagens.</span><span class="sxs-lookup"><span data-stu-id="9dc56-205">Users can't interact with a blocked app or its capabilities, such bots, tabs, and messaging extensions.</span></span> <span data-ttu-id="9dc56-206">Em um contexto compartilhado, como uma equipe ou um chat em grupo, os bots ainda podem enviar mensagens para todos os participantes desse contexto.</span><span class="sxs-lookup"><span data-stu-id="9dc56-206">In a shared context, such as a team or group chat, bots can still send messages to all participants of that context.</span></span> <span data-ttu-id="9dc56-207">Teams indica ao usuário quando um aplicativo é bloqueado.</span><span class="sxs-lookup"><span data-stu-id="9dc56-207">Teams indicates to the user when an app is blocked.</span></span> 

<span data-ttu-id="9dc56-208">Por exemplo, quando um aplicativo é bloqueado, os usuários não podem fazer nenhum dos seguintes procedimentos:</span><span class="sxs-lookup"><span data-stu-id="9dc56-208">For example, when an app is blocked, users can't do any of the following:</span></span>

- <span data-ttu-id="9dc56-209">Adicionar o aplicativo pessoalmente ou a um chat ou a uma equipe</span><span class="sxs-lookup"><span data-stu-id="9dc56-209">Add the app personally or to a chat or team</span></span>
- <span data-ttu-id="9dc56-210">Enviar mensagens ao bot do aplicativo</span><span class="sxs-lookup"><span data-stu-id="9dc56-210">Send messages to the app’s bot</span></span>
- <span data-ttu-id="9dc56-211">Executar ações de botão que enviam informações de volta para o aplicativo, como mensagens acionáveis</span><span class="sxs-lookup"><span data-stu-id="9dc56-211">Perform button actions that send information back to the app, such as actionable messages</span></span>  
- <span data-ttu-id="9dc56-212">Exibir a guia do aplicativo</span><span class="sxs-lookup"><span data-stu-id="9dc56-212">View the app’s tab</span></span>
- <span data-ttu-id="9dc56-213">Configurar conectores para receber notificações</span><span class="sxs-lookup"><span data-stu-id="9dc56-213">Set up connectors to receive notifications</span></span>
- <span data-ttu-id="9dc56-214">Usar a extensão de mensagens do aplicativo</span><span class="sxs-lookup"><span data-stu-id="9dc56-214">Use the app’s messaging extension</span></span>

 ## <a name="related-topics"></a><span data-ttu-id="9dc56-215">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="9dc56-215">Related topics</span></span>
- [<span data-ttu-id="9dc56-216">Configurações de administração para aplicativos no Teams</span><span class="sxs-lookup"><span data-stu-id="9dc56-216">Admin settings for apps in Teams</span></span>](admin-settings.md)
- [<span data-ttu-id="9dc56-217">Gerenciar políticas de configuração de aplicativo no Teams</span><span class="sxs-lookup"><span data-stu-id="9dc56-217">Manage app setup policies in Teams</span></span>](teams-app-setup-policies.md)
- [<span data-ttu-id="9dc56-218">Gerenciar políticas de aplicativo personalizado e as configurações no Teams</span><span class="sxs-lookup"><span data-stu-id="9dc56-218">Manage custom app policies and settings in Teams</span></span>](teams-custom-app-policies-and-settings.md)
