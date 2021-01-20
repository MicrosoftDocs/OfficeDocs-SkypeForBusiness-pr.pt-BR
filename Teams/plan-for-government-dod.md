---
title: Implantação do governo do Office 365 – implementações do DoD
author: SerdarSoysal
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: daro
audience: admin
description: Orientação para profissionais de ti para conduzir implantações do Office 365 em entidades que lidam com os dados sujeitos a normas do governo dos EUA.
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
ms.openlocfilehash: 954eb24cd0d6c79ab3fd30e22521660d2afeb08e
ms.sourcegitcommit: fdef9b52247097e5cae64f01b6b2b710c5b203cf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/20/2021
ms.locfileid: "49909155"
---
# <a name="plan-for-office-365-government---dod-deployments"></a><span data-ttu-id="85b63-103">Plano para implantações do Office 365 governo-DoD</span><span class="sxs-lookup"><span data-stu-id="85b63-103">Plan for Office 365 Government - DoD deployments</span></span>

<span data-ttu-id="85b63-104">Esta orientação é para os profissionais de ti que estão impulsionando implantações do Office 365 em entidades governamentais federais dos EUA ou outras entidades que lidam com os dados sujeitos a normas e requisitos governamentais, em que o uso do governo do Office 365 – DoD é adequado para atender a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="85b63-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Office 365 Government – DoD is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="85b63-105">Se a sua organização já atendeu aos requisitos de qualificação do governo do Office 365 e se aplicou e foi aceito no programa, você pode ignorar as etapas 1 e 2 e ir diretamente para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="85b63-105">If your organization has already met the Office 365 Government – DoD eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-office-365-government---dod-and-meets-eligibility-requirements"></a><span data-ttu-id="85b63-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="85b63-106">Step 1.</span></span> <span data-ttu-id="85b63-107">Determine se a sua organização precisa do Office 365 governo-DoD e atenda aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="85b63-107">Determine whether your organization needs Office 365 Government - DoD and meets eligibility requirements.</span></span> 

<span data-ttu-id="85b63-108">O ambiente governo/governo do Office 365 fornece conformidade com os requisitos governamentais dos EUA para serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="85b63-108">The Office 365 Government - DoD environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="85b63-109">Além de desfrutar dos recursos e funcionalidades do Office 365, as organizações se beneficiam dos seguintes recursos exclusivos do Office 365 governo – DoD:</span><span class="sxs-lookup"><span data-stu-id="85b63-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Office 365 Government – DoD:</span></span>

- <span data-ttu-id="85b63-110">O conteúdo do cliente da sua organização é logicamente segregado do conteúdo do cliente nos serviços comerciais do Office 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="85b63-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="85b63-111">O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="85b63-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="85b63-112">O acesso ao conteúdo do cliente da sua organização está restrito ao pessoal da Microsoft em tela.</span><span class="sxs-lookup"><span data-stu-id="85b63-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="85b63-113">O governo do Office 365 – DoD está em conformidade com certificações e capacitações necessárias para clientes do setor público dos EUA.</span><span class="sxs-lookup"><span data-stu-id="85b63-113">Office 365 Government – DoD complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="85b63-114">Você pode encontrar mais informações sobre o governo do Office 365 – ofertas do governo dos EUA para clientes do governo dos EUA em [planos do governo do office 365](https://products.office.com/government/compare-office-365-government-plans), incluindo [requisitos de qualificação](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="85b63-114">You can find more information about the Office 365 Government – DoD offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="85b63-115">A [Descrição do serviço governo dos EUA do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) descreve as vantagens da plataforma, que são centralizadas em requisitos de conformidade de reunião nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="85b63-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="85b63-116">Talvez você queira transferir as tabelas de informações na descrição do serviço para uma pasta de trabalho do Excel e adicionar duas colunas: **pertinentes para minha organização y/n** e **atender às necessidades da minha organização y/n**.</span><span class="sxs-lookup"><span data-stu-id="85b63-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="85b63-117">Em seguida, você pode revisar essa lista com seus colegas para confirmar que esse serviço atende às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="85b63-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="85b63-119">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="85b63-119">Decision points</span></span>|<ul><li><span data-ttu-id="85b63-120">Decida se o Office 365 governo-DoD é apropriado para sua organização.</span><span class="sxs-lookup"><span data-stu-id="85b63-120">Decide whether Office 365 Government - DoD is appropriate for your organization.</span></span></li><li><span data-ttu-id="85b63-121">Confirme se a sua organização atende aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="85b63-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="85b63-122">O Office 365 governo-DoD só está disponível nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="85b63-122">Office 365 Government - DoD is only available in the United States.</span></span> <span data-ttu-id="85b63-123">Os clientes do governo dos EUA podem escolher entre vários [planos governamentais do Office 365](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="85b63-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-office-365-government---dod"></a><span data-ttu-id="85b63-124">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="85b63-124">Step 2.</span></span> <span data-ttu-id="85b63-125">Aplique-se ao Office 365 governo-DoD</span><span class="sxs-lookup"><span data-stu-id="85b63-125">Apply for Office 365 Government - DoD</span></span>

<span data-ttu-id="85b63-126">Decidisse que esse serviço é ideal para sua organização, inicie o processo de [aplicação para este serviço](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="85b63-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-office-365-government---dod-default-security-settings"></a><span data-ttu-id="85b63-127">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="85b63-127">Step 3.</span></span> <span data-ttu-id="85b63-128">Compreenda as configurações de segurança padrão do governo do Office 365-DoD.</span><span class="sxs-lookup"><span data-stu-id="85b63-128">Understand Office 365 Government - DoD default security settings.</span></span>

<span data-ttu-id="85b63-129">Recomendamos que você leve tempo para revisar cuidadosamente suas [configurações de administrador e de segurança](enable-features-office-365.md) antes de modificá-las e considerar o impacto sobre a conformidade antes de fazer qualquer alteração nas configurações de segurança padrão.</span><span class="sxs-lookup"><span data-stu-id="85b63-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="85b63-131">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="85b63-131">Decision point</span></span>|<ul><li><span data-ttu-id="85b63-132">Decida se você precisará modificar qualquer uma das configurações de segurança do governo padrão do Office 365, resolvendo para compreender primeiro o impacto das alterações que você pode fazer.</span><span class="sxs-lookup"><span data-stu-id="85b63-132">Decide whether you'll need to modify any of the default Office 365 Government - DoD security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-office-365-government---dod"></a><span data-ttu-id="85b63-133">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="85b63-133">Step 4.</span></span> <span data-ttu-id="85b63-134">Entender quais recursos do teams estão disponíveis no momento no governo do Office 365-DoD</span><span class="sxs-lookup"><span data-stu-id="85b63-134">Understand which Teams capabilities are currently available in Office 365 Government - DoD</span></span>

<span data-ttu-id="85b63-135">Para acomodar os requisitos de nossos clientes de nuvem governamental, há algumas diferenças entre as equipes do Office 365 governo-DoD e equipes nos planos empresariais.</span><span class="sxs-lookup"><span data-stu-id="85b63-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Office 365 Government - DoD and Teams in the Enterprise plans.</span></span> <span data-ttu-id="85b63-136">Consulte a tabela a seguir para ver os recursos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="85b63-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="85b63-137">Descrição do serviço do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="85b63-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="85b63-138">Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="85b63-138">Step 5.</span></span> <span data-ttu-id="85b63-139">Plano de governança</span><span class="sxs-lookup"><span data-stu-id="85b63-139">Plan for governance</span></span>

<span data-ttu-id="85b63-140">Determine suas necessidades de governança e como você pode atendê-las.</span><span class="sxs-lookup"><span data-stu-id="85b63-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="85b63-141">Vá para [plano de governança no Teams](plan-teams-governance.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="85b63-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt= "An icon depicting a decision point"/>|<span data-ttu-id="85b63-142">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="85b63-142">Decision point</span></span> |<ul><li><span data-ttu-id="85b63-143">Determine e documente seus requisitos de governança, seguindo as diretrizes de [plano de controle no Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="85b63-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="85b63-144">Etapa 6.</span><span class="sxs-lookup"><span data-stu-id="85b63-144">Step 6.</span></span> <span data-ttu-id="85b63-145">Implantar equipes para colaboração</span><span class="sxs-lookup"><span data-stu-id="85b63-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="85b63-146">Depois de ter sido integrado ao Office 365 governo – DoD, siga o caminho de implantação recomendado descrito em [como implantar o Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="85b63-146">After you've been onboarded to Office 365 Government – DoD, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="85b63-147">Não deixe de entrar em contato com sua equipe de adoção e gerenciamento de mudanças e especialistas do teams.</span><span class="sxs-lookup"><span data-stu-id="85b63-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="85b63-148">Você também pode trabalhar com o [FastTrack](https://www.microsoft.com/fasttrack) ou o parceiro escolhido para onboard do serviço.</span><span class="sxs-lookup"><span data-stu-id="85b63-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

> [!NOTE]
> <span data-ttu-id="85b63-149">O cliente das equipes do Mac para ambientes DOD ainda não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="85b63-149">The Mac Teams client for DOD environments is not yet supported.</span></span>
