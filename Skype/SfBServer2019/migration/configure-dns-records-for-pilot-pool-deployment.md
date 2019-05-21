---
title: Configurar registros de DNS para implantação de pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implantar o pool piloto, você deve atualizar as entradas do host DNS a para o pool piloto. Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou ao domínio como membro do grupo Domain admins ou de um membro do grupo DnsAdmins.
ms.openlocfilehash: 3b8485564f3ea7f37a06b5c4d13c9450ba0a2694
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34289620"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="ed993-104">Configurar registros de DNS para implantação de pool piloto</span><span class="sxs-lookup"><span data-stu-id="ed993-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="ed993-105">Antes de implantar o pool piloto, você deve atualizar as entradas do host DNS a para o pool piloto.</span><span class="sxs-lookup"><span data-stu-id="ed993-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="ed993-106">Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou ao domínio como membro do grupo Domain admins ou de um membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="ed993-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="ed993-107">Para configurar registros do host DNS A</span><span class="sxs-lookup"><span data-stu-id="ed993-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="ed993-108">No servidor DNS (sistema de nomes de domínio), clique em **Iniciar**, clique em **Ferramentas administrativas**e clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="ed993-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="ed993-109">Na árvore de console do seu domínio, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Skype for Business Server 2019 será instalado.</span><span class="sxs-lookup"><span data-stu-id="ed993-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="ed993-110">Clique em **novo host (A ou aaaa)**.</span><span class="sxs-lookup"><span data-stu-id="ed993-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="ed993-111">Clique em **nome**, digite o nome do host do pool do Skype for Business Server 2019 (o nome do domínio é presumido na zona em que o registro é definido e não precisa ser inserido como parte do registro a).</span><span class="sxs-lookup"><span data-stu-id="ed993-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="ed993-112">Clique em **endereço IP**e digite o endereço IP do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="ed993-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="ed993-113">Clique em **Adicionar host**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="ed993-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="ed993-114">Quando terminar, clique em **concluído**.</span><span class="sxs-lookup"><span data-stu-id="ed993-114">When you are finished, click **Done**.</span></span>
    

