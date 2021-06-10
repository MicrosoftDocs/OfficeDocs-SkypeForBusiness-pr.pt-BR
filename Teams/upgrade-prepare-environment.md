---
title: Preparar seu ambiente para atualização para Teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: landerl
audience: admin
description: Valide o ambiente e a preparação da rede antes de iniciar a atualização de Skype for Business para Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-mar2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e154dc5844c4b8f3994c8c7bc00865c494a4c8c6
ms.sourcegitcommit: 32e3bb588abcbeded2d885483384c06706b280eb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2021
ms.locfileid: "52282138"
---
# <a name="prepare-your-environment-for-upgrading-to-teams"></a><span data-ttu-id="7d7b6-103">Preparar seu ambiente para atualização para Teams</span><span class="sxs-lookup"><span data-stu-id="7d7b6-103">Prepare your environment for upgrading to Teams</span></span>

<span data-ttu-id="7d7b6-104">![Atualizar diagrama de jornada, enfatizando o estágio de Preparação Técnica](media/upgrade-banner-tech-readiness.png "Estágios da jornada de atualização, com ênfase no estágio de Preparação Técnica")</span><span class="sxs-lookup"><span data-stu-id="7d7b6-104">![Upgrade journey diagram, emphasizing the Technical Readiness stage](media/upgrade-banner-tech-readiness.png "Stages of the upgrade journey, with emphasis on the Technical Readiness stage")</span></span>

<span data-ttu-id="7d7b6-105">Este artigo faz parte do estágio de Preparação Técnica da sua jornada de atualização, uma atividade que você realiza em paralelo com o estágio de Preparação do Usuário.</span><span class="sxs-lookup"><span data-stu-id="7d7b6-105">This article is part of the Technical Readiness stage of your upgrade journey, an activity you complete in parallel with the User Readiness stage.</span></span> <span data-ttu-id="7d7b6-106">Antes de prosseguir, confirme se você concluiu essas atividades de estágios anteriores:</span><span class="sxs-lookup"><span data-stu-id="7d7b6-106">Before proceeding, confirm that you've completed these activities from previous stages:</span></span>

- [<span data-ttu-id="7d7b6-107">Alistou as partes envolvidas no seu projeto</span><span class="sxs-lookup"><span data-stu-id="7d7b6-107">Enlisted your project stakeholders</span></span>](upgrade-enlist-stakeholders.md)
- [<span data-ttu-id="7d7b6-108">Definiu o escopo do seu projeto</span><span class="sxs-lookup"><span data-stu-id="7d7b6-108">Defined your project scope</span></span>](./upgrade-define-project-scope.md)
- [<span data-ttu-id="7d7b6-109">Compreendeu a coexistência e interoperabilidade do Skype for Business e do Teams</span><span class="sxs-lookup"><span data-stu-id="7d7b6-109">Understood coexistence and interoperability of Skype for Business and Teams</span></span>](./teams-and-skypeforbusiness-coexistence-and-interoperability.md)
- [<span data-ttu-id="7d7b6-110">Escolheu sua jornada de atualização</span><span class="sxs-lookup"><span data-stu-id="7d7b6-110">Chosen your upgrade journey</span></span>](upgrade-and-coexistence-of-skypeforbusiness-and-teams.md)

<span data-ttu-id="7d7b6-111">Para impulsionar uma atualização Teams bem-sucedida em sua organização, é importante que você valide seu ambiente Skype for Business atual e sua preparação de rede.</span><span class="sxs-lookup"><span data-stu-id="7d7b6-111">To drive a successful Teams upgrade in your organization, it's important that you validate your current Skype for Business environment and your network readiness.</span></span> <span data-ttu-id="7d7b6-112">A preparação do ambiente atual ajudará a garantir uma experiência de usuário de alta qualidade agora, além de melhorar a qualidade da experiência do usuário no Teams.</span><span class="sxs-lookup"><span data-stu-id="7d7b6-112">Preparing your current environment will help ensure a high-quality user experience now, in addition to improving the quality of the user experience in Teams.</span></span> <span data-ttu-id="7d7b6-113">O tempo necessário para planejar etapas individuais pode ajudar a acelerar sua implantação e garantir que você não tenha ignorado nenhum item de ação importante.</span><span class="sxs-lookup"><span data-stu-id="7d7b6-113">Taking time to plan individual steps can help accelerate your deployment and ensure that you haven't skipped any important action items.</span></span>

<span data-ttu-id="7d7b6-114">Conclua essas atividades em paralelo com a preparação de preparação do usuário:</span><span class="sxs-lookup"><span data-stu-id="7d7b6-114">Complete these activities in parallel with your user readiness preparation:</span></span>

- <span data-ttu-id="7d7b6-115">[Prepare sua equipe de IT](upgrade-prepare-IT-pros.md) para ajudar a garantir que eles tenham o que precisam para uma jornada de atualização bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="7d7b6-115">[Prepare your IT staff](upgrade-prepare-IT-pros.md) to help ensure they have what they need for a successful upgrade journey.</span></span>
- <span data-ttu-id="7d7b6-116">Verifique se seu ambiente atende a todos [os pré-requisitos](upgrade-plan-journey-prerequisites.md)e entenda as dependências entre Microsoft 365 ou Office 365 serviços e Teams.</span><span class="sxs-lookup"><span data-stu-id="7d7b6-116">Verify that your environment meets all [prerequisites](upgrade-plan-journey-prerequisites.md), and understand dependencies among Microsoft 365 or Office 365 services and Teams.</span></span>
- <span data-ttu-id="7d7b6-117">[Avalie seu ambiente](upgrade-plan-journey-evaluate-environment.md) executando a descoberta ambiental usando um questionário de exemplo para confirmar a preparação da sua organização para realizar uma jornada de atualização bem-sucedida para Teams.</span><span class="sxs-lookup"><span data-stu-id="7d7b6-117">[Evaluate your environment](upgrade-plan-journey-evaluate-environment.md) by performing environmental discovery by using a sample questionnaire to confirm your organization's readiness to undertake a successful upgrade journey to Teams.</span></span>
- <span data-ttu-id="7d7b6-118">[Prepare sua rede por](prepare-network.md) meio do planejamento, preparação e das etapas de correção necessárias para que sua rede suporte Teams cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="7d7b6-118">[Prepare your network](prepare-network.md) through planning, preparation, and taking any necessary remediation steps for your network to support Teams workloads.</span></span>
- <span data-ttu-id="7d7b6-119">[Prepare seu serviço](upgrade-prepare-environment-prepare-service.md) para a adoção usando listas de verificação de integração para garantir que Teams configuração do Teams esteja pronta para dar suporte à migração de seus usuários de Skype for Business para Teams.</span><span class="sxs-lookup"><span data-stu-id="7d7b6-119">[Prepare your service](upgrade-prepare-environment-prepare-service.md) for rollout by using onboarding checklists to ensure that your Teams configuration is ready to support migrating your users from Skype for Business to Teams.</span></span>