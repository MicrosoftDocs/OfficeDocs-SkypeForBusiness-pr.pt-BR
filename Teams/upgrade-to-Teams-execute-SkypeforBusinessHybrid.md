---
title: Atualizar a implantação híbrida do Skype for Business para o Microsoft Teams | PSTN
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Considerações para a atualização do teams a partir de uma implantação híbrida do Skype for Business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7729cd65ff5d58d348229c4ec5ec6182f06aa5de
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36235896"
---
<span data-ttu-id="b2626-103">![Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação] (media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="b2626-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="b2626-104">Este artigo faz parte do estágio de implantação e implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="b2626-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="b2626-105">Antes de prosseguir, confirme que você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="b2626-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

- [<span data-ttu-id="b2626-106">Listamos os participantes do projeto</span><span class="sxs-lookup"><span data-stu-id="b2626-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="b2626-107">Definiu o escopo do projeto</span><span class="sxs-lookup"><span data-stu-id="b2626-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="b2626-108">Compreendemos a coexistência e interoperabilidade do Skype for Business e do teams</span><span class="sxs-lookup"><span data-stu-id="b2626-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="b2626-109">Escolhido a jornada da atualização</span><span class="sxs-lookup"><span data-stu-id="b2626-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="b2626-110">Seu ambiente foi preparado</span><span class="sxs-lookup"><span data-stu-id="b2626-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="b2626-111">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="b2626-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="b2626-112">Conduziu um piloto</span><span class="sxs-lookup"><span data-stu-id="b2626-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="b2626-113">Atualizar de uma implantação híbrida do Skype for Business para o Teams</span><span class="sxs-lookup"><span data-stu-id="b2626-113">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="b2626-114">Siga as orientações neste artigo se você tiver implantado o Skype for Business ou o Microsoft Lync local e o configurou em uma implantação híbrida com o seu locatário do Office 365 e sua organização quiser atualizar para as equipes seletivamente — usando vários modos de coexistência — ou todos.</span><span class="sxs-lookup"><span data-stu-id="b2626-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Office 365 tenant, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="b2626-115">Para a viagem de atualização, você precisa mover seus usuários para o Skype for Business online (se eles ainda não estiverem online) e atribuí-los ao modo de coexistência e à atualização apropriados.</span><span class="sxs-lookup"><span data-stu-id="b2626-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren’t already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="b2626-116">Etapa 1: mover usuários para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="b2626-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="b2626-117">Esta etapa se aplica a usuários que estão hospedados no momento no local.</span><span class="sxs-lookup"><span data-stu-id="b2626-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="b2626-118">Para obter mais informações sobre como mover esses usuários para o Skype for Business Online, consulte [mover usuários do local para o Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="b2626-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="b2626-119">Etapa 2: atribuir um modo de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="b2626-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="b2626-120">Depois de mover os usuários para o Skype for Business Online, você pode atribuir a eles o modo de coexistência apropriado com base na jornada de atualização que a sua organização escolheu.</span><span class="sxs-lookup"><span data-stu-id="b2626-120">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="b2626-121">Para obter mais informações, consulte [definindo suas configurações de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)a coexistência.</span><span class="sxs-lookup"><span data-stu-id="b2626-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="b2626-122">Com o Skype for Business Server 2019 e uma atualização cumulativa futura do Skype for Business Server 2015, você poderá executar a etapa 1 (movendo usuários para o Skype for Business online) e a etapa 2 (atualizar usuários para o Microsoft Teams) em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="b2626-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="b2626-123">Mais informações serão fornecidas após o lançamento do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="b2626-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="b2626-124">Atualização do sistema de telefonia e do teams</span><span class="sxs-lookup"><span data-stu-id="b2626-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="b2626-125">Se você estiver fazendo a transição da sua implantação híbrida do Skype for Business para o sistema telefônico com planos de chamadas e a Microsoft for o seu provedor de rede telefônica pública comutada (PSTN) e presumir que você concluiu a portabilidade do número de telefone, a atualização dos usuários para O Microsoft Teams fará a transição de chamadas PSTN de entrada automaticamente para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b2626-125">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="b2626-126">Se os planos de chamada não estiverem disponíveis ou se você pretende usar seu provedor de conectividade PSTN existente, é preciso fazer a transição de sua implantação de voz empresarial ou a implantação de voz híbrida que usa a implantação local existente ou a edição do conector de nuvem, para Encaminhamento direto do sistema telefônico da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b2626-126">If Calling Plans isn’t available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="b2626-127">Para atualizar os usuários para o Microsoft Teams, consulte [considerações adicionais sobre o roteamento direto do sistema telefônico](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="b2626-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
