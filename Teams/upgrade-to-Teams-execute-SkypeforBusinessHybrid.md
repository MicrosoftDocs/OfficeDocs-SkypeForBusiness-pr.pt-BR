---
title: Atualizar a implantação híbrida do Skype for Business para o Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como atualizar sua organização para o Microsoft Teams a partir de uma implantação híbrida do Skype for Business.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 72786dc2ef5cefe7c3c87c5a376cc01d93a2c22c
ms.sourcegitcommit: b07938c0b6edafacaeaaef205a1be00c4c1693ba
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/16/2020
ms.locfileid: "47940511"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="df5de-103">Atualizar de uma implantação híbrida do Skype for Business para o Teams</span><span class="sxs-lookup"><span data-stu-id="df5de-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="df5de-104">![Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="df5de-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="df5de-105">Este artigo faz parte do estágio de implantação e implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="df5de-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="df5de-106">Antes de prosseguir, confirme que você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="df5de-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="df5de-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="df5de-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="df5de-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="df5de-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="df5de-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="df5de-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="df5de-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="df5de-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="df5de-111">Seu ambiente foi preparado</span><span class="sxs-lookup"><span data-stu-id="df5de-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="df5de-112">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="df5de-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="df5de-113">Conduziu um piloto</span><span class="sxs-lookup"><span data-stu-id="df5de-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="df5de-114">Siga as orientações neste artigo se você tiver implantado o Skype for Business ou o Microsoft Lync local e o configurou em uma implantação híbrida com a sua organização do Microsoft 365 ou do Office 365 e sua organização quiser atualizar para o Microsoft Teams, usando vários modos de coexistência, ou todos.</span><span class="sxs-lookup"><span data-stu-id="df5de-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="df5de-115">Para a viagem de atualização, você precisa mover seus usuários para o Skype for Business online (se eles ainda não estiverem online) e atribuí-los ao modo de coexistência e à atualização apropriados.</span><span class="sxs-lookup"><span data-stu-id="df5de-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="df5de-116">Etapa 1: mover usuários para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="df5de-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="df5de-117">Esta etapa se aplica a usuários que estão hospedados no momento no local.</span><span class="sxs-lookup"><span data-stu-id="df5de-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="df5de-118">Para obter mais informações sobre como mover esses usuários para o Skype for Business Online, consulte [mover usuários do local para o Skype for Business online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="df5de-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="df5de-119">Etapa 2: atribuir um modo de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="df5de-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="df5de-120">Depois de mover os usuários para o Skype for Business Online, você pode atribuir a eles o modo de coexistência apropriado com base na jornada de atualização que a sua organização escolheu.</span><span class="sxs-lookup"><span data-stu-id="df5de-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="df5de-121">Para obter mais informações, consulte [definindo suas configurações de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e a coexistência](upgrade-to-teams-on-prem-tools.md).</span><span class="sxs-lookup"><span data-stu-id="df5de-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="df5de-122">Com o Skype for Business Server 2019 e uma atualização cumulativa futura do Skype for Business Server 2015, você poderá executar a etapa 1 (movendo usuários para o Skype for Business online) e a etapa 2 (atualizar usuários para o Microsoft Teams) em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="df5de-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="df5de-123">Mais informações serão fornecidas após o lançamento do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="df5de-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="df5de-124">Atualização do sistema de telefonia e do teams</span><span class="sxs-lookup"><span data-stu-id="df5de-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="df5de-125">Se você estiver migrando sua implantação híbrida do Skype for Business para o sistema telefônico com planos de chamadas e a Microsoft for o seu provedor de rede telefônica pública comutada (PSTN) e pressupondo que você concluiu a portabilidade do número de telefone, a atualização de seus usuários para o Teams fará automaticamente a chamada PSTN de entrada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="df5de-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="df5de-126">Se os planos de chamada não estiverem disponíveis ou se você pretende usar seu provedor de conectividade PSTN existente, será necessário fazer a transição da implantação do Enterprise Voice, ou da implantação de voz híbrida que usa a implantação local existente ou a edição do conector de nuvem, para o roteamento direto do sistema de telefone da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="df5de-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="df5de-127">Para atualizar os usuários para o Microsoft Teams, consulte [considerações adicionais sobre o roteamento direto do sistema telefônico](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="df5de-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
