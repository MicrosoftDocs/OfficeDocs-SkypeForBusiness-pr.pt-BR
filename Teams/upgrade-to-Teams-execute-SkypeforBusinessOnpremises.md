---
title: Atualize o Skype for Business no local para o Microsoft Teams | Implantar | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerações para a atualização para o Teams a partir de uma implantação local do Skype for Business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1b41de8f54eb0e2a09e7e3700b25cba1e5564f0a
ms.sourcegitcommit: a47f0841b9a14ede65171a817ecb7ebc72f209e5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2019
ms.locfileid: "34288184"
---
<span data-ttu-id="90e9c-103">![Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação] (media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="90e9c-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="90e9c-104">Este artigo faz parte do estágio de implantação e implementação de sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="90e9c-104">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="90e9c-105">Antes de prosseguir, confirme que você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="90e9c-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="90e9c-106">Listamos os participantes do projeto</span><span class="sxs-lookup"><span data-stu-id="90e9c-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="90e9c-107">Definiu o escopo do projeto</span><span class="sxs-lookup"><span data-stu-id="90e9c-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="90e9c-108">Compreendemos a coexistência e interoperabilidade do Skype for Business e do teams</span><span class="sxs-lookup"><span data-stu-id="90e9c-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="90e9c-109">Escolhido a jornada da atualização</span><span class="sxs-lookup"><span data-stu-id="90e9c-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="90e9c-110">Seu ambiente foi preparado</span><span class="sxs-lookup"><span data-stu-id="90e9c-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="90e9c-111">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="90e9c-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="90e9c-112">Conduziu um piloto</span><span class="sxs-lookup"><span data-stu-id="90e9c-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="90e9c-113">Atualizar de uma implantação local do Skype for Business para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="90e9c-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="90e9c-114">Siga as orientações neste artigo se você tiver implantado o Skype for Business ou o Microsoft Lync local e sua organização quiser atualizar para o Microsoft Teams seletivamente — usando vários modos de coexistência ou todos.</span><span class="sxs-lookup"><span data-stu-id="90e9c-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="90e9c-115">Etapa 1: implantar a conectividade híbrida</span><span class="sxs-lookup"><span data-stu-id="90e9c-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="90e9c-116">O principal pré-requisito para atualizar os usuários para o Microsoft Teams é implantar a conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="90e9c-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="90e9c-117">Para obter mais informações, consulte [implantar conectividade híbrida entre o Skype for Business Server e o Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="90e9c-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="90e9c-118">Etapa 2: implementar a viagem de atualização escolhida para a sua organização</span><span class="sxs-lookup"><span data-stu-id="90e9c-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="90e9c-119">Depois de concluir a configuração híbrida, você poderá planejar a movimentação dos usuários para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="90e9c-119">After you’ve completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="90e9c-120">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="90e9c-120">For more information, see:</span></span>

- <span data-ttu-id="90e9c-121">[TeamsUpgradePolicy: Gerenciando a migração e](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)a coexistência.</span><span class="sxs-lookup"><span data-stu-id="90e9c-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="90e9c-122">[Mover usuários do local para o Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="90e9c-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="90e9c-123">Atualização do sistema de telefonia e do teams</span><span class="sxs-lookup"><span data-stu-id="90e9c-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="90e9c-124">A transição de sistemas telefônicos locais para o Microsoft Teams permitirá que você aproveite o roteamento direto do sistema de telefonia ("roteamento direto") ou os planos de chamada fornecidos pela Microsoft para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="90e9c-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing (“Direct Routing”) or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="90e9c-125">Se você não estiver usando planos de chamada no Office 365, será necessário fazer a transição de sua implantação do Enterprise Voice para o roteamento direto do sistema telefônico como parte de sua atualização para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="90e9c-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="90e9c-126">Para obter mais informações, consulte [considerações adicionais sobre o roteamento direto do sistema telefônico](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="90e9c-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="90e9c-127">Se estiver planejando usar planos de chamada no Office 365, consulte nossas diretrizes para [transferir seus números de telefone para o office 365](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365).</span><span class="sxs-lookup"><span data-stu-id="90e9c-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Office 365](https://docs.microsoft.com/microsoftteams/transfer-phone-numbers-to-office-365).</span></span>