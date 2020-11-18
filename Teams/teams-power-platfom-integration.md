---
title: Integração do Microsoft Teams com o Microsoft Power Platform
author: lanachin
ms.author: v-lanac
manager: serdars
ms.reviewer: kvivek
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre a integração do Microsoft Teams com as ferramentas de plataforma de energia da Microsoft, incluindo o Power BI, aplicativos de energia, automatização de energia e agentes de energia virtual.
ms.openlocfilehash: 81d673069e972f4627a8bfab18095e81803dd4b1
ms.sourcegitcommit: b282acc1633c2d62bbff0ea77b6b647775ae6dfe
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49085665"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="e6df3-103">Integração do Microsoft Teams com o Microsoft Power Platform</span><span class="sxs-lookup"><span data-stu-id="e6df3-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="e6df3-104">A plataforma de alimentação da Microsoft ajuda os usuários a acelerar o desenvolvimento com ferramentas de código baixo para analisar dados usando o **Power bi**, criar aplicativos personalizados usando **aplicativos de energia**, automatizar processos usando o **Power** bi e criar bots inteligentes usando **agentes de energia virtual** mais rápido do que nunca.</span><span class="sxs-lookup"><span data-stu-id="e6df3-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="e6df3-105">Com o turno para trabalho remoto e híbrido, o Microsoft Teams permitiu às pessoas em todo o mundo continuar a criar, colaborar e se comunicar.</span><span class="sxs-lookup"><span data-stu-id="e6df3-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="e6df3-106">Com mais de 75 milhões usuários ativos diariamente, o Teams é como as pessoas estão realizando o trabalho.</span><span class="sxs-lookup"><span data-stu-id="e6df3-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Resumindo a imagem do Teams e da plataforma de alimentação da Microsoft":::

<span data-ttu-id="e6df3-108">A plataforma de alimentação da Microsoft oferece muitos recursos de integração com o Microsoft Teams em que você pode inserir relatórios do **Power bi** no espaço de trabalho do Teams, inserir aplicativos criados **usando os** **aplicativos de energia** como uma guia ou um aplicativo pessoal, disparar um fluxo **automatizado de energia** de qualquer mensagem ou usar cartões adaptáveis e adicionar o bot para interagir com o Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="e6df3-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="e6df3-109">A partir de setembro de 2020, a integração com o Microsoft Power Platform foi aprimorada para permitir que os usuários façam o seguinte, *sem precisar sair da interface do teams*:</span><span class="sxs-lookup"><span data-stu-id="e6df3-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="e6df3-110">Crie e compartilhe painéis, relatórios e aplicativos usando o **Power bi** para fazer decisões direcionadas a dados.</span><span class="sxs-lookup"><span data-stu-id="e6df3-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="e6df3-111">Crie e compartilhe aplicativos de uso baixo e de código específico usando um **Power apps** Studio, conectando-se aos seus dados corporativos armazenados na nova plataforma de dados subjacentes (Microsoft dataverso para Teams for Teams), Microsoft 365 ou em outras fontes de dados por meio de conectores.</span><span class="sxs-lookup"><span data-stu-id="e6df3-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="e6df3-112">Crie fluxos de trabalho automatizados entre seus aplicativos e serviços para sincronizar arquivos, obter notificações, coletar dados e muito mais usando a **automatização de energia**.</span><span class="sxs-lookup"><span data-stu-id="e6df3-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="e6df3-113">Crie bots usando uma interface gráfica sem código e orientada usando **os agentes virtuais de força** para criar facilmente assistentes digitais no Teams e disponibilizá-los para seus colegas de chat.</span><span class="sxs-lookup"><span data-stu-id="e6df3-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="e6df3-114">As novas funcionalidades para criar aplicativos, bots e fluxos de trabalho são apoiadas pela nova plataforma interna de dados de código baixo para Teams, [dataverso para Teams](https://go.microsoft.com/fwlink/?linkid=2143541), que fornece armazenamento de dados relacional, tipos de dados avançados, controle de empresa e implantação de solução com um único clique.</span><span class="sxs-lookup"><span data-stu-id="e6df3-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](https://go.microsoft.com/fwlink/?linkid=2143541), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="e6df3-115">O dataverso do teams é baseado no início do [Microsoft dataverso](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="e6df3-115">Dataverse for Teams is built on top of [Microsoft Dataverse](https://docs.microsoft.com/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="e6df3-116">Com o dataverso para Teams, os usuários do teams podem localizar e instalar soluções personalizadas e prontas para uso da App Store do teams que demonstram cenários comuns em todos os setores.</span><span class="sxs-lookup"><span data-stu-id="e6df3-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="e6df3-117">Você pode personalizar e estender essas soluções personalizadas para se adaptar aos requisitos e à identidade visual da sua organização.</span><span class="sxs-lookup"><span data-stu-id="e6df3-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="e6df3-118">Licenças</span><span class="sxs-lookup"><span data-stu-id="e6df3-118">Licensing</span></span>

<span data-ttu-id="e6df3-119">Os novos recursos estão disponíveis para as assinaturas Select Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e6df3-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="e6df3-120">Para obter mais informações sobre os requisitos de licenciamento para aplicativos de energia, autoautomatizar, agentes de energia virtual e dataverso para equipes, consulte [Licenciamento](https://go.microsoft.com/fwlink/?linkid=2143647).</span><span class="sxs-lookup"><span data-stu-id="e6df3-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](https://go.microsoft.com/fwlink/?linkid=2143647).</span></span>
- <span data-ttu-id="e6df3-121">Para obter mais informações sobre os requisitos de licenciamento do Power BI, consulte [requisitos](https://go.microsoft.com/fwlink/?linkid=2143490).</span><span class="sxs-lookup"><span data-stu-id="e6df3-121">For more information about licensing requirements for Power BI, see [Requirements](https://go.microsoft.com/fwlink/?linkid=2143490).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="e6df3-122">Como posso começar?</span><span class="sxs-lookup"><span data-stu-id="e6df3-122">How do I get started?</span></span>

- [<span data-ttu-id="e6df3-123">Power BI e Teams</span><span class="sxs-lookup"><span data-stu-id="e6df3-123">Power BI and Teams</span></span>](https://aka.ms/pbi-teams-docs)
- [<span data-ttu-id="e6df3-124">Aplicativos avançados e equipes</span><span class="sxs-lookup"><span data-stu-id="e6df3-124">Power Apps and Teams</span></span>](https://aka.ms/pa-teams-docs)
- [<span data-ttu-id="e6df3-125">Automatizar e equipes de energia</span><span class="sxs-lookup"><span data-stu-id="e6df3-125">Power Automate and Teams</span></span>](https://aka.ms/pauto-teams-docs)
- [<span data-ttu-id="e6df3-126">Agentes e agentes de energia virtual</span><span class="sxs-lookup"><span data-stu-id="e6df3-126">Power Virtual Agents and Teams</span></span>](https://aka.ms/pva-teams-docs)
