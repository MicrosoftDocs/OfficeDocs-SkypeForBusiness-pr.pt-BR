---
title: Adicionar Servidor
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddMachinePage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 61647eac-9062-4381-9c80-3cbf70b7db33
description: 'Para adicionar um novo servidor a um pool de servidores existente, no qual o pool é um dos seguintes:'
ms.openlocfilehash: e40cf71b0ab52e66a3a28e0362de4f9106ddd831
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49818621"
---
# <a name="add-server"></a><span data-ttu-id="3b09e-103">Adicionar Servidor</span><span class="sxs-lookup"><span data-stu-id="3b09e-103">Add Server</span></span>
 
<span data-ttu-id="3b09e-104">Para adicionar um novo servidor a um pool de servidores existente, no qual o pool é um dos seguintes:</span><span class="sxs-lookup"><span data-stu-id="3b09e-104">To add a new server to an existing pool of servers, where the pool is one of the following:</span></span>
  
- <span data-ttu-id="3b09e-105">Servidor Front-Ends Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="3b09e-105">Enterprise Edition Front End Server</span></span>
    
- <span data-ttu-id="3b09e-106">Servidor de Diretor</span><span class="sxs-lookup"><span data-stu-id="3b09e-106">Director server</span></span>
    
- <span data-ttu-id="3b09e-107">Servidor de Mediação</span><span class="sxs-lookup"><span data-stu-id="3b09e-107">Mediation Server</span></span>
    
- <span data-ttu-id="3b09e-108">Servidor de Conferência de Áudio/Vídeo</span><span class="sxs-lookup"><span data-stu-id="3b09e-108">Audio/Video Conferencing Server</span></span>
    
- <span data-ttu-id="3b09e-109">Servidor de Aplicativo Confiável</span><span class="sxs-lookup"><span data-stu-id="3b09e-109">Trusted Application server</span></span>
    
<span data-ttu-id="3b09e-p101">Cada um dos novos servidores de pool possuem requisitos diferentes. Localize, nas seções a seguir, o tipo de servidor que você está adicionando ao pool existente e forneça a informação exigida, conforme definido para cada tipo de servidor. Você providencia a informação exigida para definir o novo servidor de pool.</span><span class="sxs-lookup"><span data-stu-id="3b09e-p101">Each of the new pool servers has different requirements. In the following sections, locate the type of server that you are adding to the existing pool, and supply the information requested as it is defined for each server type. You provide the requested information to define the new pool server.</span></span>
  
 <span data-ttu-id="3b09e-113">**Servidor de Front-Ends Enterprise Edition**</span><span class="sxs-lookup"><span data-stu-id="3b09e-113">**Enterprise Edition Front End Server**</span></span>
  
- <span data-ttu-id="3b09e-114">FQDN (nome de domínio totalmente qualificado) do novo servidor como definido no DNS (Domain Name System).</span><span class="sxs-lookup"><span data-stu-id="3b09e-114">Fully qualified domain name (FQDN) of the new server as it is defined in Domain Name System (DNS).</span></span>
    
- <span data-ttu-id="3b09e-p102">Selecione **Usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador pode ser usado. Alternativamente, você pode selecionar **Limitar utilização de serviço aos endereços IP selecionados** e inserir um endereço específico no novo servidor. O endereço IP inserido é o único endereço IP que responderá aos serviços hospedados.</span><span class="sxs-lookup"><span data-stu-id="3b09e-p102">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
- <span data-ttu-id="3b09e-118">Definir um  **Endereço IP PSTN** quando um Servidor de Mediação é colocado no Servidor Front-Ends.</span><span class="sxs-lookup"><span data-stu-id="3b09e-118">Define a **PSTN IP address** when a Mediation Server is collocated on the Front End Server.</span></span>
    
- <span data-ttu-id="3b09e-119">Select **Enable IPv6** to enable IPv6 for this server.</span><span class="sxs-lookup"><span data-stu-id="3b09e-119">Select **Enable IPv6** to enable IPv6 for this server.</span></span>
    
  <span data-ttu-id="3b09e-120">**Servidor de Diretor**</span><span class="sxs-lookup"><span data-stu-id="3b09e-120">**Director server**</span></span>
  
- <span data-ttu-id="3b09e-121">O FQDN do novo servidor como definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="3b09e-121">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="3b09e-p103">Selecione  **Usar todos os endereços de IP configurados**,  que significa que qualquer endereço IP definido no computador será usado.  Alternativamente, você pode selecionar  **Limitar utilização de serviço aos endereços IP selecionados** e inserir um endereço IP específico no novo servidor. O endereço IP inserido é o único endereço IP que responderá aos serviços hospedados.</span><span class="sxs-lookup"><span data-stu-id="3b09e-p103">Select **Use all configured IP addresses**, which means that any IP address defined on the computer will be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="3b09e-125">**Servidor de Mediação**</span><span class="sxs-lookup"><span data-stu-id="3b09e-125">**Mediation Server**</span></span>
  
- <span data-ttu-id="3b09e-126">O FQDN do novo servidor como definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="3b09e-126">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="3b09e-p104">Selecione **Usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador pode ser usado.  Alternativamente, você pode selecionar **Limitar utilização de serviço aos endereços IP selecionados** e inserir um endereço IP específico no novo servidor como o endereço IP Primário, inserindo então um endereço IP para o endereço IP PSTN (rede telefônica pública comutada). O endereço IP inserido é o único endereço IP que responderá aos serviços hospedados.</span><span class="sxs-lookup"><span data-stu-id="3b09e-p104">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you select **Limit service usage to selected IP addresses** and enter a specific IP address on the new server as the Primary IP address, and an enter an IP address for the public switched telephone network (PSTN) IP address. The IP addresses entered are the only IP address which will respond for the designated services.</span></span>
    
    > [!NOTE]
    > <span data-ttu-id="3b09e-p105">Para o Servidor de Mediação, o endereço IP inserido para o endereço IP Primário e o endereço IP PSTN são os mesmos, por padrão. Os endereços IP podem ser definidos separadamente caso você esteja usando interfaces de rede dedicadas ou endereços IP separados na mesma interface de rede. Caso você tenha duas interfaces de rede, uma para a conexão de rede local e outra para a conexão PSTN, você deve atribuir endereços IP diferentes.</span><span class="sxs-lookup"><span data-stu-id="3b09e-p105">For the Mediation Server, the IP address entered for the Primary IP address and the PSTN IP address is the same by default. The IP addresses can be defined separately if you are using dedicated network interfaces or separate IP addresses on the same network interface. If you have two network interfaces, one for the local network connection and one for the PSTN connection, you must assign different IP addresses.</span></span> 
  
  <span data-ttu-id="3b09e-133">**Servidor de Conferência de Áudio/Vídeo**</span><span class="sxs-lookup"><span data-stu-id="3b09e-133">**Audio/Video Conferencing Server**</span></span>
  
- <span data-ttu-id="3b09e-134">O FQDN do novo servidor como definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="3b09e-134">The FQDN of the new server as it is defined in DNS.</span></span>
    
- <span data-ttu-id="3b09e-p106">Selecione  **Usar todos os endereços IP configurados**, que significa que qualquer endereço IP definido no computador pode ser usado. Alternativamente, você pode selecionar  **Limitar utilização de serviço aos endereços IP selecionados** e inserir um endereço específico no novo servidor. O endereço IP inserido é o único endereço IP que responderá aos serviços hospedados.</span><span class="sxs-lookup"><span data-stu-id="3b09e-p106">Select **Use all configured IP addresses**, which means that any IP address defined on the computer can be used. Alternatively, you can select **Limit service usage to selected IP addresses** and enter a specific address on the new server. The IP address entered is the only IP address which will respond for the hosted services.</span></span>
    
  <span data-ttu-id="3b09e-138">**Servidor de Aplicativos Confiáveis**</span><span class="sxs-lookup"><span data-stu-id="3b09e-138">**Trusted Application server**</span></span>
  
- <span data-ttu-id="3b09e-139">O FQDN do novo servidor como definido no DNS.</span><span class="sxs-lookup"><span data-stu-id="3b09e-139">The FQDN of the new server as it is defined in DNS.</span></span>
    

