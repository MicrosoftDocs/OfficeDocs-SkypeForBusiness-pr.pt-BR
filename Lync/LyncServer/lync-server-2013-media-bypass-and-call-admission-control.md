---
title: 'Lync Server 2013: Bypass de mídia e controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Media bypass and call admission control
ms:assetid: 120b2a2b-5f97-4735-a2ee-0f849feb8c1d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398203(v=OCS.15)
ms:contentKeyID: 48183454
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3c5e02a57add6b93f1ad5c5efc3ac644e65e97f4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34827554"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="media-bypass-and-call-admission-control-in-lync-server-2013"></a>Bypass de mídia e controle de admissão de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-05_

O bypass de mídia e o CAC trabalham juntos para gerenciar o controle de largura de banda da mídia de chamadas. O bypass de mídia facilita o fluxo da mídia por links bem conectados, enquanto o bypass gerencia o tráfego nos links com limites de largura de banda. Como o Bypass de mídia e o CAC são mutuamente exclusivos, você deve estar atento a um quando estiver planejando o outro. Há suporte para as seguintes combinações:

  - CAC e Bypass de mídia estão habilitados. O Bypass de mídia deve estar definido como **Use Site and Region Information** (Usar informações do site e da região). As informações do site e da região são as mesmas usadas no CAC.
    
    Se você habilitar o CAC, não poderá selecionar **Sempre ignorar** e vice-versa porque as duas configurações são mutuamente exclusivas. Ou seja, somente uma das duas se aplicará a qualquer chamada de PSTN determinada. Primeiro, é realizada uma verificação para determinar se o bypass de mídia se aplica à chamada e, em caso afirmativo, não se usa o CAC. Isso faz sentido, porque se uma ligação for apta para bypass, ela está, por definição, usando uma conexão em que um CAC não é necessário. Se o bypass não pode ser aplicado à chamada (ou seja, se os IDs do bypass do cliente e do gateway não corresponderem), o CAC é aplicado à chamada.

  - CAC não habilitado e Bypass de mídia definido como **Sempre ignorar**.
    
    Nesta configuração, as sub-redes do cliente e do tronco são mapeadas a uma única ID de bypass, que é computado pelo sistema.

  - CAC não habilitado e Bypass de mídia definido é definido como **Use Site and Region Information** (Usar informações do site e da região).
    
    Onde **Use Site and Region Information** (Use Site and Region Information) estiver habilitado, a determinação do bypass funciona essencialmente da mesma maneira, independentemente de o CAC estar habilitado ou não. Ou seja, para qualquer chamada de PSTN determinada, a sub-rede do cliente é mapeada a um site em particular, e a ID de bypass dessa sub-rede é extraída. De maneira semelhante, a sub-rede do gateway é mapeada a um site particular, e a ID do bypass dessa sub-rede é extraída. O bypass só acontecerá para a chamada se as duas IDs de bypass forem idênticas. Caso não sejam idênticas, o bypass da chamada não acontecerá.
    
    Ainda que o CAC esteja desabilitado globalmente, a política de largura de banda precisa ser definida para cada site e link se você quiser usar a configuração site-e-região para controlar a decisão de bypass. O valor real da restrição da largura de banda ou da sua modalidade não importa. O objetivo final é que o sistema calcule automaticamente as IDs diferentes de bypass para associar aos locais diferentes que não estão bem conectados. Definir a restrição da largura de banda por definição significa que um link não está bem conectado.

  - O CAC está habilitado, mas o bypass de mídia não. Isso se aplica apenas onde todos os gateways e IP-PBXs não estão bem conectados ou não atendem outros requisitos para o bypass de mídia. Para obter detalhes sobre requisitos de bypass de mídia, consulte [requisitos técnicos para bypass de mídia no Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md).

<div>

## <a name="see-also"></a>Confira também


[Visão geral do bypass de mídia no Lync Server 2013](lync-server-2013-overview-of-media-bypass.md)  
[Modos de bypass de mídia no Lync Server 2013](lync-server-2013-media-bypass-modes.md)  
[Requisitos técnicos para bypass de mídia no Lync Server 2013](lync-server-2013-technical-requirements-for-media-bypass.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

