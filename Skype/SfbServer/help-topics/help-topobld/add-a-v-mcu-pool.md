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
- NOCSH
ms.custom:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Todos os servidores front-end Enterprise Edition de um site central que não tenham um serviço de conferência A/V posicionado podem usar o mesmo pool autônomo de conferência A/V. Para cada pool de conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e se ele terá apenas um único servidor de conferência A/V ou servidores de conferência A/V com carga balanceada.
ms.openlocfilehash: 1d78a9d24659ec2ad571c01528323796e7ae5d18
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41821313"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="fb20c-104">Adicionar Pool A/V MCU</span><span class="sxs-lookup"><span data-stu-id="fb20c-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="fb20c-105">Todos os servidores front-end Enterprise Edition de um site central que não tenham um serviço de conferência A/V posicionado podem usar o mesmo pool autônomo de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="fb20c-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="fb20c-106">Para cada pool de conferência A/V, você deve especificar um FQDN (nome de domínio totalmente qualificado) para o pool e se ele terá apenas um único servidor de conferência A/V ou servidores de conferência A/V com carga balanceada.</span><span class="sxs-lookup"><span data-stu-id="fb20c-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="fb20c-107">Não é possível converter um pool de servidor único em um pool de vários servidores.</span><span class="sxs-lookup"><span data-stu-id="fb20c-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="fb20c-108">Se, posteriormente, você decidir que a sua organização precisa de um pool de vários servidores, você deve excluir o pool de servidor único e, em seguida, adicionar o pool de vários servidores.</span><span class="sxs-lookup"><span data-stu-id="fb20c-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="fb20c-109">Se você pretende implementar um pool de conferência A/V no futuro, selecione **vários pools de computadores**.</span><span class="sxs-lookup"><span data-stu-id="fb20c-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="fb20c-110">Embora um pool seja definido como dois ou mais computadores com carga balanceada, é possível criar um único pool de computadores e criar um FQDN de pool para o computador único.</span><span class="sxs-lookup"><span data-stu-id="fb20c-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="fb20c-111">Quando estiver pronto para adicionar mais computadores ao pool mais tarde, você deve ter o construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e, em seguida, configurar o novo membro do pool de conferência a/V por meio do assistente de implantação do Skype for Business Server.</span><span class="sxs-lookup"><span data-stu-id="fb20c-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="fb20c-112">Os pools do servidor de conferência A/V são exclusivos porque não precisam de balanceadores de carga para criar um pool.</span><span class="sxs-lookup"><span data-stu-id="fb20c-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="fb20c-113">O balanceamento de carga de pools de conferência A/V internamente e não precisa de hardware adicional.</span><span class="sxs-lookup"><span data-stu-id="fb20c-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

