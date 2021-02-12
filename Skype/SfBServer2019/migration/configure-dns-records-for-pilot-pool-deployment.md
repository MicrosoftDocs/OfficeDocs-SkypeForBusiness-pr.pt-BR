---
title: Configurar os registros DNS para a implantação do pool piloto
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Antes de implantar o pool piloto, você deve atualizar as entradas do Host DNS A para o pool piloto. Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.
ms.openlocfilehash: d934e3bdc46ab9deffa3c588b15ab793111c1a68
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44754051"
---
# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="34d94-104">Configurar os registros DNS para a implantação do pool piloto</span><span class="sxs-lookup"><span data-stu-id="34d94-104">Configure DNS records for pilot pool deployment</span></span>

<span data-ttu-id="34d94-105">Antes de implantar o pool piloto, você deve atualizar as entradas do Host DNS A para o pool piloto.</span><span class="sxs-lookup"><span data-stu-id="34d94-105">Before deploying the pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="34d94-106">Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="34d94-106">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>
  
### <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="34d94-107">Para configurar os registros de DNS Host A</span><span class="sxs-lookup"><span data-stu-id="34d94-107">To configure DNS Host A records</span></span>

1. <span data-ttu-id="34d94-108">No servidor DNS (Sistema de Nomes de Domínio), clique em **Iniciar**, em **Ferramentas Administrativas** e em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="34d94-108">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>
    
2. <span data-ttu-id="34d94-109">Na árvore de console do seu domínio, expanda **Zonas** de Busca Encaminhar e clique com o botão direito do mouse no domínio no qual o Skype for Business Server 2019 será instalado.</span><span class="sxs-lookup"><span data-stu-id="34d94-109">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Skype for Business Server 2019 will be installed.</span></span>
    
3. <span data-ttu-id="34d94-110">Clique em **Novo Host (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="34d94-110">Click **New Host (A or AAAA)**.</span></span>
    
4. <span data-ttu-id="34d94-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span><span class="sxs-lookup"><span data-stu-id="34d94-111">Click **Name**, type the host name for the Skype for Business Server 2019 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>
    
5. <span data-ttu-id="34d94-112">Clique **no endereço IP** e digite o endereço IP do pool de Front-End.</span><span class="sxs-lookup"><span data-stu-id="34d94-112">Click **IP Address**, and then type the IP address for the Front End pool.</span></span>
    
6. <span data-ttu-id="34d94-113">Clique em **Adicionar Host** e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="34d94-113">Click **Add Host**, and then click **OK**.</span></span> 
    
7. <span data-ttu-id="34d94-114">Quando tiver terminado, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="34d94-114">When you are finished, click **Done**.</span></span>
    

