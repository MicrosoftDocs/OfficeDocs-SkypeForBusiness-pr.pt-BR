---
title: Introdução à gravação baseada em políticas de equipe para fazer chamadas & reuniões
author: microsoftheidi
ms.author: heidip
manager: serdars
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre a gravação baseada em políticas de equipe para fazer chamadas & reuniões
f1.keywords:
- CSH
ms.custom:
- Adopt
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_Adopt
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cc09323e7f0a25f0f7c7083307776ad1a08bf4fb
ms.sourcegitcommit: e0ed3b6478918c4737648e6c27eb01de0b622b0e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/19/2020
ms.locfileid: "44294046"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="538d9-103">Introdução à gravação baseada em políticas de equipe para chamadas & reuniões</span><span class="sxs-lookup"><span data-stu-id="538d9-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="538d9-104">A gravação baseada em políticas permite que as organizações que adotarem o Microsoft Teams para fazer chamadas e reuniões sejam exigidas, usando uma política administrativa, quando chamadas e reuniões online devem ser automaticamente gravadas e capturadas para processamento e retenção subsequentes, conforme exigido pela política corporativa ou normativa pertinente.</span><span class="sxs-lookup"><span data-stu-id="538d9-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="538d9-105">O Microsoft Teams foi aprimorado para dar suporte à integração de soluções de gravação de terceiros, incluindo funcionalidade da plataforma, experiências do usuário e interfaces administrativas necessárias para fornecer uma solução completa para a configuração, o gerenciamento, a gravação, o armazenamento e a análise de comunicações do teams.</span><span class="sxs-lookup"><span data-stu-id="538d9-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="538d9-106">Isso inclui APIs e eventos de plataforma de comunicações para gravação, o que fornece:</span><span class="sxs-lookup"><span data-stu-id="538d9-106">This includes communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="538d9-107">Captura de mídia de alta qualidade e contínua entre dispositivos e todos os pontos de extremidade compatíveis para áudio, vídeo, compartilhamento de tela e chat.</span><span class="sxs-lookup"><span data-stu-id="538d9-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="538d9-108">Suporte para captura de interação entre usuários do Teams e pontos de extremidade com suporte (Teams, Mobile Teams, Skype for Business, PSTN)</span><span class="sxs-lookup"><span data-stu-id="538d9-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="538d9-109">Novas políticas administrativas para a gravação de conformidade, incluindo a integração com as ferramentas de reunião e as ferramentas de reunião e as políticas de reunião existentes</span><span class="sxs-lookup"><span data-stu-id="538d9-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

- <span data-ttu-id="538d9-110">Habilitado para usuários do teams com uma licença separada</span><span class="sxs-lookup"><span data-stu-id="538d9-110">Enabled for Teams users with a separate license</span></span>

<span data-ttu-id="538d9-111">Os recursos de integração da solução de gravação de conformidade também foram revisados em Ignite 2019 na [<span class="underline">sessão de gravação de conformidade e Microsoft Teams</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span><span class="sxs-lookup"><span data-stu-id="538d9-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.techcommunity.microsoft.com/sessions/83184?source=sessions).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="538d9-112">Visão geral da gravação de interação do teams</span><span class="sxs-lookup"><span data-stu-id="538d9-112">Teams interaction recording overview</span></span>

<span data-ttu-id="538d9-113">Casos de uso de gravação de interação podem ser efetivamente separados em quatro categorias principais de funcionalidade de gravação – conveniência, funcional, organizacional e interceptação legal, conforme mostrado na imagem:</span><span class="sxs-lookup"><span data-stu-id="538d9-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="538d9-114">![Captura de tela mostrando a interação gravando o que e por quê.](media/recording-taxonomy.png "A imagem mostra as categorias de gravação.")</span><span class="sxs-lookup"><span data-stu-id="538d9-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="538d9-115">Cada uma das categorias envolve diferentes requisitos para a forma como as gravações são iniciadas, o que é gravado, em que as gravações são armazenadas, quem é notificado, quem controla o acesso e como a retenção é manipulada.</span><span class="sxs-lookup"><span data-stu-id="538d9-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

|                        | <span data-ttu-id="538d9-116">Transtorno</span><span class="sxs-lookup"><span data-stu-id="538d9-116">Convenience</span></span>        | <span data-ttu-id="538d9-117">Funcional</span><span class="sxs-lookup"><span data-stu-id="538d9-117">Functional</span></span>         | <span data-ttu-id="538d9-118">Org-geral</span><span class="sxs-lookup"><span data-stu-id="538d9-118">Org - General</span></span>      | <span data-ttu-id="538d9-119">Regulamentado pela organização</span><span class="sxs-lookup"><span data-stu-id="538d9-119">Org - Regulated</span></span> | <span data-ttu-id="538d9-120">Interceptação legal</span><span class="sxs-lookup"><span data-stu-id="538d9-120">Lawful Intercept</span></span>   |
| ---------------------- | ------------------ | ------------------ | ------------------ | --------------- | ------------------ |
| <span data-ttu-id="538d9-121">Inicia</span><span class="sxs-lookup"><span data-stu-id="538d9-121">Initiator</span></span>              | <span data-ttu-id="538d9-122">Usuário</span><span class="sxs-lookup"><span data-stu-id="538d9-122">User</span></span>               | <span data-ttu-id="538d9-123">Aplicativo/solução</span><span class="sxs-lookup"><span data-stu-id="538d9-123">App/Solution</span></span>       | <span data-ttu-id="538d9-124">Administrador (sistema)</span><span class="sxs-lookup"><span data-stu-id="538d9-124">Admin (system)</span></span>     | <span data-ttu-id="538d9-125">Administrador (sistema)</span><span class="sxs-lookup"><span data-stu-id="538d9-125">Admin (system)</span></span>  | <span data-ttu-id="538d9-126">LEA</span><span class="sxs-lookup"><span data-stu-id="538d9-126">LEA</span></span>                |
| <span data-ttu-id="538d9-127">Destino </span><span class="sxs-lookup"><span data-stu-id="538d9-127">Target</span></span>                 | <span data-ttu-id="538d9-128">Por chamada/reunião</span><span class="sxs-lookup"><span data-stu-id="538d9-128">Per-call / meeting</span></span> | <span data-ttu-id="538d9-129">Por chamada/reunião</span><span class="sxs-lookup"><span data-stu-id="538d9-129">Per-call / meeting</span></span> | <span data-ttu-id="538d9-130">Por chamada/reunião</span><span class="sxs-lookup"><span data-stu-id="538d9-130">Per-call / meeting</span></span> | <span data-ttu-id="538d9-131">Por usuário</span><span class="sxs-lookup"><span data-stu-id="538d9-131">Per-user</span></span>        | <span data-ttu-id="538d9-132">Por ponto de extremidade/DID</span><span class="sxs-lookup"><span data-stu-id="538d9-132">Per-endpoint / DID</span></span> |
| <span data-ttu-id="538d9-133">Proprietário do armazenamento</span><span class="sxs-lookup"><span data-stu-id="538d9-133">Storage owner</span></span>          | <span data-ttu-id="538d9-134">Usuário</span><span class="sxs-lookup"><span data-stu-id="538d9-134">User</span></span>               | <span data-ttu-id="538d9-135">AppV</span><span class="sxs-lookup"><span data-stu-id="538d9-135">App</span></span>                | <span data-ttu-id="538d9-136">Locatário</span><span class="sxs-lookup"><span data-stu-id="538d9-136">Admin</span></span>              | <span data-ttu-id="538d9-137">Conformidade</span><span class="sxs-lookup"><span data-stu-id="538d9-137">Compliance</span></span>      | <span data-ttu-id="538d9-138">LEA</span><span class="sxs-lookup"><span data-stu-id="538d9-138">LEA</span></span>                |
| <span data-ttu-id="538d9-139">É preciso fornecer uma notificação?</span><span class="sxs-lookup"><span data-stu-id="538d9-139">Notification required?</span></span> | <span data-ttu-id="538d9-140">Sim </span><span class="sxs-lookup"><span data-stu-id="538d9-140">Yes</span></span>                | <span data-ttu-id="538d9-141">Sim </span><span class="sxs-lookup"><span data-stu-id="538d9-141">Yes</span></span>                | <span data-ttu-id="538d9-142">Sim </span><span class="sxs-lookup"><span data-stu-id="538d9-142">Yes</span></span>                | <span data-ttu-id="538d9-143">Sim</span><span class="sxs-lookup"><span data-stu-id="538d9-143">Yes</span></span>             | <span data-ttu-id="538d9-144">Não</span><span class="sxs-lookup"><span data-stu-id="538d9-144">No</span></span>                 |
| <span data-ttu-id="538d9-145">Proprietário do Access</span><span class="sxs-lookup"><span data-stu-id="538d9-145">Access Owner</span></span>           | <span data-ttu-id="538d9-146">Usuário</span><span class="sxs-lookup"><span data-stu-id="538d9-146">User</span></span>               | <span data-ttu-id="538d9-147">AppV</span><span class="sxs-lookup"><span data-stu-id="538d9-147">App</span></span>                | <span data-ttu-id="538d9-148">Locatário</span><span class="sxs-lookup"><span data-stu-id="538d9-148">Admin</span></span>              | <span data-ttu-id="538d9-149">Conformidade</span><span class="sxs-lookup"><span data-stu-id="538d9-149">Compliance</span></span>      | <span data-ttu-id="538d9-150">LEA</span><span class="sxs-lookup"><span data-stu-id="538d9-150">LEA</span></span>                |
| <span data-ttu-id="538d9-151">Política de retenção?</span><span class="sxs-lookup"><span data-stu-id="538d9-151">Retention Policy?</span></span>      | <span data-ttu-id="538d9-152">Opcional</span><span class="sxs-lookup"><span data-stu-id="538d9-152">Optional</span></span>           | <span data-ttu-id="538d9-153">Sim </span><span class="sxs-lookup"><span data-stu-id="538d9-153">Yes</span></span>                | <span data-ttu-id="538d9-154">Sim </span><span class="sxs-lookup"><span data-stu-id="538d9-154">Yes</span></span>                | <span data-ttu-id="538d9-155">Sim </span><span class="sxs-lookup"><span data-stu-id="538d9-155">Yes</span></span>             | <span data-ttu-id="538d9-156">Sim</span><span class="sxs-lookup"><span data-stu-id="538d9-156">Yes</span></span>                |

<span data-ttu-id="538d9-157">O Microsoft Teams oferece vários recursos para gravação [<span class="underline">conveniente</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) e funcional para reuniões e eventos ao vivo.</span><span class="sxs-lookup"><span data-stu-id="538d9-157">Teams provides various capabilities for [<span class="underline">convenient</span>](https://docs.microsoft.com/microsoftteams/cloud-recording) and functional recording for meetings and live events.</span></span> <span data-ttu-id="538d9-158">A gravação organizacional significa permitir que as organizações que adotarem equipes para chamadas e reuniões sejam estipuladas, por meio de uma política administrativa, quando chamadas e reuniões online devem ser automaticamente registradas e capturadas para processamento e retenção subsequentes, conforme a necessidade de uma política corporativa ou normativa relevante.</span><span class="sxs-lookup"><span data-stu-id="538d9-158">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="538d9-159">Os usuários desta política ficarão cientes de que suas interações digitais com o Microsoft Teams estão sendo gravadas, mas não poderão desabilitar a gravação e não terão acesso à gravação após a conclusão da interação.</span><span class="sxs-lookup"><span data-stu-id="538d9-159">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="538d9-160">A gravação torna-se parte do arquivo organizacional disponível para a conformidade e o pessoal legal para eDiscovery, o controle legal e outros usos corporativos de retenção.</span><span class="sxs-lookup"><span data-stu-id="538d9-160">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="538d9-161">Exemplo de necessidades do usuário</span><span class="sxs-lookup"><span data-stu-id="538d9-161">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="538d9-162"><strong>Pessoal</strong></span><span class="sxs-lookup"><span data-stu-id="538d9-162"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="538d9-163"><strong>Deve</strong></span><span class="sxs-lookup"><span data-stu-id="538d9-163"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="538d9-164">Usuários registrados</span><span class="sxs-lookup"><span data-stu-id="538d9-164">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="538d9-165">Seja notificado quando a gravação estiver em andamento.</span><span class="sxs-lookup"><span data-stu-id="538d9-165">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="538d9-166">Seja informado quando o erro de política e/ou gravador estiver causando alterações no comportamento de chamadas.</span><span class="sxs-lookup"><span data-stu-id="538d9-166">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="538d9-167">Administrador de comunicações</span><span class="sxs-lookup"><span data-stu-id="538d9-167">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="538d9-168">Entender por que e como aplicar/impor políticas de gravação a usuários/pontos de extremidade da equipe.</span><span class="sxs-lookup"><span data-stu-id="538d9-168">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="538d9-169">Configurar e manter políticas de gravação de equipes para a organização.</span><span class="sxs-lookup"><span data-stu-id="538d9-169">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="538d9-170">Monitorar e solucionar problemas relacionados à gravação com chamadas e reuniões do teams.</span><span class="sxs-lookup"><span data-stu-id="538d9-170">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="538d9-171">Suporte ao responsável pela conformidade interna com análises operacionais sobre uso, qualidade e confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="538d9-171">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="538d9-172">Responsável pela conformidade</span><span class="sxs-lookup"><span data-stu-id="538d9-172">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="538d9-173">Reúna todas as comunicações de equipes da maneira necessária para atender obrigações de conformidade em limites regionais apropriados.</span><span class="sxs-lookup"><span data-stu-id="538d9-173">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="538d9-174">Pesquisar interações com base em conteúdo de interação ou metadados relacionados à comunicação.</span><span class="sxs-lookup"><span data-stu-id="538d9-174">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="538d9-175">Exemplos comuns incluem:</span><span class="sxs-lookup"><span data-stu-id="538d9-175">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="538d9-176"><strong>Metadados</strong> - Participantes, hora, direção, número discado, número de origem, dados corporativos personalizados</span><span class="sxs-lookup"><span data-stu-id="538d9-176"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="538d9-177"><strong>Conteúdo</strong> – transcrição, refira, fonética, interações relacionadas</span><span class="sxs-lookup"><span data-stu-id="538d9-177"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="538d9-178">Analise e interaja com comunicações coletadas, incluindo a capacidade de monitorar interações à medida que elas são coletadas.</span><span class="sxs-lookup"><span data-stu-id="538d9-178">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="538d9-179">Garanta a segurança das comunicações coletadas e impeça a violação em todos os estágios.</span><span class="sxs-lookup"><span data-stu-id="538d9-179">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="538d9-180">Visão geral da arquitetura da solução</span><span class="sxs-lookup"><span data-stu-id="538d9-180">Solution architecture overview</span></span>

<span data-ttu-id="538d9-181">As soluções de gravação de conformidade são integradas ao Teams, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="538d9-181">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="538d9-182">![Captura de tela mostrando a configuração do aplicativo personalizado da equipe](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "As imagens mostram o fluxo quando uma reunião ou uma chamada de equipe é enviada e recebida.")</span><span class="sxs-lookup"><span data-stu-id="538d9-182">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="538d9-183">Gravador</span><span class="sxs-lookup"><span data-stu-id="538d9-183">Recorder</span></span>

<span data-ttu-id="538d9-184">O componente principal da solução de gravação de conformidade é o gravador.</span><span class="sxs-lookup"><span data-stu-id="538d9-184">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="538d9-185">Os gravadores são criados como serviços baseados no Azure escaláveis (bots) que [<span class="underline">aproveitam a plataforma de comunicações da Microsoft</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) e se registram como aplicativos com o Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="538d9-185">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](https://docs.microsoft.com/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="538d9-186">O gravador fornece a interação direta com as APIs de plataforma de [<span class="underline">comunicação de comunicações</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) e as chamadas de equipe e fornece o ponto de extremidade para inclusão de mídia.</span><span class="sxs-lookup"><span data-stu-id="538d9-186">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](https://docs.microsoft.com/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="538d9-187">Um [<span class="underline">aplicativo de gravador de conformidade de exemplo está disponível</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) que mostra como configurar o bot, criar a instância do aplicativo e atribuir as políticas de conformidade.</span><span class="sxs-lookup"><span data-stu-id="538d9-187">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="538d9-188">O exemplo também tem exemplos sobre o uso da API para gravar interações específicas, como manipular o roteamento de [<span class="underline">chamadas recebidas</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244)   , [<span class="underline">alterar os Estados de gravação</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)e [<span class="underline">remover o usuário que está sendo gravado</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="538d9-188">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="538d9-189">A documentação de gráficos sobre APIs específicas pode ser encontrada aqui para [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) e [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="538d9-189">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](https://docs.microsoft.com/graph/api/call-updaterecordingstatus?view=graph-rest-1.0&tabs=http) and [<span class="underline">incomingContext</span>](https://docs.microsoft.com/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="538d9-190">A implementação exata do serviço de gravador varia de acordo com o parceiro, mas deve ser projetada para dar suporte a vários gravadores para obter alta disponibilidade e distribuição geográfica da implantação para reduzir a latência do teams para o gravador.</span><span class="sxs-lookup"><span data-stu-id="538d9-190">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="538d9-191">Além disso, espera-se que os gravadores sejam projetados com resiliência e redundância em mente.</span><span class="sxs-lookup"><span data-stu-id="538d9-191">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="538d9-192">Os parceiros devem confirmar a versão mínima necessária de lançamento das APIs e SDKs de comunicação do Microsoft Graph com a Microsoft antes de enviar sua solução para certificação para garantir que todos os requisitos de integração de gravação de conformidade sejam compatíveis.</span><span class="sxs-lookup"><span data-stu-id="538d9-192">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="538d9-193">Dois requisitos específicos que são fundamentais para o cenário de gravação de conformidade são:</span><span class="sxs-lookup"><span data-stu-id="538d9-193">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="538d9-194">O bot do gravador deve ser implantado no Azure</span><span class="sxs-lookup"><span data-stu-id="538d9-194">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="538d9-195">O bot de gravador deve ser executado em uma VM do Windows no Azure</span><span class="sxs-lookup"><span data-stu-id="538d9-195">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="538d9-196">Os requisitos do Azure e da VM do Windows se aplicam somente ao componente bot do Teams, o que significa que um parceiro pode implementar o restante da plataforma de sua preferência, que pode atender aos requisitos de desempenho e funcionamento relevantes para a gravação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="538d9-196">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="538d9-197">Conformidade de atribuição e provisionamento de política de gravação</span><span class="sxs-lookup"><span data-stu-id="538d9-197">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="538d9-198">Os administradores de ti podem determinar quais usuários devem ser gravados e qual gravador será usado para cada usuário, criando e atribuindo políticas de gravação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="538d9-198">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="538d9-199">Os gravadores são automaticamente convidados a participar de conversas com base na configuração dessas políticas quando ocorre uma interação de comunicação.</span><span class="sxs-lookup"><span data-stu-id="538d9-199">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="538d9-200">As políticas de gravação de conformidade são gerenciadas usando o [<span class="underline">Microsoft PowerShell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) e podem ser aplicadas no locatário e no nível de cada usuário para cada organização.</span><span class="sxs-lookup"><span data-stu-id="538d9-200">Compliance recording policies are managed using [<span class="underline">Microsoft Powershell</span>](https://docs.microsoft.com/microsoftteams/teams-powershell-overview) and can be applied at the tenant and per-user level for each organization.</span></span> <span data-ttu-id="538d9-201">Você pode encontrar mais informações sobre documentos da Microsoft para [<span class="underline">políticas de reunião</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) e políticas de [<span class="underline">chamadas</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy).</span><span class="sxs-lookup"><span data-stu-id="538d9-201">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](https://docs.microsoft.com/microsoftteams/meeting-policies-in-teams) and [<span class="underline">calling policies</span>](https://docs.microsoft.com/microsoftteams/teams-calling-policy).</span></span>

1. <span data-ttu-id="538d9-202">Crie uma instância do aplicativo em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="538d9-202">Create an application instance in your tenant.</span></span>

```powershell
PS C:\> New-CsOnlineApplicationInstance -UserPrincipalName cr.instance@contoso.onmicrosoft.com -DisplayName ComplianceRecordingBotInstance -ApplicationId fcc88ff5-a42d-49cf-b3d8-f2e1f609d511

RunspaceId        : 4c13efa6-77bc-42db-b5bf-bdd62cdfc5df
ObjectId          : 5069aae5-c451-4983-9e57-9455ced220b7
TenantId          : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
UserPrincipalName : cr.instance@contoso.onmicrosoft.com
ApplicationId     : fcc88ff5-a42d-49cf-b3d8-f2e1f609d511
DisplayName       : ComplianceRecordingBotInstance
PhoneNumber       :
```

```powershell
PS C:\> Sync-CsOnlineApplicationInstance -ObjectId 5069aae5-c451-4983-9e57-9455ced220b7
```

2. <span data-ttu-id="538d9-203">Crie uma política de gravação de conformidade.</span><span class="sxs-lookup"><span data-stu-id="538d9-203">Create a Compliance Recording policy.</span></span>

```powershell
PS C:\> New-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy -Enabled $true -Description "Test policy created by tenant admin"

Identity                        : Global
ComplianceRecordingApplications : {}
Enabled                         : True
WarnUserOnRemoval               : True
Description                     : Test policy created by tenant admin
```

```powershell
PS C:\> Set-CsTeamsComplianceRecordingPolicy -Identity TestComplianceRecordingPolicy `
-ComplianceRecordingApplications @(New-CsTeamsComplianceRecordingApplication -Id 5069aae5-c451-4983-9e57-9455ced220b7 -Parent TestComplianceRecordingPolicy)
```

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="538d9-204">Atribua a política de gravação de conformidade a um usuário.</span><span class="sxs-lookup"><span data-stu-id="538d9-204">Assign the Compliance Recording policy to a user.</span></span>

```powershell
PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
```

[<span class="underline">https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps</span>](https://docs.microsoft.com/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

```powershell
PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

UserPrincipalName              : testuser@contoso.onmicrosoft.com
TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
```

## <a name="user-experiences"></a><span data-ttu-id="538d9-205">Experiências do usuário</span><span class="sxs-lookup"><span data-stu-id="538d9-205">User experiences</span></span>

<span data-ttu-id="538d9-206">O suporte para notificações está habilitado com o uso das experiências do cliente das equipes.</span><span class="sxs-lookup"><span data-stu-id="538d9-206">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="538d9-207">As experiências podem ser visuais ou de áudio.</span><span class="sxs-lookup"><span data-stu-id="538d9-207">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="538d9-208">**Clientes do teams – aviso Visual**</span><span class="sxs-lookup"><span data-stu-id="538d9-208">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="538d9-209">Área de trabalho/Web</span><span class="sxs-lookup"><span data-stu-id="538d9-209">Desktop/web</span></span>
- <span data-ttu-id="538d9-210">Celular (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="538d9-210">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="538d9-211">Telefones de equipes</span><span class="sxs-lookup"><span data-stu-id="538d9-211">Teams phones</span></span>
- <span data-ttu-id="538d9-212">Salas de equipe</span><span class="sxs-lookup"><span data-stu-id="538d9-212">Teams rooms</span></span>

<span data-ttu-id="538d9-213">**Outros pontos de extremidade-aviso de áudio**</span><span class="sxs-lookup"><span data-stu-id="538d9-213">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="538d9-214">Telefones SIP</span><span class="sxs-lookup"><span data-stu-id="538d9-214">SIP phones</span></span>
- <span data-ttu-id="538d9-215">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="538d9-215">Skype for Business</span></span>
- <span data-ttu-id="538d9-216">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="538d9-216">Audio conferencing</span></span>
- <span data-ttu-id="538d9-217">Chamadores PSTN</span><span class="sxs-lookup"><span data-stu-id="538d9-217">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="538d9-218">Registro de conformidade para programas de certificação de equipes</span><span class="sxs-lookup"><span data-stu-id="538d9-218">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="538d9-219">Além de publicar as APIs publicamente disponíveis, permitindo que os parceiros desenvolvam e integrem soluções do CCaaS com o Teams, desenvolvemos o programa de certificação de conformidade para o Microsoft Teams para fornecer aos clientes a garantia de que cada parceiro participante tenha sido testado e verificado para fornecer a qualidade, a compatibilidade e a confiabilidade esperados pelas soluções da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="538d9-219">In addition to publishing publicly-available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="538d9-220">Os parceiros a seguir estão no processo de certificação da solução para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="538d9-220">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>  

|<span data-ttu-id="538d9-221">Sócio</span><span class="sxs-lookup"><span data-stu-id="538d9-221">Partner</span></span>|<span data-ttu-id="538d9-222">Site da solução</span><span class="sxs-lookup"><span data-stu-id="538d9-222">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="538d9-223">Tecnologias ASC</span><span class="sxs-lookup"><span data-stu-id="538d9-223">ASC Technologies</span></span> |[https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html](https://www.asc.de/english/ASC_Recording_Insights_for_Microsoft_Teams.html) |
|<span data-ttu-id="538d9-224">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="538d9-224">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/smarttap-360-recording) |
|<span data-ttu-id="538d9-225">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="538d9-225">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="538d9-226">Bom</span><span class="sxs-lookup"><span data-stu-id="538d9-226">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="538d9-227">Numonix</span><span class="sxs-lookup"><span data-stu-id="538d9-227">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="538d9-228">Caixa vermelha</span><span class="sxs-lookup"><span data-stu-id="538d9-228">Red Box</span></span> |[https://hubs.ly/H0qtN7Q0](https://hubs.ly/H0qtN7Q0)  |
|<span data-ttu-id="538d9-229">Verint</span><span class="sxs-lookup"><span data-stu-id="538d9-229">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |

<span data-ttu-id="538d9-230">Esta lista será atualizada à medida que mais parceiros entrarem e atenderem aos critérios de certificação.</span><span class="sxs-lookup"><span data-stu-id="538d9-230">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="538d9-231">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="538d9-231">Next steps</span></span>

<span data-ttu-id="538d9-232">Se você for um fornecedor que está procurando participar do programa de certificação, envie um email para <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a></span><span class="sxs-lookup"><span data-stu-id="538d9-232">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a></span></span>
