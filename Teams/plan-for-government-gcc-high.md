---
title: Implantações do Microsoft 365 Government - GCC High
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Diretrizes para profissionais de IT para impulsionar implantações do Office 365 em entidades que lidam com dados sujeitos à regulamentação do governo dos EUA.
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
ms.openlocfilehash: ced9f5cc68ce18bc7e1670db4031ff85b7c76ff2
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909265"
---
# <a name="plan-for-office-365-government---gcc-high-deployments"></a><span data-ttu-id="5ae7e-103">Plano para implantações do Office 365 Government - GCC High</span><span class="sxs-lookup"><span data-stu-id="5ae7e-103">Plan for Office 365 Government - GCC High deployments</span></span>

<span data-ttu-id="5ae7e-104">Essa orientação é para profissionais de IT que conduzem implantações do Office 365 em entidades do governo federal dos EUA ou outras entidades que lidam com dados sujeitos a regulamentações e requisitos governamentais, em que o uso do Office 365 Government – GCC High é apropriado para atender a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="5ae7e-105">Se sua organização já tiver atendido aos requisitos de alta qualificação do Office 365 Government – GCC High e aplicado e aceito no programa, você pode ignorar as etapas 1 e 2 e ir diretamente para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-105">If your organization has already met the Office 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="5ae7e-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-106">Step 1.</span></span> <span data-ttu-id="5ae7e-107">Determine se sua organização precisa do Office 365 Government - GCC High e atende aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-107">Determine whether your organization needs Office 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="5ae7e-108">O ambiente Office 365 Government - GCC High fornece conformidade com os requisitos do governo dos EUA para serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-108">The Office 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="5ae7e-109">Além de aproveitar os recursos e recursos do Office 365, as organizações se beneficiam dos seguintes recursos exclusivos do Office 365 Government – GCC High:</span><span class="sxs-lookup"><span data-stu-id="5ae7e-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – GCC High:</span></span>

- <span data-ttu-id="5ae7e-110">O conteúdo do cliente da sua organização é logicamente separado do conteúdo do cliente nos serviços comerciais do Office 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="5ae7e-111">O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="5ae7e-112">O acesso ao conteúdo do cliente da sua organização está restrito ao pessoal da Microsoft com tela.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="5ae7e-113">Office 365 Government – GCC High atende às certificações e aos credenciamentos necessários para clientes do Setor Público dos EUA.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-113">Office 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="5ae7e-114">Você pode encontrar mais informações sobre a oferta do Office 365 Government – GCC High para clientes do governo dos EUA em planos do [Office 365 Government,](https://products.office.com/government/compare-office-365-government-plans)incluindo requisitos [de qualificação.](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements)</span><span class="sxs-lookup"><span data-stu-id="5ae7e-114">You can find more information about the Office 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="5ae7e-115">A descrição do serviço do Governo dos EUA do [Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) descreve os benefícios da plataforma, que são centralizados em atender aos requisitos de conformidade nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="5ae7e-116">Talvez você queira transferir as tabelas de informações na descrição do serviço para uma planilha do Excel e adicionar duas colunas: Relevantes para minha organização **Y/N** e atender às necessidades da minha organização **Y/N.**</span><span class="sxs-lookup"><span data-stu-id="5ae7e-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="5ae7e-117">Em seguida, você pode revisar essa lista com seus colegas para confirmar que esse serviço atende às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5ae7e-119">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="5ae7e-119">Decision points</span></span>|<ul><li><span data-ttu-id="5ae7e-120">Decida se o Office 365 Government - GCC High é apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-120">Decide whether Office 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="5ae7e-121">Confirme se sua organização atende aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="5ae7e-122">O Office 365 Government - GCC High só está disponível nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-122">Office 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="5ae7e-123">Clientes do governo dos EUA podem escolher entre vários planos [do Office 365 Government.](https://products.office.com/en/government/compare-office-365-government-plans)</span><span class="sxs-lookup"><span data-stu-id="5ae7e-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---gcc-high"></a><span data-ttu-id="5ae7e-124">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-124">Step 2.</span></span> <span data-ttu-id="5ae7e-125">Aplicar ao Office 365 Government – GCC High</span><span class="sxs-lookup"><span data-stu-id="5ae7e-125">Apply for Office 365 Government - GCC High</span></span>

<span data-ttu-id="5ae7e-126">Tendo decidido que esse serviço é o certo para sua organização, inicie o processo [de aplicação desse serviço.](https://products.office.com/government/eligibility-validation)</span><span class="sxs-lookup"><span data-stu-id="5ae7e-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="5ae7e-127">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-127">Step 3.</span></span> <span data-ttu-id="5ae7e-128">Entenda as configurações de segurança padrão do Office 365 Government - GCC High.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-128">Understand Office 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="5ae7e-129">Recomendamos que você tenha tempo [](enable-features-office-365.md) para revisar cuidadosamente as configurações de segurança e administrador antes de modificá-las e considerar os impactos na conformidade antes de fazer alterações nas configurações de segurança padrão.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5ae7e-131">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="5ae7e-131">Decision point</span></span>|<ul><li><span data-ttu-id="5ae7e-132">Decida se você precisará modificar qualquer uma das configurações padrão do Office 365 Government - GCC High security settings, resolvendo primeiro entender o impacto de quaisquer alterações que você possa fazer.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-132">Decide whether you'll need to modify any of the default Office 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---gcc-high"></a><span data-ttu-id="5ae7e-133">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-133">Step 4.</span></span> <span data-ttu-id="5ae7e-134">Compreender quais recursos do Teams estão disponíveis no Momento no Office 365 Government – GCC High</span><span class="sxs-lookup"><span data-stu-id="5ae7e-134">Understand which Teams capabilities are currently available in Office 365 Government - GCC High</span></span>

<span data-ttu-id="5ae7e-135">Para acomodar os requisitos de nossos clientes de nuvem do governo, existem algumas diferenças entre o Teams no Office 365 Government – GCC High e o Teams nos planos Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="5ae7e-136">Confira a tabela a seguir para ver quais recursos estão disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="5ae7e-137">Descrição do serviço microsoft teams</span><span class="sxs-lookup"><span data-stu-id="5ae7e-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="5ae7e-138">Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-138">Step 5.</span></span> <span data-ttu-id="5ae7e-139">Plano de gestão</span><span class="sxs-lookup"><span data-stu-id="5ae7e-139">Plan for governance</span></span>

<span data-ttu-id="5ae7e-140">Determine seus requisitos de governança e como você pode atender a eles.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="5ae7e-141">Vá para [Plano de governança no Teams](plan-teams-governance.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="5ae7e-142">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="5ae7e-142">Decision point</span></span> |<ul><li><span data-ttu-id="5ae7e-143">Determine e documente seus requisitos de gestão, seguindo as diretrizes no [Plano de governança no Teams.](plan-teams-governance.md)</span><span class="sxs-lookup"><span data-stu-id="5ae7e-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="5ae7e-144">Etapa 6.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-144">Step 6.</span></span> <span data-ttu-id="5ae7e-145">Implantar o Teams para colaboração</span><span class="sxs-lookup"><span data-stu-id="5ae7e-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="5ae7e-146">Depois de integração com o Office 365 Government – GCC High, siga o caminho de implantação recomendado descrito em Como lançar [o Microsoft Teams.](How-to-roll-out-teams.md)</span><span class="sxs-lookup"><span data-stu-id="5ae7e-146">After you've been onboarded to Office 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="5ae7e-147">Certifique-se de interagir com sua equipe de Adoção e Gerenciamento de Alterações e os campeões do Teams.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="5ae7e-148">Você também pode trabalhar com [o FastTrack ou](https://www.microsoft.com/fasttrack) seu parceiro escolhido para integrar o serviço.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="5ae7e-149">O cliente do Mac Teams para ambientes GCCH ainda não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="5ae7e-149">The Mac Teams client for GCCH environments is not yet supported.</span></span>

