---
title: Atualize o Skype for Business online para o Microsoft Teams | Implementar
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Saiba como atualizar sua organização para o Microsoft Teams a partir de um deployement do Skype for Business online.
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
ms.openlocfilehash: 37deecdbff083718dcb5b8a16e77ac8da4b998ff
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905353"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="7600d-103">Atualizar do Skype for Business Online para o Teams</span><span class="sxs-lookup"><span data-stu-id="7600d-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="7600d-104">![Atualize o diagrama de viagem, enfatizando implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="7600d-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="7600d-105">Este artigo faz parte do estágio de implantação e implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="7600d-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="7600d-106">Antes de prosseguir, confirme que você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="7600d-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="7600d-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="7600d-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="7600d-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="7600d-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="7600d-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="7600d-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="7600d-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="7600d-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="7600d-111">Seu ambiente foi preparado</span><span class="sxs-lookup"><span data-stu-id="7600d-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="7600d-112">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="7600d-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="7600d-113">Conduziu um piloto</span><span class="sxs-lookup"><span data-stu-id="7600d-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="7600d-114">Siga as orientações neste artigo se você tiver implantado o Skype for Business online com total implementação e quiser atualizar os usuários do Skype for Business para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7600d-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="7600d-115">Você pode atualizar usuários seletivamente ou todos os usuários, com base na jornada de atualização que a sua organização escolheu, atribuindo o modo de coexistência e atualização apropriado para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="7600d-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7600d-116">O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte.</span><span class="sxs-lookup"><span data-stu-id="7600d-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="7600d-117">Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7600d-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="7600d-118">Lembre-se de que uma atualização bem-sucedida alinha a prontidão técnica e do usuário, portanto, não deixe de aproveitar as diretrizes contidas ao navegar na jornada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7600d-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="7600d-119">Atribuir a coexistência e o modo de atualização</span><span class="sxs-lookup"><span data-stu-id="7600d-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="7600d-120">Você pode atualizar os usuários para o modo TeamsOnly atribuindo a instância UpgradeToTeams do TeamsUpgradePolicy, que pode ser realizada usando o centro de administração do Microsoft Teams ou uma sessão do Windows PowerShell remota do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="7600d-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="7600d-121">Você pode fazer isso por usuário ou com base em todo o locatário, se quiser atualizar o locatário inteiro em uma etapa.</span><span class="sxs-lookup"><span data-stu-id="7600d-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="7600d-122">Para obter mais informações, consulte [definindo suas configurações de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e a coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="7600d-122">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="7600d-123">Atualizar todos os usuários para o Teams ao mesmo tempo</span><span class="sxs-lookup"><span data-stu-id="7600d-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="7600d-124">Siga estas etapas para atualizar todos os usuários para o Teams ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="7600d-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="7600d-125">Etapa 1: notifique os usuários sobre a alteração (opcional)</span><span class="sxs-lookup"><span data-stu-id="7600d-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="7600d-126">No centro de administração do Microsoft Teams, selecione**atualização de equipes** **de configurações** > de toda a organização.</span><span class="sxs-lookup"><span data-stu-id="7600d-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="7600d-127">Em **modo de coexistência**, **altere a opção** **notificar os usuários do Skype for Business que uma atualização para o Microsoft Teams está disponível** .</span><span class="sxs-lookup"><span data-stu-id="7600d-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="7600d-128">Etapa 2: definir o modo de coexistência como TeamsOnly para a organização</span><span class="sxs-lookup"><span data-stu-id="7600d-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="7600d-129">No centro de administração do Microsoft Teams, selecione **configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="7600d-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="7600d-130">Selecione modo **somente equipes** na lista suspensa **modo de coexistência** .</span><span class="sxs-lookup"><span data-stu-id="7600d-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="7600d-131">Atualizar usuários em estágios</span><span class="sxs-lookup"><span data-stu-id="7600d-131">Upgrade users in stages</span></span>

<span data-ttu-id="7600d-132">Siga estas etapas se quiser atualizar gradualmente seus usuários para o TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="7600d-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="7600d-133">Etapa 1: identificar grupos de usuários para atualização</span><span class="sxs-lookup"><span data-stu-id="7600d-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="7600d-134">Muitas vezes, as organizações podem optar por atualizar suas organizações em ondas de sucesso de usuários.</span><span class="sxs-lookup"><span data-stu-id="7600d-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="7600d-135">Convém identificar esses usuários primeiro para que você possa procurá-los facilmente no centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7600d-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="7600d-136">Você também pode querer usar o PowerShell para fazer isso com mais eficiência.</span><span class="sxs-lookup"><span data-stu-id="7600d-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="7600d-137">Depois de identificar o conjunto de usuários para uma determinada onda de atualização, continue com as etapas restantes.</span><span class="sxs-lookup"><span data-stu-id="7600d-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="7600d-138">Etapa 2: definir notificação para os usuários na onda de atualização atual (opcional)</span><span class="sxs-lookup"><span data-stu-id="7600d-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="7600d-139">Se estiver usando o centro de administração do Microsoft Teams, você pode configurar o TeamsUpgradePolicy para até 20 usuários de uma só vez:</span><span class="sxs-lookup"><span data-stu-id="7600d-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="7600d-140">No centro de administração do Microsoft Teams, selecione **usuários**e localize e selecione várias caixas de seleção para até 20 usuários que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="7600d-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="7600d-141">Selecione **Editar configurações** no canto superior esquerdo da ListView.</span><span class="sxs-lookup"><span data-stu-id="7600d-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="7600d-142">No painel **Editar configurações** à direita, em atualização do Microsoft **Teams**, altere **Notifique a opção usuário do Skype for Business** para **ligar**.</span><span class="sxs-lookup"><span data-stu-id="7600d-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="7600d-143">Observação: se o valor do modo de coexistência for "usar configurações de toda a organização", você precisará primeiro definir explicitamente o modo de coexistência para esses usuários, seja qual for o valor padrão para a organização.</span><span class="sxs-lookup"><span data-stu-id="7600d-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="7600d-144">Como alternativa, talvez seja mais fácil habilitar notificações para grupos de usuários de uma vez usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7600d-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="7600d-145">Etapa 3: definir o modo de coexistência de usuários somente para equipes</span><span class="sxs-lookup"><span data-stu-id="7600d-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="7600d-146">Quando estiver pronto para atualizar os usuários da onda atual para usar o Microsoft Teams como o único aplicativo, defina o modo de coexistência para os usuários somente para equipes.</span><span class="sxs-lookup"><span data-stu-id="7600d-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="7600d-147">Se estiver usando o centro de administração do Microsoft Teams, você pode configurar o TeamsUpgradePolicy para até 20 usuários de uma só vez:</span><span class="sxs-lookup"><span data-stu-id="7600d-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="7600d-148">No centro de administração do Microsoft Teams, selecione **usuários**e marque a caixa de seleção de até 20 usuários.</span><span class="sxs-lookup"><span data-stu-id="7600d-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="7600d-149">Selecione **Editar configurações** no canto superior esquerdo da ListView.</span><span class="sxs-lookup"><span data-stu-id="7600d-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="7600d-150">No painel **Editar configurações** à direita, em seção **atualização do teams** , defina o modo de coexistência com o Microsoft **Teams somente** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="7600d-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="7600d-151">Você também pode achar mais fácil atualizar os grupos de usuários de uma vez usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7600d-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="7600d-152">Etapa 4: Repita as etapas 1-3 para ondas sucessivas de usuários</span><span class="sxs-lookup"><span data-stu-id="7600d-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="7600d-153">Ao validar a atualização para o modo somente Teams e estiver pronto para expandir, repita as etapas anteriores para aplicar o TeamsOnly a mais usuários.</span><span class="sxs-lookup"><span data-stu-id="7600d-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="7600d-154">Atualização do sistema de telefonia e do teams</span><span class="sxs-lookup"><span data-stu-id="7600d-154">Phone System and Teams upgrade</span></span>

<span data-ttu-id="7600d-155">Se a sua implantação do Skype for Business online incluir o sistema telefônico com planos de chamadas e a Microsoft for o seu provedor de rede telefônica pública comutada (PSTN), a atualização de seus usuários para o Microsoft Teams fará automaticamente a chamada PSTN de entrada para o Teams.</span><span class="sxs-lookup"><span data-stu-id="7600d-155">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="7600d-156">Se a sua implantação do Skype for Business Online inclui o sistema telefônico com o Cloud Connector Edition, consulte [considerações adicionais sobre o roteamento direto do sistema telefônico](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="7600d-156">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
