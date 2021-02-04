---
title: Teams para visitas virtuais
author: cichur
ms.author: v-cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
searchScope:
- Microsoft Teams
- Microsoft Cloud for Healthcare
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-collaboration
- Teams_ITAdmin_Healthcare
- microsoftcloud-healthcare
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Usar o Microsoft Teams para configurar seu sistema de visitas virtuais
ms.openlocfilehash: 4c8511939532a448d5229865618aa308494c7a42
ms.sourcegitcommit: 4bf85d91befb56566130731198518c103a53ebc4
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2021
ms.locfileid: "50101329"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="81df3-103">Visitas virtuais com o Teams-integração ao EHR</span><span class="sxs-lookup"><span data-stu-id="81df3-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="81df3-104">O conector do Microsoft Teams Electronic Health Record (EHR) facilita para os clínicos iniciarem uma visita ou consultoria do paciente virtual com outro provedor no Teams diretamente do sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="81df3-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="81df3-105">Baseado na nuvem do Microsoft 365, o Microsoft Teams permite colaboração simples e segura e comunicação com as ferramentas de chat, vídeo, voz e saúde em um único Hub compatível com a HIPAA, a certificação de alta tecnologia e muito mais.</span><span class="sxs-lookup"><span data-stu-id="81df3-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="81df3-106">A plataforma de comunicação e colaboração de equipes torna mais fácil para os clínicos reduzirem o truncamento dos sistemas fragmentados para que possam perder tempo oferecendo o melhor cuidado possível.</span><span class="sxs-lookup"><span data-stu-id="81df3-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="81df3-107">O conector EHR (Microsoft Teams Electronic Health Record) pode:</span><span class="sxs-lookup"><span data-stu-id="81df3-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>
- <span data-ttu-id="81df3-108">Inicie visitas virtuais do teams de provedores e portais de pacientes.</span><span class="sxs-lookup"><span data-stu-id="81df3-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="81df3-109">Escreva novamente em metadados do EHR em eventos de conexão e desconexão para habilitar a auditoria automática e a manutenção de registros.</span><span class="sxs-lookup"><span data-stu-id="81df3-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="81df3-110">Integre-se a fluxos de trabalho clínicos e de pacientes existentes, permitindo que eles usem o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81df3-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="81df3-111">Assista ao vídeo sobre como gerenciar visitas virtuais no portal EHR.</span><span class="sxs-lookup"><span data-stu-id="81df3-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="81df3-112">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="81df3-112">Before you begin</span></span>

<span data-ttu-id="81df3-113">Você precisará certificar-se de ter os seguintes pré-requisitos antes de integrar o conector EHR:</span><span class="sxs-lookup"><span data-stu-id="81df3-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="81df3-114">Acesso a ser usado para o aplicativo Microsoft Teams no [aplicativo do testamento do pomar Marketplace](https://apporchard.epic.com/Gallery?id=6153).</span><span class="sxs-lookup"><span data-stu-id="81df3-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="81df3-115">Assinatura ativa para o Microsoft Cloud para assistência médica ou assinatura para a oferta autônoma do conector do Microsoft Teams EHR (imposta apenas durante testes de produção).</span><span class="sxs-lookup"><span data-stu-id="81df3-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="81df3-116">Os usuários devem ter uma licença do Microsoft 365 ou do Office 365 apropriada que inclua reuniões do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81df3-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="81df3-117">O Microsoft Teams deve ser adotado e usado dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="81df3-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="81df3-118">As organizações devem ter a versão testamento de novembro de 2018 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="81df3-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="81df3-119">Seus sistemas devem atender todos os [pré-requisitos do software e do navegador](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="81df3-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="81df3-120">Você também precisará de informações das seguintes pessoas em sua organização:</span><span class="sxs-lookup"><span data-stu-id="81df3-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="81df3-121">Administrador do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="81df3-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="81df3-122">Analista do cliente testamento</span><span class="sxs-lookup"><span data-stu-id="81df3-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="81df3-123">Solicite seu especialista técnico do testamento para fornecer o guia de integração de teleintegridade do teams Epic-Microsoft disponível no testamento Marketplace.</span><span class="sxs-lookup"><span data-stu-id="81df3-123">Request your Epic technical specialist to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="81df3-124">Configuração do conector</span><span class="sxs-lookup"><span data-stu-id="81df3-124">Connector setup</span></span>

<span data-ttu-id="81df3-125">A instalação do conector exige que você:</span><span class="sxs-lookup"><span data-stu-id="81df3-125">The connector setup requires that you:</span></span>

- [<span data-ttu-id="81df3-126">Iniciar o portal de configuração do conector EHR</span><span class="sxs-lookup"><span data-stu-id="81df3-126">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="81df3-127">Informações de configuração</span><span class="sxs-lookup"><span data-stu-id="81df3-127">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="81df3-128">Aprovar ou exibir configuração</span><span class="sxs-lookup"><span data-stu-id="81df3-128">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="81df3-129">Revisar e concluir a configuração</span><span class="sxs-lookup"><span data-stu-id="81df3-129">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="81df3-130">Iniciar o portal de configuração do conector EHR</span><span class="sxs-lookup"><span data-stu-id="81df3-130">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="81df3-131">Configurar sua organização de assistência médica para iniciar visitas virtuais com o Microsoft Teams inicia iniciando o portal de configuração do conector EHR.</span><span class="sxs-lookup"><span data-stu-id="81df3-131">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="81df3-132">Você configura uma única ou várias organizações para testar a integração.</span><span class="sxs-lookup"><span data-stu-id="81df3-132">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="81df3-133">Configure o teste e a URL de produção no portal de configuração.</span><span class="sxs-lookup"><span data-stu-id="81df3-133">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="81df3-134">Teste a integração do ambiente de teste do testamento antes de migrar para produção.</span><span class="sxs-lookup"><span data-stu-id="81df3-134">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="81df3-135">URL de configuração do conector EHR: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="81df3-135">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="81df3-136">O testamento de administração do Microsoft 365 e o analista do cliente da sua organização devem completar as etapas de integração e informações no portal de configuração.</span><span class="sxs-lookup"><span data-stu-id="81df3-136">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="81df3-137">Para ver as etapas de configuração do testamento, entre em contato com o recurso de especialista técnico do testamento atribuído à sua organização.</span><span class="sxs-lookup"><span data-stu-id="81df3-137">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="81df3-138">Informações de configuração</span><span class="sxs-lookup"><span data-stu-id="81df3-138">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="81df3-139">Esta etapa deve ser concluída pelo administrador do **Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="81df3-139">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="81df3-140">O administrador do Microsoft 365 deve iniciar o portal de configuração do conector e entrar com as credenciais da Microsoft para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="81df3-140">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="81df3-141">Para concluir esta etapa, o administrador do Microsoft 365 deve receber uma URL base válida dos recursos de interoperabilidade de integridade rápida (FHIR) do seu especialista técnico do testamento e do nome de usuário do analista do cliente do testamento, que aprovará a configuração.</span><span class="sxs-lookup"><span data-stu-id="81df3-141">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="81df3-142">O administrador do Microsoft 365 deve iniciar a página de configuração do conector e entrar com as credenciais da Microsoft para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="81df3-142">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="81df3-143">A URL base FHIR é um endereço estático correspondente ao seu servidor de ponto de extremidade de API do FHIR.</span><span class="sxs-lookup"><span data-stu-id="81df3-143">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="81df3-144">Um exemplo de URL é `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` .</span><span class="sxs-lookup"><span data-stu-id="81df3-144">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="81df3-145">Nome do aprovador de configuração é o nome do analista do cliente do testamento que será responsável por aprovar a configuração na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="81df3-145">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="81df3-146">O analista do cliente do testamento é uma pessoa em sua organização com acesso de entrada ao testamento.</span><span class="sxs-lookup"><span data-stu-id="81df3-146">The Epic customer analyst is a person in your organization with signin access to Epic.</span></span>

  ![O nome do aprovador de configuração é selecionado em uma lista no conector EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="81df3-148">Aprovar ou exibir configuração</span><span class="sxs-lookup"><span data-stu-id="81df3-148">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="81df3-149">O analista do cliente testamento da sua organização de assistência médica que foi adicionado como Aprovador agora deve usar a mesma URL do conector EHR da etapa anterior para entrar usando as credenciais do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="81df3-149">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="81df3-150">Após a validação bem-sucedida, o aprovador será solicitado a entrar usando suas credenciais do testamento para validar a organização do testamento.</span><span class="sxs-lookup"><span data-stu-id="81df3-150">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="81df3-151">O administrador do Microsoft 365 e o analista do cliente do testamento em sua organização podem ser a mesma pessoa.</span><span class="sxs-lookup"><span data-stu-id="81df3-151">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="81df3-152">Nesse caso, adicione seu próprio nome de usuário como Aprovador.</span><span class="sxs-lookup"><span data-stu-id="81df3-152">In that case, add your own username as approver.</span></span> <span data-ttu-id="81df3-153">Você ainda precisa entrar no testamento para validar seu acesso.</span><span class="sxs-lookup"><span data-stu-id="81df3-153">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="81df3-154">O testamento entrar é usado apenas para validar a URL base do FHIR.</span><span class="sxs-lookup"><span data-stu-id="81df3-154">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="81df3-155">A Microsoft não armazenará credenciais nem acessará dados do EHR com esta entrada.</span><span class="sxs-lookup"><span data-stu-id="81df3-155">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Verificar e aprovar a configuração de credenciais.](../../media/approve-view-configuration.png)

<span data-ttu-id="81df3-157">Após uma testamento de entrada bem-sucedida, o analista do cliente do testamento **deve** aprovar a configuração.</span><span class="sxs-lookup"><span data-stu-id="81df3-157">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="81df3-158">Se a configuração não estiver correta, o administrador do Microsoft 365 terá a capacidade de modificar as configurações originais entrando no portal do conector do EHR da Microsoft novamente.</span><span class="sxs-lookup"><span data-stu-id="81df3-158">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Confirme se o conector EHR está configurado e opção para alterar a configuração.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="81df3-160">Revisar e concluir a configuração</span><span class="sxs-lookup"><span data-stu-id="81df3-160">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="81df3-161">Quando as informações de configuração forem aprovadas pelo administrador do testamento, você será apresentado aos registros de integração do lançamento de pacientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="81df3-161">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="81df3-162">Esses registros são necessários para concluir a configuração de visita virtual no testamento.</span><span class="sxs-lookup"><span data-stu-id="81df3-162">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="81df3-163">Para obter mais detalhes, consulte o guia de integração do Epic-Microsoft Teams telehealth.</span><span class="sxs-lookup"><span data-stu-id="81df3-163">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="81df3-164">A qualquer momento, o analista do cliente do Microsoft 365 ou do testamento pode entrar no portal de configuração para ver os registros de integração e modificar a configuração da organização, se necessário.</span><span class="sxs-lookup"><span data-stu-id="81df3-164">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![As informações de integração são exibidas.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="81df3-166">O processo de aprovação deve ser concluído pelo analista do cliente do testamento para cada URL FHIR configurada pelo Microsoft admin antes.</span><span class="sxs-lookup"><span data-stu-id="81df3-166">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![As informações de configuração são aprovadas.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="81df3-168">Iniciar visitas virtuais ao Teams</span><span class="sxs-lookup"><span data-stu-id="81df3-168">Launch Teams virtual visits</span></span>

<span data-ttu-id="81df3-169">Depois de concluir as etapas do conector EHR e a configuração do testamento, sua organização está pronta para dar suporte a visitas com vídeo com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81df3-169">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="81df3-170">Pré-requisitos de visita virtual</span><span class="sxs-lookup"><span data-stu-id="81df3-170">Virtual visit prerequisites</span></span>

- <span data-ttu-id="81df3-171">Seus sistemas devem atender todos os [pré-requisitos do software e do navegador](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="81df3-171">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="81df3-172">A organização de assistência médica deve ter concluído a configuração entre a organização do testamento e a organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="81df3-172">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="81df3-173">Experiência do provedor</span><span class="sxs-lookup"><span data-stu-id="81df3-173">Provider experience</span></span>

<span data-ttu-id="81df3-174">Provedores de assistência médica da sua organização também podem ingressar em visitas virtuais ao Microsoft Teams de seus aplicativos de provedor de Testamento (hiperespacial, Haiku, canto).</span><span class="sxs-lookup"><span data-stu-id="81df3-174">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="81df3-175">O botão **Iniciar visita virtual** é inserido no fluxo do provedor.</span><span class="sxs-lookup"><span data-stu-id="81df3-175">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="81df3-176">Principais recursos da experiência do provedor:</span><span class="sxs-lookup"><span data-stu-id="81df3-176">Key features of the provider experience:</span></span>

- <span data-ttu-id="81df3-177">Provedores podem ingressar em visitas virtuais usando navegadores com suporte ou o aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81df3-177">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="81df3-178">Os provedores devem fazer um logon único com sua conta do Microsoft 365 ao ingressar em uma visita virtual pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="81df3-178">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="81df3-179">Após o logon único, o provedor será levado diretamente ao compromisso virtual no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="81df3-179">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="81df3-180">(O provedor deve estar conectado ao Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="81df3-180">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="81df3-181">O provedor pode ver atualizações em tempo real dos participantes se conectam e se desconectam de um determinado compromisso.</span><span class="sxs-lookup"><span data-stu-id="81df3-181">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="81df3-182">O provedor pode ver quando o paciente está conectado a uma visita virtual.</span><span class="sxs-lookup"><span data-stu-id="81df3-182">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Experiência do provedor de uma visita virtual com o paciente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="81df3-184">Experiência do paciente</span><span class="sxs-lookup"><span data-stu-id="81df3-184">Patient experience</span></span>

<span data-ttu-id="81df3-185">O conector dá suporte a pacientes que ingressam em visitas virtuais por meio de myChart Web e Mobile.</span><span class="sxs-lookup"><span data-stu-id="81df3-185">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="81df3-186">No momento do compromisso, os pacientes podem iniciar uma visita virtual em mycharting usando o botão **Iniciar visita virtual** .</span><span class="sxs-lookup"><span data-stu-id="81df3-186">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="81df3-187">Principais recursos da experiência do paciente:</span><span class="sxs-lookup"><span data-stu-id="81df3-187">Key features of the patient experience:</span></span>

- <span data-ttu-id="81df3-188">Os pacientes podem ingressar em visitas virtuais de navegadores modernos na área de trabalho e dispositivos móveis sem a instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="81df3-188">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="81df3-189">Os pacientes podem ingressar em visitas virtuais com um único clique, e não há outra conta ou conexão necessária.</span><span class="sxs-lookup"><span data-stu-id="81df3-189">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="81df3-190">Não é necessário ter pacientes para criar uma conta da Microsoft ou entrar para iniciar uma visita virtual.</span><span class="sxs-lookup"><span data-stu-id="81df3-190">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="81df3-191">Os pacientes serão colocados em um lobby até que o provedor de assistência médica ingresse no compromisso e os inscreva para a visita virtual.</span><span class="sxs-lookup"><span data-stu-id="81df3-191">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="81df3-192">O teste do vídeo e do microfone está disponível no lobby antes de ingressar na visita virtual.</span><span class="sxs-lookup"><span data-stu-id="81df3-192">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Experiência de paciente da visita virtual](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="81df3-194">Testamento, myChart, Haiku e canto são marcas comerciais da testamento Systems Corporation.</span><span class="sxs-lookup"><span data-stu-id="81df3-194">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="81df3-195">Privacidade e localização de dados</span><span class="sxs-lookup"><span data-stu-id="81df3-195">Privacy and location of data</span></span>

<span data-ttu-id="81df3-196">A integração de equipes em sistemas EHR otimiza a quantidade de dados que estão sendo usados e armazenados durante os fluxos de visita e de integração virtual.</span><span class="sxs-lookup"><span data-stu-id="81df3-196">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="81df3-197">A solução segue os princípios e as diretrizes gerais de privacidade e gerenciamento de dados da equipe descritos na privacidade da equipe.</span><span class="sxs-lookup"><span data-stu-id="81df3-197">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="81df3-198">O conector EHR do Microsoft Teams não armazena nem transfere nenhum dado pessoal identificável ou quaisquer registros de integridade de pacientes ou provedores de assistência médica do sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="81df3-198">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="81df3-199">Os únicos dados armazenados pelo conector EHR é a ID exclusiva do usuário do EHR, que é usada durante a configuração da reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="81df3-199">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="81df3-200">A ID exclusiva do usuário do EHR é armazenada em uma das três regiões geográficas descritas [onde seus dados do cliente do Microsoft 365 são armazenados](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span><span class="sxs-lookup"><span data-stu-id="81df3-200">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="81df3-201">Todas as mensagens de chat, gravações e outros dados inseridos no Teams pelos participantes da reunião são armazenados de acordo com as políticas de armazenamento existentes.</span><span class="sxs-lookup"><span data-stu-id="81df3-201">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="81df3-202">Se você quiser saber mais sobre o local dos dados no Microsoft Teams, acesse [locais de dados no Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span><span class="sxs-lookup"><span data-stu-id="81df3-202">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
