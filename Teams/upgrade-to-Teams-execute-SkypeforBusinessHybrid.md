---
title: Atualizar a implantação híbrida do Skype for Business para o Teams
author: cichur
ms.author: v-cichur
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
ms.openlocfilehash: 67bb6c10bb8cc5f37d332459d8e147f4f626497d
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802341"
---
# <a name="upgrade-from-a-skype-for-business-hybrid-deployment-to-teams"></a><span data-ttu-id="3e7bb-103">Atualizar de uma implantação híbrida do Skype for Business para o Teams</span><span class="sxs-lookup"><span data-stu-id="3e7bb-103">Upgrade from a Skype for Business hybrid deployment to Teams</span></span>

<span data-ttu-id="3e7bb-104">![Estágios da jornada de atualização, com ênfase no estágio de Implantação e Implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio de Implantação e Implementação")</span><span class="sxs-lookup"><span data-stu-id="3e7bb-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="3e7bb-105">Este artigo faz parte da etapa implantação e implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="3e7bb-105">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="3e7bb-106">Antes de prosseguir, confirme que você concluiu as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="3e7bb-106">Before proceeding, confirm that you've completed the following activities:</span></span>

- [<span data-ttu-id="3e7bb-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="3e7bb-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="3e7bb-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="3e7bb-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="3e7bb-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="3e7bb-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="3e7bb-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="3e7bb-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="3e7bb-111">Preparou seu ambiente</span><span class="sxs-lookup"><span data-stu-id="3e7bb-111">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="3e7bb-112">Preparar sua organização</span><span class="sxs-lookup"><span data-stu-id="3e7bb-112">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
- [<span data-ttu-id="3e7bb-113">Piloto conduzido</span><span class="sxs-lookup"><span data-stu-id="3e7bb-113">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)

<span data-ttu-id="3e7bb-114">Siga as orientações neste artigo se você implantou o Skype for Business ou o Microsoft Lync local e configurou-o em uma implantação híbrida com sua organização do Microsoft 365 ou do Office 365, e sua organização deseja atualizar para o Teams seletivamente, usando vários modos de coexistência ou tudo.</span><span class="sxs-lookup"><span data-stu-id="3e7bb-114">Follow the guidance in this article if you've deployed Skype for Business or Microsoft Lync on-premises and configured it in a hybrid deployment with your Microsoft 365 or Office 365 organization, and your organization wants to upgrade to Teams either selectively—by using multiple coexistence modes—or all-in.</span></span> <span data-ttu-id="3e7bb-115">Para uma viagem de atualização, você precisa mover os usuários para o Skype for Business Online (se eles ainda não estão online) e atribuir a eles a coexistência e o modo de atualização apropriados.</span><span class="sxs-lookup"><span data-stu-id="3e7bb-115">For either upgrade journey, you need to move your users to Skype for Business Online (if they aren't already homed online) and then assign them the appropriate coexistence and upgrade mode.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="step-1-move-users-to-skype-for-business-online"></a><span data-ttu-id="3e7bb-116">Etapa 1: mover usuários para o Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="3e7bb-116">Step 1: Move users to Skype for Business Online</span></span>

<span data-ttu-id="3e7bb-117">Esta etapa se aplica aos usuários que estão atualmente no local.</span><span class="sxs-lookup"><span data-stu-id="3e7bb-117">This step applies to users who are currently homed on-premises.</span></span> <span data-ttu-id="3e7bb-118">Para obter mais informações sobre como mover esses usuários para o Skype for Business Online, consulte Mover usuários locais para [o Skype for Business Online.](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online)</span><span class="sxs-lookup"><span data-stu-id="3e7bb-118">For more information about moving these users to Skype for Business Online, see [Move users from on -premises to Skype for Business Online](/skypeforbusiness/skype-for-business-hybrid-solutions/deploy-hybrid-connectivity/move-users-from-on-premises-to-skype-for-business-online).</span></span>

## <a name="step-2-assign-a-coexistence-and-upgrade-mode"></a><span data-ttu-id="3e7bb-119">Etapa 2: Atribuir um modo de coexistência e atualização</span><span class="sxs-lookup"><span data-stu-id="3e7bb-119">Step 2: Assign a coexistence and upgrade mode</span></span>

<span data-ttu-id="3e7bb-120">Depois de mudar seus usuários para o Skype for Business Online, você pode atribuir a eles o modo de coexistência apropriado com base na jornada de atualização escolhida pela sua organização.</span><span class="sxs-lookup"><span data-stu-id="3e7bb-120">After you've moved your users to Skype for Business Online, you can assign them the appropriate coexistence mode based on the upgrade journey that your organization has chosen.</span></span> <span data-ttu-id="3e7bb-121">Para obter mais informações, consulte [Definir suas configurações](https://aka.ms/SkypeToTeams-SetCoexistence) de coexistência e atualização e [TeamsUpgradePolicy: gerenciamento de migração e coexistência.](upgrade-to-teams-on-prem-tools.md)</span><span class="sxs-lookup"><span data-stu-id="3e7bb-121">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](upgrade-to-teams-on-prem-tools.md).</span></span>

> [!NOTE]
> <span data-ttu-id="3e7bb-122">Com o Skype for Business Server 2019 e uma futura atualização cumulativa do Skype for Business Server 2015, você poderá executar a Etapa 1 (mover usuários para o Skype for Business Online) e a Etapa 2 (atualizar usuários para o Teams) em uma única etapa.</span><span class="sxs-lookup"><span data-stu-id="3e7bb-122">With Skype for Business Server 2019 and a future cumulative update of Skype for Business Server 2015, you'll be able to perform Step 1 (moving users to Skype for Business Online) and Step 2 (upgrade users to Teams) in a single step.</span></span> <span data-ttu-id="3e7bb-123">Mais informações serão fornecidas após o lançamento do Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="3e7bb-123">More information will be provided after Skype for Business Server 2019 is released.</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="3e7bb-124">Atualização do Sistema de Telefonia e do Teams</span><span class="sxs-lookup"><span data-stu-id="3e7bb-124">Phone System and Teams upgrade</span></span>

<span data-ttu-id="3e7bb-125">Se você estiver fazendo a transição da implantação híbrida do Skype for Business para o Sistema telefônico com Planos de Chamada e a Microsoft for seu provedor de PSTN (rede telefônica pública comutado) e supondo que você concluiu a portagem de número de telefone, atualizar os usuários para o Teams fará a transição de chamadas PSTN de entrada automaticamente para o Teams.</span><span class="sxs-lookup"><span data-stu-id="3e7bb-125">If you're transitioning your Skype for Business hybrid deployment to Phone System with Calling Plans and Microsoft will be your public switched telephone network (PSTN) provider—and assuming that you've completed the phone number porting—upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="3e7bb-126">Se os Planos de Chamada não estão disponíveis ou se você pretende usar seu provedor de conectividade PSTN existente, será necessário fazer a transição da implantação de voz corporativa ou a implantação de voz híbrida que usa a implantação local ou o Cloud Connector Edition existente para o Roteamento Direto do Sistema de Telefonia do Microsoft Phone.</span><span class="sxs-lookup"><span data-stu-id="3e7bb-126">If Calling Plans isn't available or you intend to use your existing PSTN connectivity provider, you need to transition your enterprise voice deployment—or hybrid voice deployment that uses your existing on-premises deployment or Cloud Connector Edition—to Microsoft Phone System Direct Routing.</span></span> <span data-ttu-id="3e7bb-127">Para atualizar seus usuários para o Teams, consulte as considerações [adicionais sobre o Roteamento Direto do Sistema de Telefonia.](2-envision-make-my-service-decisions-direct-routing.md)</span><span class="sxs-lookup"><span data-stu-id="3e7bb-127">To upgrade your users to Teams, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>
