---
title: 'Lync Server 2013: visão geral do controle de admissão de chamadas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Overview of call admission control
ms:assetid: 6fda0195-4c89-4dea-82e8-624f03e3d062
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398529(v=OCS.15)
ms:contentKeyID: 48184474
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 545355c1746846a16cf51e4147938f9c0a35710a
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42153271"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="overview-of-call-admission-control-in-lync-server-2013"></a>Visão geral do controle de admissão de chamadas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-09-22_

As comunicações em tempo real são sensíveis à perda de latência e pacotes que pode ocorrer em redes congestionadas. O CAC (serviço de controle de admissão de chamadas) determina, com base na largura de banda da rede disponível, se será permitido estabelecer sessões de comunicação em tempo real, como chamadas de voz ou vídeo. O design do CAC no Lync Server 2013 oferece quatro atributos principais:

  - é simples de implantar e gerenciar, sem a necessidade de equipamentos adicionais, como roteadores especialmente configurados.

  - Ele aborda casos críticos de uso de comunicações unificadas, como usuários móveis e vários pontos de presença. As políticas CAC são aplicadas de acordo com a localização do ponto de extremidade, não onde o usuário está hospedado.

  - Além de chamadas de voz, ele pode ser aplicado a outro tráfego, como chamadas de vídeo e sessões de conferência de áudio/vídeo.

  - Oferece a flexibilidade para permitir a representação de vários tipos de topologias de rede. Para obter exemplos, consulte [Components and topologias for CAC in Lync Server 2013](lync-server-2013-components-and-topologies-for-cac.md).

Se uma nova voz ou sessão de vídeo exceder os limites de largura de banda definidos em um link WAN, a sessão é bloqueada ou (somente para chamadas de telefone) redirecionada ao PSTN.

O CAC controla o tráfego em tempo real somente para voz e vídeo. Ele não controla o tráfego de dados.

Os administradores definem políticas de CAC, que são impostas pelo serviço de política de largura de banda que é instalado com cada pool de front-ends. As configurações de CAC são automaticamente propagadas para todos os servidores front-end do Lync Server em sua rede.

Para chamadas que falham devido a políticas CAC, a ordem de precedência para o redirecionamento de chamada é:

1.  Internet

2.  PSTN

3.  Caixa postal

A gravação de detalhes da chamada (CDR) captura as informações sobre chamadas que são reencaminhadas para o PSTN ou o correio de voz. O CDR não captura as informações sobre chamadas reencaminhadas para a Internet, porque a Internet é tratada como um caminho alternativo, em vez de uma opção secundária.

<div>


> [!NOTE]  
> Os depósitos de correio de voz não serão negados devido a restrições de largura de banda.



</div>

O Serviço de Política de Largura de Banda gera dois tipos de arquivos de log no formato de valores separados por vírgulas (CSV). O arquivo de log **falhas de verificação** captura as informações quando as solicitações de largura de banda são negadas. O arquivo de log **utilização do link** captura um instantâneo da topologia de rede e a utilização de largura de banda do link de WAN. Ambos arquivos de log podem ajudá-lo a ajustar as políticas CAC com base na utilização.

<div>

## <a name="call-admission-control-considerations"></a>Considerações sobre o Controle de Admissão de Chamada

O administrador seleciona a instalação do Serviço de Política de Largura de Banda no primeiro pool configurado no site central. Como há apenas um site central por região da rede, há apenas um Serviço de Política de Largura de Banda por região da rede, que gerencia a política de largura de banda para aquela região, os sites associados e os links para esses sites. O serviço de política de largura de banda é executado como parte dos servidores front-end e, portanto, a alta disponibilidade é interna dentro desse pool. O serviço de política de largura de banda executado em cada servidor de front-end sincroniza a cada 15 segundos. Se o pool de front-ends falhar, as políticas do CAC não serão mais impostas para esse site até o pool de front-ends e, conseqüentemente, o serviço de política de largura de banda se tornar operacional novamente. Isso significa que todas as chamadas serão recebidas enquanto o Serviço de Política de Largura de Banda estiver inoperante. Portanto, ainda há a possibilidade de excesso de assinatura da largura de banda dos links durante esse período

O serviço de política de largura de banda fornece alta disponibilidade em um pool de front-ends; no entanto, ele não fornece redundância entre pools de front-ends. O serviço de política de largura de banda não pode fazer failover de um pool de front-ends para outro. Após a restauração do serviço para o pool de front-ends, o serviço de política de largura de banda é retomado e pode impor verificações de política de largura de banda novamente.

<div>

## <a name="network-considerations"></a>Considerações de Rede

Embora a restrição de largura de banda para áudio e vídeo seja imposta pelo serviço de política de largura de banda no Lync Server 2013, essa restrição não é imposta no roteador de rede (camada 2 e 3). Lync Server 2010 CAC não é possível impedir que um aplicativo de dados, por exemplo, consuma toda a largura de banda da rede em um link de WAN, incluindo a largura de banda reservada para áudio e vídeo pela sua política de CAC. Para proteger a largura de banda necessária em sua rede, você pode implantar um protocolo de QoS (qualidade de serviço), como os serviços diferenciados (DiffServ). Portanto, uma prática recomendada é coordenar as políticas de largura de banda do CAC que você define com qualquer configuração de QoS que você possa implantar.

</div>

<div>

## <a name="media-and-signaling-paths-over-vpn"></a>Mídia e Sinalização de Caminhos através de VPN

Se a sua empresa oferece suporte à mídia através de VPN, verifique se tanto o fluxo de mídia e o fluxo de sinalização vão através de VPN ou ambos são roteados pela internet. Por padrão, a mídia e os fluxos de sinalização passam pelo encapsulamento VPN.

</div>

<div>

## <a name="call-admission-control-of-outside-users"></a>Controle de Admissão de Chamada de Usuários Externos

O controle de admissão de chamada não será aplicado aos usuários remotos onde o tráfego de rede flui através da Internet. Como o tráfego de mídia está atravessando a Internet, o que não é gerenciado pelo Lync Server, o CAC não pode ser aplicado. Serão realizadas verificações de CAC, no entanto, na parte da chamada que flui através da rede corporativa.

</div>

<div>

## <a name="call-admission-control-of-pstn-connections"></a>Controle de Admissão de Chamada das Conexões PSTN

O controle de admissão de chamadas é aplicável no servidor de mediação independentemente de estar conectado a um IP/PBX, um gateway PSTN ou um tronco SIP. Como o servidor de mediação é um agente de usuário back-to-back (B2BUA), ele termina a mídia. Ele tem dois lados de conexão: um lado conectado ao Lync Server e um lado do gateway, que está conectado a gateways PSTN, IP/PBXs ou troncos SIP. Para obter detalhes sobre conexões PSTN, consulte [Planning for PSTN Connectivity in Lync Server 2013](lync-server-2013-planning-for-pstn-connectivity.md).

O CAC pode ser aplicado em ambos os lados do servidor de mediação, a menos que o bypass de mídia esteja habilitado. Se o bypass de mídia estiver habilitado, o tráfego de mídia não percorrerá o servidor de mediação, mas, em vez disso, fluirá diretamente entre o cliente Lync e o gateway. Nesse caso, o CAC não é necessário. Para obter detalhes, consulte [Planning for Media bypass in Lync Server 2013](lync-server-2013-planning-for-media-bypass.md).

A figura a seguir ilustra como o CAC é aplicado em conexões PSTN, com e sem o bypass de mídia habilitado.

**Aplicação de controle de admissão de chamada em conexões para o PSTN**

![Imposição de conexão de mídia do CAC de voz](images/Gg398703.4d66d529-0912-4de1-abec-266f54272eb3(OCS.15).jpg "Imposição de conexão de mídia do CAC de voz")

</div>

<div>

## <a name="compatibility-of-call-admission-control-with-earlier-versions-of-office-communications-server"></a>Compatibilidade de Controle de Admissão de Chamada com Versões Anteriores do Office Communications Server

O controle de admissão de chamadas pode ser habilitado somente em pontos de extremidade habilitados para o Lync Server 2010 e posterior.

O controle de admissão de chamadas não pode ser habilitado em pontos de extremidade que executam o Office Communicator 2007 R2 ou anterior.

**Aplicativo do CAC em diferentes versões do Lync Server**

![Diagrama de comparação de versão do CAC de voz](images/Gg398529.fdbfee7e-15fc-445b-949d-8d61e61ac350(OCS.15).jpg "Diagrama de comparação de versão do CAC de voz")

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

