---
title: Adicionar FQDN do Pool de Front-Ends
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
ROBOTS: NOINDEX, NOFOLLOW
description: Especifique o nome de domínio totalmente qualificado (FQDN) do pool de Front-End que você está criando. Depois de publicar a topologia que contém o pool de Front-End, você não pode alterar o FQDN de um pool. Se você precisar renomear um pool, você deve excluir o pool e, em seguida, adicionar um novo pool com o novo FQDN.
ms.openlocfilehash: 28e831df0cdf86620eefc1a22ced199507026c46
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30884249"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="3d221-105">Adicionar FQDN do Pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="3d221-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="3d221-106">Especifique o nome de domínio totalmente qualificado (FQDN) do pool de Front-End que você está criando.</span><span class="sxs-lookup"><span data-stu-id="3d221-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="3d221-107">Depois de publicar a topologia que contém o pool de Front-End, você não pode alterar o FQDN de um pool.</span><span class="sxs-lookup"><span data-stu-id="3d221-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="3d221-108">Se você precisar renomear um pool, você deve excluir o pool e, em seguida, adicionar um novo pool com o novo FQDN.</span><span class="sxs-lookup"><span data-stu-id="3d221-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="3d221-109">Se você pretende implementar um pool de Front-End no futuro, selecione **pool de vários computadores**.</span><span class="sxs-lookup"><span data-stu-id="3d221-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="3d221-110">Embora um pool seja definido como dois ou mais computadores com carga balanceada, é possível criar um único pool de computadores e criar um FQDN de pool para o computador único.</span><span class="sxs-lookup"><span data-stu-id="3d221-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="3d221-111">Quando você estiver pronto para adicionar mais computadores ao pool posteriormente, você deve executar o construtor de topologias novamente para definir o novo membro do pool, publicar a nova topologia e configurar o novo membro de pool de Front-End por meio do Skype para o Assistente de implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="3d221-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="3d221-112">Você também deve adicionar o novo membro de pool para os balanceadores de carga apropriado para o pool, balanceamento de carga de sistema de nome de domínio (DNS) ou balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="3d221-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="3d221-113">Em muitos casos, você teria ambos os sistemas in-loco de balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="3d221-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="3d221-114">Certifique-se de que você está adicionando o novo servidor membro para ambos.</span><span class="sxs-lookup"><span data-stu-id="3d221-114">Be sure that you are adding the new member server to both.</span></span> 
  

