---
title: Microsoft 365 Governo - GCC implantações de Alta
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Diretrizes para os profissionais de Office 365 <2> <1> implantações em entidades que lidam com dados sujeitos à regulamentação governamental dos EUA.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 9e5f8df087ca7ad999a9756467925be68c60e96f
ms.sourcegitcommit: 90615674e9703aa5ea32be64ab3638aa30e83127
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2021
ms.locfileid: "52718052"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a><span data-ttu-id="a56c1-103">Plan for Office 365 Government - GCC High deployments</span><span class="sxs-lookup"><span data-stu-id="a56c1-103">Plan for Office 365 Government - GCC High deployments</span></span>

<span data-ttu-id="a56c1-104">Essa orientação é para profissionais de IT que estão conduzindo implantações do Office 365 em entidades do governo federal dos EUA ou outras entidades que lidam com dados sujeitos a regulamentos e requisitos do governo, onde o uso do Office 365 Government – GCC High é apropriado para atender a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="a56c1-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="a56c1-105">Se sua organização já tiver atendido aos requisitos de Office 365 Government – GCC alta qualificação e aplicadas e aceitas no programa, você poderá ignorar as etapas 1 e 2 e ir diretamente para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="a56c1-105">If your organization has already met the Office 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="a56c1-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="a56c1-106">Step 1.</span></span> <span data-ttu-id="a56c1-107">Determine se sua organização precisa Office 365 Government - GCC Alta e atende aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="a56c1-107">Determine whether your organization needs Office 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="a56c1-108">O Office 365 Government - GCC ambiente High fornece conformidade com os requisitos do governo dos EUA para serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="a56c1-108">The Office 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="a56c1-109">Além de aproveitar os recursos e recursos do Office 365, as organizações se beneficiam dos seguintes recursos exclusivos da Office 365 Government – GCC Alta:</span><span class="sxs-lookup"><span data-stu-id="a56c1-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – GCC High:</span></span>

- <span data-ttu-id="a56c1-110">O conteúdo do cliente da sua organização é logicamente segregado do conteúdo do cliente nos serviços comerciais Office 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a56c1-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="a56c1-111">O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="a56c1-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="a56c1-112">O acesso ao conteúdo do cliente da sua organização é restrito à equipe da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a56c1-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="a56c1-113">Office 365 Government – GCC Alta está em conformidade com certificações e acreditações necessárias para clientes do Setor Público dos EUA.</span><span class="sxs-lookup"><span data-stu-id="a56c1-113">Office 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="a56c1-114">Você pode encontrar mais informações sobre a Office 365 Government – GCC alta oferta para clientes do Governo dos EUA em planos [Office 365 Government,](https://products.office.com/government/compare-office-365-government-plans)incluindo requisitos [de qualificação.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="a56c1-114">You can find more information about the Office 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="a56c1-115">A [Office 365 descrição do](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) serviço do Governo dos EUA descreve os benefícios da plataforma, que são centralizados em atender aos requisitos de conformidade nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="a56c1-115">The [Office 365 US Government service description](/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="a56c1-116">Talvez você queira transferir as tabelas de informações na descrição do serviço para uma Excel de trabalho e adicionar duas colunas: relevantes para minha organização **Y/N** e atende às necessidades da minha organização **Y/N**.</span><span class="sxs-lookup"><span data-stu-id="a56c1-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="a56c1-117">Em seguida, você pode revisar essa lista com seus colegas para confirmar se esse serviço atende às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="a56c1-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="a56c1-119">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="a56c1-119">Decision points</span></span>|<ul><li><span data-ttu-id="a56c1-120">Decida se Office 365 Government - GCC High é apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="a56c1-120">Decide whether Office 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="a56c1-121">Confirme se sua organização atende aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="a56c1-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="a56c1-122">Office 365 Government - GCC High só está disponível nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="a56c1-122">Office 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="a56c1-123">Os clientes do Governo não-EUA podem escolher entre vários Office 365 Government [planos.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="a56c1-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---gcc-high"></a><span data-ttu-id="a56c1-124">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="a56c1-124">Step 2.</span></span> <span data-ttu-id="a56c1-125">Aplicar para Office 365 Government - GCC Alta</span><span class="sxs-lookup"><span data-stu-id="a56c1-125">Apply for Office 365 Government - GCC High</span></span>

<span data-ttu-id="a56c1-126">Depois de decidir que esse serviço é o correto para sua organização, inicie o processo de [solicitação para esse serviço.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="a56c1-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="a56c1-127">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="a56c1-127">Step 3.</span></span> <span data-ttu-id="a56c1-128">Entenda Office 365 Government - GCC configurações de segurança padrão alta.</span><span class="sxs-lookup"><span data-stu-id="a56c1-128">Understand Office 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="a56c1-129">Recomendamos que você tenha tempo [](enable-features-office-365.md) para analisar cuidadosamente suas configurações de administração e segurança antes de modificá-las e considerar os impactos na conformidade antes de fazer alterações nas configurações de segurança padrão.</span><span class="sxs-lookup"><span data-stu-id="a56c1-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="a56c1-131">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="a56c1-131">Decision point</span></span>|<ul><li><span data-ttu-id="a56c1-132">Decida se você precisará modificar qualquer uma das configurações padrão de Office 365 Government - GCC alta segurança, resolvendo primeiro entender o impacto de quaisquer alterações que você possa fazer.</span><span class="sxs-lookup"><span data-stu-id="a56c1-132">Decide whether you'll need to modify any of the default Office 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a><span data-ttu-id="a56c1-133">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="a56c1-133">Step 4.</span></span> <span data-ttu-id="a56c1-134">Entenda quais Teams recursos estão disponíveis atualmente no Office 365 Government - GCC High</span><span class="sxs-lookup"><span data-stu-id="a56c1-134">Understand which Teams capabilities are currently available in Office 365 Government - GCC High</span></span>

<span data-ttu-id="a56c1-135">Para acomodar os requisitos de nossos clientes de nuvem governamental, há algumas diferenças entre o Teams no Office 365 Government - GCC High e Teams nos planos Enterprise.</span><span class="sxs-lookup"><span data-stu-id="a56c1-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="a56c1-136">Consulte a tabela a seguir para ver quais recursos estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="a56c1-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="a56c1-137">Microsoft Teams de serviço</span><span class="sxs-lookup"><span data-stu-id="a56c1-137">Microsoft Teams service description</span></span>](/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="a56c1-138">Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="a56c1-138">Step 5.</span></span> <span data-ttu-id="a56c1-139">Plano de governança</span><span class="sxs-lookup"><span data-stu-id="a56c1-139">Plan for governance</span></span>

<span data-ttu-id="a56c1-140">Determine seus requisitos de governança e como você pode atender a eles.</span><span class="sxs-lookup"><span data-stu-id="a56c1-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="a56c1-141">Acesse [Plan for governance in Teams](plan-teams-governance.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a56c1-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="a56c1-142">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="a56c1-142">Decision point</span></span> |<ul><li><span data-ttu-id="a56c1-143">Determine e documente seus requisitos de governança, seguindo as diretrizes em [Plan for governance in Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="a56c1-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="a56c1-144">Etapa 6.</span><span class="sxs-lookup"><span data-stu-id="a56c1-144">Step 6.</span></span> <span data-ttu-id="a56c1-145">Implantar Teams colaboração</span><span class="sxs-lookup"><span data-stu-id="a56c1-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="a56c1-146">Depois de ter sido internado para Office 365 Government – GCC Alta, siga o caminho de implantação recomendado descrito em [How to roll out Microsoft Teams](./deploy-overview.md).</span><span class="sxs-lookup"><span data-stu-id="a56c1-146">After you've been onboarded to Office 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](./deploy-overview.md).</span></span> <span data-ttu-id="a56c1-147">Certifique-se de se envolver com sua equipe de Gerenciamento de Alterações e adoção e Teams campeões.</span><span class="sxs-lookup"><span data-stu-id="a56c1-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="a56c1-148">Você também pode trabalhar com [o FastTrack ou](https://www.microsoft.com/fasttrack) seu parceiro escolhido para integração ao serviço.</span><span class="sxs-lookup"><span data-stu-id="a56c1-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>
