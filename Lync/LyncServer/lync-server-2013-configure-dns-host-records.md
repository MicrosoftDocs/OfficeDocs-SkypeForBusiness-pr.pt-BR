---
title: 'Lync Server 2013: Configurar registros de host DNS'
description: 'Lync Server 2013: Configurar registros de host DNS.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS Host records
ms:assetid: 78a1afcf-41c8-4da5-8740-c6570c19078c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398593(v=OCS.15)
ms:contentKeyID: 48184577
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7fd403402d0d2f089d7fc92a62296a56df0cf2e6
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48553427"
---
# <a name="configure-dns-host-records-for-lync-server-2013"></a><span data-ttu-id="53c71-103">Configurar registros de host DNS para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="53c71-103">Configure DNS Host records for Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="53c71-104">_**Última modificação do tópico:** 2012-10-01_</span><span class="sxs-lookup"><span data-stu-id="53c71-104">_**Topic Last Modified:** 2012-10-01_</span></span>

<span data-ttu-id="53c71-105">Para concluir com êxito este procedimento, você deve estar conectado no servidor ou domínio no mínimo como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="53c71-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<div>

## <a name="to-configure-dns-host-a-records"></a><span data-ttu-id="53c71-106">Para configurar registros do Host DNS A</span><span class="sxs-lookup"><span data-stu-id="53c71-106">To configure DNS Host A records</span></span>

1.  <span data-ttu-id="53c71-107">No servidor DNS (Sistema de Nomes de Domínio), clique em **Iniciar**, em **Ferramentas Administrativas** e em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="53c71-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="53c71-108">Na árvore do console do seu domínio, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Lync Server 2013 será instalado.</span><span class="sxs-lookup"><span data-stu-id="53c71-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="53c71-109">Clique em **Novo Host (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="53c71-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="53c71-110">Clique em **Nome**, digite o nome do host para o pool (o nome de domínio é considerado da zona na qual o registro está definido e não precisa ser inserida como parte do registro A).</span><span class="sxs-lookup"><span data-stu-id="53c71-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="53c71-111">Clique em **endereço IP**, digite o IP virtual (VIP) do balanceador de carga para o pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="53c71-111">Click **IP Address**, type the virtual IP (VIP) of the load balancer for the Front End pool.</span></span>
    
    <div>
    

    > [!IMPORTANT]  
    > <span data-ttu-id="53c71-112">Nas implantações que usam um pool do Diretor, os registros do host (A) para URLs simples devem apontar para o VIP do balanceador de carga do Diretor.</span><span class="sxs-lookup"><span data-stu-id="53c71-112">In deployments that use a Director pool, the host (A) records for the simple URLs should point to the VIP of the Director load balancer.</span></span>

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > <span data-ttu-id="53c71-p101">Se você implantar apenas um servidor Enterprise Edition ou Diretor que esteja conectado à topologia sem um balanceador de carga, ou se você implantar um servidor Standard Edition, digite o endereço IP do servidor Enterprise Edition, o servidor Standard Edition ou o Diretor. Um balanceador de carga será necessário se você implantar mais de um servidor Enterprise Edition ou Diretor em um pool. Os balanceadores de carga não são usados com servidores Standard Edition.</span><span class="sxs-lookup"><span data-stu-id="53c71-p101">If you deploy only one Enterprise Edition server or Director that is connected to the topology without a load balancer, or if you deploy a Standard Edition server, type the IP address of the Enterprise Edition server, Standard Edition server, or Director. A load balancer is required if you deploy more than one Enterprise Edition server or Director in a pool. Load balancers are not used with Standard Edition servers.</span></span>

    
    </div>

6.  <span data-ttu-id="53c71-116">Clique em **Adicionar Host** e em **OK**.</span><span class="sxs-lookup"><span data-stu-id="53c71-116">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="53c71-117">Para criar um registro A adicional, repita as etapas 4 e 5.</span><span class="sxs-lookup"><span data-stu-id="53c71-117">To create an additional A record, repeat steps 4 and 5.</span></span>

8.  <span data-ttu-id="53c71-118">Após criar todos os registros A necessários, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="53c71-118">When you are finished creating all the A records that you need, click **Done**.</span></span>

</div>

</div>

<span> </span>

</div>

</div>

</div>

