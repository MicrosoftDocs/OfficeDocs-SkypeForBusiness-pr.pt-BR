---
title: Office 365 implantação do governo do Office
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Orientação para profissionais de ti para conduzir as implantações do Office 365 em entidades que lidam com os dados sujeitos a normas do governo dos EUA
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
- remotework
appliesto:
- Microsoft Teams
ms.openlocfilehash: 2fb916b30a26694debf8d699fc05cc3fcc8c8c77
ms.sourcegitcommit: 43d66693f6f08d4dcade0095bf613240031fec56
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/06/2020
ms.locfileid: "46581242"
---
# <a name="plan-for-office-365-government---gcc-deployments"></a><span data-ttu-id="c626a-103">Plano para implantações do governo do Office 365-GCC</span><span class="sxs-lookup"><span data-stu-id="c626a-103">Plan for Office 365 Government - GCC deployments</span></span>

<span data-ttu-id="c626a-104">Esta orientação é para os profissionais de ti que estão conduzindo implantações do Office 365 em entidades federais, estaduais, tribal ou outras entidades do governo dos EUA, que lidam com os dados sujeitos a normas e requisitos governamentais, em que o uso do Office 365 governo-GCC é adequado para atender a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="c626a-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="c626a-105">Novidades de 26 de março de 2020: não perca o nosso [Guia de início rápido para download para gcc](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span><span class="sxs-lookup"><span data-stu-id="c626a-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c626a-106">O Microsoft Teams está experimentando um grande pico em chamadas online e videoconferência/videoconferência devido ao coronavirus (COVID-19) Pandemic.</span><span class="sxs-lookup"><span data-stu-id="c626a-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="c626a-107">Em resposta ao aumento sem precedente em chamadas e para garantir a continuidade e a disponibilidade, a Microsoft está permitindo que os servidores de áudio/vídeo do Microsoft Teams GCC aproveitem a capacidade de processamento em nossos datacenters comerciais, bem como nos datacenters governamentais.</span><span class="sxs-lookup"><span data-stu-id="c626a-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="c626a-108">Esses servidores de áudio/vídeo residem nos servidores de limite de capacitação alta do Microsoft Azure FedRAMP nos Estados Unidos e não armazenam qualquer conteúdo do cliente.</span><span class="sxs-lookup"><span data-stu-id="c626a-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="c626a-109">No entanto, esses servidores estão processando áudio e vídeo para chamadas e conferências e estão operando em nossos funcionários comerciais durante esse período provisório.</span><span class="sxs-lookup"><span data-stu-id="c626a-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="c626a-110">Qualificado, o pessoal em tela está monitorando esses servidores para obter acesso potencial a dados dos clientes ao analisar os logs interativos para esses servidores.</span><span class="sxs-lookup"><span data-stu-id="c626a-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="c626a-111">Os funcionários qualificados atendem aos requisitos de GCC para acessar o conteúdo do cliente.</span><span class="sxs-lookup"><span data-stu-id="c626a-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="c626a-112">Para obter detalhes sobre requisitos de triagem, consulte a [Descrição de serviço gcc](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span><span class="sxs-lookup"><span data-stu-id="c626a-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="c626a-113">Obrigado pelo seu suporte, pois seguimos as etapas para garantir que nossos serviços permaneçam disponíveis e confiáveis nestes momentos extraordinários.</span><span class="sxs-lookup"><span data-stu-id="c626a-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="c626a-114">Se sua organização já atendeu aos requisitos de qualificação do governo do Office 365 e se aplicou e foi aceito no programa, você pode ignorar as etapas 1 e 2 e ir diretamente para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="c626a-114">If your organization has already met the Office 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="c626a-115">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="c626a-115">Step 1.</span></span> <span data-ttu-id="c626a-116">Determine se a sua organização precisa do Office 365 governo-GCC e atenda aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="c626a-116">Determine whether your organization needs Office 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="c626a-117">O ambiente governamental do Office 365-GCC fornece conformidade com os requisitos governamentais dos EUA para serviços de nuvem, incluindo FedRAMP moderado e requisitos para justiça criminal e sistemas de informação federal fiscal (tipos de dados CJI e FTI).</span><span class="sxs-lookup"><span data-stu-id="c626a-117">The Office 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="c626a-118">Além de desfrutar dos recursos e funcionalidades do Office 365, as organizações se beneficiam dos seguintes recursos exclusivos do Office 365 governo-GCC:</span><span class="sxs-lookup"><span data-stu-id="c626a-118">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government - GCC:</span></span>

-   <span data-ttu-id="c626a-119">O conteúdo do cliente da sua organização é logicamente segregado do conteúdo do cliente nos serviços comerciais do Office 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="c626a-119">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
-   <span data-ttu-id="c626a-120">O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="c626a-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="c626a-121">O acesso ao conteúdo do cliente da sua organização está restrito ao pessoal da Microsoft em tela.</span><span class="sxs-lookup"><span data-stu-id="c626a-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="c626a-122">O Office 365-GCC está em conformidade com certificações e capacitações necessárias para clientes do setor público dos EUA.</span><span class="sxs-lookup"><span data-stu-id="c626a-122">Office 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="c626a-123">Você pode encontrar mais informações sobre a oferta do Office 365 governo-GCC para clientes do governo dos EUA em [planos do governo do office 365](https://products.office.com/government/compare-office-365-government-plans), incluindo [requisitos de qualificação](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="c626a-123">You can find more information about the Office 365 Government - GCC offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="c626a-124">A [Descrição do serviço governo dos EUA do Office 365](https://technet.microsoft.com/library/mt774581.aspx) descreve os benefícios da plataforma, que são centralizados em relação aos requisitos de conformidade nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="c626a-124">The [Office 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="c626a-125">Talvez você queira transferir as tabelas de informações na descrição do serviço para uma pasta de trabalho do Excel e adicionar duas colunas: **pertinentes para minha organização y/n** e **atender às necessidades da minha organização y/n**.</span><span class="sxs-lookup"><span data-stu-id="c626a-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="c626a-126">Em seguida, você pode revisar essa lista com seus colegas para confirmar que esse serviço atende às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c626a-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c626a-128">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="c626a-128">Decision points</span></span>|<ul><li><span data-ttu-id="c626a-129">Decida se o Office 365 governo-GCC é apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="c626a-129">Decide whether Office 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="c626a-130">Confirme se a sua organização atende aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="c626a-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="c626a-131">O Office 365 governo-GCC só está disponível nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="c626a-131">Office 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="c626a-132">Os clientes do governo dos EUA podem escolher entre vários [planos governamentais do Office 365](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="c626a-132">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-office-365-government---gcc"></a><span data-ttu-id="c626a-133">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="c626a-133">Step 2.</span></span> <span data-ttu-id="c626a-134">Aplicar para o Office 365 governo-GCC</span><span class="sxs-lookup"><span data-stu-id="c626a-134">Apply for Office 365 Government - GCC</span></span>

<span data-ttu-id="c626a-135">Decidisse que esse serviço é ideal para sua organização, inicie o processo de [aplicação deste serviço aqui](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="c626a-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-office-365-government---gcc-default-security-settings"></a><span data-ttu-id="c626a-136">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="c626a-136">Step 3.</span></span> <span data-ttu-id="c626a-137">Compreenda as configurações de segurança padrão do governo do Office 365-GCC.</span><span class="sxs-lookup"><span data-stu-id="c626a-137">Understand Office 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="c626a-138">Recomendamos que você leve tempo para revisar cuidadosamente suas [configurações de administrador e de segurança](enable-features-office-365.md) antes de modificá-las e considerar o impacto sobre a conformidade antes de fazer qualquer alteração nas configurações de segurança padrão.</span><span class="sxs-lookup"><span data-stu-id="c626a-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c626a-140">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="c626a-140">Decision point</span></span>|<ul><li><span data-ttu-id="c626a-141">Decida se você modificará qualquer uma das configurações de segurança do governo padrão do Office 365, resolvendo para primeiro entender o impacto das alterações que você pode fazer.</span><span class="sxs-lookup"><span data-stu-id="c626a-141">Decide whether you'll modify any of the default Office 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="c626a-142">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="c626a-142">Step 4.</span></span> <span data-ttu-id="c626a-143">Compreenda quais recursos estão indisponíveis no momento ou desabilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="c626a-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="c626a-144">Para acomodar os requisitos de nossos clientes de nuvem governamental, há algumas diferenças entre os planos do Office 365 para os EUA e os planos corporativos.</span><span class="sxs-lookup"><span data-stu-id="c626a-144">To accommodate the requirements of our government cloud customers, there are some differences between Office 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="c626a-145">Consulte a tabela a seguir para ver os recursos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="c626a-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="c626a-146">Descrição do serviço do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="c626a-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="c626a-147">Depois que outras cargas de trabalho estiverem totalmente disponíveis na nuvem GCC, elas serão disponibilizadas no Teams quando todo o trabalho adicional de integração for concluído.</span><span class="sxs-lookup"><span data-stu-id="c626a-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c626a-149">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="c626a-149">Decision point</span></span>|<ul><li><span data-ttu-id="c626a-150">Decida se o conjunto de recursos do teams atende às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="c626a-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="c626a-151">Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="c626a-151">Step 5.</span></span> <span data-ttu-id="c626a-152">Plano de governança</span><span class="sxs-lookup"><span data-stu-id="c626a-152">Plan for governance</span></span>

<span data-ttu-id="c626a-153">Determine suas necessidades de governança e como você pode atendê-las.</span><span class="sxs-lookup"><span data-stu-id="c626a-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="c626a-154">Vá para [plano de governança no Teams](plan-teams-governance.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="c626a-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="c626a-156">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="c626a-156">Decision point</span></span>|<ul><li><span data-ttu-id="c626a-157">Determine e documente seus requisitos de governança, seguindo as diretrizes de [plano de controle no Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="c626a-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="c626a-158">Etapa 6.</span><span class="sxs-lookup"><span data-stu-id="c626a-158">Step 6.</span></span> <span data-ttu-id="c626a-159">Implantar equipes para colaboração</span><span class="sxs-lookup"><span data-stu-id="c626a-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="c626a-160">Depois de ter sido integrado ao Office 365 governo – GCC, siga o caminho de implantação recomendado descrito em [como implantar o Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="c626a-160">After you've been onboarded to Office 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="c626a-161">Não deixe de entrar em contato com sua equipe de adoção e gerenciamento de mudanças e especialistas do teams.</span><span class="sxs-lookup"><span data-stu-id="c626a-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="c626a-162">Você também pode trabalhar com o [FastTrack](https://www.microsoft.com/fasttrack) ou o parceiro escolhido para onboard do serviço.</span><span class="sxs-lookup"><span data-stu-id="c626a-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="c626a-163">Etapa 7.</span><span class="sxs-lookup"><span data-stu-id="c626a-163">Step 7.</span></span> <span data-ttu-id="c626a-164">Implantar equipes para reuniões e voz</span><span class="sxs-lookup"><span data-stu-id="c626a-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="c626a-165">Também é um ótimo momento para usar o Microsoft Teams com seu grupo de Stakeholder mais largo para começar a planejar reuniões e [recursos de voz na nuvem](cloud-voice-deployment.md).</span><span class="sxs-lookup"><span data-stu-id="c626a-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

