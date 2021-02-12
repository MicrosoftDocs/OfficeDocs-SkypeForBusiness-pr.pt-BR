---
title: Equipes para visitas virtuais
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
description: Usar o Microsoft Teams para configurar seu sistema de visitas virtuais
ms.openlocfilehash: 2d2be135668bcc45f0054e987a23845e3245c38e
ms.sourcegitcommit: 1b11a2b74b8db6ed9e5da9b04cf3ed9c02a1d892
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2021
ms.locfileid: "50125774"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="d9175-103">Visitas virtuais com o Teams – Integração com o EHR</span><span class="sxs-lookup"><span data-stu-id="d9175-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="d9175-104">O Microsoft Teams Electronic Health Record (EHR) Connector facilita a entrada de pacientes virtuais ou consulta com outro provedor no Teams diretamente do sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="d9175-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="d9175-105">Criado na nuvem do Microsoft 365, o Microsoft Teams permite colaboração e comunicação simples e seguras com ferramentas de chat, vídeo, voz e saúde em um único hub que oferece suporte à conformidade com a HIPAA, certificação HITECH e muito mais.</span><span class="sxs-lookup"><span data-stu-id="d9175-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>
<span data-ttu-id="d9175-106">A plataforma de comunicação e colaboração do Teams facilita a recortar a confusão de sistemas fragmentados para que eles possam passar o tempo fornecendo o melhor cuidado possível.</span><span class="sxs-lookup"><span data-stu-id="d9175-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="d9175-107">O Microsoft Teams Electronic Health Record (EHR) Connector pode:</span><span class="sxs-lookup"><span data-stu-id="d9175-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>
- <span data-ttu-id="d9175-108">Iniciar visitas virtuais do Teams a partir de portais de provedores e pacientes.</span><span class="sxs-lookup"><span data-stu-id="d9175-108">Launch Teams virtual visits from both provider and patient portals.</span></span>
- <span data-ttu-id="d9175-109">Escreva novamente nos metadados EHR ao conectar e desconectar eventos para habilitar a auditoria automática e a manutenção de registros.</span><span class="sxs-lookup"><span data-stu-id="d9175-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>
- <span data-ttu-id="d9175-110">Integre-se aos fluxos de trabalho dos pacientes e dos fluxos de trabalho existentes, permitindo que eles usem o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d9175-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="d9175-111">Assista ao vídeo sobre como gerenciar visitas virtuais no portal do EHR.</span><span class="sxs-lookup"><span data-stu-id="d9175-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="d9175-112">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="d9175-112">Before you begin</span></span>

<span data-ttu-id="d9175-113">Você precisará garantir que tem os seguintes pré-requisitos antes de integrar o conector EHR:</span><span class="sxs-lookup"><span data-stu-id="d9175-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="d9175-114">Acesso para usar o aplicativo Microsoft Teams no [Marketplace do App Pomar do App.](https://apporchard.epic.com/Gallery?id=6153)</span><span class="sxs-lookup"><span data-stu-id="d9175-114">Access to use to the Microsoft Teams app in [Epic’s App Orchard marketplace](https://apporchard.epic.com/Gallery?id=6153).</span></span>

- <span data-ttu-id="d9175-115">Assinatura ativa do Microsoft Cloud for Healthcare ou assinatura da oferta autônoma do Microsoft Teams EHR Connector (imposta somente durante os testes de produção).</span><span class="sxs-lookup"><span data-stu-id="d9175-115">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer (only enforced during production testing).</span></span>

- <span data-ttu-id="d9175-116">Os usuários devem ter uma licença apropriada do Microsoft 365 ou do Office 365 que inclua reuniões do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d9175-116">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="d9175-117">O Microsoft Teams deve ser adotado e usado dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="d9175-117">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="d9175-118">As organizações devem ter a versão Original de novembro de 2018 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="d9175-118">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="d9175-119">Seus sistemas devem atender a [todos os pré-requisitos](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)de software e navegador.</span><span class="sxs-lookup"><span data-stu-id="d9175-119">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="d9175-120">Você também precisará de informações das seguintes pessoas em sua organização:</span><span class="sxs-lookup"><span data-stu-id="d9175-120">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="d9175-121">Administrador do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d9175-121">Microsoft 365 administrator</span></span>

- <span data-ttu-id="d9175-122">Analista de clientes com experiência em negócios</span><span class="sxs-lookup"><span data-stu-id="d9175-122">Epic customer analyst</span></span>

> [!Note]
> <span data-ttu-id="d9175-123">Solicite ao seu especialista técnico da Base de Dados para fornecer o Epic-Microsoft de Integração do Teams Telehealth disponível no marketplace Do Marketplace.</span><span class="sxs-lookup"><span data-stu-id="d9175-123">Request your Epic technical specialist to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="d9175-124">Configuração do conector</span><span class="sxs-lookup"><span data-stu-id="d9175-124">Connector setup</span></span>

<span data-ttu-id="d9175-125">A configuração do conector requer que você:</span><span class="sxs-lookup"><span data-stu-id="d9175-125">The connector setup requires that you:</span></span>

- [<span data-ttu-id="d9175-126">Iniciar o portal de configuração do Conector EHR</span><span class="sxs-lookup"><span data-stu-id="d9175-126">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="d9175-127">Informações de configuração</span><span class="sxs-lookup"><span data-stu-id="d9175-127">Configuration information</span></span>](ehr-admin.md#configuration-information)
- [<span data-ttu-id="d9175-128">Aprovar ou exibir configuração</span><span class="sxs-lookup"><span data-stu-id="d9175-128">Approve or view configuration</span></span>](ehr-admin.md#approve-or-view-configuration)
- [<span data-ttu-id="d9175-129">Revisar e concluir a configuração</span><span class="sxs-lookup"><span data-stu-id="d9175-129">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="d9175-130">Iniciar o portal de configuração do Conector EHR</span><span class="sxs-lookup"><span data-stu-id="d9175-130">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="d9175-131">Configurar sua organização de saúde para iniciar visitas virtuais com o Microsoft Teams começa iniciando o portal de configuração do EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="d9175-131">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="d9175-132">Configure uma ou várias organizações para testar a integração.</span><span class="sxs-lookup"><span data-stu-id="d9175-132">You configure a single or multiple organizations to test the integration.</span></span> <span data-ttu-id="d9175-133">Configure a URL de teste e produção no portal de configuração.</span><span class="sxs-lookup"><span data-stu-id="d9175-133">Configure the test and production URL in the configuration portal.</span></span> <span data-ttu-id="d9175-134">Teste a integração do ambiente de teste da Epic antes de ir para a produção.</span><span class="sxs-lookup"><span data-stu-id="d9175-134">Test the integration from Epic’s test environment before moving to production.</span></span>
  
- <span data-ttu-id="d9175-135">URL de configuração do conector EHR: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="d9175-135">EHR connector configuration URL: [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="d9175-136">O administrador do Microsoft 365 e o analista de clientes Dols de sua organização devem concluir as etapas de integração e informações no portal de configuração.</span><span class="sxs-lookup"><span data-stu-id="d9175-136">The Microsoft 365 admin and Epic customer analyst from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="d9175-137">Para ver as etapas de configuração doPico, entre em contato com o recurso especialista técnico Daaa atribuído à sua organização.</span><span class="sxs-lookup"><span data-stu-id="d9175-137">For Epic configuration steps, contact the Epic technical specialist resource assigned to your organization.</span></span>

### <a name="configuration-information"></a>[<span data-ttu-id="d9175-138">Informações de configuração</span><span class="sxs-lookup"><span data-stu-id="d9175-138">Configuration information</span></span>](#configuration-information)

<span data-ttu-id="d9175-139">Esta etapa deve ser concluída pelo administrador do **Microsoft 365.**</span><span class="sxs-lookup"><span data-stu-id="d9175-139">This step is to be completed by the **Microsoft 365 administrator**.</span></span> <span data-ttu-id="d9175-140">O administrador do Microsoft 365 deve iniciar o portal de configuração do conector e entrar com credenciais da Microsoft para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="d9175-140">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="d9175-141">Para concluir esta etapa, o administrador do Microsoft 365 deve receber uma URL de base FHIR (Recursos de Interoperabilidade de Saúde Rápida) válida do seu especialista técnico Do Microsoft 365 e o nome de usuário do analista de clientes Daltic que aprovará a configuração.</span><span class="sxs-lookup"><span data-stu-id="d9175-141">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Epic technical specialist and the username of the Epic customer analyst who will be approving the configuration.</span></span> <span data-ttu-id="d9175-142">O administrador do Microsoft 365 deve iniciar a página de configuração do conector e entrar com credenciais da Microsoft para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="d9175-142">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="d9175-143">A URL base FHIR é um endereço estático correspondente ao ponto de extremidade da API FHIR do servidor.</span><span class="sxs-lookup"><span data-stu-id="d9175-143">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="d9175-144">Um exemplo de URL é `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST` .</span><span class="sxs-lookup"><span data-stu-id="d9175-144">An example URL is `https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST`.</span></span>

- <span data-ttu-id="d9175-145">O nome do aprovador de configuração é o nome do analista de clientes Dalmk, que será responsável por aprovar a configuração na próxima etapa.</span><span class="sxs-lookup"><span data-stu-id="d9175-145">Configuration approver name is the name of the Epic customer analyst who will be responsible for approving the configuration in the next step.</span></span> <span data-ttu-id="d9175-146">O analista de clientes Dalm é uma pessoa em sua organização com acesso de entrada aoPico.</span><span class="sxs-lookup"><span data-stu-id="d9175-146">The Epic customer analyst is a person in your organization with sign-in access to Epic.</span></span>

  ![O nome do aprovador de configuração é selecionado em uma lista no conector EHR.](../../media/teams-ehr-connector.png)

### <a name="approve-or-view-configuration"></a>[<span data-ttu-id="d9175-148">Aprovar ou exibir configuração</span><span class="sxs-lookup"><span data-stu-id="d9175-148">Approve or view configuration</span></span>](#approve-or-view-configuration)

<span data-ttu-id="d9175-149">O analista de clientes Dalt para sua organização de saúde que foi adicionado como aprovador agora deve usar a mesma URL do Conector EHR da etapa anterior para entrar usando suas credenciais do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9175-149">The Epic customer analyst for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="d9175-150">Após a validação bem-sucedida, o aprovador será solicitado a entrar usando suas credenciais de Aérea para validar a organização Doa.</span><span class="sxs-lookup"><span data-stu-id="d9175-150">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="d9175-151">O administrador do Microsoft 365 e o analista de clientes Dols em sua organização podem ser a mesma pessoa.</span><span class="sxs-lookup"><span data-stu-id="d9175-151">The Microsoft 365 admin and Epic customer analyst in your organization can be the same person.</span></span> <span data-ttu-id="d9175-152">Nesse caso, adicione seu próprio nome de usuário como aprovador.</span><span class="sxs-lookup"><span data-stu-id="d9175-152">In that case, add your own username as approver.</span></span> <span data-ttu-id="d9175-153">Você ainda precisará entrar noPico Para validar seu acesso.</span><span class="sxs-lookup"><span data-stu-id="d9175-153">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="d9175-154">A assinatura do Élpico é usada apenas para validar sua URL base FHIR.</span><span class="sxs-lookup"><span data-stu-id="d9175-154">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="d9175-155">A Microsoft não armazenará credenciais ou acessará dados de EHR com essa entrada.</span><span class="sxs-lookup"><span data-stu-id="d9175-155">Microsoft won't store credentials or access EHR data with this sign in.</span></span>

  ![Verifique e aprove a configuração de credenciais.](../../media/approve-view-configuration.png)

<span data-ttu-id="d9175-157">Depois de uma entrada bem-sucedida da Aérea, o analista de clientes Dalmá **deve** aprovar a configuração.</span><span class="sxs-lookup"><span data-stu-id="d9175-157">After a successful Epic sign in, the Epic customer analyst **must** approve the configuration.</span></span> <span data-ttu-id="d9175-158">Se a configuração não estiver correta, o administrador do Microsoft 365 terá a capacidade de modificar as configurações originais ao entrar no portal do conector EHR da Microsoft novamente.</span><span class="sxs-lookup"><span data-stu-id="d9175-158">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR connector portal again.</span></span> 

![Confirme se o conector EHR está configurado e a opção para alterar a configuração.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="d9175-160">Revisar e concluir a configuração</span><span class="sxs-lookup"><span data-stu-id="d9175-160">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="d9175-161">Quando as informações de configuração tiverem sido aprovadas pelo administrador do Programa, você será apresentado com registros de integração para o lançamento do paciente e do provedor.</span><span class="sxs-lookup"><span data-stu-id="d9175-161">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="d9175-162">Esses registros são necessários para concluir a configuração de visita virtual noPico.</span><span class="sxs-lookup"><span data-stu-id="d9175-162">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="d9175-163">Consulte o guia Epic-Microsoft Integração do Teams Telehealth para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="d9175-163">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="d9175-164">A qualquer momento, o analista de clientes Do Microsoft 365 ou o analista de clientes Dols pode entrar no portal de configuração para exibir registros de integração e modificar a configuração da organização, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d9175-164">At any time the Microsoft 365 or Epic customer analyst can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![As informações de integração são exibidas.](../../media/finish-configuration.png)

> [!Note]
> <span data-ttu-id="d9175-166">O processo de aprovação deve ser concluído pelo analista de clientes DaLm para cada URL FHIR configurada pelo administrador da Microsoft antes.</span><span class="sxs-lookup"><span data-stu-id="d9175-166">The approval process must be completed by the Epic customer analyst for every FHIR URL configured by the Microsoft admin before.</span></span>

![As informações de configuração são aprovadas.](../../media/approve-configuration-2.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="d9175-168">Iniciar visitas virtuais do Teams</span><span class="sxs-lookup"><span data-stu-id="d9175-168">Launch Teams virtual visits</span></span>

<span data-ttu-id="d9175-169">Depois de concluir as etapas do Conector EHR e a configuração dePico, sua organização está pronta para dar suporte a visitas com vídeo com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d9175-169">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="d9175-170">Pré-requisitos de visita virtual</span><span class="sxs-lookup"><span data-stu-id="d9175-170">Virtual visit prerequisites</span></span>

- <span data-ttu-id="d9175-171">Seus sistemas devem atender a [todos os pré-requisitos](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app)de software e navegador.</span><span class="sxs-lookup"><span data-stu-id="d9175-171">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="d9175-172">A organização de serviços de saúde deve ter concluído a configuração entre a organização do Microsoft 365 e a organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d9175-172">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="d9175-173">Experiência do provedor</span><span class="sxs-lookup"><span data-stu-id="d9175-173">Provider experience</span></span>

<span data-ttu-id="d9175-174">Os provedores de saúde de sua organização também podem ingressar em visitas virtuais com o Microsoft Teams a partir de seus aplicativos de provedores Deslocados (Hyperspace, Vpnku, Canto).</span><span class="sxs-lookup"><span data-stu-id="d9175-174">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="d9175-175">O **botão Iniciar visita virtual** é inserido no fluxo do provedor.</span><span class="sxs-lookup"><span data-stu-id="d9175-175">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="d9175-176">Principais recursos da experiência do provedor:</span><span class="sxs-lookup"><span data-stu-id="d9175-176">Key features of the provider experience:</span></span>

- <span data-ttu-id="d9175-177">Os provedores podem ingressar em visitas virtuais usando navegadores com suporte ou o aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d9175-177">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="d9175-178">Os provedores devem fazer uma logon única com sua conta do Microsoft 365 ao ingressar em uma visita virtual pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="d9175-178">Providers must do a one-time sign-in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="d9175-179">Após a logon única, o provedor será levado diretamente para o compromisso virtual no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="d9175-179">After the one-time sign-in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="d9175-180">(O provedor deve estar dentro do Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="d9175-180">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="d9175-181">O provedor pode ver atualizações em tempo real dos participantes se conectam e se desconectam para um determinado compromisso.</span><span class="sxs-lookup"><span data-stu-id="d9175-181">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="d9175-182">O provedor pode ver quando o paciente está conectado a uma visita virtual.</span><span class="sxs-lookup"><span data-stu-id="d9175-182">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Experiência do provedor de uma visita virtual com o paciente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="d9175-184">Experiência do paciente</span><span class="sxs-lookup"><span data-stu-id="d9175-184">Patient experience</span></span>

<span data-ttu-id="d9175-185">O conector dá suporte a pacientes in joining virtual visits through MyChart web and mobile.</span><span class="sxs-lookup"><span data-stu-id="d9175-185">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="d9175-186">No momento do compromisso, os pacientes podem iniciar uma visita virtual a partir de Meu Gráfico usando o **botão Iniciar visita virtual.**</span><span class="sxs-lookup"><span data-stu-id="d9175-186">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="d9175-187">Principais recursos da experiência do paciente:</span><span class="sxs-lookup"><span data-stu-id="d9175-187">Key features of the patient experience:</span></span>

- <span data-ttu-id="d9175-188">Os pacientes podem ingressar em visitas virtuais a partir de navegadores da Web modernos na área de trabalho e em dispositivos móveis sem instalação de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="d9175-188">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="d9175-189">Os pacientes podem ingressar em visitas virtuais com um único clique e não há nenhuma outra conta ou necessidade de entrar.</span><span class="sxs-lookup"><span data-stu-id="d9175-189">Patients can join virtual visits with a single click and there is no other account or sign-in required.</span></span>

- <span data-ttu-id="d9175-190">Os pacientes não são obrigados a criar uma conta da Microsoft ou entrar para iniciar uma visita virtual.</span><span class="sxs-lookup"><span data-stu-id="d9175-190">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="d9175-191">Os pacientes serão colocados em um lobby até que o provedor de saúde in joins in the appointment and admits them to the virtual visit.</span><span class="sxs-lookup"><span data-stu-id="d9175-191">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="d9175-192">O teste do vídeo e do microfone está disponível no lobby antes de ingressar na visita virtual.</span><span class="sxs-lookup"><span data-stu-id="d9175-192">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Experiência do paciente da visita virtual](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="d9175-194">Émúm, MyChart,Kuku e Canto são marcas registradas da Corporação Det.</span><span class="sxs-lookup"><span data-stu-id="d9175-194">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="d9175-195">Privacidade e localização dos dados</span><span class="sxs-lookup"><span data-stu-id="d9175-195">Privacy and location of data</span></span>

<span data-ttu-id="d9175-196">A integração do Teams aos sistemas de EHR otimiza a quantidade de dados que estão sendo usados e armazenados durante a integração e os fluxos de visitas virtuais.</span><span class="sxs-lookup"><span data-stu-id="d9175-196">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="d9175-197">A solução segue os princípios gerais de privacidade e gerenciamento de dados do Teams e as diretrizes descritas na Privacidade do Teams.</span><span class="sxs-lookup"><span data-stu-id="d9175-197">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="d9175-198">O conector EHR do Microsoft Teams não armazena nem transfere dados pessoais identificáveis ou quaisquer registros de saúde de pacientes ou provedores de saúde do sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="d9175-198">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="d9175-199">Os únicos dados armazenados pelo conector EHR são a ID exclusiva do usuário do EHR, que é usada durante a configuração da reunião do Teams.</span><span class="sxs-lookup"><span data-stu-id="d9175-199">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="d9175-200">A ID exclusiva do usuário do EHR é armazenada em uma das três regiões geográficas descritas em Onde seus dados de cliente do [Microsoft 365 são armazenados.](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies)</span><span class="sxs-lookup"><span data-stu-id="d9175-200">The EHR user’s unique ID is stored in one of the three geographic regions described in [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies).</span></span> <span data-ttu-id="d9175-201">Todos os chats, gravações e outros dados inseridos no Teams pelos participantes da reunião são armazenados de acordo com as políticas de armazenamento existentes.</span><span class="sxs-lookup"><span data-stu-id="d9175-201">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="d9175-202">Se quiser saber mais sobre a localização dos dados no Microsoft Teams, visite [Locais de dados no Teams.](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams)</span><span class="sxs-lookup"><span data-stu-id="d9175-202">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
