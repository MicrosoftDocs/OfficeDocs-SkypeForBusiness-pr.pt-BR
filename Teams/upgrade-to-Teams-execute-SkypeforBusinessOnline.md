---
title: A atualização do Skype para negócios Online para equipes da Microsoft | Implantar
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerações para a atualização para equipes do Skype para negócios Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6748397c354f9238282f9646388993fc0e9f7b88
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902714"
---
<span data-ttu-id="c7e75-103">![Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação] (media/upgrade-banner-deployment.png "Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação")</span><span class="sxs-lookup"><span data-stu-id="c7e75-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="c7e75-104">Este artigo faz parte do estágio de implantação e a implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="c7e75-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="c7e75-105">Antes de continuar, confirme que você tiver concluído as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="c7e75-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="c7e75-106">Inscrito seus participantes do projeto</span><span class="sxs-lookup"><span data-stu-id="c7e75-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="c7e75-107">Definido o escopo do projeto</span><span class="sxs-lookup"><span data-stu-id="c7e75-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="c7e75-108">Compreendidos coexistência e interoperabilidade do Skype para equipes e de negócios</span><span class="sxs-lookup"><span data-stu-id="c7e75-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="c7e75-109">Escolhido sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="c7e75-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="c7e75-110">Preparado o seu ambiente</span><span class="sxs-lookup"><span data-stu-id="c7e75-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="c7e75-111">Preparado sua organização</span><span class="sxs-lookup"><span data-stu-id="c7e75-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="c7e75-112">Conduzido um piloto</span><span class="sxs-lookup"><span data-stu-id="c7e75-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="c7e75-113">Atualizar do Skype for Business Online para o Teams</span><span class="sxs-lookup"><span data-stu-id="c7e75-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="c7e75-114">Siga as orientações neste artigo se você implantou integralmente Skype para Business Online e deseja atualizar seus usuários do Skype for Business para equipes.</span><span class="sxs-lookup"><span data-stu-id="c7e75-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="c7e75-115">Você pode atualizar usuários seletivamente ou tudo em, com base na atualização jornada que sua organização tenha escolhido, atribuindo-se o modo de atualização e coexistência apropriada para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="c7e75-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="c7e75-116">Atribuir o modo de atualização e coexistência</span><span class="sxs-lookup"><span data-stu-id="c7e75-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="c7e75-117">Você pode atualizar seus usuários para o modo de TeamsOnly, atribuindo-se a instância de UpgradeToTeams do TeamsUpgradePolicy, que pode ser realizada usando o Centro de administração do Microsoft Teams ou um Skype para a sessão do Windows Powershell remoto de negócios.</span><span class="sxs-lookup"><span data-stu-id="c7e75-117">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span> <span data-ttu-id="c7e75-118">Você pode fazer isso em uma base por usuário, ou em uma base de todo o locatário de se desejar atualização inquilino inteiro em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="c7e75-118">You can do this either on a per user basis, or on a tenant-wide basis if you want to ugprade the entire tenant in one step.</span></span> 

<span data-ttu-id="c7e75-119">Para obter mais informações, consulte [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="c7e75-119">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="c7e75-120">Atualizar todos os usuários a equipes de uma só vez</span><span class="sxs-lookup"><span data-stu-id="c7e75-120">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="c7e75-121">Siga estas etapas para atualizar todos os seus usuários a equipes de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="c7e75-121">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="c7e75-122">Etapa 1: Notificar os usuários da alteração (opcional)</span><span class="sxs-lookup"><span data-stu-id="c7e75-122">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="c7e75-123">No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização** > **equipes de atualização**.</span><span class="sxs-lookup"><span data-stu-id="c7e75-123">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="c7e75-124">Em **modo de coexistência**, altere a opção de **Notificar Skype para usuários corporativos que uma atualização para equipes está disponível** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="c7e75-124">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="c7e75-125">Etapa 2: Configurar o modo de coexistência para TeamsOnly para a organização</span><span class="sxs-lookup"><span data-stu-id="c7e75-125">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="c7e75-126">No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="c7e75-126">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="c7e75-127">Selecione o modo de **Equipes somente** da lista suspensa **modo de coexistência** .</span><span class="sxs-lookup"><span data-stu-id="c7e75-127">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="c7e75-128">Atualizar os usuários em estágios</span><span class="sxs-lookup"><span data-stu-id="c7e75-128">Upgrade users in stages</span></span>

<span data-ttu-id="c7e75-129">Se você quiser que seus usuários a atualização gradual para TeamsOnly, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c7e75-129">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="c7e75-130">Etapa 1: Identificar os grupos de usuários para atualização</span><span class="sxs-lookup"><span data-stu-id="c7e75-130">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="c7e75-131">As organizações podem optar por atualizar suas organizações em ondas sucesso de usuários.</span><span class="sxs-lookup"><span data-stu-id="c7e75-131">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="c7e75-132">Você vai querer identificar esses usuários pela primeira vez, portanto, você pode facilmente procurar por elas no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c7e75-132">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="c7e75-133">Como alternativa, convém usar o PowerShell para fazer isso de maneira mais eficiente.</span><span class="sxs-lookup"><span data-stu-id="c7e75-133">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="c7e75-134">Depois de identificar o conjunto de usuários para uma determinada onda de atualização, continue com as etapas restantes.</span><span class="sxs-lookup"><span data-stu-id="c7e75-134">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-ugprade-wave-optional"></a><span data-ttu-id="c7e75-135">Etapa 2: Definir uma notificação para os usuários na atualização onda atual (opcional)</span><span class="sxs-lookup"><span data-stu-id="c7e75-135">Step 2: Set notification for the users in the current ugprade wave (optional)</span></span>

<span data-ttu-id="c7e75-136">Se estiver usando o Centro de administração do Microsoft Teams, você pode configurar TeamsUpgradePolicy para usuário até 20 ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="c7e75-136">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="c7e75-137">No Centro de administração do Microsoft Teams, selecione **os usuários**e find and seleção múltipla a caixa de seleção para até 20 usuários que deve ser atualizado.</span><span class="sxs-lookup"><span data-stu-id="c7e75-137">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="c7e75-138">Selecione **Editar configurações** no canto superior esquerdo do automático.</span><span class="sxs-lookup"><span data-stu-id="c7e75-138">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="c7e75-139">No painel à direita, em **atualização de equipes**, **Editar configurações** altere opção **notificar o Skype para o usuário de negócios** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="c7e75-139">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="c7e75-140">Observação: Se o valor do modo de coexistência for "configurações de todo o uso Org", você não verá essa opção, portanto você precisará primeiro definir explicitamente o modo de coexistência para esses usuários ao vivo do que o valor padrão é de organograma.</span><span class="sxs-lookup"><span data-stu-id="c7e75-140">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="c7e75-141">Como alternativa, você talvez seja mais fácil habilitar as notificações para grupos de usuários ao mesmo tempo usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7e75-141">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="c7e75-142">Etapa 3: Definir o modo de coexistência para que os usuários somente equipes</span><span class="sxs-lookup"><span data-stu-id="c7e75-142">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="c7e75-143">Quando estiver pronto para atualizar os usuários na onda atual para usar equipes como seus aplicativos somente, defina o modo de coexistência para os usuários para equipes apenas.</span><span class="sxs-lookup"><span data-stu-id="c7e75-143">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="c7e75-144">Se estiver usando o Centro de administração do Microsoft Teams, você pode configurar TeamsUpgradePolicy para usuário até 20 ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="c7e75-144">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="c7e75-145">No Centro de administração do Microsoft Teams, selecione **os usuários**e, em seguida, marque a caixa de seleção para até 20 usuários.</span><span class="sxs-lookup"><span data-stu-id="c7e75-145">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="c7e75-146">Selecione **Editar configurações** no canto superior esquerdo do automático.</span><span class="sxs-lookup"><span data-stu-id="c7e75-146">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="c7e75-147">No painel **Editar configurações** à direita, na seção **Atualizar equipes** , defina o modo de coexistência para **Equipes apenas** na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="c7e75-147">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="c7e75-148">Como alternativa, você talvez seja mais fácil para atualizar os grupos de usuários ao mesmo tempo usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c7e75-148">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="c7e75-149">Etapa 4: Repita as etapas 1 a 3 para fases sucessivas de usuários</span><span class="sxs-lookup"><span data-stu-id="c7e75-149">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="c7e75-150">Conforme você valida a atualização para o modo somente equipes e estiver pronto para expandir, repita as etapas anteriores para aplicar TeamsOnly a mais usuários.</span><span class="sxs-lookup"><span data-stu-id="c7e75-150">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="c7e75-151">Atualização de sistema telefônico e equipes</span><span class="sxs-lookup"><span data-stu-id="c7e75-151">Phone System and Teams upgrade</span></span>

<span data-ttu-id="c7e75-152">Se seu Skype para implantação Business Online inclui o sistema telefônico com planos de chamada e a Microsoft tem o seu provedor de telefônica pública comutada (PSTN) de rede, atualizando seus usuários para equipes passará automaticamente PSTN de entrada chamando-se às equipes.</span><span class="sxs-lookup"><span data-stu-id="c7e75-152">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="c7e75-153">Se seu Skype para implantação Business Online inclui o sistema telefônico com nuvem conector Edition, consulte as [Considerações adicionais sobre roteamento direto de sistema do telefone](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="c7e75-153">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
