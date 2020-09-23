---
title: Adicionar Pool A/V MCU
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
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Todos os Servidores Front-End Enterprise Edition de um local central que não têm um serviço de Conferência A/V colocado podem usar o mesmo pool de Conferência A/V autônomo. Para cada pool de Conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e indicar se ele terá apenas um Servidor de Conferência A/V ou vários Servidores de Conferência A/V com balanceamento de carga.
ms.openlocfilehash: e38bcf5efa065ef2f9b53a5df47f6a56eafbe29a
ms.sourcegitcommit: c69ab11b701a4833179b8479bc3204dfd4412096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/23/2020
ms.locfileid: "48217472"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="0bd9b-104">Adicionar Pool A/V MCU</span><span class="sxs-lookup"><span data-stu-id="0bd9b-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="0bd9b-p102">Todos os Servidores Front-End Enterprise Edition de um local central que não têm um serviço de Conferência A/V colocado podem usar o mesmo pool de Conferência A/V autônomo. Para cada pool de Conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e indicar se ele terá apenas um Servidor de Conferência A/V ou vários Servidores de Conferência A/V com balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="0bd9b-p102">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool. For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="0bd9b-p103">Você não pode converter um pool de servidor único em um pool de múltiplos servidores. Caso decida, mais tarde, de que sua organização necessita de um pool de múltiplos servidores, você deve deletar o pool de servidor único e então adicionar o pool de múltiplos servidores.</span><span class="sxs-lookup"><span data-stu-id="0bd9b-p103">You cannot convert a single-server pool to a multiple-server pool. If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="0bd9b-109">Caso você planeje implementar um pool de Conferência A/V no futuro, selecione **Pool de múltiplos computadores**.</span><span class="sxs-lookup"><span data-stu-id="0bd9b-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="0bd9b-110">Embora um pool seja definido como dois ou mais computadores que estão com cargas balanceadas, você pode criar um pool de único computador e criar um pool FQDN para o computador único.</span><span class="sxs-lookup"><span data-stu-id="0bd9b-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="0bd9b-111">Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você precisará do construtor de topologias novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de conferência A/V através do assistente de implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="0bd9b-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="0bd9b-112">Pools de Servidor de Conferência A/V são únicos por não precisarem de balanceadores de carga para criar um pool.</span><span class="sxs-lookup"><span data-stu-id="0bd9b-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="0bd9b-113">Pools de Conferência A/V balanceiam a carga internamente e não exigem hardware adicional.</span><span class="sxs-lookup"><span data-stu-id="0bd9b-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

