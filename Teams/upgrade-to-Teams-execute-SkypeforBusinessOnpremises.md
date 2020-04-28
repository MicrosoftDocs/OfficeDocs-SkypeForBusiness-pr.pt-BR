---
title: Atualizar do Skype for Business local para o Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Saiba como migrar sua organização para o Microsoft Teams a partir de uma implantação local do Skype for Business.
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
ms.openlocfilehash: a23adb8452a5c4173cc488a50655d2787b7849a9
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43905193"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="3cb36-103">Atualizar de uma implantação local do Skype for Business para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="3cb36-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="3cb36-104">![Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="3cb36-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="3cb36-105">Este artigo faz parte do estágio de implantação e implementação de sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="3cb36-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="3cb36-106">Antes de prosseguir, confirme que você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="3cb36-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="3cb36-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="3cb36-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="3cb36-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="3cb36-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="3cb36-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="3cb36-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="3cb36-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="3cb36-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="3cb36-111">Seu ambiente foi preparado</span><span class="sxs-lookup"><span data-stu-id="3cb36-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="3cb36-112">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="3cb36-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="3cb36-113">Conduziu um piloto</span><span class="sxs-lookup"><span data-stu-id="3cb36-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="3cb36-114">Siga as orientações neste artigo se você tiver implantado o Skype for Business ou o Microsoft Lync local e sua organização quiser atualizar para o Microsoft Teams seletivamente — usando vários modos de coexistência ou todos.</span><span class="sxs-lookup"><span data-stu-id="3cb36-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="3cb36-115">Etapa 1: implantar a conectividade híbrida</span><span class="sxs-lookup"><span data-stu-id="3cb36-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="3cb36-116">O principal pré-requisito para atualizar os usuários para o Microsoft Teams é implantar a conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="3cb36-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="3cb36-117">Para obter mais informações, consulte [implantar conectividade híbrida entre o Skype for Business Server e o Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="3cb36-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="3cb36-118">Etapa 2: implementar a viagem de atualização escolhida para a sua organização</span><span class="sxs-lookup"><span data-stu-id="3cb36-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="3cb36-119">Depois de concluir a configuração híbrida, você poderá planejar a movimentação dos usuários para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="3cb36-119">After you've completed your hybrid setup, you can plan to move your users to Office 365.</span></span>

<span data-ttu-id="3cb36-120">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="3cb36-120">For more information, see:</span></span>

- <span data-ttu-id="3cb36-121">[TeamsUpgradePolicy: Gerenciando a migração e a coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="3cb36-121">[TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

- <span data-ttu-id="3cb36-122">[Mover usuários do local para o Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="3cb36-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="3cb36-123">Atualização do sistema de telefonia e do teams</span><span class="sxs-lookup"><span data-stu-id="3cb36-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="3cb36-124">A transição de sistemas telefônicos locais para o Microsoft Teams permitirá que você aproveite o roteamento direto do sistema de telefonia ("roteamento direto") ou os planos de chamada fornecidos pela Microsoft para o Office 365.</span><span class="sxs-lookup"><span data-stu-id="3cb36-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Office 365.</span></span>

<span data-ttu-id="3cb36-125">Se você não estiver usando planos de chamada no Office 365, será necessário fazer a transição de sua implantação do Enterprise Voice para o roteamento direto do sistema telefônico como parte de sua atualização para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="3cb36-125">If you're not using Calling Plans in Office 365, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="3cb36-126">Para obter mais informações, consulte [considerações adicionais sobre o roteamento direto do sistema telefônico](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="3cb36-126">For more information, see [additional considerations for Phone System Direct Routing](https://docs.microsoft.com/MicrosoftTeams/2-envision-make-my-service-decisions-direct-routing).</span></span> <span data-ttu-id="3cb36-127">Se estiver planejando usar planos de chamada no Office 365, consulte nossas diretrizes para [transferir seus números de telefone para o Microsoft Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span><span class="sxs-lookup"><span data-stu-id="3cb36-127">If you are planning to use Calling Plans in Office 365, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>