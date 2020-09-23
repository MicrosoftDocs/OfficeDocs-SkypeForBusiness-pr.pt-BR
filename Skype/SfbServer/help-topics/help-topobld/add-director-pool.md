---
title: Adicionar Pool de Diretor
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddDirectorPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 751ead48-b97f-4c6f-ba6b-14d446473658
description: Para  Definir o FQDN do Pool de Diretores, selecione um  Pool de vários computadores , formado por dois ou mais Diretores em um pool com carga balanceada, ou um  Pool com um único computador . Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool de diretores ou ao FQDN do diretor único. Para um pool de computadores Diretores, essa seria a entrada de DNS (Sistema de Nomes de Domínio) do IP virtual de um balanceador de carga de hardware ou a entrada de DNS compartilhada para balanceamento de carga de DNS.
ms.openlocfilehash: 9209fa9e4417644b20b95668b05e660114414efc
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48219482"
---
# <a name="add-director-pool"></a><span data-ttu-id="6fc56-105">Adicionar Pool de Diretor</span><span class="sxs-lookup"><span data-stu-id="6fc56-105">Add Director Pool</span></span>
 
<span data-ttu-id="6fc56-106">Para  **Definir o FQDN do Pool de Diretores**, selecione um  \*\*Pool de vários computadores \*\*, formado por dois ou mais Diretores em um pool com carga balanceada, ou um  \*\*Pool com um único computador \*\*.</span><span class="sxs-lookup"><span data-stu-id="6fc56-106">To **Define the Director pool FQDN**, select either a **Multiple computer pool** that will consist of two or more Directors in a load-balanced pool, or a **Single computer pool**.</span></span> <span data-ttu-id="6fc56-107">Você também deve digitar o FQDN (nome de domínio totalmente qualificado) que será usado para se conectar ao pool de diretores ou ao FQDN do diretor único.</span><span class="sxs-lookup"><span data-stu-id="6fc56-107">You must also type the fully qualified domain name (FQDN) that will be used to connect to the Director pool or the single Director's FQDN.</span></span> <span data-ttu-id="6fc56-108">Para um pool de computadores Diretores, essa seria a entrada de DNS (Sistema de Nomes de Domínio) do IP virtual de um balanceador de carga de hardware ou a entrada de DNS compartilhada para balanceamento de carga de DNS.</span><span class="sxs-lookup"><span data-stu-id="6fc56-108">For a pool of Director computers, this would be the Domain Name System (DNS) entry for the virtual IP of a hardware load balancer or the shared DNS entry for DNS load balancing.</span></span>
  
> [!TIP]
> <span data-ttu-id="6fc56-109">Caso planeje implementar um pool de Diretor no futuro, selecione  \*\*Pool de múltiplos computadores \*\*.</span><span class="sxs-lookup"><span data-stu-id="6fc56-109">If you plan to implement a Director pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="6fc56-110">Embora um pool seja definido como dois ou mais computadores que estão com cargas balanceadas, você pode criar um pool de único computador e criar um pool FQDN para o computador único.</span><span class="sxs-lookup"><span data-stu-id="6fc56-110">Even though a pool is defined as two or more computers that are load-balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="6fc56-111">Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deverá executar o construtor de topologias novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de diretores através do assistente de implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6fc56-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then setup the new Director pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="6fc56-112">Você também deve adicionar o novo membro do pool aos balanceadores de carga do pool, balanceamento de carga DNS (Domain Name System) ou para balanceadores de carga de hardware apropriados.</span><span class="sxs-lookup"><span data-stu-id="6fc56-112">You must also add the new pool member to the appropriate load balancers for the pool, for Domain Name System (DNS) load-balancing, or for hardware load balancers.</span></span> <span data-ttu-id="6fc56-113">Em muitos caso, você terá ambos sistemas de balanceamento de carga instalados.</span><span class="sxs-lookup"><span data-stu-id="6fc56-113">In many cases, you will have both load balancing systems in place.</span></span> <span data-ttu-id="6fc56-114">Certifique-se de que você está adicionando o novo servidor membro a ambos.</span><span class="sxs-lookup"><span data-stu-id="6fc56-114">Be sure that you are adding the new member server to both.</span></span> 
  

