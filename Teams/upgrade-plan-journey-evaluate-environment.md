---
title: Avaliar o ambiente antes de atualizar para o Microsoft Teams
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: Saiba mais sobre os requisitos para a avaliação adequada do ambiente atual para a atualização do teams.
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
# <a name="evaluate-your-environment-before-upgrading-to-teams"></a><span data-ttu-id="ce4f4-103">Avaliar o ambiente antes de atualizar para o Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ce4f4-103">Evaluate your environment before upgrading to Teams</span></span>

<span data-ttu-id="ce4f4-104">![Atualize o diagrama de jornada, enfatizando o estágio de preparação técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada da atualização, com ênfase no estágio de preparação técnica")</span><span class="sxs-lookup"><span data-stu-id="ce4f4-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="ce4f4-105">Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="ce4f4-106">Antes de prosseguir, confirme que você concluiu essas atividades dos estágios anteriores:</span><span class="sxs-lookup"><span data-stu-id="ce4f4-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="ce4f4-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="ce4f4-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="ce4f4-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="ce4f4-108">Defined your project scope</span></span>](https://aka.ms/SkypetoTeams-Scope)
- [<span data-ttu-id="ce4f4-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="ce4f4-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](https://aka.ms/SkypeToTeams-Coexist)
- [<span data-ttu-id="ce4f4-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="ce4f4-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="ce4f4-111">Este artigo fornece uma visão geral dos requisitos para a avaliação adequada do ambiente atual para as equipes operacionais.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-111">This article gives an overview of the requirements for properly evaluating your current environment for operating Teams.</span></span> <span data-ttu-id="ce4f4-112">Ao avaliar seu ambiente, você identifica os riscos e os requisitos que influenciarão sua implantação geral.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-112">By evaluating your environment, you identify risks and requirements that will influence your overall deployment.</span></span> <span data-ttu-id="ce4f4-113">Ao identificar esses itens antecipadamente, você pode ajustar o planejamento para impulsionar o sucesso.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-113">By identifying these items beforehand, you can adjust your planning to drive success.</span></span>

## <a name="introduction-to-the-discovery-questionnaire"></a><span data-ttu-id="ce4f4-114">Introdução ao questionário de descoberta</span><span class="sxs-lookup"><span data-stu-id="ce4f4-114">Introduction to the Discovery Questionnaire</span></span>

<span data-ttu-id="ce4f4-115">Para obter seus resultados de chave objetiva (OKRs), você anteriormente fez decisões importantes sobre o serviço.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-115">To achieve your objective key results (OKRs), you previously made key service decisions.</span></span> <span data-ttu-id="ce4f4-116">A próxima etapa é executar a descoberta ambiental para avaliar todos os aspectos relacionados à sua infraestrutura de ti, à rede e às operações para confirmar se a sua organização está pronta para implementar a solução.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-116">The next step is to perform environmental discovery to evaluate all aspects relating to your IT infrastructure, networking, and operations to confirm that your organization is ready to implement the solution.</span></span> <span data-ttu-id="ce4f4-117">A descoberta é uma das principais etapas que você faz ao planejar sua jornada para o Teams.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-117">Discovery is one of the very first, key steps that you take when planning for your journey to Teams.</span></span> <span data-ttu-id="ce4f4-118">A descoberta ambiental deve incluir uma avaliação de prontidão de rede para garantir que a sua rede possa dar suporte à atualização para o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-118">Environmental discovery must include a network readiness assessment to ensure your network can support upgrading to Teams.</span></span> <span data-ttu-id="ce4f4-119">Você executa uma descoberta detalhada do seu ambiente para compreender melhor seu estado atual e para revelar qualquer dificuldade ou, ainda mais importante, aos bloqueadores de execução de sua distribuição de suas equipes.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-119">You perform a detailed discovery of your environment to better understand its current state and to reveal any difficulties or—even more important—possible blockers to the execution of your Teams rollout.</span></span>

<span data-ttu-id="ce4f4-120">Você identifica riscos técnicos como parte de uma avaliação de avaliação de adoção e avaliação ambiental e desenvolve um plano de mitigação para cada risco identificado.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-120">You identify technical risks as part of an environmental assessment and adoption readiness evaluation, and develop a mitigation plan for each identified risk.</span></span> <span data-ttu-id="ce4f4-121">Você deve incorporar essas informações no registro de risco.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-121">You should incorporate this information in the risk register.</span></span>

<span data-ttu-id="ce4f4-122">Todas as questões relacionadas à sua infraestrutura de colaboração existente e à Microsoft 365 ou à organização do Office 365, à rede, aos pontos de extremidade, às operações e à preparação e à preparação são incluídas como parte do questionário de descoberta ambiental.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-122">All matters related to your existing collaboration infrastructure and Microsoft 365 or Office 365 organization, networking, endpoints, operations, and adoption and readiness are included as part of the environmental discovery questionnaire.</span></span> <span data-ttu-id="ce4f4-123">Trabalhe com sua equipe de projeto para fornecer as informações solicitadas com o máximo de detalhes possível para facilitar suas atividades de planejamento.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-123">Work with your project team to provide the requested information with as much detail as possible to facilitate your planning activities.</span></span>

<span data-ttu-id="ce4f4-124">[O questionário](upgrade-plan-journey-discovery-questionnaire.md) se divide nas seções a seguir para confirmar a preparação da sua organização para a implantação de suas equipes em várias áreas principais:</span><span class="sxs-lookup"><span data-stu-id="ce4f4-124">[The questionnaire](upgrade-plan-journey-discovery-questionnaire.md) is divided into the following sections to confirm your organization's readiness for your Teams deployment in several major areas:</span></span>

- <span data-ttu-id="ce4f4-125">Detalhes da organização do Microsoft 365 ou do Office 365</span><span class="sxs-lookup"><span data-stu-id="ce4f4-125">Microsoft 365 or Office 365 organization details</span></span>
- <span data-ttu-id="ce4f4-126">Resumo da plataforma de colaboração existente</span><span class="sxs-lookup"><span data-stu-id="ce4f4-126">Existing collaboration platform summary</span></span>
- <span data-ttu-id="ce4f4-127">Detalhes da implantação da plataforma de colaboração</span><span class="sxs-lookup"><span data-stu-id="ce4f4-127">Collaboration platform deployment details</span></span>
- <span data-ttu-id="ce4f4-128">Rede e acesso aos serviços do Microsoft 365 ou do Office 365</span><span class="sxs-lookup"><span data-stu-id="ce4f4-128">Networking and access to Microsoft 365 or Office 365 services</span></span>
- <span data-ttu-id="ce4f4-129">Pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="ce4f4-129">Endpoints</span></span>
- <span data-ttu-id="ce4f4-130">Operações</span><span class="sxs-lookup"><span data-stu-id="ce4f4-130">Operations</span></span>
- <span data-ttu-id="ce4f4-131">Adoção e preparação</span><span class="sxs-lookup"><span data-stu-id="ce4f4-131">Adoption and readiness</span></span>

> [!TIP]
> <span data-ttu-id="ce4f4-132">Você pode começar copiando o questionário em um documento do Microsoft Word.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-132">You can start by copying the questionnaire into a Microsoft Word document.</span></span> <span data-ttu-id="ce4f4-133">Tente responder a todas as perguntas e capturar todos os detalhes durante a mudança.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-133">Try to answer all questions and capture all details as you move through.</span></span>

<table>
<tr><td><img src="media/audio_conferencing_image7.png" alt="An icon depicting a decision point"/> <br/><span data-ttu-id="ce4f4-134">Ponto de decisão</span><span class="sxs-lookup"><span data-stu-id="ce4f4-134">Decision point</span></span></td><td><ul><li><span data-ttu-id="ce4f4-135">Quem será o responsável pela conclusão de uma avaliação de ambiente?</span><span class="sxs-lookup"><span data-stu-id="ce4f4-135">Who will be responsible for completing an environment assessment?</span></span></li></ul></td></tr>
<tr><td><img src="media/audio_conferencing_image9.png" alt="An icon depicting the next step"/><br/><span data-ttu-id="ce4f4-136">Próxima etapa</span><span class="sxs-lookup"><span data-stu-id="ce4f4-136">Next step</span></span></td><td><ul><li><span data-ttu-id="ce4f4-137">Documentar os resultados da avaliação do ambiente.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-137">Document the results of the environment assessment.</span></span></li></ul></td></tr>
</table>


## <a name="project-team"></a><span data-ttu-id="ce4f4-138">Equipe do projeto</span><span class="sxs-lookup"><span data-stu-id="ce4f4-138">Project team</span></span>

<span data-ttu-id="ce4f4-139">Certifique-se de ter participado das pessoas certas para a sua equipe de projeto.</span><span class="sxs-lookup"><span data-stu-id="ce4f4-139">Ensure that you've engaged the right people for your project team.</span></span> <span data-ttu-id="ce4f4-140">Verifique as etapas que você concluiu em [inscrever seus participantes do projeto](upgrade-enlist-stakeholders.md).</span><span class="sxs-lookup"><span data-stu-id="ce4f4-140">Verify the steps you completed in [Enlist your project stakeholders](upgrade-enlist-stakeholders.md).</span></span>

<span data-ttu-id="ce4f4-141">Depois de avaliar seu ambiente, prossiga para a próxima etapa: [preparar o serviço](upgrade-prepare-environment-prepare-service.md).</span><span class="sxs-lookup"><span data-stu-id="ce4f4-141">After you evaluate your environment, proceed to the next step: [Prepare your service](upgrade-prepare-environment-prepare-service.md).</span></span>
