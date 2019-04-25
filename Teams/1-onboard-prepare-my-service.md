---
title: Preparar para implantar os serviços de voz da nuvem do Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use as listas de verificação de inclusão preparar o Office 365 para equipes e configurar recursos principais de equipes, rede e cargas de trabalho de voz na nuvem.
localization_priority: Normal
MS.collection:
- Teams_ITAdmin_PracticalGuidance
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 886fb0d851112fbb76ca20aeb6b4c1b35e736757
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32241366"
---
# <a name="prepare-my-service"></a><span data-ttu-id="73862-103">Preparar meu serviço</span><span class="sxs-lookup"><span data-stu-id="73862-103">Prepare my service</span></span>

<span data-ttu-id="73862-104">Este artigo fornece uma visão geral dos requisitos de preparação dos serviços de voz para sua organização de nuvem.</span><span class="sxs-lookup"><span data-stu-id="73862-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="73862-105">Ao preparar-se adequadamente, você pode ser que você esteja pronto para fornecer recursos de voz para sua organização de nuvem.</span><span class="sxs-lookup"><span data-stu-id="73862-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="73862-106">Listas de verificação de inclusão for Microsoft Teams cargas de trabalho de voz</span><span class="sxs-lookup"><span data-stu-id="73862-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="73862-107">As listas de verificação a seguintes orientam você pelas etapas de implementação da conferência de áudio, o sistema telefônico com chamar planos ("chamar planos") e recursos do sistema direto roteamento de telefone ("direto roteamento") no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="73862-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="73862-108">Preparar o Office 365 para equipes</span><span class="sxs-lookup"><span data-stu-id="73862-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="73862-109">Configurar os principais recursos de equipes</span><span class="sxs-lookup"><span data-stu-id="73862-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="73862-110">Configurar a rede</span><span class="sxs-lookup"><span data-stu-id="73862-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="73862-111">Configurar as cargas de trabalho de voz de nuvem em equipes</span><span class="sxs-lookup"><span data-stu-id="73862-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="73862-112">Configurar o roteamento direta em equipes</span><span class="sxs-lookup"><span data-stu-id="73862-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="73862-113">As tarefas e atividades nestas listas de verificação são core "tarefas pendentes" itens que se aplicam a todas as implantações de recursos de voz com as equipes de nuvem.</span><span class="sxs-lookup"><span data-stu-id="73862-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="73862-114">Você pode personalizar as listas de verificação para incluir as atividades e tarefas que são específicas para sua própria jornada de equipes.</span><span class="sxs-lookup"><span data-stu-id="73862-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="73862-115">Estas diretrizes se concentra somente nos planos de chamada, conferência de áudio e roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="73862-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="73862-116">Se estiver familiarizado com as equipes, analise a [Visão geral das equipes da Microsoft](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="73862-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="73862-117">Para obter orientações gerais para planejar a implantação de equipes, comece com [Deploy chat, equipes, canais e aplicativos em equipes da Microsoft](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="73862-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="73862-118">Use as listas de verificação fornecidas para rastrear o status de cada atividade individual e a tarefa e ter a certeza de que você ainda não ignorados nenhuma etapa crítica.</span><span class="sxs-lookup"><span data-stu-id="73862-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="73862-119">Cada atividade inclui uma descrição detalhada de ações necessárias e referências para obter informações adicionais que você pode usar para concluir essa atividade.</span><span class="sxs-lookup"><span data-stu-id="73862-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="73862-120">Embora seja recomendável que você siga as listas de verificação em ordem, a sequência exata dependerá do escopo de sua implantação e a configuração e a complexidade do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="73862-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="73862-121">Eles estão organizados para dar suporte a qualquer um "em ambiente intacto" às equipes de implantação (com nenhum Skype anterior para presença Online de negócios um) ou a migração do Skype para Business Online para equipes.</span><span class="sxs-lookup"><span data-stu-id="73862-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="73862-122">Se você estiver migrando do Skype para Business Online, você talvez já tenha concluído algumas dessas atividades e ignorá-las agora.</span><span class="sxs-lookup"><span data-stu-id="73862-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="73862-123">Quando você estiver inclusão de usuários em uma base por site, é altamente recomendável que você use o [Site Playbook de habilitação para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como um guia suplementar estas listas de verificação.</span><span class="sxs-lookup"><span data-stu-id="73862-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="73862-124">A maioria das definições de configuração são comuns entre equipes e Skype para negócios Online.</span><span class="sxs-lookup"><span data-stu-id="73862-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="73862-125">Você pode usar o Centro de administração do Centro de administração do Office 365 e Teams da Microsoft para definir essas configurações.</span><span class="sxs-lookup"><span data-stu-id="73862-125">You use the Office 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="73862-126">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="73862-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="73862-127">Quem será responsável pela supervisão a conclusão das listas de inclusão de verificação?</span><span class="sxs-lookup"><span data-stu-id="73862-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="73862-128">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="73862-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="73862-129">Baixe as listas de verificação de inclusão.</span><span class="sxs-lookup"><span data-stu-id="73862-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="73862-130">Trabalhar através dos itens de lista de verificação de inclusão passo a passo de acordo com o plano de implantação da sua organização.</span><span class="sxs-lookup"><span data-stu-id="73862-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="73862-131">Continuar a inclusão</span><span class="sxs-lookup"><span data-stu-id="73862-131">Continue onboarding</span></span>

<span data-ttu-id="73862-132">Após concluir estas listas de verificação, você vai adicionou com êxito os recursos de voz à sua implantação de equipes.</span><span class="sxs-lookup"><span data-stu-id="73862-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="73862-133">Como a próxima etapa, use a [Guia estratégico de habilitação de Site para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ajudá-lo a seus usuários em cada site integrado e ajudar a garantir que você planejar e executar atividades importantes de específicas do site.</span><span class="sxs-lookup"><span data-stu-id="73862-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="73862-134">Plano de implementação de sites por pronto</span><span class="sxs-lookup"><span data-stu-id="73862-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="73862-135">Estabelecer o processo de gerenciamento de serviço</span><span class="sxs-lookup"><span data-stu-id="73862-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="73862-136">Executar o teste e remediação</span><span class="sxs-lookup"><span data-stu-id="73862-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="73862-137">Cargas de trabalho de voz nuvem de teste em equipes</span><span class="sxs-lookup"><span data-stu-id="73862-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="73862-138">Após você ter definido e documentado seu sucesso nos negócios equipes nuvem voz e planos de implementação técnica como parte da fase Envision e feita a configuração desejada no Centro de administração, a próxima etapa é validar que sua organização as expectativas e requisitos são atendidos por meio do recurso, a funcionalidade e usabilidade.</span><span class="sxs-lookup"><span data-stu-id="73862-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="73862-139">Você deve realizar esta etapa de validação antes de implantar uma implantação piloto ou final em seu ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="73862-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="73862-140">Você pode aproveitar o plano de sucesso de negócios que você definiu durante a fase de Envision para servir como base para determinar as atividades, as expectativas, casos de teste de funcionalidade do recurso e escopo geral a ser avaliada durante a fase de teste.</span><span class="sxs-lookup"><span data-stu-id="73862-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="73862-141">Definir sua abordagem de teste</span><span class="sxs-lookup"><span data-stu-id="73862-141">Define your testing approach</span></span>

<span data-ttu-id="73862-142">Na sua forma mais simples, sua abordagem do teste se baseia em sua revisar os recursos de conferências de áudio, chamar planos, ou plano de serviço de roteamento direto e desenvolvendo um teste verificar se os seus requisitos de funcionalidade foram atendidos para usuários no escopo.</span><span class="sxs-lookup"><span data-stu-id="73862-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="73862-143">A seguir está um plano de teste de exemplo para a fase de Onboard de uma implementação de serviços de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="73862-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="73862-144">Recurso de conferência de áudio para testar</span><span class="sxs-lookup"><span data-stu-id="73862-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="73862-145">Resumo dos resultados</span><span class="sxs-lookup"><span data-stu-id="73862-145">Results summary</span></span> | <span data-ttu-id="73862-146">Observações adicionais</span><span class="sxs-lookup"><span data-stu-id="73862-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="73862-147">Agendar uma reunião de equipes do ad-hoc que contém informações de discagem de conferência de áudio</span><span class="sxs-lookup"><span data-stu-id="73862-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="73862-148">Aprovação/reprovação</span><span class="sxs-lookup"><span data-stu-id="73862-148">Pass/Fail</span></span>   | <span data-ttu-id="73862-149">TBD</span><span class="sxs-lookup"><span data-stu-id="73862-149">TBD</span></span> |
| <span data-ttu-id="73862-150">Usar um telefone para áudio da reunião discando em uma reunião da PSTN com as informações de discagem fornecidas</span><span class="sxs-lookup"><span data-stu-id="73862-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="73862-151">Aprovação/reprovação</span><span class="sxs-lookup"><span data-stu-id="73862-151">Pass/Fail</span></span> | <span data-ttu-id="73862-152">TBD</span><span class="sxs-lookup"><span data-stu-id="73862-152">TBD</span></span> |
| <span data-ttu-id="73862-153">Ingressar em outras pessoas a uma reunião existente discando a eles através da PSTN</span><span class="sxs-lookup"><span data-stu-id="73862-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="73862-154">Aprovação/reprovação</span><span class="sxs-lookup"><span data-stu-id="73862-154">Pass/Fail</span></span> | <span data-ttu-id="73862-155">TBD</span><span class="sxs-lookup"><span data-stu-id="73862-155">TBD</span></span> |



| <span data-ttu-id="73862-156">Roteamento direto ou em chamada planos de recurso para testar</span><span class="sxs-lookup"><span data-stu-id="73862-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="73862-157">Resumo dos resultados</span><span class="sxs-lookup"><span data-stu-id="73862-157">Results summary</span></span> | <span data-ttu-id="73862-158">Observações adicionais</span><span class="sxs-lookup"><span data-stu-id="73862-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="73862-159">Fazer uma chamada PSTN, discando um número PSTN</span><span class="sxs-lookup"><span data-stu-id="73862-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="73862-160">Aprovação/reprovação</span><span class="sxs-lookup"><span data-stu-id="73862-160">Pass/Fail</span></span>       | <span data-ttu-id="73862-161">TBD</span><span class="sxs-lookup"><span data-stu-id="73862-161">TBD</span></span> |
| <span data-ttu-id="73862-162">Receber uma chamada PSTN discando o número do seu PSTN a partir de uma linha externa (linha fixa a móvel)</span><span class="sxs-lookup"><span data-stu-id="73862-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="73862-163">Aprovação/reprovação</span><span class="sxs-lookup"><span data-stu-id="73862-163">Pass/Fail</span></span> | <span data-ttu-id="73862-164">TBD</span><span class="sxs-lookup"><span data-stu-id="73862-164">TBD</span></span>|
| <span data-ttu-id="73862-165">Transferir uma chamada PSTN de um usuário de equipes para outro</span><span class="sxs-lookup"><span data-stu-id="73862-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="73862-166">Aprovação/reprovação</span><span class="sxs-lookup"><span data-stu-id="73862-166">Pass/Fail</span></span> | <span data-ttu-id="73862-167">TBD</span><span class="sxs-lookup"><span data-stu-id="73862-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="73862-168">Para auxiliar na criação de caso de teste como um ponto de partida, consulte a lista de usuário orientação disponível em [equipes reuniões e chamadas](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span><span class="sxs-lookup"><span data-stu-id="73862-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="73862-169">Configurar as cargas de trabalho de voz de nuvem para equipes</span><span class="sxs-lookup"><span data-stu-id="73862-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="73862-170">Agora que você definiu sua abordagem de teste, a próxima etapa é configurar o seu ambiente de serviço e os usuários no escopo para recursos de voz de nuvem de equipes.</span><span class="sxs-lookup"><span data-stu-id="73862-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="73862-171">Para obter informações adicionais, consulte:</span><span class="sxs-lookup"><span data-stu-id="73862-171">For additional information, see:</span></span>

- [<span data-ttu-id="73862-172">Planejamento técnico da Audioconferência</span><span class="sxs-lookup"><span data-stu-id="73862-172">Technical Planning for Audio Conferencing</span></span>](audio-conferencing.md#technical-planning-for-audio-conferencing)

- [<span data-ttu-id="73862-173">Configurar Audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73862-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="73862-174">Técnicas de planejamento para o sistema telefônico com a chamada de planos</span><span class="sxs-lookup"><span data-stu-id="73862-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="73862-175">Configure planos de chamar para Skype para negócios e Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="73862-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="73862-176">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="73862-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="73862-177">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="73862-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="73862-178">Executar o plano de teste</span><span class="sxs-lookup"><span data-stu-id="73862-178">Execute the test plan</span></span>

[//]: # (Editar okey? "Usuário" parecia um pouco ambíguo para mim.)
<span data-ttu-id="73862-180">Depois que o ambiente do usuário e o serviço tiverem sido configurados, a última etapa de teste inclui a execução de plano de teste com foco na validação de funcionalidade e recursos.</span><span class="sxs-lookup"><span data-stu-id="73862-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="73862-181">**Serviços de audioconferência testes pré-requisitos e suposições para sites e usuários no escopo:**</span><span class="sxs-lookup"><span data-stu-id="73862-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="73862-182">Negócios usar definição de maiusculas para a conferência de áudio serviço foi concluído.</span><span class="sxs-lookup"><span data-stu-id="73862-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="73862-183">Licenciamento necessários para conferência de áudio está disponível e foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="73862-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="73862-184">A lista de sites organizacionais e de grupos de usuários foram identificados.</span><span class="sxs-lookup"><span data-stu-id="73862-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="73862-185">A lista de serviços de audioconferência dedicado e compartilhado discar números com preferência de idioma foram identificados e configurados.</span><span class="sxs-lookup"><span data-stu-id="73862-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="73862-186">[Créditos de comunicações](what-are-communications-credits.md) (se necessário) tiverem sido configurados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="73862-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="73862-187">Configurações de ponte de conferência de áudio conferência foram identificados e configurado (tamanho do PIN, notificações de entrada/saída, preferência de notificação de habilitação).</span><span class="sxs-lookup"><span data-stu-id="73862-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="73862-188">Políticas de conferência de locatários e configurações que oferecem suporte a conferência de áudio cenários de discagem foram identificados, configurados e aplicados do plano de discagem.</span><span class="sxs-lookup"><span data-stu-id="73862-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="73862-189">Requisitos de conformidade de conferência de áudio foram identificados e configurados.</span><span class="sxs-lookup"><span data-stu-id="73862-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="73862-190">**Planos de testes de pré-requisitos e suposições para sites e usuários no escopo de chamada:**</span><span class="sxs-lookup"><span data-stu-id="73862-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="73862-191">Negócios usar definição de maiusculas para a chamada planos de serviço foi concluído.</span><span class="sxs-lookup"><span data-stu-id="73862-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="73862-192">Necessário para chamar planos de licenciamento está disponível e foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="73862-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="73862-193">A lista de sites organizacionais e de grupos de usuários foram identificados.</span><span class="sxs-lookup"><span data-stu-id="73862-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="73862-194">Números de telefone a ser atribuído aos usuários foram adquiridos ou migrados para o Microsoft e estão disponíveis no portal do inquilino.</span><span class="sxs-lookup"><span data-stu-id="73862-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="73862-195">[Créditos de comunicações](what-are-communications-credits.md) (se necessário) tiverem sido configurados para sua organização.</span><span class="sxs-lookup"><span data-stu-id="73862-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="73862-196">Diretivas de usuário de Inquilino e configurações de plano de discagem que fundamentam os cenários de planos de chamar foram identificadas, configuradas e aplicadas.</span><span class="sxs-lookup"><span data-stu-id="73862-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="73862-197">Chamando planos de requisitos de conformidade foram identificados e configurados.</span><span class="sxs-lookup"><span data-stu-id="73862-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="73862-198">**Testes de pré-requisitos e suposições para sites e usuários no escopo de roteamento direto:**</span><span class="sxs-lookup"><span data-stu-id="73862-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="73862-199">Negócios usar definição de maiusculas para o roteamento direto serviço foi concluído.</span><span class="sxs-lookup"><span data-stu-id="73862-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="73862-200">Licenciamento necessários para roteamento direto está disponível e foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="73862-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="73862-201">A lista de sites organizacionais e de grupos de usuários foram identificados.</span><span class="sxs-lookup"><span data-stu-id="73862-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="73862-202">Um [certificado do controlador de borda de sessão (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) tenha sido implantado, configurado e juntamente com o sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="73862-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="73862-203">Voz empresarial tiver sido habilitada e os números de telefone que tiverem sido atribuídos.</span><span class="sxs-lookup"><span data-stu-id="73862-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="73862-204">Políticas de roteamento de voz foram identificadas, configuradas e atribuídas.</span><span class="sxs-lookup"><span data-stu-id="73862-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="73862-205">Microsoft Teams tiver sido definida como o cliente de chamada preferencial para os usuários no escopo.</span><span class="sxs-lookup"><span data-stu-id="73862-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="73862-206">Requisitos de conformidade de roteamento diretos foram identificados e configurados.</span><span class="sxs-lookup"><span data-stu-id="73862-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt=""/> <br/><span data-ttu-id="73862-207">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="73862-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="73862-208">Decida quais recursos do recurso de conferência de áudio serão implantados (decisão de serviço).</span><span class="sxs-lookup"><span data-stu-id="73862-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="73862-209">Identifique os requisitos de funcionalidade do usuário para conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="73862-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="73862-210">Identifique os requisitos de configuração do serviço de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="73862-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="73862-211">Decida se roteamento direto ou chamar planos serão implantados e configurados.</span><span class="sxs-lookup"><span data-stu-id="73862-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="73862-212">Decida quais recursos do sistema telefônico serão implantados (decisão de serviço).</span><span class="sxs-lookup"><span data-stu-id="73862-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="73862-213">Identifique os requisitos de funcionalidade do usuário para planos de chamar ou roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="73862-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="73862-214">Identifique o requisito de configuração de serviço para planos de chamar ou roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="73862-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt=""/><br/><span data-ttu-id="73862-215">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="73862-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="73862-216">Desenvolver e documentar sua abordagem de plano de teste.</span><span class="sxs-lookup"><span data-stu-id="73862-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="73862-217">Prepare seu ambiente de serviço e os usuários no escopo de recursos de conferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="73862-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="73862-218">Prepare seu ambiente de serviço e os usuários no escopo para recursos de roteamento direto ou em planos de chamada.</span><span class="sxs-lookup"><span data-stu-id="73862-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="73862-219">Execute o teste de validação para os recursos de conferência de áudio que você deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="73862-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="73862-220">Execute o teste de validação para os recursos de roteamento direto ou em planos de chamada que você deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="73862-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="73862-221">Para qualquer falhas de teste, confirme se sua configuração está correta, analise os artigos de comunidade, e — se for necessário — elevar um caso de suporte.</span><span class="sxs-lookup"><span data-stu-id="73862-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="73862-222">Para obter orientações detalhadas adicionais sobre como executar o teste para conferência de áudio em equipes, consulte o [detalhadas testando guia para conferência de áudio](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="73862-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="73862-223">Para obter orientações detalhadas adicionais sobre como executar o teste chamar planos em equipes, consulte o [detalhadas testando guia para o sistema telefônico](onboarding-test-plan-for-enterprises-Phone-System.md).</span><span class="sxs-lookup"><span data-stu-id="73862-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
