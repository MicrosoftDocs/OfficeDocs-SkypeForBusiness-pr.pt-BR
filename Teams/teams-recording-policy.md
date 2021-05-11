---
title: Introdução à Teams gravação baseada em política para & reuniões
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
description: Saiba mais sobre Teams gravação baseada em política para & reuniões
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
ms.openlocfilehash: ba99e49aa546a57d412492737cae8f6520a9eb84
ms.sourcegitcommit: 83f14c4c79559ef28357ff076938e52b369fc0c7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/10/2021
ms.locfileid: "52308360"
---
# <a name="introduction-to-teams-policy-based-recording-for-callings--meetings"></a><span data-ttu-id="b6cb3-103">Introdução Teams gravação baseada em política para & reuniões</span><span class="sxs-lookup"><span data-stu-id="b6cb3-103">Introduction to Teams policy-based recording for callings & meetings</span></span>

<span data-ttu-id="b6cb3-104">O registro baseado em política permite que as organizações que adotam o Microsoft Teams para chamadas e reuniões estipulem, usando uma política administrativa, quando chamadas e reuniões online devem ser gravadas e capturadas automaticamente para processamento e retenção subsequentes, conforme exigido pela política corporativa ou regulatória relevante.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-104">Policy-based recording enables organizations that adopt Microsoft Teams for calling and meetings to stipulate, using an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span>

<span data-ttu-id="b6cb3-105">O Teams foi aprimorado para oferecer suporte à integração de soluções de gravação de terceiros, incluindo a funcionalidade da plataforma, as experiências do usuário e as interfaces administrativas necessárias para fornecer uma solução de ponta a ponta para configurar, gerenciar, gravar, armazenar e analisar as comunicações Teams.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-105">Teams has been enhanced to support integration of third-party recording solutions, including the platform functionality, user experiences, and administrative interfaces needed to provide an end-to-end solution for configuring, managing, recording, storing, and analyzing Teams communications.</span></span> <span data-ttu-id="b6cb3-106">Os aprimoramentos incluem APIs e eventos da plataforma de comunicações para gravação, que fornece:</span><span class="sxs-lookup"><span data-stu-id="b6cb3-106">Enhancements include communications platform APIs and events for recording, which provides:</span></span>

- <span data-ttu-id="b6cb3-107">Captura de mídia perfeita e de alta qualidade em todos os dispositivos e todos os pontos de extremidade com suporte para áudio, vídeo, compartilhamento de tela e chat.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-107">Seamless, high-quality media capture across devices and all   supported endpoints for audio, video, screen share, and chat.</span></span>

- <span data-ttu-id="b6cb3-108">Suporte para captura de interação entre Teams usuários e pontos de extremidade de chamada com suporte (Teams, Teams Mobile, Skype for Business, PSTN)</span><span class="sxs-lookup"><span data-stu-id="b6cb3-108">Support for interaction capture between Teams users and supported   calling endpoints (Teams, Teams Mobile, Skype for Business, PSTN)</span></span>

- <span data-ttu-id="b6cb3-109">Novas políticas administrativas para registro de conformidade, incluindo a integração com as Teams de reunião e ferramentas e políticas administrativas existentes</span><span class="sxs-lookup"><span data-stu-id="b6cb3-109">New administrative policies for compliance recording, including   integration with existing Teams administrative calling and   meeting tools and policies</span></span>

<span data-ttu-id="b6cb3-110">O Registro de Conformidade pode ser habilitado em usuários Microsoft 365 A3/A5/E3/E5/Business Premium e Office 365 A3/A5/E3/E5.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-110">Compliance Recording can be enabled on Microsoft 365 A3/A5/E3/E5/Business Premium and Office 365 A3/A5/E3/E5 users.</span></span> 

<span data-ttu-id="b6cb3-111">Os recursos de integração da solução de registro de conformidade também foram revisados no Ignite 2019 na sessão Registro de Conformidade e Microsoft Teams [de conformidade.](https://myignite.microsoft.com/archives/IG19-VCE40)</span><span class="sxs-lookup"><span data-stu-id="b6cb3-111">The compliance recording solution integration capabilities were also reviewed at Ignite 2019 in the [Compliance Recording and Microsoft Teams session](https://myignite.microsoft.com/archives/IG19-VCE40).</span></span>

## <a name="teams-interaction-recording-overview"></a><span data-ttu-id="b6cb3-112">Teams visão geral da gravação de interação</span><span class="sxs-lookup"><span data-stu-id="b6cb3-112">Teams interaction recording overview</span></span>

<span data-ttu-id="b6cb3-113">Os casos de uso do registro de interação podem ser efetivamente separados em quatro categorias principais de funcionalidade de gravação – Conveniência, Funcional, Organizacional e Interceptação Legal, conforme mostrado na imagem:</span><span class="sxs-lookup"><span data-stu-id="b6cb3-113">Interaction recording use cases can effectively be separated into four primary categories of recording functionality – Convenience, Functional, Organizational, and Lawful Intercept, as shown in the image:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6cb3-114">![Captura de tela mostrando a interação registrando o que e por quê.](media/recording-taxonomy.png "A imagem mostra as categorias de gravação.")</span><span class="sxs-lookup"><span data-stu-id="b6cb3-114">![Screenshot showing the interaction recording what and why.](media/recording-taxonomy.png "The image shows the recording categories.")</span></span>

<span data-ttu-id="b6cb3-115">Cada uma das categorias envolve requisitos diferentes para como as gravações são iniciadas, o que é gravado, onde as gravações são armazenadas, quem é notificado, quem controla o acesso e como a retenção é manipulada.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-115">Each of the categories entails different requirements for how recordings are initiated, what is recorded, where recordings are stored, who is notified, who controls access, and how retention is handled.</span></span>

| <span data-ttu-id="b6cb3-116">Tipo</span><span class="sxs-lookup"><span data-stu-id="b6cb3-116">Type</span></span>                   | <span data-ttu-id="b6cb3-117">Conveniência (gravação Teams regular)</span><span class="sxs-lookup"><span data-stu-id="b6cb3-117">Convenience (Regular Teams Recording)</span></span> | <span data-ttu-id="b6cb3-118">Org - Regulamentado (Registro de Conformidade)</span><span class="sxs-lookup"><span data-stu-id="b6cb3-118">Org - Regulated (Compliance Recording)</span></span> |
| ---------------------- | ------------------ | --------------- |
| <span data-ttu-id="b6cb3-119">Iniciador</span><span class="sxs-lookup"><span data-stu-id="b6cb3-119">Initiator</span></span>              | <span data-ttu-id="b6cb3-120">Usuário</span><span class="sxs-lookup"><span data-stu-id="b6cb3-120">User</span></span>               | <span data-ttu-id="b6cb3-121">Administrador (sistema)</span><span class="sxs-lookup"><span data-stu-id="b6cb3-121">Admin (system)</span></span>  |
| <span data-ttu-id="b6cb3-122">Destino</span><span class="sxs-lookup"><span data-stu-id="b6cb3-122">Target</span></span>                 | <span data-ttu-id="b6cb3-123">Por chamada/reunião</span><span class="sxs-lookup"><span data-stu-id="b6cb3-123">Per-call / meeting</span></span> | <span data-ttu-id="b6cb3-124">Por usuário</span><span class="sxs-lookup"><span data-stu-id="b6cb3-124">Per-user</span></span>        |
| <span data-ttu-id="b6cb3-125">Armazenamento proprietário</span><span class="sxs-lookup"><span data-stu-id="b6cb3-125">Storage owner</span></span>          | <span data-ttu-id="b6cb3-126">Usuário</span><span class="sxs-lookup"><span data-stu-id="b6cb3-126">User</span></span>               | <span data-ttu-id="b6cb3-127">Conformidade</span><span class="sxs-lookup"><span data-stu-id="b6cb3-127">Compliance</span></span>      |
| <span data-ttu-id="b6cb3-128">Notificação necessária?</span><span class="sxs-lookup"><span data-stu-id="b6cb3-128">Notification required?</span></span> | <span data-ttu-id="b6cb3-129">Sim</span><span class="sxs-lookup"><span data-stu-id="b6cb3-129">Yes</span></span>                | <span data-ttu-id="b6cb3-130">Sim</span><span class="sxs-lookup"><span data-stu-id="b6cb3-130">Yes</span></span>             |
| <span data-ttu-id="b6cb3-131">Proprietário do Access</span><span class="sxs-lookup"><span data-stu-id="b6cb3-131">Access Owner</span></span>           | <span data-ttu-id="b6cb3-132">Usuário</span><span class="sxs-lookup"><span data-stu-id="b6cb3-132">User</span></span>               | <span data-ttu-id="b6cb3-133">Conformidade</span><span class="sxs-lookup"><span data-stu-id="b6cb3-133">Compliance</span></span>      |
| <span data-ttu-id="b6cb3-134">Política de Retenção?</span><span class="sxs-lookup"><span data-stu-id="b6cb3-134">Retention Policy?</span></span>      | <span data-ttu-id="b6cb3-135">Opcional</span><span class="sxs-lookup"><span data-stu-id="b6cb3-135">Optional</span></span>           | <span data-ttu-id="b6cb3-136">Sim</span><span class="sxs-lookup"><span data-stu-id="b6cb3-136">Yes</span></span>             |

<span data-ttu-id="b6cb3-137">Teams oferece vários recursos para [gravação](./cloud-recording.md) prática e funcional para reuniões e eventos ao vivo.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-137">Teams provides various capabilities for [convenient](./cloud-recording.md) and functional recording for meetings and live events.</span></span> <span data-ttu-id="b6cb3-138">O registro organizacional significa permitir que as organizações que adotam o Teams para chamadas e reuniões estipulem, por meio de uma política administrativa, quando chamadas e reuniões online devem ser gravadas e capturadas automaticamente para processamento e retenção subsequentes, conforme exigido pela política corporativa ou regulatória relevante.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-138">Organizational recording means enabling organizations adopting Teams for calling and meetings to stipulate, by way of an administrative policy, when calls and online meetings should be automatically recorded and captured for subsequent processing and retention as required by relevant corporate or regulatory policy.</span></span> <span data-ttu-id="b6cb3-139">Os usuários sob essa política estarão cientes de que suas interações digitais com o Teams estão sendo gravadas, mas não poderão desabilitar a gravação e não terão acesso à gravação depois que a interação for concluída.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-139">Users under this policy will be aware that their digital interactions with Teams are being recorded but will not be able to disable the recording and will not have access to the recording once the interaction is complete.</span></span> <span data-ttu-id="b6cb3-140">A gravação torna-se parte do arquivo morto organizacional disponível para conformidade e equipe jurídica para Descoberta e Descoberta, retenção legal e outros usos de retenção corporativa.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-140">The recording becomes part of the organizational archive available to compliance and legal personnel for eDiscovery, legal hold, and other corporate retention uses.</span></span>

## <a name="example-user-needs"></a><span data-ttu-id="b6cb3-141">Exemplo de necessidades do usuário</span><span class="sxs-lookup"><span data-stu-id="b6cb3-141">Example user needs</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="b6cb3-142">Pessoal</span><span class="sxs-lookup"><span data-stu-id="b6cb3-142">Persona</span></span></th>
<th><span data-ttu-id="b6cb3-143">Necessidades</span><span class="sxs-lookup"><span data-stu-id="b6cb3-143">Needs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="b6cb3-144">Usuários registrados</span><span class="sxs-lookup"><span data-stu-id="b6cb3-144">Recorded users</span></span></td>
<td><ul>
<li><p><span data-ttu-id="b6cb3-145">Seja notificado quando a gravação estiver em andamento.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-145">Be notified when recording is in progress.</span></span></p></li>
<li><p><span data-ttu-id="b6cb3-146">Seja informado quando o erro de política e/ou gravador está causando alterações no comportamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-146">Be informed when policy and/or recorder error is causing changes in calling behavior.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td><span data-ttu-id="b6cb3-147">Administrador de comunicações</span><span class="sxs-lookup"><span data-stu-id="b6cb3-147">Communications admin</span></span></td>
<td><ul>
<li><p><span data-ttu-id="b6cb3-148">Entenda por que e como aplicar/impor políticas de gravação Teams usuários/pontos de extremidade.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-148">Understand why and how to apply / enforce recording policies to Teams users / endpoints.</span></span></p></li>
<li><p><span data-ttu-id="b6cb3-149">Configure e mantenha Teams de gravação para a organização.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-149">Configure and maintain Teams recording policies for the organization.</span></span></p></li>
<li><p><span data-ttu-id="b6cb3-150">Monitore e solucione problemas relacionados à gravação com Teams chamadas e reuniões.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-150">Monitor and troubleshoot recording-related issues with Teams calls and meetings.</span></span></p></li>
<li><p><span data-ttu-id="b6cb3-151">Suporte ao responsável pela conformidade interna com análises operacionais sobre uso, qualidade e confiabilidade.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-151">Support internal compliance officer with operational analytics on usage, quality, and reliability.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="b6cb3-152">Responsável pela conformidade</span><span class="sxs-lookup"><span data-stu-id="b6cb3-152">Compliance officer</span></span></td>
<td><ul>
<li><p><span data-ttu-id="b6cb3-153">Colete todas as Teams comunicações da maneira necessária para cumprir as obrigações de conformidade nos limites regionais apropriados.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-153">Collect all Teams communications in the manner required to meet compliance obligations in appropriate regional boundaries.</span></span></p></li>
<li><p><span data-ttu-id="b6cb3-154">Pesquise interações com base em metadados relacionados à comunicação ou conteúdo de interação.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-154">Search for interactions based on communication-related metadata or interaction content.</span></span> <span data-ttu-id="b6cb3-155">Exemplos comuns incluem:</span><span class="sxs-lookup"><span data-stu-id="b6cb3-155">Common examples include:</span></span></p>
<ul>
<li><p><span data-ttu-id="b6cb3-156"><strong>Metadados</strong> - Participantes, hora, direção, número discado, número de origem, dados comerciais personalizados</span><span class="sxs-lookup"><span data-stu-id="b6cb3-156"><strong>Metadata</strong> - Participants, time, direction, dialed number, origin number, Custom business data</span></span></p></li>
<li><p><span data-ttu-id="b6cb3-157"><strong>Conteúdo</strong> – Transcrição, sentimento, phonetics, interações relacionadas</span><span class="sxs-lookup"><span data-stu-id="b6cb3-157"><strong>Content</strong> – Transcription, sentiment, phonetics, related interactions</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="b6cb3-158">Analise e interaja com comunicações coletadas, incluindo a capacidade de monitorar interações enquanto elas estão sendo coletadas.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-158">Analyze and interact with collected communications, including the ability to monitor interactions as they are being collected.</span></span></p></li>
<li><p><span data-ttu-id="b6cb3-159">Garantir a segurança das comunicações coletadas e impedir a adulteração em todos os estágios.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-159">Ensure security of collected communications and prevent tampering at all stages.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

## <a name="solution-architecture-overview"></a><span data-ttu-id="b6cb3-160">Visão geral da arquitetura de soluções</span><span class="sxs-lookup"><span data-stu-id="b6cb3-160">Solution architecture overview</span></span>

<span data-ttu-id="b6cb3-161">As soluções de registro de conformidade são integradas Teams conforme mostrado no diagrama a seguir:</span><span class="sxs-lookup"><span data-stu-id="b6cb3-161">Compliance recording solutions are integrated with Teams as shown in the following diagram:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="b6cb3-162">![Captura de tela mostrando a configuração do aplicativo personalizado da equipe](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "As imagens mostram o fluxo quando uma Teams ou chamada é enviada e recebida.")</span><span class="sxs-lookup"><span data-stu-id="b6cb3-162">![Screenshot showing the team custom app setting](media/hp-compliance-recording-for-teams-calling-and-meetings.jpg "The images shows the flow when a Teams meeting or call is sent and received.")</span></span>

## <a name="recorder"></a><span data-ttu-id="b6cb3-163">Gravador</span><span class="sxs-lookup"><span data-stu-id="b6cb3-163">Recorder</span></span>

<span data-ttu-id="b6cb3-164">O componente principal da solução de registro de conformidade é o gravador.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-164">The core component of the compliance recording solution is the recorder.</span></span>
<span data-ttu-id="b6cb3-165">Os gravadores são construídos como serviços dimensionáveis baseados no Azure (bots) que aproveitam a plataforma de comunicações da [Microsoft](/graph/cloud-communications-concept-overview) e se registram como aplicativos com o Microsoft Graph.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-165">Recorders are built as scalable Azure-based services (bots) that [leverage Microsoft’s communications platform](/graph/cloud-communications-concept-overview) and register as applications with Microsoft Graph.</span></span> <span data-ttu-id="b6cb3-166">O gravador fornece a interação direta com as [APIs](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) da plataforma de comunicações Teams reuniões e fornece o ponto de extremidade para ingestão de mídia.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-166">The recorder provides the direct interaction with the Teams calls and meetings [communications platform APIs](/graph/api/resources/communications-api-overview?view=graph-rest-1.0) and provides the endpoint for media ingestion.</span></span>

<span data-ttu-id="b6cb3-167">Um [aplicativo de gravador de conformidade](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) de exemplo está disponível que mostra como configurar o bot, criar a instância do aplicativo e atribuir as políticas de conformidade.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-167">A [sample compliance recorder application is available](https://github.com/microsoftgraph/microsoft-graph-comms-samples/tree/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot) that shows how to configure the bot, create the app instance and assign the compliance policies.</span></span> <span data-ttu-id="b6cb3-168">O exemplo também tem exemplos sobre o uso [](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) da API para gravar interações específicas, como manipular o roteamento de chamadas de [entrada,](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138)alterar estados de gravação e remover o usuário que está [sendo gravado](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span><span class="sxs-lookup"><span data-stu-id="b6cb3-168">The sample also has examples on API usage for recording specific interactions such as handling [incoming call](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Http/Controllers/PlatformCallController.cs#L199-L244) routing, [changing recording states](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L135-L138), and [removing the user who is being recorded](https://github.com/microsoftgraph/microsoft-graph-comms-samples/blob/a3943bafd73ce0df780c0e1ac3428e3de13a101f/Samples/BetaSamples/LocalMediaSamples/ComplianceRecordingBot/FrontEnd/Bot/CallHandler.cs#L121-L126).</span></span>
<span data-ttu-id="b6cb3-169">Graph documentação sobre APIs específicas pode ser encontrada aqui para [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) e [incomingContext](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span><span class="sxs-lookup"><span data-stu-id="b6cb3-169">Graph documentation on the specific APIs can be found here for [updateRecordingStatus](/graph/api/call-updaterecordingstatus?tabs=http&view=graph-rest-1.0) and [incomingContext](/graph/api/resources/incomingcontext?view=graph-rest-1.0).</span></span>

<span data-ttu-id="b6cb3-170">A implementação exata do serviço de gravador varia de acordo com o parceiro, mas deve ser projetada para dar suporte a vários gravadores para alcançar alta disponibilidade e distribuição geográfica da implantação para reduzir a latência de Teams para o gravador.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-170">The exact implementation of the recorder service will vary by partner but must be designed to support multiple recorders in order to achieve high availability and geographical distribution of deployment to reduce latency from Teams to the recorder.</span></span> <span data-ttu-id="b6cb3-171">Além disso, é esperado que os próprios Gravadores sejam projetados com resiliência e redundância em mente.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-171">In addition, it is expected that Recorders themselves be designed with resiliency and redundancy in mind.</span></span>

<span data-ttu-id="b6cb3-172">Os parceiros devem confirmar a versão de versão mínima necessária das APIs e SDKs de comunicações do Microsoft Graph com a Microsoft antes de enviar sua solução para certificação para garantir que todos os requisitos de integração de registro de conformidade sejam suportados.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-172">Partners must confirm the minimum required release version of the Microsoft Graph communications APIs and SDKs with Microsoft before submitting their solution for certification to ensure that all requirements of compliance recording integration are supported.</span></span>

<span data-ttu-id="b6cb3-173">Dois requisitos específicos que são fundamentais para o cenário de registro de conformidade são:</span><span class="sxs-lookup"><span data-stu-id="b6cb3-173">Two specific requirements that are fundamental for compliance recording scenario are:</span></span>

- <span data-ttu-id="b6cb3-174">O bot do gravador deve ser implantado no Azure</span><span class="sxs-lookup"><span data-stu-id="b6cb3-174">Recorder bot must be deployed in Azure</span></span>

- <span data-ttu-id="b6cb3-175">O bot do gravador deve ser executado em uma Windows VM no Azure</span><span class="sxs-lookup"><span data-stu-id="b6cb3-175">Recorder bot must run on a Windows VM in Azure</span></span>

<span data-ttu-id="b6cb3-176">Os requisitos do Azure e Windows VM aplicam-se apenas ao componente bot do Teams, o que significa que um parceiro pode implementar o restante da plataforma de sua escolha, desde que possa atender aos requisitos funcionais e de desempenho relevantes para o registro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-176">The Azure and Windows VM requirements only apply to the Teams Bot component, which means that a partner may implement the rest of the platform of their choice provided they can meet the relevant performance and functional requirements for compliance recording.</span></span>

## <a name="compliance-recording-policy-assignment-and-provisioning"></a><span data-ttu-id="b6cb3-177">Atribuição e provisionamento da política de registro de conformidade</span><span class="sxs-lookup"><span data-stu-id="b6cb3-177">Compliance recording policy assignment and provisioning</span></span>

<span data-ttu-id="b6cb3-178">Os administradores de IT podem determinar quais usuários devem ser gravados e qual gravador será usado para cada usuário, criando e atribuindo políticas de registro de conformidade.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-178">IT Administrators can determine which users are to be recorded and which recorder will be used for each user, by creating and assigning compliance recording policies.</span></span> <span data-ttu-id="b6cb3-179">Os gravadores são automaticamente convidados a participar de conversas com base na configuração dessas políticas quando uma interação de comunicação ocorre.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-179">Recorders are automatically invited to participate in conversations based on the configuration of these policies when a communication interaction takes place.</span></span> <span data-ttu-id="b6cb3-180">As políticas de registro de conformidade são gerenciadas usando [o Microsoft PowerShell](./teams-powershell-overview.md) e podem ser aplicadas no nível de locatário, por usuário e grupo de segurança para cada organização.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-180">Compliance recording policies are managed using [Microsoft PowerShell](./teams-powershell-overview.md) and can be applied at the tenant, per-user, and security group level for each organization.</span></span> <span data-ttu-id="b6cb3-181">Você pode encontrar mais informações sobre as políticas do Microsoft Docs for [Meeting,](./meeting-policies-in-teams.md) [políticas de chamada](./teams-calling-policy.md) e políticas de [grupo.](./assign-policies.md#assign-a-policy-to-a-group)</span><span class="sxs-lookup"><span data-stu-id="b6cb3-181">You can find more information on Microsoft Docs for [Meeting policies](./meeting-policies-in-teams.md), [calling policies](./teams-calling-policy.md) and  [group policies](./assign-policies.md#assign-a-policy-to-a-group).</span></span>

1. <span data-ttu-id="b6cb3-182">Crie uma instância de aplicativo em seu locatário.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-182">Create an application instance in your tenant.</span></span>

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

2. <span data-ttu-id="b6cb3-183">Criar uma política de Registro de Conformidade.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-183">Create a Compliance Recording policy.</span></span>

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

   <span data-ttu-id="b6cb3-184">Consulte [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b6cb3-184">See [Set-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/set-csteamscompliancerecordingpolicy?view=skype-ps).</span></span>

3. <span data-ttu-id="b6cb3-185">Atribua a política de Registro de Conformidade a um usuário.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-185">Assign the Compliance Recording policy to a user.</span></span>

   ```powershell
   PS C:\> Grant-CsTeamsComplianceRecordingPolicy -Identity testuser@contoso.onmicrosoft.com -PolicyName TestComplianceRecordingPolicy
   ```

   <span data-ttu-id="b6cb3-186">Consulte [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps).</span><span class="sxs-lookup"><span data-stu-id="b6cb3-186">See [Grant-CsTeamsComplianceRecordingPolicy](/powershell/module/skype/grant-csteamscompliancerecordingpolicy?view=skype-ps).</span></span>

   ```powershell
   PS C:\> Get-CsOnlineUser testuser@contoso.onmicrosoft.com | select SipAddress, TenantId, TeamsComplianceRecordingPolicy | fl

   UserPrincipalName              : testuser@contoso.onmicrosoft.com
   TenantId                       : 5b943d7c-5e14-474b-8237-5022eb8e0dc9
   TeamsComplianceRecordingPolicy : TestComplianceRecordingPolicy
   ```

## <a name="user-experiences"></a><span data-ttu-id="b6cb3-187">Experiências do usuário</span><span class="sxs-lookup"><span data-stu-id="b6cb3-187">User experiences</span></span>

<span data-ttu-id="b6cb3-188">O suporte para notificações é habilitado usando as experiências Teams cliente.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-188">Support for notifications is enabled using the Teams client experiences.</span></span> <span data-ttu-id="b6cb3-189">As experiências podem ser visuais ou de áudio.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-189">The experiences can be either visual or audio.</span></span>

<span data-ttu-id="b6cb3-190">**Teams clientes - aviso visual**</span><span class="sxs-lookup"><span data-stu-id="b6cb3-190">**Teams clients - visual notice**</span></span>
- <span data-ttu-id="b6cb3-191">Área de trabalho/web</span><span class="sxs-lookup"><span data-stu-id="b6cb3-191">Desktop/web</span></span>
- <span data-ttu-id="b6cb3-192">Mobile (iOS/Android)</span><span class="sxs-lookup"><span data-stu-id="b6cb3-192">Mobile (iOS/Android)</span></span>
- <span data-ttu-id="b6cb3-193">Teams telefones</span><span class="sxs-lookup"><span data-stu-id="b6cb3-193">Teams phones</span></span>
- <span data-ttu-id="b6cb3-194">Teams salas</span><span class="sxs-lookup"><span data-stu-id="b6cb3-194">Teams rooms</span></span>

<span data-ttu-id="b6cb3-195">**Outros pontos de extremidade - aviso de áudio**</span><span class="sxs-lookup"><span data-stu-id="b6cb3-195">**Other endpoints - audio notice**</span></span>
- <span data-ttu-id="b6cb3-196">Telefones SIP</span><span class="sxs-lookup"><span data-stu-id="b6cb3-196">SIP phones</span></span>
- <span data-ttu-id="b6cb3-197">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="b6cb3-197">Skype for Business</span></span>
- <span data-ttu-id="b6cb3-198">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="b6cb3-198">Audio conferencing</span></span>
- <span data-ttu-id="b6cb3-199">Chamadores PSTN</span><span class="sxs-lookup"><span data-stu-id="b6cb3-199">PSTN callers</span></span>

## <a name="compliance-recording-for-teams-certification-programs"></a><span data-ttu-id="b6cb3-200">Registro de conformidade para Teams de certificação</span><span class="sxs-lookup"><span data-stu-id="b6cb3-200">Compliance recording for Teams certification programs</span></span>

<span data-ttu-id="b6cb3-201">Além de publicar APIs disponíveis publicamente, permitindo que os parceiros desenvolvam e integrem soluções CCaaS com o Teams, desenvolvemos o registro de conformidade para o programa de certificação do Microsoft Teams para fornecer aos clientes a garantia de que a solução de cada parceiro participante foi testada e verificada para fornecer a qualidade, compatibilidade e confiabilidade esperadas das soluções da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-201">In addition to publishing publicly available APIs allowing partners to develop and integrate CCaaS solutions with Teams, we have developed the compliance recording for Microsoft Teams certification program to provide customers with the assurance that each participating partner’s solution has been tested and verified to provide the quality, compatibility and reliability they expect from Microsoft solutions.</span></span>  

<span data-ttu-id="b6cb3-202">Os parceiros a seguir certificados sua solução para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-202">The following partners have certified their solution for Microsoft Teams.</span></span><br/><br/>

|<span data-ttu-id="b6cb3-203">Parceiro</span><span class="sxs-lookup"><span data-stu-id="b6cb3-203">Partner</span></span>|<span data-ttu-id="b6cb3-204">Site da solução</span><span class="sxs-lookup"><span data-stu-id="b6cb3-204">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="b6cb3-205">Tecnologias ASC</span><span class="sxs-lookup"><span data-stu-id="b6cb3-205">ASC Technologies</span></span> |[https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html](https://www.asctechnologies.com/english/ASC_Recording_Insights_Compliance_Recording_for_Microsoft_Teams.html) |
|<span data-ttu-id="b6cb3-206">AudioCodes</span><span class="sxs-lookup"><span data-stu-id="b6cb3-206">AudioCodes</span></span> |[https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360](https://www.audiocodes.com/solutions-products/voiceai/meetings-and-recording/smarttap-360) |
|<span data-ttu-id="b6cb3-207">Selador</span><span class="sxs-lookup"><span data-stu-id="b6cb3-207">Dubber</span></span> |[https://www.dubber.net/call-recording/](https://www.dubber.net/call-recording/) |
|<span data-ttu-id="b6cb3-208">NICE</span><span class="sxs-lookup"><span data-stu-id="b6cb3-208">NICE</span></span> |[https://www.niceactimize.com/compliance/ms-teams-recording.html](https://www.niceactimize.com/compliance/ms-teams-recording.html) |
|<span data-ttu-id="b6cb3-209">Numonix</span><span class="sxs-lookup"><span data-stu-id="b6cb3-209">Numonix</span></span> |[https://numonix.cloud](https://numonix.cloud)    |
|<span data-ttu-id="b6cb3-210">Verint</span><span class="sxs-lookup"><span data-stu-id="b6cb3-210">Verint</span></span> |[https://www.verba.com/solutions/microsoft-teams-recording](https://www.verba.com/solutions/microsoft-teams-recording) |
|<span data-ttu-id="b6cb3-211">Theta Lake</span><span class="sxs-lookup"><span data-stu-id="b6cb3-211">Theta Lake</span></span> |[https://thetalake.com/integrations/microsoft/](https://thetalake.com/integrations/microsoft/) |
|<span data-ttu-id="b6cb3-212">CallCabinet</span><span class="sxs-lookup"><span data-stu-id="b6cb3-212">CallCabinet</span></span> |[https://www.callcabinet.com/compliance-microsoft-teams-call-recording](https://www.callcabinet.com/compliance-microsoft-teams-call-recording ) |

<br/>
<span data-ttu-id="b6cb3-213">Os parceiros a seguir estão no processo de certificar sua solução para Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-213">The following partners are in the process of certifying their solution for Microsoft Teams.</span></span><br/><br/>

|<span data-ttu-id="b6cb3-214">Parceiro</span><span class="sxs-lookup"><span data-stu-id="b6cb3-214">Partner</span></span>|<span data-ttu-id="b6cb3-215">Site da solução</span><span class="sxs-lookup"><span data-stu-id="b6cb3-215">Solution website</span></span> |
|:--|:--|
|<span data-ttu-id="b6cb3-216">Tecnologias Landis</span><span class="sxs-lookup"><span data-stu-id="b6cb3-216">Landis Technologies</span></span> |[https://landistechnologies.com/](https://landistechnologies.com/) |
|<span data-ttu-id="b6cb3-217">Luware</span><span class="sxs-lookup"><span data-stu-id="b6cb3-217">Luware</span></span> |[https://luware.com/en/solution/microsoft-teams-recording/](https://luware.com/en/solution/microsoft-teams-recording/) |
|<span data-ttu-id="b6cb3-218">Inovação de Carvalho</span><span class="sxs-lookup"><span data-stu-id="b6cb3-218">Oak Innovation</span></span> |[https://www.oakinnovate.com/call-recording](https://www.oakinnovate.com/call-recording) |
|<span data-ttu-id="b6cb3-219">Caixa Vermelha</span><span class="sxs-lookup"><span data-stu-id="b6cb3-219">Red Box</span></span> |[https://www.redboxvoice.com/compliance-recording-for-microsoft-teams](https://www.redboxvoice.com/compliance-recording-for-microsoft-teams)  |

<span data-ttu-id="b6cb3-220">Essa lista será atualizada à medida que mais parceiros ingressarem e atenderem aos critérios de certificação.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-220">This list will be updated as more partners join and meet the certification criteria.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b6cb3-221">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="b6cb3-221">Next steps</span></span>

<span data-ttu-id="b6cb3-222">Se você for um fornecedor que está tentando ingressar no programa de certificação, por favor,  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span><span class="sxs-lookup"><span data-stu-id="b6cb3-222">If you are a vendor seeking to join the certification program, please mail  <a href= "mailto:Teamscategorypartner@microsoft.com">Teamscategorypartner@microsoft.com</a>.</span></span>
