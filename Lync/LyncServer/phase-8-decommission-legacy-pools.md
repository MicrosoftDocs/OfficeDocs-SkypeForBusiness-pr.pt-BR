---
title: 'Fase 8: encerrar pools herdados'
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: 'Phase 8: Decommission legacy pools'
ms:assetid: 1c68e5d8-fb5f-45e6-b6e3-27f5e830c966
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204724(v=OCS.15)
ms:contentKeyID: 48183557
ms.date: 12/29/2016
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6450e129d68aadcb0e79f38def3e89176ef93373
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42034141"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="phase-8-decommission-legacy-pools"></a><span data-ttu-id="d792a-102">Fase 8: encerrar pools herdados</span><span class="sxs-lookup"><span data-stu-id="d792a-102">Phase 8: Decommission legacy pools</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="d792a-103">_**Última modificação do tópico:** 2016-12-08_</span><span class="sxs-lookup"><span data-stu-id="d792a-103">_**Topic Last Modified:** 2016-12-08_</span></span>

<span data-ttu-id="d792a-104">O tópico a seguir fornece orientações sobre como atualizar entradas DNS, mover o servidor de gerenciamento de conteúdo, encerrar pools e desativar e remover servidores e pools de uma implantação herdada do Lync Server 2010.</span><span class="sxs-lookup"><span data-stu-id="d792a-104">The following topic provides guidance in updating DNS entries, moving the Content Management Server, decommissioning pools, and deactivating and removing servers and pools from a legacy deployment of Lync Server 2010.</span></span> <span data-ttu-id="d792a-105">Nem todos os procedimentos listados nesta seção são obrigatórios.</span><span class="sxs-lookup"><span data-stu-id="d792a-105">Not all of the procedures listed in this section are required.</span></span> <span data-ttu-id="d792a-106">Leia a documentação e determine qual procedimento de descomissionamento usar.</span><span class="sxs-lookup"><span data-stu-id="d792a-106">Read the documentation and determine which decommissioning procedure to use.</span></span>

<span data-ttu-id="d792a-107">Para obter uma cobertura exaustiva da remoção de servidores e funções de servidor do Lync Server 2010 e um guia passo a passo para encerrar uma implantação do Lync Server 2010, consulte "Desinstalando o Microsoft Lync Server 2010 e removendo funções de servidor", que [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227)pode ser baixado em.</span><span class="sxs-lookup"><span data-stu-id="d792a-107">For exhaustive coverage of removing Lync Server 2010 servers and server roles, and a step-by-step guide to decommissioning a Lync Server 2010 deployment, see "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

<div>


> [!IMPORTANT]  
> <span data-ttu-id="d792a-108">Para obter informações sobre a migração e atualização de aplicativos do Microsoft Unified Communications Managed API (UCMA), antes de encerrar seu ambiente herdado, consulte<A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span><span class="sxs-lookup"><span data-stu-id="d792a-108">For information on migrating and upgrading Microsoft Unified Communications Managed API (UCMA) applications, prior to decommissioning your legacy environment, see <A href="https://go.microsoft.com/fwlink/p/?linkid=269555">https://go.microsoft.com/fwlink/p/?LinkId=269555</A></span></span>



</div>

<div>

## <a name="in-this-section"></a><span data-ttu-id="d792a-109">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="d792a-109">In This Section</span></span>

  - <span></span>  
    [<span data-ttu-id="d792a-110">Atualizar registros SRV DNS</span><span class="sxs-lookup"><span data-stu-id="d792a-110">Update DNS SRV records</span></span>](update-dns-srv-records.md)

  - <span></span>  
    [<span data-ttu-id="d792a-111">Mover o servidor de gerenciamento central do Lync Server 2010 para o Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="d792a-111">Move the Lync Server 2010 Central Management Server to Lync Server 2013</span></span>](move-the-lync-server-2010-central-management-server-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="d792a-112">Mover diretórios de conferência</span><span class="sxs-lookup"><span data-stu-id="d792a-112">Move Conference Directories</span></span>](move-lync-server-2010-conference-directories-to-lync-server-2013.md)

  - <span></span>  
    [<span data-ttu-id="d792a-113">Remover a associação do servidor de arquivamento</span><span class="sxs-lookup"><span data-stu-id="d792a-113">Remove the Archiving server association</span></span>](remove-the-archiving-server-association.md)

  - <span></span>  
    [<span data-ttu-id="d792a-114">Remover a associação do Monitoring Server</span><span class="sxs-lookup"><span data-stu-id="d792a-114">Remove the Monitoring server association</span></span>](remove-the-monitoring-server-association.md)

  - <span></span>  
    [<span data-ttu-id="d792a-115">Remover o servidor front-end Enterprise Edition ou o servidor front-end Standard Edition</span><span class="sxs-lookup"><span data-stu-id="d792a-115">Remove the Enterprise Edition Front End Server or Standard Edition Front End Server</span></span>](remove-the-enterprise-edition-front-end-server-or-standard-edition-front-end-server.md)

  - <span></span>  
    [<span data-ttu-id="d792a-116">Remover instâncias e bancos de dados do SQL Server no servidor back-end</span><span class="sxs-lookup"><span data-stu-id="d792a-116">Remove SQL Server instances and databases on the Back End Server</span></span>](remove-sql-server-instances-and-databases-on-the-back-end-server.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

