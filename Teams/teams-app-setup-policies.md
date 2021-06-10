---
title: Gerenciar políticas de configuração de aplicativo no Microsoft Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.reviewer: rarang
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
description: Saiba como usar e gerenciar políticas de configuração de aplicativos Microsoft Teams para usuários em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: ebfcff8ce7215e34e3c17e9c09f3a56d249d5b40
ms.sourcegitcommit: 1ee9b1857f472a5b95352f7471c0cf21be6ea0c3
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2021
ms.locfileid: "52059195"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="453b7-103">Gerenciar políticas de configuração de aplicativo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="453b7-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="453b7-104">Como administrador, você pode usar políticas de configuração de aplicativo para realizar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="453b7-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="453b7-105">Personalize o Teams para destacar os aplicativos mais importantes para os usuários.</span><span class="sxs-lookup"><span data-stu-id="453b7-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="453b7-106">Escolha os aplicativos para fixar e definir a ordem que eles aparecem.</span><span class="sxs-lookup"><span data-stu-id="453b7-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="453b7-107">Fixar aplicativos permite que você mostre aplicativos que os usuários em sua organização precisam, incluindo aplicativos construídos por terceiros ou por desenvolvedores em sua organização.</span><span class="sxs-lookup"><span data-stu-id="453b7-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="453b7-108">Controle se os usuários podem fixar aplicativos no Teams.</span><span class="sxs-lookup"><span data-stu-id="453b7-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="453b7-109">Instale aplicativos em nome dos usuários.</span><span class="sxs-lookup"><span data-stu-id="453b7-109">Install apps on behalf of users.</span></span> <span data-ttu-id="453b7-110">Você escolhe quais aplicativos são instalados por padrão para os usuários quando eles começam a Teams.</span><span class="sxs-lookup"><span data-stu-id="453b7-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="453b7-111">Lembre-se de que os usuários [](teams-app-permission-policies.md) ainda podem instalar aplicativos por conta própria se a política de permissão do aplicativo atribuída a eles permitir isso.</span><span class="sxs-lookup"><span data-stu-id="453b7-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="453b7-112">Para aplicativos instalados por administradores, os usuários não podem desinstalar esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="453b7-112">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="453b7-113">Os aplicativos são fixados na barra de aplicativos, que é a barra no lado do cliente da área de trabalho Teams e na parte inferior dos clientes móveis do Teams (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="453b7-113">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="453b7-114">Teams da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="453b7-114">Teams desktop client</span></span>  |<span data-ttu-id="453b7-115">Cliente de dispositivo móvel do Teams</span><span class="sxs-lookup"><span data-stu-id="453b7-115">Teams mobile client</span></span> |
|---------|---------|
|![O Teams da área de trabalho](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![O Teams cliente móvel](media/mobile-app-ui.png)      |

<span data-ttu-id="453b7-118">Para ver os aplicativos instalados pelos administradores, na barra de aplicativos, os usuários selecionam **... Mais aplicativos** no Teams da área de trabalho e da Web e passar o dedo para cima nos clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="453b7-118">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="453b7-119">Você gerencia políticas de configuração de aplicativos no Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="453b7-119">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="453b7-120">Use a política global (padrão em toda a organização) ou crie e atribua políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="453b7-120">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="453b7-121">Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="453b7-121">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="453b7-122">Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.</span><span class="sxs-lookup"><span data-stu-id="453b7-122">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="453b7-123">Edite as configurações na política global para incluir os aplicativos que deseja.</span><span class="sxs-lookup"><span data-stu-id="453b7-123">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="453b7-124">Para personalizar Teams diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="453b7-124">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![a página Políticas de configuração de aplicativo](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="453b7-126">Se você tiver Teams para Educação, é importante saber que o aplicativo Assignments está fixado por padrão na política global, mesmo que no momento, você não o veja listado na política global.</span><span class="sxs-lookup"><span data-stu-id="453b7-126">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="453b7-127">Ele será o quarto aplicativo na lista de aplicativos fixados Teams clientes.</span><span class="sxs-lookup"><span data-stu-id="453b7-127">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="453b7-128">Criar uma política de configuração de aplicativo personalizada</span><span class="sxs-lookup"><span data-stu-id="453b7-128">Create a custom app setup policy</span></span>

<span data-ttu-id="453b7-129">Você pode usar o Microsoft Teams de administração para criar uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="453b7-129">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="453b7-130">Na navegação à esquerda do centro de administração Microsoft Teams, vá **para** Teams políticas  >  **de Instalação de aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="453b7-130">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="453b7-131">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="453b7-131">Select **Add**.</span></span>

   ![a página Adicionar políticas de configuração de aplicativo](media/app-setup-policies-add.png)

3. <span data-ttu-id="453b7-133">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="453b7-133">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="453b7-134">Ativar ou desativar Upload **aplicativos** personalizados, dependendo se você deseja permitir que os usuários carreguem aplicativos personalizados para Teams.</span><span class="sxs-lookup"><span data-stu-id="453b7-134">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="453b7-135">Você não poderá alterar essa configuração se **Permitir** que aplicativos de terceiros estão desligados em [configurações de aplicativos](manage-apps.md#manage-org-wide-app-settings)em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="453b7-135">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="453b7-136">Ativar ou desativar **Permitir** fixação do usuário, dependendo se você deseja permitir que os usuários personalizem sua barra de aplicativos fixando aplicativos a ela.</span><span class="sxs-lookup"><span data-stu-id="453b7-136">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="453b7-137">A **configuração** Permitir fixação do usuário está disponível no centro de administração do Teams em ambientes Microsoft 365 Nuvem da Comunidade Governamental (GCC) (GCC, GCC Alto e DoD), mas atualmente não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="453b7-137">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="453b7-138">Para instalar aplicativos para usuários, faça as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="453b7-138">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="453b7-139">Em **Aplicativos Instalados,** selecione **Adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="453b7-139">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="453b7-140">No painel **Adicionar aplicativos instalados,** pesquise os aplicativos que você deseja instalar automaticamente para os usuários quando eles começarem a Teams.</span><span class="sxs-lookup"><span data-stu-id="453b7-140">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="453b7-141">Você também pode filtrar aplicativos por política de permissão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="453b7-141">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="453b7-142">Quando você escolher sua lista de aplicativos, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="453b7-142">When you've chosen your list of apps, select **Add**.</span></span>

       ![o painel Adicionar aplicativos instalados](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="453b7-144">Para fixar aplicativos, faça as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="453b7-144">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="453b7-145">Em **Aplicativos Fixados,** selecione **Adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="453b7-145">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="453b7-146">No painel **Adicionar aplicativos fixados,** pesquise os aplicativos que você deseja adicionar e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="453b7-146">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="453b7-147">Você também pode filtrar aplicativos por política de permissão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="453b7-147">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="453b7-148">Quando você escolheu sua lista de aplicativos a fixar, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="453b7-148">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![o painel Adicionar aplicativos fixados](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="453b7-150">Organize os aplicativos na ordem que você deseja que eles apareçam no Teams e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="453b7-150">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![a seção Aplicativos fixados](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="453b7-152">Editar uma política de configuração de aplicativo</span><span class="sxs-lookup"><span data-stu-id="453b7-152">Edit an app setup policy</span></span>

<span data-ttu-id="453b7-153">Você pode usar o Microsoft Teams de administração para editar uma política, incluindo a política global (padrão em toda a organização) e as políticas personalizadas que você criar.</span><span class="sxs-lookup"><span data-stu-id="453b7-153">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="453b7-154">Na navegação à esquerda do centro de administração Microsoft Teams, vá **para** Teams políticas  >  **de Instalação de aplicativos.**</span><span class="sxs-lookup"><span data-stu-id="453b7-154">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="453b7-155">Escolha a política clicando à esquerda do nome da política e selecionando **Editar**.</span><span class="sxs-lookup"><span data-stu-id="453b7-155">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="453b7-156">A partir daqui, faça as alterações desejadas.</span><span class="sxs-lookup"><span data-stu-id="453b7-156">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="453b7-157">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="453b7-157">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="453b7-158">Atribuir uma política de configuração de aplicativo personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="453b7-158">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="453b7-159">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="453b7-159">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="453b7-160">Trabalhar com políticas de configuração de aplicativos</span><span class="sxs-lookup"><span data-stu-id="453b7-160">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="453b7-161">Quais políticas internas de configuração de aplicativos estão incluídas no centro de Microsoft Teams de administração</span><span class="sxs-lookup"><span data-stu-id="453b7-161">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="453b7-162">**Global (padrão em toda a organização)**: Essa política padrão se aplica a todos os usuários em sua organização, a menos que você atribua outra política.</span><span class="sxs-lookup"><span data-stu-id="453b7-162">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="453b7-163">Edite a política global para fixar aplicativos que são mais importantes para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="453b7-163">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="453b7-164">**FrontlineWorker**: Esta política é para Trabalhadores de Linha de Frente.</span><span class="sxs-lookup"><span data-stu-id="453b7-164">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="453b7-165">Você pode atribuí-lo aos Trabalhadores de Linha de Frente em sua organização.</span><span class="sxs-lookup"><span data-stu-id="453b7-165">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="453b7-166">É importante saber que, como políticas personalizadas que você cria, você precisa atribuir a política aos usuários para que as configurações sejam ativas.</span><span class="sxs-lookup"><span data-stu-id="453b7-166">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="453b7-167">Para obter mais informações, acesse a seção Atribuir uma política de configuração [de aplicativo personalizada aos](#assign-a-custom-app-setup-policy-to-users) usuários deste artigo.</span><span class="sxs-lookup"><span data-stu-id="453b7-167">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="453b7-168">Por que não consigo encontrar um aplicativo no painel Adicionar aplicativos fixados</span><span class="sxs-lookup"><span data-stu-id="453b7-168">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="453b7-169">Nem todos os aplicativos podem ser fixados Teams por meio de uma política de configuração de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="453b7-169">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="453b7-170">Alguns aplicativos podem não dar suporte a essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="453b7-170">Some apps may not support this functionality.</span></span> <span data-ttu-id="453b7-171">Para encontrar aplicativos que podem ser fixados, pesquise o aplicativo no painel **Adicionar aplicativos** fixados.</span><span class="sxs-lookup"><span data-stu-id="453b7-171">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="453b7-172">Guias com escopo pessoal (guias estáticas) e bots podem ser fixados no cliente da área de trabalho Teams e esses aplicativos estão disponíveis no painel **Adicionar** aplicativos fixados.</span><span class="sxs-lookup"><span data-stu-id="453b7-172">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="453b7-173">Lembre-se de que o Teams de aplicativos lista todos os Teams aplicativos.</span><span class="sxs-lookup"><span data-stu-id="453b7-173">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="453b7-174">O **painel Adicionar aplicativos** fixados inclui apenas aplicativos que podem ser fixados Teams por meio de uma política.</span><span class="sxs-lookup"><span data-stu-id="453b7-174">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="453b7-175">Sou um administrador Teams educação. O que preciso saber sobre políticas de configuração de aplicativos no Teams Education</span><span class="sxs-lookup"><span data-stu-id="453b7-175">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="453b7-176">O aplicativo Chamar não está disponível no Teams education.</span><span class="sxs-lookup"><span data-stu-id="453b7-176">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="453b7-177">Quando você cria uma nova política de configuração de aplicativo personalizada, o aplicativo De chamada é exibido na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="453b7-177">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="453b7-178">No entanto, o aplicativo não está fixado em clientes Teams e Teams usuários do Education não verão o aplicativo Chamadas no Teams.</span><span class="sxs-lookup"><span data-stu-id="453b7-178">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="453b7-179">Quantos aplicativos fixados podem ser adicionados a uma política</span><span class="sxs-lookup"><span data-stu-id="453b7-179">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="453b7-180">Um mínimo de dois aplicativos deve ser fixado nos clientes Teams móveis (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="453b7-180">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="453b7-181">Se uma política tiver menos de dois aplicativos, os clientes móveis não refletirão as configurações de política e, em vez disso, continuarão a usar a configuração existente.</span><span class="sxs-lookup"><span data-stu-id="453b7-181">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="453b7-182">Não há limite para o número de aplicativos fixados que você pode adicionar a uma política.</span><span class="sxs-lookup"><span data-stu-id="453b7-182">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="453b7-183">Quanto tempo leva para que as alterações de política entre em vigor</span><span class="sxs-lookup"><span data-stu-id="453b7-183">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="453b7-184">Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="453b7-184">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="453b7-185">Experiência de usuário</span><span class="sxs-lookup"><span data-stu-id="453b7-185">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="453b7-186">Como os usuários podem ver todos os aplicativos fixados no Teams</span><span class="sxs-lookup"><span data-stu-id="453b7-186">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="453b7-187">Para exibir todos os aplicativos fixados para um usuário, os usuários podem ter que fazer o seguinte, dependendo do número de aplicativos instalados e do tamanho da janela do cliente Teams.</span><span class="sxs-lookup"><span data-stu-id="453b7-187">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="453b7-188">Teams da área de trabalho</span><span class="sxs-lookup"><span data-stu-id="453b7-188">Teams desktop client</span></span> |<span data-ttu-id="453b7-189">Cliente de dispositivo móvel do Teams</span><span class="sxs-lookup"><span data-stu-id="453b7-189">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="453b7-190">Na barra de aplicativos ao lado do Teams, selecione **... Mais aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="453b7-190">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="453b7-191">Na barra de aplicativos próxima à parte inferior Teams, passe o dedo para cima.</span><span class="sxs-lookup"><span data-stu-id="453b7-191">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Mais aplicativos no cliente Teams área de trabalho](media/app-setup-policies-desktop-more-apps.png)<br>   |![mais aplicativos no cliente Teams celular](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="453b7-194">O que preciso saber sobre a experiência Teams celular</span><span class="sxs-lookup"><span data-stu-id="453b7-194">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="453b7-195">Os Teams móveis (iOS e Android) suportam aplicativos pessoais com guias estáticas.</span><span class="sxs-lookup"><span data-stu-id="453b7-195">The Teams mobile clients (iOS and Android) support personal apps with static tabs.</span></span> <span data-ttu-id="453b7-196">Os aplicativos fixados no Teams da área de trabalho serão exibidos no Teams móveis.</span><span class="sxs-lookup"><span data-stu-id="453b7-196">Apps pinned to the Teams desktop client will appear in the Teams mobile clients.</span></span> <span data-ttu-id="453b7-197">Bots pessoais aparecerão em Chat em clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="453b7-197">Personal bots will appear in Chat on mobile clients.</span></span>

<span data-ttu-id="453b7-198">Aplicativos de terceiros (que podem ser baixados da Teams Store) precisam ser aprovados antes de aparecerem no celular.</span><span class="sxs-lookup"><span data-stu-id="453b7-198">Third-party apps (which can be downloaded from Teams Store) need to be approved before they show up on mobile.</span></span> <span data-ttu-id="453b7-199">Se um administrador fixar um aplicativo, que não é aprovado pela Microsoft para Dispositivos Móveis, ele será aparecer na área de trabalho Teams, mas não aparecer no celular.</span><span class="sxs-lookup"><span data-stu-id="453b7-199">If an admin pins an app, which is unapproved by Microsoft for Mobile, it will show up on the Teams Desktop, but not show up on mobile.</span></span> <span data-ttu-id="453b7-200">Consulte [Clientes móveis para](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="453b7-200">See [Mobile clients](/microsoftteams/platform/tabs/what-are-tabs#mobile-clients) for more information.</span></span>

<span data-ttu-id="453b7-201">Com os Teams móveis, os usuários verão os principais Teams aplicativos, como Atividade, Chat e Teams, e você poderá fixar alguns aplicativos de primeira parte da Microsoft, como Shifts.</span><span class="sxs-lookup"><span data-stu-id="453b7-201">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="453b7-202">Os usuários podem alterar a ordem dos aplicativos fixados por meio de uma política</span><span class="sxs-lookup"><span data-stu-id="453b7-202">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="453b7-203">Os usuários podem alterar a ordem de seus aplicativos fixados Teams clientes móveis e desktop se a opção Permitir que o **pinning** do usuário seja ligado.</span><span class="sxs-lookup"><span data-stu-id="453b7-203">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="453b7-204">Os usuários não podem alterar a ordem de seus aplicativos fixados em Teams web.</span><span class="sxs-lookup"><span data-stu-id="453b7-204">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="453b7-205">O pinamento do usuário tem precedência</span><span class="sxs-lookup"><span data-stu-id="453b7-205">Does user pinning take precedence</span></span>

<span data-ttu-id="453b7-206">Os pinos de administrador sempre têm precedência.</span><span class="sxs-lookup"><span data-stu-id="453b7-206">Admin pins always take precedence.</span></span> <span data-ttu-id="453b7-207">Se a **opção Permitir que o pinamento do** usuário estiver ligado, os usuários manterão seus aplicativos fixados abaixo dos aplicativos fixados pelo administrador.</span><span class="sxs-lookup"><span data-stu-id="453b7-207">If the **Allow user pinning** option is turned on, then users will retain their pinned apps below admin pinned apps.</span></span> <span data-ttu-id="453b7-208">Se a **opção Permitir fixação** do usuário estiver desabilitada, os usuários perderão seus pinos pré-existentes e somente aplicativos fixados por administrador estarão presentes na barra de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="453b7-208">If the **Allow user pinning** option is turned off, then users will lose their pre-existing pins, and only admin-pinned apps will be present in the app bar.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="453b7-209">Aplicativos Teams personalizados</span><span class="sxs-lookup"><span data-stu-id="453b7-209">Custom Teams apps</span></span>

<span data-ttu-id="453b7-210">Minha organização criou um aplicativo Teams personalizado e o publicou, no AppSource ou no catálogo de aplicativos de locatários, mas o ícone do aplicativo não é exibido como esperado quando o aplicativo é fixado na barra de aplicativos em Teams.</span><span class="sxs-lookup"><span data-stu-id="453b7-210">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="453b7-211">Como posso corrigi-lo</span><span class="sxs-lookup"><span data-stu-id="453b7-211">How do I fix it</span></span>

<span data-ttu-id="453b7-212">Certifique-se de seguir as diretrizes de logotipo antes de enviar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="453b7-212">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="453b7-213">Para saber mais, consulte [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span><span class="sxs-lookup"><span data-stu-id="453b7-213">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="453b7-214">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="453b7-214">Related topics</span></span>

[<span data-ttu-id="453b7-215">Configurações de administrador para aplicativos no Teams</span><span class="sxs-lookup"><span data-stu-id="453b7-215">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="453b7-216">Atribua políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="453b7-216">Assign policies to your users in Teams</span></span>](assign-policies.md)
