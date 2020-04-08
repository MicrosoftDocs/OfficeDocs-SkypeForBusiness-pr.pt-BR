---
title: Início rápido do administrador – reuniões e eventos ao vivo no Microsoft Teams
ms.reviewer: ''
description: Comece a trabalhar rapidamente com reuniões e eventos ao vivo no Microsoft Teams.
ms.topic: article
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
- remotework
localization_priority: Priority
search.appverid: MET150
appliesto:
- Microsoft Teams
ms.openlocfilehash: 65ce8eb17efe434f5da288b89485e813b21190e4
ms.sourcegitcommit: f3390e27bb63b66d1c4fb4f8afbda6b814fbbb5b
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/07/2020
ms.locfileid: "43170479"
---
# <a name="admin-quick-start---meetings-and-live-events-in-microsoft-teams"></a><span data-ttu-id="ed234-103">Início rápido do administrador – reuniões e eventos ao vivo no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ed234-103">Admin quick start - Meetings and live events in Microsoft Teams</span></span>

<span data-ttu-id="ed234-104">Há duas maneiras de se reunir no Microsoft Teams – reuniões e eventos ao vivo.</span><span class="sxs-lookup"><span data-stu-id="ed234-104">There are 2 ways to meet in Microsoft Teams - meetings and live events.</span></span> <span data-ttu-id="ed234-105">Use este artigo para implementar e configurar reuniões e eventos ao vivo na sua organização rapidamente.</span><span class="sxs-lookup"><span data-stu-id="ed234-105">Use this article to quickly roll out and configure meetings and live events for your organization.</span></span> 

 - <span data-ttu-id="ed234-106">As **reuniões** no Teams incluem áudio, vídeo e compartilhamento de tela para até 250 pessoas.</span><span class="sxs-lookup"><span data-stu-id="ed234-106">**Meetings** in Teams include audio, video, and screen sharing for up to 250 people.</span></span> <span data-ttu-id="ed234-107">Elas são uma das principais maneiras de colaboração no Teams.</span><span class="sxs-lookup"><span data-stu-id="ed234-107">They're one of the key ways to collaborate in Teams.</span></span> <span data-ttu-id="ed234-108">E não é necessário ser membro de uma organização (nem mesmo ter uma conta do Teams!) para participar de uma reunião do Teams – basta verificar no convite as instruções sobre como ingressar.</span><span class="sxs-lookup"><span data-stu-id="ed234-108">And you don't need to be a member of an organization (or even have a Teams account!) to join a Teams meeting—just look in the invitation for instructions about calling in.</span></span> 

 - <span data-ttu-id="ed234-109">Os **eventos ao vivo** são uma extensão das reuniões do Teams e permitem agendar e produzir eventos que podem ser transmitidos para grandes públicos online – até 10.000 pessoas.</span><span class="sxs-lookup"><span data-stu-id="ed234-109">**Live events** are an extension of Teams meetings that enable you to schedule and produce events that stream to large online audiences - up to 10,000 people.</span></span> <span data-ttu-id="ed234-110">Se você precisar de uma reunião para mais de 250 pessoas, use um evento ao vivo.</span><span class="sxs-lookup"><span data-stu-id="ed234-110">If you need a meeting for more than 250 people, use a live event.</span></span>

## <a name="get-licenses-for-meetings-and-live-events"></a><span data-ttu-id="ed234-111">Obter licenças para reuniões e eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="ed234-111">Get licenses for meetings and live events</span></span>

<span data-ttu-id="ed234-112">Todos podem participar de uma reunião ou evento ao vivo do Teams gratuitamente – não é necessário ter uma licença.</span><span class="sxs-lookup"><span data-stu-id="ed234-112">Anyone can attend a Teams meeting or live event for free - no license is required.</span></span> <span data-ttu-id="ed234-113">Os participantes ingressam em uma reunião ou evento ao vivo do Teams clicando no botão **Ingressar** no Teams ou no convite da reunião.</span><span class="sxs-lookup"><span data-stu-id="ed234-113">Attendees join a Teams meeting or live event by clicking the **Join** button in Teams or the meeting invitation.</span></span> <span data-ttu-id="ed234-114">O áudio da reunião faz parte das reuniões do Teams, mas se você quiser que as pessoas possam ingressar em uma reunião por telefone, você precisará fornecer um número de discagem.</span><span class="sxs-lookup"><span data-stu-id="ed234-114">Meeting audio is part of a Teams meeting, but if you want people to be able to dial in to a meeting by phone, you'll need to provide a dial-in number.</span></span> 

<span data-ttu-id="ed234-115">As pessoas que irão organizar, agendar e hospedar reuniões ou eventos ao vivo precisarão de uma das licenças do Microsoft 365 ou do Office 365 listadas na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="ed234-115">For the people who will organize, schedule, and host meetings or live events, they'll need one of the Microsoft 365 or Office 365 licenses listed in the table below.</span></span> <span data-ttu-id="ed234-116">Se você já estiver usando o Teams, provavelmente você já tem a licença necessária para organizar e hospedar reuniões e eventos ao vivo.</span><span class="sxs-lookup"><span data-stu-id="ed234-116">If you're already using Teams, you probably have the license you need for organizing and hosting meetings and live events.</span></span> 

:::image type="content" source="media/quick-start-meetings-live-events-image1.png" alt-text="Tabela com as licenças necessárias para reuniões ou eventos ao vivo do Teams":::

> <span data-ttu-id="ed234-118"><sup>1</sup> Os organizadores da reunião precisam ter uma [Licença complementar de audioconferência](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) para enviar um convite que inclua conferências discadas.</span><span class="sxs-lookup"><span data-stu-id="ed234-118"><sup>1</sup>  Meeting organizers need to have an [Audio Conferencing add-on license](teams-add-on-licensing/microsoft-teams-add-on-licensing.md) to send an invite that includes dial-in conferencing.</span></span>
>
> <span data-ttu-id="ed234-119"><sup>2</sup>  A discagem de reunião para um número [**Ligar para mim em**](set-up-the-call-me-feature-for-your-users.md) exige que os organizadores tenham uma licença de suplemento de audioconferência E5 ou [](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="ed234-119"><sup>2</sup>  Meeting dial out to a [**Call me at** number](set-up-the-call-me-feature-for-your-users.md) requires organizers to have an E5 or [Audio Conference add-in license](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).</span></span> <span data-ttu-id="ed234-120">Um [plano de discagem](what-are-dial-plans.md) também pode ser necessário.</span><span class="sxs-lookup"><span data-stu-id="ed234-120">A [dial plan](what-are-dial-plans.md) may also be needed.</span></span> 


<span data-ttu-id="ed234-121">Para saber mais sobre o licenciamento, leia [Licenciamento do Office 365 para o Teams](Office-365-licensing.md).</span><span class="sxs-lookup"><span data-stu-id="ed234-121">To learn more about licensing, read [Office 365 licensing for Teams](Office-365-licensing.md).</span></span> 

## <a name="make-sure-your-networks-ready"></a><span data-ttu-id="ed234-122">Certifique-se de que a rede esteja pronta</span><span class="sxs-lookup"><span data-stu-id="ed234-122">Make sure your network's ready</span></span>

<span data-ttu-id="ed234-123">Se você já preparou a sua rede quando implantou o Microsoft 365 ou o Office 365, provavelmente está tudo pronto.</span><span class="sxs-lookup"><span data-stu-id="ed234-123">If you already prepared your network when you rolled out Microsoft 365 or Office 365, you're probably all set.</span></span> <span data-ttu-id="ed234-124">De qualquer forma, especialmente se você estiver implantando o Teams rapidamente como sua primeira carga de trabalho do Office 365 para oferecer **suporte a trabalhadores remotos** - leia [Preparar a rede da organização para o Teams](prepare-network.md) para garantir que você esteja pronto.</span><span class="sxs-lookup"><span data-stu-id="ed234-124">In any case - and especially if you're rolling out Teams quickly as your first Office 365 workload to support **remote workers** - read [Prepare your organization's network for Teams](prepare-network.md) to be sure you're ready.</span></span>

## <a name="meetings-and-conferencing"></a><span data-ttu-id="ed234-125">Reuniões e conferências</span><span class="sxs-lookup"><span data-stu-id="ed234-125">Meetings and conferencing</span></span>

- <span data-ttu-id="ed234-126">Como administrador, você definirá as [configurações de reunião](meeting-settings-in-teams.md) para todos.</span><span class="sxs-lookup"><span data-stu-id="ed234-126">As the admin, you'll configure [meeting settings](meeting-settings-in-teams.md) for everyone.</span></span> <span data-ttu-id="ed234-127">Em seguida, você usará [políticas de reunião](meeting-policies-in-teams.md) para controlar quais recursos de reunião estão (e não estão) disponíveis para seus usuários.</span><span class="sxs-lookup"><span data-stu-id="ed234-127">Then you'll use [meeting policies](meeting-policies-in-teams.md) to control what meeting features are (and aren't) available for your users.</span></span> 

- <span data-ttu-id="ed234-128">Para saber mais sobre como gerenciar a gravação da reunião, leia [Gravação de reunião na nuvem do Teams](cloud-recording.md).</span><span class="sxs-lookup"><span data-stu-id="ed234-128">To learn about managing meeting recording, read [Teams cloud meeting recording](cloud-recording.md).</span></span>

- <span data-ttu-id="ed234-129">Se os usuários não estiverem familiarizados com as reuniões do Teams, compartilhe o treinamento de [Gerenciamento de reuniões](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) com eles.</span><span class="sxs-lookup"><span data-stu-id="ed234-129">If your users are new to Teams meetings, share the [Manage meetings](https://support.office.com/article/join-a-teams-meeting-078e9868-f1aa-4414-8bb9-ee88e9236ee4) training with them.</span></span> <span data-ttu-id="ed234-130">Confira nossa aula online ministrada por instrutor, [Realizar reuniões eficientes com o Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span><span class="sxs-lookup"><span data-stu-id="ed234-130">Check out our instructor-led online class, [Run effective meetings with Teams](https://microsoftteams.eventbuilder.com/MaximizingTeamsMeetings).</span></span>

- <span data-ttu-id="ed234-131">Para saber mais sobre como gerenciar as opções de reunião, leia [Alterar as configurações de participante de uma reunião do Teams](https://support.microsoft.com/office/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span><span class="sxs-lookup"><span data-stu-id="ed234-131">To learn about managing meeting options, read [Change participant settings for a Teams meeting](https://support.microsoft.com/office/change-participant-settings-for-a-teams-meeting-53261366-dbd5-45f9-aae9-a70e6354f88e).</span></span>

- <span data-ttu-id="ed234-132">Não se esqueça de [gerenciar os dispositivos dos usuários](device-management.md) - telefones, headsets, câmeras.</span><span class="sxs-lookup"><span data-stu-id="ed234-132">Don't forget about [managing your users' devices](device-management.md) - phones, headsets, cameras.</span></span> <span data-ttu-id="ed234-133">Para obter as informações mais recentes e atualizadas sobre os dispositivos certificados pelo Teams, acesse [Dispositivos do Teams](https://office.com/teamsdevices).</span><span class="sxs-lookup"><span data-stu-id="ed234-133">To get the latest and up-to-date information on Teams certified devices, go to [Teams devices](https://office.com/teamsdevices).</span></span>

## <a name="live-events"></a><span data-ttu-id="ed234-134">Eventos ao vivo</span><span class="sxs-lookup"><span data-stu-id="ed234-134">Live events</span></span>

- <span data-ttu-id="ed234-135">Da mesma forma como nas reuniões, você, o administrador, [configura eventos ao vivo](teams-live-events/configure-teams-live-events.md) para todos.</span><span class="sxs-lookup"><span data-stu-id="ed234-135">Similar to meetings, you - the admin - [configure live events](teams-live-events/configure-teams-live-events.md) for everyone.</span></span> <span data-ttu-id="ed234-136">Em seguida, configure (e atribua) [políticas de evento ao vivo](teams-live-events/set-up-for-teams-live-events.md) para controlar o que seus usuários podem (e não podem) fazer.</span><span class="sxs-lookup"><span data-stu-id="ed234-136">Then set up (and assign) [live event policies](teams-live-events/set-up-for-teams-live-events.md) to control what your users can (and can't) do.</span></span>

- <span data-ttu-id="ed234-137">Certifique-se de que seus produtores e organizadores de eventos ao vivo estejam treinados - recomende que eles leiam [Comece a usar os eventos ao vivo](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span><span class="sxs-lookup"><span data-stu-id="ed234-137">Make sure your live event producers and organizers are trained - send them to [Get started with live events](https://support.office.com/article/get-started-with-microsoft-teams-live-events-d077fec2-a058-483e-9ab5-1494afda578a).</span></span>

- <span data-ttu-id="ed234-138">Se você não tiver experiência com os eventos ao vivo, confira [O que são os eventos ao vivo do Teams?](teams-live-events/what-are-teams-live-events.md) e [Preparar-se para os eventos ao vivo do Teams](teams-live-events/plan-for-teams-live-events.md).</span><span class="sxs-lookup"><span data-stu-id="ed234-138">If you're new to live events, check out [What are Teams live events?](teams-live-events/what-are-teams-live-events.md) and [Plan for Teams live events](teams-live-events/plan-for-teams-live-events.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="ed234-139">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="ed234-139">Related topics</span></span>

[<span data-ttu-id="ed234-140">Reuniões e conferências no Teams</span><span class="sxs-lookup"><span data-stu-id="ed234-140">Meetings and conferencing in Teams</span></span>](deploy-meetings-microsoft-teams-landing-page.md)

[<span data-ttu-id="ed234-141">Audioconferência no Teams</span><span class="sxs-lookup"><span data-stu-id="ed234-141">Audio conferencing in Teams</span></span>](deploy-audio-conferencing-teams-landing-page.md)

[<span data-ttu-id="ed234-142">Eventos ao vivo no Teams</span><span class="sxs-lookup"><span data-stu-id="ed234-142">Live events in Teams</span></span>](teams-live-events/what-are-teams-live-events.md)

[<span data-ttu-id="ed234-143">Especificações e limites do Teams</span><span class="sxs-lookup"><span data-stu-id="ed234-143">Limits and specifications for Teams</span></span>](limits-specifications-teams.md)

[<span data-ttu-id="ed234-144">Comunidade Técnica da Microsoft: eventos ao vivo no Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="ed234-144">Microsoft Technical Community: Live events in Microsoft 365</span></span>](https://resources.techcommunity.microsoft.com/live-events/)