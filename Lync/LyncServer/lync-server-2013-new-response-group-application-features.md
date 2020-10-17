---
title: 'Lync Server 2013: novos recursos do aplicativo de grupo de resposta'
description: 'Lync Server 2013: novos recursos do aplicativo de grupo de resposta.'
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
ms.openlocfilehash: 191d3867758da427ade3470e78abfd417f6f00de
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48541957"
---
# <a name="new-response-group-application-features-in-lync-server-2013"></a><span data-ttu-id="bd958-103">Novos recursos do aplicativo de grupo de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd958-103">New Response Group application features in Lync Server 2013</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="bd958-104">_**Última modificação do tópico:** 2012-10-29_</span><span class="sxs-lookup"><span data-stu-id="bd958-104">_**Topic Last Modified:** 2012-10-29_</span></span>

<span data-ttu-id="bd958-105">O aplicativo Grupo de Resposta permite rotear e enfileirar chamadas de entrada para pessoas designadas para finalidades especiais, tais como serviço de cliente, uma assistência técnica interna, ou suporte de telefone geral para um departamento.</span><span class="sxs-lookup"><span data-stu-id="bd958-105">With the Response Group application, you can route and queue incoming calls to designated persons for special purposes, such as customer service, an internal help desk, or general telephone support for a department.</span></span>

<span data-ttu-id="bd958-106">Os seguintes recursos do aplicativo de grupo de resposta são novos no Lync Server 2013:</span><span class="sxs-lookup"><span data-stu-id="bd958-106">The following Response Group application features are new in Lync Server 2013:</span></span>

  - <span data-ttu-id="bd958-107">**Função do Gerenciador**</span><span class="sxs-lookup"><span data-stu-id="bd958-107">**Manager role**</span></span>
    
    <span data-ttu-id="bd958-108">O Lync Server 2013 introduz uma nova função de gerente de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="bd958-108">Lync Server 2013 introduces a new Response Group Manager role.</span></span> <span data-ttu-id="bd958-109">Agora há duas funções de gerenciamento para grupos de resposta: gerente de grupo de resposta e administrador de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="bd958-109">Now there are two management roles for response groups: Response Group Manager and Response Group Administrator.</span></span> <span data-ttu-id="bd958-110">Embora os administradores do grupo de resposta ainda possam configurar qualquer elemento para qualquer grupo de resposta, os gerentes podem configurar apenas determinados elementos, apenas para os grupos de resposta que eles possuem.</span><span class="sxs-lookup"><span data-stu-id="bd958-110">While Response Group Administrators can still configure any element for any response group, Managers can configure only certain elements, only for response groups they own.</span></span>
    
    <span data-ttu-id="bd958-111">Essa melhoria no modelo de administração beneficia a escalabilidade do Grupo de respostas, especialmente para os cenários de implantação de grande porte.</span><span class="sxs-lookup"><span data-stu-id="bd958-111">This improvement in the administration model benefits Response Group scalability, especially for large deployment scenarios.</span></span>

  - <span data-ttu-id="bd958-112">**Alta disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="bd958-112">**High availability**</span></span>
    
    <span data-ttu-id="bd958-113">O suporte de alta disponibilidade para o aplicativo de grupo de resposta, na forma de espelhamento do SQL Server, é habilitado como parte da configuração geral e da implantação de alta disponibilidade do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd958-113">High availability support for the Response Group application, in the form of SQL Server mirroring, is enabled as part of the overall configuration and deployment of high availability for Lync Server 2013.</span></span> <span data-ttu-id="bd958-114">Se você configurar a alta disponibilidade e perder a conectividade com o servidor Back-End primário, a função Grupo de respostas não seja afetada pelo aproveitamento do servidor Back-End espelhado.</span><span class="sxs-lookup"><span data-stu-id="bd958-114">If you configure for high availability and lose connectivity to the primary back-end server, Response Group functionality is not affected by leveraging the mirrored back-end server.</span></span>
    
    <span data-ttu-id="bd958-115">O suporte para espelhamento do SQL Server para o aplicativo de grupo de resposta não pode ser habilitado individualmente ou configurado fora da configuração geral de alta disponibilidade do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bd958-115">Support for SQL Server mirroring for the Response Group application can’t be individually enabled or configured outside of the overall Lync Server 2013 high availability configuration.</span></span>

  - <span data-ttu-id="bd958-116">**Recuperação de desastres**</span><span class="sxs-lookup"><span data-stu-id="bd958-116">**Disaster recovery**</span></span>
    
    <span data-ttu-id="bd958-117">O suporte à recuperação de desastres para o aplicativo grupo de resposta é habilitado como parte da configuração e implantação dos pools de front-ends emparelhados, que fazem parte da configuração de recuperação de desastres do Lync Server 2013 geral.</span><span class="sxs-lookup"><span data-stu-id="bd958-117">Disaster recovery support for the Response Group application is enabled as part of the configuration and deployment of the paired Front End pools, which are part of the overall Lync Server 2013 disaster recovery configuration.</span></span> <span data-ttu-id="bd958-118">Além disso, os cmdlets de importação e exportação do Grupo de respostas suportam o processo de failover para o pool de backup e o processo de failback para o pool primário ou para um novo pool.</span><span class="sxs-lookup"><span data-stu-id="bd958-118">In addition, Response Group import and export cmdlets support the failover process to the backup pool and the failback process to the primary pool or to a new pool.</span></span> <span data-ttu-id="bd958-119">Se uma interrupção ocorrer no pool primário, os grupos de respostas podem ser transferidos para o pool de backup e, em seguida, voltarem a funcionar no pool primário ou em um novo pool no qual a interrupção tenha terminado.</span><span class="sxs-lookup"><span data-stu-id="bd958-119">If an outage occurs in the primary pool, response groups can be failed over to the backup pool, and then failed back to the primary pool or to a new pool when the outage is over.</span></span>

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a><span data-ttu-id="bd958-120">Confira também</span><span class="sxs-lookup"><span data-stu-id="bd958-120">See Also</span></span>


[<span data-ttu-id="bd958-121">Planejamento de grupos de resposta no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="bd958-121">Planning for response groups in Lync Server 2013</span></span>](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

