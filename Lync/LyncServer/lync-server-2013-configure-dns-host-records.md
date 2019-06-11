---
title: 'Lync Server 2013: Configurar registros de Host DNS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: ac3bb3c771d99e56e0c584675d77a92d95fdd757
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836386"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="e34fc-102">Configurar registros de Host DNS para Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e34fc-102">Configure DNS Host records for Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e34fc-103">_**Tópico da última modificação:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="e34fc-103">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="e34fc-104">Para concluir esse procedimento com êxito, você deve estar conectado ao servidor ou domínio no mínimo como membro do grupo Domain admins ou um membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="e34fc-104">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="e34fc-105">Para configurar registros do host DNS A</span><span class="sxs-lookup"><span data-stu-id="e34fc-105">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="e34fc-106">No servidor DNS (sistema de nomes de domínio), clique em **Iniciar**, clique em **Ferramentas administrativas**e clique em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="e34fc-106">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="e34fc-107">Na árvore de console do seu domínio, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Lync Server 2013 será instalado.</span><span class="sxs-lookup"><span data-stu-id="e34fc-107">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="e34fc-108">Clique em **novo host (A ou aaaa)**.</span><span class="sxs-lookup"><span data-stu-id="e34fc-108">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="e34fc-109">Clique em **nome**, digite o nome do host do pool (o nome do domínio é presumido na zona em que o registro é definido e não precisa ser inserido como parte do registro a).</span><span class="sxs-lookup"><span data-stu-id="e34fc-109">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="e34fc-110">Clique em **endereço IP**, digite o IP virtual (VIP) do balanceador de carga do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="e34fc-110">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="e34fc-111">Em implantações que usam um pool de directors, os registros de host (A) para as URLs simples devem apontar para o VIP do balanceador de carga do diretor.</span><span class="sxs-lookup"><span data-stu-id="e34fc-111">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="e34fc-112">Se você implantar apenas um servidor ou diretor da Enterprise Edition que esteja conectado à topologia sem um balanceador de carga ou se implantar um servidor Standard Edition, digite o endereço IP do servidor Enterprise Edition, do servidor Standard Edition ou do director.</span><span class="sxs-lookup"><span data-stu-id="e34fc-112">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director.</span></span> <span data-ttu-id="e34fc-113">Um balanceador de carga será necessário se você implantar mais de um servidor ou diretor Enterprise Edition em um pool.</span><span class="sxs-lookup"><span data-stu-id="e34fc-113">A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool.</span></span> <span data-ttu-id="e34fc-114">Balanceadores de carga não são usados com servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="e34fc-114">Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="e34fc-115">Clique em **Adicionar host**e, em seguida, clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="e34fc-115">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="e34fc-116">Para criar um registro adicional adicional, repita as etapas 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="e34fc-116">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="e34fc-117">Quando terminar de criar todos os registros necessários, clique em **concluído**.</span><span class="sxs-lookup"><span data-stu-id="e34fc-117">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

