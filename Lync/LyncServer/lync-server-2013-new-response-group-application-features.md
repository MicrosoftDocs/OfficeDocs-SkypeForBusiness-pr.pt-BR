---
title: 'Lync Server 2013: Novos recursos do aplicativo de Grupo de Resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: New Response Group application features
ms:assetid: 569544b4-fa97-429b-97e6-568afab6c19b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398373(v=OCS.15)
ms:contentKeyID: 48184196
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: bddf1f670ef2a0a246100564962b2f69db741186
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755895"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="e7894-102">Novos recursos do aplicativo de Grupo de Resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7894-102">New Response Group application features in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="e7894-103">_**Tópico da última modificação:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="e7894-103">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="e7894-104">Com o aplicativo de grupo de resposta, você pode encaminhar e enfileirar chamadas de entrada para pessoas designadas para fins especiais, como atendimento ao cliente, um suporte técnico interno ou suporte geral por telefone para um departamento.</span><span class="sxs-lookup"><span data-stu-id="e7894-104">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="e7894-105">Os seguintes recursos de aplicativo de grupo de resposta são novos no Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="e7894-105">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="e7894-106">**Função gerente**</span><span class="sxs-lookup"><span data-stu-id="e7894-106">**Manager role**</span></span>
    
    <span data-ttu-id="e7894-107">O Lync Server 2013 introduz uma nova função de gerente do grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="e7894-107">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="e7894-108">Agora há duas funções de gerenciamento para grupos de resposta: gerente de grupo de resposta e administrador de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="e7894-108">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="e7894-109">Embora os administradores de grupo de resposta ainda possam configurar qualquer elemento para qualquer grupo de resposta, os gerentes podem configurar apenas determinados elementos, somente para os grupos de resposta que eles possuem.</span><span class="sxs-lookup"><span data-stu-id="e7894-109">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="e7894-110">Esse aprimoramento no modelo de administração beneficia a escalabilidade do grupo de resposta, especialmente para grandes cenários de implantação.</span><span class="sxs-lookup"><span data-stu-id="e7894-110">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="e7894-111">**Alta disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="e7894-111">**High availability**</span></span>
    
    <span data-ttu-id="e7894-112">O suporte de alta disponibilidade para o aplicativo de grupo de resposta, na forma de espelhamento do SQL Server, é habilitado como parte da configuração e implantação gerais de alta disponibilidade do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e7894-112">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="e7894-113">Se você configurar para alta disponibilidade e perder a conectividade com o servidor back-end primário, a funcionalidade do grupo de resposta não será afetada por meio do uso do servidor back-end espelhado.</span><span class="sxs-lookup"><span data-stu-id="e7894-113">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="e7894-114">O suporte para o espelhamento do SQL Server para o aplicativo do grupo de resposta não pode ser habilitado ou configurado individualmente fora da configuração geral do Lync Server 2013 de alta disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="e7894-114">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="e7894-115">**Recuperação de desastres**</span><span class="sxs-lookup"><span data-stu-id="e7894-115">**Disaster recovery**</span></span>
    
    <span data-ttu-id="e7894-116">O suporte à recuperação de desastres do aplicativo de grupo de resposta é habilitado como parte da configuração e implantação dos pools front-end emparelhados, que fazem parte da configuração de recuperação de desastres do Lync Server 2013 geral.</span><span class="sxs-lookup"><span data-stu-id="e7894-116">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="e7894-117">Além disso, os cmdlets de importação e exportação do grupo de resposta dão suporte ao processo de failover para o pool de backup e o processo de failback para o pool primário ou para um novo pool.</span><span class="sxs-lookup"><span data-stu-id="e7894-117">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="e7894-118">Se ocorrer uma falha no pool primário, os grupos de resposta poderão fazer failover para o pool de backup e, em seguida, retornar ao pool primário ou a um novo pool quando a interrupção for terminada.</span><span class="sxs-lookup"><span data-stu-id="e7894-118">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="e7894-119">Confira também</span><span class="sxs-lookup"><span data-stu-id="e7894-119">See Also</span></span>


[<span data-ttu-id="e7894-120">Planejamento de grupos de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="e7894-120">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

