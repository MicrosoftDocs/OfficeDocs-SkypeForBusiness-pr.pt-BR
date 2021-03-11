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
description: Saiba como usar e gerenciar políticas de configuração de aplicativos no Microsoft Teams para usuários em sua organização.
f1.keywords:
- CSH
ms.custom:
- ms.teamsadmincenter.appsetuppolicies.overview
ms.openlocfilehash: a58cbf682760249ee3b269d1765a265cc58d3022
ms.sourcegitcommit: 31a585cc0fe6350efacf3a7771d1e590d5e4233c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/10/2021
ms.locfileid: "50615087"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="38e98-103">Gerenciar políticas de configuração de aplicativo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38e98-103">Manage app setup policies in Microsoft Teams</span></span>

> [!NOTE]
> <span data-ttu-id="38e98-104">Se você habilitar a configuração de aplicativo em toda a **organização,** Permitir interação com aplicativos personalizados, talvez ainda não veja políticas de configuração de aplicativos no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-104">If you enabled the org-wide app setting, **Allow interaction with custom apps**, you might not see app setup policies yet in the Microsoft Teams admin center.</span></span> <span data-ttu-id="38e98-105">Ele está sendo lançado e estará disponível em breve em sua organização.</span><span class="sxs-lookup"><span data-stu-id="38e98-105">It's currently being rolled out and will be available soon in your organization.</span></span>

<span data-ttu-id="38e98-106">Como administrador, você pode usar políticas de configuração de aplicativo para realizar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="38e98-106">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="38e98-107">Personalize o Teams para destacar os aplicativos mais importantes para os usuários.</span><span class="sxs-lookup"><span data-stu-id="38e98-107">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="38e98-108">Escolha os aplicativos para fixar e definir a ordem que eles aparecem.</span><span class="sxs-lookup"><span data-stu-id="38e98-108">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="38e98-109">Fixar aplicativos permite que você mostre aplicativos que os usuários em sua organização precisam, incluindo aplicativos construídos por terceiros ou por desenvolvedores em sua organização.</span><span class="sxs-lookup"><span data-stu-id="38e98-109">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="38e98-110">Controle se os usuários podem fixar aplicativos no Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-110">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="38e98-111">Instale aplicativos em nome dos usuários.</span><span class="sxs-lookup"><span data-stu-id="38e98-111">Install apps on behalf of users.</span></span> <span data-ttu-id="38e98-112">Você escolhe quais aplicativos são instalados por padrão para os usuários quando eles iniciam o Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-112">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="38e98-113">Lembre-se de que os usuários [](teams-app-permission-policies.md) ainda podem instalar aplicativos por conta própria se a política de permissão do aplicativo atribuída a eles permitir isso.</span><span class="sxs-lookup"><span data-stu-id="38e98-113">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

> [!Note]
> <span data-ttu-id="38e98-114">Para aplicativos instalados por administradores, os usuários não podem desinstalar esses aplicativos.</span><span class="sxs-lookup"><span data-stu-id="38e98-114">For apps installed by admins, users can't uninstall those apps.</span></span>

<span data-ttu-id="38e98-115">Os aplicativos são fixados na barra de aplicativos, que é a barra no lado do cliente da área de trabalho do Teams e na parte inferior dos clientes móveis do Teams (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="38e98-115">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="38e98-116">Cliente de área de trabalho do Teams</span><span class="sxs-lookup"><span data-stu-id="38e98-116">Teams desktop client</span></span>  |<span data-ttu-id="38e98-117">Cliente de dispositivo móvel do Teams</span><span class="sxs-lookup"><span data-stu-id="38e98-117">Teams mobile client</span></span> |
|---------|---------|
|![O cliente de área de trabalho do Teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![O cliente móvel do Teams](media/mobile-app-ui.png)      |

<span data-ttu-id="38e98-120">Para ver os aplicativos instalados pelos administradores, na barra de aplicativos, os usuários selecionam **... Mais aplicativos** na área de trabalho e clientes Web do Teams e passe o dedo para cima nos clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="38e98-120">To see the apps installed by admins, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="38e98-121">Você gerencia políticas de configuração de aplicativos no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-121">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="38e98-122">Use a política global (padrão em toda a organização) ou crie e atribua políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="38e98-122">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="38e98-123">Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="38e98-123">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="38e98-124">Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.</span><span class="sxs-lookup"><span data-stu-id="38e98-124">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="38e98-125">Edite as configurações na política global para incluir os aplicativos que deseja.</span><span class="sxs-lookup"><span data-stu-id="38e98-125">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="38e98-126">Para personalizar o Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="38e98-126">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![a página Políticas de configuração de aplicativo](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="38e98-128">Se você tiver o Teams for Education, é importante saber que o aplicativo Assignments está fixado por padrão na política global, mesmo que no momento, você não o veja listado na política global.</span><span class="sxs-lookup"><span data-stu-id="38e98-128">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="38e98-129">Ele será o quarto aplicativo na lista de aplicativos fixados em clientes do Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-129">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="38e98-130">Criar uma política de configuração de aplicativo personalizada</span><span class="sxs-lookup"><span data-stu-id="38e98-130">Create a custom app setup policy</span></span>

<span data-ttu-id="38e98-131">Você pode usar o Centro de administração do Microsoft Teams para criar uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="38e98-131">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="38e98-132">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para Políticas de Instalação de **aplicativos**  >  **do** Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-132">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="38e98-133">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="38e98-133">Select **Add**.</span></span>

   ![a página Adicionar políticas de configuração de aplicativo](media/app-setup-policies-add.png)

3. <span data-ttu-id="38e98-135">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="38e98-135">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="38e98-136">Ativar ou desativar **Carregar aplicativos** personalizados, dependendo se você deseja permitir que os usuários carreguem aplicativos personalizados no Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-136">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="38e98-137">Você não poderá alterar essa configuração se **Permitir** que aplicativos de terceiros estão desligados em [configurações de aplicativos](manage-apps.md#manage-org-wide-app-settings)em toda a organização.</span><span class="sxs-lookup"><span data-stu-id="38e98-137">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="38e98-138">Ativar ou desativar **Permitir** fixação do usuário, dependendo se você deseja permitir que os usuários personalizem sua barra de aplicativos fixando aplicativos a ela.</span><span class="sxs-lookup"><span data-stu-id="38e98-138">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="38e98-139">A  configuração Permitir fixação do usuário está disponível no Centro de administração do Teams nos ambientes do Microsoft 365 Government Community Cloud (GCC) (GCC, GCC High e DoD), mas atualmente não tem efeito.</span><span class="sxs-lookup"><span data-stu-id="38e98-139">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="38e98-140">Para instalar aplicativos para usuários, faça as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="38e98-140">To install apps for users, do the following tasks:</span></span>

    1. <span data-ttu-id="38e98-141">Em **Aplicativos Instalados,** selecione **Adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="38e98-141">Under **Installed apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="38e98-142">No painel **Adicionar aplicativos instalados,** pesquise os aplicativos que você deseja instalar automaticamente para os usuários quando iniciarem o Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-142">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="38e98-143">Você também pode filtrar aplicativos por política de permissão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="38e98-143">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="38e98-144">Quando você escolher sua lista de aplicativos, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="38e98-144">When you've chosen your list of apps, select **Add**.</span></span>

       ![o painel Adicionar aplicativos instalados](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="38e98-146">Para fixar aplicativos, faça as seguintes etapas:</span><span class="sxs-lookup"><span data-stu-id="38e98-146">To pin apps, do the following steps:</span></span>

    1. <span data-ttu-id="38e98-147">Em **Aplicativos Fixados,** selecione **Adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="38e98-147">Under **Pinned apps**, select **Add apps**.</span></span>

    2. <span data-ttu-id="38e98-148">No painel **Adicionar aplicativos fixados,** pesquise os aplicativos que você deseja adicionar e selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="38e98-148">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="38e98-149">Você também pode filtrar aplicativos por política de permissão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="38e98-149">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="38e98-150">Quando você escolheu sua lista de aplicativos a fixar, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="38e98-150">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![o painel Adicionar aplicativos fixados](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="38e98-152">Organize os aplicativos na ordem que você deseja que eles apareçam no Teams e selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="38e98-152">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![a seção Aplicativos fixados](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="38e98-154">Editar uma política de configuração de aplicativo</span><span class="sxs-lookup"><span data-stu-id="38e98-154">Edit an app setup policy</span></span>

<span data-ttu-id="38e98-155">Você pode usar o Centro de administração do Microsoft Teams para editar uma política, incluindo a política global (padrão em toda a organização) e as políticas personalizadas que você cria.</span><span class="sxs-lookup"><span data-stu-id="38e98-155">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="38e98-156">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para Políticas de Instalação de **aplicativos**  >  **do** Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-156">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="38e98-157">Escolha a política clicando à esquerda do nome da política e selecionando **Editar**.</span><span class="sxs-lookup"><span data-stu-id="38e98-157">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="38e98-158">A partir daqui, faça as alterações desejadas.</span><span class="sxs-lookup"><span data-stu-id="38e98-158">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="38e98-159">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="38e98-159">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="38e98-160">Atribuir uma política de configuração de aplicativo personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="38e98-160">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="38e98-161">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="38e98-161">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="38e98-162">Trabalhar com políticas de configuração de aplicativos</span><span class="sxs-lookup"><span data-stu-id="38e98-162">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="38e98-163">Quais políticas internas de configuração de aplicativos estão incluídas no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="38e98-163">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="38e98-164">**Global (padrão em toda a organização)**: Essa política padrão se aplica a todos os usuários em sua organização, a menos que você atribua outra política.</span><span class="sxs-lookup"><span data-stu-id="38e98-164">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="38e98-165">Edite a política global para fixar aplicativos que são mais importantes para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="38e98-165">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="38e98-166">**FrontlineWorker**: Esta política é para Trabalhadores de Linha de Frente.</span><span class="sxs-lookup"><span data-stu-id="38e98-166">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="38e98-167">Você pode atribuí-lo aos Trabalhadores de Linha de Frente em sua organização.</span><span class="sxs-lookup"><span data-stu-id="38e98-167">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="38e98-168">É importante saber que, como políticas personalizadas que você cria, você precisa atribuir a política aos usuários para que as configurações sejam ativas.</span><span class="sxs-lookup"><span data-stu-id="38e98-168">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="38e98-169">Para obter mais informações, acesse a seção Atribuir uma política de configuração [de aplicativo personalizada aos](#assign-a-custom-app-setup-policy-to-users) usuários deste artigo.</span><span class="sxs-lookup"><span data-stu-id="38e98-169">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="38e98-170">Por que não consigo encontrar um aplicativo no painel Adicionar aplicativos fixados</span><span class="sxs-lookup"><span data-stu-id="38e98-170">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="38e98-171">Nem todos os aplicativos podem ser fixados no Teams por meio de uma política de configuração de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="38e98-171">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="38e98-172">Alguns aplicativos podem não dar suporte a essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="38e98-172">Some apps may not support this functionality.</span></span> <span data-ttu-id="38e98-173">Para encontrar aplicativos que podem ser fixados, pesquise o aplicativo no painel **Adicionar aplicativos** fixados.</span><span class="sxs-lookup"><span data-stu-id="38e98-173">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="38e98-174">Guias com escopo pessoal (guias estáticas) e bots podem ser fixados no cliente da área de trabalho do Teams e esses aplicativos estão disponíveis no painel **Adicionar** aplicativos fixados.</span><span class="sxs-lookup"><span data-stu-id="38e98-174">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="38e98-175">Lembre-se de que a loja de aplicativos do Teams lista todos os aplicativos do Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-175">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="38e98-176">O **painel Adicionar aplicativos** fixados inclui apenas aplicativos que podem ser fixados no Teams por meio de uma política.</span><span class="sxs-lookup"><span data-stu-id="38e98-176">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="38e98-177">Sou administrador do Teams for Education. O que preciso saber sobre políticas de configuração de aplicativos no Teams for Education</span><span class="sxs-lookup"><span data-stu-id="38e98-177">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="38e98-178">O aplicativo De chamada não está disponível no Teams for Education.</span><span class="sxs-lookup"><span data-stu-id="38e98-178">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="38e98-179">Quando você cria uma nova política de configuração de aplicativo personalizada, o aplicativo De chamada é exibido na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="38e98-179">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="38e98-180">No entanto, o aplicativo não está fixado aos clientes do Teams e os usuários do Teams para Educação não verão o aplicativo Chamadas no Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-180">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="38e98-181">Quantos aplicativos fixados podem ser adicionados a uma política</span><span class="sxs-lookup"><span data-stu-id="38e98-181">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="38e98-182">Um mínimo de dois aplicativos deve ser fixado nos clientes móveis do Teams (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="38e98-182">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="38e98-183">Se uma política tiver menos de dois aplicativos, os clientes móveis não refletirão as configurações de política e, em vez disso, continuarão a usar a configuração existente.</span><span class="sxs-lookup"><span data-stu-id="38e98-183">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="38e98-184">Não há limite para o número de aplicativos fixados que você pode adicionar a uma política.</span><span class="sxs-lookup"><span data-stu-id="38e98-184">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="38e98-185">Quanto tempo leva para que as alterações de política entre em vigor</span><span class="sxs-lookup"><span data-stu-id="38e98-185">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="38e98-186">Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="38e98-186">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="38e98-187">Experiência de usuário</span><span class="sxs-lookup"><span data-stu-id="38e98-187">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="38e98-188">Como os usuários podem ver todos os aplicativos fixados no Teams</span><span class="sxs-lookup"><span data-stu-id="38e98-188">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="38e98-189">Para exibir todos os aplicativos fixados para um usuário, os usuários podem ter que fazer o seguinte, dependendo do número de aplicativos instalados e do tamanho da janela do cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-189">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="38e98-190">Cliente de área de trabalho do Teams</span><span class="sxs-lookup"><span data-stu-id="38e98-190">Teams desktop client</span></span> |<span data-ttu-id="38e98-191">Cliente de dispositivo móvel do Teams</span><span class="sxs-lookup"><span data-stu-id="38e98-191">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="38e98-192">Na barra de aplicativos do lado do Teams, selecione **... Mais aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="38e98-192">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="38e98-193">Na barra de aplicativos próxima à parte inferior do Teams, passe o dedo para cima.</span><span class="sxs-lookup"><span data-stu-id="38e98-193">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Mais aplicativos no cliente de área de trabalho do Teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![mais aplicativos no cliente móvel do Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="38e98-196">O que preciso saber sobre a experiência móvel do Teams</span><span class="sxs-lookup"><span data-stu-id="38e98-196">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="38e98-197">Os clientes móveis do Teams (iOS e Android) atualmente não suportam aplicativos pessoais com guias estáticas.</span><span class="sxs-lookup"><span data-stu-id="38e98-197">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="38e98-198">Dependendo dos aplicativos definidos na política, os aplicativos fixados no cliente da área de trabalho do Teams podem não aparecer nos clientes móveis do Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-198">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="38e98-199">Os bots pessoais ainda aparecerão no Chat em clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="38e98-199">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="38e98-200">Com os clientes móveis do Teams, os usuários verão os principais aplicativos do Teams, como Atividade, Chat e Teams, e você pode fixar alguns aplicativos de primeira parte da Microsoft, como Shifts.</span><span class="sxs-lookup"><span data-stu-id="38e98-200">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="38e98-201">Os usuários podem alterar a ordem dos aplicativos fixados por meio de uma política</span><span class="sxs-lookup"><span data-stu-id="38e98-201">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="38e98-202">Os usuários podem alterar a ordem de seus aplicativos fixados na área de trabalho e nos clientes móveis do Teams se a opção Permitir que o **pinning** do usuário seja ligado.</span><span class="sxs-lookup"><span data-stu-id="38e98-202">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="38e98-203">Os usuários não podem alterar a ordem de seus aplicativos fixados em clientes Web do Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-203">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="38e98-204">O pinamento do usuário tem precedência</span><span class="sxs-lookup"><span data-stu-id="38e98-204">Does user pinning take precedence</span></span>

<span data-ttu-id="38e98-205">Se a política de configuração do aplicativo atribuída ao usuário for alterada para bloquear a fixação de aplicativos do usuário, o Teams removerá todos os aplicativos fixados na barra de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="38e98-205">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="38e98-206">Se a política for alterada para permitir o pinamento do aplicativo do usuário, os usuários devem repintar seus aplicativos fixados anteriormente.</span><span class="sxs-lookup"><span data-stu-id="38e98-206">If the policy is then changed to allow user app pinning, users must repin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="38e98-207">Aplicativos personalizados do Teams</span><span class="sxs-lookup"><span data-stu-id="38e98-207">Custom Teams apps</span></span>

<span data-ttu-id="38e98-208">Minha organização criou um aplicativo personalizado do Teams e o publicou, no AppSource ou no catálogo de aplicativos de locatários, mas o ícone do aplicativo não é exibido como esperado quando o aplicativo é fixado na barra de aplicativos no Teams.</span><span class="sxs-lookup"><span data-stu-id="38e98-208">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="38e98-209">Como posso corrigi-lo</span><span class="sxs-lookup"><span data-stu-id="38e98-209">How do I fix it</span></span>

<span data-ttu-id="38e98-210">Certifique-se de seguir as diretrizes de logotipo antes de enviar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="38e98-210">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="38e98-211">Para saber mais, consulte [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span><span class="sxs-lookup"><span data-stu-id="38e98-211">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="38e98-212">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="38e98-212">Related topics</span></span>

[<span data-ttu-id="38e98-213">Configurações de administrador para aplicativos no Teams</span><span class="sxs-lookup"><span data-stu-id="38e98-213">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="38e98-214">Atribua políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="38e98-214">Assign policies to your users in Teams</span></span>](assign-policies.md)
