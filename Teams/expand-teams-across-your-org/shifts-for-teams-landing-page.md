---
title: Turnos do Teams
description: Obtenha as diretrizes de administração necessárias para configurar e gerenciar turnos, a ferramenta de gerenciamento de agendamento no Teams.
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
# <a name="shifts-for-teams"></a><span data-ttu-id="ad12f-103">Turnos do Teams</span><span class="sxs-lookup"><span data-stu-id="ad12f-103">Shifts for Teams</span></span>

<span data-ttu-id="ad12f-104">O Microsoft Teams oferece aos Frontline funcionários de sua organização as ferramentas de que precisam para se comunicar e colaborar de maneira eficaz.</span><span class="sxs-lookup"><span data-stu-id="ad12f-104">Teams gives Frontline Workers in your organization the tools they need to communicate and collaborate effectively.</span></span> <span data-ttu-id="ad12f-105">Este artigo mostra como configurar e gerenciar.</span><span class="sxs-lookup"><span data-stu-id="ad12f-105">This article shows you how to set up and manage.</span></span> <span data-ttu-id="ad12f-106">Alternar e usar a ferramenta de gerenciamento de agendamento no Teams.</span><span class="sxs-lookup"><span data-stu-id="ad12f-106">Shifts and use the schedule management tool in Teams.</span></span>

### <a name="set-up-and-manage-shifts-for-your-organization"></a><span data-ttu-id="ad12f-107">Configurar e gerenciar turnos para sua organização</span><span class="sxs-lookup"><span data-stu-id="ad12f-107">Set up and manage Shifts for your organization</span></span>

|               |               |               |               |
| ------------- | ------------- | ------------- | ------------- |
|![lista de verificação de tarefas-planejamento-equipes](../media/task-checklist-planning-teams-small.svg) | <span data-ttu-id="ad12f-109">**[Gerenciar turnos em sua organização](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span><span class="sxs-lookup"><span data-stu-id="ad12f-109">**[Manage Shifts in your organization](/microsoftteams/expand-teams-across-your-org/shifts/manage-the-shifts-app-for-your-organization-in-teams)**</span></span> |![Formula](../media/Help-small.svg)  | <span data-ttu-id="ad12f-111">**[Ajuda de turnos para trabalhadores do Frontline](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span><span class="sxs-lookup"><span data-stu-id="ad12f-111">**[Shifts Help for Frontline Workers](https://support.office.com/article/apps-and-services-cc1fba57-9900-4634-8306-2360a40c665b#PickTab=Specific_apps)**</span></span> |

### <a name="shifts-extensions"></a><span data-ttu-id="ad12f-112">Extensões de turnos</span><span class="sxs-lookup"><span data-stu-id="ad12f-112">Shifts extensions</span></span>

|               |               |
| ------------- | ------------- |
| ![API](../media/api-small.svg) | <span data-ttu-id="ad12f-114">**[APIs de gráfico de deslocamento](/graph/api/resources/shift?view=graph-rest-1.0)** As APIs de gráfico de turnos permitem que você integre dados de turnos a sistemas de gerenciamento de força de equipe externos.</span><span class="sxs-lookup"><span data-stu-id="ad12f-114">**[Shift Graph APIs](/graph/api/resources/shift?view=graph-rest-1.0)** Shifts Graph APIs allow you to integrate Shifts data with external workforce management systems.</span></span> <span data-ttu-id="ad12f-115">Você terá a flexibilidade para criar experiências de turnos personalizados no back-end, ao mesmo tempo que permite aos usuários uma experiência rica e de front-end no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ad12f-115">You'll have the flexibility to build custom Shifts experiences in the back end, while giving users a rich, front-end experience in Teams.</span></span>             |
| ![API](../media/api-small.svg) | <span data-ttu-id="ad12f-117">**[Integrações de gerenciamento da força de obra](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** Se você estiver usando sistemas de gerenciamento de força de equipe de terceiros, como o Kronos e o JDA, para agendamento, tempo e presença, você pode se integrar diretamente com as APIs de gráficos de turnos e o SDK com integrações de fonte aberta.</span><span class="sxs-lookup"><span data-stu-id="ad12f-117">**[Workforce management integrations](https://github.com/OfficeDev/Microsoft-Teams-Shifts-WFM-Connectors)** If you're using third-party workforce management systems, such as Kronos and JDA, for scheduling, time, and attendance, you can integrate directly with Shifts through Shifts Graph APIs and SDK with open source integrations.</span></span> |
| ![API](../media/process-flow-teams-small.svg) | <span data-ttu-id="ad12f-119">**[Turnos + energia automatizada](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shift + Power Automate permite que você tire informações de turnos e crie fluxos de trabalho personalizados com outros aplicativos e realize operações em escala.</span><span class="sxs-lookup"><span data-stu-id="ad12f-119">**[Shifts + Power Automate](https://github.com/OfficeDev/Microsoft-Teams-Shifts-Power-Automate-Templates)** Shifts + Power Automate lets you take info from Shifts and create custom workflows with other apps and perform operations at scale.</span></span> <span data-ttu-id="ad12f-120">Automatize os principais processos com pouco ou nenhum código.</span><span class="sxs-lookup"><span data-stu-id="ad12f-120">Automate key processes with little to no code.</span></span> <span data-ttu-id="ad12f-121">Os disparadores e os modelos dão suporte a uma variedade de cenários, como habilitar aprovações automáticas para pedidos de turno quando a aprovação de um gerente não é necessária.</span><span class="sxs-lookup"><span data-stu-id="ad12f-121">The triggers and templates support a variety of scenarios such as enabling auto-approvals for shift requests when a manager’s approval isn't needed.</span></span> |

## <a name="featured-training"></a><span data-ttu-id="ad12f-122">Treinamento em destaque</span><span class="sxs-lookup"><span data-stu-id="ad12f-122">Featured training</span></span>

|               |               |               |               |               |               |
| ------------- | ------------- | ------------- | ------------- | ------------- | ------------- |
| ![seta-direita-2-equipes](../media/arrow-right-2-teams-small.svg)  |  [<span data-ttu-id="ad12f-124">Vídeo: o que é turnos?</span><span class="sxs-lookup"><span data-stu-id="ad12f-124">Video: What is Shifts?</span></span>](https://support.office.com/article/what-is-shifts-f8efe6e4-ddb3-4d23-b81b-bb812296b821) |![relógio-equipes](../media/clock-teams-small.svg)  |  [<span data-ttu-id="ad12f-126">Vídeo: o que é turnos?</span><span class="sxs-lookup"><span data-stu-id="ad12f-126">Video: What is Shifts?</span></span>](https://support.office.com/article/create-a-shifts-schedule-2b94ca38-36db-4a1c-8fee-f8f0fec9a984) |![blocos-equipes](../media/blocks-teams-small.svg)  |  [<span data-ttu-id="ad12f-128">Vídeo: gerenciar um cronograma de turnos</span><span class="sxs-lookup"><span data-stu-id="ad12f-128">Video: Manage a Shifts schedule</span></span>](https://support.office.com/article/manage-a-shifts-schedule-63acda7b-ea39-441a-b1c6-c404a72e79f7) |
