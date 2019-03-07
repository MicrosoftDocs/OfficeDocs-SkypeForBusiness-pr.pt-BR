---
title: Pré-requisitos de equipes da Microsoft | Atualização de adoção de dependências
author: turgayo
ms.author: turgayo
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: turgayo
description: Use estas diretrizes para aprender sobre os pré-requisitos e as dependências de ambientais para implantar as equipes em sua organização
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 39483e7b3c8e511f2081f907b187d97dbbaf526f
ms.sourcegitcommit: 85c34280977fb2c15c8a43874a20e9492bdca57f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/07/2019
ms.locfileid: "30462040"
---
<span data-ttu-id="61a82-103">![Estágios da atualização jornada, com ênfase na etapa de preparação técnica] (media/upgrade-banner-tech-readiness.png "Estágios da atualização jornada, com ênfase na etapa de preparação técnica")</span><span class="sxs-lookup"><span data-stu-id="61a82-103">![Stages of the upgrade journey, with emphasis on the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="61a82-104">Este artigo faz parte do estágio de prontidão técnica de sua atualização jornada, uma atividade que você concluir em paralelo com o estágio de preparação do usuário.</span><span class="sxs-lookup"><span data-stu-id="61a82-104">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="61a82-105">Antes de continuar, confirme que você tiver concluído essas atividades desde estágios anteriores:</span><span class="sxs-lookup"><span data-stu-id="61a82-105">Before proceeding, confirm that you’ve completed these activities from previous stages:</span></span>

- [<span data-ttu-id="61a82-106">Inscrito seus participantes do projeto</span><span class="sxs-lookup"><span data-stu-id="61a82-106">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="61a82-107">Definido o escopo do projeto</span><span class="sxs-lookup"><span data-stu-id="61a82-107">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="61a82-108">Compreendidos coexistência e interoperabilidade do Skype para equipes e de negócios</span><span class="sxs-lookup"><span data-stu-id="61a82-108">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="61a82-109">Escolhido sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="61a82-109">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="61a82-110">Pré-requisitos e dependências de ambientais para equipes</span><span class="sxs-lookup"><span data-stu-id="61a82-110">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="61a82-111">As equipes combina vários serviços do Office 365 e, portanto, a implementação correta e a operação desses serviços dependentes.</span><span class="sxs-lookup"><span data-stu-id="61a82-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="61a82-112">Esses serviços incluem —, mas não está limitado a — Exchange Online, SharePoint Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="61a82-112">These services include—but aren’t limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="61a82-113">Embora nem todos os serviços forem necessários, é altamente recomendável que você implemente todos eles.</span><span class="sxs-lookup"><span data-stu-id="61a82-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="61a82-114">Se você optar por não implementar determinados serviços, ele afetará a funcionalidade que equipes podem oferecer a sua organização.</span><span class="sxs-lookup"><span data-stu-id="61a82-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="61a82-115">Por exemplo, embora você não precisa implementar o SharePoint Online, equipes baseiam-se no SharePoint Online para alguns recursos, como compartilhamento de arquivo no conversas do grupo, portanto, não implementar esse serviço reduzirá a funcionalidade oferecida por meio do cliente.</span><span class="sxs-lookup"><span data-stu-id="61a82-115">For example, though you don’t have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="61a82-116">Consulte os seguintes artigos para saber mais sobre os pré-requisitos e como equipes interage com outras tecnologias:</span><span class="sxs-lookup"><span data-stu-id="61a82-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="61a82-117">Se sua organização não tiver implantado nenhum cargas de trabalho do Office 365, consulte [Getting Started with Office 365 para empresas](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="61a82-117">If your organization hasn’t deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="61a82-118">Se sua organização não tiver adicionado ou configurado um domínio verificado para o Office 365, consulte [Verify seu domínio do Office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="61a82-118">If your organization hasn’t added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="61a82-119">Se sua organização não tiver sincronizado identidades para o Windows Azure Active Directory, consulte [modelos de identidade e autenticação no equipes da Microsoft](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="61a82-119">If your organization hasn’t synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="61a82-120">Se doesn¹t sua organização tiver o Exchange Online, consulte [Noções básicas sobre como o Exchange e equipes da Microsoft interagem](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="61a82-120">If your organization doesn¹t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="61a82-121">Se sua organização não tiver o SharePoint Online, consulte [Noções básicas sobre como o SharePoint Online e o OneDrive for Business interagem com as equipes da Microsoft](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="61a82-121">If your organization doesn’t have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="61a82-122">Saiba como [interagem grupos do Office 365 e equipes da Microsoft](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="61a82-122">Learn how [Office 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="61a82-123">Se sua organização é uma instituição educacional e usar um sistema de informações de Student, [Implante a sincronização de dados da escola](https://docs.microsoft.com/schooldatasync) antes de implantar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="61a82-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="61a82-124">Depois que você tiver verificado que seu ambiente atende aos pré-requisitos aplicáveis todos, [avaliar o ambiente atual para equipes](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="61a82-124">After you’ve verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>