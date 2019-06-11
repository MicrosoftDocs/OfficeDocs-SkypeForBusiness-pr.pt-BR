---
title: 'Lync Server 2013: Recuperação de desastres do servidor de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d19e5a606c3217ad7653fd4c3c885a97aafdb5ee
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829329"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Recuperação de desastres do servidor de borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-03-12_

Assim como em outras funções de servidor, a melhor maneira de fornecer alta disponibilidade para seus servidores de borda é implantar vários servidores de borda em pools em cada site. Se um servidor de borda ficar inoperante, os outros servidores do pool continuarão a fornecer serviços de borda.

Para habilitar os procedimentos de recuperação de desastre, você deve ter pools de servidores de borda separados implantados em sites separados. Você não precisa emparelhar explicitamente pools de bordas juntos como faz com pools de front-end, mas ter vários pools de bordas ainda oferece a disponibilidade para executar se um pool de borda inteiro ficar inativo. As seções a seguir fornecem detalhes sobre a recuperação de desastres para as várias funções dos servidores de borda.

<div>

## <a name="remote-access"></a>Acesso remoto

Se você tiver vários sites, cada um com um pool de servidores de borda e um pool de bordas inteira falhar, os serviços de acesso remoto continuarão a funcionar sem a necessidade de ação do administrador. Ao criar pools de borda em sites diferentes, você não pode usar o mesmo FQDN. Cada pool de bordas deve ter FQDNs exclusivos (internos e externos). Os pools de bordas não usam regras de publicação de proxy reverso para conversar com os servidores de front-end. O failover automático ocorre quando o cliente consulta novamente os registros do serviço DNS de acesso remoto e os usuários remotos são roteados para os servidores de borda em outro site. O cliente tenta cada FQDN de borda externa de acordo com a prioridade dos registros SRV DNS.

<div>


> [!NOTE]  
> Para que o failover funcione tranqüilamente, certifique-se de que o firewall permita que os servidores de front-end de cada pool se comuniquem com todos os servidores de borda.



</div>

</div>

<div>

## <a name="federation"></a>Federação

Para relações de Federação com outras organizações que executam o Lync Server, as solicitações de Federação de entrada continuarão funcionando desde que você tenha soluções como GTM de DNS geográficos. É importante entender que o failover de Federação não fornece failover com prioridade em Registros SRV. Uma solução fornecida anteriormente pode ajudá-lo a fornecer recursos de recuperação de desastres para a Federação de entrada.

A Federação de saída sempre é configurada por meio de um pool de bordas publicado ou um servidor de borda na organização. Se esse pool de bordas estiver desativado, você deve usar o construtor de topologias para alterar a rota de Federação de saída para usar um pool de bordas que ainda está em execução. Para obter detalhes, consulte [falha sobre o pool de borda usado para Federação do Lync Server no Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

</div>

<div>

## <a name="xmpp-federation"></a>Federação do XMPP

Para a Federação do XMPP, o tráfego de entrada e saída falhará se o pool de bordas que está designado como o gateway de Federação do XMPP ficar inativo. Para fazer com que a Federação do XMPP funcione novamente, você deve alterar a Federação do XMPP para usar um pool de bordas diferente. Para obter detalhes, consulte [falha sobre o pool de borda usado para a Federação do XMPP no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>O pool de bordas falha, mas o pool de front-end ainda está em execução

Se um pool de bordas falhar em um site, mas o pool de front-end nesse site ainda estiver em execução, será necessário alterar o pool de front-ends para usar um pool de bordas diferente em um site diferente enquanto esse primeiro pool de bordas estiver inoperante. Para obter mais informações, consulte [alterando o pool de bordas associado a um pool de front-end no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

