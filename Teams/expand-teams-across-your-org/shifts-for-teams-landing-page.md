---
title: Turnos do Teams
description: Receba as orientações de administrador que você precisa para configurar e gerenciar o Shifts, a ferramenta de gerenciamento de cronograma, no Teams.
ms.topic: conceptual
author: cichur
ms.author: v-cichur
audience: admin
manager: serdars
f1.keywords:
- NOCSH
ms.date: 03/29/2019
ms.service: msteams
ms.collection:
- M365-collaboration
- Teams_ITAdmin_FLW
- microsoftcloud-healthcare
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: f699b60bddba6bcf5ffa884760540e5c20378f81
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909215"
---
# <a name="shifts-for-teams"></a><span data-ttu-id="b1588-103">Turnos do Teams</span><span class="sxs-lookup"><span data-stu-id="b1588-103">Shifts for Teams</span></span>

<span data-ttu-id="b1588-104">O Teams oferece aos Trabalhadores da Linha de Frente em sua organização as ferramentas necessárias para se comunicar e colaborar de forma eficaz.</span><span class="sxs-lookup"><span data-stu-id="b1588-104">Teams gives Frontline Workers in your organization the tools they need to communicate and collaborate effectively.</span></span> <span data-ttu-id="b1588-105">Este artigo mostra como configurar e gerenciar.</span><span class="sxs-lookup"><span data-stu-id="b1588-105">This article shows you how to set up and manage.</span></span> <span data-ttu-id="b1588-106">Shifts e use a ferramenta de gerenciamento de cronograma no Teams.</span><span class="sxs-lookup"><span data-stu-id="b1588-106">Shifts and use the schedule management tool in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="b1588-107">Configurar e gerenciar Turnos para sua organização</span><span class="sxs-lookup"><span data-stu-id="b1588-107">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![equipes de planejamento de lista de tarefas](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="b1588-109">**[Gerenciar Turnos em sua organização](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span><span class="sxs-lookup"><span data-stu-id="b1588-109">**[Manage Shifts in your organization](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span></span> |![Design](../media/Help-small.svg)  | <span data-ttu-id="b1588-111">**[Ajuda do Turnos para Trabalhadores da Linha de Frente](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="b1588-111">**[Shifts Help for Frontline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="b1588-112">Extensões de turnos</span><span class="sxs-lookup"><span data-stu-id="b1588-112">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![Api](../media/api-small.svg) | <span data-ttu-id="b1588-114">**[APIs do Shift Graph](/graph/api/resources/shift?view=graph-rest-1.0)** As APIs do Shifts Graph permitem integrar dados do Shifts com sistemas de gerenciamento de força de trabalho externos.</span><span class="sxs-lookup"><span data-stu-id="b1588-114">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems.</span></span> <span data-ttu-id="b1588-115">Você terá a flexibilidade de criar experiências personalizadas do Shifts no back-end, ao mesmo tempo que oferece aos usuários uma experiência completa e completa no Teams.</span><span class="sxs-lookup"><span data-stu-id="b1588-115">You'll have the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![Api](../media/api-small.svg) | <span data-ttu-id="b1588-117">**[Integrações de gerenciamento de força de trabalho](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** Se você estiver usando sistemas de gerenciamento de força de trabalho de terceiros, como Kronos e JDA, para agendamento, tempo e presença, você pode integrar diretamente com o Shifts por meio de APIs e SDK do Shifts Graph com integrações de open source.</span><span class="sxs-lookup"><span data-stu-id="b1588-117">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![Api](../media/process-flow-teams-small.svg) | <span data-ttu-id="b1588-119">**[Shifts+Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate permite que você pegue informações do Shifts e crie fluxos de trabalho personalizados com outros aplicativos e execute operações em escala.</span><span class="sxs-lookup"><span data-stu-id="b1588-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="b1588-120">Automatize os principais processos com pouco ou nenhum código.</span><span class="sxs-lookup"><span data-stu-id="b1588-120">Automate key processes with little to no code.</span></span> <span data-ttu-id="b1588-121">Os gatilhos e modelos suportam uma variedade de cenários, como a habilitação de aprovações automáticas para solicitações de turno quando não for necessária a aprovação de um gerente.</span><span class="sxs-lookup"><span data-stu-id="b1588-121">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="b1588-122">Treinamento em destaque</span><span class="sxs-lookup"><span data-stu-id="b1588-122">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![seta para a direita-2-equipes](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="b1588-124">Vídeo: O que é o Shifts?</span><span class="sxs-lookup"><span data-stu-id="b1588-124">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![time-teams de relógio](../media/clock-teams-small.svg)  |  [<span data-ttu-id="b1588-126">Vídeo: O que é o Shifts?</span><span class="sxs-lookup"><span data-stu-id="b1588-126">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![blocos de equipes](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="b1588-128">Vídeo: Gerenciar um cronograma do Turnos</span><span class="sxs-lookup"><span data-stu-id="b1588-128">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
