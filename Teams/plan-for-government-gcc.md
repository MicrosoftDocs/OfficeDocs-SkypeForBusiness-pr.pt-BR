---
title: Implantações do Microsoft 365 Government - GCC
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Diretrizes para profissionais de IT para impulsionar implantações do Microsoft 365 em entidades que lidam com dados sujeitos à regulamentação do governo dos EUA
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
ms.openlocfilehash: e40f511aedfed2423e04ece74a9c2c7f370acb74
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085605"
---
# <a name="plan-for-microsoft-365-government---gcc-deployments"></a><span data-ttu-id="5f056-103">Planejar implantações do Microsoft 365 Government - GCC</span><span class="sxs-lookup"><span data-stu-id="5f056-103">Plan for Microsoft 365 Government - GCC deployments</span></span>

<span data-ttu-id="5f056-104">Essa orientação é para profissionais de IT que conduzem implantações do Microsoft 365 em entidades governamentais federais, estaduais, locais, locais, ltda ou metais ou outras entidades que lidam com dados sujeitos a requisitos e regulamentações governamentais, em que o uso do Microsoft 365 Government – GCC é apropriado para atender a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="5f056-104">This guidance is for IT pros who are driving deployments of Microsoft 365 in US federal, state, local, tribal, or territorial government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government - GCC is appropriate to meet these requirements.</span></span> <span data-ttu-id="5f056-105">Novo 26 de março de 2020: Não perca nosso guia de Início Rápido para [GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true)para download.</span><span class="sxs-lookup"><span data-stu-id="5f056-105">New March 26, 2020: Don't miss our downloadable [Quick Start guide for GCC](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/Quick-Start-Guide-for-GCC.pdf?raw=true).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5f056-106">O Microsoft Teams está enfrentando um grande aumento em chamadas online e conferência de áudio/vídeo devido à pandímica (COVID-19).</span><span class="sxs-lookup"><span data-stu-id="5f056-106">Microsoft Teams is experiencing a tremendous spike in online calls and audio/video conferencing due to the coronavirus (COVID-19) pandemic.</span></span><br/>
> 
><span data-ttu-id="5f056-107">Em resposta ao aumento indevida de chamadas e para garantir a continuidade e a disponibilidade, a Microsoft está permitindo que os servidores de áudio/vídeo do Microsoft Teams aproveitem a capacidade de processamento em nossos datacenters comerciais, bem como em nossos datacenters governamentais.</span><span class="sxs-lookup"><span data-stu-id="5f056-107">In response to the unprecedented increase in calls, and to ensure continuity and availability, Microsoft is allowing Microsoft Teams GCC audio/video servers to leverage processing capacity in our commercial datacenters, as well as in our government datacenters.</span></span><br/>
> 
><span data-ttu-id="5f056-108">Esses servidores de áudio/vídeo residem nos servidores de limite de alto credenciamento do Microsoft Azure FedRAMP nos Estados Unidos e não armazenam conteúdo do cliente.</span><span class="sxs-lookup"><span data-stu-id="5f056-108">These audio/video servers reside within the Microsoft Azure FedRAMP High accreditation boundary servers in the United States and do not store any customer content.</span></span> <span data-ttu-id="5f056-109">No entanto, esses servidores estão processando áudio e vídeo para chamadas e conferências e estão funcionando sob nossa equipe comercial durante esse período provisório.</span><span class="sxs-lookup"><span data-stu-id="5f056-109">However, these servers are processing audio and video for calls and conferences and are operating under our commercial staff during this interim period.</span></span><br/>
> 
><span data-ttu-id="5f056-110">Equipes qualificadas e com tela estão monitorando esses servidores para possíveis acessos aos dados do cliente, revendo os logoff interativos desses servidores.</span><span class="sxs-lookup"><span data-stu-id="5f056-110">Qualified, screened personnel are monitoring these servers for potential access to customer data by reviewing any interactive log-ons to these servers.</span></span> <span data-ttu-id="5f056-111">As pessoas qualificadas atendem aos requisitos de GCC para acesso ao conteúdo do cliente.</span><span class="sxs-lookup"><span data-stu-id="5f056-111">Qualified personnel meet GCC requirements for access to customer content.</span></span> <span data-ttu-id="5f056-112">Para obter detalhes sobre requisitos de seleção, consulte a descrição [do serviço GCC.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc)</span><span class="sxs-lookup"><span data-stu-id="5f056-112">For details about screening requirements, see the [GCC service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/gcc).</span></span><br/>
> 
><span data-ttu-id="5f056-113">Obrigado por seu suporte à medida que tomarmos medidas para garantir que nossos serviços permaneçam disponíveis e confiáveis nesses tempos excepcionalmente.</span><span class="sxs-lookup"><span data-stu-id="5f056-113">Thank you for your support as we take steps to ensure that our services remain available and reliable in these extraordinary times.</span></span><br/>


> [!NOTE]
> <span data-ttu-id="5f056-114">Se sua organização já atendeu aos requisitos de qualificação do Microsoft 365 Government - GCC e se aplicou e foi aceita no programa, você pode ignorar as etapas 1 e 2 e ir diretamente para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="5f056-114">If your organization has already met the Microsoft 365 Government - GCC eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span> 

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-and-meets-eligibility-requirements"></a><span data-ttu-id="5f056-115">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="5f056-115">Step 1.</span></span> <span data-ttu-id="5f056-116">Determine se sua organização precisa do Microsoft 365 Government - GCC e atende aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="5f056-116">Determine whether your organization needs Microsoft 365 Government - GCC and meets eligibility requirements.</span></span> 

<span data-ttu-id="5f056-117">O ambiente Microsoft 365 Government - GCC fornece conformidade com os requisitos do governo dos EUA para serviços de nuvem, incluindo FedRAMP Moderado e requisitos para sistemas de informações fiscais criminais e federais (tipos de dados CJI e FTI).</span><span class="sxs-lookup"><span data-stu-id="5f056-117">The Microsoft 365 Government - GCC environment provides compliance with US government requirements for cloud services, including FedRAMP Moderate, and requirements for criminal justice and federal tax information systems (CJI and FTI data types).</span></span>

<span data-ttu-id="5f056-118">Além de aproveitar os recursos e recursos do Microsoft 365, as organizações se beneficiam com os seguintes recursos exclusivos do Microsoft 365 Government - GCC:</span><span class="sxs-lookup"><span data-stu-id="5f056-118">In addition to enjoying the features and capabilities of Microsoft 365, organizations benefit from the following features that are unique to Microsoft 365 Government - GCC:</span></span>

-   <span data-ttu-id="5f056-119">O conteúdo do cliente da sua organização é logicamente separado do conteúdo do cliente nos serviços comerciais do Microsoft 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5f056-119">Your organization's customer content is logically segregated from customer content in the commercial Microsoft 365 services from Microsoft.</span></span>
-   <span data-ttu-id="5f056-120">O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5f056-120">Your organization's customer content is stored within the United States.</span></span>
-   <span data-ttu-id="5f056-121">O acesso ao conteúdo do cliente da sua organização está restrito ao pessoal da Microsoft com tela.</span><span class="sxs-lookup"><span data-stu-id="5f056-121">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
-   <span data-ttu-id="5f056-122">Microsoft 365 Government - GCC atende às certificações e aos credenciamentos necessários para clientes do Setor Público dos EUA.</span><span class="sxs-lookup"><span data-stu-id="5f056-122">Microsoft 365 Government - GCC complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="5f056-123">Você pode encontrar mais informações sobre a oferta do Microsoft 365 Government - GCC para clientes do governo dos EUA em planos do [Microsoft 365 Government,](https://products.office.com/government/compare-office-365-government-plans)incluindo requisitos [de qualificação.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="5f056-123">You can find more information about the Microsoft 365 Government - GCC offering for US Government customers at [Microsoft 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="5f056-124">A descrição do serviço do [Microsoft 365 US Government](https://technet.microsoft.com/library/mt774581.aspx) descreve os benefícios da plataforma, que são centralizados em torno de atender aos requisitos de conformidade nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5f056-124">The [Microsoft 365 US Government service description](https://technet.microsoft.com/library/mt774581.aspx) describes the platform's benefits, which are centered around meeting compliance requirements within the United States.</span></span>

> [!Tip]
> <span data-ttu-id="5f056-125">Talvez você queira transferir as tabelas de informações na descrição do serviço para uma planilha do Excel e adicionar duas colunas: Relevantes para minha organização **Y/N** e atender às necessidades da minha organização **Y/N.**</span><span class="sxs-lookup"><span data-stu-id="5f056-125">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="5f056-126">Em seguida, você pode revisar essa lista com seus colegas para confirmar que esse serviço atende às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5f056-126">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>

|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5f056-128">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="5f056-128">Decision points</span></span>|<ul><li><span data-ttu-id="5f056-129">Decida se o Microsoft 365 Government - GCC é apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="5f056-129">Decide whether Microsoft 365 Government - GCC is appropriate for your organization.</span></span></li><li><span data-ttu-id="5f056-130">Confirme se sua organização atende aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="5f056-130">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="5f056-131">O Microsoft 365 Government - GCC só está disponível nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5f056-131">Microsoft 365 Government - GCC is only available in the United States.</span></span> <span data-ttu-id="5f056-132">Clientes do governo dos EUA podem escolher entre vários planos [do Microsoft 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="5f056-132">Non–US Government customers can choose from a number of [Microsoft 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>


## <a name="step-2-apply-for-microsoft-365-government---gcc"></a><span data-ttu-id="5f056-133">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="5f056-133">Step 2.</span></span> <span data-ttu-id="5f056-134">Aplicar ao Microsoft 365 Government - GCC</span><span class="sxs-lookup"><span data-stu-id="5f056-134">Apply for Microsoft 365 Government - GCC</span></span>

<span data-ttu-id="5f056-135">Tendo decidido que esse serviço é o certo para sua organização, inicie o processo [de aplicação desse serviço aqui.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="5f056-135">Having decided that this service is right for your organization, start the process of [applying for this service here](https://products.office.com/government/eligibility-validation).</span></span>

## <a name="step-3-understand-microsoft-365-government---gcc-default-security-settings"></a><span data-ttu-id="5f056-136">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="5f056-136">Step 3.</span></span> <span data-ttu-id="5f056-137">Entenda as configurações de segurança padrão do Microsoft 365 Government - GCC.</span><span class="sxs-lookup"><span data-stu-id="5f056-137">Understand Microsoft 365 Government - GCC default security settings.</span></span>

<span data-ttu-id="5f056-138">Recomendamos que você tenha tempo [](enable-features-office-365.md) para revisar cuidadosamente as configurações de segurança e administrador antes de modificá-las e considerar os impactos na conformidade antes de fazer alterações nas configurações de segurança padrão.</span><span class="sxs-lookup"><span data-stu-id="5f056-138">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5f056-140">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="5f056-140">Decision point</span></span>|<ul><li><span data-ttu-id="5f056-141">Decida se você modificará alguma das configurações de segurança padrão do Microsoft 365 Government - GCC, resolvendo primeiro entender o impacto das alterações que você pode fazer.</span><span class="sxs-lookup"><span data-stu-id="5f056-141">Decide whether you'll modify any of the default Microsoft 365 Government - GCC security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |

## <a name="step-4-understand-which-capabilities-are-currently-unavailable-or-disabled-by-default"></a><span data-ttu-id="5f056-142">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="5f056-142">Step 4.</span></span> <span data-ttu-id="5f056-143">Entenda quais recursos estão indisponíveis ou desabilitados por padrão.</span><span class="sxs-lookup"><span data-stu-id="5f056-143">Understand which capabilities are currently unavailable or disabled by default.</span></span>

<span data-ttu-id="5f056-144">Para acomodar os requisitos de nossos clientes de nuvem do governo, existem algumas diferenças entre os planos Microsoft 365 Government - GCC e Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5f056-144">To accommodate the requirements of our government cloud customers, there are some differences between Microsoft 365 Government - GCC and Enterprise plans.</span></span> <span data-ttu-id="5f056-145">Confira a tabela a seguir para ver quais recursos estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5f056-145">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="5f056-146">Descrição do serviço microsoft teams</span><span class="sxs-lookup"><span data-stu-id="5f056-146">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

> [!Note]
> <span data-ttu-id="5f056-147">Quando outras cargas de trabalho estão totalmente disponíveis na nuvem GCC, elas se tornarão disponíveis no Teams quando todo o trabalho de integração adicional for concluído.</span><span class="sxs-lookup"><span data-stu-id="5f056-147">Once other workloads are fully available in the GCC cloud, then they will become available in Teams when all additional  integration work is completed.</span></span>


|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5f056-149">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="5f056-149">Decision point</span></span>|<ul><li><span data-ttu-id="5f056-150">Decida se o conjunto de recursos do Teams atende às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5f056-150">Decide whether the Teams feature set meets your organization's needs.</span></span></li></ul> |

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="5f056-151">Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="5f056-151">Step 5.</span></span> <span data-ttu-id="5f056-152">Plano de gestão</span><span class="sxs-lookup"><span data-stu-id="5f056-152">Plan for governance</span></span>

<span data-ttu-id="5f056-153">Determine seus requisitos de governança e como você pode atender a eles.</span><span class="sxs-lookup"><span data-stu-id="5f056-153">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="5f056-154">Vá para [Plano de governança no Teams](plan-teams-governance.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5f056-154">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5f056-156">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="5f056-156">Decision point</span></span>|<ul><li><span data-ttu-id="5f056-157">Determine e documente seus requisitos de gestão, seguindo as diretrizes no [Plano de governança no Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="5f056-157">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span></li></ul> |

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="5f056-158">Etapa 6.</span><span class="sxs-lookup"><span data-stu-id="5f056-158">Step 6.</span></span> <span data-ttu-id="5f056-159">Implantar o Teams para colaboração</span><span class="sxs-lookup"><span data-stu-id="5f056-159">Deploy Teams for collaboration</span></span>

<span data-ttu-id="5f056-160">Depois de integração com o Microsoft 365 Government – GCC, siga o caminho de implantação recomendado descrito em [Como lançar o Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="5f056-160">After you've been onboarded to Microsoft 365 Government – GCC, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="5f056-161">Certifique-se de interagir com sua equipe de Adoção e Gerenciamento de Alterações e os campeões do Teams.</span><span class="sxs-lookup"><span data-stu-id="5f056-161">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="5f056-162">Você também pode trabalhar com [o FastTrack ou](https://www.microsoft.com/fasttrack) seu parceiro escolhido para integrar o serviço.</span><span class="sxs-lookup"><span data-stu-id="5f056-162">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

## <a name="step-7-deploy-teams-for-meetings-and-voice"></a><span data-ttu-id="5f056-163">Etapa 7.</span><span class="sxs-lookup"><span data-stu-id="5f056-163">Step 7.</span></span> <span data-ttu-id="5f056-164">Implantar o Teams para reuniões e voz</span><span class="sxs-lookup"><span data-stu-id="5f056-164">Deploy Teams for meetings and voice</span></span>

<span data-ttu-id="5f056-165">Este também é um ótimo momento para usar o Teams com seu grupo de participantes mais amplo para começar a planejar a implantação de reuniões e recursos [de voz na nuvem.](cloud-voice-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="5f056-165">This is also a great time to use Teams with your wider stakeholder group to start planning for rolling out meetings and [cloud voice features](cloud-voice-deployment.md).</span></span>

