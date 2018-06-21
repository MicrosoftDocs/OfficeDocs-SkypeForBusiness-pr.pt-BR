---
title: Adicionar servidor
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Para adicionar um novo servidor a um pool existente de servidores, na qual o pool é um dos seguintes:'
ms.openlocfilehash: 4972815a8e390896f40809f2604bf74b75c8500f
ms.sourcegitcommit: 08cf97296fb9ba6fbc4d68c3e380c8f37e86dd02
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/21/2018
ms.locfileid: "19988744"
---
# <a name="add-server"></a><span data-ttu-id="bdafa-103">Adicionar servidor</span><span class="sxs-lookup"><span data-stu-id="bdafa-103">Add Server</span></span>
 
<span data-ttu-id="bdafa-104">Para adicionar um novo servidor a um pool existente de servidores, na qual o pool é um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="bdafa-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="bdafa-105">Servidor de Front-End do Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="bdafa-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="bdafa-106">Servidor de diretor</span><span class="sxs-lookup"><span data-stu-id="bdafa-106">Director server</span></span>
    
- <span data-ttu-id="bdafa-107">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="bdafa-107">Mediation Server</span></span>
    
- <span data-ttu-id="bdafa-108">Servidor de conferência de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="bdafa-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="bdafa-109">Servidor de aplicativos confiáveis</span><span class="sxs-lookup"><span data-stu-id="bdafa-109">Trusted Application server</span></span>
    
<span data-ttu-id="bdafa-110">Cada um dos novos servidores de pool tem requisitos diferentes.</span><span class="sxs-lookup"><span data-stu-id="bdafa-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="bdafa-111">Nas seções a seguir, localize o tipo de servidor que você está adicionando ao pool existente e forneça as informações solicitadas como definido para cada tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="bdafa-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="bdafa-112">Você fornecer as informações solicitadas para definir o novo servidor do pool.</span><span class="sxs-lookup"><span data-stu-id="bdafa-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="bdafa-113">**Servidor de Front-End do Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="bdafa-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="bdafa-114">Nome domínio totalmente qualificado (FQDN) do novo servidor como definido no sistema de nome de domínio (DNS).</span><span class="sxs-lookup"><span data-stu-id="bdafa-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="bdafa-115">Selecione **usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador que pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="bdafa-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="bdafa-116">Como alternativa, você pode selecionar **limitar o uso do serviço aos endereços IP selecionados** e digite um endereço específico no novo servidor.</span><span class="sxs-lookup"><span data-stu-id="bdafa-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="bdafa-117">O endereço IP inserido é o único endereço IP qual responderá para os serviços hospedados.</span><span class="sxs-lookup"><span data-stu-id="bdafa-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="bdafa-118">Defina um **endereço IP PSTN** quando um servidor de mediação é colocado no servidor Front-End.</span><span class="sxs-lookup"><span data-stu-id="bdafa-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="bdafa-119">Selecione **Habilitar IPv6** para habilitar o IPv6 para esse servidor.</span><span class="sxs-lookup"><span data-stu-id="bdafa-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
 <span data-ttu-id="bdafa-120">**Servidor de diretor**</span><span class="sxs-lookup"><span data-stu-id="bdafa-120">**Director server**</span></span>
  
- <span data-ttu-id="bdafa-121">O FQDN do novo servidor como definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="bdafa-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="bdafa-122">Selecione **usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador será usado.</span><span class="sxs-lookup"><span data-stu-id="bdafa-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="bdafa-123">Como alternativa, você pode selecionar **limitar o uso do serviço aos endereços IP selecionados** e insira um endereço IP específico no novo servidor.</span><span class="sxs-lookup"><span data-stu-id="bdafa-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="bdafa-124">O endereço IP inserido é o único endereço IP qual responderá para os serviços hospedados.</span><span class="sxs-lookup"><span data-stu-id="bdafa-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
 <span data-ttu-id="bdafa-125">**Servidor de Mediação**</span><span class="sxs-lookup"><span data-stu-id="bdafa-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="bdafa-126">O FQDN do novo servidor como definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="bdafa-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="bdafa-127">Selecione **usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador que pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="bdafa-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="bdafa-128">Como alternativa, você selecionar um endereço IP para o endereço IP (PSTN) da rede telefônica pública comutada enter e digite um endereço IP específico no novo servidor como o endereço IP principal e **limitar o uso do serviço aos endereços IP selecionados** .</span><span class="sxs-lookup"><span data-stu-id="bdafa-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="bdafa-129">Os endereços IP digitados são o endereço IP único qual responderá para os serviços designados.</span><span class="sxs-lookup"><span data-stu-id="bdafa-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="bdafa-130">Para o servidor de mediação, o endereço IP inserido para o endereço IP principal e o endereço IP PSTN é a mesma por padrão.</span><span class="sxs-lookup"><span data-stu-id="bdafa-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="bdafa-131">Os endereços IP podem ser definidos separadamente, se você estiver usando interfaces de rede dedicada ou endereços IP separados a mesma interface de rede.</span><span class="sxs-lookup"><span data-stu-id="bdafa-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="bdafa-132">Se você tiver interfaces de rede dois, um para a conexão de rede local e um para a conexão de PSTN, você deve atribuir endereços IP diferentes.</span><span class="sxs-lookup"><span data-stu-id="bdafa-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
 <span data-ttu-id="bdafa-133">**Servidor de conferência de áudio/vídeo**</span><span class="sxs-lookup"><span data-stu-id="bdafa-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="bdafa-134">O FQDN do novo servidor como definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="bdafa-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="bdafa-135">Selecione **usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador que pode ser usado.</span><span class="sxs-lookup"><span data-stu-id="bdafa-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="bdafa-136">Como alternativa, você pode selecionar **limitar o uso do serviço aos endereços IP selecionados** e digite um endereço específico no novo servidor.</span><span class="sxs-lookup"><span data-stu-id="bdafa-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="bdafa-137">O endereço IP inserido é o único endereço IP qual responderá para os serviços hospedados.</span><span class="sxs-lookup"><span data-stu-id="bdafa-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
 <span data-ttu-id="bdafa-138">**Servidor de aplicativos confiáveis**</span><span class="sxs-lookup"><span data-stu-id="bdafa-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="bdafa-139">O FQDN do novo servidor como definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="bdafa-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

