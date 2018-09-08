---
title: Qualidade da experiência Revise o guia - equipes da Microsoft
author: turgayo
ms.author: turgayo
manager: serdars
ms.date: 07/16/2018
ms.topic: article
ms.service: msteams
ms.reviewer: dearbeen
description: Tarefas e atividades necessárias para monitorar a qualidade e o uso do Microsoft Teams
localization_priority: Normal
search.appverid: MET150
ms.custom: Teams-upgrade-guidance
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
ms.openlocfilehash: f74757654fffc46276907e54c41223fe7d533f2e
ms.sourcegitcommit: 940cb253923e3537cb7fb4d7ce875ed9bfbb72db
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23886066"
---
<span data-ttu-id="eecd2-103">![Estágios da atualização jornada, com ênfase no estágio excelência operacional] (media/upgrade-banner-op-excellence.png "Estágios da atualização jornada, com ênfase no estágio excelência operacional")</span><span class="sxs-lookup"><span data-stu-id="eecd2-103">![Stages of the upgrade journey, with emphasis on the Operational Excellence stage](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="eecd2-104">Este artigo faz parte do estágio da sua jornada de atualização, que começa assim que você concluir a atualização do Skype para negócios às equipes excelência operacional.</span><span class="sxs-lookup"><span data-stu-id="eecd2-104">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="eecd2-105">Qualidade da experiência Revise o guia</span><span class="sxs-lookup"><span data-stu-id="eecd2-105">Quality of Experience Review Guide</span></span>

<span data-ttu-id="eecd2-106">A [Qualidade da experiência Revise o guia](https://aka.ms/qerguide) inclui um conjunto de atividades que avaliar e oferecem orientação de remediação em áreas principais que têm o maior impacto sobre como melhorar a experiência do usuário, como ilustrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="eecd2-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="eecd2-107">![As principais áreas para examinar durante uma análise de qualidade de experiência: áudio, a confiabilidade e resultados de pesquisa do usuário.] (media/plan-my-service-management-image2.png "As principais áreas para examinar durante uma análise de qualidade de experiência: áudio, a confiabilidade e resultados de pesquisa do usuário.")</span><span class="sxs-lookup"><span data-stu-id="eecd2-107">![The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="eecd2-108">Avaliação e correção as áreas descritas no guia continuamente, você pode reduzir seu potencial para afetar negativamente a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="eecd2-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="eecd2-109">A maioria dos problemas de experiência do usuário encontrados em uma implantação podem ser agrupados nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="eecd2-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

-   <span data-ttu-id="eecd2-110">Configuração de firewall ou proxy incompleta</span><span class="sxs-lookup"><span data-stu-id="eecd2-110">Incomplete firewall or proxy configuration</span></span>

-   <span data-ttu-id="eecd2-111">Baixa cobertura de Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="eecd2-111">Poor Wi-Fi coverage</span></span>

-   <span data-ttu-id="eecd2-112">Largura de banda insuficiente</span><span class="sxs-lookup"><span data-stu-id="eecd2-112">Insufficient bandwidth</span></span>

-   <span data-ttu-id="eecd2-113">VPN</span><span class="sxs-lookup"><span data-stu-id="eecd2-113">VPN</span></span>

-   <span data-ttu-id="eecd2-114">Uso de dispositivos de áudio não otimizados ou internos</span><span class="sxs-lookup"><span data-stu-id="eecd2-114">Use of unoptimized or built-in audio devices</span></span>

-   <span data-ttu-id="eecd2-115">Sub-redes problemáticos ou dispositivos de rede</span><span class="sxs-lookup"><span data-stu-id="eecd2-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="eecd2-116">As diretrizes fornecidas no guia do Quality of Experience revisão enfoca usando Online do painel de controle de qualidade de chamada (CQD) como a ferramenta principal para relatar e investigar cada área descrita, com foco para maximizar a adoção e o impacto de áudio.</span><span class="sxs-lookup"><span data-stu-id="eecd2-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="eecd2-117">Otimizações de feitas à rede para melhorar a experiência de áudio também diretamente traduzirá melhorias no compartilhamento de área de trabalho e de vídeo.</span><span class="sxs-lookup"><span data-stu-id="eecd2-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="eecd2-118">É altamente recomendável que você designar desde o início do campeão de qualidade.</span><span class="sxs-lookup"><span data-stu-id="eecd2-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="eecd2-119">Depois que está sendo indicado, eles devem iniciar podem se familiarizar com o conteúdo no [Guia de revisão do Quality of Experience](https://aka.ms/qerguide).</span><span class="sxs-lookup"><span data-stu-id="eecd2-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->