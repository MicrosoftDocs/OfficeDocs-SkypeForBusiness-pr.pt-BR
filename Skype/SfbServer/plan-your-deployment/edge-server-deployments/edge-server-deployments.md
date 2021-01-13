---
title: Planejar implantações do Servidor de Borda no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Hybrid
ms.custom: ''
ms.assetid: 9cdc3e23-3f6a-4e4d-9e04-f038596b6700
description: 'Resumo: planeje seu ambiente de Borda do Skype for Business Server. Este tópico apresenta os conceitos do Edge e permite que você se organize com nossos tópicos mais aprofundados.'
ms.openlocfilehash: 277e344448f5229d15addf965695f19ec2884649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813801"
---
# <a name="plan-for-edge-server-deployments-in-skype-for-business-server"></a><span data-ttu-id="089c2-104">Planejar implantações do Servidor de Borda no Skype for Business Server</span><span class="sxs-lookup"><span data-stu-id="089c2-104">Plan for Edge Server deployments in Skype for Business Server</span></span>
 
<span data-ttu-id="089c2-105">**Resumo:** Planeje seu ambiente de Borda do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="089c2-105">**Summary:** Plan for your Skype for Business Server Edge environment.</span></span> <span data-ttu-id="089c2-106">Este tópico apresenta os conceitos do Edge e permite que você se organize com nossos tópicos mais aprofundados.</span><span class="sxs-lookup"><span data-stu-id="089c2-106">This topic introduces you to Edge concepts and lets you get organized with our more in-depth topics.</span></span>
  
<span data-ttu-id="089c2-107">Quando você tem um ambiente do Skype for Business Server que está funcionando bem internamente, a próxima etapa para você pode ser introduzir um Servidor de Borda ou um pool de Borda para o ambiente.</span><span class="sxs-lookup"><span data-stu-id="089c2-107">When you have a Skype for Business Server environment that's working well internally, the next step for you might be to introduce an Edge Server or an Edge pool to the environment.</span></span> <span data-ttu-id="089c2-108">Essa função será vital se você quiser que os serviços fornecidos pelo Skype for Business Server sejam usados por pessoas fora da rede interna.</span><span class="sxs-lookup"><span data-stu-id="089c2-108">This role would be vital if you want the services provided by Skype for Business Server to be used by people who are outside your internal network.</span></span> <span data-ttu-id="089c2-109">Eles podem incluir:</span><span class="sxs-lookup"><span data-stu-id="089c2-109">These can potentially include:</span></span>
  
- <span data-ttu-id="089c2-110">Usuários remotos: funcionários que estão fora do local, temporariamente ou de forma contínua.</span><span class="sxs-lookup"><span data-stu-id="089c2-110">Remote Users: Employees who are offsite, either temporarily or in an ongoing way.</span></span>
    
- <span data-ttu-id="089c2-111">Usuários federados: funcionários de suas organizações parceiras.</span><span class="sxs-lookup"><span data-stu-id="089c2-111">Federated Users: Your partner organizations' employees.</span></span>
    
- <span data-ttu-id="089c2-112">Usuários móveis.</span><span class="sxs-lookup"><span data-stu-id="089c2-112">Mobile Users.</span></span>
    
- <span data-ttu-id="089c2-113">Clientes em potencial, parceiros e até mesmo usuários anônimos que você deseja convidar para reuniões e apresentações.</span><span class="sxs-lookup"><span data-stu-id="089c2-113">Potential customers, partners and even anonymous users you want to invite to meetings and presentations.</span></span>
    
<span data-ttu-id="089c2-114">O Acesso de Usuário Externo, que é o que os Servidores de Borda fornecem, permitem que tudo isso aconteça.</span><span class="sxs-lookup"><span data-stu-id="089c2-114">External User Access, which is what Edge Servers provide, allow all this to happen.</span></span> <span data-ttu-id="089c2-115">Seus usuários internos poderão aproveitar os seguintes serviços hospedados pela implantação do Skype for Business Server:</span><span class="sxs-lookup"><span data-stu-id="089c2-115">Your internal users will be able to enjoy the following services that are hosted by your Skype for Business Server deployment:</span></span>
  
- <span data-ttu-id="089c2-116">IM e presença para comunicação: usuários externos autorizados podem participar de conversas e conferências de IM.</span><span class="sxs-lookup"><span data-stu-id="089c2-116">IM and presence for communication: Authorized external users can join in IM conversations and conferences.</span></span> <span data-ttu-id="089c2-117">Eles podem obter informações de presença para outros usuários (que também receberão suas informações de presença).</span><span class="sxs-lookup"><span data-stu-id="089c2-117">They can get presence information for other users (who get their presence info too).</span></span> <span data-ttu-id="089c2-118">Você não poderá fazer conferências com vários participantes se estiver usando um provedor de IM público, isso é estritamente uma comunicação ponto a ponto.</span><span class="sxs-lookup"><span data-stu-id="089c2-118">You won't be able to do multiparty conferences if you're using a public IM provider, that's strictly peer-to-peer communication.</span></span> <span data-ttu-id="089c2-119">Mas os protocolos SIP e XMPP são suportados.</span><span class="sxs-lookup"><span data-stu-id="089c2-119">But both SIP and XMPP protocols are supported.</span></span>
    
- <span data-ttu-id="089c2-120">Conferência de áudio/vídeo (A/V: usuários externos autorizados podem participar de suas conferências de áudio e vídeo do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="089c2-120">Audio/video (A/V) conferencing: Authorized external users can participate in your Skype for Business Server audio and video conferences.</span></span>
    
- <span data-ttu-id="089c2-121">Webconferência: seus usuários externos autorizados podem participar de suas conferências do Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="089c2-121">Web conferencing: Your authorized external users can participate in your Skype for Business conferences.</span></span> <span data-ttu-id="089c2-122">Você também pode habilitar a participação de usuários remotos, federados e anônimos, se quiser.</span><span class="sxs-lookup"><span data-stu-id="089c2-122">You can also enable participation for remote users, federated users, and anonymous users if you'd like.</span></span> <span data-ttu-id="089c2-123">Os usuários públicos de IM não podem participar de conferências.</span><span class="sxs-lookup"><span data-stu-id="089c2-123">Public IM users can't participate in conferences.</span></span> <span data-ttu-id="089c2-124">Também há opções para permitir que esses usuários participem do compartilhamento de aplicativos e da área de trabalho e até mesmo atuem como organizadores ou apresentadores da reunião.</span><span class="sxs-lookup"><span data-stu-id="089c2-124">There are also options to let these users participate in application and desktop sharing, and even act as meeting organizers or presenters.</span></span>
    
<span data-ttu-id="089c2-125">O acesso a dispositivos móveis é suportado, assim como o Enterprise Voice.</span><span class="sxs-lookup"><span data-stu-id="089c2-125">Mobile device access is supported, as is Enterprise Voice.</span></span> <span data-ttu-id="089c2-126">Você pode convidar usuários externos para as reuniões que deseja que eles participem, mesmo usuários anônimos, se quiser dar permissões a eles.</span><span class="sxs-lookup"><span data-stu-id="089c2-126">You can invite external users to those meetings you wish them to attend, even anonymous users, if you want to give permissions to them.</span></span>
  
<span data-ttu-id="089c2-127">Se isso parece algo que sua organização precisa, planejar um ambiente de Borda será de grande ajuda para implantá-lo.</span><span class="sxs-lookup"><span data-stu-id="089c2-127">If this sounds like something your organization needs, then planning for an Edge environment's going to be a big help in deploying it.</span></span> <span data-ttu-id="089c2-128">Para leitura posterior, temos os tópicos listados abaixo.</span><span class="sxs-lookup"><span data-stu-id="089c2-128">For further reading, we have the topics listed below.</span></span>

> [!NOTE]
> <span data-ttu-id="089c2-129">Gateways XMPP e proxies estão disponíveis no Skype for Business Server 2015, mas não têm mais suporte no Skype for Business Server 2019.</span><span class="sxs-lookup"><span data-stu-id="089c2-129">XMPP Gateways and proxies are available in Skype for Business Server 2015 but are no longer supported in Skype for Business Server 2019.</span></span> <span data-ttu-id="089c2-130">Consulte [Migrando federação XMPP](../../../SfBServer2019/migration/migrating-xmpp-federation.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="089c2-130">See [Migrating XMPP federation](../../../SfBServer2019/migration/migrating-xmpp-federation.md) for more information.</span></span> 
  
## <a name="planning-topics"></a><span data-ttu-id="089c2-131">Tópicos de planejamento:</span><span class="sxs-lookup"><span data-stu-id="089c2-131">Planning topics:</span></span>

<span data-ttu-id="089c2-132">Os artigos de planejamento são:</span><span class="sxs-lookup"><span data-stu-id="089c2-132">The planning articles are:</span></span>
  
- [<span data-ttu-id="089c2-133">Requisitos de sistema do Servidor de Borda no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="089c2-133">Edge Server system requirements in Skype for Business Server 2015</span></span>](system-requirements.md)
    
- [<span data-ttu-id="089c2-134">Requisitos ambientais do Servidor de Borda no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="089c2-134">Edge Server environmental requirements in Skype for Business Server 2015</span></span>](edge-environmental-requirements.md)
    
- [<span data-ttu-id="089c2-135">Cenários do Servidor de Borda no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="089c2-135">Edge Server scenarios in Skype for Business Server 2015</span></span>](scenarios.md)
    

