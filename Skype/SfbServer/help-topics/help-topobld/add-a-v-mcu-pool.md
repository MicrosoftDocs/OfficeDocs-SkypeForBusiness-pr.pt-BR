---
title: Adicionar A / V MCU Pool
ms.author: kenwith
author: kenwith
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddAvMcuPoolPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e201875e-1e81-4756-942f-c17d177e997b
description: Todos os servidores Enterprise Edition Front End de um site central que não têm um colocado uma / serviço V Conferencing pode usar a mesma stand-alone A / pool de conferência V. Para cada pool de conferência V, você deve especificar um nome de domínio totalmente qualificado (FQDN) para o pool e se ele terá somente um único a / V Conferencing Server ou múltiplo, com balanceamento de carga A / V Conferencing Servers.
ms.openlocfilehash: 435b750715246be6e1f461dd49ce53965c85d2a6
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "21016548"
---
# <a name="add-av-mcu-pool"></a><span data-ttu-id="66e06-104">Adicionar A / V MCU Pool</span><span class="sxs-lookup"><span data-stu-id="66e06-104">Add A/V MCU Pool</span></span>
 
<span data-ttu-id="66e06-105">Todos os servidores Enterprise Edition Front End de um site central que não têm um colocado uma / serviço V Conferencing pode usar a mesma stand-alone A / pool de conferência V.</span><span class="sxs-lookup"><span data-stu-id="66e06-105">All Enterprise Edition Front End Servers of a central site that do not have a collocated A/V Conferencing service can use the same stand-alone A/V Conferencing pool.</span></span> <span data-ttu-id="66e06-106">Para cada pool de conferência V, você deve especificar um nome de domínio totalmente qualificado (FQDN) para o pool e se ele terá somente um único a / V Conferencing Server ou múltiplo, com balanceamento de carga A / V Conferencing Servers.</span><span class="sxs-lookup"><span data-stu-id="66e06-106">For each A/V Conferencing pool, you must specify a fully qualified domain name (FQDN) for the pool and whether it will have only a single A/V Conferencing Server or multiple, load-balanced A/V Conferencing Servers.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="66e06-107">Você não pode converter um pool de servidor único em um pool de vários servidores.</span><span class="sxs-lookup"><span data-stu-id="66e06-107">You cannot convert a single-server pool to a multiple-server pool.</span></span> <span data-ttu-id="66e06-108">Se posteriormente você decidir que sua organização precisa de um pool de vários servidores, você deve excluir o pool de servidor único e, em seguida, adicione o pool de vários servidores.</span><span class="sxs-lookup"><span data-stu-id="66e06-108">If you later decide that your organization needs a multiple-server pool, you must delete the single-server pool, and then add the multiple-server pool.</span></span> 
  
> [!TIP]
> <span data-ttu-id="66e06-109">Se você pretende implementar um A / pool de conferência V no futuro, selecione **pool de vários computadores**.</span><span class="sxs-lookup"><span data-stu-id="66e06-109">If you plan to implement an A/V Conferencing pool in the future, select **Multiple computer pool**.</span></span> <span data-ttu-id="66e06-110">Embora um pool seja definido como dois ou mais computadores com carga balanceada, é possível criar um único pool de computadores e criar um FQDN de pool para o computador único.</span><span class="sxs-lookup"><span data-stu-id="66e06-110">Even though a pool is defined as two or more computers that are load balanced, you can create a single computer pool and create a pool FQDN for the single computer.</span></span> <span data-ttu-id="66e06-111">Quando você estiver pronto para adicionar mais computadores ao pool posteriormente, você deve construtor de topologia novamente para definir o novo membro do pool, publicar a nova topologia e em seguida, configure a novo A / V Conferencing pool membro por meio do Skype para o Assistente de implantação de servidor de negócios.</span><span class="sxs-lookup"><span data-stu-id="66e06-111">When you are ready to add more computers to the pool later, you must Topology Builder again to define the new pool member, publish the new topology, and then set up the new A/V Conferencing pool member through the Skype for Business Server Deployment Wizard.</span></span> <span data-ttu-id="66e06-112">Uma / pools V Conferencing Server são os únicos que eles não precisam balanceadores de carga para criar um pool.</span><span class="sxs-lookup"><span data-stu-id="66e06-112">A/V Conferencing Server pools are unique in that they do not need load balancers to create a pool.</span></span> <span data-ttu-id="66e06-113">Uma / pools de conferência V internamente o balanceamento de carga e não é necessário hardware adicional.</span><span class="sxs-lookup"><span data-stu-id="66e06-113">A/V Conferencing pools load balance internally and do not need additional hardware.</span></span> 
  

