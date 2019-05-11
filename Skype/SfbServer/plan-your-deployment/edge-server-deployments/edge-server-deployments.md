---
title: Planejar para implantações de servidor de borda no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumo: Planejar seu Skype para ambiente de servidor de borda de negócios. Este tópico apresenta conceitos de borda e permite que você organize-se com nossos tópicos mais aprofundados.'
ms.openlocfilehash: 4c4348d0d3aa56aa82b8ea8930176d9d135a64f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33885072"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="2ef68-104">Planejar para implantações de servidor de borda no Skype para Business Server</span><span class="sxs-lookup"><span data-stu-id="2ef68-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="2ef68-105">**Resumo:** Planeje sua Skype para ambiente de servidor de borda de negócios.</span><span class="sxs-lookup"><span data-stu-id="2ef68-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="2ef68-106">Este tópico apresenta conceitos de borda e permite que você organize-se com nossos tópicos mais aprofundados.</span><span class="sxs-lookup"><span data-stu-id="2ef68-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="2ef68-107">Quando você tem um Skype corporativos para ambiente de servidor que está funcionando bem internamente, a próxima etapa para você pode ser a apresentar um servidor de borda ou um pool de borda para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="2ef68-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="2ef68-108">Essa função seria vital se quiser que os serviços fornecidos pelo Skype para Business Server a ser usado por pessoas que estão fora da rede interna.</span><span class="sxs-lookup"><span data-stu-id="2ef68-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="2ef68-109">Isso pode incluir:</span><span class="sxs-lookup"><span data-stu-id="2ef68-109">These can potentially include:</span></span>
  
- <span data-ttu-id="2ef68-110">Usuários remotos: funcionários remotos, temporariamente ou de modo contínuo.</span><span class="sxs-lookup"><span data-stu-id="2ef68-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="2ef68-111">Os usuários federados: Seu parceiro seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="2ef68-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="2ef68-112">Usuários móveis.</span><span class="sxs-lookup"><span data-stu-id="2ef68-112">Mobile Users.</span></span>
    
- <span data-ttu-id="2ef68-113">Clientes em potencial, parceiros e até usuários anônimos que você quer convidar para reuniões e apresentações.</span><span class="sxs-lookup"><span data-stu-id="2ef68-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="2ef68-114">Acesso de usuário externo, que é o que os servidores de borda fornecem, permitir que tudo isso acontecerá.</span><span class="sxs-lookup"><span data-stu-id="2ef68-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="2ef68-115">Os usuários internos será podem aproveitar os seguintes serviços são hospedados por seu Skype para implantação de servidor de negócios:</span><span class="sxs-lookup"><span data-stu-id="2ef68-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="2ef68-116">Mensagens instantâneas e presença para comunicação: usuários externos autorizados podem participar em conversas de mensagens instantâneas e conferências.</span><span class="sxs-lookup"><span data-stu-id="2ef68-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="2ef68-117">Eles obter as informações de presença de outros usuários (que também recebem suas informações de presença).</span><span class="sxs-lookup"><span data-stu-id="2ef68-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="2ef68-118">Você não poderá fazer conferências com vários participantes, se você estiver usando um provedor público de mensagens Instantâneas, que é estritamente-a-ponto de comunicação.</span><span class="sxs-lookup"><span data-stu-id="2ef68-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="2ef68-119">Mas os protocolos SIP e XMPP são aceitos.</span><span class="sxs-lookup"><span data-stu-id="2ef68-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="2ef68-120">Áudio/vídeo (A / V) conferência: os usuários externos autorizados podem participar de sua Skype para conferências de áudio e vídeos Business Server.</span><span class="sxs-lookup"><span data-stu-id="2ef68-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="2ef68-121">Conferência da Web: os usuários externos autorizados podem participar de sua Skype para conferências de negócios.</span><span class="sxs-lookup"><span data-stu-id="2ef68-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="2ef68-122">Se você quiser, você também pode habilitar a participação de usuários remotos, usuários federados e usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="2ef68-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="2ef68-123">Os usuários públicos de mensagens Instantâneas não podem participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="2ef68-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="2ef68-124">Também existem opções para permitir que esses usuários participem do compartilhamento de área de trabalho e aplicativos, e até mesmo ajam como organizadores ou apresentadores da reunião.</span><span class="sxs-lookup"><span data-stu-id="2ef68-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="2ef68-125">Acesso de dispositivo móvel é suportado, como está o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="2ef68-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="2ef68-126">Você pode convidar usuários externos para as reuniões das quais eles devem participar, mesmo usuários anônimos, se você quiser dar permissões a eles.</span><span class="sxs-lookup"><span data-stu-id="2ef68-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="2ef68-p108">Se isso atender às necessidades de sua organização, planejar um ambiente de Borda será de grande ajuda para a implementação. Para ler mais sobre o assunto, temos os tópicos listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="2ef68-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="2ef68-129">Gateways de XMPP e proxies estão disponíveis no Skype para Business Server 2015, mas não são mais suportados no Skype para Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="2ef68-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="2ef68-130">Consulte a [federação XMPP migrando](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2ef68-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="2ef68-131">Tópicos de planejamento:</span><span class="sxs-lookup"><span data-stu-id="2ef68-131">Planning topics:</span></span>

<span data-ttu-id="2ef68-132">Os artigos de planejamento são:</span><span class="sxs-lookup"><span data-stu-id="2ef68-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="2ef68-133">Requisitos de sistema do Servidor de Borda no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2ef68-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="2ef68-134">Requisitos de ambiente do Servidor de Borda no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2ef68-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="2ef68-135">Cenários do Servidor de Borda no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2ef68-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

