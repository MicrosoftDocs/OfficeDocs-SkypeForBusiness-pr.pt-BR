---
title: Planejar implantações do Servidor de Borda no Skype for Business Server 2015
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 8/17/2015
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Hybrid
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumo: Planejar seu Skype para ambiente de borda de servidor do Business Server 2015. Este tópico apresenta conceitos de borda e permite que você organize-se com nossos tópicos mais aprofundados.'
ms.openlocfilehash: 828bdc52a6c4fe55294768d69c441b9c996fa9a0
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server-2015"></a><span data-ttu-id="ba288-104">Planejar implantações do Servidor de Borda no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ba288-104">Plan for Edge Server deployments in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="ba288-p102">**Resumo:** planeje o ambiente da Borda do Servidor de seu Skype for Business Server 2015. Este tópico apresenta os conceitos de Borda permite que você se organize com nossos tópicos mais detalhados.</span><span class="sxs-lookup"><span data-stu-id="ba288-p102">**Summary:** Plan for your Skype for Business Server 2015 Server Edge environment. This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="ba288-107">Quando você tem um Skype para ambiente de negócios 2015 de servidor que está funcionando bem internamente, a próxima etapa para você pode ser a apresentar um servidor de borda ou um pool de borda para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="ba288-107">When you have a Skype for Business Server 2015 environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="ba288-108">Essa função seria vital se quiser que os serviços fornecidos pelo Skype para negócios 2015 de servidor a ser usado por pessoas que estão fora da rede interna.</span><span class="sxs-lookup"><span data-stu-id="ba288-108">This role would be vital if you want the services provided by Skype for Business Server 2015 to be used by people who are outside your internal network.</span></span> <span data-ttu-id="ba288-109">Isso pode incluir:</span><span class="sxs-lookup"><span data-stu-id="ba288-109">These can potentially include:</span></span>
  
- <span data-ttu-id="ba288-110">Usuários remotos: funcionários remotos, temporariamente ou de modo contínuo.</span><span class="sxs-lookup"><span data-stu-id="ba288-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="ba288-111">Os usuários federados: Seu parceiro seus funcionários.</span><span class="sxs-lookup"><span data-stu-id="ba288-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="ba288-112">Usuários móveis.</span><span class="sxs-lookup"><span data-stu-id="ba288-112">Mobile Users.</span></span>
    
- <span data-ttu-id="ba288-113">Clientes em potencial, parceiros e até usuários anônimos que você quer convidar para reuniões e apresentações.</span><span class="sxs-lookup"><span data-stu-id="ba288-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="ba288-114">Acesso de usuário externo, que é o que os servidores de borda fornecem, permitir que tudo isso acontecerá.</span><span class="sxs-lookup"><span data-stu-id="ba288-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="ba288-115">Os usuários internos será podem aproveitar os seguintes serviços são hospedados por seu Skype para Business Server 2015 implantação:</span><span class="sxs-lookup"><span data-stu-id="ba288-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server 2015 deployment:</span></span>
  
- <span data-ttu-id="ba288-116">Mensagens instantâneas e presença para comunicação: usuários externos autorizados podem participar em conversas de mensagens instantâneas e conferências.</span><span class="sxs-lookup"><span data-stu-id="ba288-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="ba288-117">Eles obter as informações de presença de outros usuários (que também recebem suas informações de presença).</span><span class="sxs-lookup"><span data-stu-id="ba288-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="ba288-118">Você não poderá fazer conferências com vários participantes, se você estiver usando um provedor público de mensagens Instantâneas, que é estritamente-a-ponto de comunicação.</span><span class="sxs-lookup"><span data-stu-id="ba288-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="ba288-119">Mas os protocolos SIP e XMPP são aceitos.</span><span class="sxs-lookup"><span data-stu-id="ba288-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="ba288-120">Áudio/vídeo (A / V) conferência: os usuários externos autorizados podem participar de sua Skype para conferências de áudio e vídeos Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="ba288-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server 2015 audio and video conferences.</span></span>
    
- <span data-ttu-id="ba288-121">Conferência da Web: os usuários externos autorizados podem participar de sua Skype para conferências de negócios.</span><span class="sxs-lookup"><span data-stu-id="ba288-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="ba288-122">Se você quiser, você também pode habilitar a participação de usuários remotos, usuários federados e usuários anônimos.</span><span class="sxs-lookup"><span data-stu-id="ba288-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="ba288-123">Os usuários públicos de mensagens Instantâneas não podem participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="ba288-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="ba288-124">Também existem opções para permitir que esses usuários participem do compartilhamento de área de trabalho e aplicativos, e até mesmo ajam como organizadores ou apresentadores da reunião.</span><span class="sxs-lookup"><span data-stu-id="ba288-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="ba288-125">Acesso de dispositivo móvel é suportado, como está o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="ba288-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="ba288-126">Você pode convidar usuários externos para as reuniões das quais eles devem participar, mesmo usuários anônimos, se você quiser dar permissões a eles.</span><span class="sxs-lookup"><span data-stu-id="ba288-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="ba288-p108">Se isso atender às necessidades de sua organização, planejar um ambiente de Borda será de grande ajuda para a implementação. Para ler mais sobre o assunto, temos os tópicos listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="ba288-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>
  
## <a name="planning-topics"></a><span data-ttu-id="ba288-129">Tópicos de planejamento:</span><span class="sxs-lookup"><span data-stu-id="ba288-129">Planning topics:</span></span>

<span data-ttu-id="ba288-130">Os artigos de planejamento são:</span><span class="sxs-lookup"><span data-stu-id="ba288-130">The planning articles are:</span></span>
  
- [<span data-ttu-id="ba288-131">Requisitos de sistema do servidor de borda no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ba288-131">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="ba288-132">Requisitos de ambiente de servidor de borda no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ba288-132">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="ba288-133">Cenários de servidor de borda no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ba288-133">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

