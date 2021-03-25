---
title: Implantar os serviços de voz da nuvem do Microsoft Teams
author: rmw2890
ms.author: Rowille
manager: serdars
audience:
- ITPro
- admin
ms.date: 05/16/2018
ms.topic: conceptual
ms.service: msteams
search.appverid: MET150
ms.reviewer: rowille
description: Baixe o Playbook de Habilitação de Site para planejar a adoção do Teams e acelerar e otimizar a adoção do usuário, a percepção de qualidade e a satisfação.
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- M365-voice
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3c3f0105a04484efcabd5ab6c55d1269c3627895
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51112627"
---
# <a name="deploy-my-service"></a><span data-ttu-id="66807-103">Implantar meu serviço</span><span class="sxs-lookup"><span data-stu-id="66807-103">Deploy my service</span></span>

<span data-ttu-id="66807-104">Este artigo apresenta uma visão geral dos requisitos para a implantação adequada dos serviços de voz na nuvem.</span><span class="sxs-lookup"><span data-stu-id="66807-104">This article gives an overview of the requirements for properly deploying cloud voice services.</span></span> <span data-ttu-id="66807-105">Seguindo as diretrizes prescritivas para a implantação de serviços de voz na nuvem, você pode se certificar de que contabilização com êxito de todos os requisitos e resultados repetidos.</span><span class="sxs-lookup"><span data-stu-id="66807-105">By following prescriptive guidance for deploying cloud voice services, you can make sure you successfully account for all requirements and deliver repeatable results.</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="66807-106">Playbook de habilitação de site para cargas de trabalho de voz do Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="66807-106">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="66807-107">Use este playbook para ajudar sua organização a planejar e executar com êxito a lançamento de recursos de voz do Microsoft Teams em uma base site a site.</span><span class="sxs-lookup"><span data-stu-id="66807-107">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="66807-108">Incluindo todas as atividades necessárias, cronogramas recomendados e links para as diretrizes correspondentes para cada atividade, este manual aborda as diretrizes de ponta a ponta para ajudar a garantir uma implantação de voz bem-sucedida do Teams para um determinado site, concentrando-se em fatores importantes para o usuário.</span><span class="sxs-lookup"><span data-stu-id="66807-108">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="66807-109">Ao concluir as atividades neste playbook, sua organização pode:</span><span class="sxs-lookup"><span data-stu-id="66807-109">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="66807-110">Planeje e agende efetivamente sua lançamento do Teams.</span><span class="sxs-lookup"><span data-stu-id="66807-110">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="66807-111">Acelere e otimize a adoção do usuário.</span><span class="sxs-lookup"><span data-stu-id="66807-111">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="66807-112">Reduza as necessidades de suporte e aumente a satisfação do usuário.</span><span class="sxs-lookup"><span data-stu-id="66807-112">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="66807-113">Este artigo e o playbook associado não se destinam a descrever cada etapa de configuração técnica necessária para habilitar o serviço ou fornecer tom de discagem para um site específico.</span><span class="sxs-lookup"><span data-stu-id="66807-113">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="66807-114">Em vez disso, eles se concentram nas atividades e tarefas recomendadas para os usuários de integração facilmente e fazem com que eles comecem a consumir cargas de trabalho de voz do Teams por meio de uma transição rápida e suave com uma alta taxa de adoção, minimizando os requisitos de suporte.</span><span class="sxs-lookup"><span data-stu-id="66807-114">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="66807-115">Para obter orientações técnicas sobre como configurar melhor seu ambiente para a voz do Teams, consulte as listas de verificação de integração para configurar cargas de trabalho de voz do [Teams,](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md)configurando Roteamento Direto no [Teams,](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md)recursos principais do [Teams,](onboarding-checklist-configure-microsoft-teams-core-capabilities.md)rede para [o Teams](prepare-network.md)e habilitando o Microsoft [365 ou o Office 365](onboarding-checklist-enable-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="66807-115">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams.md), [configuring Direct Routing in Teams](onboarding-checklist-configure-direct-routing-in-Microsoft-Teams.md), [Teams core capabilities](onboarding-checklist-configure-microsoft-teams-core-capabilities.md), [networking for Teams](prepare-network.md), and [enabling Microsoft 365 or Office 365](onboarding-checklist-enable-office-365.md).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="66807-116">Áreas de foco de playbook</span><span class="sxs-lookup"><span data-stu-id="66807-116">Playbook focus areas</span></span>

<span data-ttu-id="66807-117">O foco da playbook é abordar os fatores que influenciam a percepção do usuário de uma implantação de voz do Teams.</span><span class="sxs-lookup"><span data-stu-id="66807-117">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="66807-118">Atividades e tarefas são agrupadas nas seguintes áreas de foco:</span><span class="sxs-lookup"><span data-stu-id="66807-118">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="66807-119">Validação da preparação do serviço</span><span class="sxs-lookup"><span data-stu-id="66807-119">Validation of service readiness</span></span>
    - <span data-ttu-id="66807-120">Audioconferência</span><span class="sxs-lookup"><span data-stu-id="66807-120">Audio Conferencing</span></span>
    - <span data-ttu-id="66807-121">Planos de Chamadas</span><span class="sxs-lookup"><span data-stu-id="66807-121">Calling Plans</span></span>
    - <span data-ttu-id="66807-122">Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="66807-122">Direct Routing</span></span>

-   <span data-ttu-id="66807-123">Habilitar o usuário</span><span class="sxs-lookup"><span data-stu-id="66807-123">User enablement</span></span>

-   <span data-ttu-id="66807-124">Pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="66807-124">Endpoints</span></span>

-   <span data-ttu-id="66807-125">Uso e qualidade</span><span class="sxs-lookup"><span data-stu-id="66807-125">Usage and quality</span></span>

-   <span data-ttu-id="66807-126">Adoção</span><span class="sxs-lookup"><span data-stu-id="66807-126">Adoption</span></span>

<span data-ttu-id="66807-127">O [Playbook de Habilitação de Site para Voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) é uma planilha do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="66807-127">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="66807-128">Cada uma dessas cinco áreas de foco é uma planilha separada na pasta de trabalho, e cada tarefa e atividade de implantação é agrupada em uma dessas planilhas.</span><span class="sxs-lookup"><span data-stu-id="66807-128">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="66807-129">![Captura de tela do playbook de habilitação do site](media/deploy-my-service-image1.png "Captura de tela do playbook")</span><span class="sxs-lookup"><span data-stu-id="66807-129">![Screenshot of the site enablement playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="66807-130">Você criará uma instância separada do playbook para cada site no escopo da sua adoção do Teams.</span><span class="sxs-lookup"><span data-stu-id="66807-130">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="66807-131">Como usar o playbook</span><span class="sxs-lookup"><span data-stu-id="66807-131">How to use the playbook</span></span>

<span data-ttu-id="66807-132">Independentemente do tamanho e da complexidade do local, a habilitação de cada site exige que você planeje suas tarefas e atividades com antecedência suficiente e execute-as em ordem ideal antes, durante e após a ativação real do serviço.</span><span class="sxs-lookup"><span data-stu-id="66807-132">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="66807-133">Recomendamos que você siga estas etapas ao planejar e executar sua própria jornada até a voz do Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="66807-133">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1. <span data-ttu-id="66807-134">Baixe o [Playbook de Habilitação do Site para Voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para o Microsoft Teams Voice.</span><span class="sxs-lookup"><span data-stu-id="66807-134">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2. <span data-ttu-id="66807-135">Crie uma cópia separada do playbook para cada site.</span><span class="sxs-lookup"><span data-stu-id="66807-135">Create a separate copy of the playbook for each site.</span></span>

3. <span data-ttu-id="66807-136">Na guia para a planilha chamada **Playbook for {SiteName-Code}**, substitua **{SiteName-Code}** pelo nome de site relevante e/ou código do site.</span><span class="sxs-lookup"><span data-stu-id="66807-136">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4. <span data-ttu-id="66807-137">Insira o **nome do site, o código do site** e a data de início **planejada,** conforme ilustrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="66807-137">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="66807-138">Esta é uma etapa crítica, pois ajusta os prazos recomendados para cada atividade no playbook.</span><span class="sxs-lookup"><span data-stu-id="66807-138">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

   <span data-ttu-id="66807-139">![Exemplo com nome do site, código do site e data de início planejada](media/deploy-my-service-image2.png "Exemplo com o nome do site de Nova York, código do site NY01 e data de início planejada de 20-Mar-18")</span><span class="sxs-lookup"><span data-stu-id="66807-139">![Example with site name, site code, and planned launch date](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5. <span data-ttu-id="66807-140">Revise cada atividade, tome as ações necessárias e atualize o status enquanto você passa pela linha do tempo.</span><span class="sxs-lookup"><span data-stu-id="66807-140">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="66807-141">O status é representado graficamente, conforme descrito abaixo:</span><span class="sxs-lookup"><span data-stu-id="66807-141">Status is represented graphically, as described below:</span></span>
  
   - <span data-ttu-id="66807-142">![Ilustração de uma marca de verificação verde Sim, ou não aplicável ](media/deploy-my-service-image3.png) **(verde):** a atividade foi concluída ou não é aplicável para este site e nenhuma ação é necessária.</span><span class="sxs-lookup"><span data-stu-id="66807-142">![Illustration of a green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
   - <span data-ttu-id="66807-143">![Ilustração de um ponto de exclamação amarelo A atividade ainda não foi concluída ](media/deploy-my-service-image4.png) <strong>(amarela):</strong> a atividade ainda não foi concluída e deve ser atualizada para Sim ou Não em sua agenda.</span><span class="sxs-lookup"><span data-stu-id="66807-143">![Illustration of a yellow exclamation point](media/deploy-my-service-image4.png) <strong>The activity isn’t completed yet (yellow):</strong> The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
   - <span data-ttu-id="66807-144">![Ilustração de um X vermelho indicando não (vermelho): a atividade não pode ser concluída devido a um problema e deve ser carregada para a reunião ](media/deploy-my-service-image5.png) <strong></strong> de status do projeto.</span><span class="sxs-lookup"><span data-stu-id="66807-144">![Illustration of a red X indicating no](media/deploy-my-service-image5.png) <strong>No (red):</strong> The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6. <span data-ttu-id="66807-145">O status é rolado para cima em cada seção e o título da seção é formatado com um desses indicadores de status.</span><span class="sxs-lookup"><span data-stu-id="66807-145">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="66807-146">**O status semanal** também é atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="66807-146">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="66807-147">![Captura de tela das roll-ups de status semanais no playbook](media/deploy-my-service-image6.png "Captura de tela das roll-ups de status semanais no playbook")</span><span class="sxs-lookup"><span data-stu-id="66807-147">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="66807-148">Repita as etapas acima para todos os locais que você tem.</span><span class="sxs-lookup"><span data-stu-id="66807-148">Repeat the steps above for all the locations you have.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="66807-149">Algumas etapas podem não ser aplicáveis a todos os locais e sites.</span><span class="sxs-lookup"><span data-stu-id="66807-149">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="66807-150">Se uma atividade específica não for relevante para um site, selecione **Não aplicável** a essa atividade.</span><span class="sxs-lookup"><span data-stu-id="66807-150">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="66807-151">**NÃO EXCLUa** nenhuma linha no playbook; se você fizer isso, as fórmulas de rolagem de status não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="66807-151">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="66807-152">Preste atenção às atividades que podem levar mais tempo do que você planejou, como atividades de portação de número e compras.</span><span class="sxs-lookup"><span data-stu-id="66807-152">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="66807-153">Essas atividades podem afetar negativamente a linha do tempo de implantação do site.</span><span class="sxs-lookup"><span data-stu-id="66807-153">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="66807-154">Certifique-se de revisar e atualizar a lista de atividades [](./envision-steering-committee-complete-guide.md) e a linha do tempo associada semanalmente e apresentá-las em reuniões do comitê de direção para garantir que as partes interessadas estão cientes do status de cada site e quaisquer possíveis desvios do cronograma de implantação.</span><span class="sxs-lookup"><span data-stu-id="66807-154">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](./envision-steering-committee-complete-guide.md) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting decision points"/> <br/><span data-ttu-id="66807-155">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="66807-155">Decision points</span></span></td><td><ul><li><span data-ttu-id="66807-156">Decida se o Manual de Habilitação de Site é necessário para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="66807-156">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="66807-157">Decida quem será responsável por personalizar o Playbook de Habilitação de Site para o Microsoft Teams para cada site que você implantará.</span><span class="sxs-lookup"><span data-stu-id="66807-157">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you’ll deploy.</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next steps"/><br/><span data-ttu-id="66807-158">Próximas etapas</span><span class="sxs-lookup"><span data-stu-id="66807-158">Next steps</span></span></td><td><ul><li><span data-ttu-id="66807-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Baixe o Playbook de Habilitação do Site.</a></span><span class="sxs-lookup"><span data-stu-id="66807-159"><a href="https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true" data-raw-source="[Download the Site Enablement Playbook](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true)">Download the Site Enablement Playbook</a>.</span></span></li><li><span data-ttu-id="66807-160">Personalize o Playbook de Habilitação do Site para seu primeiro site.</span><span class="sxs-lookup"><span data-stu-id="66807-160">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="66807-161">Repita conforme necessário para sites adicionais.</span><span class="sxs-lookup"><span data-stu-id="66807-161">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->