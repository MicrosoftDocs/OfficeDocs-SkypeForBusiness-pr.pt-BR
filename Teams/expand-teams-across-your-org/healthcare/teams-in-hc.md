---
title: Introdução ao Teams para Organizações de Saúde
author: jambirk
ms.author: jambirk
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
search.appverid: MET150
localization_priority: Normal
MS.collection: Teams_ITAdmin_PracticalGuidance
appliesto:
- Microsoft Teams
ms.reviewer: ''
description: Introdução ao Teams para Organizações de Saúde
ms.openlocfilehash: 7f68a21e835edb3b5ebcd8ff794f4fd3d0716bee
ms.sourcegitcommit: cf2cb5b7e03385b33e34a5ff89719adb882525b1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/06/2019
ms.locfileid: "33632280"
---
# <a name="get-started-with-teams-for-healthcare-organizations"></a><span data-ttu-id="1a64c-103">Introdução ao Teams para Organizações de Saúde</span><span class="sxs-lookup"><span data-stu-id="1a64c-103">Get started with Teams for Healthcare organizations</span></span>

<span data-ttu-id="1a64c-104">Teams da Microsoft oferece vários recursos úteis para hospitais e outras organizações de saúde.</span><span class="sxs-lookup"><span data-stu-id="1a64c-104">Microsoft Teams offers a number of features useful for hospitals and other Healthcare organizations.</span></span> <span data-ttu-id="1a64c-105">Recursos de equipes estão em desenvolvimento para auxiliar hospitais com:</span><span class="sxs-lookup"><span data-stu-id="1a64c-105">Teams features are under development to aid hospitals with:</span></span>

- <span data-ttu-id="1a64c-106">Coordenação de atendimento médico</span><span class="sxs-lookup"><span data-stu-id="1a64c-106">Care Coordination</span></span>
- <span data-ttu-id="1a64c-107">Mensagens seguras</span><span class="sxs-lookup"><span data-stu-id="1a64c-107">Secure Messaging</span></span>
- <span data-ttu-id="1a64c-108">Integração de atendimento médico Record (EHR) eletrônicos</span><span class="sxs-lookup"><span data-stu-id="1a64c-108">Electronic Healthcare Record (EHR) integration</span></span>
- <span data-ttu-id="1a64c-109">Integração de trabalhador de Firstline</span><span class="sxs-lookup"><span data-stu-id="1a64c-109">Firstline Worker integration</span></span>

## <a name="care-coordination---microsoft-teams-patients-app"></a><span data-ttu-id="1a64c-110">Equipes de atendimento médico coordenação - Microsoft app os pacientes</span><span class="sxs-lookup"><span data-stu-id="1a64c-110">Care Coordination - Microsoft Teams Patients app</span></span>

[!INCLUDE [preview-feature](../../includes/preview-feature.md)]

<span data-ttu-id="1a64c-111">Microsoft Teams agora possui uma solução de coordenação de atendimento médico específica para as organizações de saúde para ajudá-los a atender às sua objetivo final de fornecer o melhor aos pacientes.</span><span class="sxs-lookup"><span data-stu-id="1a64c-111">Microsoft Teams now has a care coordination solution specific to healthcare organizations to help them meet their ultimate goal of providing the best patient care.</span></span> <span data-ttu-id="1a64c-112">O x da solução de coordenação de atendimento médico, o aplicativo de pacientes de equipes da Microsoft, é um aplicativo de guia de terceiros primeiro que integra com sistemas de (EHR) registros saúde eletrônicos usando uma interface de recursos de interoperabilidade de atendimento médico Fast ([FHIR](https://www.hl7.org/fhir/)) para trazer valiosos informações médicas em Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a64c-112">The crux of the care coordination solution, the  Microsoft Teams Patients app, is a first party tab app that integrates with electronic health record (EHR) systems using a Fast Healthcare Interoperability Resources ([FHIR](https://www.hl7.org/fhir/)) interface to bring valuable medical information into Microsoft Teams.</span></span>  

<span data-ttu-id="1a64c-113">A solução de coordenação de atendimento médico pode estabelecer interface com fornecedores de Software independentes (ISVs) que o aplicativo de pacientes podem se conectar aos seus sistemas EHR usando existente padrões de dados de integridade, como HL7v2 e FHIR.</span><span class="sxs-lookup"><span data-stu-id="1a64c-113">The care coordination solution can interface with leading Independent Software Vendors (ISVs) that can connect the Patients app to your EHR systems using existing health data standards like HL7v2 and FHIR.</span></span> <span data-ttu-id="1a64c-114">Parceiros do Microsoft com as seguintes líderes do setor para estabelecer a integração de registros de saúde eletrônicos com equipes:</span><span class="sxs-lookup"><span data-stu-id="1a64c-114">Microsoft partners with the following industry leaders to establish electronic health record integration with Teams:</span></span>

- <span data-ttu-id="1a64c-115">Datica (por meio da oferta seus [CMI](https://datica.com/compliant-managed-integration/) )</span><span class="sxs-lookup"><span data-stu-id="1a64c-115">Datica (through their [CMI](https://datica.com/compliant-managed-integration/) offering)</span></span>
- <span data-ttu-id="1a64c-116">Informações Cloverleaf (pela [Ponte de FHIR informações](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span><span class="sxs-lookup"><span data-stu-id="1a64c-116">Infor Cloverleaf (through the [Infor FHIR Bridge](https://pages.infor.com/hcl-infor-fhir-bridge-brochure.html))</span></span>
- <span data-ttu-id="1a64c-117">Redox (por meio do [R ^ server FHIR](https://www.redoxengine.com/fhir/))</span><span class="sxs-lookup"><span data-stu-id="1a64c-117">Redox (through the [R^FHIR server](https://www.redoxengine.com/fhir/))</span></span>
- <span data-ttu-id="1a64c-118">Dapasoft (por meio de [Corolar em FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span><span class="sxs-lookup"><span data-stu-id="1a64c-118">Dapasoft (through [Corolar on FHIR](https://www.dapasoft.com/corolar-fhir-server-for-microsoft-teams/))</span></span>

<span data-ttu-id="1a64c-119">Uma integração EHR e interoperabilidade parceiro tentando implementar Teams da Microsoft para uma organização de assistência médica precisa fornecer o aplicativo de pacientes uma conexão segura e autenticada com sistemas EHR da organização de assistência médica.</span><span class="sxs-lookup"><span data-stu-id="1a64c-119">An EHR integration and interop partner trying to implement Microsoft Teams for a healthcare provider organization needs to provide the Patients app a secure and authenticated connection with the healthcare provider organization's EHR systems.</span></span> <span data-ttu-id="1a64c-120">Isso permite que o fluxo de (somente leitura) one-direcional dos pacientes registros relevantes no aplicativo os pacientes.</span><span class="sxs-lookup"><span data-stu-id="1a64c-120">This enables the one-directional (Read only) flow of the relevant patient records into to the Patients app.</span></span> <span data-ttu-id="1a64c-121">O aplicativo de pacientes entende o formato FHIR, portanto, o parceiro também é responsável por transformar os dados agregados de vários outros formatos como HL7v2, etc. em FHIR DSTU2 ou STU3.</span><span class="sxs-lookup"><span data-stu-id="1a64c-121">The Patients app understands the FHIR format, so the partner is also responsible for transforming the aggregated data from various other formats like HL7v2, etc. into FHIR DSTU2 or STU3.</span></span>

<br>

![Integração do EHR](../../media/ehr-1.png)

<br>

<span data-ttu-id="1a64c-123">O aplicativo de pacientes se integra com sistemas de registros (EHR) de saúde eletrônicos e permite que se preocupar provedores para se comunicar sobre do paciente em tempo real dentro da plataforma segura das equipes.</span><span class="sxs-lookup"><span data-stu-id="1a64c-123">The Patients app integrates with electronic health records (EHR) systems and enables care providers to communicate about patient care in real-time within Teams’ secure platform.</span></span> <span data-ttu-id="1a64c-124">O aplicativo de pacientes é o primeiro grande investimento na área de coordenação de atendimento médico que pretende resolver os seguintes desafios:</span><span class="sxs-lookup"><span data-stu-id="1a64c-124">The Patients app is the first major investment in the care coordination area which aims to address the following challenges:</span></span>

- <span data-ttu-id="1a64c-125">Baixa eficiência em transferências e comunicação crítica por meio de experiência do paciente</span><span class="sxs-lookup"><span data-stu-id="1a64c-125">Low efficiency in hand-offs and critical communication through the patient experience</span></span>
- <span data-ttu-id="1a64c-126">Silos informações que cria a carga administrativa</span><span class="sxs-lookup"><span data-stu-id="1a64c-126">Siloed information that creates administrative burdens</span></span>
- <span data-ttu-id="1a64c-127">Insatisfação entre os clínicos com ferramentas de colaboração complexa e fragmentado</span><span class="sxs-lookup"><span data-stu-id="1a64c-127">Dissatisfaction among clinicians with complex and fragmented collaboration tools</span></span>
- <span data-ttu-id="1a64c-128">Coordenação de atendimento médico de pessoal ineficientes que pode gravar a hora de início de estudos clínicos muito cara</span><span class="sxs-lookup"><span data-stu-id="1a64c-128">Inefficient in-person care coordination that can burn too much expensive clinical time</span></span>

<span data-ttu-id="1a64c-129">Microsoft Teams permite que os médicos, os médicos, enfermeiros e outros funcionários colaborar com eficiência por:</span><span class="sxs-lookup"><span data-stu-id="1a64c-129">Microsoft Teams enables physicians, clinicians, nurses, and other staff to collaborate efficiently by:</span></span>

- <span data-ttu-id="1a64c-130">Sendo parte de uma única equipe virtualizada que funciona e colabora em documentos do Office</span><span class="sxs-lookup"><span data-stu-id="1a64c-130">Being part of a single virtualized team that works and collaborates on Office documents</span></span>
- <span data-ttu-id="1a64c-131">Ter conversas persistentes sobre pacientes diferentes que precisam de atenção</span><span class="sxs-lookup"><span data-stu-id="1a64c-131">Having persistent conversations about different patients needing attention</span></span>
- <span data-ttu-id="1a64c-132">Usando canais com guias como uma maneira de estruturar seu trabalho, com a ajuda adicional de guias aos quais eles podem fixar fontes de informações</span><span class="sxs-lookup"><span data-stu-id="1a64c-132">Using channels with tabs as a way to structure their work, with additional help from tabs to which they can pin information sources</span></span>
- <span data-ttu-id="1a64c-133">Usando reuniões de canal com o poder do áudio de equipes, vídeo, compartilhamento de tela, gravação e recursos de transcrição para gerenciar reuniões diárias</span><span class="sxs-lookup"><span data-stu-id="1a64c-133">Using channel meetings with the power of Teams audio, video, screen sharing, recording, and transcription features to manage daily meetings</span></span>
- <span data-ttu-id="1a64c-134">Usando o aplicativo de pacientes para curate uma lista de alto risco pacientes que devem ser monitoradas e extrai seus detalhes mais recentes do sistema EHR.</span><span class="sxs-lookup"><span data-stu-id="1a64c-134">Using the Patients app to curate a list of high-risk patients that must be monitored, and pulls their latest details from the EHR system.</span></span> <span data-ttu-id="1a64c-135">O aplicativo de pacientes próprio adiciona os seguintes recursos para Teams da Microsoft:</span><span class="sxs-lookup"><span data-stu-id="1a64c-135">The Patients app itself adds the following features to Microsoft Teams:</span></span>

    - <span data-ttu-id="1a64c-136">Capacidade de criar vários paciente lista dentro de um único canal.</span><span class="sxs-lookup"><span data-stu-id="1a64c-136">Ability to create multiple patient lists within a single channel.</span></span>
    - <span data-ttu-id="1a64c-137">Capacidade de visualizar e classificar as informações exibidas sobre os pacientes através de colunas configuráveis.</span><span class="sxs-lookup"><span data-stu-id="1a64c-137">Ability to view and sort information displayed about patients through configurable columns.</span></span>
    - <span data-ttu-id="1a64c-138">Capacidade de autoprovisionar o aplicativo por meio de um modelo de equipe.</span><span class="sxs-lookup"><span data-stu-id="1a64c-138">Ability to auto-provision the app through a team template.</span></span>
    - <span data-ttu-id="1a64c-139">Disponível em aplicativo equipes para iOS e Android para profissionais de saúde móveis primeiro, bem como o cliente de desktop e web Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="1a64c-139">Available on the Teams App for iOS and Android for mobile first healthcare workers as well as Microsoft Teams web and desktop client.</span></span>
    - <span data-ttu-id="1a64c-140">Suporte para as versões de FHIR DSTU2 e STU3 por meio de análise de declaração de conformidade.</span><span class="sxs-lookup"><span data-stu-id="1a64c-140">Support for FHIR DSTU2 and STU3 versions via parsing of conformance statement.</span></span>
    - <span data-ttu-id="1a64c-141">Logs de auditoria para todas as ações de exibir e pesquisar em sua interface de usuário para a proteção pi por diretrizes HIPAA.</span><span class="sxs-lookup"><span data-stu-id="1a64c-141">Audit Logs for all view and search actions on its user interface to safeguard PHI per HIPAA guidelines.</span></span>

<span data-ttu-id="1a64c-142">O aplicativo de pacientes é criado na plataforma de extensibilidade de equipes e aproveita a estrutura de guias para exibir conteúdo de pacientes rico dentro de um canal.</span><span class="sxs-lookup"><span data-stu-id="1a64c-142">The Patients app is built on the Teams extensibility platform and takes advantage of the Tabs framework to display rich patient content within a channel.</span></span> <span data-ttu-id="1a64c-143">Para saber mais sobre a própria plataforma e de outros aplicativos de equipes, consulte [Apps para equipes da Microsoft](/microsoftteams/platform/concepts/apps/apps-overview).</span><span class="sxs-lookup"><span data-stu-id="1a64c-143">To learn more about other Teams apps and the platform itself, please see [Apps for Microsoft Teams](/microsoftteams/platform/concepts/apps/apps-overview).</span></span>  

> [!NOTE]
> <span data-ttu-id="1a64c-144">O aplicativo de pacientes está no modo de visualização particular e a interface FHIR está em beta.</span><span class="sxs-lookup"><span data-stu-id="1a64c-144">The Patients app is in private preview and the FHIR interface is in beta.</span></span> <span data-ttu-id="1a64c-145">Versões lançadas não deverão ser compatíveis com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="1a64c-145">Released versions are not expected to be backward compatible.</span></span>

![Captura de tela de app os pacientes](../../media/ehr-2.png)

<span data-ttu-id="1a64c-147">Consulte [Integrando registros de saúde eletrônicos em equipes da Microsoft](patients-app.md) para obter detalhes de implementação.</span><span class="sxs-lookup"><span data-stu-id="1a64c-147">See [Integrating Electronic Healthcare Records into Microsoft Teams](patients-app.md) for implementation details,.</span></span>

## <a name="templates"></a><span data-ttu-id="1a64c-148">Modelos</span><span class="sxs-lookup"><span data-stu-id="1a64c-148">Templates</span></span>

<span data-ttu-id="1a64c-149">Novos modelos para a criação de equipes foram desenvolvidos para aplicar a hospitalares e mais esperados em breve.</span><span class="sxs-lookup"><span data-stu-id="1a64c-149">New templates for creating Teams were developed to apply to a Hospital setting, and more are expected soon.</span></span> <span data-ttu-id="1a64c-150">Isso facilita criar equipes usado por profissionais de saúde para coordenar o atendimento médico para pacientes em vários departamentos ou alas.</span><span class="sxs-lookup"><span data-stu-id="1a64c-150">This makes it easier to create Teams that Healthcare workers use to coordinate care for patients in various departments or wards.</span></span> <span data-ttu-id="1a64c-151">Consulte o [guia de Introdução com modelos de equipes para organizações de saúde](healthcare-templates.md).</span><span class="sxs-lookup"><span data-stu-id="1a64c-151">See [Get started with Teams templates for Healthcare organizations](healthcare-templates.md).</span></span> <span data-ttu-id="1a64c-152">As equipes podem ser iniciadas para departamentos internos, como cardiologia, ou para alas de atendimento médico, e mais modelos estão em desenvolvimento.</span><span class="sxs-lookup"><span data-stu-id="1a64c-152">Teams can be started for internal departments such as cardiology, or for care wards, and more templates are in development.</span></span>

## <a name="secure-messaging"></a><span data-ttu-id="1a64c-153">Mensagens seguras</span><span class="sxs-lookup"><span data-stu-id="1a64c-153">Secure Messaging</span></span>

<span data-ttu-id="1a64c-154">Colaboração de suporte a mensagens em equipes de atendimento médico, incluindo vários novos recursos de segurança:</span><span class="sxs-lookup"><span data-stu-id="1a64c-154">Secure messaging supports collaboration within care teams, including several new features:</span></span>

- <span data-ttu-id="1a64c-155">O remetente da mensagem pode definir uma prioridade especial para a sua mensagem, para que o destinatário será notificado repetidamente até que eles devem ler a mensagem.</span><span class="sxs-lookup"><span data-stu-id="1a64c-155">A message sender can set a special priority for their message, so the recipient is repeatedly notified until they read the message.</span></span>
- <span data-ttu-id="1a64c-156">O remetente da mensagem pode solicitar uma confirmação de leitura, para que sejam notificados quando uma mensagem enviados por eles foi lido pelo remetente da mensagem.</span><span class="sxs-lookup"><span data-stu-id="1a64c-156">A message sender can request a read receipt, so they are notified when a message they sent was read by the message recipient.</span></span>

<span data-ttu-id="1a64c-157">Juntos, esses recursos permitem atenção mais rápida às mensagens urgentes e confiança que a mensagem foi recebida e ler.</span><span class="sxs-lookup"><span data-stu-id="1a64c-157">Together, these features allow quicker attention to urgent messages and confidence that the message was received and read.</span></span> <span data-ttu-id="1a64c-158">Novo equipes de atendimento médico usando esses recursos podem ser criadas em uma base por pacientes.</span><span class="sxs-lookup"><span data-stu-id="1a64c-158">New care teams using these features can be created on a per-patient basis.</span></span> <span data-ttu-id="1a64c-159">Esses recursos são baseadas na diretiva e podem ser atribuídos aos indivíduos ou equipes inteiros.</span><span class="sxs-lookup"><span data-stu-id="1a64c-159">These features are policy-based, and can be assigned to individuals or entire Teams.</span></span>

<span data-ttu-id="1a64c-160">Para obter mais detalhes, consulte [Introdução ao Secure Messaging políticas para as organizações de saúde](messaging-policies-hc.md) .</span><span class="sxs-lookup"><span data-stu-id="1a64c-160">See [Get started with Secure Messaging policies for Healthcare organizations](messaging-policies-hc.md) for further details.</span></span>

## <a name="firstline-worker-integration"></a><span data-ttu-id="1a64c-161">Integração de trabalhador de Firstline</span><span class="sxs-lookup"><span data-stu-id="1a64c-161">Firstline Worker integration</span></span>

<span data-ttu-id="1a64c-162">Microsoft Teams se integra ao trabalhador Firstline, que pode ser usado para coordenar shift recursos de pessoal e mais.</span><span class="sxs-lookup"><span data-stu-id="1a64c-162">Microsoft Teams integrates with Firstline Worker, which can be used to coordinate shift staffing features and more.</span></span>

 <span data-ttu-id="1a64c-163">Consulte os seguintes artigos:</span><span class="sxs-lookup"><span data-stu-id="1a64c-163">See the following articles:</span></span>

- [<span data-ttu-id="1a64c-164">Mover suas equipes da Microsoft StaffHub para mudanças na Teams da Microsoft</span><span class="sxs-lookup"><span data-stu-id="1a64c-164">Move your Microsoft StaffHub teams to Shifts in Microsoft Teams</span></span>](../shifts/move-staffhub-teams-to-shifts-in-teams.md)

- [<span data-ttu-id="1a64c-165">Gerencie o aplicativo Turnos para sua organização no Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1a64c-165">Manage the Shifts app for your organization in Microsoft Teams</span></span>](../shifts/manage-the-shifts-app-for-your-organization-in-teams.md)
