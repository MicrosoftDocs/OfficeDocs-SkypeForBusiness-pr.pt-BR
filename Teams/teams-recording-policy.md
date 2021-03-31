---
title: Introdução ao Registro baseado em política do Teams para & reuniões
author: cabailey
ms.author: cabailey
manager: laurawi
ms.date: 05/11/2020
audience: Admin
ms.topic: conceptual
ms.service: msteams
ms.reviewer: abybee
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre o Registro baseado em política do Teams para & reuniões
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
ms.openlocfilehash: 7972febeab134f0ec075418e351c35ef7e273fcf
ms.sourcegitcommit: f22e050213798a8ff69c6d502a2fc142104ab213
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/30/2021
ms.locfileid: "51439666"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="c1300-103">Introdução à gravação baseada em política do Teams para & reuniões</span><span class="sxs-lookup"><span data-stu-id="c1300-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="c1300-104">O registro baseado em política permite que as organizações que adotam o Microsoft Teams para chamadas e reuniões estipulem, usando uma política administrativa, quando chamadas e reuniões online devem ser gravadas e capturadas automaticamente para processamento e retenção subsequentes, conforme exigido pela política corporativa ou regulatória relevante.</span><span class="sxs-lookup"><span data-stu-id="c1300-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="c1300-105">O Teams foi aprimorado para oferecer suporte à integração de soluções de gravação de terceiros, incluindo a funcionalidade da plataforma, as experiências do usuário e as interfaces administrativas necessárias para fornecer uma solução de ponta a ponta para configurar, gerenciar, gravar, armazenar e analisar as comunicações do Teams.</span><span class="sxs-lookup"><span data-stu-id="c1300-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="c1300-106">Os aprimoramentos incluem APIs e eventos da plataforma de comunicações para gravação, que fornece:</span><span class="sxs-lookup"><span data-stu-id="c1300-106">Enhancements include communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="c1300-107">Captura de mídia perfeita e de alta qualidade em todos os dispositivos e todos os pontos de extremidade com suporte para áudio, vídeo, compartilhamento de tela e chat.</span><span class="sxs-lookup"><span data-stu-id="c1300-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="c1300-108">Suporte para captura de interação entre usuários do Teams e pontos de extremidade de chamadas com suporte (Teams, Teams Mobile, Skype for Business, PSTN)</span><span class="sxs-lookup"><span data-stu-id="c1300-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="c1300-109">Novas políticas administrativas para registro de conformidade, incluindo integração com as ferramentas e políticas de reunião e chamada administrativa existentes do Teams</span><span class="sxs-lookup"><span data-stu-id="c1300-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="c1300-110">O Registro de Conformidade pode ser habilitado nos usuários do Microsoft 365 A3/A5/E3/E5/Business Premium e office 365 A3/A5/E3/E5.</span><span class="sxs-lookup"><span data-stu-id="c1300-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="c1300-111">Os recursos de integração da solução de registro de conformidade também foram revisados no Ignite 2019 na sessão Registro de Conformidade [<span class="underline">e Microsoft Teams.</span>](https://myignite.microsoft.com/archives/IG19-VCE40)</span><span class="sxs-lookup"><span data-stu-id="c1300-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [<span class="underline">Compliance Recording and Microsoft Teams session</span>](https://myignite.microsoft.com/archives/IG19-VCE40).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="c1300-112">Visão geral da gravação de interação do Teams</span><span class="sxs-lookup"><span data-stu-id="c1300-112">Teams interaction recording overview</span></span>

<span data-ttu-id="c1300-113">Os casos de uso do registro de interação podem ser efetivamente separados em quatro categorias principais de funcionalidade de gravação – Conveniência, Funcional, Organizacional e Interceptação Legal, conforme mostrado na imagem:</span><span class="sxs-lookup"><span data-stu-id="c1300-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

<span data-ttu-id="c1300-114">![Captura de tela mostrando a interação registrando o que e por quê.](media/recording-taxonomy.png "A imagem mostra as categorias de gravação.")</span><span class="sxs-lookup"><span data-stu-id="c1300-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="c1300-115">Cada uma das categorias envolve requisitos diferentes para como as gravações são iniciadas, o que é gravado, onde as gravações são armazenadas, quem é notificado, quem controla o acesso e como a retenção é manipulada.</span><span class="sxs-lookup"><span data-stu-id="c1300-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="c1300-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="c1300-116">Type</span></span>                   | <span data-ttu-id="c1300-117">Conveniência (Gravação regular do Teams)</span><span class="sxs-lookup"><span data-stu-id="c1300-117">Convenience (Regular Teams Recording)</span></span> | <span data-ttu-id="c1300-118">Org - Regulamentado (Registro de Conformidade)</span><span class="sxs-lookup"><span data-stu-id="c1300-118">Org - Regulated (Compliance Recording)</span></span> |
| ---------------------- | ------------------ | --------------- |
| <span data-ttu-id="c1300-119">Iniciador</span><span class="sxs-lookup"><span data-stu-id="c1300-119">Initiator</span></span>              | <span data-ttu-id="c1300-120">Usuário</span><span class="sxs-lookup"><span data-stu-id="c1300-120">User</span></span>               | <span data-ttu-id="c1300-121">Administrador (sistema)</span><span class="sxs-lookup"><span data-stu-id="c1300-121">Admin (system)</span></span>  |
| <span data-ttu-id="c1300-122">Destino </span><span class="sxs-lookup"><span data-stu-id="c1300-122">Target</span></span>                 | <span data-ttu-id="c1300-123">Por chamada/reunião</span><span class="sxs-lookup"><span data-stu-id="c1300-123">Per-call / meeting</span></span> | <span data-ttu-id="c1300-124">Por usuário</span><span class="sxs-lookup"><span data-stu-id="c1300-124">Per-user</span></span>        |
| <span data-ttu-id="c1300-125">Proprietário do armazenamento</span><span class="sxs-lookup"><span data-stu-id="c1300-125">Storage owner</span></span>          | <span data-ttu-id="c1300-126">Usuário</span><span class="sxs-lookup"><span data-stu-id="c1300-126">User</span></span>               | <span data-ttu-id="c1300-127">Conformidade</span><span class="sxs-lookup"><span data-stu-id="c1300-127">Compliance</span></span>      |
| <span data-ttu-id="c1300-128">Notificação necessária?</span><span class="sxs-lookup"><span data-stu-id="c1300-128">Notification required?</span></span> | <span data-ttu-id="c1300-129">Sim</span><span class="sxs-lookup"><span data-stu-id="c1300-129">Yes</span></span>                | <span data-ttu-id="c1300-130">Sim</span><span class="sxs-lookup"><span data-stu-id="c1300-130">Yes</span></span>             |
| <span data-ttu-id="c1300-131">Proprietário do Access</span><span class="sxs-lookup"><span data-stu-id="c1300-131">Access Owner</span></span>           | <span data-ttu-id="c1300-132">Usuário</span><span class="sxs-lookup"><span data-stu-id="c1300-132">User</span></span>               | <span data-ttu-id="c1300-133">Conformidade</span><span class="sxs-lookup"><span data-stu-id="c1300-133">Compliance</span></span>      |
| <span data-ttu-id="c1300-134">Política de Retenção?</span><span class="sxs-lookup"><span data-stu-id="c1300-134">Retention Policy?</span></span>      | <span data-ttu-id="c1300-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="c1300-135">Optional</span></span>           | <span data-ttu-id="c1300-136">Sim</span><span class="sxs-lookup"><span data-stu-id="c1300-136">Yes</span></span>             |

<span data-ttu-id="c1300-137">O Teams fornece vários recursos para [<span class="underline">gravação</span>](./cloud-recording.md) prática e funcional para reuniões e eventos ao vivo.</span><span class="sxs-lookup"><span data-stu-id="c1300-137">Teams provides various capabilities for [<span class="underline">convenient</span>](./cloud-recording.md) and functional recording for meetings and live events.</span></span> <span data-ttu-id="c1300-138">O registro organizacional significa permitir que as organizações que adotam o Teams para chamadas e reuniões estipulem, por meio de uma política administrativa, quando chamadas e reuniões online devem ser gravadas e capturadas automaticamente para processamento e retenção subsequentes, conforme exigido pela política corporativa ou regulatória relevante.</span><span class="sxs-lookup"><span data-stu-id="c1300-138">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="c1300-139">Os usuários sob essa política estarão cientes de que suas interações digitais com o Teams estão sendo gravadas, mas não poderão desabilitar a gravação e não terão acesso à gravação depois que a interação for concluída.</span><span class="sxs-lookup"><span data-stu-id="c1300-139">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="c1300-140">A gravação torna-se parte do arquivo morto organizacional disponível para conformidade e equipe jurídica para Descoberta e Descoberta, retenção legal e outros usos de retenção corporativa.</span><span class="sxs-lookup"><span data-stu-id="c1300-140">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="c1300-141">Exemplo de necessidades do usuário</span><span class="sxs-lookup"><span data-stu-id="c1300-141">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="c1300-142"><strong>Pessoal</strong></span><span class="sxs-lookup"><span data-stu-id="c1300-142"><strong>Persona</strong></span></span></th>
<th><span data-ttu-id="c1300-143"><strong>Necessidades</strong></span><span class="sxs-lookup"><span data-stu-id="c1300-143"><strong>Needs</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="c1300-144">Usuários registrados</span><span class="sxs-lookup"><span data-stu-id="c1300-144">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="c1300-145">Seja notificado quando a gravação estiver em andamento.</span><span class="sxs-lookup"><span data-stu-id="c1300-145">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="c1300-146">Seja informado quando o erro de política e/ou gravador está causando alterações no comportamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="c1300-146">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="c1300-147">Administrador de comunicações</span><span class="sxs-lookup"><span data-stu-id="c1300-147">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="c1300-148">Entenda por que e como aplicar/impor políticas de gravação aos usuários/pontos de extremidade do Teams.</span><span class="sxs-lookup"><span data-stu-id="c1300-148">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="c1300-149">Configure e mantenha as políticas de gravação do Teams para a organização.</span><span class="sxs-lookup"><span data-stu-id="c1300-149">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="c1300-150">Monitorar e solucionar problemas relacionados à gravação com chamadas e reuniões do Teams.</span><span class="sxs-lookup"><span data-stu-id="c1300-150">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="c1300-151">Suporte ao responsável pela conformidade interna com análises operacionais sobre uso, qualidade e confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="c1300-151">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="c1300-152">Responsável pela conformidade</span><span class="sxs-lookup"><span data-stu-id="c1300-152">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="c1300-153">Colete todas as comunicações do Teams da maneira necessária para atender às obrigações de conformidade nos limites regionais apropriados.</span><span class="sxs-lookup"><span data-stu-id="c1300-153">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="c1300-154">Pesquise interações com base em metadados relacionados à comunicação ou conteúdo de interação.</span><span class="sxs-lookup"><span data-stu-id="c1300-154">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="c1300-155">Exemplos comuns incluem:</span><span class="sxs-lookup"><span data-stu-id="c1300-155">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="c1300-156"><strong>Metadados</strong> - Participantes, hora, direção, número discado, número de origem, dados comerciais personalizados</span><span class="sxs-lookup"><span data-stu-id="c1300-156"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="c1300-157"><strong>Conteúdo</strong> – Transcrição, sentimento, phonetics, interações relacionadas</span><span class="sxs-lookup"><span data-stu-id="c1300-157"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="c1300-158">Analise e interaja com comunicações coletadas, incluindo a capacidade de monitorar interações enquanto elas estão sendo coletadas.</span><span class="sxs-lookup"><span data-stu-id="c1300-158">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="c1300-159">Garantir a segurança das comunicações coletadas e impedir a adulteração em todos os estágios.</span><span class="sxs-lookup"><span data-stu-id="c1300-159">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="c1300-160">Visão geral da arquitetura de soluções</span><span class="sxs-lookup"><span data-stu-id="c1300-160">Solution architecture overview</span></span>

<span data-ttu-id="c1300-161">As soluções de registro de conformidade são integradas ao Teams, conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="c1300-161">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

<span data-ttu-id="c1300-162">![Captura de tela mostrando a configuração do aplicativo personalizado da equipe](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "As imagens mostram o fluxo quando uma reunião ou chamada do Teams é enviada e recebida.")</span><span class="sxs-lookup"><span data-stu-id="c1300-162">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="c1300-163">Gravador</span><span class="sxs-lookup"><span data-stu-id="c1300-163">Recorder</span></span>

<span data-ttu-id="c1300-164">O componente principal da solução de registro de conformidade é o gravador.</span><span class="sxs-lookup"><span data-stu-id="c1300-164">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="c1300-165">Os gravadores são construídos como serviços dimensionáveis baseados no Azure (bots) que aproveitam a plataforma de comunicações da [<span class="underline">Microsoft</span>](/graph/cloud-communications-concept-overview) e se registram como aplicativos com o Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="c1300-165">Recorders are built as scalable Azure-based services (bots) that [<span class="underline">leverage Microsoft’s communications platform</span>](/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="c1300-166">O gravador fornece a interação direta com as [<span class="underline">APIs</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) da plataforma de comunicações de reuniões e chamadas do Teams e fornece o ponto de extremidade para ingestão de mídia.</span><span class="sxs-lookup"><span data-stu-id="c1300-166">The recorder provides the direct interaction with the Teams calls and meetings [<span class="underline">communications platform APIs</span>](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="c1300-167">Um [<span class="underline">aplicativo de gravador de conformidade</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) de exemplo está disponível que mostra como configurar o bot, criar a instância do aplicativo e atribuir as políticas de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c1300-167">A [<span class="underline">sample compliance recorder application is available</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="c1300-168">O exemplo também tem exemplos sobre o uso [<span class="underline"></span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) da API para gravar interações específicas, como manipular o roteamento de chamadas de [<span class="underline">entrada,</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)alterar estados de gravação e remover o usuário que está [<span class="underline">sendo gravado</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="c1300-168">The sample also has examples on API usage for recording specific interactions such as handling [<span class="underline">incoming call</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [<span class="underline">changing recording states</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [<span class="underline">removing the user who is being recorded</span>](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="c1300-169">A documentação do graph nas APIs específicas pode ser encontrada aqui para [<span class="underline">updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) e [<span class="underline">incomingContext</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="c1300-169">Graph documentation on the specific APIs can be found here for [<span class="underline">updateRecordingStatus</span>](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) and [<span class="underline">incomingContext</span>](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="c1300-170">A implementação exata do serviço de gravador varia de acordo com o parceiro, mas deve ser projetada para dar suporte a vários gravadores para alcançar alta disponibilidade e distribuição geográfica da implantação para reduzir a latência do Teams para o gravador.</span><span class="sxs-lookup"><span data-stu-id="c1300-170">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="c1300-171">Além disso, é esperado que os próprios Gravadores sejam projetados com resiliência e redundância em mente.</span><span class="sxs-lookup"><span data-stu-id="c1300-171">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="c1300-172">Os parceiros devem confirmar a versão de versão mínima necessária das APIs e SDKs de comunicações do Microsoft Graph com a Microsoft antes de enviar sua solução para certificação para garantir que todos os requisitos de integração de registro de conformidade sejam suportados.</span><span class="sxs-lookup"><span data-stu-id="c1300-172">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="c1300-173">Dois requisitos específicos que são fundamentais para o cenário de registro de conformidade são:</span><span class="sxs-lookup"><span data-stu-id="c1300-173">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="c1300-174">O bot do gravador deve ser implantado no Azure</span><span class="sxs-lookup"><span data-stu-id="c1300-174">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="c1300-175">O bot do gravador deve ser executado em uma VM do Windows no Azure</span><span class="sxs-lookup"><span data-stu-id="c1300-175">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="c1300-176">Os requisitos de VM do Azure e do Windows só se aplicam ao componente do Teams Bot, o que significa que um parceiro pode implementar o restante da plataforma de sua escolha, desde que possa atender aos requisitos funcionais e de desempenho relevantes para o registro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c1300-176">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="c1300-177">Atribuição e provisionamento da política de registro de conformidade</span><span class="sxs-lookup"><span data-stu-id="c1300-177">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="c1300-178">Os administradores de IT podem determinar quais usuários devem ser gravados e qual gravador será usado para cada usuário, criando e atribuindo políticas de registro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="c1300-178">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="c1300-179">Os gravadores são automaticamente convidados a participar de conversas com base na configuração dessas políticas quando uma interação de comunicação ocorre.</span><span class="sxs-lookup"><span data-stu-id="c1300-179">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="c1300-180">As políticas de registro de conformidade são gerenciadas usando [<span class="underline">o Microsoft PowerShell</span>](./teams-powershell-overview.md) e podem ser aplicadas no nível de locatário, por usuário e grupo de segurança para cada organização.</span><span class="sxs-lookup"><span data-stu-id="c1300-180">Compliance recording policies are managed using [<span class="underline">Microsoft PowerShell</span>](./teams-powershell-overview.md) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="c1300-181">Você pode encontrar mais informações sobre as políticas do Microsoft Docs for [<span class="underline">Meeting,</span>](./meeting-policies-in-teams.md) [<span class="underline">políticas de chamada</span>](./teams-calling-policy.md) e políticas de [<span class="underline">grupo.</span>](./assign-policies.md#assign-a-policy-to-a-group)</span><span class="sxs-lookup"><span data-stu-id="c1300-181">You can find more information on Microsoft Docs for [<span class="underline">Meeting policies</span>](./meeting-policies-in-teams.md), [<span class="underline">calling policies</span>](./teams-calling-policy.md) and  [<span class="underline">group policies</span>](./assign-policies.md#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="c1300-182">Crie uma instância de aplicativo em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="c1300-182">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="c1300-183">Criar uma política de Registro de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="c1300-183">Create a Compliance Recording policy.</span></span>

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

   [<span data-ttu-id="c1300-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="c1300-184"><span class="underline">Set-CsTeamsComplianceRecordingPolicy</span></span></span>](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps)

3. <span data-ttu-id="c1300-185">Atribua a política de Registro de Conformidade a um usuário.</span><span class="sxs-lookup"><span data-stu-id="c1300-185">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   [<span data-ttu-id="c1300-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span><span class="sxs-lookup"><span data-stu-id="c1300-186"><span class="underline">Grant-CsTeamsComplianceRecordingPolicy</span></span></span>](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps)

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="c1300-187">Experiências do usuário</span><span class="sxs-lookup"><span data-stu-id="c1300-187">User experiences</span></span>

<span data-ttu-id="c1300-188">O suporte para notificações é habilitado usando as experiências de cliente do Teams.</span><span class="sxs-lookup"><span data-stu-id="c1300-188">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="c1300-189">As experiências podem ser visuais ou de áudio.</span><span class="sxs-lookup"><span data-stu-id="c1300-189">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="c1300-190">**Clientes do Teams - aviso visual**</span><span class="sxs-lookup"><span data-stu-id="c1300-190">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="c1300-191">Área de trabalho/web</span><span class="sxs-lookup"><span data-stu-id="c1300-191">Desktop/web</span></span>
- <span data-ttu-id="c1300-192">Mobile (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="c1300-192">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="c1300-193">Telefones do Teams</span><span class="sxs-lookup"><span data-stu-id="c1300-193">Teams phones</span></span>
- <span data-ttu-id="c1300-194">Salas do Teams</span><span class="sxs-lookup"><span data-stu-id="c1300-194">Teams rooms</span></span>

<span data-ttu-id="c1300-195">**Outros pontos de extremidade - aviso de áudio**</span><span class="sxs-lookup"><span data-stu-id="c1300-195">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="c1300-196">Telefones SIP</span><span class="sxs-lookup"><span data-stu-id="c1300-196">SIP phones</span></span>
- <span data-ttu-id="c1300-197">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="c1300-197">Skype for Business</span></span>
- <span data-ttu-id="c1300-198">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="c1300-198">Audio conferencing</span></span>
- <span data-ttu-id="c1300-199">Chamadores PSTN</span><span class="sxs-lookup"><span data-stu-id="c1300-199">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="c1300-200">Registro de conformidade para programas de certificação do Teams</span><span class="sxs-lookup"><span data-stu-id="c1300-200">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="c1300-201">Além de publicar APIs disponíveis publicamente, permitindo que os parceiros desenvolvam e integrem soluções CCaaS com o Teams, desenvolvemos o registro de conformidade para o programa de certificação do Microsoft Teams para fornecer aos clientes a garantia de que a solução de cada parceiro participante foi testada e verificada para fornecer a qualidade, a compatibilidade e a confiabilidade esperadas das soluções da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c1300-201">In addition to publishing publicly available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="c1300-202">Os parceiros a seguir certificados sua solução para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1300-202">The following partners have certified their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="c1300-203">Parceiro</span><span class="sxs-lookup"><span data-stu-id="c1300-203">Partner</span></span>|<span data-ttu-id="c1300-204">Site da solução</span><span class="sxs-lookup"><span data-stu-id="c1300-204">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="c1300-205">Tecnologias ASC</span><span class="sxs-lookup"><span data-stu-id="c1300-205">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="c1300-206">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="c1300-206">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|<span data-ttu-id="c1300-207">Selador</span><span class="sxs-lookup"><span data-stu-id="c1300-207">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="c1300-208">NICE</span><span class="sxs-lookup"><span data-stu-id="c1300-208">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |


<span data-ttu-id="c1300-209">Os parceiros a seguir estão no processo de certificar sua solução para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="c1300-209">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span>

|<span data-ttu-id="c1300-210">Parceiro</span><span class="sxs-lookup"><span data-stu-id="c1300-210">Partner</span></span>|<span data-ttu-id="c1300-211">Site da solução</span><span class="sxs-lookup"><span data-stu-id="c1300-211">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="c1300-212">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="c1300-212">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |
|<span data-ttu-id="c1300-213">Tecnologias Landis</span><span class="sxs-lookup"><span data-stu-id="c1300-213">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="c1300-214">Luware</span><span class="sxs-lookup"><span data-stu-id="c1300-214">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="c1300-215">Numonix</span><span class="sxs-lookup"><span data-stu-id="c1300-215">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="c1300-216">Inovação de Carvalho</span><span class="sxs-lookup"><span data-stu-id="c1300-216">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="c1300-217">Caixa Vermelha</span><span class="sxs-lookup"><span data-stu-id="c1300-217">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |
|<span data-ttu-id="c1300-218">Verint</span><span class="sxs-lookup"><span data-stu-id="c1300-218">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|<span data-ttu-id="c1300-219">Theta Lake</span><span class="sxs-lookup"><span data-stu-id="c1300-219">Theta Lake</span></span> |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |

<span data-ttu-id="c1300-220">Essa lista será atualizada à medida que mais parceiros ingressarem e atenderem aos critérios de certificação.</span><span class="sxs-lookup"><span data-stu-id="c1300-220">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="c1300-221">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="c1300-221">Next steps</span></span>

<span data-ttu-id="c1300-222">Se você for um fornecedor que está tentando ingressar no programa de certificação, por favor,  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="c1300-222">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
