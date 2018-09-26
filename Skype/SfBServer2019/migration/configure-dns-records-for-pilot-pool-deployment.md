---
title: Configurar registros de DNS para implantação de pool piloto
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Antes de implantar o pool piloto, você deve atualizar as entradas de DNS Host A para o pool piloto. Para concluir este procedimento, você deve estar conectado ao servidor ou domínio como membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.
ms.openlocfilehash: 13492f7972e127de7a8200a0dbe933c72aba2da7
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25029892"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="47fc5-104">Configurar registros de DNS para implantação de pool piloto</span><span class="sxs-lookup"><span data-stu-id="47fc5-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="47fc5-105">Antes de implantar o pool piloto, você deve atualizar as entradas de DNS Host A para o pool piloto.</span><span class="sxs-lookup"><span data-stu-id="47fc5-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="47fc5-106">Para concluir este procedimento, você deve estar conectado ao servidor ou domínio como membro do grupo Administradores de domínio ou membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="47fc5-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="47fc5-107">Para configurar os registros do Host DNS</span><span class="sxs-lookup"><span data-stu-id="47fc5-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="47fc5-108">No servidor de sistema de nome de domínio (DNS), clique em **Iniciar**, clique em **Ferramentas administrativas**e clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="47fc5-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="47fc5-109">Na árvore de console para seu domínio, expanda **Zonas de pesquisa direta**e, em seguida, clique com botão direito do domínio no qual Skype para Business Server 2019 será instalado.</span><span class="sxs-lookup"><span data-stu-id="47fc5-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="47fc5-110">Clique em **Novo Host (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="47fc5-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="47fc5-111">Clique em **nome**, digite o nome de host para o Skype para pool Business Server 2019 (o nome de domínio é suposto a partir da zona que o registro é definido no e não precisa ser inserido como parte do registro).</span><span class="sxs-lookup"><span data-stu-id="47fc5-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="47fc5-112">Clique em **Endereço IP**e digite o endereço IP para o pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="47fc5-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="47fc5-113">Clique em **Adicionar Host**e, em seguida, clique em **Okey**.</span><span class="sxs-lookup"><span data-stu-id="47fc5-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="47fc5-114">Quando terminar, clique em **concluído**.</span><span class="sxs-lookup"><span data-stu-id="47fc5-114">When you are finished, click **Done**.</span></span>
    

