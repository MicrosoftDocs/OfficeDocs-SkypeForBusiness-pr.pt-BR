---
title: Qualidade da experiência do usuário | Microsoft Teams | Perguntas e | Qualidade da chamada
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: conceptual
ms.service: msteams
audience: admin
ms.reviewer: landerl
description: O administrador pode saber mais sobre as tarefas e atividades necessárias para monitorar a qualidade e o uso do Microsoft Teams.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom:
- Teams-upgrade-guidance
- seo-marvel-apr2020
ms.collection:
- Teams_ITAdmin_JourneyFromSfB
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: d57f01887961ad0c458b13db20ba79023272bcdf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49808991"
---
# <a name="quality-of-experience-review-guide"></a><span data-ttu-id="44f83-103">Guia de revisão da experiência de qualidade</span><span class="sxs-lookup"><span data-stu-id="44f83-103">Quality of Experience Review Guide</span></span>

<span data-ttu-id="44f83-104">![Diagrama realçando o estágio de Excelência Operacional da jornada de atualização](media/upgrade-banner-op-excellence.png "Estágios da jornada de atualização, com ênfase no estágio de Excelência Operacional")</span><span class="sxs-lookup"><span data-stu-id="44f83-104">![Diagram highlighting Operational Excellence stage of upgrade journey](media/upgrade-banner-op-excellence.png "Stages of the upgrade journey, with emphasis on the Operational Excellence stage")</span></span>

<span data-ttu-id="44f83-105">Este artigo faz parte do estágio de Excelência Operacional da sua jornada de atualização, que começa assim que você conclui a atualização do Skype for Business para o Teams.</span><span class="sxs-lookup"><span data-stu-id="44f83-105">This article is part of the Operational Excellence stage of your upgrade journey, which begins as soon as you've completed your upgrade from Skype for Business to Teams.</span></span>

## <a name="improve-and-monitor-call-quality"></a><span data-ttu-id="44f83-106">Melhorar e monitorar a qualidade da chamada</span><span class="sxs-lookup"><span data-stu-id="44f83-106">Improve and monitor call quality</span></span>

<span data-ttu-id="44f83-107">[Melhorar e monitorar](monitor-call-quality-qos.md) a qualidade da chamada para o Teams inclui um conjunto de atividades que avaliam e fornecem orientações de correção em áreas principais que têm maior impacto sobre como melhorar a experiência do usuário, conforme ilustrado abaixo.</span><span class="sxs-lookup"><span data-stu-id="44f83-107">[Improve and monitor call quality for Teams](monitor-call-quality-qos.md) includes a set of activities that assess and provide remediation guidance in key areas that have the greatest impact on improving the user experience, as illustrated below.</span></span>

<span data-ttu-id="44f83-108">![Ilustração das principais áreas a examinar durante uma Revisão.](media/plan-my-service-management-image2.png "As principais áreas a examinar durante uma Revisão de Qualidade da Experiência: áudio, confiabilidade e resultados da pesquisa do usuário.")</span><span class="sxs-lookup"><span data-stu-id="44f83-108">![Illustration of the key areas to examine during a Review.](media/plan-my-service-management-image2.png "The key areas to examine during a Quality of Experience Review: audio, reliability, and user survey results.")</span></span>

<span data-ttu-id="44f83-109">Ao avaliar e remediar continuamente as áreas descritas no guia, você pode reduzir seu potencial para afetar negativamente a experiência do usuário.</span><span class="sxs-lookup"><span data-stu-id="44f83-109">By continually assessing and remediating the areas described in the guide, you can reduce their potential to negatively affect user experience.</span></span> <span data-ttu-id="44f83-110">A maioria dos problemas de experiência do usuário encontrada em uma implantação pode ser agrupada nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="44f83-110">Most user-experience problems encountered in a deployment can be grouped into the following categories:</span></span>

- <span data-ttu-id="44f83-111">Configuração incompleta do firewall ou proxy</span><span class="sxs-lookup"><span data-stu-id="44f83-111">Incomplete firewall or proxy configuration</span></span>

- <span data-ttu-id="44f83-112">Cobertura insatisfatória da rede Wi-Fi</span><span class="sxs-lookup"><span data-stu-id="44f83-112">Poor Wi-Fi coverage</span></span>

- <span data-ttu-id="44f83-113">Largura de banda insuficiente</span><span class="sxs-lookup"><span data-stu-id="44f83-113">Insufficient bandwidth</span></span>

- <span data-ttu-id="44f83-114">VPN</span><span class="sxs-lookup"><span data-stu-id="44f83-114">VPN</span></span>

- <span data-ttu-id="44f83-115">Uso de dispositivos de áudio internos ou não otimizados</span><span class="sxs-lookup"><span data-stu-id="44f83-115">Use of unoptimized or built-in audio devices</span></span>

- <span data-ttu-id="44f83-116">Dispositivos de rede ou sub-redes com problemas</span><span class="sxs-lookup"><span data-stu-id="44f83-116">Problematic subnets or network devices</span></span>

<span data-ttu-id="44f83-117">As diretrizes fornecidas em Melhorar e monitorar a qualidade de chamada do [Teams](monitor-call-quality-qos.md) se concentram no uso do CQD (Painel de Qualidade da Chamada) Online como a principal ferramenta para relatar e investigar cada área descrita, com foco no áudio para maximizar a adoção e o impacto.</span><span class="sxs-lookup"><span data-stu-id="44f83-117">The guidance provided in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md) focuses on using Call Quality Dashboard (CQD) Online as the primary tool to report and investigate each area described, with a focus on audio to maximize adoption and impact.</span></span> <span data-ttu-id="44f83-118">Todas as otimizações feitas à rede para melhorar a experiência de área também se converterão diretamente em aprimoramentos no vídeo e no compartilhamento da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="44f83-118">Any optimizations made to the network to improve the audio experience will also directly translate to improvements in video and desktop sharing.</span></span>

<span data-ttu-id="44f83-119">É altamente recomendável nomear o campeão de qualidade desde o início.</span><span class="sxs-lookup"><span data-stu-id="44f83-119">We highly recommend that you nominate the quality champion early on.</span></span> <span data-ttu-id="44f83-120">Depois de indicados, eles devem começar a se familiarizar com o conteúdo em Melhorar e monitorar a qualidade da chamada [para o Teams.](monitor-call-quality-qos.md)</span><span class="sxs-lookup"><span data-stu-id="44f83-120">After being nominated, they should start to familiarize themselves with the content in [Improve and monitor call quality for Teams](monitor-call-quality-qos.md).</span></span>

<!--ENDOFSECTION-->
