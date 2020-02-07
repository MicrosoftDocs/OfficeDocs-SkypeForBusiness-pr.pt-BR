---
title: Atualize o Skype for Business no local para o Microsoft Teams | Implantar | Lync
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Considerações para a atualização para o Teams a partir de uma implantação local do Skype for Business.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4e2bcd48abb34ad3b8e18b780708e588ad9d0276
ms.sourcegitcommit: ed3d7ebb193229cab9e0e5be3dc1c28c3f622c1b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41836213"
---
<span data-ttu-id="6d51b-103">![Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="6d51b-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="6d51b-104">Este artigo faz parte do estágio de implantação e implementação de sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="6d51b-104">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="6d51b-105">Antes de prosseguir, confirme se você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="6d51b-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="6d51b-106">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="6d51b-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="6d51b-107">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="6d51b-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="6d51b-108">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="6d51b-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="6d51b-109">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="6d51b-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="6d51b-110">Seu ambiente foi preparado</span><span class="sxs-lookup"><span data-stu-id="6d51b-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="6d51b-111">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="6d51b-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="6d51b-112">Conduziu um piloto</span><span class="sxs-lookup"><span data-stu-id="6d51b-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="6d51b-113">Atualizar de uma implantação local do Skype for Business para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="6d51b-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="6d51b-114">Siga as orientações neste artigo se você tiver implantado o Skype for Business ou o Microsoft Lync local e sua organização quiser atualizar para o Microsoft Teams seletivamente — usando vários modos de coexistência ou todos.</span><span class="sxs-lookup"><span data-stu-id="6d51b-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="6d51b-115">Etapa 1: implantar a conectividade híbrida</span><span class="sxs-lookup"><span data-stu-id="6d51b-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="6d51b-116">O principal pré-requisito para atualizar os usuários para o Microsoft Teams é implantar a conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="6d51b-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="6d51b-117">Para obter mais informações, consulte [implantar conectividade híbrida entre o Skype for Business Server e o Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="6d51b-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="6d51b-118">Etapa 2: implementar a viagem de atualização escolhida para a sua organização</span><span class="sxs-lookup"><span data-stu-id="6d51b-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="6d51b-119">Depois de concluir a configuração híbrida, você poderá planejar a movimentação dos usuários para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d51b-119">After you’ve completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="6d51b-120">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="6d51b-120">For more information, see:</span></span>

- <span data-ttu-id="6d51b-121">[TeamsUpgradePolicy: Gerenciando a migração e a coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="6d51b-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="6d51b-122">[Mover usuários do local para o Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="6d51b-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="6d51b-123">Atualização do sistema de telefonia e do teams</span><span class="sxs-lookup"><span data-stu-id="6d51b-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="6d51b-124">A transição de sistemas telefônicos locais para o Microsoft Teams permitirá que você aproveite o roteamento direto do sistema de telefonia ("roteamento direto") ou os planos de chamada fornecidos pela Microsoft para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="6d51b-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing (“Direct Routing”) or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="6d51b-125">Se você não estiver usando planos de chamada no Office 365, será necessário fazer a transição de sua implantação do Enterprise Voice para o roteamento direto do sistema telefônico como parte de sua atualização para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="6d51b-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="6d51b-126">Para obter mais informações, consulte [considerações adicionais sobre o roteamento direto do sistema telefônico](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="6d51b-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="6d51b-127">Se estiver planejando usar planos de chamada no Office 365, consulte nossas diretrizes para [transferir seus números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="6d51b-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>