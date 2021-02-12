---
title: Visão geral da implementação da atualização para o Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Determine o caminho ideal de atualização para o Microsoft Teams com base na sua implantação atual do Skype for Business.
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
# <a name="overview-of-implementing-your-upgrade"></a><span data-ttu-id="b67a2-103">Visão geral da implementação da atualização</span><span class="sxs-lookup"><span data-stu-id="b67a2-103">Overview of implementing your upgrade</span></span>

<span data-ttu-id="b67a2-104">![Estágios da jornada de atualização, com ênfase no estágio de Implantação e Implementação](media/upgrade-banner-deployment.png "Estágios da jornada de atualização, com ênfase no estágio de Implantação e Implementação")</span><span class="sxs-lookup"><span data-stu-id="b67a2-104">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="b67a2-105">Este artigo faz parte da etapa implantação e implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="b67a2-105">This article is part of the Deployment and Implementation stage of your upgrade journey.</span></span> 



## <a name="prerequisite-planning-activities"></a><span data-ttu-id="b67a2-106">Atividades de planejamento de pré-requisitos</span><span class="sxs-lookup"><span data-stu-id="b67a2-106">Prerequisite planning activities</span></span>

> [!IMPORTANT]
> <span data-ttu-id="b67a2-107">Antes de prosseguir com sua implementação de atualização, confirme que você leu o conteúdo de planejamento começando com Planejar sua [atualização](upgrade-plan-journey.md) para garantir que você concluiu todos os activites de planejamento de pré-requisitos.</span><span class="sxs-lookup"><span data-stu-id="b67a2-107">Before proceeding with your upgrade implementation, confirm that you've read the planning content starting with [Plan your upgrade](upgrade-plan-journey.md) to ensure you've completed all prerequisite planning activites.</span></span>


- [<span data-ttu-id="b67a2-108">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="b67a2-108">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="b67a2-109">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="b67a2-109">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="b67a2-110">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="b67a2-110">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="b67a2-111">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="b67a2-111">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
- [<span data-ttu-id="b67a2-112">Piloto de usuário planejado</span><span class="sxs-lookup"><span data-stu-id="b67a2-112">Planned a user pilot</span></span>](pilot-essentials.md)
- [<span data-ttu-id="b67a2-113">Preparou seu ambiente</span><span class="sxs-lookup"><span data-stu-id="b67a2-113">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
- [<span data-ttu-id="b67a2-114">Preparar sua organização</span><span class="sxs-lookup"><span data-stu-id="b67a2-114">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)

## <a name="choose-your-upgrade-starting-point"></a><span data-ttu-id="b67a2-115">Escolha o ponto de partida da atualização</span><span class="sxs-lookup"><span data-stu-id="b67a2-115">Choose your upgrade starting point</span></span>

<span data-ttu-id="b67a2-116">As etapas que você tomar para realizar a atualização para o Teams dependem da sua implantação atual do Skype for Business:</span><span class="sxs-lookup"><span data-stu-id="b67a2-116">The steps you take to perform your upgrade to Teams depends on your current deployment of Skype for Business:</span></span>

<span data-ttu-id="b67a2-117">Com base no ambiente atual, escolha o ponto de partida:</span><span class="sxs-lookup"><span data-stu-id="b67a2-117">Based on your current environment, choose your starting point:</span></span>  

- <span data-ttu-id="b67a2-118">**Se você estiver atualizando** do Skype for Business Online para o Teams, siga as etapas em Atualizar do [Skype for Business Online para o Teams.](https://aka.ms/SkypeToTeams-UpgradeOnline)</span><span class="sxs-lookup"><span data-stu-id="b67a2-118">**If you are upgrading from Skype for Business Online to Teams**, follow the steps in [Upgrade from Skype for Business Online to Teams](https://aka.ms/SkypeToTeams-UpgradeOnline).</span></span>

-  <span data-ttu-id="b67a2-119">Se estiver atualizando de um ambiente local do **Skype for Business,** você precisará executar algumas etapas adicionais para configurar a conectividade entre seus ambientes locais e online antes de mover os usuários para o Teams.</span><span class="sxs-lookup"><span data-stu-id="b67a2-119">**If you are upgrading from a Skype for Business on-premises environment**, you'll need to perform some extra steps to set up connectivity between your on-premises and online environments before you move your users to Teams.</span></span> <span data-ttu-id="b67a2-120">Para obter mais informações, [consulte Atualizar o Skype for Business local para o Teams.](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md)</span><span class="sxs-lookup"><span data-stu-id="b67a2-120">For more information, see [Upgrade Skype for Business on-premises to Teams](upgrade-to-teams-execute-SkypeforBusinessHybridOnPrem.md).</span></span>





> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]
