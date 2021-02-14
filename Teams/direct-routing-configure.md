---
title: Configurar o Roteamento Direto
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
audience: ITPro
ms.topic: article
ms.service: msteams
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
- m365initiative-voice
- m365solution-voice
- m365solution-scenario
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar o Roteamento Direto do Sistema De Telefonia do Microsoft Phone para conectar sua infraestrutura de telefonia local ao Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 5388c93e741323d3dc9eda0fc51968b8b344d2cb
ms.sourcegitcommit: 380a96f1ed2cefb429286854f06546bdb28d7d74
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/17/2020
ms.locfileid: "49701289"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="33bee-103">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="33bee-103">Configure Direct Routing</span></span>

<span data-ttu-id="33bee-104">O Roteamento Direto do Sistema De Telefonia do Microsoft Phone permite conectar sua infraestrutura de telefonia local ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="33bee-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="33bee-105">O artigo lista as etapas de alto nível necessárias para conectar um SBC (Controlador de Borda de Sessão) local com suporte ao Roteamento Direto e como configurar os usuários do Teams para usar o Roteamento Direto para se conectar à PSTN (Rede Telefônica Pública Comuada).</span><span class="sxs-lookup"><span data-stu-id="33bee-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="33bee-106">Este artigo vincula-se aos artigos associados para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="33bee-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="33bee-107">Para saber mais sobre se o Roteamento Direto é a solução certa para sua organização, consulte [Roteamento Direto do Sistema de Telefonia.](direct-routing-landing-page.md)</span><span class="sxs-lookup"><span data-stu-id="33bee-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="33bee-108">Para obter informações sobre pré-requisitos e planejar sua implantação, consulte [Planejar Roteamento Direto.](direct-routing-plan.md)</span><span class="sxs-lookup"><span data-stu-id="33bee-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="33bee-109">Você também pode assistir à sessão a seguir para saber mais sobre os benefícios do Roteamento Direto, como planejar e como implantá-lo: Roteamento Direto [no Microsoft Teams.](https://aka.ms/teams-direct-routing)</span><span class="sxs-lookup"><span data-stu-id="33bee-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="33bee-110">Para concluir as etapas explicadas neste artigo, os administradores precisam de alguma familiaridade com cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="33bee-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="33bee-111">Para obter mais informações sobre como usar o PowerShell, consulte [Configurar seu computador para Windows PowerShell.](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="33bee-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="33bee-112">Antes de executar as etapas nestes artigos, a Microsoft recomenda que você confirme que seu SBC já foi configurado conforme recomendado pelo fornecedor SBC:</span><span class="sxs-lookup"><span data-stu-id="33bee-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="33bee-113">Documentação de implantação de AudioCodes</span><span class="sxs-lookup"><span data-stu-id="33bee-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="33bee-114">Documentação de implantação oracle</span><span class="sxs-lookup"><span data-stu-id="33bee-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="33bee-115">Documentação de implantação de Comunicações da Faixa de Opções</span><span class="sxs-lookup"><span data-stu-id="33bee-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="33bee-116">Documentação de implantação do TE-Systems (qualquernode)</span><span class="sxs-lookup"><span data-stu-id="33bee-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="33bee-117">Documentação de implantação metaswstat</span><span class="sxs-lookup"><span data-stu-id="33bee-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="33bee-118">Para ver uma lista completa de SBCs com suporte, consulte Lista de Controladores de Borda de Sessão [certificados para Roteamento Direto.](direct-routing-border-controllers.md)</span><span class="sxs-lookup"><span data-stu-id="33bee-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="33bee-119">Para configurar o Microsoft Phone System e permitir que os usuários usem o Roteamento Direto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="33bee-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="33bee-120">**Etapa 1.**</span><span class="sxs-lookup"><span data-stu-id="33bee-120">**Step 1.**</span></span> [<span data-ttu-id="33bee-121">Conectar o SBC ao Microsoft Phone System e validar a conexão</span><span class="sxs-lookup"><span data-stu-id="33bee-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="33bee-122">**Etapa 2.**</span><span class="sxs-lookup"><span data-stu-id="33bee-122">**Step 2.**</span></span> [<span data-ttu-id="33bee-123">Habilitar usuários para Roteamento Direto, voz e caixa postal</span><span class="sxs-lookup"><span data-stu-id="33bee-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="33bee-124">**Etapa 3.**</span><span class="sxs-lookup"><span data-stu-id="33bee-124">**Step 3.**</span></span> [<span data-ttu-id="33bee-125">Configurar roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="33bee-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="33bee-126">**Etapa 4.**</span><span class="sxs-lookup"><span data-stu-id="33bee-126">**Step 4.**</span></span> [<span data-ttu-id="33bee-127">Traduzir números para um formato alternativo</span><span class="sxs-lookup"><span data-stu-id="33bee-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="33bee-128">Se você estiver configurando um SBC para vários locatários, também vai querer ler Configurar um [SBC para vários locatários.](direct-routing-sbc-multiple-tenants.md)</span><span class="sxs-lookup"><span data-stu-id="33bee-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="33bee-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="33bee-129">Related topics</span></span>

[<span data-ttu-id="33bee-130">Roteamento Direto do Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="33bee-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="33bee-131">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="33bee-131">Plan Direct Routing</span></span>](direct-routing-plan.md)

