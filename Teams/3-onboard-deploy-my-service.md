---
title: Implantar o serviço de voz de nuvem Teams da Microsoft
author: rmw2890
ms.author: MyAdvisor
manager: lehewe
ms.date: 03/13/2018
ms.topic: article
ms.service: msteams
ms.reviewer: rowille
description: Baixe o Guia estratégico habilitação de Site para planejar sua distribuição de equipes e acelerar e otimizar a adoção de usuário, percepção de qualidade e satisfação.
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ddccd9c52e25ae9d0069119641aa7e8a8077d56
ms.sourcegitcommit: b985035b91ebd7ceff8d50e9e0fa9aa6ff971f3a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2018
---
# <a name="deploy-my-service"></a><span data-ttu-id="4481b-103">Implantar o meu serviço</span><span class="sxs-lookup"><span data-stu-id="4481b-103">Deploy my service</span></span>

## <a name="site-enablement-playbook-for-microsoft-teams-voice-workloads"></a><span data-ttu-id="4481b-104">Guia estratégico de habilitação de site para cargas de trabalho do Microsoft Teams voz</span><span class="sxs-lookup"><span data-stu-id="4481b-104">Site enablement playbook for Microsoft Teams voice workloads</span></span>

<span data-ttu-id="4481b-105">Use este guia estratégico para ajudar sua organização com êxito planejar e executar a distribuição dos recursos de voz do Microsoft Teams em uma base de site por site.</span><span class="sxs-lookup"><span data-stu-id="4481b-105">Use this playbook to help your organization successfully plan and execute the rollout of Microsoft Teams voice features on a site-by-site basis.</span></span>

<span data-ttu-id="4481b-106">Incluindo necessárias todas as atividades, recomendado cronogramas e links para orientação correspondente para cada atividade, este playbook aborda a orientação de ponta a ponta para ajudar a garantir uma implantação bem-sucedida de voz de equipes para um determinado site, concentrando-se em fatores importantes para o usuário.</span><span class="sxs-lookup"><span data-stu-id="4481b-106">Including all required activities, recommended timelines, and links to corresponding guidance for each activity, this playbook covers end-to-end guidance to help ensure a successful Teams voice deployment for a given site, focusing on factors that are important to the user.</span></span>

<span data-ttu-id="4481b-107">Ao concluir as atividades deste playbook, sua organização pode:</span><span class="sxs-lookup"><span data-stu-id="4481b-107">By completing the activities in this playbook, your organization can:</span></span>

-   <span data-ttu-id="4481b-108">Efetivamente, planeje e agende a distribuição de equipes.</span><span class="sxs-lookup"><span data-stu-id="4481b-108">Effectively plan and schedule your Teams rollout.</span></span>

-   <span data-ttu-id="4481b-109">Acelerar e otimizar a adoção dos usuários.</span><span class="sxs-lookup"><span data-stu-id="4481b-109">Accelerate and optimize user adoption.</span></span>

-   <span data-ttu-id="4481b-110">Reduzir as necessidades de suporte e aumentar a satisfação do usuário.</span><span class="sxs-lookup"><span data-stu-id="4481b-110">Reduce support needs and increase user satisfaction.</span></span>

> [!NOTE]
> <span data-ttu-id="4481b-111">Este artigo e o playbook associado não são destinados para descrever cada etapa de configuração técnicos necessários para habilitação de serviços ou fornecer um tom de discagem a um site específico.</span><span class="sxs-lookup"><span data-stu-id="4481b-111">This article and the associated playbook aren’t intended to describe every technical configuration step required for service enablement or providing dial tone to a specific site.</span></span> <span data-ttu-id="4481b-112">Em vez disso, eles se concentrar em atividades e tarefas recomendadas aos usuários onboard facilmente e fazê-las a começar a consumir cargas de trabalho de voz de equipes por meio de uma transição rápida e suave com uma taxa de adoção alta, enquanto minimiza os requisitos de suporte.</span><span class="sxs-lookup"><span data-stu-id="4481b-112">Instead, they focus on activities and tasks recommended to onboard users easily and have them start consuming Teams voice workloads through a fast and smooth transition with a high adoption rate, while minimizing support requirements.</span></span> <span data-ttu-id="4481b-113">Para obter orientações técnicas sobre como configurar melhor de voz de equipes em seu ambiente, consulte as listas de verificação do inclusão para [Configurar as cargas de trabalho de voz de equipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams), [principais recursos de equipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities), [rede para equipes](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking)e [Habilitando o Office 365 ](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).</span><span class="sxs-lookup"><span data-stu-id="4481b-113">For technical guidance on how to best configure your environment for Teams voice, see the onboarding checklists for [configuring Teams voice workloads](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-cloud-voice-workloads-in-Microsoft-Teams), [Teams core capabilities](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-microsoft-teams-core-capabilities), [networking for Teams](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-configure-networking), and [enabling Office 365](https://docs.microsoft.com/MicrosoftTeams/onboarding-checklist-enable-office-365).</span></span>

<!--ENDOFSECTION-->

## <a name="playbook-focus-areas"></a><span data-ttu-id="4481b-114">Áreas de foco de playbook</span><span class="sxs-lookup"><span data-stu-id="4481b-114">Playbook focus areas</span></span>

<span data-ttu-id="4481b-115">O foco do playbook é abordar os fatores que influenciam a percepção do usuário de uma implantação de voz de equipes.</span><span class="sxs-lookup"><span data-stu-id="4481b-115">The focus of the playbook is to address the factors that influence the user’s perception of a Teams voice deployment.</span></span> <span data-ttu-id="4481b-116">Atividades e tarefas estão agrupadas nas seguintes áreas de foco:</span><span class="sxs-lookup"><span data-stu-id="4481b-116">Activities and tasks are grouped into the following focus areas:</span></span>

-   <span data-ttu-id="4481b-117">Validação da preparação do serviço</span><span class="sxs-lookup"><span data-stu-id="4481b-117">Validation of service readiness</span></span>

-   <span data-ttu-id="4481b-118">Habilitação de usuário</span><span class="sxs-lookup"><span data-stu-id="4481b-118">User enablement</span></span>

-   <span data-ttu-id="4481b-119">Pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="4481b-119">Endpoints</span></span>

-   <span data-ttu-id="4481b-120">Uso e qualidade</span><span class="sxs-lookup"><span data-stu-id="4481b-120">Usage and quality</span></span>

-   <span data-ttu-id="4481b-121">Adoção</span><span class="sxs-lookup"><span data-stu-id="4481b-121">Adoption</span></span>

<span data-ttu-id="4481b-122">O [Site Playbook de habilitação para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) é uma pasta de trabalho do Microsoft Excel.</span><span class="sxs-lookup"><span data-stu-id="4481b-122">The [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) is a Microsoft Excel workbook.</span></span> <span data-ttu-id="4481b-123">Cada uma dessas áreas de foco de cinco é uma planilha separada na pasta de trabalho, e cada tarefa de implantação e a atividade são agrupados em um dessas folhas.</span><span class="sxs-lookup"><span data-stu-id="4481b-123">Each of these five focus areas is a separate sheet in the workbook, and each deployment task and activity is grouped onto one of these sheets.</span></span>

<span data-ttu-id="4481b-124">![Captura de tela de playbook] (media/deploy-my-service-image1.png "Captura de tela de playbook")</span><span class="sxs-lookup"><span data-stu-id="4481b-124">![Screenshot of the playbook](media/deploy-my-service-image1.png "Screenshot of the playbook")</span></span>

> [!NOTE]
> <span data-ttu-id="4481b-125">Você criará uma instância separada do playbook para cada site no escopo para a distribuição de equipes.</span><span class="sxs-lookup"><span data-stu-id="4481b-125">You’ll create a separate instance of the playbook for each site in scope for your Teams rollout.</span></span>

<!--ENDOFSECTION-->

## <a name="how-to-use-the-playbook"></a><span data-ttu-id="4481b-126">Como usar o playbook</span><span class="sxs-lookup"><span data-stu-id="4481b-126">How to use the playbook</span></span>

<span data-ttu-id="4481b-127">Independentemente do tamanho e complexidade do local, permitindo que cada site requer que você planeje suas tarefas e atividades antecipado suficiente — e executá-los na ordem ideal — antes, durante e depois da distribuição de serviço real.</span><span class="sxs-lookup"><span data-stu-id="4481b-127">Regardless of the size and complexity of the location, enabling each site requires that you plan your tasks and activities early enough—and execute them in optimal order—before, during, and after the actual service rollout.</span></span> <span data-ttu-id="4481b-128">Recomendamos que você siga estas etapas ao planejar e executar sua própria jornada Voice Teams da Microsoft.</span><span class="sxs-lookup"><span data-stu-id="4481b-128">We recommend that you follow these steps as you plan and execute your own journey to Microsoft Teams voice.</span></span>

1.  <span data-ttu-id="4481b-129">Baixe o [Guia estratégico de habilitação de Site para voz (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) para equipes da Microsoft Voice.</span><span class="sxs-lookup"><span data-stu-id="4481b-129">Download the [Site Enablement Playbook for Voice (Playbook)](https://github.com/MicrosoftDocs/OfficeDocs-SkypeForBusiness/blob/live/Teams/downloads/site-enablement-playbook-for-voice-(playbook).xlsx?raw=true) for Microsoft Teams Voice.</span></span>

2.  <span data-ttu-id="4481b-130">Crie uma cópia separada do playbook para cada site.</span><span class="sxs-lookup"><span data-stu-id="4481b-130">Create a separate copy of the playbook for each site.</span></span>

3.  <span data-ttu-id="4481b-131">Na guia da planilha chamado **Playbook para {nome_do_site código}**, substitua **{Nome_do_site código}** com o nome do site relevante e/ou o código do site.</span><span class="sxs-lookup"><span data-stu-id="4481b-131">On the tab for the sheet named **Playbook for {SiteName-Code}**, replace **{SiteName-Code}** with the relevant site name and/or site code.</span></span>

4.  <span data-ttu-id="4481b-132">Insira o **nome do Site, o código do Site**e a **Data de início planejado**, conforme ilustrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="4481b-132">Enter the **Site name, Site code**, and **Planned launch date**, as illustrated below.</span></span> <span data-ttu-id="4481b-133">Isso é uma etapa importante, porque ele ajusta os prazos recomendados para todas as atividades no playbook.</span><span class="sxs-lookup"><span data-stu-id="4481b-133">This is a critical step, because it adjusts the recommended deadlines for every activity in the playbook.</span></span>

    <span data-ttu-id="4481b-134">![Exemplo com o nome do site de Nova York, código de site NY01 e a data de início planejada de 20-Mar-18] (media/deploy-my-service-image2.png "Exemplo com o nome do site de Nova York, código de site NY01 e a data de início planejada de 20-Mar-18")</span><span class="sxs-lookup"><span data-stu-id="4481b-134">![Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18](media/deploy-my-service-image2.png "Example with site name of New York, site code NY01, and planned launch date of 20-Mar-18")</span></span>

5.  <span data-ttu-id="4481b-135">Revisar cada atividade, execute as ações necessárias e atualizar o status conforme você percorrer a linha do tempo.</span><span class="sxs-lookup"><span data-stu-id="4481b-135">Review each activity, take necessary actions, and update the status as you walk through the timeline.</span></span> <span data-ttu-id="4481b-136">Status é representada graficamente, conforme descrito abaixo:</span><span class="sxs-lookup"><span data-stu-id="4481b-136">Status is represented graphically, as described below:</span></span>
    <ul>
    <li><span data-ttu-id="4481b-137">![Marca de seleção verde](media/deploy-my-service-image3.png) **Sim ou não aplicável (verde):** a atividade foi concluída, ou não for aplicável para este site e nenhuma outra ação será necessária.</span><span class="sxs-lookup"><span data-stu-id="4481b-137">![Green check mark](media/deploy-my-service-image3.png) **Yes, or not applicable (green):** The activity has been completed, or it’s not applicable for this site, and no further action is needed.</span></span></li>
    <li><span data-ttu-id="4481b-138">![Ponto de exclamação amarelo](media/deploy-my-service-image4.png) **a atividade não será concluída ainda (amarelado):** a atividade ainda não tiver sido concluída e deve ser atualizada para Sim ou não em sua agenda.</span><span class="sxs-lookup"><span data-stu-id="4481b-138">![Yellow exclamation point](media/deploy-my-service-image4.png) **The activity isn’t completed yet (yellow):** The activity hasn’t been completed yet, and must be updated to Yes or No on its schedule.</span></span></li>
    <li><span data-ttu-id="4481b-139">![X vermelho](media/deploy-my-service-image5.png) **Nenhuma (vermelho):** a atividade não pode ser concluída devido a um problema e deve ser transmitida para a reunião de status do projeto.</span><span class="sxs-lookup"><span data-stu-id="4481b-139">![Red X](media/deploy-my-service-image5.png) **No (red):** The activity can’t be completed because of an issue and must be carried to the project status meeting.</span></span></li></ul>

6.  <span data-ttu-id="4481b-140">O status é acumulado dentro de cada seção e o cabeçalho de seção é formatado com um desses indicadores de status.</span><span class="sxs-lookup"><span data-stu-id="4481b-140">The status is rolled up within each section, and the section heading is formatted with one of these status indicators.</span></span> <span data-ttu-id="4481b-141">**Status semanais** também é atualizado automaticamente.</span><span class="sxs-lookup"><span data-stu-id="4481b-141">**Weekly status** is also updated automatically.</span></span>

<span data-ttu-id="4481b-142">![Captura de tela dos semanal status acúmulos de playbook] (media/deploy-my-service-image6.png "Captura de tela dos semanal status acúmulos de playbook")</span><span class="sxs-lookup"><span data-stu-id="4481b-142">![Screenshot of the weekly status roll-ups in the playbook](media/deploy-my-service-image6.png "Screenshot of the weekly status roll-ups in the playbook")</span></span>

> [!TIP]
> <span data-ttu-id="4481b-143">Repita as etapas acima para todos os locais que você tem.</span><span class="sxs-lookup"><span data-stu-id="4481b-143">Repeat the steps above for all the locations you have.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="4481b-144">Algumas etapas podem não ser aplicáveis a todos os sites e locais.</span><span class="sxs-lookup"><span data-stu-id="4481b-144">Some steps might not be applicable to all locations and sites.</span></span> <span data-ttu-id="4481b-145">Se uma atividade específica não é relevante para um site, você deve selecionar **não aplicável** para esta atividade.</span><span class="sxs-lookup"><span data-stu-id="4481b-145">If a specific activity isn’t relevant to a site, you must select **Not applicable** for this activity.</span></span> <span data-ttu-id="4481b-146">**Não exclua** qualquer linhas no playbook; Se fizer isso, as fórmulas de acúmulo de status não funcionarão.</span><span class="sxs-lookup"><span data-stu-id="4481b-146">**DO NOT DELETE** any rows in the playbook; if you do, the status roll-up formulas won’t work.</span></span><br/><br/>
<span data-ttu-id="4481b-147">Preste atenção às atividades que podem levar mais tempo do que o planejado, como o número de porta e atividades de compras.</span><span class="sxs-lookup"><span data-stu-id="4481b-147">Pay attention to activities that might take more time than you planned for, such as number porting and procurement activities.</span></span> <span data-ttu-id="4481b-148">Essas atividades podem afetar negativamente o cronograma de implantação do site.</span><span class="sxs-lookup"><span data-stu-id="4481b-148">These activities can negatively affect the site deployment timeline.</span></span> <span data-ttu-id="4481b-149">Certifique-se de revisar e atualizar a lista de atividade e a linha do tempo associada semanalmente e apresentá-las em [reuniões comitê de orientação](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) para assegurar que os participantes estão cientes do status de cada site e quaisquer possíveis desvios da agenda de implantação.</span><span class="sxs-lookup"><span data-stu-id="4481b-149">Be sure to review and update the activity list and the associated timeline weekly, and present them at [steering committee meetings](https://docs.microsoft.com/MicrosoftTeams/envision-steering-committee-complete-guide) to ensure that stakeholders are aware of the status of each site and any possible deviations from the deployment schedule.</span></span>


<table>
<tr><td>![](media/audio_conferencing_image7.png) <br/><span data-ttu-id="4481b-150">Pontos de decisão</span><span class="sxs-lookup"><span data-stu-id="4481b-150">Decision points</span></span></td><td><ul><li><span data-ttu-id="4481b-151">Decida se o Site habilitação de Playbook é necessária para sua implantação.</span><span class="sxs-lookup"><span data-stu-id="4481b-151">Decide if the Site Enablement Playbook is required for your deployment.</span></span></li><li><span data-ttu-id="4481b-152">Decida quem será responsável por Personalizando o Playbook de habilitação de Site for Microsoft Teams para todos os sites que você vai implantar.</span><span class="sxs-lookup"><span data-stu-id="4481b-152">Decide who will be responsible for customizing the Site Enablement Playbook for Microsoft Teams for every site you'll deploy.</span></span></li></ul></td></tr>
<tr><td>![](media/audio_conferencing_image9.png)<br/><span data-ttu-id="4481b-153">Próximos passos</span><span class="sxs-lookup"><span data-stu-id="4481b-153">Next steps</span></span></td><td><ul><li><span data-ttu-id="4481b-154">Baixe o Playbook de habilitação do Site.</span><span class="sxs-lookup"><span data-stu-id="4481b-154">Download the Site Enablement Playbook.</span></span></li><li><span data-ttu-id="4481b-155">Personalize o Playbook de habilitação de Site para o seu primeiro site.</span><span class="sxs-lookup"><span data-stu-id="4481b-155">Customize the Site Enablement Playbook for your first site.</span></span></li><li><span data-ttu-id="4481b-156">Repita conforme necessário para outros sites.</span><span class="sxs-lookup"><span data-stu-id="4481b-156">Repeat as needed for additional sites.</span></span></li></ul></td></tr>
</table>

<!--ENDOFSECTION-->