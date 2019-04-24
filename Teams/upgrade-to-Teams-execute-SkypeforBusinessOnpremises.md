---
title: Atualizar Skype para negócios local às equipes da Microsoft | Implantar | Lync
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerações para atualizar a equipes de um Skype para negócios implantação local.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 78c69b8fb54a430269e63836ef430d63270841f8
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211957"
---
<span data-ttu-id="3f39d-103">![Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação] (media/upgrade-banner-deployment.png "Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação")</span><span class="sxs-lookup"><span data-stu-id="3f39d-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="3f39d-104">Este artigo faz parte do estágio de implantação e a implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="3f39d-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="3f39d-105">Antes de continuar, confirme que você tiver concluído as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="3f39d-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="3f39d-106">Inscrito seus participantes do projeto</span><span class="sxs-lookup"><span data-stu-id="3f39d-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="3f39d-107">Definido o escopo do projeto</span><span class="sxs-lookup"><span data-stu-id="3f39d-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="3f39d-108">Compreendidos coexistência e interoperabilidade do Skype para equipes e de negócios</span><span class="sxs-lookup"><span data-stu-id="3f39d-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="3f39d-109">Escolhido sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="3f39d-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="3f39d-110">Preparado o seu ambiente</span><span class="sxs-lookup"><span data-stu-id="3f39d-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="3f39d-111">Preparado sua organização</span><span class="sxs-lookup"><span data-stu-id="3f39d-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="3f39d-112">Conduzido um piloto</span><span class="sxs-lookup"><span data-stu-id="3f39d-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-on-premises-deployment-to-teams"></a><span data-ttu-id="3f39d-113">Atualizar de um Skype para implantação no local de negócios para equipes</span><span class="sxs-lookup"><span data-stu-id="3f39d-113">Upgrade from a Skype for Business on-premises deployment to Teams</span></span>

<span data-ttu-id="3f39d-114">Siga as orientações neste artigo se você implantou Skype para negócios ou Microsoft Lync no local e sua organização deseja atualizar para equipes ou seletivamente — usando vários modos de coexistência — ou tudo em.</span><span class="sxs-lookup"><span data-stu-id="3f39d-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="3f39d-115">A primeira etapa é configurar a conectividade híbrida com seu locatário do Office 365 e mova os usuários para Skype para Business Online e atribuí-las a coexistência apropriada e modo de atualização.</span><span class="sxs-lookup"><span data-stu-id="3f39d-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="3f39d-116">Etapa 1: Implantar a conectividade híbrida</span><span class="sxs-lookup"><span data-stu-id="3f39d-116">Step 1: Deploy hybrid connectivity</span></span>

<span data-ttu-id="3f39d-117">O pré-requisito principal para atualizar seus usuários para equipes é implantar conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="3f39d-117">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="3f39d-118">Isso pode envolver Implantando nova conectividade externa para sua Skype existente para a implantação do Lync ou de negócios ou simplesmente como configurar uma relação de híbrido com seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="3f39d-118">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span>

<span data-ttu-id="3f39d-119">Para obter mais informações, consulte [Deploy a conectividade de híbrido entre Skype para Business Server e do Skype para negócios Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span><span class="sxs-lookup"><span data-stu-id="3f39d-119">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity)</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="3f39d-120">Etapa 2: Mover usuários para Skype para negócios Online</span><span class="sxs-lookup"><span data-stu-id="3f39d-120">Step 2: Move users to Skype for Business Online</span></span>

<span data-ttu-id="3f39d-121">Depois de concluir sua configuração híbrida, mova usuários para Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="3f39d-121">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span>

<span data-ttu-id="3f39d-122">Para obter mais informações, consulte [mover os usuários no local para Skype para negócios Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="3f39d-122">For more information, see [Move users from on premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span></span>

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="3f39d-123">Etapa 3: Atribuir uma coexistência e modo de atualização</span><span class="sxs-lookup"><span data-stu-id="3f39d-123">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="3f39d-124">Depois que você moveu os usuários para Skype para Business Online, você pode atribuir a eles o modo de coexistência apropriada com base em uma atualização jornada que sua organização tenha escolhido.</span><span class="sxs-lookup"><span data-stu-id="3f39d-124">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="3f39d-125">Para obter mais informações, consulte [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="3f39d-125">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="3f39d-126">Com o Skype para Business Server 2019 e uma atualização cumulativa futura do Skype para Business Server 2015, você poderá executar a etapa 2 (mover usuários para Skype para Business Online) e a etapa 3 (atualização usuários às equipes) em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="3f39d-126">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="3f39d-127">Mais informações serão fornecidas após o lançamento do Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3f39d-127">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="3f39d-128">Atualização de sistema telefônico e equipes</span><span class="sxs-lookup"><span data-stu-id="3f39d-128">Phone System and Teams upgrade</span></span>

<span data-ttu-id="3f39d-129">Se você estiver fazendo a transição de seu Skype para implantação no local de negócios de voz corporativa para o sistema telefônico com planos de chamar e Microsoft será seu provedor de (PSTN) da rede telefônica pública comutada — e assumindo que você tiver concluído o número de telefone portando — atualizando seus usuários para equipes automaticamente transição entrada chamada PSTN às equipes.</span><span class="sxs-lookup"><span data-stu-id="3f39d-129">If you’re transitioning your Skype for Business on-premises deployment from enterprise voice to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="3f39d-130">Se os planos de chamada não estiver disponível, você precisará fazer a transição de sua implantação do enterprise voice roteamento direto do Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="3f39d-130">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="3f39d-131">Para atualizar seus usuários para equipes, consulte as [Considerações adicionais sobre roteamento direto de sistema do telefone](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="3f39d-131">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>