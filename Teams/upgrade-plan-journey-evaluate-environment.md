---
title: Avalie seu ambiente antes de atualizar para o Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba mais sobre os requisitos para avaliar corretamente seu ambiente atual para a atualização para o Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: Teams-upgrade-guidance
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c783934128e2c1d3f971948c41e3481839ff0aa1
ms.sourcegitcommit: 1e16c6c7112bdde03209c12468b5705ddd116a62
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/05/2020
ms.locfileid: "49578234"
---
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="5d2c3-103">Avalie seu ambiente antes de atualizar para o Teams</span><span class="sxs-lookup"><span data-stu-id="5d2c3-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="5d2c3-104">![Diagrama de atualização da jornada, enfatizando o estágio de Preparação Técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada de atualização, com ênfase no estágio de Preparação Técnica")</span><span class="sxs-lookup"><span data-stu-id="5d2c3-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="5d2c3-105">Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="5d2c3-106">Antes de prosseguir, confirme que você concluiu essas atividades de estágios anteriores:</span><span class="sxs-lookup"><span data-stu-id="5d2c3-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="5d2c3-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="5d2c3-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="5d2c3-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="5d2c3-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="5d2c3-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="5d2c3-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="5d2c3-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="5d2c3-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="5d2c3-111">Este artigo apresenta uma visão geral dos requisitos para avaliar corretamente seu ambiente atual para o Teams operacional.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="5d2c3-112">Ao avaliar seu ambiente, você identifica riscos e requisitos que influenciarão sua implantação geral.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="5d2c3-113">Ao identificar esses itens antecipadamente, você pode ajustar seu planejamento para impulsionar o sucesso.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="5d2c3-114">Introdução ao Questionário de Descoberta</span><span class="sxs-lookup"><span data-stu-id="5d2c3-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="5d2c3-115">Para alcançar seus resultados de chave de objetivo (OKRs), você já fez as principais decisões de serviço.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="5d2c3-116">A próxima etapa é executar a descoberta de questões ambientais para avaliar todos os aspectos relacionados à sua infraestrutura de TI, rede e operações para confirmar que sua organização está pronta para implementar a solução.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="5d2c3-117">A descoberta é uma das primeiras etapas fundamentais que você deve seguir ao planejar sua jornada para o Teams.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="5d2c3-118">A descoberta do meio ambiente deve incluir uma avaliação de preparação de rede para garantir que sua rede possa dar suporte à atualização para o Teams.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="5d2c3-119">Você executa uma descoberta detalhada do seu ambiente para entender melhor seu estado atual e revelar quaisquer dificuldades ou, ainda mais importante, possíveis bloqueadores para a execução da sua adoção do Teams.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="5d2c3-120">Você identifica os riscos técnicos como parte de uma avaliação e avaliação de preparação para adoção e desenvolve um plano de atenuação para cada risco identificado.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="5d2c3-121">Você deve incorporar essas informações no registro de risco.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="5d2c3-122">Todos os assuntos relacionados à sua infraestrutura de colaboração existente e à organização do Microsoft 365 ou office 365, rede, pontos de extremidade, operações, adoção e preparação são incluídos como parte do questionário de descoberta de questões ambientais.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="5d2c3-123">Trabalhe com sua equipe de projeto para fornecer as informações solicitadas com o máximo de detalhes possível para facilitar suas atividades de planejamento.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="5d2c3-124">[O questionário](upgrade-plan-journey-discovery-questionnaire.md) é dividido nas seções a seguir para confirmar a preparação da sua organização para a implantação do Teams em várias áreas principais:</span><span class="sxs-lookup"><span data-stu-id="5d2c3-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="5d2c3-125">Detalhes da organização do Microsoft 365 ou do Office 365</span><span class="sxs-lookup"><span data-stu-id="5d2c3-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="5d2c3-126">Resumo da plataforma de colaboração existente</span><span class="sxs-lookup"><span data-stu-id="5d2c3-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="5d2c3-127">Detalhes da implantação da plataforma de colaboração</span><span class="sxs-lookup"><span data-stu-id="5d2c3-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="5d2c3-128">Rede e acesso aos serviços do Microsoft 365 ou do Office 365</span><span class="sxs-lookup"><span data-stu-id="5d2c3-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="5d2c3-129">Pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="5d2c3-129">Endpoints</span></span>
- <span data-ttu-id="5d2c3-130">Operações</span><span class="sxs-lookup"><span data-stu-id="5d2c3-130">Operations</span></span>
- <span data-ttu-id="5d2c3-131">Adoção e preparação</span><span class="sxs-lookup"><span data-stu-id="5d2c3-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="5d2c3-132">Você pode começar copiando o questionário para um documento do Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="5d2c3-133">Tente responder a todas as perguntas e capturar todos os detalhes conforme você avança.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="5d2c3-134">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="5d2c3-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="5d2c3-135">Quem será responsável por concluir uma avaliação de ambiente?</span><span class="sxs-lookup"><span data-stu-id="5d2c3-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="5d2c3-136">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="5d2c3-136">Next step</span></span></td><td><ul><li><span data-ttu-id="5d2c3-137">Documente os resultados da avaliação do ambiente.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="5d2c3-138">Equipe do Project</span><span class="sxs-lookup"><span data-stu-id="5d2c3-138">Project team</span></span>

<span data-ttu-id="5d2c3-139">Certifique-se de que você contratou as pessoas certas para sua equipe de projeto.</span><span class="sxs-lookup"><span data-stu-id="5d2c3-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="5d2c3-140">Verifique as etapas que você concluiu [no Alisar os participantes do projeto.](upgrade-enlist-stakeholders.md)</span><span class="sxs-lookup"><span data-stu-id="5d2c3-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="5d2c3-141">Depois de avaliar seu ambiente, prossiga para a próxima etapa: [Preparar seu serviço.](upgrade-prepare-environment-prepare-service.md)</span><span class="sxs-lookup"><span data-stu-id="5d2c3-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
