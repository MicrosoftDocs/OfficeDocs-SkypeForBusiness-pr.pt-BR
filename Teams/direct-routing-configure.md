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
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
description: Saiba como configurar o roteamento direto do sistema de telefone da Microsoft para conectar sua infraestrutura de telefonia local ao Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f12eb67fd63a3d1bbed3ddcd0c4fadce16529083
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43904823"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="0ddae-103">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="0ddae-103">Configure Direct Routing</span></span>

<span data-ttu-id="0ddae-104">O roteamento direto do Microsoft Phone System permite que você conecte sua infraestrutura de telefonia local ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="0ddae-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="0ddae-105">O artigo lista as etapas de alto nível necessárias para conectar um controlador de borda de sessão local (SBC) com suporte para roteamento direto e como configurar os usuários do teams para usar o roteamento direto para se conectar à rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="0ddae-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="0ddae-106">Este artigo contém links para artigos associados para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="0ddae-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="0ddae-107">Para saber se o roteamento direto é a solução certa para a sua organização, consulte [Roteamento direto do sistema telefônico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="0ddae-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="0ddae-108">Para obter informações sobre pré-requisitos e planejar sua implantação, consulte [planejar roteamento direto](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="0ddae-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="0ddae-109">Você também pode assistir à sessão a seguir para saber mais sobre os benefícios de roteamento direto, como planejar e como implantá-lo: [Roteamento direto no Microsoft Teams](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="0ddae-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="0ddae-110">Para concluir as etapas explicadas neste artigo, os administradores precisam estar familiarizados com cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="0ddae-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="0ddae-111">Para obter mais informações sobre como usar o PowerShell, consulte [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="0ddae-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="0ddae-112">Antes de executar as etapas nestes artigos, a Microsoft recomenda que você confirme que o seu SBC já foi configurado como recomendado pelo fornecedor do SBC:</span><span class="sxs-lookup"><span data-stu-id="0ddae-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="0ddae-113">Documentação de implantação do AudioCodes</span><span class="sxs-lookup"><span data-stu-id="0ddae-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="0ddae-114">Documentação de implantação do Oracle</span><span class="sxs-lookup"><span data-stu-id="0ddae-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="0ddae-115">Documentação da implantação de comunicações da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="0ddae-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="0ddae-116">Documentação de implantação do anynode (File-Systems)</span><span class="sxs-lookup"><span data-stu-id="0ddae-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)
- [<span data-ttu-id="0ddae-117">Documentação da implantação do metaswitch</span><span class="sxs-lookup"><span data-stu-id="0ddae-117">Metaswitch deployment documentation</span></span>](https://www.metaswitch.com/products/core-network/perimeta-sbc)

<span data-ttu-id="0ddae-118">Para obter uma lista completa do SBCs compatível, consulte [lista de controladores de borda de sessão certificados para roteamento direto](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="0ddae-118">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="0ddae-119">Para configurar o Microsoft Phone System e permitir que os usuários usem o roteamento direto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="0ddae-119">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="0ddae-120">**Etapa 1.**</span><span class="sxs-lookup"><span data-stu-id="0ddae-120">**Step 1.**</span></span> [<span data-ttu-id="0ddae-121">Conectar o SBC com o sistema Microsoft Phone e validar a conexão</span><span class="sxs-lookup"><span data-stu-id="0ddae-121">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="0ddae-122">**Etapa 2.**</span><span class="sxs-lookup"><span data-stu-id="0ddae-122">**Step 2.**</span></span> [<span data-ttu-id="0ddae-123">Habilite os usuários para roteamento direto, voz e correio de voz</span><span class="sxs-lookup"><span data-stu-id="0ddae-123">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="0ddae-124">**Etapa 3.**</span><span class="sxs-lookup"><span data-stu-id="0ddae-124">**Step 3.**</span></span> [<span data-ttu-id="0ddae-125">Configurar roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="0ddae-125">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="0ddae-126">**Etapa 4.**</span><span class="sxs-lookup"><span data-stu-id="0ddae-126">**Step 4.**</span></span> [<span data-ttu-id="0ddae-127">Converter números em um formato alternativo</span><span class="sxs-lookup"><span data-stu-id="0ddae-127">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="0ddae-128">Se você estiver configurando um SBC para vários locatários, também vai querer ler [configurar um SBC para vários locatários](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="0ddae-128">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="related-topics"></a><span data-ttu-id="0ddae-129">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="0ddae-129">Related topics</span></span>

[<span data-ttu-id="0ddae-130">Roteamento Direto do Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="0ddae-130">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="0ddae-131">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="0ddae-131">Plan Direct Routing</span></span>](direct-routing-plan.md)

