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
ms.openlocfilehash: 0db2e752bb163f806c5dcba7aa56fc36bae7c2ef
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578354"
---
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="532c8-103">Visão geral da implementação da atualização</span><span class="sxs-lookup"><span data-stu-id="532c8-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="532c8-104">![Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação](media/upgrade-banner-deployment.png "Estágios da jornada da atualização, com ênfase no estágio de implantação e implementação")</span><span class="sxs-lookup"><span data-stu-id="532c8-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="532c8-105">Este artigo faz parte do estágio de implantação e implementação de sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="532c8-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="532c8-106">Atividades de planejamento de pré-requisito</span><span class="sxs-lookup"><span data-stu-id="532c8-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="532c8-107">Antes de prosseguir com a implementação de atualização, confirme se você leu o conteúdo de planejamento começando com [planejar a atualização](upgrade-plan-journey.md) para garantir que todas as atividades de planejamento de pré-requisito sejam concluídas.</span><span class="sxs-lookup"><span data-stu-id="532c8-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="532c8-108">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="532c8-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="532c8-109">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="532c8-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="532c8-110">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="532c8-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="532c8-111">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="532c8-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="532c8-112">Planejou um piloto de usuário</span><span class="sxs-lookup"><span data-stu-id="532c8-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="532c8-113">Seu ambiente foi preparado</span><span class="sxs-lookup"><span data-stu-id="532c8-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="532c8-114">Preparou sua organização</span><span class="sxs-lookup"><span data-stu-id="532c8-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="532c8-115">Escolha o ponto de partida da atualização</span><span class="sxs-lookup"><span data-stu-id="532c8-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="532c8-116">As etapas que você executa para executar a atualização do teams depende da sua implantação atual do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="532c8-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="532c8-117">Com base em seu ambiente atual, escolha seu ponto de partida:</span><span class="sxs-lookup"><span data-stu-id="532c8-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="532c8-118">**Se você estiver atualizando do Skype for Business online para o Microsoft Teams**, siga as etapas em [Atualizar do Skype for Business online para o Microsoft Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span><span class="sxs-lookup"><span data-stu-id="532c8-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="532c8-119">**Se estiver atualizando a partir de um ambiente local do Skype for Business**, você precisará realizar algumas etapas adicionais para configurar a conectividade entre seus ambientes locais e online antes de mover os usuários para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="532c8-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="532c8-120">Para obter mais informações, consulte [atualizar o Skype for Business no local para o Microsoft Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span><span class="sxs-lookup"><span data-stu-id="532c8-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
