---
title: Adicionar FQDN do Pool de Front-Ends
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique o FQDN (nome de domínio totalmente qualificado) do pool de Front-Ends que você está criando. Você não pode alterar o FQDN de um pool após publicar a topologia que contém o pool de Front-Ends. Se precisar renomear um pool, você deverá excluí-lo e adicionar um novo pool com o novo FQDN.
ms.openlocfilehash: 7b0b14ab9b8cb450a80872cedf61e6f24da91dc2
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49811651"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="4a401-105">Adicionar FQDN do Pool de Front-ends</span><span class="sxs-lookup"><span data-stu-id="4a401-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="4a401-p102">Especifique o FQDN (nome de domínio totalmente qualificado) do pool de Front-Ends que você está criando. Você não pode alterar o FQDN de um pool após publicar a topologia que contém o pool de Front-Ends. Se precisar renomear um pool, você deverá excluí-lo e adicionar um novo pool com o novo FQDN.</span><span class="sxs-lookup"><span data-stu-id="4a401-p102">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating. You cannot change the FQDN of a pool after you publish the topology containing the Front End pool. If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="4a401-109">Se você planeja implementar um pool de Front-Ends no futuro, selecione **Pool de múltiplos computadores**.</span><span class="sxs-lookup"><span data-stu-id="4a401-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="4a401-110">Embora um pool seja definido como dois ou mais computadores que estão com cargas balanceadas, você pode criar um pool de único computador e criar um pool FQDN para o computador único.</span><span class="sxs-lookup"><span data-stu-id="4a401-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="4a401-111">Quando estiver pronto para adicionar mais computadores ao pool posteriormente, você deverá executar o Construtor de Topologias novamente para definir o novo membro do pool, publicar a nova topologia e configurar o novo membro do pool de Front-End por meio do Assistente de Implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="4a401-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="4a401-112">Também é necessário adicionar o novo membro do pool aos balanceadores de carga apropriados para o pool, balanceamento de carga DNS (Domain Name System) ou balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="4a401-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="4a401-113">Em muitos casos, existem os dois sistemas de balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="4a401-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="4a401-114">Certifique-se de que você está adicionando o novo servidor membro a ambos.</span><span class="sxs-lookup"><span data-stu-id="4a401-114">Be sure that you are adding the new member server to both.</span></span> 
  

