---
title: Atualizar Skype para implantação híbrida do Business a Microsoft Teams | PSTN
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerações para atualizar a equipes de um Skype para implantação híbrida do Business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2c043d870c719d4427494ab24dade4f733febf5d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926111"
---
<span data-ttu-id="3e78a-103">![Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação] (media/upgrade-banner-deployment.png "Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação")</span><span class="sxs-lookup"><span data-stu-id="3e78a-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="3e78a-104">Este artigo faz parte do estágio de implantação e a implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="3e78a-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="3e78a-105">Antes de continuar, confirme que você tiver concluído as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="3e78a-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="3e78a-106">Inscrito seus participantes do projeto</span><span class="sxs-lookup"><span data-stu-id="3e78a-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="3e78a-107">Definido o escopo do projeto</span><span class="sxs-lookup"><span data-stu-id="3e78a-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="3e78a-108">Compreendidos coexistência e interoperabilidade do Skype para equipes e de negócios</span><span class="sxs-lookup"><span data-stu-id="3e78a-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="3e78a-109">Escolhido sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="3e78a-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="3e78a-110">Preparado o seu ambiente</span><span class="sxs-lookup"><span data-stu-id="3e78a-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="3e78a-111">Preparado sua organização</span><span class="sxs-lookup"><span data-stu-id="3e78a-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="3e78a-112">Conduzido um piloto</span><span class="sxs-lookup"><span data-stu-id="3e78a-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="3e78a-113">Atualizar a partir de um Skype para implantação híbrida do Business às equipes</span><span class="sxs-lookup"><span data-stu-id="3e78a-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="3e78a-114">Siga as orientações neste artigo se você implantou Skype para negócios ou Microsoft Lync local configurado em uma implantação híbrida com seu locatário do Office 365 e sua organização deseja atualizar para equipes ou seletivamente — usando vários modos de coexistência — ou tudo em.</span><span class="sxs-lookup"><span data-stu-id="3e78a-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="3e78a-115">Para qualquer um dos jornada de atualização, você precisa mover os usuários para Skype para Business Online (se eles já não são hospedados online) e atribuí-las a coexistência apropriada e o modo de atualização.</span><span class="sxs-lookup"><span data-stu-id="3e78a-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="3e78a-116">Etapa 1: Mover usuários para Skype para negócios Online</span><span class="sxs-lookup"><span data-stu-id="3e78a-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="3e78a-117">Esta etapa se aplica a usuários que estão atualmente hospedados no local.</span><span class="sxs-lookup"><span data-stu-id="3e78a-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="3e78a-118">Para obter mais informações sobre como mover esses usuários para Skype para Business Online, consulte [mover usuários de em - local para Skype para negócios Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="3e78a-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="3e78a-119">Etapa 2: Atribuir uma coexistência e modo de atualização</span><span class="sxs-lookup"><span data-stu-id="3e78a-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="3e78a-120">Depois que você moveu os usuários para Skype para Business Online, você pode atribuir a eles o modo de coexistência apropriada com base em uma atualização jornada que sua organização tenha escolhido.</span><span class="sxs-lookup"><span data-stu-id="3e78a-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="3e78a-121">Para obter mais informações, consulte [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="3e78a-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="3e78a-122">Com o Skype para Business Server 2019 e uma atualização cumulativa futura do Skype para Business Server 2015, você poderá executar a etapa 1 (mover usuários para Skype para Business Online) e a etapa 2 (atualização usuários às equipes) em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="3e78a-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="3e78a-123">Mais informações serão fornecidas após o lançamento do Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3e78a-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="3e78a-124">Atualização de sistema telefônico e equipes</span><span class="sxs-lookup"><span data-stu-id="3e78a-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="3e78a-125">Se você estiver fazendo a transição de seu Skype para implantação híbrida de negócios para o sistema telefônico com planos de chamada e Microsoft será seu provedor de (PSTN) da rede telefônica pública comutada — e assumindo que você tiver concluído o número de telefone portando — atualizando os usuários As equipes passará automaticamente PSTN de entrada chamando-se às equipes.</span><span class="sxs-lookup"><span data-stu-id="3e78a-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="3e78a-126">Se os planos de chamada não está disponível ou se você pretende usar seu provedor de conectividade PSTN existente, será necessário fazer a transição de sua implantação do enterprise voice — ou implantação de voz híbrida que usa as existentes no local implantação ou a edição de conector de nuvem — para Sistema telefônico Microsoft direcionar circulação.</span><span class="sxs-lookup"><span data-stu-id="3e78a-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="3e78a-127">Para atualizar seus usuários para equipes, consulte as [Considerações adicionais sobre roteamento direto de sistema do telefone](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="3e78a-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
