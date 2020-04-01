---
title: Plano para o Microsoft 365 Government ‒ elevadas implantações de GCC ‒ Microsoft Teams
author: lolajacobsen
ms.author: heidip
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: daro
description: Orientação para profissionais de ti para conduzir implantações do Office 365 em entidades que lidam com os dados sujeitos a normas do governo dos EUA.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 7be9916a1c51b7e98467d1e8c44a18dd6d227d35
ms.sourcegitcommit: 4e1647d19501b37860d9fc79370fa4347f76f85f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/01/2020
ms.locfileid: "43079413"
---
# <a name="plan-for-microsoft-365-government---gcc-high-deployments"></a><span data-ttu-id="5cb2f-103">Plano para implantações altas do Microsoft 365 governo-GCC</span><span class="sxs-lookup"><span data-stu-id="5cb2f-103">Plan for Microsoft 365 Government - GCC High deployments</span></span>

<span data-ttu-id="5cb2f-104">Esta orientação é para os profissionais de ti que estão impulsionando implantações do Office 365 em entidades governamentais federais dos EUA ou outras entidades que lidam com os dados sujeitos a normas e requisitos governamentais, em que o uso do Microsoft 365 governo – o GCC High é adequado para atender a esses requisitos.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-104">This guidance is for IT pros who are driving deployments of Office 365 in US federal government entities or other entities that handle data that's subject to government regulations and requirements, where the use of Microsoft 365 Government – GCC High is appropriate to meet these requirements.</span></span>

> [!NOTE]
> <span data-ttu-id="5cb2f-105">Se a sua organização já tiver atendido à Microsoft 365 governo-os requisitos de elegibilidade de alta qualificação e se foram aceitos no programa, você poderá ignorar as etapas 1 e 2 e ir diretamente para a etapa 3.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-105">If your organization has already met the Microsoft 365 Government – GCC High eligibility requirements and applied for and been accepted into the program, you can skip steps 1 and 2 and go directly to step 3.</span></span>

## <a name="step-1-determine-whether-your-organization-needs-microsoft-365-government---gcc-high-and-meets-eligibility-requirements"></a><span data-ttu-id="5cb2f-106">Etapa 1.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-106">Step 1.</span></span> <span data-ttu-id="5cb2f-107">Determine se a sua organização precisa do Microsoft 365 governo-GCC alto e atenda aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-107">Determine whether your organization needs Microsoft 365 Government - GCC High and meets eligibility requirements.</span></span> 

<span data-ttu-id="5cb2f-108">O ambiente High Microsoft 365 governo-GCC oferece conformidade com os requisitos governamentais dos EUA para serviços de nuvem.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-108">The Microsoft 365 Government - GCC  High environment provides compliance with US government requirements for cloud services.</span></span> <span data-ttu-id="5cb2f-109">Além de desfrutar dos recursos e funcionalidades do Office 365, as organizações se beneficiam dos seguintes recursos exclusivos para o governo da Microsoft 365 – GCC High:</span><span class="sxs-lookup"><span data-stu-id="5cb2f-109">In addition to enjoying the features and capabilities of Office 365, organizations benefit from the following features that are unique to Microsoft 365 Government – GCC High:</span></span>

- <span data-ttu-id="5cb2f-110">O conteúdo do cliente da sua organização é logicamente segregado do conteúdo do cliente nos serviços comerciais do Office 365 da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-110">Your organization's customer content is logically segregated from customer content in the commercial Office 365 services from Microsoft.</span></span>
- <span data-ttu-id="5cb2f-111">O conteúdo do cliente da sua organização é armazenado nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-111">Your organization's customer content is stored within the United States.</span></span>
- <span data-ttu-id="5cb2f-112">O acesso ao conteúdo do cliente da sua organização está restrito ao pessoal da Microsoft em tela.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-112">Access to your organization's customer content is restricted to screened Microsoft personnel.</span></span>
- <span data-ttu-id="5cb2f-113">Microsoft 365 governo – o GCC é compatível com certificações e certificações necessárias para clientes do setor público dos EUA.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-113">Microsoft 365 Government – GCC High complies with certifications and accreditations that are required for US Public Sector customers.</span></span>

<span data-ttu-id="5cb2f-114">Você pode encontrar mais informações sobre o governo Microsoft 365 – GCC High para clientes do governo dos EUA nos [planos do governo](https://products.office.com/government/compare-office-365-government-plans)dos EUA do Office 365, incluindo [os requisitos de qualificação](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span><span class="sxs-lookup"><span data-stu-id="5cb2f-114">You can find more information about the Microsoft 365 Government – GCC High offering for US Government customers at [Office 365 Government plans](https://products.office.com/government/compare-office-365-government-plans), including [eligibility requirements](https://products.office.com/government/compare-office-365-government-plans#EligibilityRequirements).</span></span>

<span data-ttu-id="5cb2f-115">A [Descrição do serviço governo dos EUA do Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) descreve as vantagens da plataforma, que são centralizadas em requisitos de conformidade de reunião nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-115">The [Office 365 US Government service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-us-government/office-365-us-government) describes the platform's benefits, which are centered on meeting compliance requirements within the United States.</span></span>


> [!Tip]
> <span data-ttu-id="5cb2f-116">Talvez você queira transferir as tabelas de informações na descrição do serviço para uma pasta de trabalho do Excel e adicionar duas colunas: **pertinentes para minha organização y/n** e **atender às necessidades da minha organização y/n**.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-116">You might want to transfer the tables of information in the service description into an Excel workbook and add two columns: **Relevant for my organization Y/N** and **Meets the needs of my organization Y/N**.</span></span> <span data-ttu-id="5cb2f-117">Em seguida, você pode revisar essa lista com seus colegas para confirmar que esse serviço atende às necessidades da sua organização.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-117">Then you can review this list with your colleagues to confirm that this service meets your organization's needs.</span></span>


|    |     |
|-----------|------------|
| ![Um ícone representando pontos de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5cb2f-119">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="5cb2f-119">Decision points</span></span>|<ul><li><span data-ttu-id="5cb2f-120">Decida se o Microsoft 365 governo-GCC High é apropriado para a sua organização.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-120">Decide whether Microsoft 365 Government - GCC High is appropriate for your organization.</span></span></li><li><span data-ttu-id="5cb2f-121">Confirme se a sua organização atende aos requisitos de qualificação.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-121">Confirm that your organization meets eligibility requirements.</span></span></li></ul> |

> [!Note]
> <span data-ttu-id="5cb2f-122">O Microsoft 365 governo-GCC High só está disponível nos Estados Unidos.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-122">Microsoft 365 Government - GCC High is only available in the United States.</span></span> <span data-ttu-id="5cb2f-123">Os clientes do governo dos EUA podem escolher entre vários [planos governamentais do Office 365](https://products.office.com/en/government/compare-office-365-government-plans).</span><span class="sxs-lookup"><span data-stu-id="5cb2f-123">Non–US Government customers can choose from a number of [Office 365 Government plans](https://products.office.com/en/government/compare-office-365-government-plans).</span></span>

## <a name="step-2-apply-for-microsoft-365-government---gcc-high"></a><span data-ttu-id="5cb2f-124">Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-124">Step 2.</span></span> <span data-ttu-id="5cb2f-125">Solicitar o Microsoft 365 governo-GCC alto</span><span class="sxs-lookup"><span data-stu-id="5cb2f-125">Apply for Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="5cb2f-126">Decidisse que esse serviço é ideal para sua organização, inicie o processo de [aplicação para este serviço](https://products.office.com/government/eligibility-validation).</span><span class="sxs-lookup"><span data-stu-id="5cb2f-126">Having decided that this service is right for your organization, start the process of [applying for this service](https://products.office.com/government/eligibility-validation).</span></span>


## <a name="step-3-understand-microsoft-365-government---gcc-high-default-security-settings"></a><span data-ttu-id="5cb2f-127">Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-127">Step 3.</span></span> <span data-ttu-id="5cb2f-128">Compreenda as configurações de segurança padrão do governo do Microsoft 365-GCC High.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-128">Understand Microsoft 365 Government - GCC High default security settings.</span></span>

<span data-ttu-id="5cb2f-129">Recomendamos que você leve tempo para revisar cuidadosamente suas [configurações de administrador e de segurança](enable-features-office-365.md) antes de modificá-las e considerar o impacto sobre a conformidade antes de fazer qualquer alteração nas configurações de segurança padrão.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-129">We recommend that you take time to carefully review your [admin and security settings](enable-features-office-365.md) before you modify them, and consider impacts on compliance before you make any changes to the default security settings.</span></span>

|    |     |
|-----------|------------|
| ![Um ícone representando um ponto de decisão](media/audio_conferencing_image7.png) <br/><span data-ttu-id="5cb2f-131">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="5cb2f-131">Decision point</span></span>|<ul><li><span data-ttu-id="5cb2f-132">Decida se você precisará modificar qualquer uma das configurações de alta segurança do governo padrão do Microsoft 365, a solução para compreender primeiro o impacto de todas as alterações que você possa fazer.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-132">Decide whether you'll need to modify any of the default Microsoft 365 Government - GCC High security settings, resolving to first understand the impact of any changes you might make.</span></span></li></ul> |


## <a name="step-4-understand-which-teams-capabilities-are-currently-available-in-microsoft-365-government---gcc-high"></a><span data-ttu-id="5cb2f-133">Etapa 4.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-133">Step 4.</span></span> <span data-ttu-id="5cb2f-134">Entender quais recursos do teams estão disponíveis no momento no Microsoft 365 governo-GCC alto</span><span class="sxs-lookup"><span data-stu-id="5cb2f-134">Understand which Teams capabilities are currently available in Microsoft 365 Government - GCC High</span></span>

<span data-ttu-id="5cb2f-135">Para acomodar os requisitos de nossos clientes de nuvem governamental, há algumas diferenças entre as equipes do Microsoft 365 governo-GCC alta e as equipes nos planos empresariais.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-135">To accommodate the requirements of our government cloud customers, there are some differences between Teams in Microsoft 365 Government - GCC High and Teams in the Enterprise plans.</span></span> <span data-ttu-id="5cb2f-136">Consulte a tabela a seguir para ver os recursos disponíveis.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-136">Refer to the following table to see which features are available.</span></span>

[<span data-ttu-id="5cb2f-137">Descrição do serviço do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="5cb2f-137">Microsoft Teams service description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/teams-service-description)

## <a name="step-5-plan-for-governance"></a><span data-ttu-id="5cb2f-138">Etapa 5.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-138">Step 5.</span></span> <span data-ttu-id="5cb2f-139">Plano de governança</span><span class="sxs-lookup"><span data-stu-id="5cb2f-139">Plan for governance</span></span>

<span data-ttu-id="5cb2f-140">Determine suas necessidades de governança e como você pode atendê-las.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-140">Determine your requirements for governance and how you can meet them.</span></span> <span data-ttu-id="5cb2f-141">Vá para [plano de governança no Teams](plan-teams-governance.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-141">Go to [Plan for governance in Teams](plan-teams-governance.md) for more information.</span></span>

|         |         |         |
|---------|---------|---------|
|<img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/>|<span data-ttu-id="5cb2f-142">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="5cb2f-142">Decision point</span></span> |<ul><li><span data-ttu-id="5cb2f-143">Determine e documente seus requisitos de governança, seguindo as diretrizes de [plano de controle no Teams](plan-teams-governance.md).</span><span class="sxs-lookup"><span data-stu-id="5cb2f-143">Determine and document your governance requirements, following the guidelines in [Plan for governance in Teams](plan-teams-governance.md).</span></span> </li></ul>|

## <a name="step-6-deploy-teams-for-collaboration"></a><span data-ttu-id="5cb2f-144">Etapa 6.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-144">Step 6.</span></span> <span data-ttu-id="5cb2f-145">Implantar equipes para colaboração</span><span class="sxs-lookup"><span data-stu-id="5cb2f-145">Deploy Teams for collaboration</span></span>

<span data-ttu-id="5cb2f-146">Depois de ter sido integrado ao Microsoft 365 governo – GCC High, siga o caminho de implantação recomendado descrito em [como implantar o Microsoft Teams](How-to-roll-out-teams.md).</span><span class="sxs-lookup"><span data-stu-id="5cb2f-146">After you've been onboarded to Microsoft 365 Government – GCC High, follow the recommended deployment path outlined in [How to roll out Microsoft Teams](How-to-roll-out-teams.md).</span></span> <span data-ttu-id="5cb2f-147">Não deixe de entrar em contato com sua equipe de adoção e gerenciamento de mudanças e especialistas do teams.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-147">Be sure to engage with your Adoption and Change Management team and Teams champions.</span></span>

<span data-ttu-id="5cb2f-148">Você também pode trabalhar com o [FastTrack](https://www.microsoft.com/fasttrack) ou o parceiro escolhido para onboard do serviço.</span><span class="sxs-lookup"><span data-stu-id="5cb2f-148">You can also work with [FastTrack](https://www.microsoft.com/fasttrack) or your chosen partner to onboard the service.</span></span>

