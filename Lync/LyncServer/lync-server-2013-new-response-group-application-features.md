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

# <a name="new-response-group-application-features-in-lync-server-2013"></a>Novos recursos do aplicativo de Grupo de Resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-29_

Com o aplicativo de grupo de resposta, você pode encaminhar e enfileirar chamadas de entrada para pessoas designadas para fins especiais, como atendimento ao cliente, um suporte técnico interno ou suporte geral por telefone para um departamento.

Os seguintes recursos de aplicativo de grupo de resposta são novos no Lync Server 2013:

  - **Função gerente**
    
    O Lync Server 2013 introduz uma nova função de gerente do grupo de resposta. Agora há duas funções de gerenciamento para grupos de resposta: gerente de grupo de resposta e administrador de grupo de resposta. Embora os administradores de grupo de resposta ainda possam configurar qualquer elemento para qualquer grupo de resposta, os gerentes podem configurar apenas determinados elementos, somente para os grupos de resposta que eles possuem.
    
    Esse aprimoramento no modelo de administração beneficia a escalabilidade do grupo de resposta, especialmente para grandes cenários de implantação.

  - **Alta disponibilidade**
    
    O suporte de alta disponibilidade para o aplicativo de grupo de resposta, na forma de espelhamento do SQL Server, é habilitado como parte da configuração e implantação gerais de alta disponibilidade do Lync Server 2013. Se você configurar para alta disponibilidade e perder a conectividade com o servidor back-end primário, a funcionalidade do grupo de resposta não será afetada por meio do uso do servidor back-end espelhado.
    
    O suporte para o espelhamento do SQL Server para o aplicativo do grupo de resposta não pode ser habilitado ou configurado individualmente fora da configuração geral do Lync Server 2013 de alta disponibilidade.

  - **Recuperação de desastres**
    
    O suporte à recuperação de desastres do aplicativo de grupo de resposta é habilitado como parte da configuração e implantação dos pools front-end emparelhados, que fazem parte da configuração de recuperação de desastres do Lync Server 2013 geral. Além disso, os cmdlets de importação e exportação do grupo de resposta dão suporte ao processo de failover para o pool de backup e o processo de failback para o pool primário ou para um novo pool. Se ocorrer uma falha no pool primário, os grupos de resposta poderão fazer failover para o pool de backup e, em seguida, retornar ao pool primário ou a um novo pool quando a interrupção for terminada.

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

