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
ms.openlocfilehash: ed952f678fb353ae623a0020ac565ee4e8288445
ms.sourcegitcommit: 62d5ccf10202a50755166e3b8de0bd31d1f94fef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/28/2020
ms.locfileid: "48790453"
---
# <a name="virtual-visits-with-teams---integration-into-ehr"></a><span data-ttu-id="4d2e2-103">Visitas virtuais com o Teams-integração ao EHR</span><span class="sxs-lookup"><span data-stu-id="4d2e2-103">Virtual visits with Teams - Integration into EHR</span></span>

<span data-ttu-id="4d2e2-104">O conector do Microsoft Teams Electronic Health Record (EHR) facilita para os clínicos iniciarem uma visita ou consultoria do paciente virtual com outro provedor no Teams diretamente do sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-104">Microsoft Teams Electronic Health Record (EHR) Connector makes it easy for clinicians to launch a virtual patient visit or consultation with another provider in Teams directly from the EHR system.</span></span> <span data-ttu-id="4d2e2-105">Baseado na nuvem do Microsoft 365, o Microsoft Teams permite colaboração simples e segura e comunicação com as ferramentas de chat, vídeo, voz e saúde em um único Hub compatível com a HIPAA, a certificação de alta tecnologia e muito mais.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-105">Built on the Microsoft 365 cloud, Microsoft Teams enables simple, secure collaboration and communication with chat, video, voice, and healthcare tools in a single hub that supports compliance with HIPAA, HITECH certification, and more.</span></span>

<span data-ttu-id="4d2e2-106">A plataforma de comunicação e colaboração de equipes torna mais fácil para os clínicos reduzirem o truncamento dos sistemas fragmentados para que possam perder tempo oferecendo o melhor cuidado possível.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-106">The communication and collaboration platform of Teams makes it easy for clinicians to cut through the clutter of fragmented systems so they can spend time providing the best possible care.</span></span> <span data-ttu-id="4d2e2-107">O conector EHR (Microsoft Teams Electronic Health Record) pode:</span><span class="sxs-lookup"><span data-stu-id="4d2e2-107">Microsoft Teams Electronic Health Record (EHR) Connector can:</span></span>

- <span data-ttu-id="4d2e2-108">Inicie visitas virtuais do teams de provedores e portais de pacientes.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-108">Launch Teams virtual visits from both provider and patient portals.</span></span>

- <span data-ttu-id="4d2e2-109">Escreva novamente em metadados do EHR em eventos de conexão e desconexão para habilitar a auditoria automática e a manutenção de registros.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-109">Write back into EHR metadata on connect and disconnect events to enable automatic auditing and record keeping.</span></span>

- <span data-ttu-id="4d2e2-110">Integre-se a fluxos de trabalho clínicos e de pacientes existentes, permitindo que eles usem o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-110">Integrate into existing clinician and patient workflows while allowing them to use Microsoft Teams.</span></span>

  <span data-ttu-id="4d2e2-111">Assista ao vídeo sobre como gerenciar visitas virtuais no portal EHR.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-111">Watch the video of How to manage virtual visits from the EHR portal.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4HAtn]

## <a name="before-you-begin"></a><span data-ttu-id="4d2e2-112">Antes de você começar</span><span class="sxs-lookup"><span data-stu-id="4d2e2-112">Before you begin</span></span>

<span data-ttu-id="4d2e2-113">Você precisará certificar-se de ter os seguintes pré-requisitos antes de integrar o conector EHR:</span><span class="sxs-lookup"><span data-stu-id="4d2e2-113">You’ll need to make sure you have the following prerequisites before you can integrate the EHR connector:</span></span>

- <span data-ttu-id="4d2e2-114">Assinatura ativa para o Microsoft Cloud para assistência médica ou assinatura para a oferta autônoma do Microsoft Teams EHR Connector.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-114">Active subscription to Microsoft Cloud for Healthcare or subscription to Microsoft Teams EHR Connector standalone offer.</span></span>

- <span data-ttu-id="4d2e2-115">Os usuários devem ter uma licença do Microsoft 365 ou do Office 365 apropriada que inclua reuniões do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-115">Users must have an appropriate Microsoft 365 or Office 365 license that includes Microsoft Teams meetings.</span></span>

- <span data-ttu-id="4d2e2-116">O Microsoft Teams deve ser adotado e usado dentro da organização.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-116">Microsoft Teams should be adopted and used inside the organization.</span></span>

- <span data-ttu-id="4d2e2-117">As organizações devem ter a versão testamento de novembro de 2018 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-117">Organizations must have with Epic version November 2018 or later.</span></span>

- <span data-ttu-id="4d2e2-118">Seus sistemas devem atender todos os [pré-requisitos do software e do navegador](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="4d2e2-118">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

<span data-ttu-id="4d2e2-119">Você também precisará de informações das seguintes pessoas em sua organização:</span><span class="sxs-lookup"><span data-stu-id="4d2e2-119">You’ll also need information from the following people in your organization:</span></span>

- <span data-ttu-id="4d2e2-120">Administrador do Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4d2e2-120">Microsoft 365 administrator</span></span>

- <span data-ttu-id="4d2e2-121">Administrador do testamento</span><span class="sxs-lookup"><span data-stu-id="4d2e2-121">Epic administrator</span></span>

> [!Note]
> <span data-ttu-id="4d2e2-122">Solicite ao seu administrador do testamento que forneça o guia de integração de teleintegridade do teams Epic-Microsoft disponível no testamento Marketplace.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-122">Request your Epic admin to provide the Epic-Microsoft Teams Telehealth Integration Guide available in the Epic marketplace.</span></span>

## <a name="connector-setup"></a><span data-ttu-id="4d2e2-123">Configuração do conector</span><span class="sxs-lookup"><span data-stu-id="4d2e2-123">Connector setup</span></span>

<span data-ttu-id="4d2e2-124">A instalação do conector exige que você:</span><span class="sxs-lookup"><span data-stu-id="4d2e2-124">The connector setup requires that you:</span></span>

- [<span data-ttu-id="4d2e2-125">Iniciar o portal de configuração do conector EHR</span><span class="sxs-lookup"><span data-stu-id="4d2e2-125">Launch the EHR Connector configuration portal</span></span>](ehr-admin.md#launch-the-ehr-connector-configuration-portal)
- [<span data-ttu-id="4d2e2-126">Configurar informações da organização do provedor</span><span class="sxs-lookup"><span data-stu-id="4d2e2-126">Configure provider organization information</span></span>](ehr-admin.md#configure-provider-organization-information)
- [<span data-ttu-id="4d2e2-127">Verificar e aprovar a configuração</span><span class="sxs-lookup"><span data-stu-id="4d2e2-127">Verify and approve the configuration</span></span>](ehr-admin.md#verify-and-approve-the-configuration)
- [<span data-ttu-id="4d2e2-128">Revisar e concluir a configuração</span><span class="sxs-lookup"><span data-stu-id="4d2e2-128">Review and finish the configuration</span></span>](ehr-admin.md#review-and-finish-the-configuration)

### <a name="launch-the-ehr-connector-configuration-portal"></a>[<span data-ttu-id="4d2e2-129">Iniciar o portal de configuração do conector EHR</span><span class="sxs-lookup"><span data-stu-id="4d2e2-129">Launch the EHR Connector configuration portal</span></span>](#launch-the-ehr-connector-configuration-portal)

<span data-ttu-id="4d2e2-130">Configurar sua organização de assistência médica para iniciar visitas virtuais com o Microsoft Teams inicia iniciando o portal de configuração do conector EHR.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-130">Configuring your healthcare organization to launch virtual visits with Microsoft Teams starts by launching the EHR Connector configuration portal.</span></span> <span data-ttu-id="4d2e2-131">Use a URL de teste para configurar o conector para o ambiente de teste do testamento.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-131">Use the test URL to configure the connector for your Epic test environment.</span></span> <span data-ttu-id="4d2e2-132">Use a URL de produção quando estiver pronto para habilitar o ambiente de produção do testamento.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-132">Use the production URL when you're ready to enable your Epic production environment.</span></span>
  
- <span data-ttu-id="4d2e2-133">Ambiente de teste [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4d2e2-133">Test environment [https://ehrconnector-ppe.teams.microsoft.com](https://ehrconnector-ppe.teams.microsoft.com)</span></span>
- <span data-ttu-id="4d2e2-134">Ambiente de produção [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="4d2e2-134">Production environment [https://ehrconnector.teams.microsoft.com](https://ehrconnector.teams.microsoft.com)</span></span>

<span data-ttu-id="4d2e2-135">O administrador do Microsoft 365 e o administrador do testamento da sua organização devem completar as etapas de integração e informações no portal de configuração.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-135">The Microsoft 365 admin and Epic admin from your organization must complete the information and integration steps in the configuration portal.</span></span> <span data-ttu-id="4d2e2-136">Para ver as etapas de configuração do testamento, entre em contato com o recurso do testamento atribuído à sua organização.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-136">For Epic configuration steps, contact the Epic resource assigned to your organization.</span></span>

### <a name="configure-provider-organization-information"></a>[<span data-ttu-id="4d2e2-137">Configurar informações da organização do provedor</span><span class="sxs-lookup"><span data-stu-id="4d2e2-137">Configure provider organization information</span></span>](#configure-provider-organization-information)

<span data-ttu-id="4d2e2-138">Esta etapa deve ser concluída pelo administrador do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-138">This step is to be completed by the Microsoft 365 administrator.</span></span> <span data-ttu-id="4d2e2-139">O administrador do Microsoft 365 deve iniciar o portal de configuração do conector e entrar com as credenciais da Microsoft para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-139">The Microsoft 365 administrator must launch the connector configuration portal and sign in with Microsoft credentials to start the configuration process.</span></span>

<span data-ttu-id="4d2e2-140">Para concluir esta etapa, o administrador do Microsoft 365 deve receber uma URL base válida de recursos de interoperabilidade de integridade rápida (FHIR) do seu administrador do Microsoft 365 e o nome de usuário do administrador do testamento, que aprovará a configuração.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-140">To complete this step, the Microsoft 365 administrator must receive a valid Fast Health Interoperability Resources (FHIR) base URL from your Microsoft 365 administrator and the username of the Epic administrator who will be approving the configuration.</span></span> <span data-ttu-id="4d2e2-141">O administrador do Microsoft 365 deve iniciar a página de configuração do conector e entrar com as credenciais da Microsoft para iniciar o processo de configuração.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-141">The Microsoft 365 administrator must launch the connector configuration page and sign in with Microsoft credentials to start the configuration process.</span></span>

- <span data-ttu-id="4d2e2-142">A URL base FHIR é um endereço estático correspondente ao seu servidor de ponto de extremidade de API do FHIR.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-142">The FHIR base URL is a static address corresponding to your server FHIR API endpoint.</span></span> <span data-ttu-id="4d2e2-143">Um exemplo de URL é [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST) .</span><span class="sxs-lookup"><span data-stu-id="4d2e2-143">An example URL is [https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST](https://lamnahealthcare.org/fihr/auth/connect-ocurprd-oauth/api/FHDST).</span></span>

- <span data-ttu-id="4d2e2-144">Nome do aprovador de configuração é o nome do administrador do sistema do testamento que será responsável por aprovar a configuração.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-144">Configuration approver name is the name of the Epic system administrator who will be responsible for approving the configuration.</span></span>

  ![O nome do aprovador de configuração é selecionado em uma lista no conector EHR.](../../media/ehc-provider-1.png)

### <a name="verify-and-approve-the-configuration"></a>[<span data-ttu-id="4d2e2-146">Verificar e aprovar a configuração</span><span class="sxs-lookup"><span data-stu-id="4d2e2-146">Verify and approve the configuration</span></span>](#verify-and-approve-the-configuration)

<span data-ttu-id="4d2e2-147">O administrador do testamento da sua organização de assistência médica que foi adicionado como Aprovador agora deve usar a mesma URL do conector EHR da etapa anterior para entrar usando as credenciais do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-147">The Epic administrator for your healthcare organization who was added as an approver must now use the same EHR Connector URL from the previous step to sign in using their Microsoft 365 credentials.</span></span> <span data-ttu-id="4d2e2-148">Após a validação bem-sucedida, o aprovador será solicitado a entrar usando suas credenciais do testamento para validar a organização do testamento.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-148">After successful validation, the approver is going to be asked to sign in using their Epic credentials to validate the Epic organization.</span></span>

> [!Note]
> <span data-ttu-id="4d2e2-149">O administrador do Microsoft 365 e o administrador do testamento em suas organizações podem ser a mesma pessoa.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-149">The Microsoft 365 admin and Epic admin in your organizations can be the same person.</span></span> <span data-ttu-id="4d2e2-150">Nesse caso, adicione seu próprio nome de usuário como Aprovador na primeira etapa.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-150">In that case, add your own username as approver in the first step.</span></span> <span data-ttu-id="4d2e2-151">Você ainda precisa entrar no testamento para validar seu acesso.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-151">You'll still need to sign in to Epic to validate your access.</span></span> <span data-ttu-id="4d2e2-152">O testamento entrar é usado apenas para validar a URL base do FHIR.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-152">The Epic sign in is only used to validate your FHIR base URL.</span></span> <span data-ttu-id="4d2e2-153">A Microsoft não irá armazenar credenciais nem acessar dados do EHR com esta entrada.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-153">Microsoft will not store credentials or access EHR data with this sign in.</span></span>

  ![Verificar e aprovar a configuração de credenciais.](../../media/ehc-provider-2.png)

<span data-ttu-id="4d2e2-155">Após uma testamento de entrada bem-sucedida, o administrador do testamento **deve** aprovar a configuração.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-155">After a successful Epic sign in, the Epic administrator **must** approve the configuration.</span></span> <span data-ttu-id="4d2e2-156">Se a configuração não estiver correta, o administrador do Microsoft 365 terá a capacidade de modificar as configurações originais entrando no portal do conector do EHR da Microsoft novamente.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-156">If the configuration isn't correct, the Microsoft 365 admin will have the ability to modify the original configurations by signing in to the Microsoft EHR Connector portal again.</span></span>

![Confirme se o conector EHR está configurado e opção para alterar a configuração.](../../media/ehc-approve-3.png)

### <a name="review-and-finish-the-configuration"></a>[<span data-ttu-id="4d2e2-158">Revisar e concluir a configuração</span><span class="sxs-lookup"><span data-stu-id="4d2e2-158">Review and finish the configuration</span></span>](#review-and-finish-the-configuration)

<span data-ttu-id="4d2e2-159">Quando as informações de configuração forem aprovadas pelo administrador do testamento, você será apresentado aos registros de integração do lançamento de pacientes e fornecedores.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-159">When the configuration information is approved by the Epic administrator, you'll be presented with integration records for patient and provider launch.</span></span> <span data-ttu-id="4d2e2-160">Esses registros são necessários para concluir a configuração de visita virtual no testamento.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-160">These records are necessary to complete the virtual visit configuration in Epic.</span></span> <span data-ttu-id="4d2e2-161">Para obter mais detalhes, consulte o guia de integração do Epic-Microsoft Teams telehealth.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-161">Refer to the Epic-Microsoft Teams Telehealth Integration guide for more details.</span></span>

> [!Note]  
> <span data-ttu-id="4d2e2-162">A qualquer momento, o administrador do Microsoft 365 ou testamento pode entrar no portal de configuração para ver os registros de integração e modificar a configuração da organização, se necessário.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-162">At any time the Microsoft 365 or Epic administrator can sign in to the configuration portal to view integration records and modify organization configuration, if needed.</span></span>

![As informações de integração são exibidas.](../../media/ehc-final-config-4.png)

## <a name="launch-teams-virtual-visits"></a><span data-ttu-id="4d2e2-164">Iniciar visitas virtuais ao Teams</span><span class="sxs-lookup"><span data-stu-id="4d2e2-164">Launch Teams virtual visits</span></span>

<span data-ttu-id="4d2e2-165">Depois de concluir as etapas do conector EHR e a configuração do testamento, sua organização está pronta para dar suporte a visitas com vídeo com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-165">After completing the EHR Connector steps and Epic configuration, your organization is ready to support video visits with Microsoft Teams.</span></span>

### <a name="virtual-visit-prerequisites"></a><span data-ttu-id="4d2e2-166">Pré-requisitos de visita virtual</span><span class="sxs-lookup"><span data-stu-id="4d2e2-166">Virtual visit prerequisites</span></span>

- <span data-ttu-id="4d2e2-167">Seus sistemas devem atender todos os [pré-requisitos do software e do navegador](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span><span class="sxs-lookup"><span data-stu-id="4d2e2-167">Your systems must meet all [software and browser prerequisites](https://docs.microsoft.com/microsoftteams/hardware-requirements-for-the-teams-app).</span></span>

- <span data-ttu-id="4d2e2-168">A organização de assistência médica deve ter concluído a configuração entre a organização do testamento e a organização do Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-168">Healthcare organization must have completed the setup between the Epic organization and Microsoft 365 organization.</span></span>

### <a name="provider-experience"></a><span data-ttu-id="4d2e2-169">Experiência do provedor</span><span class="sxs-lookup"><span data-stu-id="4d2e2-169">Provider experience</span></span>

<span data-ttu-id="4d2e2-170">Provedores de assistência médica da sua organização também podem ingressar em visitas virtuais ao Microsoft Teams de seus aplicativos de provedor de Testamento (hiperespacial, Haiku, canto).</span><span class="sxs-lookup"><span data-stu-id="4d2e2-170">Healthcare providers from your organization can also join virtual visits with Microsoft Teams from their Epic provider applications (Hyperspace, Haiku, Canto).</span></span> <span data-ttu-id="4d2e2-171">O botão **Iniciar visita virtual** é inserido no fluxo do provedor.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-171">The **Begin virtual visit** button is embedded in the provider flow.</span></span>

<span data-ttu-id="4d2e2-172">Principais recursos da experiência do provedor:</span><span class="sxs-lookup"><span data-stu-id="4d2e2-172">Key features of the provider experience:</span></span>

- <span data-ttu-id="4d2e2-173">Provedores podem ingressar em visitas virtuais usando navegadores com suporte ou o aplicativo Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-173">Providers can join virtual visits using supported browsers or the Microsoft Teams application.</span></span>

- <span data-ttu-id="4d2e2-174">Os provedores devem fazer uma única entrada com a conta do Microsoft 365 ao ingressar em uma visita virtual pela primeira vez.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-174">Providers must do a one time sign in with their Microsoft 365 account when joining a virtual visit for the first time.</span></span>

- <span data-ttu-id="4d2e2-175">Após o logon único, o provedor será levado diretamente ao compromisso virtual no Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-175">After the one time sign in, the provider will be taken straight to the virtual appointment in Microsoft Teams.</span></span> <span data-ttu-id="4d2e2-176">(O provedor deve estar conectado ao Microsoft Teams).</span><span class="sxs-lookup"><span data-stu-id="4d2e2-176">(Provider must be signed-in to Microsoft Teams).</span></span>

- <span data-ttu-id="4d2e2-177">O provedor pode ver atualizações em tempo real dos participantes se conectam e se desconectam de um determinado compromisso.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-177">Provider can see real-time updates of participants connect and disconnect for a given appointment.</span></span> <span data-ttu-id="4d2e2-178">O provedor pode ver quando o paciente está conectado a uma visita virtual.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-178">The provider can see when the patient is connected to a virtual visit.</span></span>

  ![Experiência do provedor de uma visita virtual com o paciente](../../media/ehc-provider-experience-6.png)

### <a name="patient-experience"></a><span data-ttu-id="4d2e2-180">Experiência do paciente</span><span class="sxs-lookup"><span data-stu-id="4d2e2-180">Patient experience</span></span>

<span data-ttu-id="4d2e2-181">O conector dá suporte a pacientes que ingressam em visitas virtuais por meio de myChart Web e Mobile.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-181">The connector supports patients joining virtual visits through MyChart web and mobile.</span></span> <span data-ttu-id="4d2e2-182">No momento do compromisso, os pacientes podem iniciar uma visita virtual em mycharting usando o botão **Iniciar visita virtual** .</span><span class="sxs-lookup"><span data-stu-id="4d2e2-182">At the time of the appointment, patients can start a virtual visit from MyChart using the **Begin virtual visit** button.</span></span>

<span data-ttu-id="4d2e2-183">Principais recursos da experiência do paciente:</span><span class="sxs-lookup"><span data-stu-id="4d2e2-183">Key features of the patient experience:</span></span>

- <span data-ttu-id="4d2e2-184">Os pacientes podem ingressar em visitas virtuais de navegadores modernos na área de trabalho e dispositivos móveis sem a instalação do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-184">Patients can join virtual visits from modern web browsers on desktop and mobile without app installation.</span></span>

- <span data-ttu-id="4d2e2-185">Os pacientes podem ingressar em visitas virtuais com um único clique, e não há nenhuma conta adicional ou uma assinatura necessária.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-185">Patients can join virtual visits with a single click and there is no additional account or sign in required.</span></span>

- <span data-ttu-id="4d2e2-186">Não é necessário ter pacientes para criar uma conta da Microsoft ou entrar para iniciar uma visita virtual.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-186">Patients aren't required to create a Microsoft account or sign in to launch a virtual visit.</span></span>

- <span data-ttu-id="4d2e2-187">Os pacientes serão colocados em um lobby até que o provedor de assistência médica ingresse no compromisso e os inscreva para a visita virtual.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-187">Patients will be placed in a lobby until the healthcare provider joins the appointment and admits them to the virtual visit.</span></span>

- <span data-ttu-id="4d2e2-188">O teste do vídeo e do microfone está disponível no lobby antes de ingressar na visita virtual.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-188">Testing of the video and microphone is available in the lobby before joining the virtual visit.</span></span>

  ![Experiência de paciente da visita virtual](../../media/ehc-virtual-visit-5.png)

> [!Note]
> <span data-ttu-id="4d2e2-190">Testamento, myChart, Haiku e canto são marcas comerciais da testamento Systems Corporation.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-190">Epic, MyChart, Haiku, and Canto are trademarks of Epic Systems Corporation.</span></span>

### <a name="privacy-and-location-of-data"></a><span data-ttu-id="4d2e2-191">Privacidade e localização de dados</span><span class="sxs-lookup"><span data-stu-id="4d2e2-191">Privacy and location of data</span></span>

<span data-ttu-id="4d2e2-192">A integração de equipes em sistemas EHR otimiza a quantidade de dados que estão sendo usados e armazenados durante os fluxos de visita e de integração virtual.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-192">Teams integration into EHR systems optimizes the amount of data being used and stored during integration and virtual visit flows.</span></span> <span data-ttu-id="4d2e2-193">A solução segue os princípios e as diretrizes gerais de privacidade e gerenciamento de dados da equipe descritos na privacidade da equipe.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-193">The solution follows the overall Teams privacy and data management principles and guidelines outlined in Teams Privacy.</span></span>

<span data-ttu-id="4d2e2-194">O conector EHR do Microsoft Teams não armazena nem transfere nenhum dado pessoal identificável ou quaisquer registros de integridade de pacientes ou provedores de assistência médica do sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-194">The Microsoft Teams EHR connector doesn't store nor transfer any identifiable personal data or any health records of patients or healthcare providers from the EHR system.</span></span> <span data-ttu-id="4d2e2-195">Os únicos dados armazenados pelo conector EHR é a ID exclusiva do usuário do EHR, que é usada durante a configuração da reunião do teams.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-195">The only data that is stored by the EHR connector is the EHR user’s unique ID, which is used during Teams meeting setup.</span></span> <span data-ttu-id="4d2e2-196">A ID exclusiva do usuário do EHR é armazenada em uma das três regiões geográficas descritas no [local onde os seus dados do cliente do Microsoft 365 estão armazenados](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) .</span><span class="sxs-lookup"><span data-stu-id="4d2e2-196">The EHR user’s unique ID is stored in one of the three geographic regions described in the [Where your Microsoft 365 customer data is stored](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations?view=o365-worldwide#data-center-geographies) article.</span></span> <span data-ttu-id="4d2e2-197">Todas as mensagens de chat, gravações e outros dados inseridos no Teams pelos participantes da reunião são armazenados de acordo com as políticas de armazenamento existentes.</span><span class="sxs-lookup"><span data-stu-id="4d2e2-197">All chat, recordings, and other data entered into Teams by the meeting participants are stored according to existing storage policies.</span></span> <span data-ttu-id="4d2e2-198">Se você quiser saber mais sobre o local dos dados no Microsoft Teams, acesse [locais de dados no Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span><span class="sxs-lookup"><span data-stu-id="4d2e2-198">If you want to learn more information on the location of data in Microsoft Teams, visit [Locations of data in Teams](https://docs.microsoft.com/microsoftteams/location-of-data-in-teams).</span></span>
