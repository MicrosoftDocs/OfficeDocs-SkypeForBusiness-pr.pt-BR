---
title: Teams para Visitas virtuais
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
- m365solution-healthcare
- m365solution-scenario
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Usar o Microsoft Teams para configurar seu Sistema de visitas virtuais
ms.openlocfilehash: 37b93533aeff6b519b1f5a65cf49211464b41388
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51096275"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="75097-103">Visitas virtuais com o Teams - Integração com EHR</span><span class="sxs-lookup"><span data-stu-id="75097-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="75097-104">O Conector do Registro Eletrônico de Saúde (EHR) do Microsoft Teams facilita para os médicos a inicialização de uma visita virtual ou consulta com outro provedor no Teams diretamente do sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="75097-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="75097-105">Construído na nuvem Microsoft 365, o Microsoft Teams permite colaboração e comunicação simples e seguras com ferramentas de chat, vídeo, voz e saúde em um único hub que oferece suporte à conformidade com HIPAA, certificação HITECH e muito mais.</span><span class="sxs-lookup"><span data-stu-id="75097-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="75097-106">A plataforma de comunicação e colaboração do Teams torna mais fácil para os médicos eliminarem a desordem de sistemas fragmentados para que possam dedicar tempo fornecendo o melhor atendimento possível.</span><span class="sxs-lookup"><span data-stu-id="75097-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="75097-107">O Conector de Registro de Saúde Eletrônica (EHR) do Microsoft Teams pode:</span><span class="sxs-lookup"><span data-stu-id="75097-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="75097-108">Lance as visitas virtuais do Teams dos portais do provedor e do paciente.</span><span class="sxs-lookup"><span data-stu-id="75097-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="75097-109">Faça write-back dos metadados EHR em eventos de conexão e desconexão para habilitar a auditoria automática e a manutenção de registros.</span><span class="sxs-lookup"><span data-stu-id="75097-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="75097-110">Integre-se aos fluxos de trabalho existentes de médicos e pacientes, permitindo que eles usem o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="75097-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="75097-111">Assista ao vídeo de Como gerenciar visitas virtuais no portal EHR.</span><span class="sxs-lookup"><span data-stu-id="75097-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="75097-112">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="75097-112">Before you begin</span></span>

<span data-ttu-id="75097-113">Você precisará certificar-se de que possui os seguintes pré-requisitos antes de integrar o conector EHR:</span><span class="sxs-lookup"><span data-stu-id="75097-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="75097-114">Acesso para usar o aplicativo Microsoft Teams no [mercado App Orchard da Epic](https://apporchard.epic.com/Gallery?id=6153).</span><span class="sxs-lookup"><span data-stu-id="75097-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="75097-115">Assinatura ativa da Nuvem da Microsoft para Saúde ou assinatura da oferta autônoma do Conector EHR do Microsoft Teams (aplicada apenas durante os testes de produção).</span><span class="sxs-lookup"><span data-stu-id="75097-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="75097-116">Os usuários devem ter uma licença apropriada do Microsoft 365 ou Office 365 que inclua reuniões do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="75097-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="75097-117">O Microsoft Teams deve ser adotado e usado dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="75097-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="75097-118">As organizações devem ter a versão Epic de novembro de 2018 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="75097-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="75097-119">Seus sistemas devem atender a todos os [pré-requisitos de software e navegador ](../../hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="75097-119">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

<span data-ttu-id="75097-120">Você também precisará de informações das seguintes pessoas em sua organização:</span><span class="sxs-lookup"><span data-stu-id="75097-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="75097-121">Administrador do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="75097-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="75097-122">Analista de clientes Epic</span><span class="sxs-lookup"><span data-stu-id="75097-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="75097-123">Consulte o [Guia de integração de Telessaúde do Epic-Microsoft Teams](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) com o especialista técnico do seu Epic.</span><span class="sxs-lookup"><span data-stu-id="75097-123">Review the [Epic-Microsoft Teams Telehealth Integration Guide](https://galaxy.epic.com/Search/GetFile?Url=1!68!100!100100357) with your Epic technical specialist.</span></span> <span data-ttu-id="75097-124">Certifique-se de que todos os pré-requisitos foram concluídos.</span><span class="sxs-lookup"><span data-stu-id="75097-124">Make sure that all pre-requisites are completed.</span></span> 

## <a name="connector-setup"></a><span data-ttu-id="75097-125">Configuração do conector</span><span class="sxs-lookup"><span data-stu-id="75097-125">Connector setup</span></span>

<span data-ttu-id="75097-126">A configuração do conector requer que você:</span><span class="sxs-lookup"><span data-stu-id="75097-126">The connector setup requires that you:</span></span>

- [<span data-ttu-id="75097-127">Inicie o portal de configuração do Conector EHR</span><span class="sxs-lookup"><span data-stu-id="75097-127">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="75097-128">Informações de configuração</span><span class="sxs-lookup"><span data-stu-id="75097-128">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="75097-129">Aprovar ou visualizar a configuração</span><span class="sxs-lookup"><span data-stu-id="75097-129">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="75097-130">Análise e conclua a configuração</span><span class="sxs-lookup"><span data-stu-id="75097-130">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="75097-131">Inicie o portal de configuração do Conector EHR</span><span class="sxs-lookup"><span data-stu-id="75097-131">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="75097-132">Configurar sua organização de integridade para lançar visitas virtuais com o Microsoft Teams começa com o lançamento do portal de configuração do Conector EHR.</span><span class="sxs-lookup"><span data-stu-id="75097-132">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="75097-133">Você configura uma única ou várias organizações para testar a integração.</span><span class="sxs-lookup"><span data-stu-id="75097-133">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="75097-134">Configure a URL de teste e produção no portal de configuração.</span><span class="sxs-lookup"><span data-stu-id="75097-134">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="75097-135">Teste a integração do ambiente de teste da Epic antes de passar para a produção.</span><span class="sxs-lookup"><span data-stu-id="75097-135">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="75097-136">URL de configuração do conector EHR: [ https://ehrconnector.teams.microsoft.com ](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="75097-136">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="75097-137">O administrador do Microsoft 365 e o analista de clientes da Epic de sua organização devem concluir as etapas de informação e integração no portal de configuração.</span><span class="sxs-lookup"><span data-stu-id="75097-137">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="75097-138">Para as etapas de configuração da Epic, entre em contato com o recurso especialista técnico da Epic atribuído à sua organização.</span><span class="sxs-lookup"><span data-stu-id="75097-138">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="75097-139">Informações de configuração</span><span class="sxs-lookup"><span data-stu-id="75097-139">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="75097-140">Esta etapa deve ser concluída pelo **administrador do Microsoft 365**.</span><span class="sxs-lookup"><span data-stu-id="75097-140">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="75097-141">O administrador do Microsoft 365 deve iniciar o portal de configuração do conector e entrar com a conta da Microsoft para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="75097-141">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="75097-142">Para concluir esta etapa, o administrador do Microsoft 365 deve receber uma URL base válida de Recursos de Interoperabilidade de Integridade Rápida (FHIR) de seu especialista técnico da Epic e o nome de usuário do analista de cliente da Epic que aprovará a configuração.</span><span class="sxs-lookup"><span data-stu-id="75097-142">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="75097-143">O administrador do Microsoft 365 deve iniciar a página de configuração do conector e entrar com a conta da Microsoft para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="75097-143">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="75097-144">O URL base FHIR é um endereço estático correspondente ao ponto de extremidade da API FHIR do servidor.</span><span class="sxs-lookup"><span data-stu-id="75097-144">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="75097-145">Um exemplo de URL é `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span><span class="sxs-lookup"><span data-stu-id="75097-145">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="75097-146">O nome do aprovador da configuração é o nome do analista do cliente Epic que será responsável por aprovar a configuração na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="75097-146">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="75097-147">O analista de clientes da Epic é uma pessoa em sua organização com acesso de entrada ao Epic.</span><span class="sxs-lookup"><span data-stu-id="75097-147">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![O nome do aprovador da configuração é selecionado em uma lista no conector EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="75097-149">Aprovar ou exibir a configuração</span><span class="sxs-lookup"><span data-stu-id="75097-149">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="75097-150">O analista de cliente da Epic para sua organização de saúde que foi adicionado como um aprovador agora deve usar o mesmo URL do Conector EHR da etapa anterior para entrar usando a conta do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75097-150">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="75097-151">Após a validação, o aprovador será solicitado a entrar usando suas credenciais da Epic para validar a organização da Epic.</span><span class="sxs-lookup"><span data-stu-id="75097-151">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="75097-152">O administrador do Microsoft 365 e o analista de clientes da Epic em sua organização podem ser a mesma pessoa.</span><span class="sxs-lookup"><span data-stu-id="75097-152">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="75097-153">Nesse caso, adicione seu próprio nome de usuário como aprovador.</span><span class="sxs-lookup"><span data-stu-id="75097-153">In that case, add your own username as approver.</span></span> <span data-ttu-id="75097-154">Você ainda precisará entrar no Epic para validar seu acesso.</span><span class="sxs-lookup"><span data-stu-id="75097-154">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="75097-155">A entrada da Epic é usada apenas para validar seu URL base FHIR.</span><span class="sxs-lookup"><span data-stu-id="75097-155">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="75097-156">A Microsoft não armazenará credenciais ou acessará dados EHR com esta entrada.</span><span class="sxs-lookup"><span data-stu-id="75097-156">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Verifique e aprove a configuração da credencial.](../../media/approve-view-configuration.png)

<span data-ttu-id="75097-158">Após uma entrada com êxito da Epic, o analista de cliente da Epic **deve** aprovar a configuração.</span><span class="sxs-lookup"><span data-stu-id="75097-158">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="75097-159">Se a configuração não estiver correta, o administrador do Microsoft 365 poderá modificar as configurações originais entrando novamente no portal do conector EHR da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="75097-159">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Confirme se o conector EHR está configurado e a opção de alterar a configuração.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="75097-161">Análise e conclua a configuração</span><span class="sxs-lookup"><span data-stu-id="75097-161">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="75097-162">Quando as informações de configuração forem aprovadas pelo administrador da Epic, você verá os registros de integração para o paciente e o provedor iniciarem.</span><span class="sxs-lookup"><span data-stu-id="75097-162">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="75097-163">Esses registros são necessários para concluir a configuração da visita virtual no Epic.</span><span class="sxs-lookup"><span data-stu-id="75097-163">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="75097-164">Consulte o guia Epic-Microsoft Teams Telessaúde Integration para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="75097-164">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="75097-165">A qualquer momento, o analista do cliente Microsoft 365 ou Epic pode entrar no portal de configuração para visualizar os registros de integração e modificar a configuração da organização, se necessário.</span><span class="sxs-lookup"><span data-stu-id="75097-165">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![As informações de integração são exibidas.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="75097-167">O processo de aprovação deve ser concluído pelo analista de cliente da Epic para cada URL FHIR configurado pelo administrador da Microsoft antes.</span><span class="sxs-lookup"><span data-stu-id="75097-167">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![As informações de configuração são aprovadas.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="75097-169">Visitas virtuais do Teams de lançamento</span><span class="sxs-lookup"><span data-stu-id="75097-169">Launch Teams virtual visits</span></span>

<span data-ttu-id="75097-170">Depois de concluir as etapas do Conector EHR e a configuração da Epic, sua organização está pronta para oferecer suporte a visitas de vídeo com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="75097-170">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="75097-171">Pré-requisitos da visita virtual</span><span class="sxs-lookup"><span data-stu-id="75097-171">Virtual visit prerequisites</span></span>

- <span data-ttu-id="75097-172">Seus sistemas devem atender a todos os [pré-requisitos de software e navegador ](../../hardware-requirements-for-the-teams-app.md).</span><span class="sxs-lookup"><span data-stu-id="75097-172">Your systems must meet all [software and browser prerequisites](../../hardware-requirements-for-the-teams-app.md).</span></span>

- <span data-ttu-id="75097-173">A organização de deve ter concluído a configuração entre a organização Epic e a organização Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="75097-173">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="75097-174">Experiência do provedor</span><span class="sxs-lookup"><span data-stu-id="75097-174">Provider experience</span></span>

<span data-ttu-id="75097-175">Os provedores de saúde da sua organização também podem participar de visitas virtuais com o Microsoft Teams de seus aplicativos de provedor da Epic (Hyperspace, Haiku, Canto).</span><span class="sxs-lookup"><span data-stu-id="75097-175">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="75097-176">O botão **Iniciar visita virtual** está incorporado no fluxo do provedor.</span><span class="sxs-lookup"><span data-stu-id="75097-176">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="75097-177">Principais recursos da experiência do provedor:</span><span class="sxs-lookup"><span data-stu-id="75097-177">Key features of the provider experience:</span></span>

- <span data-ttu-id="75097-178">Os provedores podem ingressar em visitas virtuais usando navegadores compatíveis ou o aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="75097-178">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="75097-179">Os provedores devem fazer uma entrada única com sua conta do Microsoft 365 ao ingressar em uma visita virtual pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="75097-179">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="75097-p114">Após o logon único, o provedor será levado diretamente para o compromisso virtual no Microsoft Teams. (O provedor deve estar conectado ao Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="75097-p114">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams. (Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="75097-182">O provedor pode ver atualizações em tempo real dos participantes que se conectam e desconectam para um determinado compromisso.</span><span class="sxs-lookup"><span data-stu-id="75097-182">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="75097-183">O provedor pode ver quando o paciente está conectado a uma visita virtual.</span><span class="sxs-lookup"><span data-stu-id="75097-183">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Experiência do provedor de uma visita virtual com o paciente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="75097-185">Experiência do paciente</span><span class="sxs-lookup"><span data-stu-id="75097-185">Patient experience</span></span>

<span data-ttu-id="75097-186">O conector oferece suporte a pacientes que ingressam em visitas virtuais por meio do MyChart web e móvel.</span><span class="sxs-lookup"><span data-stu-id="75097-186">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="75097-187">No momento da consulta, os pacientes podem iniciar uma visita virtual no MyChart usando o botão **Iniciar visita virtual**.</span><span class="sxs-lookup"><span data-stu-id="75097-187">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="75097-188">Características principais da experiência do paciente:</span><span class="sxs-lookup"><span data-stu-id="75097-188">Key features of the patient experience:</span></span>

- <span data-ttu-id="75097-189">Os pacientes podem participar de visitas virtuais a partir de navegadores modernos no desktop e no celular sem a instalação de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="75097-189">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="75097-190">Os pacientes podem participar de visitas virtuais com um único clique e não há outra conta ou entrada necessária.</span><span class="sxs-lookup"><span data-stu-id="75097-190">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="75097-191">Os pacientes não são obrigados a criar uma conta Microsoft ou entrar para iniciar uma visita virtual.</span><span class="sxs-lookup"><span data-stu-id="75097-191">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="75097-192">Os pacientes serão colocados em um saguão até que o profissional de saúde participe da consulta e os admita para a visita virtual.</span><span class="sxs-lookup"><span data-stu-id="75097-192">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="75097-193">O teste do vídeo e do microfone está disponível no saguão antes de entrar na visita virtual.</span><span class="sxs-lookup"><span data-stu-id="75097-193">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Experiência do paciente na visita virtual](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="75097-195">Epic, MyChart, Haiku e Canto são marcas comerciais da Epic Systems Corporation.</span><span class="sxs-lookup"><span data-stu-id="75097-195">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="75097-196">Privacidade e localização de dados</span><span class="sxs-lookup"><span data-stu-id="75097-196">Privacy and location of data</span></span>

<span data-ttu-id="75097-197">A integração do Teams em sistemas EHR otimiza a quantidade de dados que estão sendo usados ​​e armazenados durante a integração e os fluxos de visita virtual.</span><span class="sxs-lookup"><span data-stu-id="75097-197">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="75097-198">A solução segue os princípios e diretrizes gerais de privacidade e gerenciamento de dados do Teams, descritos em Privacidade do Teams.</span><span class="sxs-lookup"><span data-stu-id="75097-198">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="75097-199">O conector EHR do Microsoft Teams não armazena nem transfere quaisquer dados pessoais identificáveis ​​ou registros de saúde de pacientes ou prestadores de serviços de saúde do sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="75097-199">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="75097-200">Os únicos dados armazenados pelo conector EHR são a ID exclusiva do usuário EHR, que é usada durante a configuração da reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="75097-200">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="75097-201">A ID exclusiva do usuário EHR é armazenada em uma das três regiões geográficas descritas em [Onde seus dados de cliente Microsoft 365 são armazenados](/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span><span class="sxs-lookup"><span data-stu-id="75097-201">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="75097-202">Todos os chats, gravações e outros dados inseridos nas equipes pelos participantes da reunião são armazenados de acordo com as políticas de armazenamento existentes.</span><span class="sxs-lookup"><span data-stu-id="75097-202">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="75097-203">Se você quiser saber mais informações sobre a localização dos dados no Microsoft Teams, visite [ Locais dos dados no Teams ](../../location-of-data-in-teams.md).</span><span class="sxs-lookup"><span data-stu-id="75097-203">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](../../location-of-data-in-teams.md).</span></span>