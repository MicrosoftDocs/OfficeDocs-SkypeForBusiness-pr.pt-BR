---
title: 'Lync Server 2013: recuperação de desastre do servidor de borda'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Edge Server disaster recovery
ms:assetid: 05ec8d26-d167-4a6f-a966-a1f8873cf974
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ687960(v=OCS.15)
ms:contentKeyID: 49733545
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 519243475f5452cebc6fff82cc54f267bb8b36fd
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42136348"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="edge-server-disaster-recovery-in-lync-server-2013"></a>Recuperação de desastre do servidor de borda no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-03-12_

Assim como ocorre com outras funções de servidor, a melhor maneira de fornecer alta disponibilidade para seus Servidores de Borda é implantar múltiplos Servidores de borda em pools em cada site. Se um Servidor de Borda ficar inativo, os outros servidores no pool continuarão a fornecer serviços de Borda.

Para habilitar procedimentos de recuperação de desastre, é necessário ter pools de Servidor de Borda separados implantados em sites separados. Não é necessário parear explicitamente os pools de Borda da mesma forma que você faz com os pools Front-End, mas ter vários pools de Borda ainda fornece a disponibilidade para continuar caso um pool de Borda inteiro fique inativo. As seções a seguir fornecem detalhes sobre recuperação de desastre para as diversas funções dos Servidores de Borda.

<div>

## <a name="remote-access"></a>Acesso remoto

Se você tiver vários sites, cada um com um pool de servidores de borda e um pool de borda inteiro falhar, os serviços de acesso remoto continuarão a funcionar sem a necessidade de ação do administrador. Ao criar pools de borda em sites diferentes, você não pode usar o mesmo FQDN. Cada pool de borda deve ter FQDNs exclusivos (internos e externos). Os pools de borda não usam regras de publicação de proxy reverso para falar com os servidores front-end. O failover automático ocorre quando o cliente consulta novamente os registros de serviço DNS de acesso remoto e os usuários remotos são roteados para os servidores de borda em outro site. O cliente tenta cada FQDN de borda externa de acordo com a prioridade dos registros SRV DNS.

<div>


> [!NOTE]  
> Para que o failover funcione suavemente, verifique se o firewall permite que os servidores front-end de cada pool se comuniquem com todos os servidores de borda.



</div>

</div>

<div>

## <a name="federation"></a>Federação

Para relações de Federação com outras organizações que executam o Lync Server, as solicitações de Federação de entrada continuarão funcionando desde que você tenha soluções como GTM de DNS geográficos. É importante entender que o failover de Federação não fornece failover com prioridade em Registros SRV. Uma solução fornecida anteriormente pode ajudá-lo a fornecer recursos de recuperação de desastre para a Federação de entrada.

A federação de saída sempre é configurada por meio de um pool de Borda ou Servidor de Borda publicado na organização. Se esse pool de Borda estiver inativo, será necessário usar o Construtor de Topologia para alterar a rota de federação de saída a fim de usar um pool de Borda que ainda está em execução. Para obter detalhes, consulte [failover do pool de borda usado para Federação do Lync Server no Lync server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-lync-server-federation.md)

</div>

<div>

## <a name="xmpp-federation"></a>Federação XMPP

Para federação XMPP, o tráfego de saída e de entrada falhará se o pool de Borda designado como o gateway de federação XMPP ficar inativo. Para fazer a federação XMPP funcionar novamente, é necessário alterar a federação XMPP a fim de usar um pool de Borda diferente. Para obter detalhes, consulte [failover do pool de borda usado para Federação XMPP no Lync Server 2013](lync-server-2013-failing-over-the-edge-pool-used-for-xmpp-federation.md).

</div>

<div>

## <a name="edge-pool-fails-but-front-end-pool-is-still-running"></a>Pool de Borda falha, mas o pool Front-End ainda está em execução

Se um pool de Borda falhar em um site, mas o pool Front-End nesse site ainda estiver em execução, será necessário alterar o pool Front-End a fim de usar um pool de Borda diferente em um site diferente, enquanto o primeiro pool de Borda está inativo. Para obter mais informações, consulte [alterar o pool de borda associado a um pool de front-ends no Lync Server 2013](lync-server-2013-changing-the-edge-pool-associated-with-a-front-end-pool.md).

</div>

</div>

<span> </span>

</div>

</div>

</div>

