---
title: Teams integração com a Plataforma Microsoft Power
author: cichur
ms.author: v-cichur
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
description: Saiba mais Teams integração com ferramentas do Microsoft Power Platform, incluindo Power BI, aplicativos do Power, Power automate e Power Virtual Agents.
ms.openlocfilehash: c6442cd654dd8da6e26de048d50b7c80ef95cf26
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51111037"
---
# <a name="teams-integration-with-microsoft-power-platform"></a><span data-ttu-id="56554-103">Teams integração com a Plataforma Microsoft Power</span><span class="sxs-lookup"><span data-stu-id="56554-103">Teams integration with Microsoft Power Platform</span></span>

<span data-ttu-id="56554-104">A Plataforma do Microsoft Power ajuda os usuários a acelerar seu desenvolvimento com ferramentas de baixo código **para** analisar dados usando Power BI, criar aplicativos personalizados usando **Power Apps,** automatizar processos usando **Power Automate** e criar bots inteligentes usando Power Virtual Agents **mais** rapidamente do que nunca.</span><span class="sxs-lookup"><span data-stu-id="56554-104">Microsoft Power Platform helps users accelerate their development with low-code tools to analyze data using **Power BI**, build custom apps using **Power Apps**, automate processes using **Power Automate**, and create intelligent bots using **Power Virtual Agents** more quickly than ever.</span></span> <span data-ttu-id="56554-105">Com a mudança para o trabalho remoto e híbrido, a Microsoft Teams permitiu que as pessoas em todo o mundo continuasse a criar, colaborar e se comunicar.</span><span class="sxs-lookup"><span data-stu-id="56554-105">With the shift to remote and hybrid work, Microsoft Teams has enabled people around the world to continue to create, collaborate, and communicate.</span></span> <span data-ttu-id="56554-106">Com mais de 75 milhões de usuários ativos diários, Teams é como as pessoas estão trabalhando.</span><span class="sxs-lookup"><span data-stu-id="56554-106">With more than 75 million daily active users, Teams is how people are getting work done.</span></span>

:::image type="content" source="media/teams-power-platform-integration.png" alt-text="Resumo de imagens Teams e Plataforma do Microsoft Power":::

<span data-ttu-id="56554-108">O Microsoft Power Platform fornece muitos recursos de integração com o Teams onde você pode inserir relatórios do **Power BI** no espaço de trabalho do Teams, incorporar aplicativos criados usando **o Power Apps** como uma guia ou aplicativo pessoal, disparar um fluxo **Power Automate de** qualquer mensagem ou usar cartões adaptáveis e adicionar seu bot criado usando o **Power Virtual Agents** para Teams para outros membros da sua organização interagirem.</span><span class="sxs-lookup"><span data-stu-id="56554-108">Microsoft Power Platform provides many integration capabilities with Teams where you can embed **Power BI** reports in the Teams workspace, embed apps created using **Power Apps** as a tab or personal app, trigger a **Power Automate** flow from any message or use adaptive cards, and add your bot created using **Power Virtual Agents** to Teams for other members of your organization to interact with.</span></span>

<span data-ttu-id="56554-109">A partir de setembro de 2020, a integração com a Plataforma Do Microsoft Power melhorou para permitir que os usuários façaem o seguinte sem sair da *interface Teams :*</span><span class="sxs-lookup"><span data-stu-id="56554-109">Starting September 2020, integration with Microsoft Power Platform has improved to let users do the following *without ever leaving the Teams interface*:</span></span>

- <span data-ttu-id="56554-110">Crie e compartilhe painéis, relatórios e aplicativos usando Power BI **para** tomar decisões orientadas por dados.</span><span class="sxs-lookup"><span data-stu-id="56554-110">Create and share dashboards, reports, and apps using **Power BI** to make data-driven decisions.</span></span>
- <span data-ttu-id="56554-111">Crie e compartilhe aplicativos de baixo código e de finalidade usando um estúdio Power Apps integrado conectando-se **aos** dados de negócios armazenados na nova plataforma de dados subjacente (Microsoft Dataverse para Teams), Microsoft 365 ou em outras fontes de dados por meio de conectores.</span><span class="sxs-lookup"><span data-stu-id="56554-111">Create and share low-code, purpose-built apps using an integrated **Power Apps** studio by connecting to your business data stored either in the new underlying data platform (Microsoft Dataverse for Teams), Microsoft 365, or in other data sources through connectors.</span></span>
- <span data-ttu-id="56554-112">Crie fluxos de trabalho automatizados entre seus aplicativos e serviços para sincronizar arquivos, receber notificações, coletar dados e muito mais usando Power Automate **.**</span><span class="sxs-lookup"><span data-stu-id="56554-112">Create automated workflows between your apps and services to synchronize files, get notifications, collect data, and more using **Power Automate**.</span></span>
- <span data-ttu-id="56554-113">Crie bots usando uma interface gráfica sem código guiada usando o **Power Virtual Agents** para criar facilmente assistentes digitais no Teams e torná-los disponíveis para seus colegas conversarem.</span><span class="sxs-lookup"><span data-stu-id="56554-113">Build bots using a guided, no-code graphical interface using **Power Virtual Agents** to easily create digital assistants within Teams and make them available to your colleagues to chat with.</span></span>

<span data-ttu-id="56554-114">Os novos recursos para criar aplicativos, bots e fluxos de trabalho são respaldados pela nova plataforma de dados integrada e de baixo código para Teams, [Dataverse para Teams](/powerapps/teams/overview-data-platform), que fornece armazenamento de dados relacionais, tipos de dados avançados, governança de nível empresarial e implantação de solução de um clique.</span><span class="sxs-lookup"><span data-stu-id="56554-114">The new capabilities to create apps, bots, and workflows are backed by the new built-in, low-code data platform for Teams, [Dataverse for Teams](/powerapps/teams/overview-data-platform), which provides relational data storage, rich data types, enterprise grade governance, and one-click solution deployment.</span></span> <span data-ttu-id="56554-115">O dataverse para Teams é criado sobre o [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span><span class="sxs-lookup"><span data-stu-id="56554-115">Dataverse for Teams is built on top of [Microsoft Dataverse](/powerapps/maker/common-data-service/data-platform-intro).</span></span> <span data-ttu-id="56554-116">Com o Dataverse para Teams, Teams os usuários podem encontrar e instalar soluções personalizadas e prontas para uso no armazenamento de aplicativos Teams que mostram cenários comuns em todos os setores.</span><span class="sxs-lookup"><span data-stu-id="56554-116">With Dataverse for Teams, Teams users can find and install custom, ready-to-use solutions from the Teams app store that showcase common scenarios across industries.</span></span> <span data-ttu-id="56554-117">Você pode personalizar e estender essas soluções personalizadas para se adaptar à identidade visual e aos requisitos da sua organização.</span><span class="sxs-lookup"><span data-stu-id="56554-117">You can customize and extend these custom solutions to adapt to your organization's branding and requirements.</span></span>

## <a name="licensing"></a><span data-ttu-id="56554-118">Licenciamento</span><span class="sxs-lookup"><span data-stu-id="56554-118">Licensing</span></span>

<span data-ttu-id="56554-119">Os novos recursos estão disponíveis para a seleção Microsoft 365 assinaturas.</span><span class="sxs-lookup"><span data-stu-id="56554-119">The new capabilities are available to the select Microsoft 365 subscriptions.</span></span>

- <span data-ttu-id="56554-120">Para obter mais informações sobre os requisitos de licenciamento para Power Apps, Power Automate, Power Virtual Agents e Dataverse para Teams, consulte [Licensing](/power-platform/admin/about-teams-environment).</span><span class="sxs-lookup"><span data-stu-id="56554-120">For more information about licensing requirements for Power Apps, Power Automate, Power Virtual Agents, and Dataverse for Teams, see [Licensing](/power-platform/admin/about-teams-environment).</span></span>
- <span data-ttu-id="56554-121">Para obter mais informações sobre os requisitos de licenciamento para Power BI, consulte [Requirements](/power-bi/collaborate-share/service-collaborate-microsoft-teams).</span><span class="sxs-lookup"><span data-stu-id="56554-121">For more information about licensing requirements for Power BI, see [Requirements](/power-bi/collaborate-share/service-collaborate-microsoft-teams).</span></span>
 
## <a name="how-do-i-get-started"></a><span data-ttu-id="56554-122">Como começar?</span><span class="sxs-lookup"><span data-stu-id="56554-122">How do I get started?</span></span>

- [<span data-ttu-id="56554-123">Power BI e Teams</span><span class="sxs-lookup"><span data-stu-id="56554-123">Power BI and Teams</span></span>](/power-bi/collaborate-share/service-collaborate-microsoft-teams)
- [<span data-ttu-id="56554-124">Power Apps e Teams</span><span class="sxs-lookup"><span data-stu-id="56554-124">Power Apps and Teams</span></span>](/powerapps/teams/overview)
- [<span data-ttu-id="56554-125">Power Automate e Teams</span><span class="sxs-lookup"><span data-stu-id="56554-125">Power Automate and Teams</span></span>](/power-automate/teams/overview)
- [<span data-ttu-id="56554-126">Power Virtual Agents e Teams</span><span class="sxs-lookup"><span data-stu-id="56554-126">Power Virtual Agents and Teams</span></span>](/power-virtual-agents/teams/fundamentals-what-is-power-virtual-agents-teams)