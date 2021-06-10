---
title: Atualizar Skype for Business implantação híbrida para Teams
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba como atualizar sua organização para Microsoft Teams de uma implantação Skype for Business híbrida.
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
ms.openlocfilehash: 97725e7a9790f47f9789366567981f0167fdd806
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51104017"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="c88f9-103">Atualizar de uma implantação Skype for Business híbrida para Teams</span><span class="sxs-lookup"><span data-stu-id="c88f9-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="c88f9-104">![Estágios da jornada de atualização, com ênfase no estágio implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="c88f9-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="c88f9-105">Este artigo faz parte do estágio implantação e implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="c88f9-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="c88f9-106">Antes de prosseguir, confirme se você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="c88f9-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="c88f9-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="c88f9-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="c88f9-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="c88f9-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="c88f9-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="c88f9-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="c88f9-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="c88f9-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="c88f9-111">Preparou seu ambiente</span><span class="sxs-lookup"><span data-stu-id="c88f9-111">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="c88f9-112">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="c88f9-112">Prepared your organization</span></span>](./upgrade-prepare-organization.md)
- [<span data-ttu-id="c88f9-113">Conduzido um piloto</span><span class="sxs-lookup"><span data-stu-id="c88f9-113">Conducted a pilot</span></span>](./pilot-essentials.md)

<span data-ttu-id="c88f9-114">Siga as diretrizes deste artigo se você implantou o Skype for Business ou o Microsoft Lync local e configurou-o em uma implantação híbrida com sua organização do Microsoft 365 ou do Office 365, e sua organização deseja atualizar para o Teams de forma seletiva, usando vários modos de coexistência ou tudo.</span><span class="sxs-lookup"><span data-stu-id="c88f9-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="c88f9-115">Para uma jornada de atualização, você precisa mover seus usuários para Skype for Business Online (se eles ainda não estão online) e atribua a eles o modo de coexistência e atualização apropriado.</span><span class="sxs-lookup"><span data-stu-id="c88f9-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="c88f9-116">Etapa 1: mover os usuários para Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="c88f9-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="c88f9-117">Esta etapa se aplica aos usuários que estão atualmente no local.</span><span class="sxs-lookup"><span data-stu-id="c88f9-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="c88f9-118">Para obter mais informações sobre como mover esses usuários para Skype for Business Online, consulte [Move users from on-premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span><span class="sxs-lookup"><span data-stu-id="c88f9-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="c88f9-119">Etapa 2: Atribuir um modo de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="c88f9-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="c88f9-120">Depois de ter movido seus usuários para o Skype for Business Online, você pode atribuir a eles o modo de coexistência apropriado com base na jornada de atualização escolhida pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="c88f9-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="c88f9-121">Para obter mais informações, consulte [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span><span class="sxs-lookup"><span data-stu-id="c88f9-121">For more information, see [Setting your coexistence and upgrade settings](./setting-your-coexistence-and-upgrade-settings.md) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="c88f9-122">Com o Skype for Business Server 2019 e uma atualização cumulativa futura do Skype for Business Server 2015, você poderá executar a Etapa 1 (mover usuários para o Skype for Business Online) e a Etapa 2 (atualizar usuários para Teams) em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="c88f9-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="c88f9-123">Mais informações serão fornecidas depois que Skype for Business Server 2019 for lançado.</span><span class="sxs-lookup"><span data-stu-id="c88f9-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="c88f9-124">Sistema de Telefonia e Teams atualização</span><span class="sxs-lookup"><span data-stu-id="c88f9-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="c88f9-125">Se você estiver fazendo a transição da implantação híbrida do Skype for Business para o Sistema de Telefonia com Planos de Chamadas e a Microsoft será o provedor PSTN (rede telefônica pública comutado) e supondo que você concluiu a portação de número de telefone, atualizar seus usuários para o Teams fará a transição automática de chamadas PSTN de entrada para Teams.</span><span class="sxs-lookup"><span data-stu-id="c88f9-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="c88f9-126">Se Os Planos de Chamadas não estão disponíveis ou você pretende usar seu provedor de conectividade PSTN existente, você precisará fazer a transição da implantação de voz corporativa ou a implantação de voz híbrida que usa sua implantação local ou o Cloud Connector Edition existente para Telefone Microsoft Roteamento Direto do Sistema.</span><span class="sxs-lookup"><span data-stu-id="c88f9-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="c88f9-127">Para atualizar seus usuários para Teams, consulte as [considerações adicionais para Sistema de Telefonia Roteamento Direto.](./direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="c88f9-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](./direct-routing-landing-page.md).</span></span>