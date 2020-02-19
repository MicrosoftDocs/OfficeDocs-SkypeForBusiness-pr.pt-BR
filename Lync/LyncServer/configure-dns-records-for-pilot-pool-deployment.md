---
title: Configurar registros DNS para implantação do pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: eb421bad-4bf1-4837-a077-7795094692d9
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ721921(v=OCS.15)
ms:contentKeyID: 49733855
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 549aa706700d7f2163e9149d8dd29311141968e0
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136398"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="0f1b4-102">Configurar registros DNS para implantação do pool piloto</span><span class="sxs-lookup"><span data-stu-id="0f1b4-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="0f1b4-103">_**Última modificação do tópico:** 2012-09-29_</span><span class="sxs-lookup"><span data-stu-id="0f1b4-103">_**Topic Last Modified:** 2012-09-29_</span></span>

<span data-ttu-id="0f1b4-104">Antes de implantar o pool piloto do Lync Server 2013, você deve atualizar as entradas do host DNS a para o pool piloto.</span><span class="sxs-lookup"><span data-stu-id="0f1b4-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="0f1b4-105">Para concluir com êxito este procedimento, você deverá estar conectado no servidor ou domínio como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="0f1b4-105">To successfully complete this procedure, you should be logged on to the server or domain as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="0f1b4-106">**Para configurar os registros de DNS Host A**</span><span class="sxs-lookup"><span data-stu-id="0f1b4-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="0f1b4-107">No servidor DNS (Sistema de Nomes de Domínio), clique em **Iniciar**, em **Ferramentas Administrativas** e em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="0f1b4-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="0f1b4-108">Na árvore do console do seu domínio, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Lync Server 2013 será instalado.</span><span class="sxs-lookup"><span data-stu-id="0f1b4-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="0f1b4-109">Clique em **Novo Host (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="0f1b4-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="0f1b4-110">Clique em **nome**, digite o nome do host para o pool do Lync Server 2013 (o nome do domínio é considerado da zona em que o registro está definido e não precisa ser inserido como parte do registro a).</span><span class="sxs-lookup"><span data-stu-id="0f1b4-110">Click **Name**, type the host name for the Lync Server 2013 pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="0f1b4-111">Clique em **endereço IP**, digite o endereço IP do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="0f1b4-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="0f1b4-112">Clique em **Adicionar Host** e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="0f1b4-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="0f1b4-113">Quando tiver terminado, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="0f1b4-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

