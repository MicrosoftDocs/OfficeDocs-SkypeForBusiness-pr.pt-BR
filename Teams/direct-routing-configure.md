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
description: Saiba como configurar o roteamento direto do sistema de telefonia da Microsoft.
ms.openlocfilehash: 9c56078a6d016967e518746e3567373404d1c486
ms.sourcegitcommit: 0289062510f0791906dab2791c5db8acb1cf849a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/20/2020
ms.locfileid: "42157869"
---
# <a name="configure-direct-routing"></a><span data-ttu-id="9e2f1-103">Configurar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="9e2f1-103">Configure Direct Routing</span></span>

<span data-ttu-id="9e2f1-104">O roteamento direto do Microsoft Phone System permite que você conecte sua infraestrutura de telefonia local ao Microsoft Teams.</span><span class="sxs-lookup"><span data-stu-id="9e2f1-104">Microsoft Phone System Direct Routing enables you to connect your on-premises telephony infrastructure to Microsoft Teams.</span></span> <span data-ttu-id="9e2f1-105">O artigo lista as etapas de alto nível necessárias para conectar um controlador de borda de sessão local (SBC) com suporte para roteamento direto e como configurar os usuários do teams para usar o roteamento direto para se conectar à rede telefônica pública comutada (PSTN).</span><span class="sxs-lookup"><span data-stu-id="9e2f1-105">The article lists the high-level steps required for connecting a supported on-premises Session Border Controller (SBC) to Direct Routing, and how to configure Teams users to use Direct Routing to connect to the Public Switched Telephone Network (PSTN).</span></span> <span data-ttu-id="9e2f1-106">Este artigo contém links para artigos associados para obter detalhes.</span><span class="sxs-lookup"><span data-stu-id="9e2f1-106">This article links to associated articles for details.</span></span>  

<span data-ttu-id="9e2f1-107">Para saber se o roteamento direto é a solução certa para a sua organização, consulte [Roteamento direto do sistema telefônico](direct-routing-landing-page.md).</span><span class="sxs-lookup"><span data-stu-id="9e2f1-107">For information about whether Direct Routing is the right solution for your organization, see [Phone System Direct Routing](direct-routing-landing-page.md).</span></span> <span data-ttu-id="9e2f1-108">Para obter informações sobre pré-requisitos e planejar sua implantação, consulte [planejar roteamento direto](direct-routing-plan.md).</span><span class="sxs-lookup"><span data-stu-id="9e2f1-108">For information about prerequisites and planning your deployment, see [Plan Direct Routing](direct-routing-plan.md).</span></span>

> [!Tip]
> <span data-ttu-id="9e2f1-109">Você também pode assistir à sessão a seguir para saber mais sobre os benefícios de roteamento direto, como planejar e como implantá-lo: [Roteamento direto no Microsoft Teams](https://aka.ms/teams-direct-routing).</span><span class="sxs-lookup"><span data-stu-id="9e2f1-109">You can also watch the following session to learn about the benefits of Direct Routing, how to plan for it, and how to deploy it: [Direct Routing in Microsoft Teams](https://aka.ms/teams-direct-routing).</span></span>

<span data-ttu-id="9e2f1-110">Para concluir as etapas explicadas neste artigo, os administradores precisam estar familiarizados com cmdlets do PowerShell.</span><span class="sxs-lookup"><span data-stu-id="9e2f1-110">To complete the steps explained in this article, administrators need some familiarity with PowerShell cmdlets.</span></span> <span data-ttu-id="9e2f1-111">Para obter mais informações sobre como usar o PowerShell, consulte [configurar seu computador para Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="9e2f1-111">For more information about using PowerShell, see [Set up your computer for Windows PowerShell](https://docs.microsoft.com/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell).</span></span> 

<span data-ttu-id="9e2f1-112">Antes de executar as etapas nestes artigos, a Microsoft recomenda que você confirme que o seu SBC já foi configurado como recomendado pelo fornecedor do SBC:</span><span class="sxs-lookup"><span data-stu-id="9e2f1-112">Before performing the steps in these articles, Microsoft recommends that you confirm that your SBC has already been configured as recommended by your SBC vendor:</span></span> 

- [<span data-ttu-id="9e2f1-113">Documentação de implantação do AudioCodes</span><span class="sxs-lookup"><span data-stu-id="9e2f1-113">AudioCodes deployment documentation</span></span>](https://www.audiocodes.com/solutions-products/products/products-for-microsoft-365/direct-routing-for-microsoft-teams)
- [<span data-ttu-id="9e2f1-114">Documentação de implantação do Oracle</span><span class="sxs-lookup"><span data-stu-id="9e2f1-114">Oracle deployment documentation</span></span>](https://www.oracle.com/industries/communications/enterprise-session-border-controller/microsoft.html)
- [<span data-ttu-id="9e2f1-115">Documentação da implantação de comunicações da faixa de opções</span><span class="sxs-lookup"><span data-stu-id="9e2f1-115">Ribbon Communications deployment documentation</span></span>](https://ribboncommunications.com/solutions/enterprise-solutions/microsoft-solutions/direct-routing-microsoft-teams-calling)
- [<span data-ttu-id="9e2f1-116">Documentação de implantação do anynode (File-Systems)</span><span class="sxs-lookup"><span data-stu-id="9e2f1-116">TE-Systems (anynode) deployment documentation</span></span>](https://www.anynode.de/anynode-and-microsoft-teams/)

<span data-ttu-id="9e2f1-117">Para obter uma lista completa do SBCs compatível, consulte [lista de controladores de borda de sessão certificados para roteamento direto](direct-routing-border-controllers.md).</span><span class="sxs-lookup"><span data-stu-id="9e2f1-117">For a complete list of supported SBCs, see [List of Session Border Controllers certified for Direct Routing](direct-routing-border-controllers.md).</span></span>

<span data-ttu-id="9e2f1-118">Para configurar o Microsoft Phone System e permitir que os usuários usem o roteamento direto, siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="9e2f1-118">To configure Microsoft Phone System and enable users to use Direct Routing, follow these steps:</span></span> 

- <span data-ttu-id="9e2f1-119">**Etapa 1.**</span><span class="sxs-lookup"><span data-stu-id="9e2f1-119">**Step 1.**</span></span> [<span data-ttu-id="9e2f1-120">Conectar o SBC com o sistema Microsoft Phone e validar a conexão</span><span class="sxs-lookup"><span data-stu-id="9e2f1-120">Connect the SBC with Microsoft Phone System and validate the connection</span></span>](direct-routing-connect-the-sbc.md)
- <span data-ttu-id="9e2f1-121">**Etapa 2.**</span><span class="sxs-lookup"><span data-stu-id="9e2f1-121">**Step 2.**</span></span> [<span data-ttu-id="9e2f1-122">Habilite os usuários para roteamento direto, voz e correio de voz</span><span class="sxs-lookup"><span data-stu-id="9e2f1-122">Enable users for Direct Routing, voice, and voicemail</span></span>](direct-routing-enable-users.md)
- <span data-ttu-id="9e2f1-123">**Etapa 3.**</span><span class="sxs-lookup"><span data-stu-id="9e2f1-123">**Step 3.**</span></span> [<span data-ttu-id="9e2f1-124">Configurar roteamento de voz</span><span class="sxs-lookup"><span data-stu-id="9e2f1-124">Configure voice routing</span></span>](direct-routing-voice-routing.md)
- <span data-ttu-id="9e2f1-125">**Etapa 4.**</span><span class="sxs-lookup"><span data-stu-id="9e2f1-125">**Step 4.**</span></span> [<span data-ttu-id="9e2f1-126">Converter números em um formato alternativo</span><span class="sxs-lookup"><span data-stu-id="9e2f1-126">Translate numbers to an alternate format</span></span>](direct-routing-translate-numbers.md) 

<span data-ttu-id="9e2f1-127">Se você estiver configurando um SBC para vários locatários, também vai querer ler [configurar um SBC para vários locatários](direct-routing-sbc-multiple-tenants.md).</span><span class="sxs-lookup"><span data-stu-id="9e2f1-127">If you are configuring an SBC for multiple tenants, you'll also want to read [Configure an SBC for multiple tenants](direct-routing-sbc-multiple-tenants.md).</span></span>


## <a name="see-also"></a><span data-ttu-id="9e2f1-128">Confira também</span><span class="sxs-lookup"><span data-stu-id="9e2f1-128">See also</span></span>

[<span data-ttu-id="9e2f1-129">Roteamento Direto do Sistema Telefônico</span><span class="sxs-lookup"><span data-stu-id="9e2f1-129">Phone System Direct Routing</span></span>](direct-routing-landing-page.md)

[<span data-ttu-id="9e2f1-130">Planejar o Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="9e2f1-130">Plan Direct Routing</span></span>](direct-routing-plan.md)

