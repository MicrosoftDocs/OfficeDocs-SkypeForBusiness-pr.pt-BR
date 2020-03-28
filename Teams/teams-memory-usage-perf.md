---
title: Como o Microsoft Teams usa a memória
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Como o Microsoft Teams usa a memória do sistema e porque o uso da memória é o mesmo entre o aplicativo da área de trabalho e o aplicativo Web.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 59940eafcdb6f86961b3cd6805cb9c5bb40f9fb2
ms.sourcegitcommit: e710bb8dbbd084912cbf509896515a674ab5e19f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2020
ms.locfileid: "43033395"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="2fd05-103">Como o Microsoft Teams usa a memória</span><span class="sxs-lookup"><span data-stu-id="2fd05-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="2fd05-104">Alguns usuários do Microsoft Teams têm perguntas sobre como o Microsoft Teams usa a memória.</span><span class="sxs-lookup"><span data-stu-id="2fd05-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="2fd05-105">Este artigo descreve como a memória é usada pelo Teams e por que o aplicativo da área de trabalho do Teams (aplicativo) e o aplicativo Web Teams não impedem que outros aplicativos e cargas de trabalho no mesmo computador tenham memória suficiente para serem executados de forma ideal.</span><span class="sxs-lookup"><span data-stu-id="2fd05-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="2fd05-106">O Teams foi projetado para usar a tecnologia da Web moderna.</span><span class="sxs-lookup"><span data-stu-id="2fd05-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="2fd05-107">Para fazer isso, o cliente da equipe de trabalho do teams foi desenvolvido em uma área de uso.</span><span class="sxs-lookup"><span data-stu-id="2fd05-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="2fd05-108">Esse é o mesmo mecanismo de renderização por trás de muitos dos navegadores mais populares do dia, incluindo o Edge e o Chrome.</span><span class="sxs-lookup"><span data-stu-id="2fd05-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="2fd05-109">Como as equipes funcionam</span><span class="sxs-lookup"><span data-stu-id="2fd05-109">How Teams works</span></span>

<span data-ttu-id="2fd05-110">As equipes que estão sendo projetadas para o sistema de redes com o sistema de redes e do sistema operacional são mais rápidas, e também mantém a paridade entre versões do Team em diferentes sistemas operacionais (Windows, Mac e Linux).</span><span class="sxs-lookup"><span data-stu-id="2fd05-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="2fd05-111">Essa paridade é possível porque a Chromium e a da digital mantêm uma base de código semelhante em todas as versões.</span><span class="sxs-lookup"><span data-stu-id="2fd05-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="2fd05-112">Outra vantagem dessa arquitetura é que há um perfil de uso de memória semelhante entre o aplicativo Web Teams e a versão da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2fd05-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="2fd05-113">As versões do aplicativo Web e da área de trabalho usam memória de maneira semelhante à de um navegador usá-lo.</span><span class="sxs-lookup"><span data-stu-id="2fd05-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="2fd05-114">Mais informações sobre o recurso do recurso de dados de dados do recurso de dados [do seu site](https://electronjs.org/).</span><span class="sxs-lookup"><span data-stu-id="2fd05-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="2fd05-115">Consulte [Chromium uso da memória](https://www.chromium.org/developers/memory-usage-backgrounder) e [conceitos principais na memória do Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2fd05-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="2fd05-116">A imagem a seguir mostra os usos de memória lado a lado do aplicativo Teams desktop para Windows e o aplicativo Web Teams (neste exemplo, em execução no Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="2fd05-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Uso da memória do aplicativo Web do Teams e do aplicativo Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="2fd05-118">Uso de memória no Teams</span><span class="sxs-lookup"><span data-stu-id="2fd05-118">Memory usage in Teams</span></span>

<span data-ttu-id="2fd05-119">É importante entender o comportamento *esperado* do teams quando chega à memória do sistema e conhecer os sintomas de problemas de memória de sistema realmente problemáticos.</span><span class="sxs-lookup"><span data-stu-id="2fd05-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="2fd05-120">Uso de memória esperado por Teams</span><span class="sxs-lookup"><span data-stu-id="2fd05-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="2fd05-121">Não importa se você está executando o aplicativo da área de trabalho do teams ou o aplicativo Web do Teams, o Chromium detecta a quantidade de memória do sistema disponível e utiliza o suficiente para otimizar a experiência de renderização.</span><span class="sxs-lookup"><span data-stu-id="2fd05-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="2fd05-122">Quando outros aplicativos ou serviços exigem a memória do sistema, o Chromium fornece a memória a esses processos.</span><span class="sxs-lookup"><span data-stu-id="2fd05-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="2fd05-123">O Chromium ajusta o uso da memória do teams continuamente para otimizar o desempenho da equipe sem afetar mais nada em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="2fd05-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="2fd05-124">Dessa forma, cargas de trabalho Chromium semelhantes podem utilizar quantidades variáveis de memória, dependendo da quantidade de memória do sistema que está disponível.</span><span class="sxs-lookup"><span data-stu-id="2fd05-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="2fd05-125">O gráfico a seguir descreve o uso da memória por equipes em quatro sistemas separados, cada um com uma quantidade de memória diferente disponível.</span><span class="sxs-lookup"><span data-stu-id="2fd05-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="2fd05-126">Cada um dos sistemas está processando cargas de trabalho semelhantes (os mesmos aplicativos abertos e em execução).</span><span class="sxs-lookup"><span data-stu-id="2fd05-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Uso de memória do Team em diferentes sistemas](media/teams-memory-usage.png)

<span data-ttu-id="2fd05-128">Quando os computadores tiverem mais memória, o Microsoft Teams vai usar essa memória.</span><span class="sxs-lookup"><span data-stu-id="2fd05-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="2fd05-129">Em sistemas em que a memória está escassa, as equipes usarão menos.</span><span class="sxs-lookup"><span data-stu-id="2fd05-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="2fd05-130">Sintomas de problemas de memória do sistema</span><span class="sxs-lookup"><span data-stu-id="2fd05-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="2fd05-131">Se você vir um ou mais dos seguintes sintomas em seu computador, você pode ter um problema sério de memória do sistema:</span><span class="sxs-lookup"><span data-stu-id="2fd05-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="2fd05-132">Alta utilização de memória quando vários aplicativos grandes são executados simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="2fd05-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="2fd05-133">Baixo desempenho do sistema ou aplicativos travam.</span><span class="sxs-lookup"><span data-stu-id="2fd05-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="2fd05-134">Uso de memória geral do sistema sustentável de 90% ou mais em todos os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="2fd05-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="2fd05-135">Com essa quantidade de uso de memória, as equipes devem dar memória novamente para outros aplicativos e cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="2fd05-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="2fd05-136">Uso de memória sustentada de 90% pode significar que o Microsoft Teams não está fornecendo memória de volta ao sistema, o que indica um problema.</span><span class="sxs-lookup"><span data-stu-id="2fd05-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="2fd05-137">As imagens a seguir mostram exemplos de modos de exibição no Gerenciador de tarefas quando o uso da memória do sistema é anormalmente alto.</span><span class="sxs-lookup"><span data-stu-id="2fd05-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Modo de exibição uso de memória do teams no Gerenciador de tarefas](media/teams-memory-high-mem-process-list.png)

![Gráfico de uso de memória do teams no Gerenciador de tarefas](media/teams-memory-high-mem-process-list2.png)
