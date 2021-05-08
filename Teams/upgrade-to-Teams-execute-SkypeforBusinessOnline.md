---
title: Atualizar do Skype for Business Online para o Microsoft Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como atualizar sua organização para Microsoft Teams de uma implantação Skype for Business Online.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7c35909bf7787242a07f89d1442a25365348c91a
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282098"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="52275-103">Atualizar do Skype for Business Online para o Teams</span><span class="sxs-lookup"><span data-stu-id="52275-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="52275-104">![Atualizar diagrama de jornada, enfatizando Implantação e Implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="52275-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="52275-105">Este artigo faz parte do estágio implantação e implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="52275-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="52275-106">Antes de prosseguir, confirme se você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="52275-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="52275-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="52275-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="52275-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="52275-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="52275-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="52275-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="52275-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="52275-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="52275-111">Preparou seu ambiente</span><span class="sxs-lookup"><span data-stu-id="52275-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="52275-112">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="52275-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="52275-113">Conduzido um piloto</span><span class="sxs-lookup"><span data-stu-id="52275-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="52275-114">Siga as diretrizes deste artigo se você tiver implantado totalmente o Skype for Business Online e quiser atualizar seus usuários de Skype for Business para Teams.</span><span class="sxs-lookup"><span data-stu-id="52275-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="52275-115">Você pode atualizar os usuários de forma seletiva ou all-in, com base na jornada de atualização escolhida pela sua organização, atribuindo a coexistência apropriada e o modo de atualização aos seus usuários.</span><span class="sxs-lookup"><span data-stu-id="52275-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="52275-116">O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte.</span><span class="sxs-lookup"><span data-stu-id="52275-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="52275-117">Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="52275-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="52275-118">Lembre-se de que uma atualização bem-sucedida alinha a preparação técnica e do usuário, portanto, certifique-se de aproveitar as diretrizes aqui enquanto você navega sua jornada até Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="52275-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="52275-119">Atribuir o modo de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="52275-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="52275-120">Você pode atualizar seus usuários para o modo TeamsOnly atribuindo a instância UpgradeToTeams do TeamsUpgradePolicy, que pode ser executada usando o centro de administração do Microsoft Teams ou uma sessão Skype for Business de Windows PowerShell remota.</span><span class="sxs-lookup"><span data-stu-id="52275-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows PowerShell session.</span></span> <span data-ttu-id="52275-121">Você pode fazer isso por usuário ou em toda a locatário se quiser atualizar o locatário inteiro em uma etapa.</span><span class="sxs-lookup"><span data-stu-id="52275-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="52275-122">Para obter mais informações, consulte [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span><span class="sxs-lookup"><span data-stu-id="52275-122">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="52275-123">Atualizar todos os usuários para Teams ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="52275-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="52275-124">Siga estas etapas para atualizar todos os seus usuários para Teams de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="52275-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="52275-125">Etapa 1: Notificar os usuários sobre a alteração (opcional)</span><span class="sxs-lookup"><span data-stu-id="52275-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="52275-126">No centro Microsoft Teams de administração, selecione **Configurações** em toda a  >  **organização Teams atualização**.</span><span class="sxs-lookup"><span data-stu-id="52275-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="52275-127">Em **Modo de Coexistência,** altere a opção **Notificar** Skype for Business usuários que uma atualização para Teams está disponível para **On**.</span><span class="sxs-lookup"><span data-stu-id="52275-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="52275-128">Etapa 2: Definir o modo de coexistência como TeamsOnly para a organização</span><span class="sxs-lookup"><span data-stu-id="52275-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="52275-129">No centro Microsoft Teams de administração, selecione **Configurações em toda a organização.**</span><span class="sxs-lookup"><span data-stu-id="52275-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="52275-130">Selecione **Teams modo Somente** na **lista** de listada no modo coexistência.</span><span class="sxs-lookup"><span data-stu-id="52275-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="52275-131">Atualizar usuários em estágios</span><span class="sxs-lookup"><span data-stu-id="52275-131">Upgrade users in stages</span></span>

<span data-ttu-id="52275-132">Siga estas etapas se quiser atualizar gradualmente seus usuários para o TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="52275-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="52275-133">Etapa 1: Identificar grupos de usuários para atualização</span><span class="sxs-lookup"><span data-stu-id="52275-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="52275-134">Muitas vezes, as organizações podem optar por atualizar suas organizações em ondas de sucesso de usuários.</span><span class="sxs-lookup"><span data-stu-id="52275-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="52275-135">Você vai querer identificar esses usuários primeiro para que você possa pesquisar facilmente por eles no Microsoft Teams de administração.</span><span class="sxs-lookup"><span data-stu-id="52275-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="52275-136">Como alternativa, talvez você queira usar o PowerShell para fazer isso com mais eficiência.</span><span class="sxs-lookup"><span data-stu-id="52275-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="52275-137">Depois de identificar o conjunto de usuários para uma determinada onda de atualização, continue com as etapas restantes.</span><span class="sxs-lookup"><span data-stu-id="52275-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="52275-138">Etapa 2: Definir notificação para os usuários na onda de atualização atual (opcional)</span><span class="sxs-lookup"><span data-stu-id="52275-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="52275-139">Se estiver usando o Microsoft Teams de administração, você poderá configurar o TeamsUpgradePolicy para até 20 usuários ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="52275-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="52275-140">No centro Microsoft Teams de administração, selecione **Usuários** e localize e selecione a caixa de seleção para até 20 usuários que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="52275-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="52275-141">Selecione **Editar configurações** no canto superior esquerdo da listview.</span><span class="sxs-lookup"><span data-stu-id="52275-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="52275-142">No painel **Editar configurações** à direita, em atualização Teams **,** altere **Notificar** o Skype for Business de usuário para **Ligar**.</span><span class="sxs-lookup"><span data-stu-id="52275-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="52275-143">Observação: se o valor do modo de coexistência for "Usar configurações em toda a organização", você não verá essa opção, portanto, primeiro você precisará definir explicitamente o modo coexistência para esses usuários como qualquer que seja o valor padrão para a organização.</span><span class="sxs-lookup"><span data-stu-id="52275-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="52275-144">Como alternativa, você pode encontrar mais fácil habilitar notificações para grupos de usuários ao mesmo tempo usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52275-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="52275-145">Etapa 3: Definir o modo de coexistência para que os usuários Teams Somente</span><span class="sxs-lookup"><span data-stu-id="52275-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="52275-146">Quando você estiver pronto para atualizar os usuários na onda atual para usar o Teams como seu único aplicativo, de definir o modo coexistência para os usuários Teams Somente.</span><span class="sxs-lookup"><span data-stu-id="52275-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="52275-147">Se estiver usando o Microsoft Teams de administração, você poderá configurar o TeamsUpgradePolicy para até 20 usuários ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="52275-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="52275-148">No centro Microsoft Teams de administração, selecione **Usuários** e selecione a caixa de seleção para até 20 usuários.</span><span class="sxs-lookup"><span data-stu-id="52275-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="52275-149">Selecione **Editar configurações** no canto superior esquerdo da listview.</span><span class="sxs-lookup"><span data-stu-id="52275-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="52275-150">No painel **Editar configurações** à direita, em Teams de atualização, de definir o modo de coexistência como Teams **somente** na lista de menus. </span><span class="sxs-lookup"><span data-stu-id="52275-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="52275-151">Como alternativa, talvez seja mais fácil atualizar grupos de usuários ao mesmo tempo usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="52275-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="52275-152">Etapa 4: Repita as etapas 1-3 para ondas sucessivas de usuários</span><span class="sxs-lookup"><span data-stu-id="52275-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="52275-153">À medida que você valida sua atualização para o modo Somente Teams e está pronto para expandir, repita as etapas anteriores para aplicar o TeamsOnly a mais usuários.</span><span class="sxs-lookup"><span data-stu-id="52275-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="52275-154">Sistema de Telefonia e opções de conectividade PSTN</span><span class="sxs-lookup"><span data-stu-id="52275-154">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="52275-155">Sistema de Telefonia com Teams é suportado depois que o usuário está no modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="52275-155">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="52275-156">(Se o usuário estiver no modo Ilhas, Sistema de Telefonia só será suportado com Skype for Business.)</span><span class="sxs-lookup"><span data-stu-id="52275-156">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span>  

### <a name="pstn-connectivity-options"></a><span data-ttu-id="52275-157">Opções de conectividade PSTN</span><span class="sxs-lookup"><span data-stu-id="52275-157">PSTN connectivity options</span></span>

<span data-ttu-id="52275-158">Ao considerar as opções de conectividade PSTN (Rede Telefônica Pública Comutado), há dois cenários possíveis ao mudar do Skype for Business Online para o modo TeamsOnly:</span><span class="sxs-lookup"><span data-stu-id="52275-158">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business Online to TeamsOnly mode:</span></span>

- <span data-ttu-id="52275-159">Um usuário no Skype for Business Online, com um Plano de Chamada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52275-159">A user in Skype for Business Online, with a Microsoft Calling Plan.</span></span> <span data-ttu-id="52275-160">Após a atualização, esse usuário continuará a ter um plano de Chamada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="52275-160">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span> <span data-ttu-id="52275-161">Esse é o cenário mais simples que exige apenas algumas etapas.</span><span class="sxs-lookup"><span data-stu-id="52275-161">This is the simplest scenario requiring only a couple of steps.</span></span> <span data-ttu-id="52275-162">Para obter mais informações, [consulte From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span><span class="sxs-lookup"><span data-stu-id="52275-162">For more information, see [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span>

- <span data-ttu-id="52275-163">Um usuário no Skype for Business Online, com funcionalidade de voz local por meio Skype for Business local ou Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="52275-163">A user in Skype for Business Online, with on-premises voice functionality through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="52275-164">A atualização do usuário para Teams precisa ser coordenada com a migração do usuário para Roteamento Direto para garantir que o usuário teamsOnly tenha funcionalidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="52275-164">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>  <span data-ttu-id="52275-165">Para obter mais informações, [consulte From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span><span class="sxs-lookup"><span data-stu-id="52275-165">For more information see, [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span></span>