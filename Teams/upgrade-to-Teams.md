---
title: Visão geral da implementação da atualização para o Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Determine o caminho de atualização ideal para o Microsoft Teams com base em sua implantação atual do Skype for Business.
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
ms.openlocfilehash: 3eb6c65d414217810c795aa72701a8e546f30643
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096025"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="74f76-103">Visão geral da implementação da atualização</span><span class="sxs-lookup"><span data-stu-id="74f76-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="74f76-104">![Estágios da jornada de atualização, com ênfase no estágio implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="74f76-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="74f76-105">Este artigo faz parte do estágio implantação e implementação de sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="74f76-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="74f76-106">Atividades de planejamento de pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="74f76-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="74f76-107">Antes de prosseguir com sua implementação de atualização, confirme se você leu o conteúdo de planejamento começando com Planejar sua atualização para garantir que você concluiu todos os pré-requisitos de planejamento de aactivites. [](upgrade-plan-journey.md)</span><span class="sxs-lookup"><span data-stu-id="74f76-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="74f76-108">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="74f76-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="74f76-109">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="74f76-109">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="74f76-110">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="74f76-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="74f76-111">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="74f76-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="74f76-112">Planejar um piloto de usuário</span><span class="sxs-lookup"><span data-stu-id="74f76-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="74f76-113">Preparou seu ambiente</span><span class="sxs-lookup"><span data-stu-id="74f76-113">Prepared your environment</span></span>](./upgrade-prepare-environment.md)
- [<span data-ttu-id="74f76-114">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="74f76-114">Prepared your organization</span></span>](./upgrade-prepare-organization.md)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="74f76-115">Escolha o ponto de partida da atualização</span><span class="sxs-lookup"><span data-stu-id="74f76-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="74f76-116">As etapas que você executa para executar a atualização para o Teams dependem da implantação atual do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="74f76-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="74f76-117">Com base no seu ambiente atual, escolha seu ponto de partida:</span><span class="sxs-lookup"><span data-stu-id="74f76-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="74f76-118">**Se você estiver atualizando** do Skype for Business Online para o Teams, siga as etapas em [Upgrade from Skype for Business Online to Teams](./upgrade-to-teams-execute-skypeforbusinessonline.md).</span><span class="sxs-lookup"><span data-stu-id="74f76-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](./upgrade-to-teams-execute-skypeforbusinessonline.md).</span></span>

-  <span data-ttu-id="74f76-119">Se você estiver atualizando de um ambiente local do **Skype for Business,** será necessário executar algumas etapas adicionais para configurar a conectividade entre seus ambientes locais e online antes de mover seus usuários para o Teams.</span><span class="sxs-lookup"><span data-stu-id="74f76-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="74f76-120">Para obter mais informações, [consulte Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span><span class="sxs-lookup"><span data-stu-id="74f76-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]