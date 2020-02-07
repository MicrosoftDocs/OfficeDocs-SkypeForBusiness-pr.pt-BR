---
title: Preparar para implantar os serviços de voz da nuvem do Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience: ITPro
ms.date: 03/18/2019
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Use as listas de verificação integradas para preparar o Office 365 para equipes e configurar as principais funcionalidades, redes e cargas de trabalho de voz na nuvem do teams.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 418496b5dd86fb9720393721854c0fcf68daf52a
ms.sourcegitcommit: bfa5b8db4e42e0480542d61fe05716c52016873c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41825139"
---
# <a name="prepare-my-service"></a><span data-ttu-id="7f5c9-103">Preparar meu serviço</span><span class="sxs-lookup"><span data-stu-id="7f5c9-103">Prepare my service</span></span>

<span data-ttu-id="7f5c9-104">Este artigo apresenta uma visão geral dos requisitos para a preparação dos serviços de voz em nuvem para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-104">This article gives an overview of the requirements for preparing cloud voice services for your organization.</span></span> <span data-ttu-id="7f5c9-105">Ao preparar-se corretamente, você pode ter certeza de que está pronto para fornecer recursos de voz na nuvem para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-105">By preparing properly, you can be sure you’re ready to provide cloud voice capabilities to your organization.</span></span>

## <a name="onboarding-checklists-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="7f5c9-106">Listas de verificação de integração para as cargas de trabalho de voz do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f5c9-106">Onboarding checklists for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="7f5c9-107">As listas de verificação a seguir orientam você pelas etapas para implementar a conferência de áudio, sistema telefônico com planos de chamada ("planos de chamada") e recursos de roteamento direto do sistema telefônico ("roteamento direto") no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-107">The following checklists walk you through the steps for implementing Audio Conferencing, Phone System with Calling Plans (“Calling Plans”), and Phone System Direct Routing (“Direct Routing”) capabilities in Microsoft Teams.</span></span>

*  [<span data-ttu-id="7f5c9-108">Preparar o Office 365 para Teams</span><span class="sxs-lookup"><span data-stu-id="7f5c9-108">Prepare Office 365 for Teams</span></span>](onboarding-checklist-enable-office-365.md)

*  [<span data-ttu-id="7f5c9-109">Configurar recursos essenciais do teams</span><span class="sxs-lookup"><span data-stu-id="7f5c9-109">Configure Teams core capabilities</span></span>](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)

*  [<span data-ttu-id="7f5c9-110">Configurar a rede</span><span class="sxs-lookup"><span data-stu-id="7f5c9-110">Configure networking</span></span>](onboarding-checklist-configure-networking.md)

*  [<span data-ttu-id="7f5c9-111">Configurar cargas de trabalho de voz na nuvem no Teams</span><span class="sxs-lookup"><span data-stu-id="7f5c9-111">Configure cloud voice workloads in Teams</span></span>](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)

*  [<span data-ttu-id="7f5c9-112">Configurar o roteamento direto no Teams</span><span class="sxs-lookup"><span data-stu-id="7f5c9-112">Configure Direct Routing in Teams</span></span>](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)

<span data-ttu-id="7f5c9-113">As tarefas e atividades nessas listas de verificação são itens principais que se aplicam a cada implantação de recursos de voz na nuvem com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-113">The tasks and activities in these checklists are the core “to-do” items that apply to every deployment of cloud voice capabilities with Teams.</span></span> <span data-ttu-id="7f5c9-114">Você pode personalizar as listas de verificação para incluir as atividades e tarefas específicas à sua viagem de equipes.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-114">You can customize the checklists to include the activities and tasks that are specific to your own Teams journey.</span></span>

>[!NOTE]
><span data-ttu-id="7f5c9-115">Esta orientação se concentra exclusivamente em planos de chamada, videoconferências e encaminhamento direto.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-115">This guidance focuses solely on Calling Plans, Audio Conferencing, and Direct Routing.</span></span> <span data-ttu-id="7f5c9-116">Se você não tem experiência com o Microsoft Teams, consulte [visão geral do Microsoft Teams](teams-overview.md).</span><span class="sxs-lookup"><span data-stu-id="7f5c9-116">If you’re new to Teams, review [Overview of Microsoft Teams](teams-overview.md).</span></span> <span data-ttu-id="7f5c9-117">Para obter orientação geral para planejar a implantação de suas equipes, comece com a [implantação de chat, equipes, canais e aplicativos no Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="7f5c9-117">For general guidance for planning your Teams deployment, start with [Deploy chat, teams, channels, and apps in Microsoft Teams](deploy-chat-teams-channels-microsoft-teams-landing-page.md).</span></span>

<span data-ttu-id="7f5c9-118">Use as listas de verificação fornecidas para acompanhar o status de cada atividade e tarefa individual e para ter certeza de que você não ignorou nenhuma etapa crítica.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-118">Use the provided checklists to track the status of each individual activity and task, and to be sure you haven’t skipped any critical steps.</span></span> <span data-ttu-id="7f5c9-119">Cada atividade inclui uma descrição detalhada das ações necessárias e referências a informações adicionais que você pode usar para concluir a atividade.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-119">Each activity includes a detailed description of required actions and references to additional information that you can use to complete that activity.</span></span>

<span data-ttu-id="7f5c9-120">Embora recomendemos que você siga as listas de verificação em ordem, a sequência exata dependerá do escopo da sua implantação e da configuração e da complexidade do seu ambiente.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-120">Although we recommend that you follow the checklists in order, the exact sequence will depend on the scope of your deployment and the configuration and complexity of your environment.</span></span> <span data-ttu-id="7f5c9-121">Elas são organizadas para dar suporte a uma implantação de equipes "greenfield" (uma sem presença anterior do Skype for Business online) ou migrar do Skype for Business online para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-121">They’re organized to support either a “greenfield” Teams deployment (one with no previous Skype for Business Online presence) or migrating from Skype for Business Online to Teams.</span></span> <span data-ttu-id="7f5c9-122">Se você estiver migrando do Skype for Business Online, talvez já tenha concluído algumas dessas atividades e poderá ignorá-las agora.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-122">If you’re migrating from Skype for Business Online, you might have already completed some of these activities and can ignore them now.</span></span>

<span data-ttu-id="7f5c9-123">Quando você estiver fazendo a integração de usuários de acordo com o site, é altamente recomendável usar o guia [de habilitação do site para voz (guia estratégico)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) como um guia complementar para essas listas de verificação.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-123">When you’re onboarding users on a per-site basis, we highly recommended that you use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) as a supplementary guide to these checklists.</span></span>

>[!NOTE]
><span data-ttu-id="7f5c9-124">A maioria das configurações de configuração é comum entre o Teams e o Skype for Business online.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-124">Most of the configuration settings are common between Teams and Skype for Business Online.</span></span> <span data-ttu-id="7f5c9-125">Você usa o centro de administração do Microsoft 365 e o centro de administração do Microsoft Teams para definir essas configurações.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-125">You use the Microsoft 365 Admin Center and Microsoft Teams admin center to configure those settings.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="7f5c9-126">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="7f5c9-126">Decision points</span></span></td><td><ul><li><span data-ttu-id="7f5c9-127">Quem será responsável por supervisionar a conclusão das listas de verificação de integração?</span><span class="sxs-lookup"><span data-stu-id="7f5c9-127">Who will be responsible for overseeing the completion of the onboarding checklists?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="7f5c9-128">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7f5c9-128">Next steps</span></span></td><td><ul><li><span data-ttu-id="7f5c9-129">Baixe as listas de verificação de integração.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-129">Download the onboarding checklists.</span></span></li><li><span data-ttu-id="7f5c9-130">Trabalhe nos itens da lista de verificação de integração, passo a passo, de acordo com o plano de implantação da sua organização.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-130">Work through the onboarding checklist items step-by-step in accordance with your organization’s deployment plan.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->

## <a name="continue-onboarding"></a><span data-ttu-id="7f5c9-131">Continuar a integração</span><span class="sxs-lookup"><span data-stu-id="7f5c9-131">Continue onboarding</span></span>

<span data-ttu-id="7f5c9-132">Depois de concluir essas listas de verificação, você terá adicionado recursos de voz com êxito à implantação do seu Teams.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-132">After you complete these checklists, you’ll have successfully added voice capabilities to your Teams deployment.</span></span>

<span data-ttu-id="7f5c9-133">Como a próxima etapa, use o [Guia do guia de capacitação de site para voz (guia estratégico)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para ajudá-lo a integrar seus usuários em cada site e ajudar a garantir que você planeje e execute atividades importantes específicas do site.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-133">As the next step, use the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) to help you onboard your users on each site, and help ensure that you plan and execute important site-specific activities.</span></span>

-   <span data-ttu-id="7f5c9-134">Plano de site pronto para distribuição de site</span><span class="sxs-lookup"><span data-stu-id="7f5c9-134">Ready Site by Site Rollout Plan</span></span>

-   <span data-ttu-id="7f5c9-135">Estabelecer processo de gerenciamento de serviços</span><span class="sxs-lookup"><span data-stu-id="7f5c9-135">Establish Service Management Process</span></span>

-   <span data-ttu-id="7f5c9-136">Executar testes e correções</span><span class="sxs-lookup"><span data-stu-id="7f5c9-136">Execute Testing and Remediation</span></span>

<!--ENDOFSECTION-->

## <a name="test-cloud-voice-workloads-in-teams"></a><span data-ttu-id="7f5c9-137">Testar cargas de trabalho de voz na nuvem no Teams</span><span class="sxs-lookup"><span data-stu-id="7f5c9-137">Test cloud voice workloads in Teams</span></span>

<span data-ttu-id="7f5c9-138">Depois de definir e documentar seus planos de sucesso e implementação de negócios de voz na nuvem da equipe como parte da fase enVision e fazer a configuração que você deseja no centro de administração, a próxima etapa é validar que a sua organização as expectativas e os requisitos são atendidos por meio do recurso, da funcionalidade e da usabilidade.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-138">After you’ve defined and documented your Teams cloud voice business success and technical implementation plans as part of the Envision phase and undertaken the configuration you want in the admin center, the next step is to validate that your organization’s expectations and requirements are met through feature, functionality, and usability.</span></span> <span data-ttu-id="7f5c9-139">Você deve executar esta etapa de validação antes de implantar uma implantação piloto ou final em seu ambiente de produção.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-139">You should perform this validation step before you deploy a pilot or final deployment in your production environment.</span></span>

<span data-ttu-id="7f5c9-140">Você pode aproveitar o plano de sucesso para empresas definido durante a fase do enVision para servir como base para determinar as atividades, expectativas, recursos/casos de teste de funcionalidade e escopo geral a serem avaliados durante a fase de teste.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-140">You can leverage the business success plan you defined during the Envision phase to serve as the basis for determining the activities, expectations, feature/functionality test cases, and overall scope to be evaluated during the testing phase.</span></span>

## <a name="define-your-testing-approach"></a><span data-ttu-id="7f5c9-141">Definir a abordagem de teste</span><span class="sxs-lookup"><span data-stu-id="7f5c9-141">Define your testing approach</span></span>

<span data-ttu-id="7f5c9-142">Em sua forma mais simples, a abordagem de teste baseia-se na revisão dos recursos de recursos da videoconferência, dos planos de chamada ou do serviço de roteamento direto e no desenvolvimento de um plano de teste para verificar se os seus requisitos de funcionalidade são atendidos para os usuários no escopo.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-142">In its simplest form, your testing approach is based on your reviewing the feature capabilities of the Audio Conferencing, Calling Plans, or Direct Routing service and developing a test plan to verify that your functionality requirements are met for users in scope.</span></span> <span data-ttu-id="7f5c9-143">Veja a seguir um exemplo de plano de teste para a fase onboard de uma implementação de áudio de audioconferência.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-143">The following is an example test plan for the Onboard phase of an audio conferencing implementation.</span></span>


| <span data-ttu-id="7f5c9-144">Recurso de conferência de áudio para testar</span><span class="sxs-lookup"><span data-stu-id="7f5c9-144">Audio Conferencing feature to test</span></span> | <span data-ttu-id="7f5c9-145">Resumo dos resultados</span><span class="sxs-lookup"><span data-stu-id="7f5c9-145">Results summary</span></span> | <span data-ttu-id="7f5c9-146">Anotações adicionais</span><span class="sxs-lookup"><span data-stu-id="7f5c9-146">Additional notes</span></span> |
|------------|-----------------|------------------|
| <span data-ttu-id="7f5c9-147">Agendar uma reunião de equipes ad hoc que contém informações de discagem de audioconferência</span><span class="sxs-lookup"><span data-stu-id="7f5c9-147">Schedule an ad-hoc Teams meeting that contains audio conferencing dial-in information</span></span> | <span data-ttu-id="7f5c9-148">Aprovado/reprovado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-148">Pass/Fail</span></span>   | <span data-ttu-id="7f5c9-149">A ser determinado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-149">TBD</span></span> |
| <span data-ttu-id="7f5c9-150">Usar um telefone para o áudio da reunião discando para uma reunião da PSTN com as informações de discagem fornecidas</span><span class="sxs-lookup"><span data-stu-id="7f5c9-150">Use a phone for meeting audio by dialing into a meeting from the PSTN with the dial-in information provided</span></span> | <span data-ttu-id="7f5c9-151">Aprovado/reprovado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-151">Pass/Fail</span></span> | <span data-ttu-id="7f5c9-152">A ser determinado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-152">TBD</span></span> |
| <span data-ttu-id="7f5c9-153">Ingressar em outras pessoas em uma reunião existente discando pela PSTN</span><span class="sxs-lookup"><span data-stu-id="7f5c9-153">Join other people to an existing meeting by dialing out via the PSTN</span></span> | <span data-ttu-id="7f5c9-154">Aprovado/reprovado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-154">Pass/Fail</span></span> | <span data-ttu-id="7f5c9-155">A ser determinado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-155">TBD</span></span> |



| <span data-ttu-id="7f5c9-156">Planos de chamada ou o recurso de roteamento direto para testar</span><span class="sxs-lookup"><span data-stu-id="7f5c9-156">Calling Plans or Direct Routing feature to test</span></span> | <span data-ttu-id="7f5c9-157">Resumo dos resultados</span><span class="sxs-lookup"><span data-stu-id="7f5c9-157">Results summary</span></span> | <span data-ttu-id="7f5c9-158">Anotações adicionais</span><span class="sxs-lookup"><span data-stu-id="7f5c9-158">Additional notes</span></span> |
|----------------------------------------------------|-----------------|------------------|
| <span data-ttu-id="7f5c9-159">Fazer uma chamada PSTN discando um número PSTN</span><span class="sxs-lookup"><span data-stu-id="7f5c9-159">Make a PSTN call by dialing a PSTN number</span></span>       | <span data-ttu-id="7f5c9-160">Aprovado/reprovado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-160">Pass/Fail</span></span>       | <span data-ttu-id="7f5c9-161">A ser determinado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-161">TBD</span></span> |
| <span data-ttu-id="7f5c9-162">Receber uma chamada PSTN discando o seu número PSTN de uma linha externa (móvel, telefone fixo)</span><span class="sxs-lookup"><span data-stu-id="7f5c9-162">Receive a PSTN call by dialing your PSTN number from an external line (mobile, landline)</span></span> | <span data-ttu-id="7f5c9-163">Aprovado/reprovado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-163">Pass/Fail</span></span> | <span data-ttu-id="7f5c9-164">A ser determinado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-164">TBD</span></span>|
| <span data-ttu-id="7f5c9-165">Transferir uma chamada PSTN de um usuário do teams para outro</span><span class="sxs-lookup"><span data-stu-id="7f5c9-165">Transfer a PSTN call from one Teams user to another</span></span> | <span data-ttu-id="7f5c9-166">Aprovado/reprovado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-166">Pass/Fail</span></span> | <span data-ttu-id="7f5c9-167">A ser determinado</span><span class="sxs-lookup"><span data-stu-id="7f5c9-167">TBD</span></span> |


>[!TIP]
><span data-ttu-id="7f5c9-168">Para ajudar a criação de casos de teste como ponto de partida, confira a lista de diretrizes do usuário disponível em [reuniões e chamadas do Microsoft Teams](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span><span class="sxs-lookup"><span data-stu-id="7f5c9-168">To assist with test-case creation as a starting point, see the list of user guidance available at [Teams Meetings and calls](https://support.office.com/article/Meetings-and-calls-d92432d5-dd0f-4d17-8f69-06096b6b48a8#bkmk_havingmeetings).</span></span>

<!--ENDOFSECTION-->

## <a name="set-up-cloud-voice-workloads-for-teams"></a><span data-ttu-id="7f5c9-169">Configurar cargas de trabalho de voz na nuvem para equipes</span><span class="sxs-lookup"><span data-stu-id="7f5c9-169">Set up cloud voice workloads for Teams</span></span>

<span data-ttu-id="7f5c9-170">Agora que você definiu a abordagem de teste, a próxima etapa é configurar seu ambiente de serviço e os usuários em escopo para recursos de voz na nuvem do teams.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-170">Now that you’ve defined your testing approach, the next step is configuring your service environment and users in scope for Teams cloud voice features.</span></span>

<span data-ttu-id="7f5c9-171">Para obter mais informações, consulte:</span><span class="sxs-lookup"><span data-stu-id="7f5c9-171">For additional information, see:</span></span>

- [<span data-ttu-id="7f5c9-172">Planejamento técnico da Audioconferência</span><span class="sxs-lookup"><span data-stu-id="7f5c9-172">Technical Planning for Audio Conferencing</span></span>](cloud-voice-deployment.md)

- [<span data-ttu-id="7f5c9-173">Configurar Audioconferência no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f5c9-173">Set up Audio Conferencing for Microsoft Teams</span></span>](set-up-audio-conferencing-in-teams.md)

- [<span data-ttu-id="7f5c9-174">Planejamento técnico para o sistema telefônico com planos de chamada</span><span class="sxs-lookup"><span data-stu-id="7f5c9-174">Technical Planning for Phone System with Calling Plans</span></span>](calling-plan-landing-page.md)

- [<span data-ttu-id="7f5c9-175">Configurar planos de chamadas para o Skype for Business e o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7f5c9-175">Set up Calling Plans for Skype for Business and Microsoft Teams</span></span>](https://docs.microsoft.com/skypeforbusiness/what-are-calling-plans-in-office-365/set-up-calling-plans)

- [<span data-ttu-id="7f5c9-176">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="7f5c9-176">Plan Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-plan)

- [<span data-ttu-id="7f5c9-177">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="7f5c9-177">Configure Direct Routing</span></span>](https://docs.microsoft.com/microsoftteams/direct-routing-configure)

### <a name="execute-the-test-plan"></a><span data-ttu-id="7f5c9-178">Executar o plano de teste</span><span class="sxs-lookup"><span data-stu-id="7f5c9-178">Execute the test plan</span></span>

[//]: # (Editar Ok? "Usuário" parecia um pouco ambíguo para mim.)
<span data-ttu-id="7f5c9-180">Após a configuração do ambiente do usuário e do serviço, a última etapa do teste inclui a execução do plano de teste com foco na validação de recursos e funcionalidades.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-180">After the user environment and the service have been configured, the last step of testing includes test plan execution with focus on feature and functionality validation.</span></span> 

<span data-ttu-id="7f5c9-181">**Pré-requisitos e Premissões de teste de áudio para usuários e sites em escopo:**</span><span class="sxs-lookup"><span data-stu-id="7f5c9-181">**Audio Conferencing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="7f5c9-182">Definição de caso de uso empresarial para o serviço de audioconferência foi concluída.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-182">Business use case definition for the Audio Conferencing service has been completed.</span></span>

-   <span data-ttu-id="7f5c9-183">O licenciamento necessário para a conferência de áudio está disponível e foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-183">Licensing required for Audio Conferencing is available and has been assigned.</span></span>

-   <span data-ttu-id="7f5c9-184">A lista de sites organizacionais e grupos de usuários foi identificada.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-184">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="7f5c9-185">A lista de números de discagem de conferência de áudio dedicada e compartilhada com a preferência de idioma foi identificada e configurada.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-185">The list of dedicated and shared audio conferencing dial in numbers with language preference have been identified and configured.</span></span>

-   <span data-ttu-id="7f5c9-186">[Créditos de comunicações](what-are-communications-credits.md) (se necessário) foram configurados para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-186">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="7f5c9-187">As configurações da ponte de conferência de áudio foram identificadas e configuradas (tamanho do pino, notificações de entrada/saída, preferência de notificação de habilitação).</span><span class="sxs-lookup"><span data-stu-id="7f5c9-187">Audio Conferencing conference bridge settings have been identified and configured (PIN length, entry/exit notifications, enablement notification preference).</span></span>

-   <span data-ttu-id="7f5c9-188">Políticas de conferência de locatários e configurações de plano de discagem que dão suporte a cenários de discagem de conferência de áudio foram identificadas, configuradas e aplicadas.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-188">Tenant conferencing policies and dial plan settings that support Audio Conferencing dial-out scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="7f5c9-189">Os requisitos de conformidade do Audio Conferencing foram identificados e configurados.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-189">Audio Conferencing compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="7f5c9-190">**Planos de chamada testando pré-requisitos e suposições para usuários e sites em escopo:**</span><span class="sxs-lookup"><span data-stu-id="7f5c9-190">**Calling Plans testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="7f5c9-191">Definição de caso de uso empresarial para o serviço de planos de chamada foi concluída.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-191">Business use case definition for the Calling Plans service has been completed.</span></span>

-   <span data-ttu-id="7f5c9-192">O licenciamento necessário para planos de chamada está disponível e foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-192">Licensing required for Calling Plans is available and has been assigned.</span></span>

-   <span data-ttu-id="7f5c9-193">A lista de sites organizacionais e grupos de usuários foi identificada.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-193">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="7f5c9-194">Os números de telefone a serem atribuídos aos usuários foram adquiridos ou portados para a Microsoft e estão disponíveis no portal de locatários.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-194">Phone numbers to be assigned to users have been acquired or ported to Microsoft and are available in the tenant portal.</span></span>

-   <span data-ttu-id="7f5c9-195">[Créditos de comunicações](what-are-communications-credits.md) (se necessário) foram configurados para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-195">[Communications Credits](what-are-communications-credits.md) (if required) have been set up for your organization.</span></span>

-   <span data-ttu-id="7f5c9-196">Políticas de usuário locatários e configurações de plano de discagem que dão suporte a cenários de planos de chamada foram identificadas, configuradas e aplicadas.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-196">Tenant user policies and dial plan settings that support Calling Plans scenarios have been identified, configured, and applied.</span></span>

-   <span data-ttu-id="7f5c9-197">Os requisitos de conformidade dos planos de chamada foram identificados e configurados.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-197">Calling Plans compliance requirements have been identified and configured.</span></span>

<span data-ttu-id="7f5c9-198">**Pré-requisitos e suposições de testes de roteamento direto para usuários e sites em escopo:**</span><span class="sxs-lookup"><span data-stu-id="7f5c9-198">**Direct Routing testing prerequisites and assumptions for users and sites in scope:**</span></span>

-   <span data-ttu-id="7f5c9-199">Definição de caso de uso empresarial para o serviço de roteamento direto foi concluída.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-199">Business use case definition for the Direct Routing service has been completed.</span></span>

-   <span data-ttu-id="7f5c9-200">O licenciamento necessário para roteamento direto está disponível e foi atribuído.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-200">Licensing required for Direct Routing is available and has been assigned.</span></span>

-   <span data-ttu-id="7f5c9-201">A lista de sites organizacionais e grupos de usuários foi identificada.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-201">The list of organizational sites and user groups have been identified.</span></span>

-   <span data-ttu-id="7f5c9-202">Um [SBC (controlador de borda de sessão) certificado (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) foi implantado, configurado e emparelhado com o sistema telefônico.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-202">A [certified session border controller (SBC)](https://docs.microsoft.com/microsoftteams/direct-routing-plan#supported-session-border-controllers-sbcs) has been deployed, configured and paired with Phone System.</span></span>

-   <span data-ttu-id="7f5c9-203">O Enterprise Voice foi habilitado e os números de telefone foram atribuídos.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-203">Enterprise voice has been enabled, and the phone numbers have been assigned.</span></span>

-   <span data-ttu-id="7f5c9-204">As políticas de roteamento de voz foram identificadas, configuradas e atribuídas.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-204">Voice routing policies have been identified, configured, and assigned.</span></span>

-   <span data-ttu-id="7f5c9-205">O Microsoft Teams foi definido como o cliente de chamada preferencial para os usuários no escopo.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-205">Microsoft Teams has been set as the preferred calling client for the users in scope.</span></span>
 
-   <span data-ttu-id="7f5c9-206">Os requisitos de conformidade de roteamento direto foram identificados e configurados.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-206">Direct Routing compliance requirements have been identified and configured.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="7f5c9-207">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="7f5c9-207">Decision points</span></span></td><td><ul><li><span data-ttu-id="7f5c9-208">Decidir quais recursos do recurso de audioconferência de áudio serão implantados (decisão do serviço).</span><span class="sxs-lookup"><span data-stu-id="7f5c9-208">Decide which Audio Conferencing feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="7f5c9-209">Identifique os requisitos de funcionalidade do usuário para videoconferência.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-209">Identify user functionality requirements for Audio Conferencing.</span></span></li><li><span data-ttu-id="7f5c9-210">Identifique os requisitos de configuração do serviço para videoconferência.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-210">Identify service configuration requirements for Audio Conferencing.</span></span></li><br><li><span data-ttu-id="7f5c9-211">Decida se o roteamento direto ou os planos de chamada serão implantados e configurados.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-211">Decide whether Direct Routing or Calling Plans will be deployed and configured.</span></span><li><span data-ttu-id="7f5c9-212">Decida quais recursos de recursos do sistema telefônico serão implantados (decisão de serviço).</span><span class="sxs-lookup"><span data-stu-id="7f5c9-212">Decide which Phone System feature capabilities will be deployed (service decision).</span></span></li><li><span data-ttu-id="7f5c9-213">Identifique os requisitos de funcionalidade do usuário para planos de chamada ou roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-213">Identify user functionality requirements for Calling Plans or Direct Routing.</span></span></li><li><span data-ttu-id="7f5c9-214">Identifique o requisito de configuração de serviço para planos de chamadas ou roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-214">Identify service configuration requirement for Calling Plans or Direct Routing.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="7f5c9-215">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="7f5c9-215">Next steps</span></span></td><td><ul><li><span data-ttu-id="7f5c9-216">Desenvolver e documentar a abordagem do plano de teste.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-216">Develop and document your test plan approach.</span></span></li><li><span data-ttu-id="7f5c9-217">Preparar o ambiente de serviço e os usuários em escopo para os recursos de videoconferência de áudio.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-217">Prepare your service environment and users in scope for Audio Conferencing features.</span></span></li><li><span data-ttu-id="7f5c9-218">Preparar o ambiente de serviço e os usuários em escopo para planos de chamadas ou recursos de roteamento direto.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-218">Prepare your service environment and users in scope for Calling Plans or Direct Routing features.</span></span></li><li><span data-ttu-id="7f5c9-219">Execute a validação de teste para os recursos de audioconferência que você deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-219">Execute test validation for the Audio Conferencing features that you want to enable.</span></span></li><li><span data-ttu-id="7f5c9-220">Execute a validação de teste para os planos de chamada ou os recursos de roteamento direto que você deseja habilitar.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-220">Execute test validation for the Calling Plans or Direct Routing features that you want to enable.</span></span></li><li><span data-ttu-id="7f5c9-221">Para qualquer falha de teste, confirme se a configuração está correta, examine os artigos da Comunidade e, se necessário, gere um caso de suporte.</span><span class="sxs-lookup"><span data-stu-id="7f5c9-221">For any test failures, confirm that your configuration is correct, review community articles, and—if required—raise a support case.</span></span></li></ul></td></tr>
</table>


<span data-ttu-id="7f5c9-222">Para obter orientações detalhadas adicionais sobre como executar testes de videoconferências no Microsoft Teams, consulte o [Guia de teste detalhado para videoconferências](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span><span class="sxs-lookup"><span data-stu-id="7f5c9-222">For additional detailed guidance on how to perform testing for Audio Conferencing in Teams, see the [detailed testing guide for Audio Conferencing](onboarding-test-plan-for-enterprises-Audio-Conferencing.md).</span></span>

<span data-ttu-id="7f5c9-223">Para obter orientações detalhadas adicionais sobre como executar o teste de planos de chamada no Microsoft Teams, consulte o [Guia de teste detalhado para o sistema telefônico](onboarding-test-plan-for-enterprises-Phone-System.md).</span><span class="sxs-lookup"><span data-stu-id="7f5c9-223">For additional detailed guidance on how to perform testing for Calling Plans in Teams, see the [detailed testing guide for Phone System](onboarding-test-plan-for-enterprises-Phone-System.md).</span></span>

<!--ENDOFSECTION-->
