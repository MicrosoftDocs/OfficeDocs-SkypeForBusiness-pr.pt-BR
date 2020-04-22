---
title: Pré-requisitos do Microsoft Teams | Atualização de adoção de dependências
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
audience: admin
description: Use esta orientação para saber mais sobre os pré-requisitos e as dependências ambientais para implantar equipes em sua organização
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
ms.openlocfilehash: f340146225d7e386233e727bb8c5d181db7f15fb
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43776716"
---
# <a name="prerequisites-and-environmental-dependencies-for-teams"></a><span data-ttu-id="8b394-103">Pré-requisitos e dependências ambientais para equipes</span><span class="sxs-lookup"><span data-stu-id="8b394-103">Prerequisites and environmental dependencies for Teams</span></span>

<span data-ttu-id="8b394-104">![Atualize o diagrama de jornada, enfatizando o estágio de preparação técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada da atualização, com ênfase no estágio de preparação técnica")</span><span class="sxs-lookup"><span data-stu-id="8b394-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="8b394-105">Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário.</span><span class="sxs-lookup"><span data-stu-id="8b394-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="8b394-106">Antes de prosseguir, confirme que você concluiu essas atividades dos estágios anteriores:</span><span class="sxs-lookup"><span data-stu-id="8b394-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="8b394-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="8b394-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="8b394-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="8b394-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="8b394-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="8b394-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="8b394-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="8b394-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="8b394-111">O Teams combina vários serviços do Office 365 e, portanto, depende da implementação e operação corretas desses serviços.</span><span class="sxs-lookup"><span data-stu-id="8b394-111">Teams combines multiple Office 365 services, and is therefore dependent on the correct implementation and operation of these services.</span></span> <span data-ttu-id="8b394-112">Esses serviços incluem, entre outros, o SharePoint Online, o Exchange Online e o OneDrive for Business.</span><span class="sxs-lookup"><span data-stu-id="8b394-112">These services include—but aren't limited to—SharePoint Online, Exchange Online, and OneDrive for Business.</span></span>

<span data-ttu-id="8b394-113">Embora nem todos os serviços sejam necessários, é altamente recomendável que você implemente todos eles.</span><span class="sxs-lookup"><span data-stu-id="8b394-113">Although not all services are required, we highly recommend that you implement all of them.</span></span> <span data-ttu-id="8b394-114">Se você optar por não implementar determinados serviços, ele afetará a funcionalidade que as equipes podem oferecer à sua organização.</span><span class="sxs-lookup"><span data-stu-id="8b394-114">If you choose not to implement certain services, it will affect the functionality that Teams can offer your organization.</span></span> <span data-ttu-id="8b394-115">Por exemplo, embora você não precise implementar o SharePoint Online, o Teams depende do SharePoint Online para determinadas funcionalidades, como compartilhamento de arquivos em conversas em grupo, para que a implementação desse serviço reduza a funcionalidade oferecida por meio do cliente.</span><span class="sxs-lookup"><span data-stu-id="8b394-115">For example, though you don't have to implement SharePoint Online, Teams does rely on SharePoint Online for certain functionality such as file sharing in group conversations, so not implementing this service will reduce the functionality offered through the client.</span></span>

<span data-ttu-id="8b394-116">Consulte os artigos a seguir para saber mais sobre pré-requisitos e como o Microsoft Teams interage com outras tecnologias:</span><span class="sxs-lookup"><span data-stu-id="8b394-116">See the following articles to learn about prerequisites and how Teams interacts with other technologies:</span></span>

- <span data-ttu-id="8b394-117">Se sua organização ainda não implantou nenhuma carga de trabalho do Office 365, consulte [introdução ao office 365 para empresas](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span><span class="sxs-lookup"><span data-stu-id="8b394-117">If your organization hasn't deployed any Office 365 workloads, see [Getting Started with Office 365 for business](https://support.office.com/article/Get-started-with-Office-365-for-Business-d6466f0d-5d13-464a-adcb-00906ae87029).</span></span>

- <span data-ttu-id="8b394-118">Se a sua organização ainda não adicionou ou configurou um domínio verificado para o Office 365, consulte [verificar seu domínio do office 365](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span><span class="sxs-lookup"><span data-stu-id="8b394-118">If your organization hasn't added or configured a verified domain for Office 365, see [Verify your Office 365 domain](https://support.office.com/article/Verify-your-Office-365-domain-to-prove-ownership-nonprofit-or-education-status-or-to-activate-Yammer-87d1844e-aa47-4dc0-a61b-1b773fd4e590).</span></span>

- <span data-ttu-id="8b394-119">Se sua organização não tiver identidades sincronizadas com o Azure Active Directory, consulte [modelos de identidade e autenticação no Microsoft Teams](identify-models-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="8b394-119">If your organization hasn't synchronized identities to Azure Active Directory, see [Identity models and authentication in Microsoft Teams](identify-models-authentication.md).</span></span>

- <span data-ttu-id="8b394-120">Se a sua organização não tiver<sup>um</sup>Exchange Online, confira [entender como o Exchange e o Microsoft Teams interagem](Exchange-Teams-interact.md).</span><span class="sxs-lookup"><span data-stu-id="8b394-120">If your organization doesn<sup>1</sup>t have Exchange Online, see [Understand how Exchange and Microsoft Teams interact](Exchange-Teams-interact.md).</span></span>

- <span data-ttu-id="8b394-121">Se sua organização não tiver o SharePoint Online, confira [entender como o SharePoint Online e o onedrive for Business interagem com o Microsoft Teams](SharePoint-OneDrive-interact.md).</span><span class="sxs-lookup"><span data-stu-id="8b394-121">If your organization doesn't have SharePoint Online, see [Understand how SharePoint Online and OneDrive for Business interact with Microsoft Teams](SharePoint-OneDrive-interact.md).</span></span>

- <span data-ttu-id="8b394-122">Saiba como os [grupos do microsoft 365 e o Microsoft Teams interagem](Office-365-groups.md).</span><span class="sxs-lookup"><span data-stu-id="8b394-122">Learn how [Microsoft 365 groups and Microsoft Teams interact](Office-365-groups.md).</span></span>

- <span data-ttu-id="8b394-123">Se sua organização for uma instituição educacional e você usar um sistema de informações do aluno, [implante a sincronização de dados da escola](https://docs.microsoft.com/schooldatasync) antes de implantar o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="8b394-123">If your organization is an educational institution and you use a Student Information System, [deploy School Data Sync](https://docs.microsoft.com/schooldatasync) before deploying Microsoft Teams.</span></span>

<span data-ttu-id="8b394-124">Depois de verificar se o seu ambiente atende a todos os pré-requisitos aplicáveis, [avalie o ambiente atual do teams](upgrade-plan-journey-evaluate-environment.md).</span><span class="sxs-lookup"><span data-stu-id="8b394-124">After you've verified that your environment meets all applicable prerequisites, [evaluate your current environment for Teams](upgrade-plan-journey-evaluate-environment.md).</span></span>
