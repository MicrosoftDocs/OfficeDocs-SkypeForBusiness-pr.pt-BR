---
title: Adicionar Pool de diretor
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2014
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para definir o FQDN do pool de diretor, selecione um pool de vários computadores que consiste em dois ou mais diretores em um pool com balanceamento de carga, ou um pool de computador único. Você também deverá digitar o nome de domínio totalmente qualificado (FQDN) que será usado para conectar ao pool de diretores ou FQDN do Diretor único. Para um pool de computadores de diretor, isso seria a entrada de sistema de nome de domínio (DNS) para o IP virtual de um balanceador de carga de hardware ou a entrada DNS compartilhada para balanceamento de carga DNS.
ms.openlocfilehash: d71219f6e9c51d69bee8d2457cc30c19f4fa6c89
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="add-director-pool"></a><span data-ttu-id="5d859-105">Adicionar Pool de diretor</span><span class="sxs-lookup"><span data-stu-id="5d859-105">Add Director Pool</span></span>
 
<span data-ttu-id="5d859-106">Para **definir o FQDN do pool de diretor**, selecione um **pool de vários computadores** que consiste em dois ou mais diretores em um pool com balanceamento de carga ou um **pool de computador único**.</span><span class="sxs-lookup"><span data-stu-id="5d859-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="5d859-107">Você também deverá digitar o nome de domínio totalmente qualificado (FQDN) que será usado para conectar ao pool de diretores ou FQDN do Diretor único.</span><span class="sxs-lookup"><span data-stu-id="5d859-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="5d859-108">Para um pool de computadores de diretor, isso seria a entrada de sistema de nome de domínio (DNS) para o IP virtual de um balanceador de carga de hardware ou a entrada DNS compartilhada para balanceamento de carga DNS.</span><span class="sxs-lookup"><span data-stu-id="5d859-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="5d859-109">Se você pretende implementar um pool de diretores no futuro, selecione **pool de vários computadores**.</span><span class="sxs-lookup"><span data-stu-id="5d859-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="5d859-110">Embora um pool estiver definido como dois ou mais computadores que estão com balanceamento de carga, você pode criar um pool de computador único e criar um pool FQDN para o único computador.</span><span class="sxs-lookup"><span data-stu-id="5d859-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="5d859-111">Quando você estiver pronto para adicionar mais computadores ao pool posteriormente, você deve executar o construtor de topologias novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro de pool de diretor através do Skype para o Assistente de implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="5d859-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="5d859-112">Você também deve adicionar o novo membro de pool para os balanceadores de carga apropriado para o pool, para o sistema de nome de domínio (DNS) balanceamento de carga, ou balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="5d859-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="5d859-113">Em muitos casos, você terá de ambos os sistemas in-loco de balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="5d859-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="5d859-114">Certifique-se de que você está adicionando o novo servidor membro para ambos.</span><span class="sxs-lookup"><span data-stu-id="5d859-114">Be sure that you are adding the new member server to both.</span></span> 
  

