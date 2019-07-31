---
title: Atualizar para o Microsoft Teams de uma implantação híbrida ou local do Skype for Business ‒ Microsoft Teams
author: lanachin
ms.author: v-lanac
manager: serdars
ms.date: 01/09/2019
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerações para a atualização do teams a partir de uma implantação híbrida ou local do Skype for Business.
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 731a6b30fe2476d180198e88f83e80f24c8e8227
ms.sourcegitcommit: 195a4e1bbab46034408a22d636874c10f797945a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/30/2019
ms.locfileid: "35934514"
---
<span data-ttu-id="292f0-103">![Atualize o diagrama de viagem, enfatizando implantação e implementação] (media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="292f0-103">![Upgrade journey diagram, emphasizing Deployment and Implementation](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="292f0-104">Este artigo faz parte do estágio de implantação e implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="292f0-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="292f0-105">Antes de prosseguir, confirme que você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="292f0-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="292f0-106">Listamos os participantes do projeto</span><span class="sxs-lookup"><span data-stu-id="292f0-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="292f0-107">Definiu o escopo do projeto</span><span class="sxs-lookup"><span data-stu-id="292f0-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="292f0-108">Compreendemos a coexistência e interoperabilidade do Skype for Business e do teams</span><span class="sxs-lookup"><span data-stu-id="292f0-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="292f0-109">Escolhido a jornada da atualização</span><span class="sxs-lookup"><span data-stu-id="292f0-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="292f0-110">Seu ambiente foi preparado</span><span class="sxs-lookup"><span data-stu-id="292f0-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="292f0-111">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="292f0-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="292f0-112">Conduziu um piloto</span><span class="sxs-lookup"><span data-stu-id="292f0-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

# <a name="upgrade-to-teams-from-a-skype-for-business-hybrid-or-on-premises-deployment"></a><span data-ttu-id="292f0-113">Atualize para o Teams a partir de uma implantação híbrida ou local do Skype for Business</span><span class="sxs-lookup"><span data-stu-id="292f0-113">Upgrade to Teams from a Skype for Business hybrid or on-premises deployment</span></span>

<span data-ttu-id="292f0-114">Siga as orientações neste artigo se você tiver implantado o Skype for Business ou o Microsoft Lync local e sua organização quiser atualizar para o Microsoft Teams de forma seletiva, usando vários modos de coexistência, ou todos.</span><span class="sxs-lookup"><span data-stu-id="292f0-114">Follow the guidance in this article if you’ve deployed Skype for Business or Microsoft Lync on-premises and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="292f0-115">A primeira etapa é configurar a conectividade híbrida com o seu locatário do Office 365 e, em seguida, mover os usuários para o Skype for Business Online e atribuir a eles o modo de atualização e a coexistência apropriada.</span><span class="sxs-lookup"><span data-stu-id="292f0-115">The first step is to set up hybrid connectivity with your Office 365 tenant, and then move your users to Skype for Business Online and assign them the appropriate coexistence and upgrade mode.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="292f0-116">O Skype for Business online será desativado em 31 de julho de 2021, após o qual ele não estará mais acessível ou compatível.</span><span class="sxs-lookup"><span data-stu-id="292f0-116">Skype for Business Online will be retired on July 31, 2021, after which it will no longer be accessible or supported.</span></span> <span data-ttu-id="292f0-117">Para maximizar a concretização de benefícios e garantir que sua organização tenha tempo adequado para implementar a sua atualização, recomendamos que você comece sua jornada ao Microsoft Teams hoje mesmo.</span><span class="sxs-lookup"><span data-stu-id="292f0-117">To maximize benefit realization and ensure your organization has proper time to implement your upgrade, we encourage you to begin your journey to Microsoft Teams today.</span></span> <span data-ttu-id="292f0-118">Lembre-se de que uma atualização bem-sucedida alinha a prontidão técnica e do usuário, portanto, não deixe de aproveitar as diretrizes contidas ao navegar na jornada para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="292f0-118">Remember that a successful upgrade aligns technical and user readiness, so be sure to leverage the guidance herein as you navigate your journey to Microsoft Teams.</span></span>

## <a name="step-1-deploy-hybrid-connectivity"></a><span data-ttu-id="292f0-119">Etapa 1: implantar a conectividade híbrida</span><span class="sxs-lookup"><span data-stu-id="292f0-119">Step 1: Deploy hybrid connectivity</span></span> 

<span data-ttu-id="292f0-120">O principal pré-requisito para atualizar os usuários para o Microsoft Teams é implantar a conectividade híbrida.</span><span class="sxs-lookup"><span data-stu-id="292f0-120">The key prerequisite for upgrading your users to Teams is to deploy hybrid connectivity.</span></span> <span data-ttu-id="292f0-121">Isso pode envolver a implantação de uma nova conectividade externa para a implantação existente do Skype for Business ou do Lync, ou simplesmente configurar uma relação híbrida com o seu locatário do Office 365.</span><span class="sxs-lookup"><span data-stu-id="292f0-121">This might involve deploying new external connectivity for your existing Skype for Business or Lync deployment, or simply configuring a hybrid relationship with your Office 365 tenant.</span></span> 

<span data-ttu-id="292f0-122">Para obter mais informações, consulte [implantar conectividade híbrida entre o Skype for Business Server e o Skype for Business online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span><span class="sxs-lookup"><span data-stu-id="292f0-122">For more information, see [Deploy hybrid connectivity between Skype for Business Server and Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/deploy-hybrid-connectivity).</span></span>

## <a name="step-2-move-users-to-skype-for-business-online"></a><span data-ttu-id="292f0-123">Etapa 2: mover usuários para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="292f0-123">Step 2: Move users to Skype for Business Online</span></span> 

<span data-ttu-id="292f0-124">Depois de concluir a configuração híbrida, mova os usuários para o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="292f0-124">After you’ve completed your hybrid setup, move users to Skype for Business Online.</span></span> 

<span data-ttu-id="292f0-125">Para obter mais informações, consulte [mover usuários do local para o Skype for Business online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="292f0-125">For more information, see [Move users from on premises to Skype for Business Online](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span> 

## <a name="step-3-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="292f0-126">Etapa 3: atribuir um modo de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="292f0-126">Step 3: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="292f0-127">Depois de mover os usuários para o Skype for Business Online, você pode atribuir a eles o modo de coexistência apropriado com base na jornada de atualização que a sua organização escolheu.</span><span class="sxs-lookup"><span data-stu-id="292f0-127">After you’ve moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="292f0-128">Para obter mais informações, consulte [definindo suas configurações de coexistência e atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence)a coexistência.</span><span class="sxs-lookup"><span data-stu-id="292f0-128">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

> [!NOTE]
> <span data-ttu-id="292f0-129">Com o Skype for Business Server 2019 e uma atualização cumulativa futura do Skype for Business Server 2015, você poderá executar a etapa 2 (movendo usuários para o Skype for Business online) e a etapa 3 (atualizar usuários para o Microsoft Teams) em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="292f0-129">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you’ll be able to perform Step 2 (moving users to Skype for Business Online) and Step 3 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="292f0-130">Mais informações serão fornecidas após o lançamento do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="292f0-130">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="292f0-131">Atualização do sistema de telefonia e do teams</span><span class="sxs-lookup"><span data-stu-id="292f0-131">Phone System and Teams upgrade</span></span>

<span data-ttu-id="292f0-132">Se você estiver fazendo a transição da sua implantação híbrida do Skype for Business para o sistema telefônico com planos de chamadas e a Microsoft for o seu provedor de rede telefônica pública comutada (PSTN) e presumir que você concluiu a portabilidade do número de telefone, a atualização dos usuários para O Microsoft Teams fará a transição de chamadas PSTN de entrada automaticamente para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="292f0-132">If you’re transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you’ve completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="292f0-133">Se os planos de chamada não estiverem disponíveis, você precisará fazer a transição de sua implantação do Enterprise Voice para o roteamento direto do Microsoft Phone System.</span><span class="sxs-lookup"><span data-stu-id="292f0-133">If Calling Plans isn’t available, you need to transition your enterprise voice deployment to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="292f0-134">Para atualizar os usuários para o Microsoft Teams, consulte [considerações adicionais sobre o roteamento direto do sistema telefônico](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="292f0-134">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
