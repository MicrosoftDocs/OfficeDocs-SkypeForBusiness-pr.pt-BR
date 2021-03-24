---
title: Pré-requisitos e dependências ambientais para atualizar para o Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Use esta orientação para saber mais sobre os pré-requisitos e as dependências ambientais para implantar o Teams em sua organização
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 6ceca08be6d69a10fe84daa64d0da4e31c61c67c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51092189"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="36baa-103">Pré-requisitos e dependências ambientais do Teams</span><span class="sxs-lookup"><span data-stu-id="36baa-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="36baa-104">![Atualizar diagrama de jornada, enfatizando o estágio de Preparação Técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada de atualização, com ênfase no estágio de Preparação Técnica")</span><span class="sxs-lookup"><span data-stu-id="36baa-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="36baa-105">Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário.</span><span class="sxs-lookup"><span data-stu-id="36baa-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="36baa-106">Antes de prosseguir, confirme se você concluiu essas atividades de estágios anteriores:</span><span class="sxs-lookup"><span data-stu-id="36baa-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="36baa-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="36baa-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="36baa-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="36baa-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="36baa-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="36baa-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="36baa-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="36baa-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="36baa-111">O Teams combina vários serviços do Microsoft 365 e do Office 365 e, portanto, depende da implementação correta e da operação desses serviços.</span><span class="sxs-lookup"><span data-stu-id="36baa-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="36baa-112">Esses serviços incluem— mas não estão limitados a — SharePoint Online, Exchange Online e OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="36baa-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="36baa-113">Embora nem todos os serviços sejam necessários, é altamente recomendável implementar todos eles.</span><span class="sxs-lookup"><span data-stu-id="36baa-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="36baa-114">Se você optar por não implementar determinados serviços, isso afetará a funcionalidade que o Teams pode oferecer à sua organização.</span><span class="sxs-lookup"><span data-stu-id="36baa-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="36baa-115">Por exemplo, embora você não tenha que implementar o SharePoint Online, o Teams depende do SharePoint Online para determinada funcionalidade, como o compartilhamento de arquivos em conversas em grupo, portanto, a não implementação desse serviço reduzirá a funcionalidade oferecida pelo cliente.</span><span class="sxs-lookup"><span data-stu-id="36baa-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="36baa-116">Consulte os artigos a seguir para saber mais sobre os pré-requisitos e como o Teams interage com outras tecnologias:</span><span class="sxs-lookup"><span data-stu-id="36baa-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="36baa-117">Se sua organização não implantou cargas de trabalho do Microsoft 365 ou office 365, consulte [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="36baa-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="36baa-118">Se sua organização não tiver adicionado ou configurado um domínio verificado para o Microsoft 365 ou Office 365, consulte [Perguntas frequentes sobre domínios.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)</span><span class="sxs-lookup"><span data-stu-id="36baa-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="36baa-119">Se sua organização não tiver sincronizado identidades com o Azure Active Directory, consulte [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="36baa-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="36baa-120">Se sua organização não tiver o Exchange Online, consulte [Entenda como o Exchange e o Microsoft Teams interagem.](Exchange-Teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="36baa-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="36baa-121">Se sua organização não tiver o SharePoint Online, consulte Entenda como o SharePoint Online e [o OneDrive for Business interagem com o Microsoft Teams.](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="36baa-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="36baa-122">Para saber como os [grupos do Microsoft 365 e o Microsoft Teams interagem](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="36baa-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="36baa-123">Se sua organização for uma instituição educacional e você usar um Sistema de Informações do Aluno, consulte [Welcome to Microsoft School Data Sync](/schooldatasync) before deploying Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="36baa-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="36baa-124">Se sua organização estiver considerando as opções de chamadas PSTN (Rede Telefônica Pública Comugada), consulte Voice - Phone System and [PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan](calling-plan-landing-page.md)is right for you , and Phone System Direct [Routing](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="36baa-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="36baa-125">Para garantir que todos os requisitos de rede tenham sido atendidos antes de lançar o Teams, consulte [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span><span class="sxs-lookup"><span data-stu-id="36baa-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

- <span data-ttu-id="36baa-126">Se você estiver usando o Conector do Skype for Business Online para gerenciar seus serviços, será necessário mover para o módulo do PowerShell do Teams e atualizar os scripts existentes do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="36baa-126">If you are currently using Skype for Business Online Connector to manage your services, you will need to move to the Teams PowerShell module and update your existing PowerShell scripts.</span></span> <span data-ttu-id="36baa-127">Consulte [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span><span class="sxs-lookup"><span data-stu-id="36baa-127">See [Move from Skype for Business Online Connector to the Teams PowerShell module](teams-powershell-move-from-sfbo.md) for more information.</span></span>

<span data-ttu-id="36baa-128">Depois de verificar se seu ambiente atende a todos os pré-requisitos aplicáveis, avalie seu ambiente [atual para o Teams](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="36baa-128">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>