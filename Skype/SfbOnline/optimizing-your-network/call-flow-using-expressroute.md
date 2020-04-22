---
title: Fluxo de chamadas usando Rota Expressa
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Optimization
description: Este artigo ajuda a explicar os princípios centrais do fluxo de chamadas do Skype for Business Online e da Rota Expressa, além de fornecer alguns exemplos detalhados de fluxos de chamadas para que você possa entender e planejar corretamente.
ms.openlocfilehash: 8460d845302fbca2ab10e5c43f9feda8af45a321
ms.sourcegitcommit: ea54990240fcdde1fb061489468aadd02fb4afc7
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/22/2020
ms.locfileid: "43777586"
---
# <a name="call-flow-using-expressroute"></a>Fluxo de chamadas usando Rota Expressa

Este artigo ajuda a explicar os princípios centrais do fluxo de chamadas do Skype for Business Online e da Rota Expressa, além de fornecer alguns exemplos detalhados de fluxos de chamadas para que você possa entender e planejar corretamente.

Se você estiver implantando o Skype for Business online como parte do Office 365, do Skype for Business Server Hybrid ou do Skype for Business Cloud Connector Edition, será necessário entender a comunicação entre o cliente e os servidores do Skype for Business e o fluxo de chamadas para que você possa planejar, implantar, operar e solucionar problemas de seus serviços do Skype for Business online com eficiência.

## <a name="call-flow-overview"></a>Visão geral do fluxo de chamadas

Este documento descreve os segmentos de rede que podem transportar dados para esses fluxos de chamadas e ajuda você a entender qual tráfego permanecerá local na sua rede, em comparação com o tráfego que vai viajar pela Internet ou via ExpressRoute. Saber qual tráfego usa o ExpressRoute o ajudará a avaliar os benefícios que a sua empresa receberá usando o ExpressRoute, além de ajudar você a entender a orientação de implantação do ExpressRoute para validar e solucionar problemas de implantação depois de decidir usar o ExpressRoute.

Os fluxos de chamadas descritos aqui podem ser afetados por uma série de fatores que você controla, inclusive as regras de firewall, a configuração NAT, proxies e a configuração do roteador. Este documento presume que as configurações recomendadas já estão aplicadas. Essas configurações recomendadas são descritas em:

- [Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Visão geral do ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Rota Expressa do Azure](https://azure.microsoft.com/services/expressroute/)

A configuração e as configurações que não seguiram as etapas de configuração encontradas na documentação acima podem ter fluxos de chamadas diferentes daqueles que documentamos aqui. Além disso, você pode se encontrar com problemas de configuração, como rotas de rede assimétricas e não otimizadas, ou protocolos de transporte não otimizados. O roteamento assimétrico é uma consideração importante sempre que o ExpressRoute estiver envolvido, porque o ExpressRoute apresenta um segundo caminho para o Office 365, que cria a possibilidade de uma rota que usa a Internet em uma direção e outra rota que usa o ExpressRoute na outra direção. Isso pode fazer com que o tráfego seja bloqueado na direção de retorno se ele atravessar um firewall stateful.

## <a name="network-segments-and-traffic-types"></a>Segmentos de rede e tipos de tráfego

### <a name="network-segments"></a>Segmentos de rede

Antes de explicar o fluxo de chamadas, precisamos definir alguns termos que ajudarão você a entender os segmentos de rede e os tipos de mídia usados no Skype for Business Online.

Os diagramas de fluxo de chamadas abaixo mostram quatro segmentos de rede diferentes, cada um deles gerenciados por organizações diferentes (sua rede interna, seu provedor de serviços de rede e seus parceiros de redes pares na Internet e Microsoft) que têm características de desempenho diferentes. Para obter diretrizes sobre destinos de desempenho de rede, confira [qualidade de mídia e desempenho de conectividade de rede no Skype for Business online](media-quality-and-network-connectivity-performance.md).

A seguir, apresentamos todos os segmentos de rede sobre os quais falaremos.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **Sua rede** Esse é o segmento de rede que faz parte da sua rede geral que você controla e gerencia. Isso inclui todas as suas conexões em seus escritórios, seja com fio ou sem fio, entre prédios do escritório, em datacenters locais e suas conexões com provedores de Internet ou com parceiros do ExpressRoute.

Geralmente, a borda da sua rede tem uma ou mais DMZ com firewalls e/ou servidores proxy, que impõem as políticas de segurança da sua organização e que só permitem certos tráfegos de rede que você configurou e configurou. Como você gerencia essa rede, você tem controle direto sobre o desempenho da sua rede, e é altamente recomendável que você conclua as avaliações de rede para validar o desempenho tanto dentro dos sites da sua rede quanto da rede para o Skype for Business online. Para ver os requisitos de desempenho, consulte [qualidade de mídia e desempenho de conectividade de rede no Skype for Business online](media-quality-and-network-connectivity-performance.md).

 **Acesso à Internet** Este é o segmento de rede que faz parte de sua rede geral que será usado por usuários que estão se conectando ao Skype for Business online de fora da sua rede e que é usado para todas as conexões quando o ExpressRoute não está configurado. A Internet e todas as suas conexões não são gerenciadas por você ou pela Microsoft, portanto, os caminhos de desempenho e roteamento não podem ser determinados, e isso terá o maior impacto no fluxo de chamadas geral e na qualidade.

 **ExpressRoute** Este é o segmento de rede que faz parte de sua rede geral que lhe dará uma conexão privada dedicada para a rede da Microsoft. Esta é a opção recomendada para conectar sua rede à rede Microsoft (Office 365 datacenters) para todas as cargas de trabalho que dependem da velocidade da rede e do desempenho, como a comunicação em tempo real do Skype for Business online. As conexões do ExpressRoute são feitas entre a rede e a rede da Microsoft usam [provedores de conectividade do expressroute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) para fornecer uma rede privada e gerenciada, com tempo limite de 99,9% e suporte para a QoS (qualidade de serviço) que pode melhorar o desempenho de mídia em tempo real durante períodos de congestionamento de rede.

 **Rede da Microsoft** Esse é o segmento de rede que faz parte de sua rede geral compatível com os serviços do Office 365. Isso inclui toda a comunicação entre os servidores online do Office 365. Isso pode incluir tráfego que atravessa o backbone da rede Microsoft e é transmitido entre regiões geográficas.

### <a name="types-of-traffic"></a>Tipos de tráfego

O tráfego de rede do Skype for Business online se encaixa em duas categorias amplas, mostradas como caminhos separados no fluxo de chamadas:

 **Mídia em tempo real** são dados encapsulados dentro do RTP (protocolo de transporte em tempo real) e compatível com áudio, vídeo, compartilhamento de aplicativos e cargas de trabalho de transferência de arquivos. Em geral, o tráfego de mídia é altamente sensível à latência, portanto, você quer que esse tráfego leve o caminho mais direto possível e use UDP como o protocolo de camada de transporte porque o uso de TCP apresenta maior latência.

 **Sinalização** é o link de comunicação entre o cliente e o servidor ou outros clientes que são usados para controlar atividades (por exemplo, quando uma chamada é iniciada) e enviar mensagens de chat. A maior parte do tráfego de sinalização usa o protocolo SIP, embora alguns clientes usem interfaces REST baseadas em HTTP. Para simplificar, estamos considerando um sinal de variedade que pode viajar por meio de conexões HTTP e HTTPS ou TLS nesse tipo de tráfego. É importante entender que esse tráfego é muito menos sensível à latência, mas pode causar paralisações de serviço ou tempos limite de chamadas se a latência entre os pontos de extremidade ultrapassar vários segundos.

Os destinos para esse tráfego são encontrados nas [URLs do office 365 e nos intervalos de endereços IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) de todos os serviços do Office 365. Para cada URL, ele indica se essa parte do tráfego pode atravessar o ExpressRoute para o Office 365. Para os diagramas que mostram que a Internet ainda está sendo usada para algum tráfego quando o ExpressRoute está habilitado, consulte o [Azure ExpressRoute para Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). É importante compreender que mesmo URLs que são listadas como roteáveis pelo ExpressRoute também são roteáveis pela Internet. Isso significa que, em alguns cenários, a determinação sobre se a Internet ou rota expressa será usada depende da localização do cliente e da configuração dos servidores proxy e firewalls. Também é importante compreender que, como nem todas as URLs associadas ao Office 365 podem usar o ExpressRoute, uma conexão à Internet é necessária, mesmo se você comprar o ExpressRoute de um parceiro do ExpressRoute.

O tráfego que só pode ser enviado pela Internet inclui dependências comuns à Internet, como listas de certificados revogados (CRLs), pesquisas de DNS e resolução de nome, URLs para serviços compartilhados do Office 365, como para o centro de administração do Microsoft 365 e alguns recursos de comunicação não em tempo real do Skype for Business Online, como telemetria e Federação para interoperabilidade com o Skype Consumer, como mídias de transmissão de reunião do Skype. Para ajudá-lo a tomar decisões, consulte o [roteiro com o ExpressRoute para o Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) para obter mais considerações quando você estiver planejando o roteamento de rede.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Princípios para fluxos de chamadas com o Skype for Business

Antes de nos aprofundarmos em cenários específicos de fluxos de chamadas, existem seis princípios gerais que ajudam a entender os fluxos de chamadas do Skype for Business.

1. Uma conferência do Skype for Business é hospedada na mesma região em que o organizador de conferências é hospedado. Isso se encontra na nuvem do Office 365 se o organizador for um usuário online ou em um datacenter local se o organizador da reunião for um usuário local.

2. O tráfego de mídia enviado de um cliente para uma conferência hospedada sempre vai para o servidor em que a conferência está hospedada. Pode ser um servidor local dentro de um datacenter que você gerencia ou um servidor online dentro da nuvem do Office 365. No entanto, um servidor de borda sempre é usado para o fluxo de mídia para conferências online.

3. O tráfego de mídia para chamadas ponto a ponto usa a rota mais direta que estiver disponível. A rota preferencial é direta para o ponto (cliente) remoto, mas se a rota não estiver disponível, porque o firewall está bloqueando o tráfego ou algo parecido, então um ou mais servidores de borda transmitirão o tráfego.

4. O tráfego de sinalização sempre irá para o servidor onde o usuário está localizado, Online ou no local. Um servidor de borda será usado se não for possível conectar-se diretamente ao servidor Front-End.

5. Os usuários que participam de uma conferência hospedada online sempre usarão um servidor de borda (ou dois, se necessário, dependendo das configurações de firewall do cliente).

6. Os usuários que ingressam em uma conferência hospedada no local normalmente não usarão um servidor de borda se estiverem se conectando pela mesma rede que contém a implantação local, mas usarão um ou dois servidores de borda quando estiverem se conectando de fora da sua rede.

Para saber mais sobre os detalhes no caminho de mídia que é escolhido, consulte [conectividade de mídia de borda Ice](https://aka.ms/AVEdge). Embora este vídeo seja sobre o Lync Server 2013, os princípios e protocolos ainda se aplicam ao Skype for Business.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Fluxos de chamadas do Skype for Business com Rota Expressa

Agora que você tem uma compreensão dos quatro segmentos de rede diferentes e alguns princípios gerais de orientação para fluxos de chamadas do Skype for Business, você pode usar essas informações para ajudá-lo a entender qual tráfego do Skype for Business atravessará um segmento de rede do ExpressRoute.

Em geral, o tráfego de rede usará a conexão da Rota Expressa, caso um ponto de extremidade seja sua rede e o outro ponto de extremidade seja o datacenter do Office 365. Isso incluirá o tráfego de sinalização entre o cliente e o servidor, o tráfego de mídia usado durante as chamadas em conferência ou chamadas ponto a ponto que usam o servidor de borda online.

O tráfego não percorrerá a conexão do ExpressRoute se os dois pontos de extremidade puderem se comunicar diretamente pela Internet ou se estiverem localizados em sua rede. Isso inclui mídia para chamadas ponto a ponto, tráfego da Internet destinado a uma implantação local ou qualquer tráfego entre a Internet e servidores de Edge do Office 365. Um exemplo disso seria um usuário ingressando em uma conferência online de um hotel.

## <a name="basic-skype-for-business-call-flow"></a>Como usar o fluxo de chamadas do Skype for Business

Para ajudá-lo a aplicar os princípios gerais de fluxos de chamadas do Skype for Business descritos anteriormente, a próxima seção deste artigo contém vários diagramas para referência. Não se trata de uma lista exaustiva de todos os fluxos de chamadas possíveis, mas tem como finalidade ajudá-lo a aplicar os princípios detalhados anteriormente. Além disso, os cenários nos diagramas foram selecionados para abranger tipos comuns de implantação, incluindo Online, Híbrido, Cloud Connector e um caso especial: a Transmissão de Reunião do Skype.

> [!NOTE]
> Um subconjunto de tráfego usado pelo Skype for Business não está roteável pelo ExpressRoute e sempre terá um caminho da Internet. Consulte as [URLs e os intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para determinar as URLs que podem ser afetadas.

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>Chamada ponto a ponto para o Microsoft 365 ou o Office 365 usuário de dentro da rede do cliente
<a name="bk_Figure2"> </a>

Para chamadas ponto a ponto, o tráfego de mídia sempre usa a rota mais direta até o seu destino. No entanto, o tráfego de sinalização vai para um datacenter do Office 365 onde o usuário online está localizado. Visto que os dois usuários estão na mesma WAN e nada impede a comunicação direta entre os clientes, a mídia flui diretamente entre eles. O tráfego de sinalização, dos dois usuários, usa a conexão da Rota Expressa que está destinada a cada datacenter da organização. Para mostrar o fluxo de chamadas neste cenário, veja isto.

 **Fluxo de chamadas ponto a ponto**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Usuário online de sua rede ingressando em uma conferência hospedada online
<a name="bk_Figure3"> </a>

No exemplo ponto a ponto, o tráfego de mídia sempre usa a rota mais direta para seu destino. No entanto, para uma conferência online, o destino está na nuvem do Office 365. Isso significa que o tráfego de mídia para todos os usuários que ingressam na conferência de dentro da rede atravessará a conexão do ExpressRoute e o tráfego de sinalização se transformará na nuvem do Office 365. O elemento gráfico abaixo mostra que a mídia e a sinalização percorram a conexão do ExpressRoute para um usuário em sua rede e percorra diretamente a Internet para os usuários que estão conectados à Internet de fora da sua rede, como de uma lanchonete ou Hotel.

Lembre-se de que o local de uma conferência é definido pelo organizador da reunião e não pelos participantes. Isso significa que, se a reunião for agendada por um cliente local, o tráfego de mídia não fluirá para a nuvem do Office 365 pelo ExpressRoute, mas, em vez disso, percorreria a Internet para o datacenter local do organizador da reunião.

O destino da mídia de conferências online será um datacenter na nuvem do Office 365, mas esse datacenter pode estar em uma região geográfica diferente daquela dos usuários que estão participando da conferência. Isso pode acontecer de uma das seguintes maneiras:

- Se o organizador da reunião for de uma empresa diferente da dos participantes, e se a organização dele estiver hospedada em outra localização geográfica ou país/região.

- Se um usuário estiver participando de um país/região diferente de onde a organização da empresa está localizada, pelo fato de a empresa ser multinacional ou o usuário estar viajando.

A boa notícia sobre o uso do ExpressRoute nesse cenário é que com o complemento Premium do ExpressRoute, os dados que acompanham o caminho do ExpressRoute passarão automaticamente pelo backbone da Microsoft independentemente da região geográfica do organizador do datacenter da organização da reunião.

 **Usuário online com fluxo de chamadas de reunião online**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Ingressando em uma conferência hospedada por usuário local em implantação híbrida
<a name="bk_Figure3"> </a>

Lembre-se de que os servidores de conferência que dão suporte a conferências hospedadas são determinados por onde o organizador da reunião é hospedado. Nesse cenário, a mídia para todos os usuários que participam de uma conferência programada por um usuário local em uma implantação híbrida fluirá para um datacenter local. A sinalização de usuários online online será estabelecida por meio de sua organização na nuvem do Office 365, enquanto a mídia tentará uma conexão direta. Nesse cenário, como os dois usuários estão se conectando de dentro da rede, é possível usar uma conexão de mídia direta, portanto, o ExpressRoute é usado apenas para o tráfego de sinalização para o usuário doméstico online. Se um usuário hospedado online se conectar da Internet, a mídia poderá atravessar o ExpressRoute se um servidor de borda online for usado para conexão.

 **Conferência hospedada por um fluxo de chamadas de usuário híbrido**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-office-365-hosted-conferences"></a>Servidor de borda local com conferências hospedadas no Office 365
<a name="bk_Figure5"> </a>

Quando um usuário híbrido entra em uma conferência hospedada online, sabemos que a sinalização e a mídia serão destinadas à nuvem do Office 365, e como o usuário está se unindo da Internet, normalmente um caminho de Internet direto seria usado. No entanto, em alguns casos, por exemplo, devido a restrições de firewall, um caminho de Internet direto não está disponível. Nesse caso, um servidor de borda local pode retransmitir o tráfego de mídia, o que faz com que o tráfego de mídia retorne à sua rede local antes de atravessar o circuito do ExpressRoute para a nuvem do Office 365.

 **Usuário local ingressando em uma chamada em conferência online através de servidor de borda local**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Chamada PSTN usando o Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

Usar o [Skype for Business online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) fornece conectividade PSTN usando recursos locais, como um tronco SIP ou um gateway PSTN, ou usando um dispositivo de hardware mínimo para integração com o Skype for Business. Com o Cloud Connector Edition, os usuários são hospedados online e atuam como usuários normais online quando não envolvem planos de chamada. A sinalização para cenários PSTN se transportará entre o cliente e a nuvem em uma conexão do ExpressRoute, se disponível, e o tráfego de mídia permanecerá dentro da sua WAN. Nesse caso, a sinalização se transforma na nuvem do Office 365 e termina no conector da nuvem.

 **Chamada PSTN via sistema telefônico no Office 365 e no conector de nuvem**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Transmissão de Reunião do Skype com usuários ingressando pela rede do cliente
<a name="bk_Figure6"> </a>

A transmissão de reunião do Skype é um caso de uso especial, que consiste em uma reunião de duas partes com cada parte com diferentes perfis de transporte de rede. A primeira parte e aquela que é mais importante de um ponto de vista de desempenho de rede é a reunião interna. Esta é a porção em tempo real da reunião que inclui um ou mais pontos de extremidade do cliente se conectando ao servidor de conferência na nuvem do Office 365. Os dados transmitidos usando esta parte da reunião são exatamente iguais aos do exemplo acima, com um usuário do Office 365 ingressando em uma conferência online.

O que torna a transmissão de reunião do Skype exclusiva é que a reunião é distribuída para um grande número de participantes da conferência usando um serviço de transmissão de transmissão. Esse serviço de transmissão de transmissão não está roteável pelo ExpressRoute, mas em vez disso usa a Internet com o suporte opcional de serviços de rede de distribuição de conteúdo (CDN). É útil reconhecer que o fluxo de transmissão é um fluxo de mídia unidirecional, pois os participantes escutam, mas não falam e dão suporte ao buffer, portanto, é bem menos sensível a problemas de desempenho de rede, como latência, perda de pacote e Tremulação. Em vez de otimizar o tráfego de transmissão para esses problemas, ele é otimizado para uso de largura de banda porque é potencialmente um número muito grande de participantes recebendo a mídia transmitida.

 **Transmissão de Reunião do Skype com usuários da rede do cliente**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Padrões de fluxo de chamadas por tipo de implantação

Com os exemplos de fluxo de chamadas comuns acima e uma compreensão dos princípios gerais que controlam os padrões de tráfego, as tabelas a seguir fornecem um resumo dos padrões de tráfego para uma combinação grande de cenários de implantação e uso. Essas tabelas não capturam todas as combinações possíveis de fluxos de chamadas, mas devem ajudá-lo a entender melhor os princípios gerais do fluxo de chamadas.

Os dados são transmitidos e listados como sendo locais para a organização; Ele não deixa a rede do cliente, a Internet ou o ExpressRoute. Os padrões listados abaixo são baseados nas configurações de rede mais comuns, como firewalls, Federação e Internet, e presumimos que todas as organizações envolvidas em fluxos de vários participantes ou federados tenham o ExpressRoute. Na prática, ter configurações diferentes pode resultar em diferentes padrões de tráfego do que os listados abaixo.

### <a name="call-flows-for-skype-for-business-online"></a>Fluxos de chamadas do Skype for Business Online

Os cenários de uso do Skype for Business online envolvem usuários que estão hospedados online e podem estar chamando a partir de sua rede interna ou da Internet. Os servidores locais não fazem parte desses cenários, portanto, todas as mídias relacionadas a conferência ou PSTN fluirão para a nuvem do Office 365, e o servidor de borda de usuários online também estará na nuvem.

 **Resumo do fluxo de chamadas do Skype for Business Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: ambos em sua rede.  <br/> |Rota Expressa  <br/> |local  <br/> |[Chamada ponto a ponto para o Microsoft 365 ou o Office 365 usuário de dentro da rede do cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Chamada ponto a ponto  <br/> |Dois clientes, um na rede (interna) e outro cliente na Internet (externo).  <br/> |Usuário interno: Rota Expressa  <br/> Usuário externo: Internet  <br/> |Usuário interno: Rota Expressa  <br/> Usuário externo: Internet para servidor de borda do Office 365.  <br/> |[Chamada ponto a ponto para usuários do Office 365 em uma rede de clientes](call-flow-using-expressroute.md#bk_Figure2) <br/> |Assume que o firewall bloqueia conexões diretas entre clientes, que exigem um servidor de borda online. O tráfego do usuário interno para o servidor de borda online segue um caminho semelhante ao do servidor de conferência para chamada em conferência.  <br/> |
|Chamada ponto a ponto para um usuário em uma organização federada  <br/> |Dois clientes: em sua rede (interna) e no usuário online na rede da organização federada (federada).  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Supõe que o firewall bloqueia as conexões diretas entre os clientes, o que exige um servidor de borda online. O tráfego do usuário interno para o servidor de borda online segue um caminho similar ao do servidor de conferência para chamada em conferência.  <br/> |
|Ingressar em chamada em conferência por usuário na rede do cliente  <br/> |Cliente na sua rede e servidor de conferência na nuvem do Office 365.  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Ingressar em chamada em conferência por usuário na Internet  <br/> |O cliente está na Internet e no servidor de conferência na nuvem do Office 365.  <br/> |Internet  <br/> |Internet  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Ingressar em conferência hospedada por outro servidor local da empresa  <br/> |Cliente na sua rede e servidor de conferência em datacenter de terceiros.  <br/> |Internet  <br/> |Internet  <br/> |Não se aplica  <br/> |Como o servidor de conferência que hospeda a conferência está em uma rede local de outro cliente, nenhum dado passaria pela nuvem da Microsoft.  <br/> |
|Chamada PSTN  <br/> |Cliente na rede do cliente e servidores de sistema telefônico na nuvem do Office 365  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Chamada PSTN  <br/> |Cliente na Internet e servidores de sistema telefônico na nuvem do Office 365  <br/> |Internet  <br/> |Internet  <br/> |Não se aplica  <br/> |A mídia e a sinalização fluirão para o datacenter do Office 365. Como o ponto de extremidade do cliente está na Internet, todos os dados fluirão para o Microsoft datacenter pela Internet (mesmo se um servidor de borda online for necessário para conectividade).  <br/> |

> [!NOTE]
> O ExpressRoute será usado no caminho de mídia de um usuário localizado na rede da empresa para um servidor de borda online, mas não será usado se o servidor de borda para a implantação local de outro cliente for usado.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Fluxos de chamadas do Skype for Business Híbrido

Os fluxos de chamadas híbridas se aplicam quando você tem uma implantação do Skype for Business que inclui pelo menos alguns usuários que são hospedados no local. Os fluxos de chamadas nesta seção incluem conferências locais e chamadas ponto a ponto ou PSTN com pelo menos um usuário local no local.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: na rede do cliente e hospedados localmente  <br/> |Local  <br/> |local  <br/> |[Chamada ponto a ponto para o Microsoft 365 ou o Office 365 usuário de dentro da rede do cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Como os usuários estão hospedados localmente, a sinalização flui localmente até o datacenter local, em vez fluir para a nuvem do Office 365.  <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: ambos se conectam pela rede do cliente. Um está hospedado online; o outro, localmente.  <br/> |Usuário online: Rota Expressa  <br/> Usuário local: local  <br/> |local  <br/> |[Chamada ponto a ponto para usuários do Office 365 em uma rede de clientes](call-flow-using-expressroute.md#bk_Figure2) <br/> |Somente o usuário hospedado online envia tráfego de sinalização para a nuvem do Office 365.  <br/> |
|Chamada ponto a ponto para um usuário em uma organização federada  <br/> |Dois clientes: usuário local na rede do cliente (interna) e usuário online na rede da empresa federada (federada).  <br/> |Usuário interno: local  <br/> Usuário federado: Rota Expressa  <br/> |Internet ou Rota Expressa (depende se for usado o servidor de borda online ou local)  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) e parte do [servidor de borda local com conferências hospedadas no Office 365](call-flow-using-expressroute.md#bk_Figure5) (para tráfego de mídia). <br/> |Assume que um firewall bloqueia conexões diretas entre clientes, exigindo servidor de borda online. A negociação ICE oferecerá os servidores online (pelo usuário online) e de borda local (pelo usuário local) para conectividade.  <br/> |
|Ingressar em chamada em conferência por usuário na rede do cliente (conferência agendada pelo usuário online)  <br/> |Usuário local na sua rede e servidor de conferência na nuvem do Office 365.  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Os recursos do servidor para a chamada em conferência são definidos pelo organizador da reunião. Nesse caso, ele foi agendado por um usuário online, portanto, os recursos estão na nuvem do Office 365.  <br/> |
|Chamada PSTN  <br/> |Usuário local em sua rede e o datacenter local do Skype for Business.  <br/> |Local  <br/> |Local  <br/> |[Chamada PSTN usando o Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Cenário similar para uso do Cloud Connector Edition, exceto que o usuário está hospedado localmente. Portanto, a sinalização permanece dentro de sua rede.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Fluxos de chamadas para Skype for Business com Cloud Connector

Os usuários que vão se conectar ao Cloud Connector Edition estão todos hospedados online. Isso significa que as conferências estarão online, e a sinalização seguirá os mesmos padrões que os dos usuários online. Para cenários que não são de chamadas PSTN, o fluxo de chamadas ocorrerá exatamente como descrito anteriormente para o Skype for Business Online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada PSTN  <br/> |Usuário online em sua rede usando o Cloud Connector Edition.  <br/> |local  <br/> |local  <br/> |[Chamada PSTN usando o Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Chamada PSTN  <br/> |Usuário online usando a Internet com o Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinação de [servidor de borda local com conferências hospedadas do Office 365](call-flow-using-expressroute.md#bk_Figure5) e [chamada PSTN usando o Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6).  <br/> |Os usuários de Internet se conectam pelo servidor de borda que é incluído no Cloud Connector, e o Cloud Connector se conecta à rede PSTN.  <br/> |

## <a name="related-topics"></a>Tópicos relacionados

[Documentação do ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)


