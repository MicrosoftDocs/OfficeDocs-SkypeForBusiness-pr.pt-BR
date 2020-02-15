---
title: 'Lync Server 2013: novos recursos do aplicativo de grupo de resposta'
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
ms.openlocfilehash: f98261aaf40413c52598465338c9c198aca435f9
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42048305"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Novos recursos do aplicativo de grupo de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-29_

O aplicativo Grupo de Resposta permite rotear e enfileirar chamadas de entrada para pessoas designadas para finalidades especiais, tais como serviço de cliente, uma assistência técnica interna, ou suporte de telefone geral para um departamento.

Os seguintes recursos do aplicativo de grupo de resposta são novos no Lync Server 2013:

  - **Função do Gerenciador**
    
    O Lync Server 2013 introduz uma nova função de gerente de grupo de resposta. Agora há duas funções de gerenciamento para grupos de resposta: gerente de grupo de resposta e administrador de grupo de resposta. Embora os administradores do grupo de resposta ainda possam configurar qualquer elemento para qualquer grupo de resposta, os gerentes podem configurar apenas determinados elementos, apenas para os grupos de resposta que eles possuem.
    
    Essa melhoria no modelo de administração beneficia a escalabilidade do Grupo de respostas, especialmente para os cenários de implantação de grande porte.

  - **Alta disponibilidade**
    
    O suporte de alta disponibilidade para o aplicativo de grupo de resposta, na forma de espelhamento do SQL Server, é habilitado como parte da configuração geral e da implantação de alta disponibilidade do Lync Server 2013. Se você configurar a alta disponibilidade e perder a conectividade com o servidor Back-End primário, a função Grupo de respostas não seja afetada pelo aproveitamento do servidor Back-End espelhado.
    
    O suporte para espelhamento do SQL Server para o aplicativo de grupo de resposta não pode ser habilitado individualmente ou configurado fora da configuração geral de alta disponibilidade do Lync Server 2013.

  - **Recuperação de desastres**
    
    O suporte à recuperação de desastres para o aplicativo grupo de resposta é habilitado como parte da configuração e implantação dos pools de front-ends emparelhados, que fazem parte da configuração de recuperação de desastres do Lync Server 2013 geral. Além disso, os cmdlets de importação e exportação do Grupo de respostas suportam o processo de failover para o pool de backup e o processo de failback para o pool primário ou para um novo pool. Se uma interrupção ocorrer no pool primário, os grupos de respostas podem ser transferidos para o pool de backup e, em seguida, voltarem a funcionar no pool primário ou em um novo pool no qual a interrupção tenha terminado.

<div id="sectionSection0" class="section">

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de grupos de resposta no Lync Server 2013](lync-server-2013-planning-for-response-groups.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

