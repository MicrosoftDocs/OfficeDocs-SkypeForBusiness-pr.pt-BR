---
title: Configurar registros DNS para implantação do pool piloto
ms.reviewer: ''
ms.author: kenwith
author: kenwith
audience: Admin
f1.keywords:
- NOCSH
TOCTitle: Configure DNS records for pilot pool deployment
ms:assetid: 5c7a6e10-e1e9-4479-9bf9-d4a3e2e09ff0
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ688072(v=OCS.15)
ms:contentKeyID: 49733666
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: fd9ae4eff928413838fc014a125b681aa15f0def
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "41998996"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configure-dns-records-for-pilot-pool-deployment"></a><span data-ttu-id="94acc-102">Configurar registros DNS para implantação do pool piloto</span><span class="sxs-lookup"><span data-stu-id="94acc-102">Configure DNS records for pilot pool deployment</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="94acc-103">_**Última modificação do tópico:** 2012-09-24_</span><span class="sxs-lookup"><span data-stu-id="94acc-103">_**Topic Last Modified:** 2012-09-24_</span></span>

<span data-ttu-id="94acc-104">Antes de implantar o pool piloto do Lync Server 2013, você deve atualizar as entradas do host DNS a para o pool piloto.</span><span class="sxs-lookup"><span data-stu-id="94acc-104">Prior to deploying the Lync Server 2013 pilot pool, you must update the DNS Host A entries for the pilot pool.</span></span> <span data-ttu-id="94acc-105">Para concluir com êxito este procedimento, você deve estar conectado no servidor ou domínio no mínimo como um membro do grupo de Administradores de Domínio ou membro do grupo DnsAdmins.</span><span class="sxs-lookup"><span data-stu-id="94acc-105">To successfully complete this procedure, you should be logged on to the server or domain at minimum as a member of the Domain Admins group or a member of the DnsAdmins group.</span></span>

<span data-ttu-id="94acc-106">**Para configurar registros do Host DNS A**</span><span class="sxs-lookup"><span data-stu-id="94acc-106">**To configure DNS Host A records**</span></span>

1.  <span data-ttu-id="94acc-107">No servidor DNS (Sistema de Nomes de Domínio), clique em **Iniciar**, em **Ferramentas Administrativas** e em **DNS**.</span><span class="sxs-lookup"><span data-stu-id="94acc-107">On the Domain Name System (DNS) server, click **Start**, click **Administrative Tools**, and then click **DNS**.</span></span>

2.  <span data-ttu-id="94acc-108">Na árvore do console do seu domínio, expanda **zonas de pesquisa direta**e clique com o botão direito do mouse no domínio no qual o Lync Server 2013 será instalado.</span><span class="sxs-lookup"><span data-stu-id="94acc-108">In the console tree for your domain, expand **Forward Lookup Zones**, and then right-click the domain in which Lync Server 2013 will be installed.</span></span>

3.  <span data-ttu-id="94acc-109">Clique em **Novo Host (A ou AAAA)**.</span><span class="sxs-lookup"><span data-stu-id="94acc-109">Click **New Host (A or AAAA)**.</span></span>

4.  <span data-ttu-id="94acc-110">Clique em **Nome**, digite o nome do host para o pool (o nome de domínio é considerado da zona na qual o registro está definido e não precisa ser inserida como parte do registro A).</span><span class="sxs-lookup"><span data-stu-id="94acc-110">Click **Name**, type the host name for the pool (the domain name is assumed from the zone that the record is defined in and does not need to be entered as part of the A record).</span></span>

5.  <span data-ttu-id="94acc-111">Clique em **endereço IP**, digite o endereço IP do pool de front-ends.</span><span class="sxs-lookup"><span data-stu-id="94acc-111">Click **IP Address**, type the IP address for the Front End pool.</span></span>

6.  <span data-ttu-id="94acc-112">Clique em **Adicionar Host** e depois clique em **OK**.</span><span class="sxs-lookup"><span data-stu-id="94acc-112">Click **Add Host**, and then click **OK**.</span></span>

7.  <span data-ttu-id="94acc-113">Quando tiver terminado, clique em **Concluído**.</span><span class="sxs-lookup"><span data-stu-id="94acc-113">When you are finished, click **Done**.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

