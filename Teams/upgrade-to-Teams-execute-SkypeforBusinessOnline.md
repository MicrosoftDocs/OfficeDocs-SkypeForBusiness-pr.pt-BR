---
title: Atualizar do Skype for Business Online para o Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como atualizar sua organização para o Microsoft Teams a partir de uma implantação do Skype for Business Online.
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
ms.openlocfilehash: ca99c193a17547943018eba75004f0ec0a1a92f3
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578254"
---
# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="78d4f-103">Atualizar do Skype for Business Online para o Teams</span><span class="sxs-lookup"><span data-stu-id="78d4f-103">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="78d4f-104">![Diagrama de atualização da jornada, enfatizando Implantação e Implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio de Implantação e Implementação")</span><span class="sxs-lookup"><span data-stu-id="78d4f-104">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="78d4f-105">Este artigo faz parte da etapa implantação e implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="78d4f-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="78d4f-106">Antes de prosseguir, confirme que você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="78d4f-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="78d4f-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="78d4f-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="78d4f-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="78d4f-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="78d4f-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="78d4f-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="78d4f-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="78d4f-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="78d4f-111">Preparou seu ambiente</span><span class="sxs-lookup"><span data-stu-id="78d4f-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="78d4f-112">Preparar sua organização</span><span class="sxs-lookup"><span data-stu-id="78d4f-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="78d4f-113">Piloto conduzido</span><span class="sxs-lookup"><span data-stu-id="78d4f-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="78d4f-114">Siga as orientações neste artigo se você implantou o Skype for Business Online e deseja atualizar seus usuários do Skype for Business para o Teams.</span><span class="sxs-lookup"><span data-stu-id="78d4f-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="78d4f-115">Você pode atualizar os usuários seletivamente ou de forma total, com base na jornada de atualização escolhida pela sua organização, atribuindo a coexistência e o modo de atualização apropriados aos usuários.</span><span class="sxs-lookup"><span data-stu-id="78d4f-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="78d4f-116">O Skype for Business Online será desativado em 31 de julho de 2021, e depois disso não estará mais acessível nem terá suporte.</span><span class="sxs-lookup"><span data-stu-id="78d4f-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="78d4f-117">Para maximizar a realização dos benefícios e garantir que sua organização tenha tempo adequado para implementar a atualização, recomendamos que você comece hoje sua jornada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="78d4f-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="78d4f-118">Lembre-se de que uma atualização bem-sucedida alinha a preparação técnica e do usuário, portanto, lembre-se de aproveitar as orientações aqui enquanto navega para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="78d4f-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="78d4f-119">Atribuir a coexistência e o modo de atualização</span><span class="sxs-lookup"><span data-stu-id="78d4f-119">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="78d4f-120">Você pode atualizar seus usuários para o modo TeamsOnly atribuindo a instância UpgradeToTeams do TeamsUpgradePolicy, que pode ser executada usando o centro de administração do Microsoft Teams ou uma sessão remota do Windows PowerShell do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="78d4f-120">You can upgrade your users to TeamsOnly mode by assigning the UpgradeToTeams instance of TeamsUpgradePolicy, which can be performed by using the Microsoft Teams admin center or a Skype for Business remote Windows PowerShell session.</span></span> <span data-ttu-id="78d4f-121">Você pode fazer isso por usuário ou em todo o locatário se quiser atualizar o locatário inteiro em uma etapa.</span><span class="sxs-lookup"><span data-stu-id="78d4f-121">You can do this either on a per user basis, or on a tenant-wide basis if you want to upgrade the entire tenant in one step.</span></span> 

<span data-ttu-id="78d4f-122">Para obter mais informações, consulte [Definir suas configurações](https://aka.ms/SkypeToTeams-SetCoexistence) de coexistência e atualização e [TeamsUpgradePolicy: gerenciamento de migração e coexistência.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="78d4f-122">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

## <a name="upgrade-all-users-to-teams-at-one-time"></a><span data-ttu-id="78d4f-123">Atualizar todos os usuários para o Teams de uma só vez</span><span class="sxs-lookup"><span data-stu-id="78d4f-123">Upgrade all users to Teams at one time</span></span>

<span data-ttu-id="78d4f-124">Siga estas etapas para atualizar todos os usuários para o Teams de uma só vez.</span><span class="sxs-lookup"><span data-stu-id="78d4f-124">Follow these steps to upgrade all of your users to Teams at one time.</span></span>

### <a name="step-1-notify-the-users-of-the-change-optional"></a><span data-ttu-id="78d4f-125">Etapa 1: notificar os usuários sobre a alteração (opcional)</span><span class="sxs-lookup"><span data-stu-id="78d4f-125">Step 1: Notify the users of the change (optional)</span></span>

1. <span data-ttu-id="78d4f-126">No Centro de administração do Microsoft Teams, selecione Atualização do Teams para configurações **em toda a**  >  **organização.**</span><span class="sxs-lookup"><span data-stu-id="78d4f-126">In the Microsoft Teams admin center, select **Org-wide settings** > **Teams upgrade**.</span></span>
2. <span data-ttu-id="78d4f-127">Em **Modo de Coexistência,** altere a **notificação** dos usuários do Skype for Business de que uma atualização para o Teams está disponível para **a opção Para.**</span><span class="sxs-lookup"><span data-stu-id="78d4f-127">Under **Coexistence mode**, change the **Notify Skype for Business users that an upgrade to Teams is available** switch to **On**.</span></span>

### <a name="step-2-set-the-coexistence-mode-to-teamsonly-for-the-organization"></a><span data-ttu-id="78d4f-128">Etapa 2: Definir o modo de coexistência como TeamsOnly para a organização</span><span class="sxs-lookup"><span data-stu-id="78d4f-128">Step 2: Set the coexistence mode to TeamsOnly for the organization</span></span>

1. <span data-ttu-id="78d4f-129">No Centro de administração do Microsoft Teams, selecione **configurações de toda a organização.**</span><span class="sxs-lookup"><span data-stu-id="78d4f-129">In the Microsoft Teams admin center, select **Org-wide settings**.</span></span>
2. <span data-ttu-id="78d4f-130">Selecione **o modo Somente** Equipes na listada do modo Coexistência. </span><span class="sxs-lookup"><span data-stu-id="78d4f-130">Select **Teams Only** mode from the **Coexistence mode** drop-down list.</span></span>

## <a name="upgrade-users-in-stages"></a><span data-ttu-id="78d4f-131">Atualizar usuários em estágios</span><span class="sxs-lookup"><span data-stu-id="78d4f-131">Upgrade users in stages</span></span>

<span data-ttu-id="78d4f-132">Siga estas etapas se quiser atualizar gradualmente seus usuários para o TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="78d4f-132">Follow these steps if you want to gradually upgrade your users to TeamsOnly.</span></span>

### <a name="step-1-identify-groups-of-users-for-upgrade"></a><span data-ttu-id="78d4f-133">Etapa 1: identificar grupos de usuários para atualização</span><span class="sxs-lookup"><span data-stu-id="78d4f-133">Step 1: Identify groups of users for upgrade</span></span>

<span data-ttu-id="78d4f-134">Muitas vezes, as organizações podem optar por atualizar suas organizações em ondas de sucesso dos usuários.</span><span class="sxs-lookup"><span data-stu-id="78d4f-134">Often organizations may choose to upgrade their organizations in success waves of users.</span></span>  <span data-ttu-id="78d4f-135">Primeiro, você deve identificar esses usuários para poder pesquisá-los facilmente no Centro de administração do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="78d4f-135">You'll want to identify these users first so you can easily search for them in the Microsoft Teams admin center.</span></span> <span data-ttu-id="78d4f-136">Como alternativa, talvez você queira usar o PowerShell para fazer isso com mais eficiência.</span><span class="sxs-lookup"><span data-stu-id="78d4f-136">Alternatively, you may want to use PowerShell to more efficiently do this.</span></span> <span data-ttu-id="78d4f-137">Depois de identificar o conjunto de usuários para uma determinada onda de atualização, continue com as etapas restantes.</span><span class="sxs-lookup"><span data-stu-id="78d4f-137">Once you have identified the set of users for a given upgrade wave, continue with the remaining steps.</span></span>

### <a name="step-2-set-notification-for-the-users-in-the-current-upgrade-wave-optional"></a><span data-ttu-id="78d4f-138">Etapa 2: Definir notificação para os usuários na onda de atualização atual (opcional)</span><span class="sxs-lookup"><span data-stu-id="78d4f-138">Step 2: Set notification for the users in the current upgrade wave (optional)</span></span>

<span data-ttu-id="78d4f-139">Se estiver usando o Centro de administração do Microsoft Teams, você poderá configurar o TeamsUpgradePolicy para até 20 usuários ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="78d4f-139">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="78d4f-140">No Centro de administração do Microsoft Teams, selecione Usuários e localize e marque várias caixas de seleção para até 20 usuários que devem ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="78d4f-140">In the Microsoft Teams admin center, select **Users**, and find and multi-select the checkbox for up to 20 users who should be upgraded.</span></span> 
2. <span data-ttu-id="78d4f-141">Selecione **Editar configurações** no canto superior esquerdo da visualização de lista.</span><span class="sxs-lookup"><span data-stu-id="78d4f-141">Select **Edit settings** in the upper left corner of the listview.</span></span> 
3. <span data-ttu-id="78d4f-142">No painel **Editar configurações à** direita, em Atualização do **Teams,** altere **Notificar** a opção do usuário do Skype for Business para **2010.**</span><span class="sxs-lookup"><span data-stu-id="78d4f-142">In the **Edit settings** pane on the right, under **Teams upgrade**, change **Notify the Skype for Business user** switch to **On**.</span></span> <span data-ttu-id="78d4f-143">Observação: se o valor do modo de coexistência for "Usar configurações de toda a organização", você não verá essa opção, portanto, primeiro será necessário definir explicitamente o modo de Coexistência para esses usuários, seja qual for o valor padrão para a organização.</span><span class="sxs-lookup"><span data-stu-id="78d4f-143">Note: If the value of coexistence mode is "Use Org-wide settings", you won't see this switch, so you'll need to first explicitly set the Coexistence mode for these users to whatever the default value is for the org.</span></span>

<span data-ttu-id="78d4f-144">Como alternativa, talvez seja mais fácil habilitar notificações para grupos de usuários ao mesmo tempo usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78d4f-144">Alternatively, you may find it easier to enable notifications for groups of users at once using PowerShell.</span></span> 

### <a name="step-3-set-the-coexistence-mode-for-users-to-teams-only"></a><span data-ttu-id="78d4f-145">Etapa 3: definir o modo de coexistência para os usuários como Somente Equipes</span><span class="sxs-lookup"><span data-stu-id="78d4f-145">Step 3: Set the coexistence mode for users to Teams Only</span></span>

<span data-ttu-id="78d4f-146">Quando você estiver pronto para atualizar os usuários na onda atual para usar o Teams como seu único aplicativo, de definir o modo de Coexistência para os usuários apenas para o Teams.</span><span class="sxs-lookup"><span data-stu-id="78d4f-146">When you are ready to upgrade the users in the current wave to use Teams as their only application, set the Coexistence mode for the users to Teams Only.</span></span>

<span data-ttu-id="78d4f-147">Se estiver usando o Centro de administração do Microsoft Teams, você poderá configurar o TeamsUpgradePolicy para até 20 usuários ao mesmo tempo:</span><span class="sxs-lookup"><span data-stu-id="78d4f-147">If using the Microsoft Teams admin center, you can configure TeamsUpgradePolicy for up to 20 user at once:</span></span>
1. <span data-ttu-id="78d4f-148">No Centro de administração do Microsoft Teams, selecione **Usuários** e marque a caixa de seleção para até 20 usuários.</span><span class="sxs-lookup"><span data-stu-id="78d4f-148">In the Microsoft Teams admin center, select **Users**, and then select the checkbox for up to 20 users.</span></span>
2. <span data-ttu-id="78d4f-149">Selecione **Editar configurações** no canto superior esquerdo da visualização de lista.</span><span class="sxs-lookup"><span data-stu-id="78d4f-149">Select **Edit settings** in the upper left corner of the listview.</span></span>
3. <span data-ttu-id="78d4f-150">No painel **Editar configurações** à direita, na seção de atualização do **Teams,** de definir o modo de coexistência como **Equipes** somente na lista listada.</span><span class="sxs-lookup"><span data-stu-id="78d4f-150">In the **Edit settings** pane on the right, under **Teams upgrade** section, set the coexistence mode to **Teams Only** in the drop-down list.</span></span>

<span data-ttu-id="78d4f-151">Como alternativa, talvez seja mais fácil atualizar grupos de usuários de uma só vez usando o PowerShell.</span><span class="sxs-lookup"><span data-stu-id="78d4f-151">Alternatively, you may find it easier to upgrade groups of users at once using PowerShell.</span></span> 

### <a name="step-4-repeat-steps-1-3-for-successive-waves-of-users"></a><span data-ttu-id="78d4f-152">Etapa 4: repetir as etapas de 1 a 3 para ondas sucessivas de usuários</span><span class="sxs-lookup"><span data-stu-id="78d4f-152">Step 4: Repeat steps 1-3 for successive waves of users</span></span>

<span data-ttu-id="78d4f-153">Conforme validar sua atualização para o modo Somente do Teams e estiver pronto para expandir, repita as etapas anteriores para aplicar o TeamsOnly a mais usuários.</span><span class="sxs-lookup"><span data-stu-id="78d4f-153">As you validate your upgrade to Teams Only mode and are ready to expand, repeat the previous steps to apply TeamsOnly to  more users.</span></span>  


## <a name="phone-system-and-pstn-connectivity-options"></a><span data-ttu-id="78d4f-154">Opções de conectividade PSTN e sistema telefônico</span><span class="sxs-lookup"><span data-stu-id="78d4f-154">Phone System and PSTN connectivity options</span></span>

<span data-ttu-id="78d4f-155">O Sistema telefônico com o Teams tem suporte depois que o usuário está no modo TeamsOnly.</span><span class="sxs-lookup"><span data-stu-id="78d4f-155">Phone System with Teams is supported after the user is in TeamsOnly mode.</span></span> <span data-ttu-id="78d4f-156">(Se o usuário estiver no modo Ilhas, o Sistema telefônico só tem suporte no Skype for Business.)</span><span class="sxs-lookup"><span data-stu-id="78d4f-156">(If the user is in Islands mode, Phone System is only supported with Skype for Business.)</span></span>  

### <a name="pstn-connectivity-options"></a><span data-ttu-id="78d4f-157">Opções de conectividade PSTN</span><span class="sxs-lookup"><span data-stu-id="78d4f-157">PSTN connectivity options</span></span>

<span data-ttu-id="78d4f-158">Ao considerar as opções de conectividade PSTN (Rede Telefônica Pública Comutado), há dois cenários possíveis ao mudar do Skype for Business Online para o modo TeamsOnly:</span><span class="sxs-lookup"><span data-stu-id="78d4f-158">When considering Public Switched Telephone Network (PSTN) connectivity options, there are two possible scenarios when moving from Skype for Business Online to TeamsOnly mode:</span></span>

- <span data-ttu-id="78d4f-159">Um usuário no Skype for Business Online, com um Plano de Chamada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78d4f-159">A user in Skype for Business Online, with a Microsoft Calling Plan.</span></span> <span data-ttu-id="78d4f-160">Após a atualização, esse usuário continuará a ter um plano de Chamada da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="78d4f-160">Upon upgrade, this user will continue to have a Microsoft Calling plan.</span></span> <span data-ttu-id="78d4f-161">Esse é o cenário mais simples que requer apenas algumas etapas.</span><span class="sxs-lookup"><span data-stu-id="78d4f-161">This is the simplest scenario requiring only a couple of steps.</span></span> <span data-ttu-id="78d4f-162">Para obter mais informações, [consulte Do Skype for Business Online com planos de Chamada da Microsoft.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans)</span><span class="sxs-lookup"><span data-stu-id="78d4f-162">For more information, see [From Skype for Business Online with Microsoft Calling Plans](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-microsoft-calling-plans).</span></span>

- <span data-ttu-id="78d4f-163">Um usuário no Skype for Business Online, com funcionalidade de voz local por meio do Skype for Business local ou do Cloud Connector Edition.</span><span class="sxs-lookup"><span data-stu-id="78d4f-163">A user in Skype for Business Online, with on-premises voice functionality through Skype for Business on-premises or Cloud Connector Edition.</span></span> <span data-ttu-id="78d4f-164">A atualização do usuário para o Teams precisa ser coordenada com a migração do usuário para o Roteamento Direto para garantir que o usuário do TeamsOnly tenha funcionalidade PSTN.</span><span class="sxs-lookup"><span data-stu-id="78d4f-164">The user’s upgrade to Teams needs to be coordinated with migration of the user to Direct Routing to ensure the TeamsOnly user has PSTN functionality.</span></span>  <span data-ttu-id="78d4f-165">Para obter mais informações, [consulte o Skype for Business Online com voz local.](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice)</span><span class="sxs-lookup"><span data-stu-id="78d4f-165">For more information see, [From Skype for Business Online with on-premises voice](upgrade-to-teams-on-prem-pstn-considerations.md#from-skype-for-business-online-with-on-premises-voice).</span></span>


