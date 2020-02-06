---
title: Adicionar Servidor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- NOCSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Para adicionar um novo servidor a um pool de servidores existente, onde o pool é um dos seguintes:'
ms.openlocfilehash: d4f4afc0d4a7cb6fafe47de95c648aa1769027e6
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41820643"
---
# <a name="add-server"></a><span data-ttu-id="1adad-103">Adicionar Servidor</span><span class="sxs-lookup"><span data-stu-id="1adad-103">Add Server</span></span>
 
<span data-ttu-id="1adad-104">Para adicionar um novo servidor a um pool de servidores existente, onde o pool é um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="1adad-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="1adad-105">Servidor front-end do Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="1adad-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="1adad-106">Servidor diretor</span><span class="sxs-lookup"><span data-stu-id="1adad-106">Director server</span></span>
    
- <span data-ttu-id="1adad-107">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="1adad-107">Mediation Server</span></span>
    
- <span data-ttu-id="1adad-108">Servidor de conferência de áudio/vídeo</span><span class="sxs-lookup"><span data-stu-id="1adad-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="1adad-109">Servidor de aplicativos confiável</span><span class="sxs-lookup"><span data-stu-id="1adad-109">Trusted Application server</span></span>
    
<span data-ttu-id="1adad-110">Cada um dos novos servidores de pool tem requisitos diferentes.</span><span class="sxs-lookup"><span data-stu-id="1adad-110">Each of the new pool servers has different requirements.</span></span> <span data-ttu-id="1adad-111">Nas seções a seguir, localize o tipo de servidor que você está adicionando ao pool existente e forneça as informações solicitadas conforme elas são definidas para cada tipo de servidor.</span><span class="sxs-lookup"><span data-stu-id="1adad-111">In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type.</span></span> <span data-ttu-id="1adad-112">Forneça as informações solicitadas para definir o novo servidor de pool.</span><span class="sxs-lookup"><span data-stu-id="1adad-112">You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="1adad-113">**Servidor front-end do Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="1adad-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="1adad-114">FQDN (nome de domínio totalmente qualificado) do novo servidor conforme definido no DNS (sistema de nomes de domínio).</span><span class="sxs-lookup"><span data-stu-id="1adad-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="1adad-115">Selecione **usar todos os endereços IP configurados**, o que significa que qualquer endereço IP definido no computador poderá ser usado.</span><span class="sxs-lookup"><span data-stu-id="1adad-115">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1adad-116">Você também pode selecionar limitar o **uso do serviço a endereços IP selecionados** e inserir um endereço específico no novo servidor.</span><span class="sxs-lookup"><span data-stu-id="1adad-116">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="1adad-117">O endereço IP inserido é o único endereço IP que irá responder aos serviços hospedados.</span><span class="sxs-lookup"><span data-stu-id="1adad-117">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="1adad-118">Defina um **endereço IP PSTN** quando um servidor de mediação estiver posicionado no servidor front-end.</span><span class="sxs-lookup"><span data-stu-id="1adad-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="1adad-119">Selecione **habilitar IPv6** para habilitar o IPv6 para este servidor.</span><span class="sxs-lookup"><span data-stu-id="1adad-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="1adad-120">**Servidor diretor**</span><span class="sxs-lookup"><span data-stu-id="1adad-120">**Director server**</span></span>
  
- <span data-ttu-id="1adad-121">O FQDN do novo servidor como ele está definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="1adad-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1adad-122">Selecione **usar todos os endereços IP configurados**, o que significa que qualquer endereço IP definido no computador será usado.</span><span class="sxs-lookup"><span data-stu-id="1adad-122">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used.</span></span> <span data-ttu-id="1adad-123">Ou, se preferir, selecione **limitar o uso do serviço para endereços IP selecionados** e insira um endereço IP específico no novo servidor.</span><span class="sxs-lookup"><span data-stu-id="1adad-123">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server.</span></span> <span data-ttu-id="1adad-124">O endereço IP inserido é o único endereço IP que irá responder aos serviços hospedados.</span><span class="sxs-lookup"><span data-stu-id="1adad-124">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="1adad-125">**Servidor de mediação**</span><span class="sxs-lookup"><span data-stu-id="1adad-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="1adad-126">O FQDN do novo servidor como ele está definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="1adad-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1adad-127">Selecione **usar todos os endereços IP configurados**, o que significa que qualquer endereço IP definido no computador poderá ser usado.</span><span class="sxs-lookup"><span data-stu-id="1adad-127">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1adad-128">Ou, se preferir, selecione **limitar o uso do serviço para endereços IP selecionados** e insira um endereço IP específico no novo servidor como o endereço IP principal e insira um endereço IP para o endereço IP da rede telefônica comutada pública (PSTN).</span><span class="sxs-lookup"><span data-stu-id="1adad-128">Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address.</span></span> <span data-ttu-id="1adad-129">Os endereços IP inseridos são o único endereço IP que responderá aos serviços designados.</span><span class="sxs-lookup"><span data-stu-id="1adad-129">The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="1adad-130">Para o servidor de mediação, o endereço IP inserido para o endereço IP primário e o endereço IP PSTN é o mesmo por padrão.</span><span class="sxs-lookup"><span data-stu-id="1adad-130">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default.</span></span> <span data-ttu-id="1adad-131">Os endereços IP podem ser definidos separadamente se você estiver usando interfaces de rede dedicadas ou endereços IP separados na mesma interface de rede.</span><span class="sxs-lookup"><span data-stu-id="1adad-131">The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface.</span></span> <span data-ttu-id="1adad-132">Se você tiver duas interfaces de rede, uma para a conexão de rede local e outra para a conexão PSTN, será preciso atribuir endereços IP diferentes.</span><span class="sxs-lookup"><span data-stu-id="1adad-132">If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="1adad-133">**Servidor de conferência de áudio/vídeo**</span><span class="sxs-lookup"><span data-stu-id="1adad-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="1adad-134">O FQDN do novo servidor como ele está definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="1adad-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="1adad-135">Selecione **usar todos os endereços IP configurados**, o que significa que qualquer endereço IP definido no computador poderá ser usado.</span><span class="sxs-lookup"><span data-stu-id="1adad-135">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used.</span></span> <span data-ttu-id="1adad-136">Você também pode selecionar limitar o **uso do serviço a endereços IP selecionados** e inserir um endereço específico no novo servidor.</span><span class="sxs-lookup"><span data-stu-id="1adad-136">Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server.</span></span> <span data-ttu-id="1adad-137">O endereço IP inserido é o único endereço IP que irá responder aos serviços hospedados.</span><span class="sxs-lookup"><span data-stu-id="1adad-137">The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="1adad-138">**Servidor de aplicativos confiável**</span><span class="sxs-lookup"><span data-stu-id="1adad-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="1adad-139">O FQDN do novo servidor como ele está definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="1adad-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

