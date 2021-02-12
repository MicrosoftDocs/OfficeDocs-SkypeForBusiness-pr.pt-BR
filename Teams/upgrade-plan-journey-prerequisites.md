---
title: Pré-requisitos e dependências ambientais para a atualização para o Teams
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
ms.openlocfilehash: bcd3de45954ea500a6be0d325370ab0660604a65
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578274"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="ff593-103">Pré-requisitos e dependências ambientais do Teams</span><span class="sxs-lookup"><span data-stu-id="ff593-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="ff593-104">![Diagrama de atualização da jornada, enfatizando o estágio de Preparação Técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada de atualização, com ênfase no estágio de Preparação Técnica")</span><span class="sxs-lookup"><span data-stu-id="ff593-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="ff593-105">Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário.</span><span class="sxs-lookup"><span data-stu-id="ff593-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="ff593-106">Antes de prosseguir, confirme que você concluiu essas atividades de estágios anteriores:</span><span class="sxs-lookup"><span data-stu-id="ff593-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="ff593-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="ff593-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="ff593-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="ff593-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="ff593-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="ff593-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="ff593-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="ff593-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="ff593-111">O Teams combina vários serviços do Microsoft 365 e do Office 365 e, portanto, depende da implementação e operação correta desses serviços.</span><span class="sxs-lookup"><span data-stu-id="ff593-111">Teams combines multiple Microsoft 365 and Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="ff593-112">Esses serviços incluem— mas não estão limitados a — o SharePoint Online, o Exchange Online e o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="ff593-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="ff593-113">Embora nem todos os serviços sejam necessários, é altamente recomendável que você implemente todos eles.</span><span class="sxs-lookup"><span data-stu-id="ff593-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="ff593-114">Se você optar por não implementar determinados serviços, isso afetará a funcionalidade que o Teams pode oferecer à sua organização.</span><span class="sxs-lookup"><span data-stu-id="ff593-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="ff593-115">Por exemplo, embora você não tenha que implementar o SharePoint Online, o Teams depende do SharePoint Online para determinadas funcionalidades, como o compartilhamento de arquivos em conversas em grupo, portanto, não implementar esse serviço reduzirá a funcionalidade oferecida por meio do cliente.</span><span class="sxs-lookup"><span data-stu-id="ff593-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="ff593-116">Confira os artigos a seguir para saber mais sobre pré-requisitos e como o Teams interage com outras tecnologias:</span><span class="sxs-lookup"><span data-stu-id="ff593-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="ff593-117">Se sua organização não implantou cargas de trabalho do Microsoft 365 ou do Office 365, consulte [Começar.](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029)</span><span class="sxs-lookup"><span data-stu-id="ff593-117">If your organization hasn't deployed any Microsoft 365 or Office 365 workloads, see [Get started](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="ff593-118">Se sua organização não tiver adicionado ou configurado um domínio verificado para o Microsoft 365 ou o Office 365, consulte [Perguntas frequentes sobre Domínios.](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590)</span><span class="sxs-lookup"><span data-stu-id="ff593-118">If your organization hasn't added or configured a verified domain for Microsoft 365 or Office 365, see [Domains FAQ](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="ff593-119">Se sua organização não sincronizou identidades com o Azure Active Directory, consulte modelos de identidade e autenticação [no Microsoft Teams.](identify-models-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="ff593-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="ff593-120">Se sua organização não tiver o Exchange Online, veja [como o Exchange e o Microsoft Teams interagem.](Exchange-Teams-interact.md)</span><span class="sxs-lookup"><span data-stu-id="ff593-120">If your organization doesn't have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="ff593-121">Se sua organização não tiver o SharePoint Online, veja Como o SharePoint Online e o [OneDrive for Business interagem com o Microsoft Teams.](SharePoint-OneDrive-interact.md)</span><span class="sxs-lookup"><span data-stu-id="ff593-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="ff593-122">Para saber como os [grupos do Microsoft 365 e o Microsoft Teams interagem.](Office-365-groups.md)</span><span class="sxs-lookup"><span data-stu-id="ff593-122">To learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="ff593-123">Se sua organização for uma instituição de ensino e você usar um Sistema de Informações do Aluno, consulte Bem-vindo ao [Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) antes de implantar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ff593-123">If your organization is an educational institution and you use a Student Information System, see [Welcome to Microsoft School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

- <span data-ttu-id="ff593-124">Se a sua organização estiver considerando as opções de chamada PSTN (Rede Telefônica Pública Comutado), consulte Voz – Sistema de Telefonia e conectividade [PSTN,](cloud-voice-landing-page.md)qual plano de chamada é certo para você [e](calling-plan-landing-page.md)Roteamento Direto do Sistema de Telefonia. [](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="ff593-124">If your organization is considering Public Switched Telephone Network (PSTN) calling options, see [Voice - Phone System and PSTN connectivity](cloud-voice-landing-page.md), [Which Calling Plan is right for you](calling-plan-landing-page.md), and [Phone System Direct Routing](direct-routing-landing-page.md).</span></span>

- <span data-ttu-id="ff593-125">Para garantir que todos os requisitos de rede tenham sido atendidos antes de lançar o Teams, consulte Preparar a [rede da sua organização para o Microsoft Teams.](prepare-network.md)</span><span class="sxs-lookup"><span data-stu-id="ff593-125">To ensure all network requirements have been met before rolling out Teams, see [Prepare your organization's network for Microsoft Teams](prepare-network.md).</span></span>

<span data-ttu-id="ff593-126">Depois de verificar se seu ambiente atende a todos os pré-requisitos aplicáveis, avalie seu [ambiente atual para o Teams.](upgrade-plan-journey-evaluate-environment.md)</span><span class="sxs-lookup"><span data-stu-id="ff593-126">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
