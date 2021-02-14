---
title: Adicionar Pool A/V MCU
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
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Todos os Servidores Front-End Enterprise Edition de um local central que não têm um serviço de Conferência A/V colocado podem usar o mesmo pool de Conferência A/V autônomo. Para cada pool de Conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e indicar se ele terá apenas um Servidor de Conferência A/V ou vários Servidores de Conferência A/V com balanceamento de carga.
ms.openlocfilehash: 689f91bd27e4b3bbb2bd31149f34438bac59db46
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49810461"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="6ead9-104">Adicionar Pool A/V MCU</span><span class="sxs-lookup"><span data-stu-id="6ead9-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="6ead9-p102">Todos os Servidores Front-End Enterprise Edition de um local central que não têm um serviço de Conferência A/V colocado podem usar o mesmo pool de Conferência A/V autônomo. Para cada pool de Conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e indicar se ele terá apenas um Servidor de Conferência A/V ou vários Servidores de Conferência A/V com balanceamento de carga.</span><span class="sxs-lookup"><span data-stu-id="6ead9-p102">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool. For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="6ead9-p103">Você não pode converter um pool de servidor único em um pool de múltiplos servidores. Caso decida, mais tarde, de que sua organização necessita de um pool de múltiplos servidores, você deve deletar o pool de servidor único e então adicionar o pool de múltiplos servidores.</span><span class="sxs-lookup"><span data-stu-id="6ead9-p103">You cannot convert a single-server pool to a multiple-server pool. If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="6ead9-109">Caso você planeje implementar um pool de Conferência A/V no futuro, selecione **Pool de múltiplos computadores**.</span><span class="sxs-lookup"><span data-stu-id="6ead9-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="6ead9-110">Embora um pool seja definido como dois ou mais computadores que estão com cargas balanceadas, você pode criar um pool de único computador e criar um pool FQDN para o computador único.</span><span class="sxs-lookup"><span data-stu-id="6ead9-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="6ead9-111">Quando estiver pronto para adicionar mais computadores ao pool posteriormente, você deverá definir o Construtor de Topologias novamente para definir o novo membro do pool, publicar a nova topologia e configurar o novo membro do pool de Conferência A/V por meio do Assistente de Implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="6ead9-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="6ead9-112">Pools de Servidor de Conferência A/V são únicos por não precisarem de balanceadores de carga para criar um pool.</span><span class="sxs-lookup"><span data-stu-id="6ead9-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="6ead9-113">Pools de Conferência A/V balanceiam a carga internamente e não exigem hardware adicional.</span><span class="sxs-lookup"><span data-stu-id="6ead9-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

