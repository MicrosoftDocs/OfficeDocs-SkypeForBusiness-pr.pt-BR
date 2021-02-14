---
title: Como o Microsoft Teams usa a memória
author: msdmaguire
ms.author: dmaguire
manager: serdars
ms.topic: article
ms.service: msteams
ms.reviewer: ramesa
audience: admin
description: Saiba mais sobre o uso da memória do sistema Microsoft Teams e por que o uso da memória é o mesmo entre o aplicativo da área de trabalho e o aplicativo Web.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_PracticalGuidance
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.custom: seo-marvel-jun2020
ms.openlocfilehash: d218c71a0e3ecdde40559d67e1ad3a408d65a5d9
ms.sourcegitcommit: 43dc627e9fef31a2508f54acf741000551ff68b5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2020
ms.locfileid: "48878715"
---
# <a name="how-microsoft-teams-uses-memory"></a><span data-ttu-id="29b81-103">Como o Microsoft Teams usa a memória</span><span class="sxs-lookup"><span data-stu-id="29b81-103">How Microsoft Teams uses memory</span></span>

<span data-ttu-id="29b81-104">Alguns usuários do Microsoft Teams têm dúvidas sobre como o Teams usa a memória.</span><span class="sxs-lookup"><span data-stu-id="29b81-104">Some Microsoft Teams users have questions about how Teams uses memory.</span></span> <span data-ttu-id="29b81-105">Este artigo descreve como a memória é usada pelo Teams e por que o aplicativo da área de trabalho do Teams (aplicativo) e o aplicativo Web do Teams não impedem que outros aplicativos e cargas de trabalho no mesmo computador tenha memória suficiente para funcionar de forma ideal.</span><span class="sxs-lookup"><span data-stu-id="29b81-105">This article describes how memory is used by Teams, and why the Teams desktop application (app) and the Teams web app do not prevent other apps and workloads on the same computer from having enough memory to run optimally.</span></span> <span data-ttu-id="29b81-106">O Teams foi projetado para usar a tecnologia da Web moderna.</span><span class="sxs-lookup"><span data-stu-id="29b81-106">Teams is designed to use modern web technology.</span></span> <span data-ttu-id="29b81-107">Para isso, o cliente de área de trabalho do Teams foi desenvolvido em Eletrônica, que usa o Chromium para renderização.</span><span class="sxs-lookup"><span data-stu-id="29b81-107">To achieve this, the Teams desktop client was developed on Electron, which uses Chromium for rendering.</span></span> <span data-ttu-id="29b81-108">Esse é o mesmo mecanismo de renderização por trás de muitos dos navegadores mais populares de hoje, incluindo o Edge e o Chrome.</span><span class="sxs-lookup"><span data-stu-id="29b81-108">This is the same rendering engine behind many of today's most popular browsers, including Edge and Chrome.</span></span>

## <a name="how-teams-works"></a><span data-ttu-id="29b81-109">Como o Teams funciona</span><span class="sxs-lookup"><span data-stu-id="29b81-109">How Teams works</span></span>

<span data-ttu-id="29b81-110">As equipes projetadas em Eletrônica permitem um desenvolvimento mais rápido e também mantém a paridade entre as versões do Teams em diferentes sistemas operacionais (Windows, Mac e Linux).</span><span class="sxs-lookup"><span data-stu-id="29b81-110">Teams being designed on Electron allows for faster development, and it also maintains parity between Teams versions across different operating systems (Windows, Mac, and Linux).</span></span> <span data-ttu-id="29b81-111">Essa paridade é possível porque o Electron e o Chromium mantêm uma base de código semelhante em todas as versões.</span><span class="sxs-lookup"><span data-stu-id="29b81-111">This parity is possible because Electron and Chromium maintain a similar code base across all versions.</span></span> <span data-ttu-id="29b81-112">Outra vantagem dessa arquitetura é que há um perfil de uso de memória semelhante entre o aplicativo Web do Teams e a versão da área de trabalho.</span><span class="sxs-lookup"><span data-stu-id="29b81-112">Another advantage of this architecture is there's a similar memory usage profile between the Teams web app and the desktop version.</span></span> <span data-ttu-id="29b81-113">Tanto o aplicativo Web quanto as versões da área de trabalho usam a memória de maneira semelhante à forma como um navegador a usaria.</span><span class="sxs-lookup"><span data-stu-id="29b81-113">Both the web app and the desktop versions use memory in a similar way to how a browser would use it.</span></span> <span data-ttu-id="29b81-114">Mais informações sobre o Electron estão disponíveis em [seu site.](https://electronjs.org/)</span><span class="sxs-lookup"><span data-stu-id="29b81-114">More information about Electron is available at [their Web site](https://electronjs.org/).</span></span>

<span data-ttu-id="29b81-115">Confira [o Uso da Memória Chromium e](https://www.chromium.org/developers/memory-usage-backgrounder) os Principais [Conceitos na Memória do Chrome](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="29b81-115">See [Chromium Memory Usage](https://www.chromium.org/developers/memory-usage-backgrounder) and [Key Concepts in Chrome Memory](https://chromium.googlesource.com/chromium/src.git/+/master/docs/memory/key_concepts.md) for more information.</span></span>

<span data-ttu-id="29b81-116">A imagem a seguir mostra os usos de memória lado a lado do aplicativo da área de trabalho do Teams para Windows e do aplicativo Teams Web (neste exemplo, em execução no Google Chrome).</span><span class="sxs-lookup"><span data-stu-id="29b81-116">The following image shows side-by-side memory usages of the Teams desktop app for Windows and the Teams Web app (in this example, running in Google Chrome).</span></span>

![Uso da memória do Teams para o aplicativo da área de trabalho e o aplicativo Web](media/teams-memory-clientweb.png)

## <a name="memory-usage-in-teams"></a><span data-ttu-id="29b81-118">Uso da memória no Teams</span><span class="sxs-lookup"><span data-stu-id="29b81-118">Memory usage in Teams</span></span>

<span data-ttu-id="29b81-119">É importante entender  o comportamento esperado do Teams quando se trata de memória do sistema e conhecer os sintomas de problemas realmente problemáticos de memória do sistema.</span><span class="sxs-lookup"><span data-stu-id="29b81-119">It is important to understand the *expected* behavior of Teams when it comes to system memory, and to know the symptoms of truly problematic system memory issues.</span></span>

### <a name="expected-memory-usage-by-teams"></a><span data-ttu-id="29b81-120">Uso esperado da memória pelo Teams</span><span class="sxs-lookup"><span data-stu-id="29b81-120">Expected memory usage by Teams</span></span>

<span data-ttu-id="29b81-121">Se você estiver executando o aplicativo da área de trabalho do Teams ou o aplicativo Web do Teams, o Chromium detecta quanto de memória do sistema está disponível e utiliza o suficiente dessa memória para otimizar a experiência de renderização.</span><span class="sxs-lookup"><span data-stu-id="29b81-121">Whether you're running the Teams desktop app or the Teams web app, Chromium detects how much system memory is available and utilizes enough of that memory to optimize the rendering experience.</span></span> <span data-ttu-id="29b81-122">Quando outros aplicativos ou serviços exigem memória do sistema, o Chromium concede memória a esses processos.</span><span class="sxs-lookup"><span data-stu-id="29b81-122">When other apps or services require system memory, Chromium gives up memory to those processes.</span></span> <span data-ttu-id="29b81-123">O Chromium ajusta o uso da memória do Teams continuamente para otimizar o desempenho do Teams sem afetar nada em execução no momento.</span><span class="sxs-lookup"><span data-stu-id="29b81-123">Chromium tunes Teams memory usage on an ongoing basis in order to optimize Teams performance without impacting anything else currently running.</span></span>

<span data-ttu-id="29b81-124">Dessa forma, cargas de trabalho semelhantes do Chromium podem utilizar várias quantidades de memória, dependendo da quantidade de memória do sistema disponível.</span><span class="sxs-lookup"><span data-stu-id="29b81-124">In this way, similar Chromium workloads can utilize varying amounts of memory, depending on the amount of system memory that is available.</span></span>

<span data-ttu-id="29b81-125">O gráfico a seguir mostra o uso da memória pelo Teams em quatro sistemas separados, cada um com quantidades diferentes de memória disponíveis.</span><span class="sxs-lookup"><span data-stu-id="29b81-125">The following graph depicts memory usage by Teams on four separate systems, each with different amounts of memory available.</span></span> <span data-ttu-id="29b81-126">Cada um dos sistemas está processando cargas de trabalho semelhantes (mesmos aplicativos abertos e em execução).</span><span class="sxs-lookup"><span data-stu-id="29b81-126">Each of the systems is processing similar workloads (same apps open and running).</span></span>

![Uso da memória do Teams em diferentes sistemas](media/teams-memory-usage.png)

<span data-ttu-id="29b81-128">Quando os computadores têm mais memória, o Teams usará essa memória.</span><span class="sxs-lookup"><span data-stu-id="29b81-128">When computers have more memory, Teams will use that memory.</span></span> <span data-ttu-id="29b81-129">Nos sistemas em que a memória está ficando ruim, o Teams usará menos.</span><span class="sxs-lookup"><span data-stu-id="29b81-129">In systems where memory is scarce, Teams will use less.</span></span>

### <a name="symptoms-of-system-memory-issues"></a><span data-ttu-id="29b81-130">Sintomas de problemas de memória do sistema</span><span class="sxs-lookup"><span data-stu-id="29b81-130">Symptoms of system memory issues</span></span>

<span data-ttu-id="29b81-131">Se você vir um ou mais dos seguintes sintomas em seu computador, poderá ter um problema grave de memória do sistema:</span><span class="sxs-lookup"><span data-stu-id="29b81-131">If you see one or more of the following symptoms on your computer, you could have a serious system memory issue:</span></span>

- <span data-ttu-id="29b81-132">Alto uso da memória quando vários aplicativos grandes estão sendo executados simultaneamente.</span><span class="sxs-lookup"><span data-stu-id="29b81-132">High memory use when multiple large applications are running simultaneously.</span></span>
- <span data-ttu-id="29b81-133">Desempenho lento do sistema ou suspensão de aplicativos.</span><span class="sxs-lookup"><span data-stu-id="29b81-133">Slow system performance or applications hanging.</span></span>
- <span data-ttu-id="29b81-134">Uso geral de memória total do sistema de 90% ou superior em todos os aplicativos.</span><span class="sxs-lookup"><span data-stu-id="29b81-134">Sustained overall system memory usage of 90% or higher across all apps.</span></span> <span data-ttu-id="29b81-135">Com essa quantidade de uso de memória, o Teams deve devolver a memória a outros aplicativos e cargas de trabalho.</span><span class="sxs-lookup"><span data-stu-id="29b81-135">With this amount of memory usage, Teams should be giving memory back to other apps and workloads.</span></span> <span data-ttu-id="29b81-136">O uso contínuo de memória de 90% pode significar que o Teams não está dando memória de volta ao sistema, o que indica um problema.</span><span class="sxs-lookup"><span data-stu-id="29b81-136">Sustained memory usage of 90% could mean Teams isn't giving memory back to the system, which indicates a problem.</span></span>

<span data-ttu-id="29b81-137">As imagens a seguir mostram exemplos de exibições no Gerenciador de Tarefas quando o uso da memória do sistema é anormalmente alto.</span><span class="sxs-lookup"><span data-stu-id="29b81-137">The following images show examples of views in Task Manager when system memory usage is abnormally high.</span></span>

![Exibição de uso da memória do Teams no Gerenciador de Tarefas](media/teams-memory-high-mem-process-list.png)

![Gráfico de uso da memória do Teams no Gerenciador de Tarefas](media/teams-memory-high-mem-process-list2.png)
