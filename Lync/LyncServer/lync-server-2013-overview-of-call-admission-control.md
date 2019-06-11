---
title: 'Lync Server 2013: visão geral do controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5cba1a83ce64fa575cf5de724d5dd215fcb459c7
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34825839"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Visão geral do controle de admissão de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-22_

As comunicações em tempo real são sensíveis à latência e perda de pacotes que podem ocorrer em redes congestionadas. O CAC (serviço de controle de admissão de chamadas) determina, com base na largura de banda da rede disponível, se será permitido estabelecer sessões de comunicação em tempo real, como chamadas de voz ou vídeo. O design do CAC no Lync Server 2013 oferece quatro atributos principais:

  - É simples implantar e gerenciar sem exigir equipamento adicional, como roteadores especialmente configurados.

  - Ele aborda casos críticos de uso de comunicações unificadas, como usuários móveis e vários pontos de presença. Políticas do CAC são impostas de acordo com o local em que o ponto de extremidade está localizado, não onde o usuário está hospedado.

  - Além de chamadas de voz, ela pode ser aplicada a outro tráfego, como chamadas com vídeo e sessões de videoconferência/videoconferência.

  - Fornece a flexibilidade para habilitar a representação de vários tipos de topologias de rede. Para obter exemplos, consulte [componentes e topologias do CAC no Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Se uma nova sessão de voz ou de vídeo exceder os limites de largura de banda definidos em um link de rede de longa distância, a sessão será bloqueada ou (apenas para chamadas telefônicas) redirecionada para a PSTN.

O CAC controla o tráfego em tempo real para voz e vídeo somente. Ele não controla o tráfego de dados.

Os administradores definem políticas do CAC, que são impostas pelo serviço de política de largura de banda que é instalado com cada pool de front-ends. As configurações de CAC são automaticamente propagadas para todos os servidores de front-end do Lync Server na sua rede.

Para chamadas que falham devido às políticas do CAC, a ordem de precedência para redirecionar a chamada é a seguinte:

1.  Internet

2.  PSTN

3.  Caixa postal

A gravação de detalhes de chamadas (CDR) captura informações sobre chamadas redirecionadas para a PSTN ou para a caixa postal. A CDR não captura informações sobre chamadas redirecionadas para a Internet, porque a Internet é tratada como um caminho alternativo, em vez de uma opção secundária.

<div>


> [!NOTE]  
> Os depósitos da caixa postal não serão negados devido a restrições de largura de banda.



</div>

O serviço de política de largura de banda gera dois tipos de arquivos de log no formato CSV (valores separados por vírgula). O arquivo de log de **falhas de verificação** captura informações quando as solicitações de largura de banda são negadas. O arquivo de log de **utilização do link** captura um instantâneo da topologia de rede e a utilização da largura de banda do link WAN. Esses dois arquivos de registro podem ajudá-lo a ajustar suas políticas do CAC com base na utilização.

<div>

## <a name="call-admission-control-considerations"></a>Considerações sobre o controle de admissão de chamadas

O administrador seleciona a instalação do serviço de política de largura de banda no primeiro pool configurado no site central. Como há um único site central por região de rede, há apenas um serviço de política de largura de banda por região de rede, que gerencia a política de largura de banda para essa região, seus sites associados e os links para esses sites. O serviço de política de largura de banda é executado como parte dos servidores front-end e, portanto, a alta disponibilidade é interna dentro desse pool. O serviço de política de largura de banda executado em cada servidor front-end sincroniza a cada 15 segundos. Se o pool de front-ends falhar, as políticas do CAC não serão mais impostas para esse site até o pool de front-ends e, consequentemente, o serviço de política de largura de banda ficará operacional novamente. Isso indica que todas as chamadas passarão durante a duração em que o serviço de política de largura de banda está fora do serviço. Portanto, há a possibilidade de largura de banda superassinatura de seus links durante este período

O serviço de política de largura de banda fornece alta disponibilidade em um pool de front-end; no entanto, ele não fornece redundância entre pools de front-end. O serviço de política de largura de banda não pode fazer failover de um pool de front-end para outro. Uma vez que o serviço para o pool de front-end seja restaurado, o serviço de política de largura de banda é retomado e pode impor verificações de política de largura

<div>

## <a name="network-considerations"></a>Considerações de rede

Embora a restrição de largura de banda para áudio e vídeo seja imposta pelo serviço de política de largura de banda no Lync Server 2013, essa restrição não é imposta no roteador de rede (camada 2 e 3). Lync Server 2010 o CAC não pode impedir que um aplicativo de dados, por exemplo, consuma toda a largura de banda de rede em um link de WAN, incluindo a largura de banda que é reservada para áudio e vídeo pela sua política do CAC. Para proteger a largura de banda necessária na sua rede, você pode implantar um protocolo de QoS (qualidade de serviço), como serviços diferenciados (DiffServ). Portanto, uma prática recomendada é coordenar as políticas de largura de banda do CAC que você define com qualquer configuração de QoS que possa ser implantada.

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>Caminhos de mídia e sinalização via VPN

Se a sua empresa for compatível com mídia via VPN, certifique-se de que tanto o fluxo de mídia quanto o fluxo de sinalização passem pela VPN ou ambos sejam roteados pela Internet. Por padrão, a mídia e os fluxos de sinalização passam pelo túnel VPN.

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>Controle de admissão de chamadas de usuários externos

O controle de admissão de chamadas não é imposto para usuários remotos nos quais o tráfego de rede flui pela Internet. Como o tráfego de mídia está atravessando a Internet, o que não é gerenciado pelo Lync Server, o CAC não pode ser aplicado. Cheques do CAC serão executados, no entanto, na parte da chamada que flui pela rede da empresa.

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>Controle de admissão de chamadas de conexões PSTN

O controle de admissão de chamadas é aplicável no servidor de mediação independentemente de estar conectado a um IP/PBX, a um gateway PSTN ou a um tronco SIP. Como o servidor de mediação é um agente de usuário back-to-back (B2BUA), ele termina a mídia. Ele tem dois lados de conexão: um lado conectado ao Lync Server e um lado do gateway, que é conectado a gateways PSTN, IP/PBXs ou troncos SIP. Para obter detalhes sobre conexões PSTN, consulte [planejando a conectividade PSTN no Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

O CAC pode ser imposto em ambos os lados do servidor de mediação, a menos que a opção ignorar mídia esteja habilitada. Se a bypass de mídia estiver habilitada, o tráfego de mídia não percorrerá o servidor de mediação, mas fluirá diretamente entre o cliente do Lync e o gateway. Nesse caso, o CAC não é necessário. Para obter detalhes, consulte [planejando o bypass de mídia no Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

A figura a seguir ilustra como o CAC é imposto sobre conexões PSTN com e sem o bypass de mídia habilitado.

**Aplicação de controle de admissão de chamadas em conexões com PSTN**

![Aplicação de voz do CAC ignorando] a imposição de conexão (images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Aplicação de voz do CAC ignorando") a imposição de conexão

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>Compatibilidade do controle de admissão de chamadas com versões anteriores do Office Communications Server

O controle de admissão de chamadas pode ser habilitado somente em pontos de extremidade habilitados para o Lync Server 2010 e posteriores.

O controle de admissão de chamadas não pode ser habilitado em pontos de extremidade que executam o Office Communicator 2007 R2 ou anterior.

**Aplicativo do CAC em diferentes versões do Lync Server**

![Diagrama de comparação da versão do CAC do CAC] (images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagrama de comparação da versão do CAC do CAC")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

