---
title: Adicionar FQDN do Pool de Front-Ends
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddFrontEndPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 02ae996c-a1c6-4ff4-b6d6-bdef4ad44d2a
description: Especifique o nome de domínio totalmente qualificado (FQDN) do pool de front-ends que você está criando. Não é possível alterar o FQDN de um pool após a publicação da topologia que contém o pool de front-ends. Se precisar renomear um pool, você deve excluir o pool e adicionar um novo pool com o novo FQDN.
ms.openlocfilehash: e9e420956656d7bd0217f122844ea222f6bd2b40
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41698226"
---
# <a name="add-front-end-pool-fqdn"></a><span data-ttu-id="8d5cc-105">Adicionar FQDN do Pool de Front-Ends</span><span class="sxs-lookup"><span data-stu-id="8d5cc-105">Add Front End Pool FQDN</span></span>
 
<span data-ttu-id="8d5cc-106">Especifique o nome de domínio totalmente qualificado (FQDN) do pool de front-ends que você está criando.</span><span class="sxs-lookup"><span data-stu-id="8d5cc-106">Specify the fully qualified domain name (FQDN) of the Front End pool that you are creating.</span></span> <span data-ttu-id="8d5cc-107">Não é possível alterar o FQDN de um pool após a publicação da topologia que contém o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="8d5cc-107">You cannot change the FQDN of a pool after you publish the topology containing the Front End pool.</span></span> <span data-ttu-id="8d5cc-108">Se precisar renomear um pool, você deve excluir o pool e adicionar um novo pool com o novo FQDN.</span><span class="sxs-lookup"><span data-stu-id="8d5cc-108">If you need to rename a pool, you must delete the pool and then add a new pool with the new FQDN.</span></span>
  
> [!TIP]
> <span data-ttu-id="8d5cc-109">Se você pretende implementar um pool de front-end no futuro, selecione **vários pools de computadores**.</span><span class="sxs-lookup"><span data-stu-id="8d5cc-109">If you plan to implement a Front End pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="8d5cc-110">Embora um pool seja definido como dois ou mais computadores com carga balanceada, é possível criar um único pool de computadores e criar um FQDN de pool para o computador único.</span><span class="sxs-lookup"><span data-stu-id="8d5cc-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="8d5cc-111">Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deve executar o construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de front-end por meio do assistente de implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="8d5cc-111">When you are ready to add more computers to the pool later, you must run Topology Builder again to define the new pool member, publish the new topology, and then set up the new Front End pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="8d5cc-112">Você também deve adicionar o novo membro do pool aos balanceadores de carga apropriados para o pool, o balanceamento de carga DNS (sistema de nomes de domínio) ou balanceadores de carga de hardware.</span><span class="sxs-lookup"><span data-stu-id="8d5cc-112">You must also add the new pool member to the appropriate load balancers for the pool, Domain Name System (DNS) load balancing, or hardware load balancers.</span></span> <span data-ttu-id="8d5cc-113">Em muitos casos, você teria dois sistemas de balanceamento de carga in-loco.</span><span class="sxs-lookup"><span data-stu-id="8d5cc-113">In many cases, you would have both load balancing systems in place.</span></span> <span data-ttu-id="8d5cc-114">Certifique-se de que você está adicionando o novo servidor membro a ambos.</span><span class="sxs-lookup"><span data-stu-id="8d5cc-114">Be sure that you are adding the new member server to both.</span></span> 
  

