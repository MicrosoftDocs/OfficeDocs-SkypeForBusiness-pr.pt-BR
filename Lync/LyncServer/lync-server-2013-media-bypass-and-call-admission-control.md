---
title: 'Lync Server 2013: bypass de mídia e controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a0a2df9eee6ee9cf0ca387c9098623d574292a27
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42045213"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a>Bypass de mídia e controle de admissão de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-05_

O desvio de mídia e o controle de admissão de chamadas trabalham juntos para gerenciar o controle de largura de banda da mídia de chamadas. O desvio de mídia facilita o fluxo da mídia por links bem conectados, enquanto o controle de admissão de chamadas gerencia o tráfego nos links com limites de largura de banda. Como o Desvio de Mídia e o controle de admissão de chamadas são mutuamente exclusivos, você deve estar atento a um quando estiver planejando o outro. Há suporte para as seguintes combinações:

  - CAC e Desvio de Mídia estão habilitados. O Desvio de Mídia deve estar definido como **Usar informações de site e da região**. As informações do site e da região são as mesmas usadas para o CAC.
    
    Se você habilitar o CAC, não pode selecionar **Desviar Sempre** e vice-versa porque as duas configurações são mutuamente exclusivas. Ou seja, somente uma das duas irá se aplicar a qualquer chamada de PSTN determinada. Primeiro, é realizada uma verificação para determinar se o desvio de mídia se aplica à chamada e, em caso afirmativo, não se usa o CAC. Isso faz sentido, porque se uma ligação for apta para desvio, ela está, por definição, usando uma conexão em que um CAC não é necessário. Se o desvio não pode ser aplicado à chamada (ou seja, se os IDs do desvio do cliente e do gateway não corresponderem), o CAC é aplicado à chamada.

  - CAC não habilitado e Desvio de Mídia definido como **Desviar Sempre**.
    
    Nesta configuração, as sub-redes do cliente e do tronco são mapeadas a um único ID de desvio, que é computado pelo sistema.

  - CAC não habilitado e Desvio de Mídia definido é definido como **Usar Informações do Site e da Região**.
    
    Onde **Usar Informações do Site e da Região** estiver disponível, a determinação do desvio funciona essencialmente da mesma maneira, independente de o CAC estar habilitado ou não. Ou seja, para qualquer chamada de PSTN determinada, a sub-rede do cliente é mapeada a um site em particular, e a ID de desvio dessa sub-rede é extraída. De maneira semelhante, a sub-rede do gateway é mapeada a um site particular, e a ID do desvio dessa sub-rede é extraída. Somente se duas IDs de desvio forem idênticas o desvio acontecerá para a chamada. Caso não sejam idênticas, o desvio de chamada não irá acontecer.
    
    Ainda que o CAC esteja desabilitado globalmente, a política de largura de banda precisa ser definida para cada site e link se você quiser usar a configuração site-e-região para controlar a decisão de desvio. O valor real da restrição da largura de banda ou da sua modalidade não importa. O objetivo final é que o sistema calcule automaticamente as IDs diferentes de desvio para associar aos locais diferentes que não estão bem conectados. Definir a restrição da largura de banda por definição significa que um link não está bem conectado.

  - O CAC está habilitado, mas o desvio de mídia não. Isso se aplica apenas onde todos os gateways e IP-PBXs não estão bem conectados ou não atendem outros requisitos para desvio de mídia. Para obter detalhes sobre os requisitos para bypass de mídia, consulte [Technical Requirements for Media bypass in Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).

<div>

## <a name="see-also"></a>Confira Também


[Visão geral do bypass de mídia no Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Modos de bypass de mídia no Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Requisitos técnicos para bypass de mídia no Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

