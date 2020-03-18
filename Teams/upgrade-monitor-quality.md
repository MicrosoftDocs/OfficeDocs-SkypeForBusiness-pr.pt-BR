---
title: Qualidade da experiência do usuário | Microsoft Teams | QoS | Qualidade da chamada
author: lanachin
ms.author: v-lanac
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: dearbeen
description: Tarefas e atividades necessárias para monitorar a qualidade e o uso do Microsoft Teams
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
ms.openlocfilehash: e870c6e6561bac991e7b9498ef76162ec1fa2eb9
ms.sourcegitcommit: 5d64e30a1984a4b1d9ff36e2e1721cb4bbf9e450
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/17/2020
ms.locfileid: "42706971"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="979c8-103">Guia de revisão da experiência de qualidade</span><span class="sxs-lookup"><span data-stu-id="979c8-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="979c8-104">![Diagrama realçando a excelência operacional estágio da viagem de atualização](media/upgrade-banner-op-excellence.png "Estágios da jornada da atualização, com ênfase no estágio Operational de excelência")</span><span class="sxs-lookup"><span data-stu-id="979c8-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="979c8-105">Este artigo faz parte do estágio operacional de excelência da sua jornada de atualização, que começa assim que você concluiu a atualização do Skype for Business para o Teams.</span><span class="sxs-lookup"><span data-stu-id="979c8-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

<span data-ttu-id="979c8-106">O [Guia de revisão da qualidade da experiência](https://aka.ms/qerguide) inclui um conjunto de atividades que avaliam e fornecem orientação de correção em áreas importantes que têm o maior impacto na melhoria da experiência do usuário, conforme ilustrado a seguir.</span><span class="sxs-lookup"><span data-stu-id="979c8-106">The [Quality of Experience Review Guide](https://aka.ms/qerguide) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="979c8-107">![Ilustração das principais áreas a serem examinadas durante uma crítica.](media/plan-my-service-management-image2.png "As principais áreas a serem examinadas durante uma revisão de qualidade da experiência: áudio, confiabilidade e resultados da pesquisa de usuários.")</span><span class="sxs-lookup"><span data-stu-id="979c8-107">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="979c8-108">Ao avaliar continuamente e corrigir as áreas descritas no guia, você pode reduzir o potencial de afetar negativamente a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="979c8-108">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="979c8-109">A maioria dos problemas de experiência do usuário encontrada em uma implantação pode ser agrupada nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="979c8-109">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="979c8-110">Configuração incompleta do firewall ou proxy</span><span class="sxs-lookup"><span data-stu-id="979c8-110">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="979c8-111">Cobertura insatisfatória da rede Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="979c8-111">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="979c8-112">Largura de banda insuficiente</span><span class="sxs-lookup"><span data-stu-id="979c8-112">Insufficient bandwidth</span></span>

- <span data-ttu-id="979c8-113">VPN</span><span class="sxs-lookup"><span data-stu-id="979c8-113">VPN</span></span>

- <span data-ttu-id="979c8-114">Uso de dispositivos de áudio internos ou não otimizados</span><span class="sxs-lookup"><span data-stu-id="979c8-114">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="979c8-115">Dispositivos de rede ou sub-redes com problemas</span><span class="sxs-lookup"><span data-stu-id="979c8-115">Problematic subnets or network devices</span></span>

<span data-ttu-id="979c8-116">As diretrizes fornecidas no guia de revisão de qualidade de experiência concentram-se em usar o painel de qualidade de chamada (CQD) online como a principal ferramenta para denunciar e investigar cada área descrita, com foco no áudio para maximizar a adoção e o impacto.</span><span class="sxs-lookup"><span data-stu-id="979c8-116">The guidance provided in the Quality of Experience Review Guide focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="979c8-117">Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="979c8-117">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="979c8-118">É altamente recomendável que você innomeado o especialista em qualidade no início.</span><span class="sxs-lookup"><span data-stu-id="979c8-118">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="979c8-119">Depois de serem nomeados, eles devem começar a se familiarizar com o conteúdo no [Guia de revisão da qualidade da experiência](https://aka.ms/qerguide).</span><span class="sxs-lookup"><span data-stu-id="979c8-119">After being nominated, they should start to familiarize themselves with the content in the [Quality of Experience Review Guide](https://aka.ms/qerguide).</span></span>

<!--ENDOFSECTION-->
