---
title: Atualizar do Skype for Business local para o Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como fazer a transição da sua organização para Microsoft Teams de uma implantação Skype for Business local.
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
ms.openlocfilehash: 0585f0ad829f19334d5a970461f1f3248a107e9d
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51115549"
---
# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="e575f-103">Atualizar de uma implantação Skype for Business local para Teams</span><span class="sxs-lookup"><span data-stu-id="e575f-103">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="e575f-104">![Estágios da jornada de atualização, com ênfase no estágio implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="e575f-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="e575f-105">Este artigo faz parte do estágio implantação e implementação de sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="e575f-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="e575f-106">Antes de prosseguir, confirme se você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="e575f-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="e575f-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="e575f-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="e575f-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="e575f-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="e575f-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="e575f-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="e575f-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="e575f-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="e575f-111">Preparou seu ambiente</span><span class="sxs-lookup"><span data-stu-id="e575f-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="e575f-112">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="e575f-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="e575f-113">Conduzido um piloto</span><span class="sxs-lookup"><span data-stu-id="e575f-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="e575f-114">Siga as diretrizes deste artigo se você tiver implantado o Skype for Business ou o Microsoft Lync no local e sua organização quiser atualizar para o Microsoft Teams seletivamente, usando vários modos de coexistência ou todo o pacote.</span><span class="sxs-lookup"><span data-stu-id="e575f-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Microsoft Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> 

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="e575f-115">Etapa 1: Implantar conectividade híbrida</span><span class="sxs-lookup"><span data-stu-id="e575f-115">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="e575f-116">O principal pré-requisito para atualizar seus usuários para Teams é implantar a conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="e575f-116">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span>

<span data-ttu-id="e575f-117">Para obter mais informações, [consulte Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="e575f-117">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-implement-your-chosen-upgrade-journey-for-your-organization"></a><span data-ttu-id="e575f-118">Etapa 2: Implementar sua jornada de atualização escolhida para sua organização</span><span class="sxs-lookup"><span data-stu-id="e575f-118">Step 2: Implement your chosen upgrade journey for your organization</span></span>

<span data-ttu-id="e575f-119">Depois de concluir sua configuração híbrida, você pode planejar mover seus usuários para Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="e575f-119">After you've completed your hybrid setup, you can plan to move your users to Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="e575f-120">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="e575f-120">For more information, see:</span></span>

- <span data-ttu-id="e575f-121">[TeamsUpgradePolicy: gerenciando migração e coexistência.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="e575f-121">[TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

- <span data-ttu-id="e575f-122">[Mover usuários do local para o Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="e575f-122">[Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="e575f-123">Sistema de Telefonia e Teams atualização</span><span class="sxs-lookup"><span data-stu-id="e575f-123">Phone System and Teams upgrade</span></span>

<span data-ttu-id="e575f-124">A transição de sistemas telefônicos locais para o Teams permitirá que você tire proveito do roteamento direto Sistema de Telefonia ("Roteamento Direto") ou dos Planos de Chamadas fornecidos pela Microsoft para Microsoft 365 ou Office 365.</span><span class="sxs-lookup"><span data-stu-id="e575f-124">Transitioning from on-premises phone systems to Teams will allow you to take advantage of Phone System Direct Routing ("Direct Routing") or the Microsoft-provided Calling Plans for Microsoft 365 or Office 365.</span></span>

<span data-ttu-id="e575f-125">Se você não estiver usando Planos de Chamadas, precisará fazer a transição da implantação de voz da empresa para Sistema de Telefonia Roteamento Direto como parte da atualização para Teams.</span><span class="sxs-lookup"><span data-stu-id="e575f-125">If you're not using Calling Plans, you need to transition your enterprise voice deployment to Phone System Direct Routing as part of your upgrade to Teams.</span></span>

<span data-ttu-id="e575f-126">Para obter mais informações, [consulte considerações adicionais sobre Sistema de Telefonia Roteamento Direto.](./direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="e575f-126">For more information, see [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span> <span data-ttu-id="e575f-127">Se você estiver planejando usar Planos de Chamadas, consulte nossas diretrizes para transferir seus números de telefone [para](phone-number-calling-plans/transfer-phone-numbers-to-teams.md)Teams .</span><span class="sxs-lookup"><span data-stu-id="e575f-127">If you are planning to use Calling Plans, please refer to our guidance for [transferring your phone numbers to Teams](phone-number-calling-plans/transfer-phone-numbers-to-teams.md).</span></span>