---
title: A atualização do Skype para negócios Online para equipes da Microsoft | Implantar
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerações para a atualização para equipes do Skype para negócios Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Teams_ITAdmin_JourneyFromSfB
appliesto:
- Microsoft Teams
ms.openlocfilehash: 668e44b66b08b16a04e730c43dbbe02a9edea4fe
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754627"
---
<span data-ttu-id="c522c-103">![Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação] (media/upgrade-banner-deployment.png "Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação")</span><span class="sxs-lookup"><span data-stu-id="c522c-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="c522c-104">Este artigo faz parte do estágio de implantação e a implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="c522c-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="c522c-105">Antes de continuar, confirme que você tiver concluído as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="c522c-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="c522c-106">Inscrito seus participantes do projeto</span><span class="sxs-lookup"><span data-stu-id="c522c-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="c522c-107">Definido o escopo do projeto</span><span class="sxs-lookup"><span data-stu-id="c522c-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="c522c-108">Compreendidos coexistência e interoperabilidade do Skype para equipes e de negócios</span><span class="sxs-lookup"><span data-stu-id="c522c-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="c522c-109">Escolhido sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="c522c-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="c522c-110">Preparado o seu ambiente</span><span class="sxs-lookup"><span data-stu-id="c522c-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="c522c-111">Preparado sua organização</span><span class="sxs-lookup"><span data-stu-id="c522c-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="c522c-112">Conduzido um piloto</span><span class="sxs-lookup"><span data-stu-id="c522c-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="c522c-113">Atualização do Skype para negócios Online para equipes</span><span class="sxs-lookup"><span data-stu-id="c522c-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="c522c-114">Siga as orientações neste artigo se você implantou integralmente Skype para Business Online e deseja atualizar seus usuários do Skype for Business para equipes.</span><span class="sxs-lookup"><span data-stu-id="c522c-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="c522c-115">Você pode atualizar usuários seletivamente ou tudo em, com base na atualização jornada que sua organização tenha escolhido, atribuindo-se o modo de atualização e coexistência apropriada para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="c522c-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="c522c-116">Atribuir o modo de atualização e coexistência</span><span class="sxs-lookup"><span data-stu-id="c522c-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="c522c-117">Você pode atualizar seus usuários por equipes, atribuindo-se o modo de TeamsOnly de TeamsUpgradePolicy, que pode ser realizada usando o Centro de administração do Microsoft Teams ou um Skype para a sessão do Windows Powershell remoto de negócios.</span><span class="sxs-lookup"><span data-stu-id="c522c-117">You can upgrade your users by Teams by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="c522c-118">Para obter mais informações, consulte [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="c522c-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="c522c-119">Atualizar todos os usuários a equipes de uma só vez</span><span class="sxs-lookup"><span data-stu-id="c522c-119">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="c522c-120">Siga estas etapas para atualizar todos os seus usuários a equipes de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="c522c-120">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change"></a><span data-ttu-id="c522c-121">Etapa 1: Notificar os usuários da alteração</span><span class="sxs-lookup"><span data-stu-id="c522c-121">Step 1: Notify the users of the change</span></span>

1. <span data-ttu-id="c522c-122">No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização** > **equipes de atualização**.</span><span class="sxs-lookup"><span data-stu-id="c522c-122">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="c522c-123">Em **modo de coexistência**, altere a opção de **Notificar Skype para usuários corporativos que uma atualização para equipes está disponível** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="c522c-123">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-for-the-users"></a><span data-ttu-id="c522c-124">Etapa 2: Definir o modo de coexistência para os usuários</span><span class="sxs-lookup"><span data-stu-id="c522c-124">Step 2: Set the coexistence mode for the users</span></span>

1. <span data-ttu-id="c522c-125">No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização**.</span><span class="sxs-lookup"><span data-stu-id="c522c-125">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="c522c-126">Selecione o modo de **Equipes somente** da lista suspensa **modo de coexistência** .</span><span class="sxs-lookup"><span data-stu-id="c522c-126">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="c522c-127">Atualizar os usuários em estágios</span><span class="sxs-lookup"><span data-stu-id="c522c-127">Upgrade users in stages</span></span>

<span data-ttu-id="c522c-128">Se você quiser que seus usuários a atualização gradual para equipes, siga estas etapas.</span><span class="sxs-lookup"><span data-stu-id="c522c-128">Follow these steps if you want to gradually upgrade your users to Teams.</span></span>

### <a name="step-1-create-your-user-cohorts-for-the-upgrade"></a><span data-ttu-id="c522c-129">Etapa 1: Criar seus colaboradores do usuário para a atualização</span><span class="sxs-lookup"><span data-stu-id="c522c-129">Step 1: Create your user cohorts for the upgrade</span></span>

<span data-ttu-id="c522c-130">Colaboradores do usuário são grupos de usuários que serão movidos para o modo de equipes apenas ao mesmo tempo.</span><span class="sxs-lookup"><span data-stu-id="c522c-130">User cohorts are groups of users who will be moved to Teams Only mode at the same time.</span></span>

<span data-ttu-id="c522c-131">Para criar seus colaboradores (adicionar o link à página de seleção do usuário) do usuário</span><span class="sxs-lookup"><span data-stu-id="c522c-131">To create your user cohorts (Add link to user selection page)</span></span>

### <a name="step-2-set-the-user-mode-to-islands"></a><span data-ttu-id="c522c-132">Etapa 2: Configurar o modo de usuário para ilhas</span><span class="sxs-lookup"><span data-stu-id="c522c-132">Step 2: Set the user mode to Islands</span></span>

1. <span data-ttu-id="c522c-133">No Centro de administração do Microsoft Teams, selecione **usuários**e selecione um cohort do usuário.</span><span class="sxs-lookup"><span data-stu-id="c522c-133">In the Microsoft Teams admin center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="c522c-134">Ao lado de **atualização de equipes**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c522c-134">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="c522c-135">No painel de **Atualização de equipes** , em **modo de coexistência**, selecione **Ilhas** da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="c522c-135">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Islands** from the drop-down list.</span></span>

### <a name="step-3-set-notification-for-the-user-optional"></a><span data-ttu-id="c522c-136">Etapa 3: Configurar a notificação para o usuário (opcional)</span><span class="sxs-lookup"><span data-stu-id="c522c-136">Step 3: Set notification for the user (optional)</span></span>

1. <span data-ttu-id="c522c-137">No Centro de administração do Microsoft Teams, selecione **usuários**e selecione um cohort do usuário.</span><span class="sxs-lookup"><span data-stu-id="c522c-137">In the Microsoft Teams admin center, select **Users**, and select a user cohort.</span></span>
2. <span data-ttu-id="c522c-138">Ao lado de **atualização de equipes**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c522c-138">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="c522c-139">No painel de **Atualização de equipes** , em **modo de coexistência**, altere opção **notificar o Skype para o usuário de negócios** para **ativado**.</span><span class="sxs-lookup"><span data-stu-id="c522c-139">In the **Teams Upgrade** pane, under **Coexistence mode**, change **Notify the Skype for Business user** switch to **On**.</span></span>

### <a name="step-4-set-the-user-mode-to-teams-only"></a><span data-ttu-id="c522c-140">Etapa 4: Configurar o modo de usuário para equipes somente</span><span class="sxs-lookup"><span data-stu-id="c522c-140">Step 4: Set the user mode to Teams Only</span></span>

<span data-ttu-id="c522c-141">Quando estiver pronto para atualizar os usuários para usar equipes como seus aplicativos somente, defina o modo de coexistência para o usuário para equipes somente.</span><span class="sxs-lookup"><span data-stu-id="c522c-141">When you are ready to upgrade the users to use Teams as their only application, set the Coexistence mode for the user to Teams Only.</span></span>

1. <span data-ttu-id="c522c-142">No Centro de administração do Microsoft Teams, selecione **usuários**e selecione um cohort do usuário.</span><span class="sxs-lookup"><span data-stu-id="c522c-142">In the Microsoft Teams admin center, select **Users**, and then select a user cohort.</span></span>
2. <span data-ttu-id="c522c-143">Ao lado de **atualização de equipes**, selecione **Editar**.</span><span class="sxs-lookup"><span data-stu-id="c522c-143">Next to **Teams upgrade**, select **Edit**.</span></span>
3. <span data-ttu-id="c522c-144">No painel de **Atualização de equipes** , em **modo de coexistência**, selecione **Equipes somente** da lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="c522c-144">In the **Teams Upgrade** pane, under **Coexistence mode**, select **Teams Only** from the drop-down list.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="c522c-145">Atualização de sistema telefônico e equipes</span><span class="sxs-lookup"><span data-stu-id="c522c-145">Phone System and Teams upgrade</span></span>

<span data-ttu-id="c522c-146">Se seu Skype para implantação Business Online inclui o sistema telefônico com planos de chamada e a Microsoft tem o seu provedor de telefônica pública comutada (PSTN) de rede, atualizando seus usuários para equipes passará automaticamente PSTN de entrada chamando-se às equipes.</span><span class="sxs-lookup"><span data-stu-id="c522c-146">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="c522c-147">Se seu Skype para implantação Business Online inclui o sistema telefônico com nuvem conector Edition, consulte as [Considerações adicionais sobre roteamento direto de sistema do telefone](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="c522c-147">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>