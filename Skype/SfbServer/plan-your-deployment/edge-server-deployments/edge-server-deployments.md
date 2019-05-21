---
title: Plano para implantações do servidor de borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumo: planeje o ambiente do Skype for Business Server Edge. Este tópico apresenta os conceitos de borda e permite que você se organize com nossos tópicos mais detalhados.'
ms.openlocfilehash: 536ab82ec6845c55a0ee067ad8c1a4f5d9b9e153
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34277157"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="dbba9-104">Plano para implantações do servidor de borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="dbba9-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="dbba9-105">**Resumo:** Planeje o ambiente do Skype for Business Server Edge.</span><span class="sxs-lookup"><span data-stu-id="dbba9-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="dbba9-106">Este tópico apresenta os conceitos de borda e permite que você se organize com nossos tópicos mais detalhados.</span><span class="sxs-lookup"><span data-stu-id="dbba9-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="dbba9-107">Quando você tem um ambiente do Skype for Business Server que está funcionando bem internamente, a próxima etapa para você pode ser apresentar um servidor de borda ou um pool de bordas para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="dbba9-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="dbba9-108">Essa função seria vital se você quiser que os serviços fornecidos pelo Skype for Business Server sejam usados por pessoas que estão fora da sua rede interna.</span><span class="sxs-lookup"><span data-stu-id="dbba9-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="dbba9-109">Isso pode incluir:</span><span class="sxs-lookup"><span data-stu-id="dbba9-109">These can potentially include:</span></span>
  
- <span data-ttu-id="dbba9-110">Usuários remotos: funcionários remotos, temporariamente ou de modo contínuo.</span><span class="sxs-lookup"><span data-stu-id="dbba9-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="dbba9-111">Usuários federados: os funcionários de sua organização parceira.</span><span class="sxs-lookup"><span data-stu-id="dbba9-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="dbba9-112">Usuários móveis.</span><span class="sxs-lookup"><span data-stu-id="dbba9-112">Mobile Users.</span></span>
    
- <span data-ttu-id="dbba9-113">Clientes em potencial, parceiros e até usuários anônimos que você quer convidar para reuniões e apresentações.</span><span class="sxs-lookup"><span data-stu-id="dbba9-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="dbba9-114">O acesso de usuários externos, que é o servidor de borda fornecido, permite que tudo isso aconteça.</span><span class="sxs-lookup"><span data-stu-id="dbba9-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="dbba9-115">Seus usuários internos poderão aproveitar os seguintes serviços hospedados pela implantação do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="dbba9-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="dbba9-116">Mensagens instantâneas e presença para comunicação: usuários externos autorizados podem participar em conversas de mensagens instantâneas e conferências.</span><span class="sxs-lookup"><span data-stu-id="dbba9-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="dbba9-117">Eles obter as informações de presença de outros usuários (que também recebem suas informações de presença).</span><span class="sxs-lookup"><span data-stu-id="dbba9-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="dbba9-118">Você não poderá fazer conferências com vários participantes se estiver usando um provedor de mensagens de chat público, que é estritamente de comunicação ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="dbba9-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="dbba9-119">Mas os protocolos SIP e XMPP são aceitos.</span><span class="sxs-lookup"><span data-stu-id="dbba9-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="dbba9-120">Conferência de áudio/vídeo (A/V): os usuários externos autorizados podem participar de conferências de áudio e vídeo do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="dbba9-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="dbba9-121">Webconferência: seus usuários externos autorizados podem participar de conferências do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="dbba9-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="dbba9-122">Você também pode habilitar a participação para usuários remotos, usuários federados e usuários anônimos, se quiser.</span><span class="sxs-lookup"><span data-stu-id="dbba9-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="dbba9-123">Os usuários de mensagens de chat públicas não podem participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="dbba9-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="dbba9-124">Também existem opções para permitir que esses usuários participem do compartilhamento de área de trabalho e aplicativos, e até mesmo ajam como organizadores ou apresentadores da reunião.</span><span class="sxs-lookup"><span data-stu-id="dbba9-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="dbba9-125">O acesso ao dispositivo móvel tem suporte, como o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="dbba9-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="dbba9-126">Você pode convidar usuários externos para as reuniões das quais eles devem participar, mesmo usuários anônimos, se você quiser dar permissões a eles.</span><span class="sxs-lookup"><span data-stu-id="dbba9-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="dbba9-p108">Se isso atender às necessidades de sua organização, planejar um ambiente de Borda será de grande ajuda para a implementação. Para ler mais sobre o assunto, temos os tópicos listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="dbba9-p108">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it. For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="dbba9-129">Os gateways e proxies XMPP estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="dbba9-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="dbba9-130">Consulte [migrando a Federação do XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="dbba9-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="dbba9-131">Tópicos de planejamento:</span><span class="sxs-lookup"><span data-stu-id="dbba9-131">Planning topics:</span></span>

<span data-ttu-id="dbba9-132">Os artigos de planejamento são:</span><span class="sxs-lookup"><span data-stu-id="dbba9-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="dbba9-133">Requisitos de sistema do Servidor de Borda no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dbba9-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="dbba9-134">Requisitos de ambiente do Servidor de Borda no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dbba9-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="dbba9-135">Cenários do Servidor de Borda no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dbba9-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

