---
title: Fluxo de chamadas usando Rota Expressa
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.date: 01/22/2018
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Este artigo ajuda a explicar os princípios centrais do fluxo de chamadas do Skype for Business Online e da Rota Expressa, além de fornecer alguns exemplos detalhados de fluxos de chamadas para que você possa entender e planejar corretamente.
ms.openlocfilehash: 220a23a5a43b281790422c39908e7a0ea32c03b4
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="call-flow-using-expressroute"></a>Fluxo de chamadas usando Rota Expressa

Este artigo ajuda a explicar os princípios centrais do fluxo de chamadas do Skype for Business Online e da Rota Expressa, além de fornecer alguns exemplos detalhados de fluxos de chamadas para que você possa entender e planejar corretamente.
  
Se você estiver implantando Skype para Business Online como parte do Office 365, Skype para Business Server híbrido ou Skype para Business Edition do conector de nuvem, você precisa compreender a comunicação entre o Skype para servidores e clientes de negócios e o fluxo de chamadas tão Você pode efetivamente planejar, implantar, operar e solucionar problemas de sua Skype para serviços corporativos Online. 
  
## <a name="call-flow-overview"></a>Visão geral do fluxo de chamadas

Este documento descreve a rede segmentos que podem carregar dados para essas chamadas fluem e ajudam a entender qual tráfego permanecerá locais à sua rede em comparação com o tráfego percorrida pela Internet ou por meio de ExpressRoute. Saber o tráfego que usa ExpressRoute ajudará você a avaliar os benefícios que sua empresa receberá usando ExpressRoute, bem como ajudam que você a compreender as diretrizes de implantação de ExpressRoute para validar e solucionar problemas de sua implantação depois de decidir Para usar ExpressRoute.
  
Os fluxos de chamadas descritos aqui podem ser afetados por uma série de fatores que você controla, inclusive as regras de firewall, a configuração NAT, proxies e a configuração do roteador. Este documento presume que as configurações recomendadas já estão aplicadas. Essas configurações recomendadas são descritas em:
  
- [Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- [Visão geral de ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)
    
- [Rota Expressa do Azure](https://azure.microsoft.com/services/expressroute/)
    
Instalação e as configurações que ainda não tiver seguido as etapas de instalação encontradas na documentação acima podem ter fluxos de chamada diferentes daquelas que podemos ter documentadas aqui. Além disso, você pode achar sozinho com problemas de configuração, como as rotas de rede assimétrica e não ideal ou protocolos de transporte não ideal. Roteamento assimétrica é uma consideração importante sempre que está envolvido ExpressRoute, pois ExpressRoute apresenta um segundo caminho para o Office 365, que cria a possibilidade de uma rota que utiliza a Internet em uma direção e outra rota que usa ExpressRoute na outra direção. Isso pode resultar no bloqueio do tráfego na direção de retorno, se ele passar por um firewall com estado.
  
## <a name="network-segments-and-traffic-types"></a>Segmentos de rede e tipos de tráfego

### <a name="network-segments"></a>Segmentos de rede

Antes de explicar o fluxo de chamadas, precisamos definir alguns termos que ajudarão você a entender os segmentos de rede e os tipos de mídia usados no Skype for Business Online. 
  
Os diagramas de fluxo de chamada abaixo mostram quatro segmentos de rede diferente, cada um deles são gerenciados por organizações diferentes (sua rede interna, seu provedor de serviços de rede e seus parceiros de correspondência da Internet e Microsoft) que tenham diferentes características de desempenho. Para obter diretrizes de metas de desempenho de rede, consulte [qualidade de mídia e o desempenho da conectividade de rede em Skype para negócios Online](media-quality-and-network-connectivity-performance.md).
  
A seguir, apresentamos todos os segmentos de rede sobre os quais falaremos.
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **Sua rede** Esse é o segmento de rede que faz parte da sua rede geral que você controlar e gerenciar. Isso inclui todas as suas conexões dentro de suas escritórios entre si, se com ou sem fio, entre prédios, em centros de dados local e as conexões estabelecidas com provedores de Internet ou ExpressRoute parceiros.
  
Geralmente, a borda da sua rede tem um ou mais DMZ com firewalls e/ou servidores proxy, qual impor diretivas de segurança da sua organização e que permitir apenas determinado tráfego de rede que você configure e configurou. Porque você gerenciar esta rede, você tem controle direto sobre o desempenho da sua rede e é altamente recomendável que você conclua avaliações de rede para validar desempenho tanto dentro dos sites em sua rede e de sua rede Skype para negócios Online. Para ver os requisitos de desempenho, consulte [qualidade de mídia e o desempenho da conectividade de rede em Skype para negócios Online](media-quality-and-network-connectivity-performance.md).
  
 **Internet** Esse é o segmento de rede que faz parte da sua rede geral que será usada pelos usuários que estiverem se conectando ao Skype para negócios Online de fora da sua rede e são usados para todas as conexões quando ExpressRoute não está configurado. Internet e todas as suas conexões não são gerenciadas por você ou Microsoft, portanto desempenho e caminhos de roteamento não podem ser determinados, e isso terá o maior impacto sobre o fluxo de chamada e qualidade geral.
  
 **Rota Expressa** Este é o segmento de rede que faz parte de sua rede geral e que fornecerá uma conexão dedicada e privada à rede da Microsoft. Essa é a opção recomendada para conectar sua rede à rede Microsoft (centros de dados do Office 365) para todas as cargas de trabalho que são dependentes de desempenho, como Skype para comunicação em tempo real Business Online e velocidade da rede. Conexões de ExpressRoute são feitas entre a rede e o uso de rede Microsoft [ExpressRoute provedores de conectividade](https://azure.microsoft.com/documentation/articles/expressroute-locations/) para fornecer uma rede privada e gerenciada, 99,9% de tempo de atividade e suporte para a qualidade do serviço (QoS) que podem melhorar o desempenho para a mídia em tempo real durante os períodos de congestionamento da rede.
  
 **Rede da Microsoft** Este é o segmento de rede que faz parte de sua rede geral e que dá suporte aos serviços do Office 365. Isso inclui toda a comunicação entre os servidores Online para o Office 365. Isso pode incluir o tráfego que atravessa o backbone de rede da Microsoft e é transmitido entre regiões geográficas.
  
### <a name="types-of-traffic"></a>Tipos de tráfego

O tráfego de rede para Skype para Business Online se encaixa em duas amplas categorias, mostradas como caminhos separados no fluxo de chamada:
  
 **Mídia em tempo real** são dados encapsulados no protocolo RTP, com suporte para áudio, vídeo, compartilhamento de aplicativos e cargas de trabalho de transferência de arquivo. Em geral, o tráfego de mídia é altamente sensível à latência. Assim, convém que esse tráfego use o caminho mais direto possível, com UDP como o protocolo de camada de transporte, pois o uso de TCP introduz uma latência mais alta.
  
 **Sinalização** é o link de comunicação entre o cliente e servidor, ou outros clientes que são usados para controlar as atividades (por exemplo, quando uma chamada é iniciada) e entregar mensagens instantâneas. A maior parte do tráfego de sinalização usa o protocolo SIP, embora alguns clientes usem as interfaces REST baseadas em HTTP. Para tornar simples, estamos considerando uma variedade de sinalização que podem ser transmitidos conexões HTTP e HTTPS ou TLS nesse tipo de tráfego. É importante entender que esse tráfego é bem menos sensível à latência, mas pode ocasionar interrupções de serviço ou finalizações de chamadas, caso a latência entre os pontos de extremidade excedam vários segundos.
  
Os destinos desse tráfego são encontrados em [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para todos os serviços do Office 365. Para cada URL, ele indica se essa parte do tráfego pode usar a Rota Expressa do Office 365. Para diagramas que mostram que a Internet ainda é usada para alguns tráfego quando ExpressRoute estiver habilitado, consulte [ExpressRoute do Windows Azure para o Office 365](http://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). É importante entender pares URLs que estão listados como sendo roteável via ExpressRoute também são roteáveis pela Internet. This means that in some scenarios, the determination about whether the Internet or ExpressRoute will be used depends on location of client and configuration of proxy servers and firewalls. It is also important to understand that since not all URLs associated with Office 365 are able to use ExpressRoute, an Internet connection is required even if you purchase ExpressRoute from an ExpressRoute partner. 
  
O tráfego que só pode ser enviado pela Internet inclui dependências de Internet comuns, como listas de certificados revogados (CRLs), pesquisas de DNS e resolução de nomes e URLs para serviços compartilhados do Office 365, tais como para o Centro de administração do Office 365 e alguns não em tempo real recursos de comunicação do Skype para negócios Online, como telemetria e federação para a interoperabilidade com Skype consumidor, como bem mídia que é transmitida para transmissão do Skype reunião. Para ajudar você a tomar decisões, veja [Roteamento com o ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) para obter mais considerações durante o planejamento de seu roteamento de rede.
  
## <a name="principles-for-call-flows-with-skype-for-business"></a>Princípios para fluxos de chamadas com o Skype for Business

Antes de nos aprofundarmos em cenários específicos de fluxos de chamadas, existem seis princípios gerais que ajudam a entender os fluxos de chamadas do Skype for Business.
  
1. Um Skype para conferência de negócios é hospedado na mesma região em que o organizador da conferência está hospedado. A conferência estará na nuvem do Office 365, se o organizador for um usuário Online, ou em um datacenter local, se o organizador da reunião for um usuário local.
    
2. O tráfego de mídia enviado de um cliente para uma conferência hospedada sempre vai para o servidor onde a conferência está hospedada. Este pode ser um servidor local dentro de um datacenter que você gerencia ou um servidor online dentro de uma nuvem do Office 365. No entanto, um servidor de borda sempre é usado para o fluxo de mídia de conferências online.
    
3. O tráfego de mídia para chamadas ponto a ponto usa a rota mais direta que estiver disponível. A rota preferencial é direta para o ponto (cliente) remoto, mas se a rota não estiver disponível, porque o firewall está bloqueando o tráfego ou algo parecido, então um ou mais servidores de borda transmitirão o tráfego.
    
4. O tráfego de sinalização sempre irá para o servidor onde o usuário está localizado, Online ou no local. Um servidor de borda será usado se não for possível conectar-se diretamente ao servidor Front-End.
    
5. Os usuários que participam de uma conferência hospedada online sempre usarão um servidor de borda (ou dois, se necessário, dependendo das configurações de firewall do cliente).
    
6. Os usuários que ingressam em uma conferência hospedada no local normalmente não usarão um servidor de borda se estiverem se conectando pela mesma rede que contém a implantação local, mas usarão um ou dois servidores de borda quando estiverem se conectando de fora da sua rede. 
    
Para saber mais sobre os detalhes do caminho de mídia que foi escolhido, veja [ICE - Conectividade de mídia de borda](https://aka.ms/AVEdge). Although this video is about Lync Server 2013, the principles and protocols still apply to Skype for Business.
  
## <a name="skype-for-business-call-flows-with-expressroute"></a>Fluxos de chamadas do Skype for Business com Rota Expressa

Now that you have an understanding of the four different network segments and some general guiding principles for Skype for Business call flows, you can use that information to help you understand which Skype for Business traffic will traverse an ExpressRoute network segment.
  
Em geral, o tráfego de rede usará a conexão da Rota Expressa, caso um ponto de extremidade seja sua rede e o outro ponto de extremidade seja o datacenter do Office 365. Isso incluirá o tráfego de sinalização entre o cliente e o servidor, o tráfego de mídia usado durante as chamadas em conferência ou chamadas ponto a ponto que usam o servidor de borda online.
  
O tráfego não usará a conexão da Rota Expressa se os dois pontos de extremidade conseguirem se comunicar diretamente pela Internet ou se estiverem localizados em sua rede. Isso inclui a mídia para chamadas ponto a ponto, o tráfego da Internet destinado a uma implantação local ou qualquer tráfego entre a Internet e os servidores de borda do Office 365. Um exemplo disso seria a participação em uma conferência online de um usuário hospedado em um hotel.
  
## <a name="basic-skype-for-business-call-flow"></a>Como usar o fluxo de chamadas do Skype for Business

Para ajudá-lo a aplicar os princípios gerais de fluxos de chamadas do Skype for Business descritos anteriormente, a próxima seção deste artigo contém vários diagramas para referência. Não se trata de uma lista exaustiva de todos os fluxos de chamadas possíveis, mas tem como finalidade ajudá-lo a aplicar os princípios detalhados anteriormente. Além disso, os cenários nos diagramas foram selecionados para abranger tipos comuns de implantação, incluindo Online, Híbrido, Cloud Connector e um caso especial: a Transmissão de Reunião do Skype.
  
> [!NOTE]
> [!OBSERVAçãO] Um subconjunto de tráfego usado pelo Skype for Business não é roteável pela Rota Expressa e sempre usará o caminho da Internet. Veja [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para determinar as URLs que podem ser afetadas.
  
### <a name="peer-to-peer-call-for-office-365-users-from-within-customer-network"></a>Chamada ponto a ponto para usuários do Office 365 de dentro da rede do cliente
<a name="bk_Figure2"> </a>

Para chamadas ponto a ponto, o tráfego de mídia sempre usa a rota mais direta até o seu destino. No entanto, o tráfego de sinalização vai para um datacenter do Office 365 onde o usuário online está localizado. Visto que os dois usuários estão na mesma WAN e nada impede a comunicação direta entre os clientes, a mídia flui diretamente entre eles. O tráfego de sinalização, dos dois usuários, usa a conexão da Rota Expressa que está destinada a cada datacenter da organização. Para mostrar o fluxo de chamadas neste cenário, veja isto.
  
 **Fluxo de chamadas ponto a ponto**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Usuário online de sua rede ingressando em uma conferência hospedada online
<a name="bk_Figure3"> </a>

No exemplo-a-ponto, o tráfego de mídia sempre leva a rota mais direta ao seu destino. No entanto, para uma conferência Online, o destino é na nuvem Office 365. Isso significa que o tráfego de mídia para todos os usuários de ingresso na conferência de dentro de sua rede percorrerá a conexão ExpressRoute e o tráfego de sinalização é encaminhado para o Office 365 na nuvem. O gráfico a seguir mostra que sinalização e mídia percorrerão a conexão ExpressRoute de um usuário em sua rede e percorrerão diretamente da Internet para usuários que estão conectados à Internet de fora da rede, como a partir de um café loja ou hotel.
  
Lembre-se de que o local de uma conferência é definido pelo organizador da reunião, e não pelos participantes. Isso significa que se a reunião fosse agendada por um cliente local, o tráfego de mídia não fluiria para a nuvem do Office 365 pela Rota Expressa, mas usaria a Internet até o datacenter local do organizador da reunião.
  
O destino da mídia de conferências online será um datacenter na nuvem do Office 365, mas esse datacenter pode estar em uma região geográfica diferente daquela dos usuários que estão participando da conferência. Isso pode acontecer de uma das seguintes maneiras:
  
- Se o organizador da reunião for de uma empresa diferente da dos participantes, e se a organização dele estiver hospedada em outra localização geográfica ou país/região.
    
- Se um usuário estiver participando de um país/região diferente de onde a organização da empresa está localizada, pelo fato de a empresa ser multinacional ou o usuário estar viajando.
    
A boa notícia sobre como usar ExpressRoute neste cenário é que com ExpressRoute complemento de premium, dados que segue o caminho ExpressRoute passará automaticamente entre backbone da Microsoft, independentemente da região geográfica do organizador da reunião datacenter da organização.
  
 **Usuário online com fluxo de chamadas de reunião online**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Ingressando em uma conferência hospedada por usuário local em implantação híbrida
<a name="bk_Figure3"> </a>

Lembre-se de que os servidores de conferência que dão suporte a conferências hospedadas são determinados pelo local onde o organizador da reunião está. Nesse cenário, as mídias de todos os usuários participantes de uma conferência agendada por um usuário local em uma implantação híbrida fluirão para um datacenter local. A sinalização para usuários online será estabelecida por meio de sua organização na nuvem do Office 365, enquanto as mídias tentarão uma conexão direta. Nesse cenário, como os dois usuários estão se conectando a partir de sua rede, é possível uma conexão direta de mídias, pois a Rota Expressa é usada somente para tráfego de sinalização de usuário hospedado online. Se um usuário hospedado online se conectar pela Internet, a mídia poderá usar a Rota Expressa, caso um servidor de borda online seja usado para conexão.
  
 **Conferência hospedada por um fluxo de chamadas de usuário híbrido**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>Servidor de borda local com conferências hospedadas no Office 365
<a name="bk_Figure5"> </a>

Quando um usuário de híbrido junções um Online hospedado conferência, nós sabemos que sinalização e mídia vai ser destinada para o Office 365 na nuvem e desde que o usuário está ingressando a partir da Internet, normalmente um caminho de internet direto poderia ser utilizado. No entanto, em alguns casos, tais como devido a restrições de firewall, um caminho direto da Internet não está disponível. Nesse caso, um servidor de borda de local pode retransmitir o tráfego de mídia, o que faz com que o tráfego de mídia retornar à sua rede local antes de passar pelo circuito ExpressRoute para a nuvem do Office 365.
  
 **Usuário local ingressando em uma chamada em conferência online através de servidor de borda local**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Chamada PSTN usando o Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

O [Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) fornece conectividade PSTN por meio de recursos locais, como um tronco SIP ou um gateway PSTN ou por meio de um dispositivo de hardware mínimo, para integrar-se ao Skype for Business. Com a edição do conector de nuvem, os usuários hospedados Online e agir como usuários Online normais quando eles não envolvem chamar planos. A sinalização para cenários PSTN viaja entre o cliente e a nuvem por meio da conexão da Rota Expressa, se ela estiver disponível, e o tráfego de mídias permanece em sua WAN. Nesse caso, a sinalização gira em torno da nuvem do Office 365 e termina no Cloud Connector.
  
 **PSTN call via the Phone System in Office 365 and Cloud Connector**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Transmissão de Reunião do Skype com usuários ingressando pela rede do cliente
<a name="bk_Figure6"> </a>

A Transmissão de Reunião do Skype é um caso de uso especial, que consiste em uma reunião de duas partes, cada qual com diferentes perfis de transporte de rede. The first part, and the one that is most important from a network performance point of view, is the inner meeting. This is the real-time portion of the meeting that includes one or more client endpoints connecting to the conferencing server in the Office 365 cloud. Data transmitted using this portion of the meeting is exactly like the example above, with an Office 365 user joining and Online conference. 
  
What makes Skype Meeting Broadcast unique is that the meeting is distributed to a large number of conference attendees using a broadcast streaming service. This broadcast streaming service isn't routable over ExpressRoute, but instead uses the Internet with the optional support of Content Delivery Network (CDN) services. It is helpful to recognize that the broadcast streaming is a unidirectional media flow because the attendees listen but don't talk and supports buffering, so it is much less sensitive to network performance issues such as latency, packet loss, and jitter. Instead of optimizing broadcast traffic for these issues, it is optimized for bandwidth utilization because there is potentially a very large number of attendees receiving the streamed media.
  
 **Transmissão de Reunião do Skype com usuários da rede do cliente**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## <a name="call-flow-patterns-by-deployment-type"></a>Padrões de fluxo de chamadas por tipo de implantação

With the common call flow examples above, and an understanding of the general principles that control traffic patterns, the tables below provide a summary of the traffic patterns for a large combination of deployment and usage scenarios. These tables do not capture all possible combinations of call flows, but should help you to further understand the general principles of call flow.
  
Data is transmitted and is listed as being local to the organization; it doesn't leave the customer network, Internet, or ExpressRoute. The patterns listed below are based on the most common network settings, such as firewalls, federation, and Internet, and assume that all organizations involved in multi-party or federated flows have ExpressRoute. In practice, having different settings could result in different traffic patterns than those that are listed below.
  
### <a name="call-flows-for-skype-for-business-online"></a>Fluxos de chamadas do Skype for Business Online

Os cenários de uso do Skype for Business Online envolvem usuários que estão online e podem estar ligando de sua rede interna ou usando a Internet. Os servidores locais não fazem parte desses cenários. Portanto, qualquer mídia relacionada à conferência ou à PSTN fluirá para a nuvem do Office 365. O servidor de borda dos usuários online também estará na nuvem.
  
 **Resumo do fluxo de chamadas do Skype for Business Online**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: ambos em sua rede.  <br/> |Rota Expressa  <br/> |local  <br/> |[Peer-to-peer call for Office 365 users from within customer network](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Chamada ponto a ponto  <br/> |Two clients, one on your network (internal) and the other client on the Internet (external).  <br/> |Usuário interno: Rota Expressa  <br/> Usuário externo: Internet  <br/> |Usuário interno: Rota Expressa  <br/> Usuário externo: Internet para servidor de borda do Office 365.  <br/> |[Peer-to-peer call for Office 365 users from within customer network](call-flow-using-expressroute.md#bk_Figure2) <br/> |Supõe que o firewall bloqueia as conexões diretas entre os clientes, o que exige um servidor de borda online. O tráfego do usuário interno para o servidor de borda online segue um caminho similar ao do servidor de conferência para chamada em conferência.  <br/> |
|Chamada ponto a ponto para um usuário em uma organização federada  <br/> |Dois clientes: em sua rede (interna) e no usuário online na rede da organização federada (federada).  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Supõe que o firewall bloqueia as conexões diretas entre os clientes, o que exige um servidor de borda online. O tráfego do usuário interno para o servidor de borda online segue um caminho similar ao do servidor de conferência para chamada em conferência.  <br/> |
|Ingressar em chamada em conferência por usuário na rede do cliente  <br/> |Cliente na sua rede e servidor de conferência na nuvem do Office 365.  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Ingressar em chamada em conferência por usuário na Internet  <br/> |Cliente na Internet e servidor de conferência na nuvem do Office 365.  <br/> |Internet  <br/> |Internet  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Ingressar em conferência hospedada por outro servidor local da empresa  <br/> |Cliente na sua rede e servidor de conferência em datacenter de terceiros.  <br/> |Internet  <br/> |Internet  <br/> |Não se aplica  <br/> |Como o servidor de conferência que hospeda a conferência está em uma rede local de outro cliente, nenhum dado passaria pela nuvem da Microsoft.  <br/> |
|Chamada PSTN  <br/> |Client in customer network and Phone System servers in Office 365 cloud  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Chamada PSTN  <br/> |Client on the Internet and Phone System servers in Office 365 cloud  <br/> |Internet  <br/> |Internet  <br/> |Não se aplica  <br/> |A mídia e a sinalização fluirão para o datacenter do Office 365. Como o ponto de extremidade do cliente está na Internet, todos os dados fluirão para o datacenter da Microsoft pela Internet (mesmo se um servidor de borda online for necessário para conectividade).  <br/> |
   
> [!NOTE]
> ExpressRoute will be used on the media path from a user located on the corporate network to an online Edge Server, but won't be used if the Edge server for another customer's on-premises deployment is used. 
  
### <a name="call-flows-for-skype-for-business-hybrid"></a>Fluxos de chamadas do Skype for Business Híbrido

Os fluxos de chamadas híbridos são aplicáveis quando há uma implantação do Skype for Business que inclui pelo menos alguns usuários hospedados localmente. The call flows in this section include both on-premises conferences and peer-to-peer or PSTN calls with at least one on-premises homed user.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: na rede do cliente e hospedados localmente  <br/> |Local  <br/> |local  <br/> |[Peer-to-peer call for Office 365 users from within customer network](call-flow-using-expressroute.md#bk_Figure2) <br/> |Como os usuários estão hospedados localmente, a sinalização flui localmente até o datacenter local, em vez fluir para a nuvem do Office 365.  <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: ambos se conectam pela rede do cliente. Um está hospedado online; o outro, localmente.  <br/> |Usuário online: Rota Expressa  <br/> Usuário local: local  <br/> |local  <br/> |[Peer-to-peer call for Office 365 users from within customer network](call-flow-using-expressroute.md#bk_Figure2) <br/> |Somente o usuário hospedado online envia tráfego de sinalização para a nuvem do Office 365.  <br/> |
|Chamada ponto a ponto para um usuário em uma organização federada  <br/> |Dois clientes: usuário local na rede do cliente (interna) e usuário online na rede da empresa federada (federada).  <br/> |Usuário interno: local  <br/> Usuário federado: Rota Expressa  <br/> |Internet ou Rota Expressa (depende se for usado o servidor de borda online ou local)  <br/> |[Online user on your network joining a conference that is hosted Online](call-flow-using-expressroute.md#bk_Figure3) and part of [On-premises Edge server with Office 365 hosted conferences](call-flow-using-expressroute.md#bk_Figure5) (for media traffic). <br/> |Supõe que o firewall bloqueia as conexões diretas entre os clientes, o que exige um servidor de borda online. A negociação ICE oferecerá tanto servidores online (pelo usuário online) quanto servidores de borda locais (pelo usuário local) para conectividade.  <br/> |
|Ingressar em chamada em conferência por usuário na rede do cliente (conferência agendada pelo usuário online)  <br/> |Usuário local na sua rede e servidor de conferência na nuvem do Office 365.  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Server resources for conference call are defined by the meeting organizer. In this case, it was scheduled by an Online user, so resources are in the Office 365 cloud.  <br/> |
|Chamada PSTN  <br/> |Usuário local em sua rede e o datacenter local do Skype for Business.  <br/> |Local  <br/> |Local  <br/> |[Chamada PSTN usando o Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Cenário similar para uso do Cloud Connector Edition, exceto que o usuário está hospedado localmente. Portanto, a sinalização permanece dentro de sua rede.  <br/> |
   
### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Fluxos de chamadas para Skype for Business com Cloud Connector

Os usuários que vão se conectar ao Cloud Connector Edition estão todos hospedados online. Isso significa que as conferências estarão online, e a sinalização seguirá os mesmos padrões que os dos usuários online. Para cenários que não são de chamadas PSTN, o fluxo de chamadas ocorrerá exatamente como descrito anteriormente para o Skype for Business Online.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada PSTN  <br/> |Usuário online em sua rede usando o Cloud Connector Edition.  <br/> |local  <br/> |local  <br/> |[Chamada PSTN usando o Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Chamada PSTN  <br/> |Usuário online usando a Internet com o Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combination of [On-premises Edge server with Office 365 hosted conferences](call-flow-using-expressroute.md#bk_Figure5) and [PSTN call using Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Os usuários de Internet se conectam pelo servidor de borda que é incluído no Cloud Connector, e o Cloud Connector se conecta à rede PSTN.  <br/> |
   
## <a name="related-topics"></a>Tópicos relacionados

[Documentação do ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)

  
 