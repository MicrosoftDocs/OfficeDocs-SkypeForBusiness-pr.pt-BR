---
title: Atualização do Skype para negócios Online para equipes - equipes da Microsoft
author: arachmanGitHub
ms.author: arachman
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Considerações para a atualização para equipes do Skype para negócios Online
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 50c595643e9c6a1805c44676cfa38fd04beb11bb
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23883003"
---
<span data-ttu-id="f27a5-103">![Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação] (media/upgrade-banner-deployment.png "Estágios da atualização jornada, com ênfase sobre a implantação e o estágio de implementação")</span><span class="sxs-lookup"><span data-stu-id="f27a5-103">![Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage](media/upgrade-banner-deployment.png "Stages of the upgrade journey, with emphasis on the Deployment and Implementation stage")</span></span>

<span data-ttu-id="f27a5-104">Este artigo faz parte do estágio de implantação e a implementação da sua jornada de atualização.</span><span class="sxs-lookup"><span data-stu-id="f27a5-104">This article is part of Deployment and Implementation stage of your upgrade journey.</span></span> <span data-ttu-id="f27a5-105">Antes de continuar, confirme que você tiver concluído as seguintes atividades:</span><span class="sxs-lookup"><span data-stu-id="f27a5-105">Before proceeding, confirm that you’ve completed the following activities:</span></span>

-   [<span data-ttu-id="f27a5-106">Inscrito seus participantes do projeto</span><span class="sxs-lookup"><span data-stu-id="f27a5-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
-   [<span data-ttu-id="f27a5-107">Definido o escopo do projeto</span><span class="sxs-lookup"><span data-stu-id="f27a5-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
-   [<span data-ttu-id="f27a5-108">Compreendidos coexistência e interoperabilidade do Skype para equipes e de negócios</span><span class="sxs-lookup"><span data-stu-id="f27a5-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
-   [<span data-ttu-id="f27a5-109">Escolhido sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="f27a5-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)
-   [<span data-ttu-id="f27a5-110">Preparado o seu ambiente</span><span class="sxs-lookup"><span data-stu-id="f27a5-110">Prepared your environment</span></span>](https://aka.ms/SkypeToTeams-TechnicalReadiness)
-   [<span data-ttu-id="f27a5-111">Preparado sua organização</span><span class="sxs-lookup"><span data-stu-id="f27a5-111">Prepared your organization</span></span>](https://aka.ms/SkypeToTeams-UserReadiness)
-   [<span data-ttu-id="f27a5-112">Conduzido um piloto</span><span class="sxs-lookup"><span data-stu-id="f27a5-112">Conducted a pilot</span></span>](https://aka.ms/SkypeToTeams-Pilot)


# <a name="upgrade-from-skype-for-business-online-to-teams"></a><span data-ttu-id="f27a5-113">Atualização do Skype para negócios Online para equipes</span><span class="sxs-lookup"><span data-stu-id="f27a5-113">Upgrade from Skype for Business Online to Teams</span></span>

<span data-ttu-id="f27a5-114">Siga as orientações neste artigo se você implantou integralmente Skype para Business Online e deseja atualizar seus usuários do Skype for Business para equipes.</span><span class="sxs-lookup"><span data-stu-id="f27a5-114">Follow the guidance in this article if you have wholly deployed Skype for Business Online and want to upgrade your users from Skype for Business to Teams.</span></span> <span data-ttu-id="f27a5-115">Você pode atualizar usuários seletivamente ou tudo em, com base na atualização jornada que sua organização tenha escolhido, atribuindo-se o modo de atualização e coexistência apropriada para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="f27a5-115">You can upgrade users selectively or all-in, based on the upgrade journey that your organization has chosen, by assigning the appropriate coexistence and upgrade mode to your users.</span></span>

> [!IMPORTANT]
> [!INCLUDE [upgrade-disclaimer](includes/upgrade-disclaimer.md)]

## <a name="assign-the-coexistence-and-upgrade-mode"></a><span data-ttu-id="f27a5-116">Atribuir o modo de atualização e coexistência</span><span class="sxs-lookup"><span data-stu-id="f27a5-116">Assign the coexistence and upgrade mode</span></span>

<span data-ttu-id="f27a5-117">Atualizando para as equipes pode ser realizada, atribuindo-se o modo de TeamsOnly de TeamsUpgradePolicy, que pode ser realizada usando Microsoft Teams & Skype para o Centro de administração de empresa ou um Skype para sessão do Windows Powershell remoto de negócios.</span><span class="sxs-lookup"><span data-stu-id="f27a5-117">Upgrading to Teams can be accomplished by assigning the TeamsOnly mode of TeamsUpgradePolicy, which can be performed by using Microsoft Teams & Skype for Business Admin Center or a Skype for Business remote Windows Powershell session.</span></span>

<span data-ttu-id="f27a5-118">Para obter mais informações, consulte [definindo sua coexistência e as configurações de atualização](https://aka.ms/SkypeToTeams-SetCoexistence) e [TeamsUpgradePolicy: Gerenciando a migração e coexistência](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span><span class="sxs-lookup"><span data-stu-id="f27a5-118">For more information, see [Setting your coexistence and upgrade settings](https://aka.ms/SkypeToTeams-SetCoexistence) and [TeamsUpgradePolicy: managing migration and coexistence](migration-interop-guidance-for-teams-with-skype.md#teamsupgradepolicy-managing-migration-and-co-existence).</span></span>

## <a name="phone-system-and-teams-upgrade"></a><span data-ttu-id="f27a5-119">Atualização de sistema telefônico e equipes</span><span class="sxs-lookup"><span data-stu-id="f27a5-119">Phone System and Teams upgrade</span></span>

<span data-ttu-id="f27a5-120">Se seu Skype para implantação Business Online inclui o sistema telefônico com planos de chamada e a Microsoft tem o seu provedor de telefônica pública comutada (PSTN) de rede, atualizando seus usuários para equipes passará automaticamente PSTN de entrada chamando-se às equipes.</span><span class="sxs-lookup"><span data-stu-id="f27a5-120">If your Skype for Business Online deployment includes Phone System with Calling Plans and Microsoft is your public switched telephone network (PSTN) provider, upgrading your users to Teams will automatically transition inbound PSTN calling to Teams.</span></span>

<span data-ttu-id="f27a5-121">Se seu Skype para implantação Business Online inclui o sistema telefônico com nuvem conector Edition, consulte as [Considerações adicionais sobre roteamento direto de sistema do telefone](2-envision-make-my-service-decisions-direct-routing.md).</span><span class="sxs-lookup"><span data-stu-id="f27a5-121">If your Skype for Business Online deployment includes Phone System with Cloud Connector Edition, see the [additional considerations for Phone System Direct Routing](2-envision-make-my-service-decisions-direct-routing.md).</span></span>