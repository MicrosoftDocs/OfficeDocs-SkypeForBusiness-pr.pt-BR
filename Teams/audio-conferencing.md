---
title: "Audioconferência no Microsoft Teams"
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
description: "Orientações práticas para a implantação de Audioconferência no Microsoft Teams."
Set_Free_Tag: Strat_MT_TeamsAdmin
ms.openlocfilehash: 5442f5bf11540f5429566bc683afaeb3a24ff4ac
ms.sourcegitcommit: 2592b268977460d0d483a75d741b1ce9fa8da908
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/28/2017
---
<a name="audio-conferencing-in-microsoft-teams"></a><span data-ttu-id="16df8-103">Audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16df8-103">Audio Conferencing in Microsoft Teams</span></span>
=====================================

> [!IMPORTANT]
> <span data-ttu-id="16df8-104">A Audioconferência está em uma prévia pública.</span><span class="sxs-lookup"><span data-stu-id="16df8-104">Audio conferencing is in public preview.</span></span> <span data-ttu-id="16df8-105">Está disponível para adotantes precoces (EA) e clientes da prévia, e poderá sofrer modificações ao ser lançada ou atualizada.</span><span class="sxs-lookup"><span data-stu-id="16df8-105">It's available to Early Adopters (EA) and preview customers and could change as it is released or updated.</span></span>

<span data-ttu-id="16df8-106">A Audioconferência do Office 365 (conhecida anteriormente como Conferência PSTN) permite que os participantes entrem em reuniões a partir de qualquer telefone.</span><span class="sxs-lookup"><span data-stu-id="16df8-106">Audio Conferencing in Office 365 (formerly known as PSTN Conferencing) allows participants to join your meetings from any telephone.</span></span> <span data-ttu-id="16df8-107">Esse recurso está agora disponível no Microsoft Teams em prévia pública, permitindo que os usuários entrem em reuniões do Teams usando seus telefones.</span><span class="sxs-lookup"><span data-stu-id="16df8-107">This feature is now available in Microsoft Teams, in public preview, allowing users to join Teams meetings using their phones.</span></span> <span data-ttu-id="16df8-108">As orientações práticas deste artigo levam você pela estrutura da jornada do cliente do Office 365 FastTrack para Audioconferência - Concepção, Integração e Geração de valor.</span><span class="sxs-lookup"><span data-stu-id="16df8-108">The practical guidance in this article steps you through the Office 365 FastTrack customer journey framework for Audio Conferencing - Envision, Onboard, and Drive value.</span></span>

<span data-ttu-id="16df8-109">Eis o que você obtém com a [Audioconferência](https://go.microsoft.com/fwlink/?linkid=858992) no Office 365.</span><span class="sxs-lookup"><span data-stu-id="16df8-109">Here's what you get with [Audio Conferencing](https://go.microsoft.com/fwlink/?linkid=858992) in Office 365.</span></span>

> [!NOTE]
> <span data-ttu-id="16df8-110">A Audioconferência suporta tanto o Teams, quanto o Skype for Business Online.</span><span class="sxs-lookup"><span data-stu-id="16df8-110">Audio Conferencing supports both Teams and Skype for Business Online.</span></span> <span data-ttu-id="16df8-111">No momento, o centro de administração do Skype for Business e o PowerShell remota oferecem as interfaces administrativas para gerenciar a Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-111">Currently, the existing Skype for Business Admin center and remote PowerShell provide the administrative interfaces to manage Audio Conferencing.</span></span>


|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AGPvaW4Vg0o" frameborder="0" allowfullscreen></iframe>   | |

<span data-ttu-id="16df8-112">Concepção <a name="Envision_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="16df8-112">Envision <a name="Envision_AudioConferencing"> </a></span></span>
=========

<span data-ttu-id="16df8-113">A fase de Concepção oferece a base a jornada do cliente Office 365 e se aplica a todas as cargas de trabalho, como a Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-113">The Envision phase provides the foundation for the Office 365 customer journey and is applicable to all workloads such as Audio Conferencing.</span></span>

<span data-ttu-id="16df8-114">Nessa fase, os objetivos de negócios são estabelecidos com as partes envolvidas relevantes do projeto reunidas, para entregar:</span><span class="sxs-lookup"><span data-stu-id="16df8-114">In this phase, business goals are captured, with relevant project stakeholders assembled, to ultimately deliver:</span></span>

-   <span data-ttu-id="16df8-115">um plano de sucesso e de alto nível que tenha casos de uso comercial, as principais partes envolvidas, os objetivos e os resultados principais(OKRs), os principais indicadores de sucesso (KSIs), os riscos, a avaliação do ambiente, a prontidão para adoção e o plano operacional.</span><span class="sxs-lookup"><span data-stu-id="16df8-115">a high-level success plan that contains business use cases, key stakeholders, objectives and key results (OKRs), key success indicators (KSIs), risks, environmental assessment, adoption readiness, and operational plan.</span></span>

-   <span data-ttu-id="16df8-116">e, posteriormente, um plano detalhado da implementação técnica da Audioconferência para atingir o status final desejado.</span><span class="sxs-lookup"><span data-stu-id="16df8-116">and subsequently, a detailed Audio Conferencing technical implementation plan to achieve the desired end state.</span></span>

<a name="define-business-use-cases-for-audio-conferencing"></a><span data-ttu-id="16df8-117">Definição de casos de uso comercial para Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-117">Define business use cases for Audio Conferencing</span></span>
------------------------------------------------

<span data-ttu-id="16df8-118">A Audioconferência oferece à organização pontos de entradas adicionais para todas as reuniões agendadas ao permitir que os participantes entrem via PSTN discando pelo tradicional telefone fixo, PBX ou telefones celulares.</span><span class="sxs-lookup"><span data-stu-id="16df8-118">Audio Conferencing provides organizations with additional entry points to any scheduled meetings by allowing meeting participants to join via PSTN by dialing in using traditional landline, PBX, or mobile phones.</span></span>

<span data-ttu-id="16df8-119">Isso é útil quando o organizador ou os participantes não estão na frente do computador ou quando as conexões de dados estão indisponíveis ou não são confiáveis para o suporte a comunicações de voz, como em áreas remotas com cobertura irregular de dados móveis ou conexão a um serviço de Wi-Fi público com largura de banda limitada, ou quando os participantes da reunião preferem discar para a reunião usando o endpoint de telefonia que possam acessar prontamente.</span><span class="sxs-lookup"><span data-stu-id="16df8-119">This is useful when the organizer or participants are not in front of a computer, or when data connections are unavailable or unreliable to support voice communications—such as when in a remote area with spotty mobile data coverage, or if connected to a free, public Wi-Fi service with limited bandwidth, or when meeting participants prefer to dial in to the meeting using telephony endpoint readily accessible to them.</span></span>

<span data-ttu-id="16df8-120">Nessa etapa, as principais partes envolvidas no projeto definirão os casos de uso comercial que suportem a implementação de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-120">In this step, core project stakeholders will define business use cases that support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="16df8-121">Os casos de uso comercial devem definir e documentar os resultados comerciais esperados e mensuráveis, e incluir o que segue:</span><span class="sxs-lookup"><span data-stu-id="16df8-121">Business use cases are meant to define and document the expected and measurable business outcomes, and include the following:</span></span>

-   <span data-ttu-id="16df8-122">Descrição do processo comercial atual.</span><span class="sxs-lookup"><span data-stu-id="16df8-122">Description of current business process.</span></span>

-   <span data-ttu-id="16df8-123">Definição dos desafios com os processos comerciais existentes.</span><span class="sxs-lookup"><span data-stu-id="16df8-123">Challenges with existing business process defined.</span></span>

-   <span data-ttu-id="16df8-124">Como a tecnologia pode ajudar a superar esses desafios.</span><span class="sxs-lookup"><span data-stu-id="16df8-124">How technology can help overcome these challenges.</span></span>

-   <span data-ttu-id="16df8-125">Os resultados comerciais esperados e mensuráveis se esses desafios forem superados.</span><span class="sxs-lookup"><span data-stu-id="16df8-125">The expected and measurable business outcome if these challenges are overcome.</span></span>

<table>
<tbody>
<tr class="header">
<th align="left"><p><img src="media/audio_conferencing_image2.png" /></p></th>
<td align="left"><p><span data-ttu-id="16df8-126"><strong>Descrição do processo comercial atual</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-126"><strong>Description of current business process</strong></span></span></p>
<p><span data-ttu-id="16df8-127">A Contoso conta atualmente com serviços de conferência PSTN fornecidos pelo provedor de telefonia local vigente, cobrados por minutos de reunião para reuniões internas e reuniões envolvendo partes externas.</span><span class="sxs-lookup"><span data-stu-id="16df8-127">Contoso currently relies on PSTN conferencing services provided by the incumbent local telephony provider chargeable by meeting minutes for internal meetings and meetings involving external parties.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image3.png" /></p></td>
<td align="left"><p><span data-ttu-id="16df8-128"><strong>Desafios com os processos comerciais existentes</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-128"><strong>Challenges with existing business process</strong></span></span></p>
<p><span data-ttu-id="16df8-129">A Contoso gasta cerca de US$ 1 milhão por ano com o serviço de conferência PSTN atual, com 75% do custo incorrendo para reuniões internas.</span><span class="sxs-lookup"><span data-stu-id="16df8-129">Contoso spends roughly USD 1 million per year for the current PSTN conferencing service, with 75% of the cost incurred for internal meetings.</span></span></p>
<p><span data-ttu-id="16df8-130">O uso dos endpoints tradicionais de telefonia para entrar em reuniões hospedadas pelo serviço de conferência PSTN não está alinhado com o plano de a organização adotar o Teams como uma plataforma de colaboração e comunicação moderna.</span><span class="sxs-lookup"><span data-stu-id="16df8-130">The use of traditional telephony endpoints to join the meetings hosted by the PSTN conferencing service is not aligned with the plan for the organization to adopt Teams as modern communications and collaboration platform.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><img src="media/audio_conferencing_image4.png" /></p></td>
<td align="left"><p><span data-ttu-id="16df8-131"><strong>Como a tecnologia pode superar esses desafios</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-131"><strong>How technology can overcome these challenges</strong></span></span></p>
<p><span data-ttu-id="16df8-132">Com a adoção do Microsoft Teams como uma plataforma de colaboração e comunicação moderna, espera-se que os usuários internos participem principalmente de reuniões usando seus PCs equipados com fones de ouvido otimizados e dispositivos de sala de reunião.</span><span class="sxs-lookup"><span data-stu-id="16df8-132">With the adoption of Microsoft Teams as modern communications and collaboration platform, internal users are expected to primarily join meetings using their PCs equipped with optimized headsets and meeting room devices.</span></span> <span data-ttu-id="16df8-133">O serviço de Audioconferência estará disponível para ter suporte para participantes externos ou situações em que o uso do áudio do PC não seja favorável para os participantes internos.</span><span class="sxs-lookup"><span data-stu-id="16df8-133">Audio Conferencing service will be available to support external participants or to support situations where the use of PC audio is not favorable for the internal participants.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><img src="media/audio_conferencing_image5.png" /></p></td>
<td align="left"><p><span data-ttu-id="16df8-134"><strong>Resultados comerciais esperados e mensuráveis</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-134"><strong>Expected, measurable, business outcomes</strong></span></span></p>
<p><span data-ttu-id="16df8-135">A mudança para o Teams como uma plataforma de colaboração e comunicação moderna, aliada ao serviço de Audioconferência, reduzirá consideravelmente o custo de entrega do serviço de conferência PSTN, ao ponto que a Contoso deverá gastar apenas cerca de 20% do custo anual do serviço de conferência PSTN existente.</span><span class="sxs-lookup"><span data-stu-id="16df8-135">The move to Teams as modern communications and collaboration platform, combined with Audio Conferencing service, will greatly reduce the cost to deliver the PSTN conferencing service to the point that Contoso is expected to only spend approximately 20% of the annual cost of the existing PSTN conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-136">_Tabela 1 Exemplo de casos de uso comercial_</span><span class="sxs-lookup"><span data-stu-id="16df8-136">_Table 1 Business use case example_</span></span>


<span data-ttu-id="16df8-137">Além de definir os casos de uso comercial, ter clareza sobre o escopo organizacional e os cronogramas do projeto nessa fase ajudará na passagem para a próxima fase de Concepção.</span><span class="sxs-lookup"><span data-stu-id="16df8-137">In addition to defining the business use cases, having a clarity around the organizational scope and project timelines at this step helps move onto the next step of the Envision phase.</span></span>

<a name="identify-key-stakeholders"></a><span data-ttu-id="16df8-138">Identificar as principais partes envolvidas</span><span class="sxs-lookup"><span data-stu-id="16df8-138">Identify key stakeholders</span></span>
-------------------------

<span data-ttu-id="16df8-139">Os casos de uso comercial definidos na etapa anterior incluirão o escopo organizacional da implementação da Audioconferência e, com base nisso, a matriz abrangente das partes envolvidas pode ser completada para incluir as pessoas certas a serem envolvidas no projeto.</span><span class="sxs-lookup"><span data-stu-id="16df8-139">The business use cases defined in the previous step will include organizational scope of Audio Conferencing implementation, and based on that, the comprehensive stakeholder matrix can be completed to include the right people to be involved in the project.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-140">Função</span><span class="sxs-lookup"><span data-stu-id="16df8-140">Role</span></span></th>
<th align="left"><span data-ttu-id="16df8-141">Descrição</span><span class="sxs-lookup"><span data-stu-id="16df8-141">Description</span></span></th>
<th align="left"><span data-ttu-id="16df8-142">Nome, informações de contato, localização</span><span class="sxs-lookup"><span data-stu-id="16df8-142">Name, contact information, location</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-143"><strong>Patrocinador executivo do projeto</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-143"><strong>Project Executive Sponsor</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-144">A autoridade e a responsabilidade final pelo projeto e pela entrega dos objetivos do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-144">Ultimate authority and accountability for the project and delivery on project objectives</span></span></li>
<li><span data-ttu-id="16df8-145">Ajudar a solucionar problemas escalados pelo Líder do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-145">Help resolve issues escalated by Project Lead</span></span></li>
<li><span data-ttu-id="16df8-146">Comunicação do patrocinador internamente na empresa sobre os objetivos do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-146">Sponsors communication within the company about project goals</span></span></li>
<li><span data-ttu-id="16df8-147">Responsável pela tomada de decisões estratégicas</span><span class="sxs-lookup"><span data-stu-id="16df8-147">Responsible for making key strategic decisions</span></span></li>
<li><span data-ttu-id="16df8-148">Responsável pela disponibilidade do orçamento e dos recursos necessários</span><span class="sxs-lookup"><span data-stu-id="16df8-148">Responsible for availability of required resources and budget</span></span></p>
<li><span data-ttu-id="16df8-149">Liderança da avaliação trimestral de negócios (QBR)</span><span class="sxs-lookup"><span data-stu-id="16df8-149">Leading Quarterly Business Reviews (QBR)</span></span></li>
<li><span data-ttu-id="16df8-150">Aceitação e ajuda nos esforços da campanha de conscientização</span><span class="sxs-lookup"><span data-stu-id="16df8-150">Buy-In and support of awareness campaign effort</span></span></li>
<li><span data-ttu-id="16df8-151">Atuando como patrocinador do projeto de distribuição do programa</span><span class="sxs-lookup"><span data-stu-id="16df8-151">Serving as the Project Sponsor to the program rollout</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-152">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-152">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-153"><strong>Líder de projeto</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-153"><strong>Project Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-154">Gerenciamento e liderança da equipe do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-154">Managing and leading project team</span></span></li>
<li><span data-ttu-id="16df8-155">Coordena os parceiros e as equipes de trabalho envolvidos no projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-155">Coordinates partners and working teams engaged in the project</span></span></li>
<li><span data-ttu-id="16df8-156">Responsável pela criação e pelo gerenciamento dos planos do projeto para atingir os principais resultados trimestrais</span><span class="sxs-lookup"><span data-stu-id="16df8-156">Accountable for creating and managing project plans to meet quarterly key results</span></span></li>
<li><span data-ttu-id="16df8-157">Solucionar problemas multifuncionais</span><span class="sxs-lookup"><span data-stu-id="16df8-157">Resolving cross-functional issues</span></span></li>
<li><span data-ttu-id="16df8-158">Passar atualizações regulares aos patrocinadores do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-158">Providing regular updates to the project sponsors</span></span></li>
<li><span data-ttu-id="16df8-159">Incorporação dos aspectos de adoção em todo o plano do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-159">Incorporating Adoption aspects into the all-up project plan</span></span></li>
<li><span data-ttu-id="16df8-160">Liderança das avaliações mensais de negócios e operações (MBR), contribuindo com as avaliações trimestrais de negócios</span><span class="sxs-lookup"><span data-stu-id="16df8-160">Leading Monthly Business and Operational Reviews (MBR), contributing to Quarterly Business Reviews</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-161">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-161">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-162"><strong>Líder/arquiteto de colaboração</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-162"><strong>Collaboration Lead/Architect</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-163">Responsável pela execução da estratégia de colaboração definida pelos executivos da empresa</span><span class="sxs-lookup"><span data-stu-id="16df8-163">Responsible for execution on collaboration strategy defined by company executives</span></span></li>
<li><span data-ttu-id="16df8-164">Analisar e escolher produtos de colaboração para a empresa que atendam aos objetivos de negócios</span><span class="sxs-lookup"><span data-stu-id="16df8-164">Analyzing and choosing collaboration products for the company that meets business goals</span></span></li>
<li><span data-ttu-id="16df8-165">Responsável pela concepção das operações dos produtos de colaboração</span><span class="sxs-lookup"><span data-stu-id="16df8-165">Responsible for the design of the operations for collaboration products</span></span></li>
<li><span data-ttu-id="16df8-166">Define o modelo de operação e suporte</span><span class="sxs-lookup"><span data-stu-id="16df8-166">Defines operation and support model</span></span></li>
<li><span data-ttu-id="16df8-167">Contribuir com as avaliações trimestrais de negócios</span><span class="sxs-lookup"><span data-stu-id="16df8-167">Contributing to Monthly and Quarterly Business Reviews</span></span></li><ul></td>
<td align="left"><span data-ttu-id="16df8-168">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-168">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-169"><strong>Consultor</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-169"><strong>Consultant</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-170">Responsável pelos serviços de configuração</span><span class="sxs-lookup"><span data-stu-id="16df8-170">Responsible for configuration services</span></span></li>
<li><span data-ttu-id="16df8-171">Contribui na arquitetura geral da solução</span><span class="sxs-lookup"><span data-stu-id="16df8-171">Contributes in overall solution architecture</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-172">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-172">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-173"><strong>Gerente de projetos</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-173"><strong>Project Manager</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-174">Desenvolvimento e manutenção do plano do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-174">Developing and maintaining project plan</span></span></li>
<li><span data-ttu-id="16df8-175">Gerenciar os produtos finais do projeto de acordo com o plano do projeto e o orçamento</span><span class="sxs-lookup"><span data-stu-id="16df8-175">Managing project deliverables in line with project plan and budget</span></span></li>
<li><span data-ttu-id="16df8-176">Registrar e gerenciar os problemas de projeto, incluindo o dimensionamento</span><span class="sxs-lookup"><span data-stu-id="16df8-176">Recording and managing project issues, including escalations</span></span></li>
<li><span data-ttu-id="16df8-177">Conduzir chamadas stand up semanais</span><span class="sxs-lookup"><span data-stu-id="16df8-177">Conducting weekly stand up calls</span></span></li>
<li><span data-ttu-id="16df8-178">Conectar-se e passar atualizações para patrocinadores executivos do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-178">Liaises with, and provides updates to project executive sponsors</span></span></li>
<li><span data-ttu-id="16df8-179">Trabalhar com o Arquiteto para definir a abordagem de gerenciamento de mudanças e os planos de comunicação</span><span class="sxs-lookup"><span data-stu-id="16df8-179">Working with the Architect to define the Change Management approach and Communication Plans</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-180">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-180">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-181"><strong>Gerenciamento de mudanças/Especialista em adoção</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-181"><strong>Change Management/Adoption Specialist</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-182">Alimentar a fase de Descoberta em processos de treinamento e adoção</span><span class="sxs-lookup"><span data-stu-id="16df8-182">Provide input on Discovery phase into adoption and training processes</span></span></li>
<li><span data-ttu-id="16df8-183">Participar do workshop de estratégia de adoção</span><span class="sxs-lookup"><span data-stu-id="16df8-183">Participate in adoption strategy workshop</span></span></li>
<li><span data-ttu-id="16df8-184">Desenvolvimento e responsabilidade pela estratégia de adoção</span><span class="sxs-lookup"><span data-stu-id="16df8-184">Developing and responsible for adoption strategy</span></span></li>
<li><span data-ttu-id="16df8-185">Desenvolvimento e execução do plano de comunicação</span><span class="sxs-lookup"><span data-stu-id="16df8-185">Developing and executing communication plan</span></span></li>
<li><span data-ttu-id="16df8-186">Responsável por ministrar treinamentos aos usuários finais</span><span class="sxs-lookup"><span data-stu-id="16df8-186">Responsible for delivering trainings to end users</span></span></li>
<li><span data-ttu-id="16df8-187">Coletar feedback e conduzir pesquisas</span><span class="sxs-lookup"><span data-stu-id="16df8-187">Collect feedback and conduct surveys</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-188">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-188">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-189"><strong>Líder de rede</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-189"><strong>Network Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-190">Alimentar a fase de Descoberta em design de rede</span><span class="sxs-lookup"><span data-stu-id="16df8-190">Providing input on Discovery phase into network design</span></span></li>
<li><span data-ttu-id="16df8-191">Participar do planejamento durante o workshop de Concepção</span><span class="sxs-lookup"><span data-stu-id="16df8-191">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="16df8-192">Coordena o trabalho da equipe de rede durante a execução do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-192">Coordinates work of networking team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-193">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-193">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-194"><strong>Líder de segurança</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-194"><strong>Security Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-195">Alimentar a fase de Descoberta em processos e designs de segurança</span><span class="sxs-lookup"><span data-stu-id="16df8-195">Providing input on Discovery phase into security design and processes</span></span></li>
<li><span data-ttu-id="16df8-196">Participar do planejamento durante o workshop de Concepção</span><span class="sxs-lookup"><span data-stu-id="16df8-196">Participating in planning during Envisioning workshop</span></span></li>
<li><span data-ttu-id="16df8-197">Coordena o trabalho da equipe de segurança durante a execução do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-197">Coordinates work of security team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-198">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-198">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-199"><strong>Líder de telefonia</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-199"><strong>Telephony Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-200">Alimentar a fase de Descoberta em design de telefonia</span><span class="sxs-lookup"><span data-stu-id="16df8-200">Providing input on Discovery phase into telephony design</span></span></li>
<li><span data-ttu-id="16df8-201">Participar do planejamento durante o workshop de Concepção</span><span class="sxs-lookup"><span data-stu-id="16df8-201">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="16df8-202">Coordena o trabalho da equipe de telefonia durante a execução do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-202">Coordinates work of telephony team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-203">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-203">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-204"><strong>Líder de desktop</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-204"><strong>Desktop Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-205">Alimentar a fase de Descoberta em clientes e processos de atualização</span><span class="sxs-lookup"><span data-stu-id="16df8-205">Providing input on Discovery phase into clients and update process</span></span></li>
<li><span data-ttu-id="16df8-206">Participar do planejamento durante o workshop de Concepção</span><span class="sxs-lookup"><span data-stu-id="16df8-206">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="16df8-207">Coordena o trabalho da equipe de desktop durante a execução do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-207">Coordinates work of desktop team during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-208">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-208">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-209"><strong>Líder de suporte/central de ajuda</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-209"><strong>Support/Help Desk Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-210">Alimentar a fase de Descoberta em modelos de operação e suporte</span><span class="sxs-lookup"><span data-stu-id="16df8-210">Providing input on Discovery phase into operational and support model</span></span></li>
<li><span data-ttu-id="16df8-211">Participar do planejamento durante o workshop de Concepção</span><span class="sxs-lookup"><span data-stu-id="16df8-211">Participating in planning during envisioning workshop</span></span></li>
<li><span data-ttu-id="16df8-212">Participar no planejamento do modelo de suporte</span><span class="sxs-lookup"><span data-stu-id="16df8-212">Participating into support model planning</span></span></li>
<li><span data-ttu-id="16df8-213">Coordena o trabalho das equipes/recursos de suporte durante a execução do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-213">Coordinates work of support teams/resources during the project execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-214">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-214">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-215"><strong>Representantes das unidades de negócios</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-215"><strong>Business Unit Representatives</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-216">Contribuir com guias e materiais de adoção baseados no usuário final</span><span class="sxs-lookup"><span data-stu-id="16df8-216">Contribute in End User based adoption guides and materials</span></span></li>
<li><span data-ttu-id="16df8-217">Contribuir e analisar casos de uso comercial</span><span class="sxs-lookup"><span data-stu-id="16df8-217">Contribute to and review Business Use Cases</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-218">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-218">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-219"><strong>Líder de implantação</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-219"><strong>Deployment Lead</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-220">Garantir que os pré-requisitos de implantação sejam atendidos</span><span class="sxs-lookup"><span data-stu-id="16df8-220">Ensure that deployment prerequisites are met</span></span></li>
<li><span data-ttu-id="16df8-221">Envolver os recursos do cliente para as atividades da fase de preparação e implantação</span><span class="sxs-lookup"><span data-stu-id="16df8-221">Engage customer resources to engage on prepare and deploy stage activities</span></span></li>
<li><span data-ttu-id="16df8-222">Participar de reuniões para analisar o status de preparação e implantação</span><span class="sxs-lookup"><span data-stu-id="16df8-222">Participate in meetings to review prepare and deploy status</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-223">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-223">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-224"><strong>Administradores de TI</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-224"><strong>IT Admins</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-225">Profissionais de TI responsáveis pela assistência no planejamento e execução de testes</span><span class="sxs-lookup"><span data-stu-id="16df8-225">IT Pros responsible for assistance with test planning and execution</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-226">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-226">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-227"><strong>Proprietário do serviço</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-227"><strong>Service Owner</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-228">Responsável pela operação do serviço de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-228">Is responsible for the operation of the Audio Conferencing service all up</span></span></li>
<li><span data-ttu-id="16df8-229">Proprietário do serviço de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-229">Owner of Audio Conferencing service</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-230">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-230">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-231"><strong>Defensor da qualidade</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-231"><strong>Quality Champion</strong></span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-232">Direciona qualidade, confiabilidade e feedback dos usuários</span><span class="sxs-lookup"><span data-stu-id="16df8-232">Drives quality, reliability and user feedback</span></span></li>
<li><span data-ttu-id="16df8-233">Identifica as tendências de qualidade e direciona remediação com as respectivas equipes</span><span class="sxs-lookup"><span data-stu-id="16df8-233">Identifies the quality trends and drive remediation with the respective teams</span></span></li>
<li><span data-ttu-id="16df8-234">Reporta-se ao comitê de direção e de volta à liderança</span><span class="sxs-lookup"><span data-stu-id="16df8-234">Reports through the steering committee back to leadership</span></span></li>
<li><span data-ttu-id="16df8-235">Reporta-se sobre qualidade, confiabilidade e sentimento dos usuários através do Rate My Call e Net Promoter Score</span><span class="sxs-lookup"><span data-stu-id="16df8-235">Reports on quality, reliability, and user sentiment through Rate My Call and Net Promoter Score</span></span></li></ul></td>
<td align="left"><span data-ttu-id="16df8-236">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-236">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-237">_Tabela 2 Exemplo de modelo de matriz das partes envolvidas_</span><span class="sxs-lookup"><span data-stu-id="16df8-237">_Table 2 Stakeholder matrix template example_</span></span>


> [!NOTE]
> <span data-ttu-id="16df8-238">A tabela de exemplo acima e as tabelas subsequentes ao longo deste documento servem como modelo.</span><span class="sxs-lookup"><span data-stu-id="16df8-238">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="16df8-239">Você verá “TBA” (a ser adicionado) para informações que você precisa inserir como parte do seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="16df8-239">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>



<a name="define-objectives-and-key-results-key-success-indicators-and-risks"></a><span data-ttu-id="16df8-240">Defina os objetivos e os resultados principais, os principais indicadores de sucesso e os riscos</span><span class="sxs-lookup"><span data-stu-id="16df8-240">Define objectives and key results, key success indicators, and risks</span></span>
--------------------------------------------------------------------

<span data-ttu-id="16df8-241">Com as partes envolvidas do projeto reunidas, os casos de uso comercial, o escopo organizacional e os cronogramas do projeto podem ser traduzidos em objetivos e resultados principais (OKRs), e as medições de sucesso do projeto podem ser definidas em uma lista de principais indicadores de sucesso (KSIs).</span><span class="sxs-lookup"><span data-stu-id="16df8-241">With the project stakeholders assembled, business use cases, organizational scope and project timelines can be translated into objectives and key results (OKRs) and the measures of project success can be defined into a list of key success indicators (KSIs).</span></span>

<span data-ttu-id="16df8-242">A participação das partes envolvidas do projeto na definição dos OKRs e KSIs assegurará o senso de propriedade e eles serão alinhados aos requisitos comerciais das empresas.</span><span class="sxs-lookup"><span data-stu-id="16df8-242">Full participation from project stakeholders when defining the OKRs and KSIs will ensure sense of ownership and they are aligned to organizational business requirements.</span></span>

<span data-ttu-id="16df8-243">Os OKRs contêm a lista dos objetivos estabelecidos no início do projeto, com os principais resultados mensuráveis definidos em uma base trimestral.</span><span class="sxs-lookup"><span data-stu-id="16df8-243">OKRs will contain the list of objectives set in the beginning of the project, with measurable key results defined in a quarterly basis.</span></span> <span data-ttu-id="16df8-244">Os principais resultados são avaliados mensalmente para monitorar o status geral do projeto e, com base no progresso, podem ser feitos ajustes nos planos trimestrais conforme a necessidade.</span><span class="sxs-lookup"><span data-stu-id="16df8-244">The key results are reviewed monthly to track status of the overall project, and based on progress, adjustment to the quarterly plans can be made as needed.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><p><span data-ttu-id="16df8-245"><strong>Visão</strong>: Aumentar a produtividade maximizando os investimentos no Office 365</span><span class="sxs-lookup"><span data-stu-id="16df8-245"><strong>Vision</strong>: Increase productivity by maximizing Office 365 investments</span></span></p>
</th>
<th align="left"></th>
<th align="left"></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-246"><strong>Objetivos</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-246"><strong>Objectives</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-247"><strong>Resultados principais</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-247"><strong>Key Results</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-248"><strong>A fazer</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-248"><strong>To Do</strong></span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-249">Implantar Audioconferência no Teams até o final do ano fiscal de 2018</span><span class="sxs-lookup"><span data-stu-id="16df8-249">Deploy Audio Conferencing in Teams by end of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="16df8-250">1º trimestre do ano fiscal de 2018: Implantar Audioconferência no Teams globalmente</span><span class="sxs-lookup"><span data-stu-id="16df8-250">FY18Q1: Deploy Audio Conferencing in Teams globally</span></span></td>
<td align="left"><p><span data-ttu-id="16df8-251">Concepção</span><span class="sxs-lookup"><span data-stu-id="16df8-251">Envision</span></span></p>
<ul><li><span data-ttu-id="16df8-252">Criar plano de sucesso</span><span class="sxs-lookup"><span data-stu-id="16df8-252">Create success plan</span></span></li>
<li><span data-ttu-id="16df8-253">Criar plano detalhado de implementação técnica</span><span class="sxs-lookup"><span data-stu-id="16df8-253">Create detailed technical implementation plan</span></span></li></ul>
<p><span data-ttu-id="16df8-254">Integração</span><span class="sxs-lookup"><span data-stu-id="16df8-254">Onboard</span></span></p>
<ul><li><span data-ttu-id="16df8-255">Executar plano de sucesso</span><span class="sxs-lookup"><span data-stu-id="16df8-255">Execute success plan</span></span></li>
<li><span data-ttu-id="16df8-256">Executar plano de implementação técnica</span><span class="sxs-lookup"><span data-stu-id="16df8-256">Execute technical implementation plan</span></span></li></ul></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-257">Encerrar globalmente o serviço de conferência PSTN herdado até o meio do ano fiscal de 2018</span><span class="sxs-lookup"><span data-stu-id="16df8-257">Decommission legacy PSTN Conferencing service globally by mid of fiscal year 2018</span></span></td>
<td align="left"><span data-ttu-id="16df8-258">2º trimestre do ano fiscal de 2018: Encerrar globalmente o serviço de conferência PSTN herdado</span><span class="sxs-lookup"><span data-stu-id="16df8-258">FY18Q2: Decommission legacy PSTN Conferencing service globally</span></span></td>
<td align="left"><p><span data-ttu-id="16df8-259">Gerar valor</span><span class="sxs-lookup"><span data-stu-id="16df8-259">Drive Value</span></span></p>
<ul><li><span data-ttu-id="16df8-260">Aumentar o envolvimento do usuário e direcionar adoção</span><span class="sxs-lookup"><span data-stu-id="16df8-260">Boost user engagement and drive adoption</span></span></li>
<li><span data-ttu-id="16df8-261">Gerenciar e preparar a mudança</span><span class="sxs-lookup"><span data-stu-id="16df8-261">Manage and prepare change</span></span></li>
<li><span data-ttu-id="16df8-262">Mensurar, compartilhar o sucesso e iterar</span><span class="sxs-lookup"><span data-stu-id="16df8-262">Measure, share success, and iterate</span></span></li></ul></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-263">_Tabela 3 Exemplo de OKRs_</span><span class="sxs-lookup"><span data-stu-id="16df8-263">_Table 3 Example of OKRs_</span></span>


<span data-ttu-id="16df8-264">Os KSIs mensuram a qualidade e o sucesso dos principais resultados e complementam a natureza binária dos OKRs (alcançados ou não alcançados) ao detalhar os bons e/ou maus resultados.</span><span class="sxs-lookup"><span data-stu-id="16df8-264">KSIs measure quality and success of the key results and complement the binary nature of OKRs (achieved or not achieved), by detailing the good and/or bad results.</span></span> <span data-ttu-id="16df8-265">Ao definir os KSIs, recomendamos aproveitar os critérios “específicos, mensuráveis, atribuíveis, realistas, relacionados ao tempo” ou SMART.</span><span class="sxs-lookup"><span data-stu-id="16df8-265">When defining KSIs, we recommend leveraging the “specific, measurable, assignable, realistic, time-related” or SMART criteria.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-266">Tipo</span><span class="sxs-lookup"><span data-stu-id="16df8-266">Type</span></span></th>
<th align="left"><p><span data-ttu-id="16df8-267">Perguntas de KSI &amp;</span><span class="sxs-lookup"><span data-stu-id="16df8-267">KSI questions &amp;</span></span></p>
<p><span data-ttu-id="16df8-268">critérios</span><span class="sxs-lookup"><span data-stu-id="16df8-268">criteria</span></span></p></th>
<th align="left"><span data-ttu-id="16df8-269">Como foi mensurado</span><span class="sxs-lookup"><span data-stu-id="16df8-269">How measured</span></span></th>
<th align="left"><span data-ttu-id="16df8-270">Critérios de sucesso</span><span class="sxs-lookup"><span data-stu-id="16df8-270">Success criteria</span></span></th>
<th align="left"><span data-ttu-id="16df8-271">Mensurado</span><span class="sxs-lookup"><span data-stu-id="16df8-271">Measured</span></span></th>
<th align="left"><span data-ttu-id="16df8-272">Responsável</span><span class="sxs-lookup"><span data-stu-id="16df8-272">Responsible</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-273"><strong>Uso/adoção</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-273"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-274">A qualidade da chamada é igual ou melhor que a solução anterior</span><span class="sxs-lookup"><span data-stu-id="16df8-274">Call quality is equal to or better than the previous solution</span></span></td>
<td align="left"><span data-ttu-id="16df8-275">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="16df8-275">Survey page</span></span></td>
<td align="left"><span data-ttu-id="16df8-276">80% dos usuários concordam ou concordam fortemente</span><span class="sxs-lookup"><span data-stu-id="16df8-276">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="16df8-277">Após a habilitação e trimestralmente</span><span class="sxs-lookup"><span data-stu-id="16df8-277">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="16df8-278">Esquipe de Tecnologia da Informação</span><span class="sxs-lookup"><span data-stu-id="16df8-278">Information Technology team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-279"><strong>Uso/adoção</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-279"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-280">O Teams facilitou o processo de comunicação</span><span class="sxs-lookup"><span data-stu-id="16df8-280">Teams made the communication process easier</span></span></td>
<td align="left"><span data-ttu-id="16df8-281">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="16df8-281">Survey page</span></span></td>
<td align="left"><span data-ttu-id="16df8-282">80% dos usuários concordam ou concordam fortemente</span><span class="sxs-lookup"><span data-stu-id="16df8-282">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="16df8-283">Após a habilitação e trimestralmente</span><span class="sxs-lookup"><span data-stu-id="16df8-283">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="16df8-284">Equipe de gerenciamento de mudanças</span><span class="sxs-lookup"><span data-stu-id="16df8-284">Change Management team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-285"><strong>Uso/adoção</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-285"><strong>Usage/adoption</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-286">Os usuários usam a solução ativamente</span><span class="sxs-lookup"><span data-stu-id="16df8-286">Users actively use the solution</span></span></td>
<td align="left"><span data-ttu-id="16df8-287">Relatórios do Office 365, Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="16df8-287">Office 365 reports, Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="16df8-288">80% dos usuários são usuários ativos diariamente</span><span class="sxs-lookup"><span data-stu-id="16df8-288">80% of users are active daily users</span></span></td>
<td align="left"><span data-ttu-id="16df8-289">Diariamente</span><span class="sxs-lookup"><span data-stu-id="16df8-289">Daily</span></span></td>
<td align="left"><span data-ttu-id="16df8-290">Equipe de gerenciamento de mudanças</span><span class="sxs-lookup"><span data-stu-id="16df8-290">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-291"><strong>Uso/qualidade</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-291"><strong>Usage/quality</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-292">A porcentagem de chamadas/conferências de má qualidade deve ser mínima</span><span class="sxs-lookup"><span data-stu-id="16df8-292">Percentage of poor calls/conferences should be minimal</span></span></td>
<td align="left"><span data-ttu-id="16df8-293">Painel de Qualidade da Chamada</span><span class="sxs-lookup"><span data-stu-id="16df8-293">Call Quality Dashboard</span></span></td>
<td align="left"><span data-ttu-id="16df8-294">&lt; 5% de chamadas de má qualidade por mês</span><span class="sxs-lookup"><span data-stu-id="16df8-294">&lt; 5% of poor calls per month</span></span></td>
<td align="left"><span data-ttu-id="16df8-295">Diariamente</span><span class="sxs-lookup"><span data-stu-id="16df8-295">Daily</span></span></td>
<td align="left"><span data-ttu-id="16df8-296">Esquipe de Tecnologia da Informação</span><span class="sxs-lookup"><span data-stu-id="16df8-296">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-297"><strong>Uso/suporte</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-297"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-298">Eu sei como obter suporte técnico</span><span class="sxs-lookup"><span data-stu-id="16df8-298">I know how to get technical support</span></span></td>
<td align="left"><span data-ttu-id="16df8-299">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="16df8-299">Survey page</span></span></td>
<td align="left"><span data-ttu-id="16df8-300">90% dos usuários concordam ou concordam fortemente</span><span class="sxs-lookup"><span data-stu-id="16df8-300">90% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="16df8-301">Após a habilitação e trimestralmente</span><span class="sxs-lookup"><span data-stu-id="16df8-301">After enablement and quarterly</span></span></td>
<td align="left"><span data-ttu-id="16df8-302">Equipe de gerenciamento de mudanças</span><span class="sxs-lookup"><span data-stu-id="16df8-302">Change Management team</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-303"><strong>Uso/suporte</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-303"><strong>Usage/support</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-304">Estou satisfeito com a qualidade do suporte técnico</span><span class="sxs-lookup"><span data-stu-id="16df8-304">I am satisfied with the quality of technical support</span></span></td>
<td align="left"><span data-ttu-id="16df8-305">Pesquisa</span><span class="sxs-lookup"><span data-stu-id="16df8-305">Survey page</span></span></td>
<td align="left"><span data-ttu-id="16df8-306">80% dos usuários concordam ou concordam fortemente</span><span class="sxs-lookup"><span data-stu-id="16df8-306">80% of users agree or strongly agree</span></span></td>
<td align="left"><span data-ttu-id="16df8-307">Após cada incidente</span><span class="sxs-lookup"><span data-stu-id="16df8-307">After each incident</span></span></td>
<td align="left"><span data-ttu-id="16df8-308">Esquipe de Tecnologia da Informação</span><span class="sxs-lookup"><span data-stu-id="16df8-308">Information Technology team</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-309"><strong>Financeiro</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-309"><strong>Financial</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-310">Redução dos minutos de conferência herdados</span><span class="sxs-lookup"><span data-stu-id="16df8-310">Reduction of legacy conferencing minutes</span></span></td>
<td align="left"><span data-ttu-id="16df8-311">Sistema financeiro</span><span class="sxs-lookup"><span data-stu-id="16df8-311">Financial system</span></span></td>
<td align="left"><span data-ttu-id="16df8-312">Atingir o ROI estabelecido</span><span class="sxs-lookup"><span data-stu-id="16df8-312">Meet defined ROI</span></span></td>
<td align="left"><span data-ttu-id="16df8-313">Baseado no ROI</span><span class="sxs-lookup"><span data-stu-id="16df8-313">Based on ROI</span></span></td>
<td align="left"><span data-ttu-id="16df8-314">Equipe de gerenciamento de mudanças</span><span class="sxs-lookup"><span data-stu-id="16df8-314">Change Management team</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-315">_Tabela 4 Exemplo de KSIs_</span><span class="sxs-lookup"><span data-stu-id="16df8-315">_Table 4 Example of KSIs_</span></span>


<span data-ttu-id="16df8-316">Como parte desse exercício, você precisa identificar os riscos de negócios e definir um plano de mitigação para cada um dos riscos identificados.</span><span class="sxs-lookup"><span data-stu-id="16df8-316">You need to identify business risks as part of this exercise and define a mitigation plan for each identified risk.</span></span> <span data-ttu-id="16df8-317">Essas informações podem ser coletadas em um plano de riscos.</span><span class="sxs-lookup"><span data-stu-id="16df8-317">This information can be captured into a risk plan.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-318">Risco</span><span class="sxs-lookup"><span data-stu-id="16df8-318">Risk</span></span></th>
<th align="left"><span data-ttu-id="16df8-319">Probabilidade</span><span class="sxs-lookup"><span data-stu-id="16df8-319">Likelihood</span></span></th>
<th align="left"><span data-ttu-id="16df8-320">Impacto</span><span class="sxs-lookup"><span data-stu-id="16df8-320">Impact</span></span></th>
<th align="left"><span data-ttu-id="16df8-321">Geral</span><span class="sxs-lookup"><span data-stu-id="16df8-321">Overall</span></span></th>
<th align="left"><span data-ttu-id="16df8-322">Plano de mitigação</span><span class="sxs-lookup"><span data-stu-id="16df8-322">Mitigation plan</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-323">A incorporação acrescentará até 1.000 pessoas</span><span class="sxs-lookup"><span data-stu-id="16df8-323">Upcoming merger will add up to 1,000 people</span></span></td>
<td align="left"><span data-ttu-id="16df8-324">Alto</span><span class="sxs-lookup"><span data-stu-id="16df8-324">High</span></span></td>
<td align="left"><span data-ttu-id="16df8-325">Alto</span><span class="sxs-lookup"><span data-stu-id="16df8-325">High</span></span></td>
<td align="left"><span data-ttu-id="16df8-326">Alto</span><span class="sxs-lookup"><span data-stu-id="16df8-326">High</span></span></td>
<td align="left"><p><span data-ttu-id="16df8-327">Para empresas incorporadas, separar o OKR com o processo próprio (Concepção, Integração, Geração de valor)</span><span class="sxs-lookup"><span data-stu-id="16df8-327">For merged companies, separate OKR with own process (Envision, Onboard, Drive Value)</span></span></p>
<p><span data-ttu-id="16df8-328">Não inclui-los nos OKRs existentes</span><span class="sxs-lookup"><span data-stu-id="16df8-328">Do not include them in existing OKRs</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-329">A portabilidade dos números de telefone atrasará a conclusão do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-329">Telephone number porting will delay project completion</span></span></td>
<td align="left"><span data-ttu-id="16df8-330">Alto</span><span class="sxs-lookup"><span data-stu-id="16df8-330">High</span></span></td>
<td align="left"><span data-ttu-id="16df8-331">Alto</span><span class="sxs-lookup"><span data-stu-id="16df8-331">High</span></span></td>
<td align="left"><span data-ttu-id="16df8-332">Alto</span><span class="sxs-lookup"><span data-stu-id="16df8-332">High</span></span></td>
<td align="left"><p><span data-ttu-id="16df8-333">Preparar todas as informações necessárias para dar suporte à portabilidade dos números de telefone antes (ou seja, registros do atendimento ao cliente, detalhes de cobrança, Carta de Autorização)</span><span class="sxs-lookup"><span data-stu-id="16df8-333">Prepare all the required information to support telephone number porting ahead of time (i.e.: customer service record, billing details, Letter of Authorization)</span></span></p>
<p><span data-ttu-id="16df8-334">Ajustar o cronograma do projeto para absorver o tempo de entrega dos resultados da execução da portabilidade dos números de telefone</span><span class="sxs-lookup"><span data-stu-id="16df8-334">Adjust project timeline to accommodate turnaround time of telephone number porting execution</span></span></p>
<p><span data-ttu-id="16df8-335">Comunicar o uso de novos números de conferência de discagem para os participantes externos</span><span class="sxs-lookup"><span data-stu-id="16df8-335">Communicate the use of new dial-in conferencing numbers to external participants</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-336">Reestruturação planejada da rede</span><span class="sxs-lookup"><span data-stu-id="16df8-336">Planned network redesign</span></span></td>
<td align="left"><span data-ttu-id="16df8-337">Alto</span><span class="sxs-lookup"><span data-stu-id="16df8-337">High</span></span></td>
<td align="left"><span data-ttu-id="16df8-338">Médio</span><span class="sxs-lookup"><span data-stu-id="16df8-338">Medium</span></span></td>
<td align="left"><span data-ttu-id="16df8-339">Médio</span><span class="sxs-lookup"><span data-stu-id="16df8-339">Medium</span></span></td>
<td align="left"><span data-ttu-id="16df8-340">Antes de implementar o Teams como uma plataforma de colaboração e comunicação moderna, execute a avaliação da prontidão da rede para sites no âmbito do projeto</span><span class="sxs-lookup"><span data-stu-id="16df8-340">Before implementing Teams as modern communications and collaboration platform, run network readiness assessment for sites in scope of the project</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-341">_Tabela 5 Exemplo de plano de risco_</span><span class="sxs-lookup"><span data-stu-id="16df8-341">_Table 5 Risk plan example_</span></span>


<a name="assess-environment-and-evaluate-adoption-readiness"></a><span data-ttu-id="16df8-342">Avalie o ambiente e avalie a prontidão para adoção</span><span class="sxs-lookup"><span data-stu-id="16df8-342">Assess environment and evaluate adoption readiness</span></span>
--------------------------------------------------

<span data-ttu-id="16df8-343">Para alcançar os OKRs pretendidos, você pode precisar definir a arquitetura de alto nível da solução.</span><span class="sxs-lookup"><span data-stu-id="16df8-343">To achieve the intended OKRs, you may have to define the high-level architecture of the solution.</span></span> <span data-ttu-id="16df8-344">É necessária uma pesquisa do ambiente para avaliar todos os aspectos relacionados à infraestrutura de TI e telefonia, redes e operações.</span><span class="sxs-lookup"><span data-stu-id="16df8-344">It takes environmental discovery to evaluate all aspects relating to IT and telephony infrastructure, networking, and operations.</span></span>

<span data-ttu-id="16df8-345">Todos os assuntos relacionados a computação de usuário final, como a avaliação de prontidão dos computadores pessoais e dispositivos móveis para suportar os casos de uso comercial de Audioconferência, desde os requisitos de hardware até os requisitos de software, serão incluídos como parte da pesquisa do ambiente.</span><span class="sxs-lookup"><span data-stu-id="16df8-345">All matters related to end-user computing, such as readiness assessment of the personal computers and mobile devices to support Audio Conferencing business use cases, from hardware requirements to software requirements, will be included as part of the environmental discovery.</span></span>

<span data-ttu-id="16df8-346">A pesquisa do ambiente também esclarece se há necessidade de [transferir os números de telefone para a Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span><span class="sxs-lookup"><span data-stu-id="16df8-346">Environmental discovery can also uncover if there are requirements to [transfer phone numbers to Microsoft](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span> <span data-ttu-id="16df8-347">Isso ajudará a sua organização a ajustar adequadamente o plano do projeto e preparar as informações necessárias para a portabilidade dos números.</span><span class="sxs-lookup"><span data-stu-id="16df8-347">This will help your organization to adjust the project plan accordingly and prepare the necessary information required for number porting.</span></span> <span data-ttu-id="16df8-348">Você pode fazer a pesquisa do ambiente utilizado o seguinte [questionário](https://go.microsoft.com/fwlink/?linkid=858995).</span><span class="sxs-lookup"><span data-stu-id="16df8-348">You can perform environmental discovery by leveraging the following [questionnaire](https://go.microsoft.com/fwlink/?linkid=858995).</span></span>

<span data-ttu-id="16df8-349">A pesquisa do ambiente deve incluir avaliação da prontidão da rede para garantir que a rede esteja pronta para suportar a implementação do serviço de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-349">Environmental discovery must include network readiness assessment to ensure the network is ready to support the implementation of the Audio Conferencing service.</span></span>

<span data-ttu-id="16df8-350">A prontidão da rede para suportar o serviço de Audioconferência pode ser determinada utilizando as informações coletadas através da pesquisa do ambiente (como detalhes da conectividade com a internet e topologia da WAN, links de sites, largura de banda disponível e dados de análise pessoal, que podem ser traduzidos para o uso esperado de cada carga de trabalho) na [ferramenta My Advisor Network Planner](https://go.microsoft.com/fwlink/?linkid=858999).</span><span class="sxs-lookup"><span data-stu-id="16df8-350">Network readiness to support the Audio Conferencing service can be determined by leveraging the information captured through the environmental discovery (such as details of internet connectivity and WAN topology, site links, available bandwidth, and persona analysis data (that can be translated into an expected usage of each workload) into the [My Advisor Network Planner tool](https://go.microsoft.com/fwlink/?linkid=858999).</span></span> <span data-ttu-id="16df8-351">Para confirmar a prontidão da rede, pode ser feita uma simulação de tráfego de mídia em tempo real usando as soluções fornecidas pela [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) ou pelos [parceiros das ferramentas de Avaliação da prontidão da rede](https://go.microsoft.com/fwlink/?linkid=859003).</span><span class="sxs-lookup"><span data-stu-id="16df8-351">To further confirm network readiness, real-time media traffic simulation can be performed using the solutions provided by [Microsoft](https://go.microsoft.com/fwlink/?linkid=859002) or by [Network Readiness Assessment tools partners](https://go.microsoft.com/fwlink/?linkid=859003).</span></span>

<span data-ttu-id="16df8-352">Os resultados da avaliação da prontidão da rede darão uma ideia mais clara da otimização ou da remediação necessária da rede para o sucesso da implementação da Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-352">The results of the Network Readiness Assessment will paint a clearer picture of the required network optimization or remediation required for the success of Audio Conferencing implementation.</span></span>

<span data-ttu-id="16df8-353">A prontidão para a adoção pode ser avaliada através da execução de análise pessoal para criar uma lista de pessoas na organização que podem ser direcionadas para a implementação do serviço de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-353">Adoption readiness can be evaluated by executing persona analysis to come up with a list of personas in the organization who can be targeted for the implementation of Audio Conferencing service.</span></span> <span data-ttu-id="16df8-354">A análise pessoal inclui a identificação de periféricos adicionais ou dispositivos necessários para atingir os resultados comerciais pretendidos.</span><span class="sxs-lookup"><span data-stu-id="16df8-354">The persona analysis includes the identification of additional peripherals or devices required to realize the intended business outcomes.</span></span>

<span data-ttu-id="16df8-355">Fara fazer a análise pessoal, você pode conduzir um workshop envolvendo as partes envolvidas no projeto, utilizando o [deck de workshop Alinhamento Pessoal](https://go.microsoft.com/fwlink/?linkid=859005) e a [Matriz de características pessoais](https://go.microsoft.com/fwlink/?linkid=859006).</span><span class="sxs-lookup"><span data-stu-id="16df8-355">To perform persona analysis, you can conduct a workshop by involving relevant project stakeholders, leveraging the [Persona Alignment](https://go.microsoft.com/fwlink/?linkid=859005) workshop deck and [Persona Feature Matrix](https://go.microsoft.com/fwlink/?linkid=859006).</span></span> <span data-ttu-id="16df8-356">O resultado do workshop de análise pessoal pode ser resumido em um relatório usando o modelo de [Relatório de análise pessoal](https://go.microsoft.com/fwlink/?linkid=859007).</span><span class="sxs-lookup"><span data-stu-id="16df8-356">The result of persona analysis workshop can be summarized into a report using the [Persona Analysis Report](https://go.microsoft.com/fwlink/?linkid=859007) template.</span></span>


> [!NOTE]
> <span data-ttu-id="16df8-357">Ao passo que os exemplos de Questionário de Descoberta e Análise Pessoal foram inicialmente escritos para o Skype for Business Online, a maioria do conteúdo é relevante para o Teams.</span><span class="sxs-lookup"><span data-stu-id="16df8-357">While the Discovery Questionnaire and Persona Analysis examples were initially written for Skype for Business Online, a majority of the content is relevant to Teams.</span></span> <span data-ttu-id="16df8-358">Fique à vontade para modificar e remover itens que não são relevantes para os objetivos do projeto.</span><span class="sxs-lookup"><span data-stu-id="16df8-358">Feel free to modify and remove items that are not relevant to the project goals.</span></span>


<span data-ttu-id="16df8-359">Você pode identificar riscos técnicos como parte da avaliação ambiental e da avaliação de prontidão para adoção, e desenvolver um plano de mitigação para cada risco identificado.</span><span class="sxs-lookup"><span data-stu-id="16df8-359">You can identify technical risks as part of an environmental assessment and adoption readiness evaluation and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="16df8-360">Essas informações devem ser incorporadas como parte do plano de risco.</span><span class="sxs-lookup"><span data-stu-id="16df8-360">This information should be incorporated as part of the risk plan.</span></span>

<a name="map-operational-roles"></a><span data-ttu-id="16df8-361">Mapear funções operacionais</span><span class="sxs-lookup"><span data-stu-id="16df8-361">Map operational roles</span></span>
---------------------

<span data-ttu-id="16df8-362">O planejamento das operações e a identificação das equipes que operarão o serviço de Audioconferência é um passo importante, pois as operações devem ser iniciadas quando os primeiros usuários piloto estiverem habilitados.</span><span class="sxs-lookup"><span data-stu-id="16df8-362">Planning for operations and identifying the teams that will operate the Audio Conferencing service is an important step, as operations must start when the first pilot users are enabled.</span></span> <span data-ttu-id="16df8-363">Cada uma das equipes identificadas precisa avaliar e chegar a um acordo quanto às tarefas e responsabilidades identificadas, e iniciar a preparação para operar o serviço de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-363">Each identified team must review and agree on the tasks and responsibilities identified and start the preparation to operate the Audio Conferencing service.</span></span> <span data-ttu-id="16df8-364">A preparação pode incluir treinamentos e prontidão, pessoal adicional ou a certeza de que os provedores externos estão configurados para entregar o serviço.</span><span class="sxs-lookup"><span data-stu-id="16df8-364">The preparation might include training and readiness, additional staffing, or ensuring external providers are set up to deliver the service.</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-365">Função operacional</span><span class="sxs-lookup"><span data-stu-id="16df8-365">Operational Role</span></span></th>
<th align="left"><span data-ttu-id="16df8-366">Descrição</span><span class="sxs-lookup"><span data-stu-id="16df8-366">Description</span></span></th>
<th align="left"><span data-ttu-id="16df8-367">Equipe</span><span class="sxs-lookup"><span data-stu-id="16df8-367">Team Call</span></span></th>
<th align="left"><span data-ttu-id="16df8-368">Detalhes de contato</span><span class="sxs-lookup"><span data-stu-id="16df8-368">Contact Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-369">Proprietário do serviço</span><span class="sxs-lookup"><span data-stu-id="16df8-369">Service Owner</span></span></td>
<td align="left"><span data-ttu-id="16df8-370">Proprietário do serviço, interface com as divisões da empresa, estratégia</span><span class="sxs-lookup"><span data-stu-id="16df8-370">Service owner, interface to business divisions, strategy</span></span></td>
<td align="left"><span data-ttu-id="16df8-371">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-371">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-372">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-372">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-373">Operações de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-373">Audio Conferencing Operations</span></span></td>
<td align="left"><span data-ttu-id="16df8-374">Operações diárias, migração/adição/alteração de contas de usuários e dispositivos, monitoramento</span><span class="sxs-lookup"><span data-stu-id="16df8-374">Daily operations, user and device account move/add/change, monitoring</span></span></td>
<td align="left"><span data-ttu-id="16df8-375">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-375">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-376">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-376">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-377">Administração de locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-377">Office 365 Tenant Admin</span></span></td>
<td align="left"><span data-ttu-id="16df8-378">Alterar configuração de todos os locatários, habilitar novos recursos</span><span class="sxs-lookup"><span data-stu-id="16df8-378">Change tenant-wide settings, enable new features</span></span></td>
<td align="left"><span data-ttu-id="16df8-379">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-379">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-380">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-380">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-381">Central de atendimento</span><span class="sxs-lookup"><span data-stu-id="16df8-381">Help Desk.</span></span></td>
<td align="left"><span data-ttu-id="16df8-382">Interface para os usuários finais obterem suporte</span><span class="sxs-lookup"><span data-stu-id="16df8-382">Interface for end-users to get support</span></span></td>
<td align="left"><span data-ttu-id="16df8-383">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-383">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-384">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-384">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-385">Operações de rede</span><span class="sxs-lookup"><span data-stu-id="16df8-385">Network Operations</span></span></td>
<td align="left"><span data-ttu-id="16df8-386">Executa LAN, WAN, Wi-Fi e acesso à internet</span><span class="sxs-lookup"><span data-stu-id="16df8-386">Runs LAN, WAN, Wi-Fi, and Internet Access</span></span></td>
<td align="left"><span data-ttu-id="16df8-387">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-387">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-388">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-388">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-389">Cliente &amp; Equipe de endpoints</span><span class="sxs-lookup"><span data-stu-id="16df8-389">Client &amp; Endpoints Team</span></span></td>
<td align="left"><span data-ttu-id="16df8-390">Gerenciar implantações de desktop</span><span class="sxs-lookup"><span data-stu-id="16df8-390">Manage desktop deployments</span></span></td>
<td align="left"><span data-ttu-id="16df8-391">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-391">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-392">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-392">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-393">Operações de identidade</span><span class="sxs-lookup"><span data-stu-id="16df8-393">Identity Operations</span></span></td>
<td align="left"><span data-ttu-id="16df8-394">Gerenciar infraestrutura de identidade (AD, ADFS, Azure AD)</span><span class="sxs-lookup"><span data-stu-id="16df8-394">Manage identity infrastructure (AD, ADFS, Azure AD)</span></span></td>
<td align="left"><span data-ttu-id="16df8-395">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-395">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-396">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-396">TBA</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-397">Gerenciamento de mudanças/adoção</span><span class="sxs-lookup"><span data-stu-id="16df8-397">Adoption/change management</span></span></td>
<td align="left"><span data-ttu-id="16df8-398">Gerenciar conscientização, treinamentos e adoção da solução</span><span class="sxs-lookup"><span data-stu-id="16df8-398">Manage awareness, training and adoption for the solution</span></span></td>
<td align="left"><span data-ttu-id="16df8-399">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-399">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-400">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-400">TBA</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-401">Operações do Exchange</span><span class="sxs-lookup"><span data-stu-id="16df8-401">Exchange Operations</span></span></td>
<td align="left"><span data-ttu-id="16df8-402">Gerenciar o ambiente do Exchange</span><span class="sxs-lookup"><span data-stu-id="16df8-402">Manages the Exchange environment</span></span></td>
<td align="left"><span data-ttu-id="16df8-403">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-403">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-404">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-404">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-405">_Tabela 6 Exemplo de mapeamento de funções operacionais_</span><span class="sxs-lookup"><span data-stu-id="16df8-405">_Table 6 Example of operational roles mapping_</span></span>


<span data-ttu-id="16df8-406">Para facilitar um mapeamento mais detalhado das funções operacionais, incluindo as tarefas associadas a cada uma das funções operacionais, você pode usar o [Pasta de trabalho de mapeamento de funções operacionais](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) para coletar os detalhes que esclarecerão as funções e responsabilidades para suportar o serviço de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-406">To facilitate a more detailed operational roles mapping, including the tasks associated with each operational role, you can use the [Operational Role Mapping Workbook](https://www.skypeoperationsframework.com/Downloads?SelectedIDs=4_4_0_16) to capture the details that will provide the clarity around roles and responsibilities to support Audio Conferencing service.</span></span>

<a name="document-success-plan"></a><span data-ttu-id="16df8-407">Documentar plano de sucesso</span><span class="sxs-lookup"><span data-stu-id="16df8-407">Document success plan</span></span>
---------------------

<span data-ttu-id="16df8-408">O plano de sucesso é a documentação criada na fase de Concepção, que consiste em caso de negócios, prontidão de serviço, plano de adoção e plano operacional.</span><span class="sxs-lookup"><span data-stu-id="16df8-408">A success plan is the documentation created in the Envision phase that consists of business case, service readiness, adoption plan, and operational plan.</span></span>

<span data-ttu-id="16df8-409">O plano de sucesso fornecerá à equipe do projeto, que pode incluir FastTrack ou parceiro de implantação, informações suficientes para atingir os objetivos do serviço de Audioconferência da organização.</span><span class="sxs-lookup"><span data-stu-id="16df8-409">The success plan will provide the project team, which can include FastTrack or deployment partner, with sufficient information to realize the organization’s goals with Audio Conferencing service.</span></span>

<span data-ttu-id="16df8-410">No geral, um plano de sucesso deve conter as seguintes seções principais:</span><span class="sxs-lookup"><span data-stu-id="16df8-410">In general, a success plan will contain the following main sections:</span></span>

-   <span data-ttu-id="16df8-411">Caso de negócios</span><span class="sxs-lookup"><span data-stu-id="16df8-411">Business case</span></span>

-   <span data-ttu-id="16df8-412">Prontidão de serviço</span><span class="sxs-lookup"><span data-stu-id="16df8-412">Service readiness</span></span>

-   <span data-ttu-id="16df8-413">Plano de adoção</span><span class="sxs-lookup"><span data-stu-id="16df8-413">Adoption plan</span></span>

-   <span data-ttu-id="16df8-414">Plano operacional</span><span class="sxs-lookup"><span data-stu-id="16df8-414">Operational plan</span></span>

### <a name="business-case"></a><span data-ttu-id="16df8-415">Caso de negócios</span><span class="sxs-lookup"><span data-stu-id="16df8-415">Business case</span></span>

<span data-ttu-id="16df8-416">Casos de uso comercial, partes envolvidas, OKRs e KSIs, riscos e cronogramas do projeto geralmente compõem a maior parte das informações necessárias para um caso de negócios.</span><span class="sxs-lookup"><span data-stu-id="16df8-416">Business use cases, stakeholders, OKRs and KSIs, risks, and project timelines typically make up the bulk of information required for a business case.</span></span> <span data-ttu-id="16df8-417">Você precisa documentá-los como parte do plano de sucesso.</span><span class="sxs-lookup"><span data-stu-id="16df8-417">You need to document them as part of the success plan.</span></span>

### <a name="service-readiness"></a><span data-ttu-id="16df8-418">Prontidão de serviço</span><span class="sxs-lookup"><span data-stu-id="16df8-418">Service readiness</span></span>

<span data-ttu-id="16df8-419">A avaliação do ambiente fornece as informações iniciais necessárias para determinar a prontidão técnica para a organização implementar a Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-419">Environmental assessment provides the initial information required to determine technical readiness for the organization to implement Audio Conferencing.</span></span>

<span data-ttu-id="16df8-420">Aqui incluído está o plano para abordar as áreas que precisam de remediação descobertas através da avaliação do ambiente.</span><span class="sxs-lookup"><span data-stu-id="16df8-420">Included here is the plan to address areas needing remediation discovered through environmental assessment.</span></span> <span data-ttu-id="16df8-421">Você precisa incluir a avaliação de prontidão de serviço e o plano de remediação como parte do plano de sucesso.</span><span class="sxs-lookup"><span data-stu-id="16df8-421">You need to include the service readiness assessment and remediation plan as part of the success plan.</span></span>

### <a name="adoption-plan"></a><span data-ttu-id="16df8-422">Plano de adoção</span><span class="sxs-lookup"><span data-stu-id="16df8-422">Adoption plan</span></span>

<span data-ttu-id="16df8-423">Após a avaliação de prontidão para adoção, deve ser feito um planejamento detalhado adicional para que a equipe do projeto estabeleça um conjunto abrangente de planos de comunicação, plano de treinamento e atividades de adoção pré-lançamento, no lançamento e pós-lançamento.</span><span class="sxs-lookup"><span data-stu-id="16df8-423">Following an adoption readiness assessment, further detailed planning must be completed for the project team to come up with a comprehensive set of communication plans, training plan, and pre-launch, at-launch, and post-launch adoption activities.</span></span>

<span data-ttu-id="16df8-424">Os recursos para dar suporte às atividades de adoção, como folhetos, e-mails de boas-vindas e materiais de treinamento, são identificados nesta etapa, juntamente com as personalizações necessárias para atender aos requisitos organizacionais.</span><span class="sxs-lookup"><span data-stu-id="16df8-424">Resources to support adoption activities such as flyers, welcome emails, and training materials are identified at this step, along with any customizations needed to meet organizational requirements.</span></span>

<span data-ttu-id="16df8-425">Os modelos para as atividades de adoção estão disponíveis [aqui](https://www.microsoft.com/download/details.aspx?id=54244).</span><span class="sxs-lookup"><span data-stu-id="16df8-425">The templates for adoption activities are available [here](https://www.microsoft.com/download/details.aspx?id=54244).</span></span>

### <a name="operational-plan"></a><span data-ttu-id="16df8-426">Plano operacional</span><span class="sxs-lookup"><span data-stu-id="16df8-426">Operational plan</span></span>

<span data-ttu-id="16df8-427">O exercício de mapeamento de funções operacionais estabelecerá as funções, as responsabilidades,e as equipes designadas a cada função operacional para dar suporte à implementação da Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-427">Operational roles mapping exercise will establish the roles and responsibilities, and the teams assigned to each operational role to support the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="16df8-428">Você precisa inserir isso e incluir o plano operacional como parte do plano de sucesso para garantir a prontidão operacional da solução.</span><span class="sxs-lookup"><span data-stu-id="16df8-428">You need to complete this and include the operational plan as part of the success plan to ensure operational readiness of the solution.</span></span>

<span data-ttu-id="16df8-429">Planejamento da Audioconferência no Teams  <a name="Planning_AudioConferencing"> </a></span><span class="sxs-lookup"><span data-stu-id="16df8-429">Planning for Audio Conferencing in Teams  <a name="Planning_AudioConferencing"> </a></span></span>
========================================

<span data-ttu-id="16df8-430">Para planejar a implementação da Audioconferência no Teams, uma série de decisões deve ser tomada antecipadamente para melhor preparar a sua organização para implementar uma solução que atenda aos requisitos da empresa.</span><span class="sxs-lookup"><span data-stu-id="16df8-430">To plan for the implementation of Audio Conferencing in Teams, a series of decisions must be made ahead of time to better prepare your organization to implement a solution that meets business requirements.</span></span> <span data-ttu-id="16df8-431">Essas decisões serão documentadas no plano de implementação técnica.</span><span class="sxs-lookup"><span data-stu-id="16df8-431">These decisions will be documented into a technical implementation plan.</span></span>

|  |  |
|---------|---------|
|  <iframe width="350" height="200" src="https://www.youtube.com/embed/AWbuvcWcYIc" frameborder="0" allowfullscreen></iframe>    | |


## <a name="availability-of-audio-conferencing"></a><span data-ttu-id="16df8-432">Disponibilidade da Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-432">Availability of Audio Conferencing</span></span>

<span data-ttu-id="16df8-433">A Audioconferência está disponível nestes [países e regiões](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).</span><span class="sxs-lookup"><span data-stu-id="16df8-433">Audio Conferencing is available in these [countries and regions](https://support.office.com/article/Countries-and-regions-that-are-supported-for-Skype-for-Business-Online-PSTN-Services-6ba72f37-d303-4795-aa8f-7e1845078ed7?ui=en-US&rs=en-US&ad=US).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="16df8-434">Devido a restrições legais, para a Audioconferência estar disponível para organizações multinacionais, o contrato de assinaturas do Office 365 deve ser obtido dos países e regiões cobertos pelo serviço de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-434">Due to legal constraints, for Audio Conferencing to be available to multinational organizations, the contract for Office 365 subscriptions must be sourced from countries and regions covered by Audio Conferencing service.</span></span>

<span data-ttu-id="16df8-435">Depois de confirmar a elegibilidade da sua organização para obter o serviço de Audioconferência, com base na lista de países e regiões disponíveis, compile a lista dos locais de usuários ou escritórios onde o serviço de Audioconferência será implementado.</span><span class="sxs-lookup"><span data-stu-id="16df8-435">After confirming your organization’s eligibility for obtaining the Audio Conferencing service, compile the list of user locations or offices where Audio Conferencing service will be implemented based on the list of available countries and regions.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="16df8-436">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="16df8-436">Decision Points</span></span></td>
<td align="left"><p><span data-ttu-id="16df8-437">Decida quais locais de usuários ou escritórios implementarão o serviço de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-437">Decide which user locations or offices will implement the Audio Conferencing service.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="16df8-438">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="16df8-438">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="16df8-439">Documente os locais de usuários ou escritórios que implementarão o serviço de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-439">Document the user locations or offices to be enabled for the Audio Conferencing service.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-440">Escritório</span><span class="sxs-lookup"><span data-stu-id="16df8-440">Office</span></span></th>
<th align="left"><span data-ttu-id="16df8-441">Localização</span><span class="sxs-lookup"><span data-stu-id="16df8-441">Location</span></span></th>
<th align="left"><span data-ttu-id="16df8-442">Serviço de Conferência PSTN</span><span class="sxs-lookup"><span data-stu-id="16df8-442">PSTN Conference Service</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-443">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="16df8-443">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-444">Austrália</span><span class="sxs-lookup"><span data-stu-id="16df8-444">Australia</span></span></td>
<td align="left"><span data-ttu-id="16df8-445">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-445">Audio Video Conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-446">100 Alma Road</span><span class="sxs-lookup"><span data-stu-id="16df8-446">100 Cyberport Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-447">Hong Kong SAR</span><span class="sxs-lookup"><span data-stu-id="16df8-447">Hong Kong SAR</span></span></td>
<td align="left"><span data-ttu-id="16df8-448">Conferência PSTN herdada</span><span class="sxs-lookup"><span data-stu-id="16df8-448">Legacy PSTN Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-449">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="16df8-449">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="16df8-450">Cingapura</span><span class="sxs-lookup"><span data-stu-id="16df8-450">Singapore</span></span></td>
<td align="left"><span data-ttu-id="16df8-451">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-451">Audio Video Conferencing</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-452">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="16df8-452">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="16df8-453">Reino Unido</span><span class="sxs-lookup"><span data-stu-id="16df8-453">United Kingdom</span></span></td>
<td align="left"><span data-ttu-id="16df8-454">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-454">Audio Video Conferencing</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-455">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="16df8-455">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="16df8-456">França</span><span class="sxs-lookup"><span data-stu-id="16df8-456">France</span></span></td>
<td align="left"><span data-ttu-id="16df8-457">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-457">Audio Video Conferencing</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-458">_Tabela 7 Exemplo de lista de habilitação do site do serviço de Audioconferência_</span><span class="sxs-lookup"><span data-stu-id="16df8-458">_Table 7 Example of Audio Conferencing service site enablement list_</span></span>


## <a name="licensing-for-audio-conferencing"></a><span data-ttu-id="16df8-459">Licença para a Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-459">Licensing for Audio Conferencing</span></span>

<span data-ttu-id="16df8-460">[A licença para a Audioconferência](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), anteriormente conhecida como licença de Conferência PSTN do Skype for Business, está disponível como parte dos planos de inscrição Office 365 E5 ou como um complemento aos parte dos planos de inscrição Office 365 E1 ou Office 365 E3.</span><span class="sxs-lookup"><span data-stu-id="16df8-460">[Audio Conferencing license](https://support.office.com/article/Skype-for-Business-add-on-licensing-3ed752b1-5983-43f9-bcfd-760619ab40a7?ui=en-US&rs=en-US&ad=US), formerly known as Skype for Business PSTN Conferencing license, is available as part of Office 365 E5 subscription plans, or as an add-on to Office 365 E1 or Office 365 E3 subscription plans.</span></span>

> [!NOTE]
> <span data-ttu-id="16df8-461">A conferência PSTN ou por discagem no Teams não suporta Provedores de Audioconferência<sup></sup> de terceiros (ACPs).</span><span class="sxs-lookup"><span data-stu-id="16df8-461">PSTN or dial-in conferencing in Teams does not support 3<sup>rd</sup>-party Audio Conferencing Providers (ACPs).</span></span>
> <br><span data-ttu-id="16df8-462">Se você já usa a Conferência PSTN do Skype for Business hoje, você pode aproveitar a Audioconferência no Teams imediatamente.</span><span class="sxs-lookup"><span data-stu-id="16df8-462">If you already use Skype for Business Online PSTN Conferencing today, you can immediately take advantage of Audio Conferencing in Teams.</span></span>

<span data-ttu-id="16df8-463">Para fornecer números de telefone gratuitos de ponte de conferência e para suportar discagem de conferência para números de telefone internacionais, você precisa configurar [Créditos de Comunicação](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="16df8-463">To provide toll-free conference bridge phone numbers and to support conferencing dial-out to International phone numbers, you need to setup [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) for your organization.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="16df8-464">Alguns países são atendidos apenas por números de telefone gratuitos para ponte de conferência, e nesse caso, o uso de Créditos de Comunicação é um requisito obrigatório para ter suporte de acesso a esses países.</span><span class="sxs-lookup"><span data-stu-id="16df8-464">Some countries are serviced by toll-free conference bridge phone numbers only, and in this case the use of Communications Credits is a mandatory requirement to support dial in for such countries.</span></span>

<span data-ttu-id="16df8-465">A primeira consideração a fazer ao implementar os Créditos de Comunicação é decidir o valor inicial de fundos a serem comprados.</span><span class="sxs-lookup"><span data-stu-id="16df8-465">The first consideration to make when implementing Communications Credits is to decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="16df8-466">Os valores de fundos recomendados podem ser consultados na documentação dos [Créditos de Comunicação](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059).</span><span class="sxs-lookup"><span data-stu-id="16df8-466">Recommended funding amounts can be referenced from the [Communications Credits](https://support.office.com/en-us/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span>

<span data-ttu-id="16df8-467">Se a sua organização optar por usar recarga automática, uma recomendação sobre o gatilho (menor valor de fundos) também está incluída na documentação dos [Créditos de Comunicação](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059).</span><span class="sxs-lookup"><span data-stu-id="16df8-467">If your organization chooses to use auto-recharge, a recommendation on the trigger (lowest amount of funds) is also included in the [Communications Credits](https://support.office.com/article/What-is-PSTN-Consumption-billing-524dbea7-117f-493d-8005-6461f7f10059) documentation.</span></span> <span data-ttu-id="16df8-468">O valor da recarga automática deve ser determinado pelo uso real.</span><span class="sxs-lookup"><span data-stu-id="16df8-468">Auto-recharge amount needs to be determined by the actual usage.</span></span> <span data-ttu-id="16df8-469">O uso de Créditos de Comunicação deve ser monitorado ao longo do tempo e o valor da recarga precisa ser ajustado conforme a necessidade.</span><span class="sxs-lookup"><span data-stu-id="16df8-469">Communications Credits usage should be monitored over time and the recharge amount needs to be adjusted as required.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="16df8-470">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="16df8-470">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-471">Se a sua organização ainda não tiver adquirido a licença necessária para a Audioconferência, decida se as licenças da Audioconferência serão adquiridas ampliando as inscrições existentes do Office 365 ou adquirindo complementos de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-471">If your organization has not already purchased the required Audio Conferencing licensing, decide whether Audio Conferencing licenses will be acquired by stepping up existing Office 365 subscriptions or by acquiring Audio Conferencing add-ons.</span></span></li>
<li><span data-ttu-id="16df8-472">Decida se os Créditos de Comunicação serão obrigatórios para a implementação da Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-472">Decide if Communications Credits is required for Audio Conferencing implementation.</span></span> <span data-ttu-id="16df8-473">Em caso positivo, decida o valor inicial de fundos a serem comprados.</span><span class="sxs-lookup"><span data-stu-id="16df8-473">If so, decide the initial amount of funds to be purchased.</span></span> <span data-ttu-id="16df8-474">Onde aplicável, decida o valor do gatilho e o valor da recarga automática.</span><span class="sxs-lookup"><span data-stu-id="16df8-474">Where applicable, decide the trigger amount and auto-recharge amount.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="16df8-475">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="16df8-475">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-476">Documentar os usuários que receberão a licença da Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-476">Document the users that will be assigned Audio Conferencing license.</span></span></li>
<li><span data-ttu-id="16df8-477">Documentar o plano de Créditos de Comunicação (valor inicial, valor do gatilho, valor da recarga automática).</span><span class="sxs-lookup"><span data-stu-id="16df8-477">Document the Communications Credits plan (initial amount, trigger amount, auto-recharge amount).</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-478">Usuário</span><span class="sxs-lookup"><span data-stu-id="16df8-478">User</span></span></th>
<th align="left"><span data-ttu-id="16df8-479">Escritório</span><span class="sxs-lookup"><span data-stu-id="16df8-479">Office</span></span></th>
<th align="left"><span data-ttu-id="16df8-480">Licença do Office 365</span><span class="sxs-lookup"><span data-stu-id="16df8-480">Office 365 License</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-481">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="16df8-481">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="16df8-482">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="16df8-482">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-483">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="16df8-483">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-484">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="16df8-484">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="16df8-485">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="16df8-485">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-486">Office 365 E3, complemento de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-486">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-487">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="16df8-487">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="16df8-488">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="16df8-488">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-489">Office 365 E3, complemento de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-489">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-490">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="16df8-490">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="16df8-491">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="16df8-491">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="16df8-492">Office 365 E3, complemento de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-492">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-493">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="16df8-493">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="16df8-494">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="16df8-494">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="16df8-495">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="16df8-495">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-496">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="16df8-496">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="16df8-497">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="16df8-497">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="16df8-498">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="16df8-498">Office 365 E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-499">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="16df8-499">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="16df8-500">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="16df8-500">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="16df8-501">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="16df8-501">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-502">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="16df8-502">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="16df8-503">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="16df8-503">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="16df8-504">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="16df8-504">Office 365 E5</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-505">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="16df8-505">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="16df8-506">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="16df8-506">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="16df8-507">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="16df8-507">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-508">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="16df8-508">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="16df8-509">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="16df8-509">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="16df8-510">Office 365 E3, complemento de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-510">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-511">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="16df8-511">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="16df8-512">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="16df8-512">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="16df8-513">Office 365 E5</span><span class="sxs-lookup"><span data-stu-id="16df8-513">Office 365 E5</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-514">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="16df8-514">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="16df8-515">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="16df8-515">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="16df8-516">Office 365 E3, complemento de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-516">Office 365 E3, Audio Conferencing add-on</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-517">_Tabela 8 Exemplo de lista de atribuição de licenças para organizadores de reunião de Audioconferência_</span><span class="sxs-lookup"><span data-stu-id="16df8-517">_Table 8 Example of license assignment list for Audio Conferencing meeting organizers_</span></span>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-518">Valor inicial</span><span class="sxs-lookup"><span data-stu-id="16df8-518">Initial amount</span></span></th>
<td align="left"><span data-ttu-id="16df8-519">US$ 1.000</span><span class="sxs-lookup"><span data-stu-id="16df8-519">$ 1,000</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-520">Valor do gatilho</span><span class="sxs-lookup"><span data-stu-id="16df8-520">Trigger amount</span></span></th>
<td align="left"><span data-ttu-id="16df8-521">US$ 400</span><span class="sxs-lookup"><span data-stu-id="16df8-521">$ 400</span></span></td>
</tr>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-522">Valor da recarga automática</span><span class="sxs-lookup"><span data-stu-id="16df8-522">Auto-recharge amount</span></span></th>
<td align="left"><span data-ttu-id="16df8-523">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-523">TBA</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-524">_Tabela 9 Exemplo de números de planejamento de Créditos de Comunicação_</span><span class="sxs-lookup"><span data-stu-id="16df8-524">_Table 9 Example of Communications Credits planning numbers_</span></span>


## <a name="conference-bridge-phone-numbers"></a><span data-ttu-id="16df8-525">Números de telefone de ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="16df8-525">Conference bridge phone numbers</span></span>

<span data-ttu-id="16df8-526">O serviço de Audioconferência do Office 365 inclui:</span><span class="sxs-lookup"><span data-stu-id="16df8-526">The Audio Conferencing service in Office 365 includes:</span></span>

-   <span data-ttu-id="16df8-527">Vários tipos de números de telefone de ponte de conferência (pagos e gratuitos)</span><span class="sxs-lookup"><span data-stu-id="16df8-527">Multiple types of conference bridge phone numbers (Toll and Toll-Free)</span></span>

-   <span data-ttu-id="16df8-528">Várias categorias de número de telefone (exclusivo e compartilhado)</span><span class="sxs-lookup"><span data-stu-id="16df8-528">Multiple categories of the phone number (dedicated and shared)</span></span>

-   <span data-ttu-id="16df8-529">Suporte de vários idiomas para a ponte de conferência (primária e secundária)</span><span class="sxs-lookup"><span data-stu-id="16df8-529">Support for multiple languages for the conference bridge (primary and secondary)</span></span>

-   <span data-ttu-id="16df8-530">Um número de telefone padrão para o locatário.</span><span class="sxs-lookup"><span data-stu-id="16df8-530">A default phone number for the tenant.</span></span>

<span data-ttu-id="16df8-531">A descrição completa dos recursos incluídos pode ser consultada em [Configurar conferência PSTN ou por discagem para o Skype for Business](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) e [Números de telefone para conferência de discagem](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span><span class="sxs-lookup"><span data-stu-id="16df8-531">Full description of the included capabilities can be referenced from [Set up dial-in or PSTN conferencing for Skype for Business](https://support.office.com/article/Set-up-dial-in-or-PSTN-conferencing-for-Skype-for-Business-d01954f1-4f37-4cf5-a636-20039e5c59e9?ui=en-US&rs=en-US&ad=US) and [Phone numbers for dial-in conferencing](https://support.office.com/article/Phone-numbers-for-dial-in-conferencing-95a08f84-04e5-4f72-88a8-d6472a7c89d7?ui=en-US&rs=en-US&ad=US)**.**</span></span>

> [!NOTE]
> <span data-ttu-id="16df8-532">Os números de telefone exclusivos da ponte de conferência são contados em relação ao limite de números de telefone que podem ser adquiridos por locatário com base no número de licenças aplicáveis,conforme descrito em [Obter números de telefone para o serviço Skype for Business](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span><span class="sxs-lookup"><span data-stu-id="16df8-532">Dedicated conference bridge phone numbers are counted towards the limit of phone numbers that can be acquired per tenant, based on the number of applicable licenses as described in [Getting Skype for Business service phone numbers](https://support.office.com/article/Getting-Skype-for-Business-service-phone-numbers-e434aeb2-af99-40e7-981e-a474f0383734).</span></span> <span data-ttu-id="16df8-533">Os números de telefone gratuitos da ponte de conferência não precisam de Créditos de Comunicação.</span><span class="sxs-lookup"><span data-stu-id="16df8-533">Toll-free conference bridge phone numbers require Communications Credits.</span></span>

<span data-ttu-id="16df8-534">Se houver números de telefone existentes da ponte de conferência que precisem ser transferidos para o serviço de Audioconferência, presumindo que estejam cumprindo os requisitos específicos do país, os números de telefone da ponte de conferência existentes poderão ser transferidos para a Microsoft.</span><span class="sxs-lookup"><span data-stu-id="16df8-534">If there are existing conference bridge phone numbers that must be transferred to the Audio Conferencing service, assuming they are meeting the country-specific requirements, then the existing conference bridge phone numbers can be transferred to Microsoft.</span></span>


> [!NOTE]
> <span data-ttu-id="16df8-535">A complexidade da transferência de números de telefone para a Microsoft varia muito com base nos países ou regiões, operadoras, o número de circuitos envolvidos e vários outros fatores.</span><span class="sxs-lookup"><span data-stu-id="16df8-535">Complexity of transferring phone numbers to Microsoft varies greatly based on the countries or regions, carriers, the number of circuits involved, and many other contributing factors.</span></span> <span data-ttu-id="16df8-536">Para planejar a portabilidade dos números de telefone, consulte o [Guia de portabilidade de números](https://go.microsoft.com/fwlink/?linkid=859011).</span><span class="sxs-lookup"><span data-stu-id="16df8-536">To plan for phone number porting, check out the [Number Porting Guide](https://go.microsoft.com/fwlink/?linkid=859011).</span></span>

|  |  |
|---------|---------|
| <iframe width="350" height="200" src="https://www.youtube.com/embed/5k0C21KAsns" frameborder="0" allowfullscreen></iframe>  |  |

<span data-ttu-id="16df8-537">Detalhes adicionais sobre a transferência de números de telefone para o serviço de Audioconferência podem ser encontrados em [Transferir números de telefone para o Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span><span class="sxs-lookup"><span data-stu-id="16df8-537">Additional details on transferring phone numbers to Audio Conferencing service can be found in [Transfer phone numbers to Skype for Business Online](https://support.office.com/article/Transfer-phone-numbers-to-Skype-for-Business-Online-47b3af8e-4171-4dec-8333-c956f108664e).</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="16df8-538">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="16df8-538">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-539">Decidir se a organização exigirá números de telefone exclusivos da ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="16df8-539">Decide whether the organization requires dedicated conference bridge phone numbers</span></span></li>
<li><span data-ttu-id="16df8-540">Decidir como os números de telefone exclusivos da ponte da conferência serão obtidos para locais de usuários ou escritórios que estão no escopo de implementação da Audioconferência (obter da Microsoft ou transferir os números de telefone existentes)</span><span class="sxs-lookup"><span data-stu-id="16df8-540">Decide how the dedicated conference bridge phone numbers will be obtained for user locations or offices in-scope for the Audio Conferencing implementation (obtain from Microsoft or transfer existing phone numbers)</span></span></li>
<li><span data-ttu-id="16df8-541">Se você optar por obter da Microsoft, decidir o método para obter números de telefone (envio de formulários ou automatizado) para os locais de usuários ou escritórios que estão no escopo de implementação da Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-541">If you choose to obtain from Microsoft, decide the method to obtain phone numbers (form submission or automated) for user locations or offices in-scope for the Audio Conferencing implementation</span></span></li>
<li><span data-ttu-id="16df8-542">Decidir as preferências de idioma a ser configuradas para naca números de telefone de ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="16df8-542">Decide the language preferences to be set up for each dedicated conference bridge phone number</span></span></li>
<li><span data-ttu-id="16df8-543">Decidir o número de telefone de ponte de conferência padrão do locatário</span><span class="sxs-lookup"><span data-stu-id="16df8-543">Decide the tenant default conference bridge phone number</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="16df8-544">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="16df8-544">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-545">Documentar o plano mestre para a aquisição de números de telefone, detalhando como os números de telefone serão obtidos para cada um dos locais de usuários ou escritórios que estão no escopo de implementação da Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-545">Document the master plan for phone numbers acquisition, detailing how phone numbers will be obtained for each user location or office in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="16df8-546">Se aplicável, preencha <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">o formulário de solicitação de novo número de telefone</a>, um formulário para cada local ou escritório</span><span class="sxs-lookup"><span data-stu-id="16df8-546">If applicable, complete <a href="https://support.office.com/article/Get-phone-numbers-for-Skype-for-Business-Online-6b61cb3c-361c-48a8-a9ef-d81bddde27bb?ui=en-US&amp;rs=en-US&amp;ad=US">the New Telephone Number Request form</a>, one form for each location or office</span></span></li>
<li><span data-ttu-id="16df8-547">Se você optar por transferir números de telefone existentes confira o <a href="https://go.microsoft.com/fwlink/?linkid=859011">Guia de portabilidade de números</a> para planejar a ajustar o cronograma de implementação da Audioconferência de acordo.</span><span class="sxs-lookup"><span data-stu-id="16df8-547">If you choose to transfer existing phone numbers, check out the <a href="https://go.microsoft.com/fwlink/?linkid=859011">Number Porting Guide</a> to plan it and adjust Audio Conferencing implementation timeline accordingly.</span></span></li>
<li><span data-ttu-id="16df8-548">Documentar as configurações detalhadas do número de telefone da ponte de conferência (números de telefone exclusivos e compartilhados da ponte de conferência, preferências de idioma para cada número exclusivo de telefone da ponte de conferência, número de telefone da ponte de conferência padrão do locatário)</span><span class="sxs-lookup"><span data-stu-id="16df8-548">Document the detailed conference bridge phone number configurations (shared and dedicated conference bridge phone numbers, language preferences for each dedicated conference bridge phone number, tenant default conference bridge phone number)</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-549">Escritório</span><span class="sxs-lookup"><span data-stu-id="16df8-549">Office</span></span></th>
<th align="left"><span data-ttu-id="16df8-550">Aquisição do número da ponte e Tipo da ponte</span><span class="sxs-lookup"><span data-stu-id="16df8-550">Bridge Number Acquisition and Bridge Type</span></span></th>
<th align="left"><span data-ttu-id="16df8-551">Número da ponte</span><span class="sxs-lookup"><span data-stu-id="16df8-551">Bridge Number</span></span></th>
<th align="left"><span data-ttu-id="16df8-552">Idioma da ponte</span><span class="sxs-lookup"><span data-stu-id="16df8-552">Bridge Language</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-553">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="16df8-553">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-554">Adquirir novo, exclusivo</span><span class="sxs-lookup"><span data-stu-id="16df8-554">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="16df8-555">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-555">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-556">Inglês (Austrália)</span><span class="sxs-lookup"><span data-stu-id="16df8-556">en-AU – English (Australia)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-557">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="16df8-557">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="16df8-558">Adquirir novo, compartilhado</span><span class="sxs-lookup"><span data-stu-id="16df8-558">Acquire new, shared</span></span></td>
<td align="left"><span data-ttu-id="16df8-559">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-559">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-560">Inglês (Estados Unidos); Chinês (Simplificado, PRC)</span><span class="sxs-lookup"><span data-stu-id="16df8-560">English (United States), Chinese (Simplified, PRC)</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-561">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="16df8-561">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="16df8-562">Porta existente, exclusiva</span><span class="sxs-lookup"><span data-stu-id="16df8-562">Port existing, dedicated</span></span></td>
<td align="left"><span data-ttu-id="16df8-563">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="16df8-563">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="16df8-564">Inglês (Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="16df8-564">en-GB – English (United Kingdom)</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-565">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="16df8-565">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="16df8-566">Adquirir novo, exclusivo</span><span class="sxs-lookup"><span data-stu-id="16df8-566">Acquire new, dedicated</span></span></td>
<td align="left"><span data-ttu-id="16df8-567">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-567">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-568">Francês (França), Inglês (Reino Unido)</span><span class="sxs-lookup"><span data-stu-id="16df8-568">French (France), English (United Kingdom)</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-569">_Tabela 10 Exemplo de detalhes de ponte de conferência_</span><span class="sxs-lookup"><span data-stu-id="16df8-569">_Table 10 Example of conference bridge details_</span></span>


> [!NOTE]
> <span data-ttu-id="16df8-570">A tabela de exemplo acima e as tabelas subsequentes ao longo deste documento servem como modelo.</span><span class="sxs-lookup"><span data-stu-id="16df8-570">The example table above and subsequent tables throughout this document serve as a template.</span></span> <span data-ttu-id="16df8-571">Você verá “TBA” (a ser adicionado) para informações que você precisa inserir como parte do seu processo de planejamento.</span><span class="sxs-lookup"><span data-stu-id="16df8-571">You'll see "TBA" (to be added) for information that you need to complete as part of your planning process.</span></span>

## <a name="conference-bridge-settings"></a><span data-ttu-id="16df8-572">Configurações de ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="16df8-572">Conference bridge settings</span></span>

<span data-ttu-id="16df8-573">As opções de configuração da experiência de entrar em uma reunião de Audioconferência em toda a organização (notificação de entrada e saída e gravação de nome do chamador), o comprimento do PIN do organizador da reunião e a notificação por e-mail estão disponíveis para adaptar melhor a experiência do usuário final.</span><span class="sxs-lookup"><span data-stu-id="16df8-573">Organization-wide configuration options around Audio Conferencing meeting join experience (meeting entry and exit notification and caller name recording), meeting organizer’s PIN length, and email notification are available to further tailor the end-user experience.</span></span>

-   <span data-ttu-id="16df8-574">As notificações de entrada e saída de reuniões estão disponíveis na forma de nome, número de telefone e tons registrados.</span><span class="sxs-lookup"><span data-stu-id="16df8-574">Meeting entry and exit notifications are available in the form of recorded name, phone number, and tones.</span></span>

-   <span data-ttu-id="16df8-575">O comprimento do PIN pode ter de 4 a 12 dígitos, com um PIN de 5 dígitos como padrão.</span><span class="sxs-lookup"><span data-stu-id="16df8-575">PIN length is configurable from 4 to 12 digits, with a 5-digit PIN as the default.</span></span>

-   <span data-ttu-id="16df8-576">Os e-mails de notificação após a habilitação da licença de Audioconferência ou qualquer outra alteração conduzida pelo administrador estão habilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="16df8-576">Notification emails upon enablement of Audio Conferencing license or any other admin-driven changes are enabled by default.</span></span> <span data-ttu-id="16df8-577">Você pode desabilitar esse recurso e assumir o controle das comunicações dos usuários finais da sua organização.</span><span class="sxs-lookup"><span data-stu-id="16df8-577">You can disable this feature and take control of your organization’s end-user communications.</span></span>

<span data-ttu-id="16df8-578">Para os usuários aos quais tenha sido atribuída uma licença de Audioconferência, os números chamada pagos e gratuitos padrão, mostrados nas coordenadas de Audioconferência, podem ser configurados para uso:</span><span class="sxs-lookup"><span data-stu-id="16df8-578">For users who are assigned an Audio Conferencing license, the default toll/toll-free numbers, shown in the Audio Conferencing coordinates, are configurable to use:</span></span>

-   <span data-ttu-id="16df8-579">no padrão em nível de locatário ou</span><span class="sxs-lookup"><span data-stu-id="16df8-579">the tenant-level default, or</span></span>

-   <span data-ttu-id="16df8-580">em números de telefone de ponte de conferência atribuídos automaticamente ou</span><span class="sxs-lookup"><span data-stu-id="16df8-580">the automatically-assigned conference bridge phone numbers, or</span></span>

-   <span data-ttu-id="16df8-581">em números de telefone de ponte de conferência definidos manualmente para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="16df8-581">manually defined conference bridge phone numbers for each user.</span></span>

<span data-ttu-id="16df8-582">Os números de telefone da ponte de conferência específicos do usuário costumam ser úteis em organizações nacionais ou internacionais, onde os usuários são distribuídos e precisam fornecer números locais como números de telefone da ponte de conferência padrão nos convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="16df8-582">User-specific conference bridge phone numbers are typically useful in global or nationwide organizations where users are distributed and must provide local numbers as the default conference bridge phone numbers in the meeting invites.</span></span>

<span data-ttu-id="16df8-583">Os participantes que entram de diferentes cidades ou do exterior podem procurar números adicionais configurados no nível do locatário, mas esses números não aparecem diretamente nos convites de reunião.</span><span class="sxs-lookup"><span data-stu-id="16df8-583">Participants joining from different cities or overseas can look up additional numbers configured at the tenant-level, but these numbers do not appear directly in the meeting invites.</span></span> <span data-ttu-id="16df8-584">Os convites de reunião contêm um link que levará os participantes à página de números de discagem da conferência do Teams para que eles procurem os números de telefone da ponte de conferência mais próximos do seu local que estejam disponíveis.</span><span class="sxs-lookup"><span data-stu-id="16df8-584">The meeting invites provide a link that will take participants to the Teams Conference Dial-in Numbers page for them to lookup the closest conference bridge phone numbers available from their location.</span></span>

<span data-ttu-id="16df8-585">Você também pode configurar como os autores de chamada não autenticados são tratados por cada organizador de reunião individual para exigir que o organizador da reunião inicie a reunião antes que os autores de chamada não autenticados sejam admitidos ou para permitir que os autores de chamada não autenticados iniciem uma reunião.</span><span class="sxs-lookup"><span data-stu-id="16df8-585">You can also configure how unauthenticated callers are handled by each individual meeting organizer, whether to require meeting organizer to start the meeting before unauthenticated callers are admitted, or to allow unauthenticated callers to start a meeting.</span></span>

<span data-ttu-id="16df8-586">Estão disponíveis configurações adicionais que podem ser aplicadas para cada usuário para controlar o uso de números de telefone gratuitos de ponte de conferência e discagem de uma conferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-586">Additional configurations that can be applied for each user are available to control the use of toll-free conference bridge phone numbers and dial-out from a conference.</span></span>

> [!NOTE]
> <span data-ttu-id="16df8-587">Esses controles relacionados a custo estão atualmente disponíveis somente para clientes da prévia.</span><span class="sxs-lookup"><span data-stu-id="16df8-587">These cost-related controls are currently available for preview customers only.</span></span> <span data-ttu-id="16df8-588">Você pode inscrever a sua organização no programa de prévia em [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).</span><span class="sxs-lookup"><span data-stu-id="16df8-588">You can enroll your organization in the preview program from [https://www.skypepreview.com](https://go.microsoft.com/fwlink/?linkid=859013).</span></span>

<span data-ttu-id="16df8-589">Com esses controles, você pode decidir se os organizadores da reunião podem fornecer números de telefone gratuitos de ponte de conferência para reuniões organizadas por eles, ou para controlar se os participantes podem discar das reuniões organizadas por eles.</span><span class="sxs-lookup"><span data-stu-id="16df8-589">With these controls, you can decide whether meeting organizers can provide toll-free conference bridge phone numbers for meetings organized by them, and to control whether participants can dial out from the meetings organized by them.</span></span> <span data-ttu-id="16df8-590">O nível de controle de discagem vai da exclusão da permissão de discagem, permitindo discar apenas para números domésticos, até a permissão de discagem para números domésticos e internacionais.</span><span class="sxs-lookup"><span data-stu-id="16df8-590">The level of dial-out control spans from disallowing dial out, only allowing dial out to domestic numbers, to allowing dial out to both domestic and international numbers.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="16df8-591">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="16df8-591">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-592">Decidir se a organização exigirá notificações de entrada e saída e, em caso afirmativo, o tipo de notificação a ser implementada (tons, número de telefone ou nome registrado).</span><span class="sxs-lookup"><span data-stu-id="16df8-592">Decide whether the organization requires entry and exit notifications, and if yes, the type of notification to be implemented (tones, phone number, or recorded name).</span></span></li>
<li><span data-ttu-id="16df8-593">Decidir o comprimento do PIN da Audioconferência que atenda às exigências de segurança da organização.</span><span class="sxs-lookup"><span data-stu-id="16df8-593">Decide the Audio Conferencing PIN length that meets the organizational security requirements.</span></span></li>
<li><span data-ttu-id="16df8-594">Decidir se a organização deseja assumir o controle das comunicações do usuário final relacionadas ao serviço de Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-594">Decide if the organization wants to take control of end-user communications related to Audio Conferencing service.</span></span></li>
<li><span data-ttu-id="16df8-595">Decidir os números de telefone da ponte da conferência a serem atribuídos a cada organizador de reunião.</span><span class="sxs-lookup"><span data-stu-id="16df8-595">Decide the conference bridge phone numbers to be assigned to each meeting organizer.</span></span></li>
<li><span data-ttu-id="16df8-596">Decidir se alguns organizadores de reunião exigirão o recurso de usar números de telefone gratuitos de ponte de conferência para as suas reuniões</span><span class="sxs-lookup"><span data-stu-id="16df8-596">Decide whether some meeting organizers require the ability to use toll-free conference bridge phone numbers for their meeings</span></span></li>
<li><span data-ttu-id="16df8-597">Decidir se alguns organizadores de reunião exigirão o recurso de permitir que os autores da chamada não autenticados iniciem uma reunião.</span><span class="sxs-lookup"><span data-stu-id="16df8-597">Decide whether some meeting organizers require the ability to allow unauthenticated callers to start a meeting.</span></span></li>
<li><span data-ttu-id="16df8-598">Decidir se alguns organizadores de reunião exigirão que a discagem de saída da conferência seja controlada.</span><span class="sxs-lookup"><span data-stu-id="16df8-598">Decide whether some meeting organizers require conference dial out to be controlled.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="16df8-599">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="16df8-599">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-600">Documentar detalhadamente as configurações de ponte de conferência (notificações de entrada e saída, comprimento do PIN, notificação por e-mail de alteração do configurações).</span><span class="sxs-lookup"><span data-stu-id="16df8-600">Document the detailed conference bridge settings (entry and exit notifications, PIN length, configuration change email notification).</span></span></li>
<li><span data-ttu-id="16df8-601">Documentar os números de telefone de ponte de conferência a serem atribuídos a cada organizador de reunião na configuração correspondente para controlar a política de autores de chamada não autenticados e os controles gratuitos e de discagem de saída.</span><span class="sxs-lookup"><span data-stu-id="16df8-601">Document the conference bridge phone numbers to be assinged to each meeting organizer and the corresponding setting to control unauthenticated caller’s policy, and toll-free and dial out controls.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="16df8-602"><strong>Habilitar notificações de entrada e saída de reuniões</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-602"><strong>Enable meeting entry and exit notifications</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-603">Habilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-603">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="16df8-604"><strong>Tipo de anúncio de entrada/saída</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-604"><strong>Entry/exit announcement type</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-605">Tons</span><span class="sxs-lookup"><span data-stu-id="16df8-605">Tones</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="16df8-606"><strong>Solicitar que os autores da chamada registrem seu nome antes de entrar na reunião</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-606"><strong>Ask callers to record their name before joining the meeting</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-607">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-607">Disabled.</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="16df8-608"><strong>Tamanho mínimo do PIN</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-608"><strong>Minimum PIN length</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-609">5</span><span class="sxs-lookup"><span data-stu-id="16df8-609">Example 5</span></span></td>
</tr>
<tr class="header">
<td align="left"><span data-ttu-id="16df8-610"><strong>Enviar e-mails automaticamente aos usuários se suas configurações de discagem forem alteradas</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-610"><strong>Automatically send emails to users if their dial-in settings change</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-611">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-611">Disabled.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-612">_Tabela 11 Exemplo de configurações de ponte de conferência_</span><span class="sxs-lookup"><span data-stu-id="16df8-612">_Table 11 Example of conference bridge settings_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-613">Usuário</span><span class="sxs-lookup"><span data-stu-id="16df8-613">User</span></span></th>
<th align="left"><span data-ttu-id="16df8-614">Escritório</span><span class="sxs-lookup"><span data-stu-id="16df8-614">Office</span></span></th>
<th align="left"><span data-ttu-id="16df8-615">Número de chamada padrão</span><span class="sxs-lookup"><span data-stu-id="16df8-615">Default toll number</span></span></th>
<th align="left"><span data-ttu-id="16df8-616">Número de chamada gratuita padrão</span><span class="sxs-lookup"><span data-stu-id="16df8-616">Default toll-free number</span></span></th>
<th align="left"><span data-ttu-id="16df8-617">Permitir chamada gratuita</span><span class="sxs-lookup"><span data-stu-id="16df8-617">Allow toll-free</span></span></th>
<th align="left"><span data-ttu-id="16df8-618">Autores de chamada não autenticados ignoram o lobby</span><span class="sxs-lookup"><span data-stu-id="16df8-618">PSTN callers bypass lobby</span></span></th>
<th align="left"><span data-ttu-id="16df8-619">Discagem de saída de conferência</span><span class="sxs-lookup"><span data-stu-id="16df8-619">Conference dial out</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-620">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="16df8-620">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="16df8-621">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="16df8-621">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-622">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-622">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-623">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-623">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-624">Sim</span><span class="sxs-lookup"><span data-stu-id="16df8-624">Yes</span></span></td>
<td align="left"><span data-ttu-id="16df8-625">Habilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-625">Enabled</span></span></td>
<td align="left"><span data-ttu-id="16df8-626">Doméstico e internacional</span><span class="sxs-lookup"><span data-stu-id="16df8-626">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-627">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="16df8-627">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="16df8-628">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="16df8-628">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-629">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-629">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-630">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-630">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-631">Não</span><span class="sxs-lookup"><span data-stu-id="16df8-631">No</span></span></td>
<td align="left"><span data-ttu-id="16df8-632">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-632">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="16df8-633">Não permitido</span><span class="sxs-lookup"><span data-stu-id="16df8-633">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-634">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="16df8-634">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="16df8-635">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="16df8-635">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-636">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-636">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-637">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-637">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-638">Não</span><span class="sxs-lookup"><span data-stu-id="16df8-638">No</span></span></td>
<td align="left"><span data-ttu-id="16df8-639">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-639">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="16df8-640">Não permitido</span><span class="sxs-lookup"><span data-stu-id="16df8-640">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-641">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="16df8-641">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="16df8-642">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="16df8-642">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="16df8-643">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-643">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-644">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-644">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-645">Sim</span><span class="sxs-lookup"><span data-stu-id="16df8-645">Yes</span></span></td>
<td align="left"><span data-ttu-id="16df8-646">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-646">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="16df8-647">Doméstico</span><span class="sxs-lookup"><span data-stu-id="16df8-647">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-648">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="16df8-648">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="16df8-649">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="16df8-649">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="16df8-650">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-650">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-651">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-651">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-652">Sim</span><span class="sxs-lookup"><span data-stu-id="16df8-652">Yes</span></span></td>
<td align="left"><span data-ttu-id="16df8-653">Habilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-653">Enabled</span></span></td>
<td align="left"><span data-ttu-id="16df8-654">Doméstico</span><span class="sxs-lookup"><span data-stu-id="16df8-654">Domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-655">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="16df8-655">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="16df8-656">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="16df8-656">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="16df8-657">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-657">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-658">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-658">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-659">Sim</span><span class="sxs-lookup"><span data-stu-id="16df8-659">Yes</span></span></td>
<td align="left"><span data-ttu-id="16df8-660">Habilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-660">Enabled</span></span></td>
<td align="left"><span data-ttu-id="16df8-661">Doméstico</span><span class="sxs-lookup"><span data-stu-id="16df8-661">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-662">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="16df8-662">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="16df8-663">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="16df8-663">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="16df8-664">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="16df8-664">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="16df8-665">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-665">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-666">Sim</span><span class="sxs-lookup"><span data-stu-id="16df8-666">Yes</span></span></td>
<td align="left"><span data-ttu-id="16df8-667">Habilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-667">Enabled</span></span></td>
<td align="left"><span data-ttu-id="16df8-668">Não permitido</span><span class="sxs-lookup"><span data-stu-id="16df8-668">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-669">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="16df8-669">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="16df8-670">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="16df8-670">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="16df8-671">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="16df8-671">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="16df8-672">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-672">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-673">Sim</span><span class="sxs-lookup"><span data-stu-id="16df8-673">Yes</span></span></td>
<td align="left"><span data-ttu-id="16df8-674">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-674">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="16df8-675">Não permitido</span><span class="sxs-lookup"><span data-stu-id="16df8-675">Not allowed</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-676">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="16df8-676">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="16df8-677">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="16df8-677">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="16df8-678">+44 20 7946 0001</span><span class="sxs-lookup"><span data-stu-id="16df8-678">+44 20 7946 0001</span></span></td>
<td align="left"><span data-ttu-id="16df8-679">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-679">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-680">Sim</span><span class="sxs-lookup"><span data-stu-id="16df8-680">Yes</span></span></td>
<td align="left"><span data-ttu-id="16df8-681">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-681">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="16df8-682">Não permitido</span><span class="sxs-lookup"><span data-stu-id="16df8-682">Not allowed</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-683">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="16df8-683">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="16df8-684">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="16df8-684">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="16df8-685">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-685">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-686">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-686">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-687">Não</span><span class="sxs-lookup"><span data-stu-id="16df8-687">No</span></span></td>
<td align="left"><span data-ttu-id="16df8-688">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-688">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="16df8-689">Doméstico</span><span class="sxs-lookup"><span data-stu-id="16df8-689">Domestic</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-690">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="16df8-690">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="16df8-691">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="16df8-691">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="16df8-692">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-692">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-693">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-693">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-694">Sim</span><span class="sxs-lookup"><span data-stu-id="16df8-694">Yes</span></span></td>
<td align="left"><span data-ttu-id="16df8-695">Habilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-695">Enabled</span></span></td>
<td align="left"><span data-ttu-id="16df8-696">Doméstico e internacional</span><span class="sxs-lookup"><span data-stu-id="16df8-696">International and domestic</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-697">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="16df8-697">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="16df8-698">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="16df8-698">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="16df8-699">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-699">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-700">TBA</span><span class="sxs-lookup"><span data-stu-id="16df8-700">TBA</span></span></td>
<td align="left"><span data-ttu-id="16df8-701">Não</span><span class="sxs-lookup"><span data-stu-id="16df8-701">No</span></span></td>
<td align="left"><span data-ttu-id="16df8-702">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-702">Disabled.</span></span></td>
<td align="left"><span data-ttu-id="16df8-703">Doméstico</span><span class="sxs-lookup"><span data-stu-id="16df8-703">Domestic</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-704">_Tabela 12 Exemplo de atribuições de configurações de ponte de conferência_</span><span class="sxs-lookup"><span data-stu-id="16df8-704">_Table 12 Example of conference bridge settings assignments_</span></span>


## <a name="dial-plans"></a><span data-ttu-id="16df8-705">Planos de discagem</span><span class="sxs-lookup"><span data-stu-id="16df8-705">Dial plans</span></span>

<span data-ttu-id="16df8-706">O [Plano de discagem](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), um Sistema de Telefonia do Office 365, é um conjunto de regras de normalização que converte números telefônicos discados em um formato alternativo (normalmente no formato[E.164](https://go.microsoft.com/fwlink/?linkid=859014)) para autorização de chamada e roteamento de chamada.</span><span class="sxs-lookup"><span data-stu-id="16df8-706">A [Dial Plan](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b), a Phone System feature of Office 365, is a set of normalization rules that translates dialed phone numbers into an alternate format (typically [E.164](https://go.microsoft.com/fwlink/?linkid=859014) format) for call authorization and call routing.</span></span> <span data-ttu-id="16df8-707">O serviço de Audioconferência aproveita os mesmos recursos usados pelo Sistema de Telefonia para converter números de telefone discados em cenários de discagem de saída de conferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-707">Audio Conferencing service leverages the same capabilities used by Phone System to translate dialed phone numbers in conference dial out scenarios.</span></span>

<span data-ttu-id="16df8-708">Um plano de discagem permite que os usuários disquem números de telefone da forma como estão acostumados, como omitir o código de área para chamadas locais, omitir o código de país para chamadas domésticas ou mesmo usar atalhos de discagem ao fazer uma discagem de saída de conferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-708">A dial plan allows users to dial phone numbers the way they are accustomed to, such as omitting area code for local calls, omitting country code for domestic calls, or even using short digit dialing when performing conference dial out.</span></span>

<span data-ttu-id="16df8-709">Dentro do recurso Sistema de Telefonia do Office 365, existem dois tipos de planos de discagem:</span><span class="sxs-lookup"><span data-stu-id="16df8-709">Within the Phone System feature of Office 365, there are two types of dial plans:</span></span>

-   <span data-ttu-id="16df8-710">**Plano de discagem para serviço**.</span><span class="sxs-lookup"><span data-stu-id="16df8-710">**Service dial plan**.</span></span> <span data-ttu-id="16df8-711">Esse é o plano de discagem padrão, é aplicado aos usuários com base no local de uso do Office 365 e não pode ser modificado.</span><span class="sxs-lookup"><span data-stu-id="16df8-711">This is the default dial plan and applied to users based on Office 365 usage location, and it cannot be modified.</span></span>

<!-- -->

-   <span data-ttu-id="16df8-712">**Plano de discagem para locatários**.</span><span class="sxs-lookup"><span data-stu-id="16df8-712">**Tenant dial plan**.</span></span> <span data-ttu-id="16df8-713">Esse é um plano de discagem personalizável em um locatário e é dividido em mais dois tipos:</span><span class="sxs-lookup"><span data-stu-id="16df8-713">This is a customizable dial plan within a tenant, and further divided into two types:</span></span>

    -   <span data-ttu-id="16df8-714">**Plano de discagem para locatário global** – o plano de discagem se aplica para todos os usuários do locatário.</span><span class="sxs-lookup"><span data-stu-id="16df8-714">**Tenant-global dial plan**—the dial plan applies to all users within the tenant.</span></span>

    -   <span data-ttu-id="16df8-715">**Plano de discagem para locatário usuário** – o plano de discagem se aplica apenas a usuários específicos.</span><span class="sxs-lookup"><span data-stu-id="16df8-715">**Tenant-user dial plan**—the dial plan applies only to specific users.</span></span>


> [!NOTE]
> <span data-ttu-id="16df8-716">Confira a documentação dos [planos de discagem do Plano de Chamadas do Office 365](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) pata obter exemplos e mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="16df8-716">Check out the [Office 365 Calling Plan dial plans](https://support.office.com/article/What-are-PSTN-Calling-dial-plans-2f0cfb59-1ca1-4e31-84ce-09d0b1a7ce1b) documentation for further details and examples.</span></span>

<span data-ttu-id="16df8-717">O plano de discagem efetivo atribuído aos usuários é a combinação do plano de discagem para serviço (com base no local de uso do Office 365 do usuário) e do plano de discagem para locatários (que pode ser o plano de discagem para locatário global ou o plano de discagem para locatário usuário).</span><span class="sxs-lookup"><span data-stu-id="16df8-717">The effective dial plan assigned to users is the combination of service dial plan (based on user’s Office 365 usage location) and tenant dial plan (can be either tenant-global dial plan or tenant-user dial plan).</span></span>

![](media/audio_conferencing_image8.png)

<span data-ttu-id="16df8-718">Há um máximo de 25 regras de normalização em cada plano de discagem para locatários e, portanto, a duplicação das regras de normalização já disponíveis como parte do plano de discagem para serviço precisa ser evitada.</span><span class="sxs-lookup"><span data-stu-id="16df8-718">There is a maximum of 25 normalization rules in each tenant dial plan, and thus duplication with normalization rules already available as part of service dial plan needs to be avoided.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="16df8-719">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="16df8-719">Decision Points</span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-720">Decida se sua organização exigirá planos de discagem personalizados (requisitos de negócios, requisitos de adoção, etc.).</span><span class="sxs-lookup"><span data-stu-id="16df8-720">Decide if your organization requires customized dial plans (business requirements, adoption requirements, etc.).</span></span></li>
<li><span data-ttu-id="16df8-721">Se aplicável, decidir o escopo do plano de discagem para locatários (locatário global ou locatário usuário) para ter suporte para os requisitos dos planos de discagem personalizados.</span><span class="sxs-lookup"><span data-stu-id="16df8-721">If applicable, decide the scope of tenant dial plan (tenant-global or tenant-user) to support the requirements for customized dial plans.</span></span></li>
<li><span data-ttu-id="16df8-722">Se aplicável, decidir os planos de discagem para locatários que serão criados para oferecer suporte para locais de usuários ou escritórios que estejam no escopo de implementação da Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-722">If applicable, decide the tenant dial plans that will be created to support user locations or offices in-scope for the Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="16df8-723">Se aplicável, decidir qual usuário exigirá um plano de discagem personalizado e o plano de discagem para locatários a ser atribuído para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="16df8-723">If applicable, decide which user require customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="16df8-724">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="16df8-724">Next Steps</span></span></td>
<td align="left"><ul><li><span data-ttu-id="16df8-725">Documentar os planos de discagem personalizados e as regras de normalização associadas a serem configuradas como parte da implementação da Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-725">Document the customized dial plans and the associated normalization rules to be configured as part of Audio Conferencing implementation.</span></span></li>
<li><span data-ttu-id="16df8-726">Documentar os usuários aos quais serão atribuídos um plano de discagem personalizado e o plano de discagem para locatários a ser atribuído para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="16df8-726">Document the users to be assigned with customized dial plan and the tenant dial plan to be assigned for each user.</span></span></li></ul></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-727">Nome/descrição do plano de discagem para locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-727">Tenant Dial Plan Name/Description</span></span></th>
<th align="left"><span data-ttu-id="16df8-728">Nome/descrição das regras de normalização</span><span class="sxs-lookup"><span data-stu-id="16df8-728">Normalization Rules Name/Description</span></span></th>
<th align="left"><span data-ttu-id="16df8-729">Padrão</span><span class="sxs-lookup"><span data-stu-id="16df8-729">IPv6 Pattern</span></span></th>
<th align="left"><span data-ttu-id="16df8-730">Conversão</span><span class="sxs-lookup"><span data-stu-id="16df8-730">Translation</span></span></th>
<th align="left"><span data-ttu-id="16df8-731">IsInternalExtension</span><span class="sxs-lookup"><span data-stu-id="16df8-731">IsInternalExtension</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="16df8-732"><strong>AU-NSW-NorthRyde-OER</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-732"><strong>AU-NSW-NorthRyde-OER</strong></span></span></p>
<p><span data-ttu-id="16df8-733"><em>One Epping Road North Ryde, NSW, AU Dial Plan</em></span><span class="sxs-lookup"><span data-stu-id="16df8-733"><em>One Epping Road North Ryde, NSW, AU Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="16df8-734"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-734"><strong>AU-NSW-NorthRyde-OER-Internal</strong></span></span></p>
<p><span data-ttu-id="16df8-735"><em>Número interno (x7000 - x7999) para o escritório de One Epping Road, North Ryde, NSW, Austrália</em></span><span class="sxs-lookup"><span data-stu-id="16df8-735"><em>Internal number (x7000 - x7999) for One Epping Road office, North Ryde, NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="16df8-736">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="16df8-736">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="16df8-737">+6125550$1</span><span class="sxs-lookup"><span data-stu-id="16df8-737">+6125550$1</span></span></td>
<td align="left"><span data-ttu-id="16df8-738">True</span><span class="sxs-lookup"><span data-stu-id="16df8-738">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="16df8-739"><strong>AU-NSW-Local</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-739"><strong>AU-NSW-Local</strong></span></span></p>
<p><span data-ttu-id="16df8-740"><em>Normalização do número local para NSW, Austrália</em></span><span class="sxs-lookup"><span data-stu-id="16df8-740"><em>Local number normalization for NSW, Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="16df8-741">^([2-9]\d{7})$</span><span class="sxs-lookup"><span data-stu-id="16df8-741">^([2-9]\d{7})$</span></span></td>
<td align="left"><span data-ttu-id="16df8-742">+612$1</span><span class="sxs-lookup"><span data-stu-id="16df8-742">+612$1</span></span></td>
<td align="left"><span data-ttu-id="16df8-743">False</span><span class="sxs-lookup"><span data-stu-id="16df8-743">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="16df8-744"><strong>AU-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-744"><strong>AU-TollFree</strong></span></span></p>
<p><span data-ttu-id="16df8-745"><em>Normalização de número gratuito na Austrália</em></span><span class="sxs-lookup"><span data-stu-id="16df8-745"><em>Toll Free number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="16df8-746">^(1[38]\d{4,8})\d*$</span><span class="sxs-lookup"><span data-stu-id="16df8-746">^(1[38]\d{4,8})\d*$</span></span></td>
<td align="left"><span data-ttu-id="16df8-747">+61$1</span><span class="sxs-lookup"><span data-stu-id="16df8-747">+61$1</span></span></td>
<td align="left"><span data-ttu-id="16df8-748">False</span><span class="sxs-lookup"><span data-stu-id="16df8-748">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="16df8-749"><strong>AU-Service</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-749"><strong>AU-Service</strong></span></span></p>
<p><span data-ttu-id="16df8-750"><em>Normalização de número de serviço na Austrália</em></span><span class="sxs-lookup"><span data-stu-id="16df8-750"><em>Service number normalization for Australia</em></span></span></p></td>
<td align="left"><span data-ttu-id="16df8-751">^(000|1[0125]\d{1,8})$</span><span class="sxs-lookup"><span data-stu-id="16df8-751">^(000|1[0125]\d{1,8})$</span></span></td>
<td align="left"><span data-ttu-id="16df8-752">$1</span><span class="sxs-lookup"><span data-stu-id="16df8-752">$1</span></span></td>
<td align="left"><span data-ttu-id="16df8-753">False</span><span class="sxs-lookup"><span data-stu-id="16df8-753">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="16df8-754"><strong>SG-Singapore-OMB</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-754"><strong>SG-Singapore-OMB</strong></span></span></p>
<p><span data-ttu-id="16df8-755"><em>OMB Singapore, SG Dial Plan</em></span><span class="sxs-lookup"><span data-stu-id="16df8-755"><em>OMB Singapore, SG Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="16df8-756"><strong>SG-OMB-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-756"><strong>SG-OMB-Internal</strong></span></span></p>
<p><span data-ttu-id="16df8-757"><em>Número interno (x8000 – x8999) para o escritório OMB, Cingapura</em></span><span class="sxs-lookup"><span data-stu-id="16df8-757"><em>Internal number (x8000 – x8999) for OMB office, Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="16df8-758">^(8\d{3})$</span><span class="sxs-lookup"><span data-stu-id="16df8-758">^(8\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="16df8-759">+656888$1</span><span class="sxs-lookup"><span data-stu-id="16df8-759">+656888$1</span></span></td>
<td align="left"><span data-ttu-id="16df8-760">True</span><span class="sxs-lookup"><span data-stu-id="16df8-760">True</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="16df8-761"><strong>SG-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-761"><strong>SG-TollFree</strong></span></span></p>
<p><span data-ttu-id="16df8-762"><em>Normalização de número gratuito em Cingapura</em></span><span class="sxs-lookup"><span data-stu-id="16df8-762"><em>Toll Free number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="16df8-763">^(1?800\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="16df8-763">^(1?800\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="16df8-764">+65$1</span><span class="sxs-lookup"><span data-stu-id="16df8-764">+65$1</span></span></td>
<td align="left"><span data-ttu-id="16df8-765">False</span><span class="sxs-lookup"><span data-stu-id="16df8-765">False</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="16df8-766"><strong>SG-Service</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-766"><strong>SG-Service</strong></span></span></p>
<p><span data-ttu-id="16df8-767"><em>Normalização de número de serviço em Cingapura</em></span><span class="sxs-lookup"><span data-stu-id="16df8-767"><em>Service number normalization for Singapore</em></span></span></p></td>
<td align="left"><span data-ttu-id="16df8-768">^(1\d{3,4}|9\d{2})$</span><span class="sxs-lookup"><span data-stu-id="16df8-768">^(1\d{3,4}|9\d{2})$</span></span></td>
<td align="left"><span data-ttu-id="16df8-769">$1</span><span class="sxs-lookup"><span data-stu-id="16df8-769">$1</span></span></td>
<td align="left"><span data-ttu-id="16df8-770">False</span><span class="sxs-lookup"><span data-stu-id="16df8-770">False</span></span></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="16df8-771"><strong>FR-Paris-Issy-39qdPR</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-771"><strong>FR-Paris-Issy-39qdPR</strong></span></span></p>
<p><span data-ttu-id="16df8-772"><em>39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan</em></span><span class="sxs-lookup"><span data-stu-id="16df8-772"><em>39 quai du Président Roosevelt Issy-les-Moulineaux, France Dial Plan</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="16df8-773"><strong>FR-39qdPR-Internal</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-773"><strong>FR-39qdPR-Internal</strong></span></span></p>
<p><span data-ttu-id="16df8-774"><em>Número interno (x7000 – x7999) para o escritório de 39 quai du Président Roosevelt, Issy-les-Moulineaux, França</em></span><span class="sxs-lookup"><span data-stu-id="16df8-774"><em>Internal number (x7000 – x7999) for 39 quai du Président Roosevelt office, Issy-les-Moulineaux, France</em></span></span></p></td>
<td align="left"><span data-ttu-id="16df8-775">^(7\d{3})$</span><span class="sxs-lookup"><span data-stu-id="16df8-775">^(7\d{3})$</span></span></td>
<td align="left"><span data-ttu-id="16df8-776">+3319999$1</span><span class="sxs-lookup"><span data-stu-id="16df8-776">+3319999$1</span></span></td>
<td align="left"><span data-ttu-id="16df8-777">True</span><span class="sxs-lookup"><span data-stu-id="16df8-777">True</span></span></td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="16df8-778"><strong>FR-TollFree</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-778"><strong>FR-TollFree</strong></span></span></p>
<p><span data-ttu-id="16df8-779"><em>Normalização de número gratuito na França</em></span><span class="sxs-lookup"><span data-stu-id="16df8-779"><em>Toll Free number normalization for France</em></span></span></p></td>
<td align="left"><span data-ttu-id="16df8-780">^0?(80\d{7})\d*$</span><span class="sxs-lookup"><span data-stu-id="16df8-780">^0?(80\d{7})\d*$</span></span></td>
<td align="left"><span data-ttu-id="16df8-781">+33$1</span><span class="sxs-lookup"><span data-stu-id="16df8-781">+33$1</span></span></td>
<td align="left"><span data-ttu-id="16df8-782">False</span><span class="sxs-lookup"><span data-stu-id="16df8-782">False</span></span></td>
</tr>
<tr class="even">
<td align="left"></td>
<td align="left"><p><span data-ttu-id="16df8-783"><strong>FR-Service</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-783"><strong>FR-Service</strong></span></span></p>
<p><span data-ttu-id="16df8-784"><em>Normalização de número de serviço na França</em></span><span class="sxs-lookup"><span data-stu-id="16df8-784"><em>Service number normalization for France</em></span></span></p></td>
<td align="left"><p><span data-ttu-id="16df8-785">^(1\d{1,2}|11[68]\d{3}|</span><span class="sxs-lookup"><span data-stu-id="16df8-785">^(1\d{1,2}|11[68]\d{3}|</span></span></p>
<p><span data-ttu-id="16df8-786">10\d{2}|3\d{3})$</span><span class="sxs-lookup"><span data-stu-id="16df8-786">10\d{2}|3\d{3})$</span></span></p></td>
<td align="left"><span data-ttu-id="16df8-787">$1</span><span class="sxs-lookup"><span data-stu-id="16df8-787">$1</span></span></td>
<td align="left"><span data-ttu-id="16df8-788">False</span><span class="sxs-lookup"><span data-stu-id="16df8-788">False</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-789">_Tabela 13 Exemplo de planos de discagem para locatários_</span><span class="sxs-lookup"><span data-stu-id="16df8-789">_Table 13 Example of tenant dial plans_</span></span>


<table>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="16df8-790">Usuário</span><span class="sxs-lookup"><span data-stu-id="16df8-790">User</span></span></th>
<th align="left"><span data-ttu-id="16df8-791">Escritório</span><span class="sxs-lookup"><span data-stu-id="16df8-791">Office</span></span></th>
<th align="left"><span data-ttu-id="16df8-792">Tipo do plano de discagem</span><span class="sxs-lookup"><span data-stu-id="16df8-792">Dial Plan Type</span></span></th>
<th align="left"><span data-ttu-id="16df8-793">Nome do plano de discagem</span><span class="sxs-lookup"><span data-stu-id="16df8-793">Dial Plan Name</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-794">Adele Vance</span><span class="sxs-lookup"><span data-stu-id="16df8-794">Adele Vance</span></span></td>
<td align="left"><span data-ttu-id="16df8-795">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="16df8-795">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-796">Plano de discagem para locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-796">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-797">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="16df8-797">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-798">Alex Wilber</span><span class="sxs-lookup"><span data-stu-id="16df8-798">Alex Wilber</span></span></td>
<td align="left"><span data-ttu-id="16df8-799">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="16df8-799">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-800">Plano de discagem para locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-800">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-801">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="16df8-801">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-802">Ben Walters</span><span class="sxs-lookup"><span data-stu-id="16df8-802">Ben Walters</span></span></td>
<td align="left"><span data-ttu-id="16df8-803">One Epping Road</span><span class="sxs-lookup"><span data-stu-id="16df8-803">One Epping Road</span></span></td>
<td align="left"><span data-ttu-id="16df8-804">Plano de discagem para locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-804">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-805">AU-NSW-NorthRyde-OER</span><span class="sxs-lookup"><span data-stu-id="16df8-805">AU-NSW-NorthRyde-OER</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-806">Christie Cline</span><span class="sxs-lookup"><span data-stu-id="16df8-806">Christie Cline</span></span></td>
<td align="left"><span data-ttu-id="16df8-807">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="16df8-807">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="16df8-808">Plano de discagem para locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-808">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-809">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="16df8-809">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-810">Debra Berger</span><span class="sxs-lookup"><span data-stu-id="16df8-810">Debra Berger</span></span></td>
<td align="left"><span data-ttu-id="16df8-811">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="16df8-811">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="16df8-812">Plano de discagem para locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-812">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-813">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="16df8-813">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-814">Lee Gu</span><span class="sxs-lookup"><span data-stu-id="16df8-814">Lee Gu</span></span></td>
<td align="left"><span data-ttu-id="16df8-815">One Marina Boulevard</span><span class="sxs-lookup"><span data-stu-id="16df8-815">One Marina Boulevard</span></span></td>
<td align="left"><span data-ttu-id="16df8-816">Plano de discagem para locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-816">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-817">SG-Singapore-OMB</span><span class="sxs-lookup"><span data-stu-id="16df8-817">SG-Singapore-OMB</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-818">Emily Braun</span><span class="sxs-lookup"><span data-stu-id="16df8-818">Emily Braun</span></span></td>
<td align="left"><span data-ttu-id="16df8-819">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="16df8-819">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="16df8-820">Plano de discagem para serviço</span><span class="sxs-lookup"><span data-stu-id="16df8-820">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-821">N/A</span><span class="sxs-lookup"><span data-stu-id="16df8-821">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-822">Lidia Holloway</span><span class="sxs-lookup"><span data-stu-id="16df8-822">Lidia Holloway</span></span></td>
<td align="left"><span data-ttu-id="16df8-823">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="16df8-823">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="16df8-824">Plano de discagem para serviço</span><span class="sxs-lookup"><span data-stu-id="16df8-824">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-825">N/A</span><span class="sxs-lookup"><span data-stu-id="16df8-825">N/A</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-826">Pradeep Gupta</span><span class="sxs-lookup"><span data-stu-id="16df8-826">Pradeep Gupta</span></span></td>
<td align="left"><span data-ttu-id="16df8-827">32 London Bridge Street</span><span class="sxs-lookup"><span data-stu-id="16df8-827">32 London Bridge Street</span></span></td>
<td align="left"><span data-ttu-id="16df8-828">Plano de discagem para serviço</span><span class="sxs-lookup"><span data-stu-id="16df8-828">Service dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-829">N/A</span><span class="sxs-lookup"><span data-stu-id="16df8-829">N/A</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-830">Marcel Beauchamp</span><span class="sxs-lookup"><span data-stu-id="16df8-830">Marcel Beauchamp</span></span></td>
<td align="left"><span data-ttu-id="16df8-831">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="16df8-831">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="16df8-832">Plano de discagem para locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-832">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-833">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="16df8-833">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-834">Rachelle Cormier</span><span class="sxs-lookup"><span data-stu-id="16df8-834">Rachelle Cormier</span></span></td>
<td align="left"><span data-ttu-id="16df8-835">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="16df8-835">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="16df8-836">Plano de discagem para locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-836">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-837">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="16df8-837">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
<tr class="even">
<td align="left"><span data-ttu-id="16df8-838">Isabell Potvin</span><span class="sxs-lookup"><span data-stu-id="16df8-838">Isabell Potvin</span></span></td>
<td align="left"><span data-ttu-id="16df8-839">39 quai du Président Roosevelt</span><span class="sxs-lookup"><span data-stu-id="16df8-839">39 quai du Président Roosevelt</span></span></td>
<td align="left"><span data-ttu-id="16df8-840">Plano de discagem para locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-840">Tenant dial plan</span></span></td>
<td align="left"><span data-ttu-id="16df8-841">FR-Paris-Issy-39qdPR</span><span class="sxs-lookup"><span data-stu-id="16df8-841">FR-Paris-Issy-39qdPR</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-842">_Tabela 14 Exemplo de atribuições de planos de discagem_</span><span class="sxs-lookup"><span data-stu-id="16df8-842">_Table 14 Example of dial plan assignments_</span></span>


## <a name="microsoft-teams-configurations"></a><span data-ttu-id="16df8-843">Configurações do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16df8-843">Microsoft Teams configurations</span></span>

<span data-ttu-id="16df8-844">Uma vez que a Audioconferência está disponível apenas para reuniões agendadas, as configurações de nível de locatário que regem o agendamento de reuniões (reuniões privadas e de canal) devem estar habilitadas.</span><span class="sxs-lookup"><span data-stu-id="16df8-844">Since Audio Conferencing is only available for scheduled meetings, tenant-level configurations that govern meeting scheduling (private and channel meetings) must be enabled.</span></span>


> [!NOTE]
> <span data-ttu-id="16df8-845">No momento, se sua organização tiver exigências de conformidade para garantir que todas as discussões nas reuniões sejam detectáveis, é necessário desabilitar as reuniões privadas se o organizador tiver uma caixa de correio no Exchange.</span><span class="sxs-lookup"><span data-stu-id="16df8-845">Currently, if your organization has compliance requirements to ensure all meeting discussions are discoverable, you should disable private meetings if the organizer has an Exchange on-premises mailbox.</span></span><br><br>
> <span data-ttu-id="16df8-846">Em outro caso de uso, se todas as reuniões da organização tiverem que permanecer visíveis apenas <strong>para as partes convidadas</strong>, recomendamos que você desabilite a possibilidade de agendar reuniões nos <strong>canais</strong> para evitar a divulgação das informações da reunião para as partes que não foram convidadas.</span><span class="sxs-lookup"><span data-stu-id="16df8-846">In another use case, if all meetings in the organization must be visible <strong>to invited parties</strong> only, to avoid disclosing meeting information to uninvited parties, we recommend that you disable the ability to schedule meetings in <strong>channels</strong>.</span></span>

<span data-ttu-id="16df8-847">As configurações, disponíveis como configurações em nível de locatário, são aplicáveis para todos os usuários da organização e afetarão todas as reuniões agendadas no Teams, não especificamente as reuniões Teams **com** Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-847">The settings, available as tenant-level configurations, are applicable to all users in the organization, and will impact all meeting scheduling in Teams, not specific to Teams meetings **with** Audio Conferencing.</span></span>

<table>
<thead>
<tr class="header">
<td align="left"><img src="media/audio_conferencing_image7.png" /></td>
<td align="left"><span data-ttu-id="16df8-848">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="16df8-848">Policy Decision Point</span></span></td>
<td align="left"><p><span data-ttu-id="16df8-849">Decidir se a organização exigirá ativar ou desativar o agendamento de reuniões privadas.</span><span class="sxs-lookup"><span data-stu-id="16df8-849">Decide if the organization requires to enable or disable scheduling of private meetings.</span></span></p>
<p><span data-ttu-id="16df8-850">Decidir se a organização exigirá ativar ou desativar o agendamento de reuniões de canal.</span><span class="sxs-lookup"><span data-stu-id="16df8-850">Decide if the organization requires to enable or disable scheduling of channel meetings.</span></span></p></td>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="media/audio_conferencing_image9.png" /></td>
<td align="left"><span data-ttu-id="16df8-851">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="16df8-851">Next Steps</span></span></td>
<td align="left"><p><span data-ttu-id="16df8-852">Documentar as configurações de agendamento de reuniões para o Teams.</span><span class="sxs-lookup"><span data-stu-id="16df8-852">Document the meeting scheduling configurations for Teams.</span></span></p></td>
</tr>
</tbody>
</table>

<table>
<thead>
<tr class="header">
<td align="left"><span data-ttu-id="16df8-853"><strong>Permitir agendamento de reuniões privadas</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-853"><strong>Allow scheduling for private meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-854">Habilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-854">Enabled</span></span></td>
</tr>
</thead>
<thead>
<tr class="odd">
<td align="left"><span data-ttu-id="16df8-855"><strong>Permitir agendamento de reuniões de canal</strong></span><span class="sxs-lookup"><span data-stu-id="16df8-855"><strong>Allow scheduling for channel meetings</strong></span></span></td>
<td align="left"><span data-ttu-id="16df8-856">Desabilitado</span><span class="sxs-lookup"><span data-stu-id="16df8-856">Disabled.</span></span></td>
</tr>
</tbody>
</table>

<span data-ttu-id="16df8-857">_Tabela 15 Exemplo de configurações de reuniões Microsoft Teams_</span><span class="sxs-lookup"><span data-stu-id="16df8-857">_Table 15 Example of Microsoft Teams meetings configurations_</span></span>


## <a name="document-technical-implementation-plan"></a><span data-ttu-id="16df8-858">Documentar o plano de implementação técnica</span><span class="sxs-lookup"><span data-stu-id="16df8-858">Document technical implementation plan</span></span>

<span data-ttu-id="16df8-859">Utilizar os pontos de decisão acima para documentar o seu plano de implementação técnica.</span><span class="sxs-lookup"><span data-stu-id="16df8-859">Use the decision points above to document your technical implementation plan.</span></span>

<span data-ttu-id="16df8-860">Esse plano de implementação técnica fornecerá à equipe do projeto, que pode incluir o FastTrack ou um parceiro de implantação, as informações necessárias para executar a integração técnica para a implementação da Audioconferência.</span><span class="sxs-lookup"><span data-stu-id="16df8-860">This technical implementation plan will provide the project team, which can include FastTrack or a deployment partner, with the information required to execute the technical onboarding for the implementation of Audio Conferencing.</span></span>

<span data-ttu-id="16df8-861">No geral, um plano de implementação técnica deve conter as seguintes seções principais:</span><span class="sxs-lookup"><span data-stu-id="16df8-861">In general, a technical implementation plan will contain the following main sections:</span></span>

-   <span data-ttu-id="16df8-862">Lista de habilitação do site do serviço de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-862">Audio Conferencing service site enablement list</span></span>

-   <span data-ttu-id="16df8-863">Lista de atribuição de licenças para organizadores de reunião de Audioconferência</span><span class="sxs-lookup"><span data-stu-id="16df8-863">License assignment list for Audio Conferencing meeting organizers</span></span>

-   <span data-ttu-id="16df8-864">Número de planejamento de Créditos de Comunicação</span><span class="sxs-lookup"><span data-stu-id="16df8-864">Communications Credits planning numbers</span></span>

-   <span data-ttu-id="16df8-865">Detalhes de ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="16df8-865">Conference bridge details</span></span>

-   <span data-ttu-id="16df8-866">Configurações de ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="16df8-866">Conference bridge settings</span></span>

-   <span data-ttu-id="16df8-867">Atribuições das configurações de ponte de conferência</span><span class="sxs-lookup"><span data-stu-id="16df8-867">Conference bridge settings assignments</span></span>

-   <span data-ttu-id="16df8-868">Planos de discagem para locatários</span><span class="sxs-lookup"><span data-stu-id="16df8-868">Tenant dial plans</span></span>

-   <span data-ttu-id="16df8-869">Atribuições de planos de discagem</span><span class="sxs-lookup"><span data-stu-id="16df8-869">Dial plan assignments</span></span>

-   <span data-ttu-id="16df8-870">Configurações de reuniões Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="16df8-870">Microsoft Teams meetings configurations</span></span>

<span data-ttu-id="16df8-871">Com a conclusão do plano de sucesso e do plano de implementação técnica, agora você está pronto para conduzir a sua organização para as próximas etapas da jornada do cliente do Office 365.</span><span class="sxs-lookup"><span data-stu-id="16df8-871">With the completion of success plan and technical implementation plan, you are now ready to take your organization to the next steps along the Office 365 customer journey.</span></span>

<a name="onboard"></a><span data-ttu-id="16df8-872">Integração</span><span class="sxs-lookup"><span data-stu-id="16df8-872">Onboard</span></span>
=======

<span data-ttu-id="16df8-873">*Em breve.*</span><span class="sxs-lookup"><span data-stu-id="16df8-873">*Coming Soon*</span></span>

<a name="drive-value"></a><span data-ttu-id="16df8-874">Gerar valor</span><span class="sxs-lookup"><span data-stu-id="16df8-874">Drive Value</span></span>
===========

<span data-ttu-id="16df8-875">*Em breve.*</span><span class="sxs-lookup"><span data-stu-id="16df8-875">*Coming Soon*</span></span>



### <a name="see-also"></a><span data-ttu-id="16df8-876">Consulte também</span><span class="sxs-lookup"><span data-stu-id="16df8-876">See also</span></span>
[<span data-ttu-id="16df8-877">Configurar conferência PSTN ou de discagem para o Skype for Business</span><span class="sxs-lookup"><span data-stu-id="16df8-877">Set up dial-in or PSTN conferencing for Skype for Business</span></span>](https://support.office.com/article/Set-up-audio-conferencing-for-Skype-for-Business-and-Microsoft-Teams-d01954f1-4f37-4cf5-a636-20039e5c59e9)
