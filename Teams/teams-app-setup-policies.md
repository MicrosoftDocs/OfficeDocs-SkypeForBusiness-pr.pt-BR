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
ms.openlocfilehash: ffc2f15cdbef49daf36e09ca9676925ebb1ac99e
ms.sourcegitcommit: 27bfa015413bc7742bca4ea227e0324da0c740d7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145918"
---
# <a name="manage-app-setup-policies-in-microsoft-teams"></a><span data-ttu-id="2bb27-103">Gerenciar políticas de configuração de aplicativo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2bb27-103">Manage app setup policies in Microsoft Teams</span></span>

<span data-ttu-id="2bb27-104">Como administrador, você pode usar políticas de configuração do aplicativo para realizar as seguintes tarefas:</span><span class="sxs-lookup"><span data-stu-id="2bb27-104">As an admin, you can use app setup policies to do the following tasks:</span></span>

- <span data-ttu-id="2bb27-105">Personalize o Teams para destacar os aplicativos mais importantes para os usuários.</span><span class="sxs-lookup"><span data-stu-id="2bb27-105">Customize Teams to highlight the apps that are most important for your users.</span></span> <span data-ttu-id="2bb27-106">Você escolhe os aplicativos para fixar e define a ordem em que eles aparecem.</span><span class="sxs-lookup"><span data-stu-id="2bb27-106">You choose the apps to pin and set the order that they appear.</span></span> <span data-ttu-id="2bb27-107">Fixar aplicativos permite que você exporte aplicativos que os usuários da sua organização precisam, incluindo aplicativos criados por terceiros ou por desenvolvedores em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2bb27-107">Pinning apps lets you showcase apps that users in your organization need, including apps built by third parties or by developers in your organization.</span></span>
- <span data-ttu-id="2bb27-108">Controle se os usuários podem fixar aplicativos no Teams.</span><span class="sxs-lookup"><span data-stu-id="2bb27-108">Control whether users can pin apps to Teams.</span></span>
- <span data-ttu-id="2bb27-109">Instale aplicativos em nome dos usuários **(na visualização)**.</span><span class="sxs-lookup"><span data-stu-id="2bb27-109">Install apps on behalf of users **(in preview)**.</span></span> <span data-ttu-id="2bb27-110">Você escolhe quais aplicativos são instalados por padrão para os usuários quando eles iniciam o Teams.</span><span class="sxs-lookup"><span data-stu-id="2bb27-110">You choose which apps are installed by default for users when they start Teams.</span></span> <span data-ttu-id="2bb27-111">Lembre-se de que os usuários ainda poderão instalar os próprios aplicativos se a [política de permissão do aplicativo](teams-app-permission-policies.md) atribuída a ele permitir.</span><span class="sxs-lookup"><span data-stu-id="2bb27-111">Keep in mind that users can still install apps themselves if the [app permission policy](teams-app-permission-policies.md) that's assigned to them allows it.</span></span>

<span data-ttu-id="2bb27-112">Os aplicativos são fixados na barra de aplicativos, que é a barra do lado do cliente de desktop Teams e na parte inferior dos clientes móveis do Teams (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="2bb27-112">Apps are pinned to the app bar, which is the bar on the side of the Teams desktop client and at the bottom of the Teams mobile clients (iOS and Android).</span></span>

|<span data-ttu-id="2bb27-113">Cliente de desktop Teams</span><span class="sxs-lookup"><span data-stu-id="2bb27-113">Teams desktop client</span></span>  |<span data-ttu-id="2bb27-114">Cliente de dispositivo móvel do Teams</span><span class="sxs-lookup"><span data-stu-id="2bb27-114">Teams mobile client</span></span> |
|---------|---------|
|![O cliente da área de trabalho do teams](media/app-setup-policies-desktop-app-bar.png)<br>  |   ![O cliente móvel do teams](media/mobile-app-ui.png)      |

<span data-ttu-id="2bb27-117">Para ver seus aplicativos pré-instalados, na barra de aplicativos, os usuários selecionam **... Mais aplicativos** na área de trabalho da equipe e nos clientes Web e passe o dedo para cima nos clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="2bb27-117">To see their pre-installed apps, in the app bar, users select **... More apps** in the Teams desktop and web clients and swipe up in the mobile clients.</span></span>

<span data-ttu-id="2bb27-118">Você gerencia as políticas de configuração do aplicativo no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2bb27-118">You manage app setup policies in the Microsoft Teams admin center.</span></span> <span data-ttu-id="2bb27-119">Use a política global (padrão para toda a organização) ou crie e atribua políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2bb27-119">Use the global (Org-wide default) policy or create and assign custom policies.</span></span>  <span data-ttu-id="2bb27-120">Os usuários em sua organização obterão automaticamente a política global, a menos que você crie e atribua uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="2bb27-120">Users in your organization will automatically get the global policy unless you create and assign a custom policy.</span></span> <span data-ttu-id="2bb27-121">Você deve ser um administrador global ou administrador de serviços do Teams para gerenciar essas políticas.</span><span class="sxs-lookup"><span data-stu-id="2bb27-121">You must be a global admin or Teams service admin to manage these policies.</span></span>

<span data-ttu-id="2bb27-122">Edite as configurações da política global para incluir os aplicativos desejados.</span><span class="sxs-lookup"><span data-stu-id="2bb27-122">You edit the settings in the global policy to include the apps that you want.</span></span> <span data-ttu-id="2bb27-123">Para personalizar o Microsoft Teams para diferentes grupos de usuários em sua organização, crie e atribua uma ou mais políticas personalizadas.</span><span class="sxs-lookup"><span data-stu-id="2bb27-123">To customize Teams for different groups of users in your organization, create and assign one or more custom policies.</span></span>

![a página de políticas de configuração de aplicativos](media/app-setup-policies.png)

> [!NOTE]
> <span data-ttu-id="2bb27-125">Se você tiver equipes para educação, é importante saber que o aplicativo de atribuições está fixado por padrão na política global, ainda que, no momento, você não a veja listado na política global.</span><span class="sxs-lookup"><span data-stu-id="2bb27-125">If you have Teams for Education, it's important to know that the Assignments app is pinned by default in the global policy even though currently, you don't see it listed in the global policy.</span></span> <span data-ttu-id="2bb27-126">Será o quarto aplicativo na lista de aplicativos fixos em clientes do teams.</span><span class="sxs-lookup"><span data-stu-id="2bb27-126">It will be the fourth app in the list of pinned apps on Teams clients.</span></span>

## <a name="create-a-custom-app-setup-policy"></a><span data-ttu-id="2bb27-127">Criar uma política de configuração de aplicativo personalizada</span><span class="sxs-lookup"><span data-stu-id="2bb27-127">Create a custom app setup policy</span></span>

<span data-ttu-id="2bb27-128">Você pode usar o centro de administração do Microsoft Teams para criar uma política personalizada.</span><span class="sxs-lookup"><span data-stu-id="2bb27-128">You can use the Microsoft Teams admin center to create a custom policy.</span></span>

1. <span data-ttu-id="2bb27-129">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de configuração de **aplicativos do teams**  >  .</span><span class="sxs-lookup"><span data-stu-id="2bb27-129">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="2bb27-130">Selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2bb27-130">Select **Add**.</span></span>

   ![a página Adicionar políticas de configuração de aplicativos](media/app-setup-policies-add.png)
    
3. <span data-ttu-id="2bb27-132">Insira um nome e uma descrição para a política.</span><span class="sxs-lookup"><span data-stu-id="2bb27-132">Enter a name and description for the policy.</span></span>

4. <span data-ttu-id="2bb27-133">Ative ou desative **carregar aplicativos personalizados**, dependendo se você deseja permitir que os usuários carreguem aplicativos personalizados para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2bb27-133">Turn on or turn off **Upload custom apps**, depending on whether you want to let users upload custom apps to Teams.</span></span> <span data-ttu-id="2bb27-134">Você não poderá alterar essa configuração se a opção **permitir que aplicativos de terceiros** estiverem desativados em [configurações de aplicativo de toda a organização](manage-apps.md#manage-org-wide-app-settings).</span><span class="sxs-lookup"><span data-stu-id="2bb27-134">You can't change this setting if **Allow third-party apps** is turned off in [org-wide app settings](manage-apps.md#manage-org-wide-app-settings).</span></span>

5. <span data-ttu-id="2bb27-135">Ative ou desative **permitir a fixação do usuário**, dependendo se você deseja permitir que os usuários personalizem a barra de aplicativos fixando os aplicativos nela.</span><span class="sxs-lookup"><span data-stu-id="2bb27-135">Turn on or turn off **Allow user pinning**, depending on whether you want to let users personalize their app bar by pinning apps to it.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2bb27-136">A configuração **permitir fixação do usuário** está disponível no centro de administração do Microsoft 365 (GCC, gcc High e DoD), mas atualmente não tem nenhum efeito.</span><span class="sxs-lookup"><span data-stu-id="2bb27-136">The **Allow user pinning** setting is available in the Teams admin center in Microsoft 365 Government Community Cloud (GCC) environments (GCC, GCC High and DoD), but currently it has no effect.</span></span>

6. <span data-ttu-id="2bb27-137">Para instalar aplicativos para usuários **(na visualização)**, siga estas tarefas:</span><span class="sxs-lookup"><span data-stu-id="2bb27-137">To install apps for users **(in preview)**, do the following tasks:</span></span>

    1. <span data-ttu-id="2bb27-138">Em **aplicativos instalados**, selecione **adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="2bb27-138">Under **Installed apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="2bb27-139">No painel **adicionar aplicativos instalados** , procure os aplicativos que você deseja instalar automaticamente para os usuários quando eles iniciarem o Teams.</span><span class="sxs-lookup"><span data-stu-id="2bb27-139">In the **Add installed apps** pane, search for the apps you want to automatically install for users when they start Teams.</span></span> <span data-ttu-id="2bb27-140">Você também pode filtrar aplicativos por política de permissão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2bb27-140">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="2bb27-141">Depois de escolher a sua lista de aplicativos, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2bb27-141">When you've chosen your list of apps, select **Add**.</span></span>

       ![o painel Adicionar aplicativos instalados](media/app-setup-policies-add-installed-apps.png)

7. <span data-ttu-id="2bb27-143">Para fixar aplicativos, faça o seguinte:</span><span class="sxs-lookup"><span data-stu-id="2bb27-143">To pin apps, do the following:</span></span>

    1. <span data-ttu-id="2bb27-144">Em **aplicativos fixos**, selecione **adicionar aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="2bb27-144">Under **Pinned apps**, select **Add apps**.</span></span>
    
    2. <span data-ttu-id="2bb27-145">No painel **adicionar aplicativos fixos** , procure os aplicativos que você deseja adicionar e, em seguida, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2bb27-145">In the **Add pinned apps** pane, search for the apps you want to add, and then select **Add**.</span></span> <span data-ttu-id="2bb27-146">Você também pode filtrar aplicativos por política de permissão do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2bb27-146">You can also filter apps by app permission policy.</span></span> <span data-ttu-id="2bb27-147">Depois de escolher a lista de aplicativos a serem fixados, selecione **Adicionar**.</span><span class="sxs-lookup"><span data-stu-id="2bb27-147">When you've chosen your list of apps to pin, select **Add**.</span></span>

       ![o painel Adicionar aplicativos fixos](media/app-setup-policies-add-apps.png)

    3. <span data-ttu-id="2bb27-149">Organize os aplicativos na ordem em que você deseja que eles apareçam no Teams e selecione **salvar**.</span><span class="sxs-lookup"><span data-stu-id="2bb27-149">Arrange the apps in the order that you want them to appear in Teams, and then select **Save**.</span></span>

       ![a seção de aplicativos fixos](media/app-setup-policies-new-policy-setup.png)

## <a name="edit-an-app-setup-policy"></a><span data-ttu-id="2bb27-151">Editar uma política de configuração de aplicativo</span><span class="sxs-lookup"><span data-stu-id="2bb27-151">Edit an app setup policy</span></span>

<span data-ttu-id="2bb27-152">Você pode usar o centro de administração do Microsoft Teams para editar uma política, incluindo a política global (padrão de toda a organização) e políticas personalizadas que você criar.</span><span class="sxs-lookup"><span data-stu-id="2bb27-152">You can use the Microsoft Teams admin center to edit a policy, including the global (Org-wide default) policy and custom policies that you create.</span></span>

1. <span data-ttu-id="2bb27-153">Na navegação à esquerda do centro de administração do Microsoft Teams, vá para políticas de configuração de **aplicativos do teams**  >  .</span><span class="sxs-lookup"><span data-stu-id="2bb27-153">In the left navigation of the Microsoft Teams admin center, go to **Teams apps** > **Setup policies**.</span></span>

2. <span data-ttu-id="2bb27-154">Escolha a política clicando à esquerda do nome da política e selecionando **Editar**.</span><span class="sxs-lookup"><span data-stu-id="2bb27-154">Select the policy by clicking to the left of the policy name, and then select **Edit**.</span></span>

3. <span data-ttu-id="2bb27-155">A partir daqui, faça as alterações desejadas.</span><span class="sxs-lookup"><span data-stu-id="2bb27-155">From here, make the changes that you want.</span></span>

4. <span data-ttu-id="2bb27-156">Selecione **Salvar**.</span><span class="sxs-lookup"><span data-stu-id="2bb27-156">Select **Save**.</span></span>

## <a name="assign-a-custom-app-setup-policy-to-users"></a><span data-ttu-id="2bb27-157">Atribuir uma política de configuração de aplicativo personalizada aos usuários</span><span class="sxs-lookup"><span data-stu-id="2bb27-157">Assign a custom app setup policy to users</span></span>

[!INCLUDE [assign-policy](includes/assign-policy.md)]

## <a name="faq"></a><span data-ttu-id="2bb27-158">Perguntas frequentes</span><span class="sxs-lookup"><span data-stu-id="2bb27-158">FAQ</span></span>

### <a name="working-with-app-setup-policies"></a><span data-ttu-id="2bb27-159">Trabalhando com políticas de configuração de aplicativos</span><span class="sxs-lookup"><span data-stu-id="2bb27-159">Working with app setup policies</span></span>

#### <a name="what-built-in-app-setup-policies-are-included-in-the-microsoft-teams-admin-center"></a><span data-ttu-id="2bb27-160">Quais políticas de configuração de aplicativos internas estão incluídas no centro de administração do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2bb27-160">What built-in app setup policies are included in the Microsoft Teams admin center</span></span>

- <span data-ttu-id="2bb27-161">**Global (padrão para toda a organização)**: essa política padrão se aplica a todos os usuários da sua organização, a menos que você atribua outra política.</span><span class="sxs-lookup"><span data-stu-id="2bb27-161">**Global (Org-wide default)**: This default policy applies to all users in your organization unless you assign another policy.</span></span> <span data-ttu-id="2bb27-162">Edite a política global para fixar aplicativos que são mais importantes para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="2bb27-162">Edit the global policy to pin apps that are most important for your users.</span></span>

- <span data-ttu-id="2bb27-163">**FrontlineWorker**: esta política é para trabalhadores Frontline.</span><span class="sxs-lookup"><span data-stu-id="2bb27-163">**FrontlineWorker**: This policy is for Frontline Workers.</span></span> <span data-ttu-id="2bb27-164">Você pode atribuí-lo a trabalhadores do Frontline em sua organização.</span><span class="sxs-lookup"><span data-stu-id="2bb27-164">You can assign it to Frontline Workers in your organization.</span></span> <span data-ttu-id="2bb27-165">É importante saber que, assim como as políticas personalizadas que você cria, você precisa atribuir a política aos usuários para que as configurações sejam ativas.</span><span class="sxs-lookup"><span data-stu-id="2bb27-165">It's important to know that like custom policies that you create, you have to assign the policy to users for the settings to be active.</span></span> <span data-ttu-id="2bb27-166">Para obter mais informações, acesse a seção [atribuir política de configuração de aplicativo personalizada a usuários](#assign-a-custom-app-setup-policy-to-users) deste artigo.</span><span class="sxs-lookup"><span data-stu-id="2bb27-166">For more information, go to the [Assign a custom app setup policy to users](#assign-a-custom-app-setup-policy-to-users) section of this article.</span></span>

#### <a name="why-cant-i-find-an-app-in-the-add-pinned-apps-pane"></a><span data-ttu-id="2bb27-167">Por que não consigo encontrar um aplicativo no painel Adicionar aplicativos fixos</span><span class="sxs-lookup"><span data-stu-id="2bb27-167">Why can't I find an app in the Add pinned apps pane</span></span>

<span data-ttu-id="2bb27-168">Nem todos os aplicativos podem ser fixados para o Microsoft Teams por meio de uma política de configuração de aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2bb27-168">Not all apps can be pinned to Teams through an app setup policy.</span></span> <span data-ttu-id="2bb27-169">Alguns aplicativos podem não oferecer suporte a essa funcionalidade.</span><span class="sxs-lookup"><span data-stu-id="2bb27-169">Some apps may not support this functionality.</span></span> <span data-ttu-id="2bb27-170">Para localizar aplicativos que possam ser fixados, procure o aplicativo no painel **adicionar aplicativos fixos** .</span><span class="sxs-lookup"><span data-stu-id="2bb27-170">To find apps that can be pinned, search for the app in the **Add pinned apps** pane.</span></span> <span data-ttu-id="2bb27-171">As guias que têm um escopo pessoal (guias estáticos) e bots podem ser fixadas ao cliente da área de trabalho do Teams e esses aplicativos estão disponíveis no painel **adicionar aplicativos fixos** .</span><span class="sxs-lookup"><span data-stu-id="2bb27-171">Tabs that have a personal scope (static tabs) and bots can be pinned to the Teams desktop client and these apps are available in the **Add pinned apps** pane.</span></span>

<span data-ttu-id="2bb27-172">Lembre-se de que a loja de aplicativos do teams lista todos os aplicativos do teams.</span><span class="sxs-lookup"><span data-stu-id="2bb27-172">Keep in mind that the Teams app store lists all Teams apps.</span></span> <span data-ttu-id="2bb27-173">O painel **adicionar aplicativos fixos** inclui apenas aplicativos que podem ser fixados ao Teams por meio de uma política.</span><span class="sxs-lookup"><span data-stu-id="2bb27-173">The **Add pinned apps** pane includes only apps that can be pinned to Teams through a policy.</span></span>

#### <a name="im-a-teams-for-education-admin-what-do-i-need-to-know-about-app-setup-policies-in-teams-for-education"></a><span data-ttu-id="2bb27-174">Sou um administrador do Microsoft Teams para educação. O que preciso saber sobre as políticas de configuração de aplicativos no Teams for Education</span><span class="sxs-lookup"><span data-stu-id="2bb27-174">I'm a Teams for Education admin. What do I need to know about app setup policies in Teams for Education</span></span>

<span data-ttu-id="2bb27-175">O aplicativo de chamada não está disponível no Teams for Education.</span><span class="sxs-lookup"><span data-stu-id="2bb27-175">The Calling app isn't available in Teams for Education.</span></span> <span data-ttu-id="2bb27-176">Quando você cria uma nova política de configuração de aplicativo personalizada, o aplicativo de chamada é exibido na lista de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="2bb27-176">When you create a new custom app setup policy, the Calling app is displayed in the list of apps.</span></span> <span data-ttu-id="2bb27-177">No entanto, o aplicativo não está fixado a clientes do Teams e o Microsoft Teams para que os usuários de educação não vejam o aplicativo chamadas no Teams.</span><span class="sxs-lookup"><span data-stu-id="2bb27-177">However, the app isn't pinned to Teams clients and Teams for Education users won't see the Calls app in Teams.</span></span>

#### <a name="how-many-pinned-apps-can-be-added-to-a-policy"></a><span data-ttu-id="2bb27-178">Quantos aplicativos fixos podem ser adicionados a uma política</span><span class="sxs-lookup"><span data-stu-id="2bb27-178">How many pinned apps can be added to a policy</span></span>

<span data-ttu-id="2bb27-179">No mínimo dois aplicativos devem ser fixados para os clientes móveis do Teams (iOS e Android).</span><span class="sxs-lookup"><span data-stu-id="2bb27-179">A minimum of two apps must be pinned to the Teams mobile clients (iOS and Android).</span></span> <span data-ttu-id="2bb27-180">Se uma política tem menos de dois aplicativos, os clientes móveis não refletem as configurações de política e, em vez disso, continuarão a usar a configuração existente.</span><span class="sxs-lookup"><span data-stu-id="2bb27-180">If a policy has fewer than two apps, the mobile clients won't reflect the policy settings and instead will continue to use the existing configuration.</span></span>

<span data-ttu-id="2bb27-181">Não há limite quanto ao número de aplicativos fixos que você pode adicionar a uma política.</span><span class="sxs-lookup"><span data-stu-id="2bb27-181">There's no limit on the number of pinned apps you can add to a policy.</span></span>

#### <a name="how-long-does-it-take-for-policy-changes-to-take-effect"></a><span data-ttu-id="2bb27-182">Quanto tempo leva para as alterações de política entrarem em vigor</span><span class="sxs-lookup"><span data-stu-id="2bb27-182">How long does it take for policy changes to take effect</span></span>

<span data-ttu-id="2bb27-183">Depois de editar ou atribuir uma política, pode levar algumas horas para que as alterações entrem em vigor.</span><span class="sxs-lookup"><span data-stu-id="2bb27-183">After you edit or assign a policy, it can take a few hours for changes to take effect.</span></span>

### <a name="user-experience"></a><span data-ttu-id="2bb27-184">Experiência de usuário</span><span class="sxs-lookup"><span data-stu-id="2bb27-184">User experience</span></span>

#### <a name="how-can-users-see-all-their-pinned-apps-in-teams"></a><span data-ttu-id="2bb27-185">Como os usuários podem ver todos os seus aplicativos fixos no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2bb27-185">How can users see all their pinned apps in Teams</span></span>

<span data-ttu-id="2bb27-186">Para exibir todos os aplicativos que estão fixos para um usuário, talvez os usuários precisem fazer o seguinte, dependendo do número de aplicativos instalados e do tamanho da janela do cliente de suas equipes.</span><span class="sxs-lookup"><span data-stu-id="2bb27-186">To view all apps that are pinned for a user, users might have to do the following depending on the number of installed apps and the size of their Teams client window.</span></span>

|<span data-ttu-id="2bb27-187">Cliente de desktop Teams</span><span class="sxs-lookup"><span data-stu-id="2bb27-187">Teams desktop client</span></span> |<span data-ttu-id="2bb27-188">Cliente de dispositivo móvel do Teams</span><span class="sxs-lookup"><span data-stu-id="2bb27-188">Teams mobile client</span></span> |
|---------|---------|
|<span data-ttu-id="2bb27-189">Na barra de aplicativos na lateral do Teams, selecione **... Mais aplicativos**.</span><span class="sxs-lookup"><span data-stu-id="2bb27-189">In the app bar on the side of Teams, select **... More apps**.</span></span>| <span data-ttu-id="2bb27-190">Na barra do aplicativo, próxima à parte inferior do Teams, passe o dedo para cima.</span><span class="sxs-lookup"><span data-stu-id="2bb27-190">In the app bar near the bottom of Teams, swipe up.</span></span>|
|![Mais aplicativos no cliente da área de trabalho do teams](media/app-setup-policies-desktop-more-apps.png)<br>   |![mais aplicativos no cliente móvel do Microsoft Teams](media/app-setup-policies-mobile-more-apps.png)  

#### <a name="what-do-i-need-to-know-about-the-teams-mobile-experience"></a><span data-ttu-id="2bb27-193">O que preciso saber sobre a experiência móvel do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="2bb27-193">What do I need to know about the Teams mobile experience</span></span>

<span data-ttu-id="2bb27-194">Atualmente, os clientes móveis do Teams (iOS e Android) não dão suporte a aplicativos pessoais com guias estáticas.</span><span class="sxs-lookup"><span data-stu-id="2bb27-194">The Teams mobile clients (iOS and Android) currently don't support personal apps with static tabs.</span></span> <span data-ttu-id="2bb27-195">Dependendo dos aplicativos definidos na política, os aplicativos fixos no cliente da área de trabalho do teams podem não aparecer nos clientes móveis do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="2bb27-195">Depending on the apps set in the policy, apps pinned to the Teams desktop client might not appear in the Teams mobile clients.</span></span> <span data-ttu-id="2bb27-196">Os bots pessoais ainda serão exibidos em chat em clientes móveis.</span><span class="sxs-lookup"><span data-stu-id="2bb27-196">Personal bots will still appear in Chat on mobile clients.</span></span>

<span data-ttu-id="2bb27-197">Com os clientes móveis do Microsoft Teams, os usuários verão aplicativos centrais do Teams, como atividade, chat e equipes, e você poderá fixar alguns aplicativos de terceiros da Microsoft, como turnos.</span><span class="sxs-lookup"><span data-stu-id="2bb27-197">With the Teams mobile clients, users will see core Teams apps such as Activity, Chat, and Teams, and you can pin some first-party apps from Microsoft, such as Shifts.</span></span>

#### <a name="can-users-change-the-order-of-apps-pinned-through-a-policy"></a><span data-ttu-id="2bb27-198">Os usuários podem alterar a ordem dos aplicativos fixos por meio de uma política</span><span class="sxs-lookup"><span data-stu-id="2bb27-198">Can users change the order of apps pinned through a policy</span></span>

<span data-ttu-id="2bb27-199">Os usuários podem alterar a ordem dos aplicativos fixos na área de trabalho do Microsoft Teams e clientes móveis se a opção **permitir fixação do usuário** estiver ativada.</span><span class="sxs-lookup"><span data-stu-id="2bb27-199">Users can change the order of their pinned apps on Teams desktop and mobile clients if the **Allow user pinning** option is turned on.</span></span> <span data-ttu-id="2bb27-200">Os usuários não podem alterar a ordem dos aplicativos fixos nos clientes Web do teams.</span><span class="sxs-lookup"><span data-stu-id="2bb27-200">Users can't change the order of their pinned apps on Teams web clients.</span></span>

#### <a name="does-user-pinning-take-precedence"></a><span data-ttu-id="2bb27-201">A fixação do usuário tem prioridade</span><span class="sxs-lookup"><span data-stu-id="2bb27-201">Does user pinning take precedence</span></span>

<span data-ttu-id="2bb27-202">Se a política de configuração do aplicativo atribuída ao usuário for alterada para bloquear a fixação do aplicativo do usuário, o Teams removerá todos os aplicativos fixados na barra de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="2bb27-202">If the app setup policy assigned to the user is changed to block user app pinning, Teams removes any apps pinned to the app bar.</span></span> <span data-ttu-id="2bb27-203">Se a política for alterada para permitir a fixação do aplicativo do usuário, os usuários deverão refixar os aplicativos anteriormente desafixados.</span><span class="sxs-lookup"><span data-stu-id="2bb27-203">If the policy is then changed to allow user app pinning, users must re-pin their previously pinned apps.</span></span>

### <a name="custom-teams-apps"></a><span data-ttu-id="2bb27-204">Aplicativos personalizados do teams</span><span class="sxs-lookup"><span data-stu-id="2bb27-204">Custom Teams apps</span></span>

#### <a name="my-organization-built-a-custom-teams-app-and-published-it-either-to-appsource-or-the-tenant-app-catalog-but-the-app-icon-isnt-displayed-as-expected-when-the-app-is-pinned-to-the-app-bar-in-teams-how-do-i-fix-it"></a><span data-ttu-id="2bb27-205">Minha organização construiu um aplicativo de equipes personalizado e o publicou, seja para AppSource ou o catálogo de aplicativos do locatário, mas o ícone do aplicativo não é exibido como esperado quando o aplicativo é fixado à barra de aplicativos no Teams.</span><span class="sxs-lookup"><span data-stu-id="2bb27-205">My organization built a custom Teams app and published it, either to AppSource or the tenant app catalog, but the app icon isn't displayed as expected when the app is pinned to the app bar in Teams.</span></span> <span data-ttu-id="2bb27-206">Como corrigir</span><span class="sxs-lookup"><span data-stu-id="2bb27-206">How do I fix it</span></span>

<span data-ttu-id="2bb27-207">Certifique-se de seguir as diretrizes do logotipo antes de enviar o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="2bb27-207">Make sure that you follow the logo guidelines before you submit the app.</span></span> <span data-ttu-id="2bb27-208">Para saber mais, consulte [a lista de verificação para envio do painel do vendedor](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span><span class="sxs-lookup"><span data-stu-id="2bb27-208">To learn more, see [Checklist for Seller Dashboard submission](/microsoftteams/platform/concepts/deploy-and-publish/appsource/prepare/overview).</span></span>

## <a name="related-topics"></a><span data-ttu-id="2bb27-209">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="2bb27-209">Related topics</span></span>

[<span data-ttu-id="2bb27-210">Configurações de administrador para aplicativos no Teams</span><span class="sxs-lookup"><span data-stu-id="2bb27-210">Admin settings for apps in Teams</span></span>](admin-settings.md)

[<span data-ttu-id="2bb27-211">Atribua políticas a seus usuários no Teams</span><span class="sxs-lookup"><span data-stu-id="2bb27-211">Assign policies to your users in Teams</span></span>](assign-policies.md)
