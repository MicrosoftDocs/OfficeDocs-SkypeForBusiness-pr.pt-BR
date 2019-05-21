---
title: Adicionar Pool de Diretor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir o FQDN do pool de directors, selecione um pool de vários computadores que consistirá em dois ou mais directors em um pool de balanceamento de carga ou em um único pool de computador. Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool do diretor ou ao FQDN do diretor único. Para um pool de computadores do diretor, essa seria a entrada do sistema de nome de domínio (DNS) para o IP virtual de um balanceador de carga de hardware ou a entrada DNS compartilhada para o balanceamento de carga de DNS.
ms.openlocfilehash: 163de8a6091e74238c4a4127ae39f7cd500cdb84
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34304783"
---
# <a name="add-director-pool"></a><span data-ttu-id="d8d73-105">Adicionar Pool de Diretor</span><span class="sxs-lookup"><span data-stu-id="d8d73-105">Add Director Pool</span></span>
 
<span data-ttu-id="d8d73-106">Para **definir o FQDN do pool de directors**, selecione um **pool de vários computadores** que consistirá em dois ou mais directors em um pool de balanceamento de carga ou em um **único pool de computador**.</span><span class="sxs-lookup"><span data-stu-id="d8d73-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="d8d73-107">Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool do diretor ou ao FQDN do diretor único.</span><span class="sxs-lookup"><span data-stu-id="d8d73-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="d8d73-108">Para um pool de computadores do diretor, essa seria a entrada do sistema de nome de domínio (DNS) para o IP virtual de um balanceador de carga de hardware ou a entrada DNS compartilhada para o balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="d8d73-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="d8d73-109">Se você pretende implementar um pool de diretor no futuro, selecione **vários pools de computadores**.</span><span class="sxs-lookup"><span data-stu-id="d8d73-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="d8d73-110">Embora um pool seja definido como dois ou mais computadores com balanceamento de carga, você pode criar um único pool de computador e criar um FQDN do pool para o único computador.</span><span class="sxs-lookup"><span data-stu-id="d8d73-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="d8d73-111">Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deve executar o construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de directors por meio do assistente de implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="d8d73-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="d8d73-112">Você também deve adicionar o novo membro do pool aos balanceadores de carga apropriados para o pool, para o balanceamento de carga do sistema de nome de domínio (DNS) ou para balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="d8d73-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="d8d73-113">Em muitos casos, você terá os dois sistemas de balanceamento de carga in-loco.</span><span class="sxs-lookup"><span data-stu-id="d8d73-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="d8d73-114">Certifique-se de que você está adicionando o novo servidor membro a ambos.</span><span class="sxs-lookup"><span data-stu-id="d8d73-114">Be sure that you are adding the new member server to both.</span></span> 
  

