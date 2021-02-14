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
ms.openlocfilehash: b65d7b1e3677c82e562de63257f28ad1561d7190
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164630"
---
# <a name="call-flow-using-expressroute"></a>Fluxo de chamadas usando Rota Expressa

Este artigo ajuda a explicar os princípios centrais do fluxo de chamadas do Skype for Business Online e da Rota Expressa, além de fornecer alguns exemplos detalhados de fluxos de chamadas para que você possa entender e planejar corretamente.

Se você estiver implantando o Skype for Business Online como parte do Microsoft 365 ou office 365, do Skype for Business Server Híbrido ou do Skype for Business Cloud Connector Edition, precisará entender a comunicação entre o cliente e os servidores do Skype for Business e o fluxo de chamadas para que você possa planejar, implantar, operar e solucionar problemas eficazmente com seus serviços do Skype for Business Online.

## <a name="call-flow-overview"></a>Visão geral do fluxo de chamadas

Este documento descreve os segmentos de rede que podem carregar dados para esses fluxos de chamada e ajuda você a entender qual tráfego permanecerá local para sua rede em comparação com o tráfego que viajará pela Internet ou pelo ExpressRoute. Saber qual tráfego usa o ExpressRoute ajudará você a avaliar os benefícios que sua empresa receberá usando o ExpressRoute, além de ajudá-lo a entender as diretrizes de implantação do ExpressRoute para validar e solucionar problemas de implantação depois que você decidir usar o ExpressRoute.

Os fluxos de chamadas descritos aqui podem ser afetados por uma série de fatores que você controla, inclusive as regras de firewall, a configuração NAT, proxies e a configuração do roteador. Este documento presume que as configurações recomendadas já estão aplicadas. Essas configurações recomendadas são descritas em:

- [Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)

- [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

- [Visão geral do ExpressRoute](https://docs.microsoft.com/azure/expressroute/expressroute-introduction)

- [Rota Expressa do Azure](https://azure.microsoft.com/services/expressroute/)

Configurações e configurações que não seguiram as etapas de configuração encontradas na documentação acima podem ter fluxos de chamada diferentes daqueles documentados aqui. Além disso, você pode encontrar problemas de configuração, como rotas de rede assimétricas e não ideais, ou protocolos de transporte não ideais. O roteamento assimétrico é uma consideração importante sempre que o ExpressRoute está envolvido, pois o ExpressRoute introduz um segundo caminho para o Office 365, que cria a possibilidade de uma rota que usa a Internet em uma direção e outra rota que usa o ExpressRoute em outra direção. Isso pode fazer com que o tráfego seja bloqueado na direção de retorno se ele usar um firewall com estado.

## <a name="network-segments-and-traffic-types"></a>Segmentos de rede e tipos de tráfego

### <a name="network-segments"></a>Segmentos de rede

Antes de explicar o fluxo de chamadas, precisamos definir alguns termos que ajudarão você a entender os segmentos de rede e os tipos de mídia usados no Skype for Business Online.

Os diagramas de fluxo de chamada a seguir mostram quatro segmentos de rede diferentes, cada um deles gerenciados por organizações diferentes (sua rede interna, seu provedor de serviços de rede, seus parceiros de peering de Internet e a Microsoft) que têm características de desempenho diferentes. Para ver diretrizes sobre metas de desempenho de rede, consulte Qualidade de Mídia e Desempenho de Conectividade de [Rede no Skype for Business Online.](media-quality-and-network-connectivity-performance.md)

A seguir, apresentamos todos os segmentos de rede sobre os quais falaremos.

![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)

 **Sua rede** Esse é o segmento de rede que faz parte de sua rede geral que você controla e gerencia. Isso inclui todas as suas conexões dentro de seus escritórios, seja com fio ou sem fio, entre edifícios de escritório, com datacenters locais e suas conexões com provedores de Internet ou parceiros do ExpressRoute.

Normalmente, a borda da sua rede tem um ou mais DMZ com firewalls e/ou servidores proxy, que impõem as políticas de segurança da sua organização e que só permitem determinado tráfego de rede que você configurou e configurou. Como você gerencia essa rede, tem controle direto sobre o desempenho da sua rede e é altamente recomendável que você conclua avaliações de rede para validar o desempenho dentro de sites em sua rede e de sua rede para o Skype for Business Online. Para ver os requisitos de desempenho, consulte Qualidade de Mídia e Desempenho de Conectividade [de Rede no Skype for Business Online.](media-quality-and-network-connectivity-performance.md)

 **Internet** Este é o segmento de rede que faz parte de sua rede geral que será usado pelos usuários que estão se conectando ao Skype for Business Online fora da sua rede e é usado para todas as conexões quando o ExpressRoute não estiver configurado. A Internet e todas as suas conexões não são gerenciadas por você ou pela Microsoft, portanto, o desempenho e os caminhos de roteamento não podem ser determinados, e isso terá o maior impacto sobre o fluxo geral de chamadas e a qualidade.

 **Rota Expressa** Esse é o segmento de rede que faz parte de sua rede geral que lhe dará uma conexão dedicada e privada com a rede da Microsoft. Essa é a opção recomendada para conectar sua rede à rede da Microsoft (datacenters do Microsoft 365 ou do Office 365) para todas as cargas de trabalho que dependem da velocidade e do desempenho da rede, como a comunicação em tempo real do Skype for Business Online. As conexões do ExpressRoute são feitas entre sua rede e a rede da Microsoft usam provedores de conectividade do [ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/) para fornecer uma rede privada e gerenciada, com 99,9% de tempo de atividade e suporte para QoS (Qualidade de Serviço) que podem melhorar o desempenho de mídias em tempo real durante períodos de congestionamento da rede.

 **Rede da Microsoft** Este é o segmento de rede que faz parte de sua rede geral que dá suporte aos serviços do Microsoft 365 e do Office 365. Isso inclui toda a comunicação entre servidores online do Microsoft 365 ou do Office 365. Isso pode incluir tráfego que atravessa o backbone de rede da Microsoft e é transmitido entre regiões geográficas.

### <a name="types-of-traffic"></a>Tipos de tráfego

O tráfego de rede do Skype for Business Online se enquadra em duas categorias amplas, mostradas como caminhos separados no fluxo de chamadas:

 **Mídia em tempo real** são dados encapsulados em RTP (Protocolo de Transporte em Tempo Real) e são compatíveis com cargas de trabalho de áudio, vídeo, compartilhamento de aplicativos e transferência de arquivos. Em geral, o tráfego de mídia é altamente sensível à latência, portanto, você deseja que esse tráfego pegue o caminho mais direto possível e use UDP como o protocolo de camada de transporte porque o uso de TCP introduz uma latência mais alta.

 **A sinalização** é o vínculo de comunicação entre o cliente e o servidor ou outros clientes que são usados para controlar atividades (por exemplo, quando uma chamada é iniciada) e entregar IMs. A maioria do tráfego de sinalização usa o protocolo SIP, embora alguns clientes usem interfaces REST baseadas em HTTP. Para facilitar, estamos considerando uma variedade de sinalização que pode viajar por conexões HTTP e HTTPS ou TLS nesse tipo de tráfego. É importante compreender que esse tráfego é muito menos sensível à latência, mas pode causar interrupções de serviço ou tempos limite de chamada se a latência entre os pontos de extremidade exceder vários segundos.

Os destinos desse tráfego são encontrados em [URLs do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) e intervalos de endereços IP para todos os serviços do Microsoft 365 ou do Office 365. Para cada URL, indica se essa parte do tráfego pode percorrer o ExpressRoute para o Microsoft 365 ou o Office 365. Para diagramas que mostram que a Internet ainda é usada para algum tráfego quando o ExpressRoute está habilitado, consulte [Azure ExpressRoute para Office 365.](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd) É importante entender que até mesmo AS URLs listadas como sendo rou rouáveis pelo ExpressRoute também são rupáveis pela Internet. Isso significa que, em alguns cenários, a determinação sobre se a Internet ou o ExpressRoute será usado depende da localização do cliente e da configuração de servidores proxy e firewalls. Também é importante compreender que, como nem todas as URLs associadas ao Microsoft 365 ou Ao Office 365 podem usar o ExpressRoute, é necessária uma conexão com a Internet mesmo que você compre o ExpressRoute de um parceiro do ExpressRoute.

O tráfego que só pode ser enviado pela Internet inclui dependências comuns com a Internet, como listas de certificados revogados (CRLs), pesquisas dns e resolução de nomes, URLs para serviços compartilhados do Microsoft 365 ou office 365, como para o Centro de administração do Microsoft 365, e alguns recursos de comunicação não em tempo real do Skype for Business Online, como telemetria e federação para interoperabilidade com o consumidor do Skype, bem como mídias transmitidas para Transmissão de Reunião do Skype. Para ajudá-lo a tomar decisões, consulte [Roteamento com o ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) para obter mais considerações ao planejar seu roteamento de rede.

## <a name="principles-for-call-flows-with-skype-for-business"></a>Princípios para fluxos de chamadas com o Skype for Business

Antes de nos aprofundarmos em cenários específicos de fluxos de chamadas, existem seis princípios gerais que ajudam a entender os fluxos de chamadas do Skype for Business.

1. Uma conferência do Skype for Business é hospedada na mesma região onde o organizador da conferência está hospedado. Isso está na nuvem se o organizador for um usuário online ou em um datacenter local se o organizador da reunião for um usuário local.

2. O tráfego de mídia enviado de um cliente para uma conferência hospedada sempre vai para o servidor onde a conferência está hospedada. Pode ser um servidor local dentro de um datacenter que você gerencia ou um servidor Online dentro da nuvem. No entanto, um servidor de borda sempre é usado para o fluxo de mídia para conferências online.

3. O tráfego de mídia para chamadas ponto a ponto usa a rota mais direta que estiver disponível. A rota preferencial é direta para o ponto (cliente) remoto, mas se a rota não estiver disponível, porque o firewall está bloqueando o tráfego ou algo parecido, então um ou mais servidores de borda transmitirão o tráfego.

4. O tráfego de sinalização sempre irá para o servidor onde o usuário está localizado, Online ou no local. Um servidor de borda será usado se não for possível conectar-se diretamente ao servidor Front-End.

5. Os usuários que participam de uma conferência hospedada online sempre usarão um servidor de borda (ou dois, se necessário, dependendo das configurações de firewall do cliente).

6. Os usuários que ingressam em uma conferência hospedada no local normalmente não usarão um servidor de borda se estiverem se conectando pela mesma rede que contém a implantação local, mas usarão um ou dois servidores de borda quando estiverem se conectando de fora da sua rede.

Para saber mais sobre os detalhes sobre o caminho de mídia escolhido, consulte [ICE - Conectividade de Mídia de Borda.](https://aka.ms/AVEdge) Embora este vídeo seja sobre o Lync Server 2013, os princípios e protocolos ainda se aplicam ao Skype for Business.

## <a name="skype-for-business-call-flows-with-expressroute"></a>Fluxos de chamadas do Skype for Business com Rota Expressa

Agora que você tem um entendimento dos quatro diferentes segmentos de rede e alguns princípios gerais norteadores para fluxos de chamadas do Skype for Business, pode usar essas informações para ajudá-lo a entender qual tráfego do Skype for Business usará um segmento de rede do ExpressRoute.

Em geral, o tráfego de rede atravessará a conexão do ExpressRoute se um ponto de extremidade estiver em sua rede e o outro ponto de extremidade estiver no datacenter do Microsoft 365 ou do Office 365. Isso incluirá tráfego de sinalização entre cliente e servidor, tráfego de mídia usado durante chamadas em conferência ou chamadas ponto a ponto que usam um servidor de borda online.

O tráfego não atravessará a conexão do ExpressRoute se ambos os pontos de extremidade conseguem se comunicar diretamente pela Internet ou se estão localizados em sua rede. Isso incluirá mídia para chamadas ponto a ponto, tráfego da Internet destinado a uma implantação local ou qualquer tráfego entre a Internet e os Servidores de Borda do Microsoft 365 ou office 365. Um exemplo disso seria um usuário participando de uma conferência online de um hotel.

## <a name="basic-skype-for-business-call-flow"></a>Como usar o fluxo de chamadas do Skype for Business

Para ajudá-lo a aplicar os princípios gerais de fluxos de chamadas do Skype for Business descritos anteriormente, a próxima seção deste artigo contém vários diagramas para referência. Não se trata de uma lista exaustiva de todos os fluxos de chamadas possíveis, mas tem como finalidade ajudá-lo a aplicar os princípios detalhados anteriormente. Além disso, os cenários nos diagramas foram selecionados para abranger tipos comuns de implantação, incluindo Online, Híbrido, Cloud Connector e um caso especial: a Transmissão de Reunião do Skype.

> [!NOTE]
> Um subconjunto de tráfego usado pelo Skype for Business não é rouco pelo ExpressRoute e sempre seguirá um caminho de Internet. Consulte as [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para determinar as URLs que podem ser afetadas.

### <a name="peer-to-peer-call-for-microsoft-365-or-office-365-user-from-within-customer-network"></a>Chamada ponto a ponto para o usuário do Microsoft 365 ou do Office 365 a partir da rede do cliente
<a name="bk_Figure2"> </a>

Para chamadas ponto a ponto, o tráfego de mídia sempre leva a rota mais direta para seu destino. No entanto, o tráfego de sinalização vai para um datacenter do Microsoft 365 ou office 365 onde o usuário online está em casa. Como os dois usuários estão na mesma WAN e nada impede que os clientes se comuniquem diretamente, a mídia flui diretamente entre eles. Tráfego de sinalização, para ambos os usuários, percorre a conexão do ExpressRoute que é destinada ao datacenter de cada organização. Para mostrar o fluxo de chamada neste cenário, veja isto.

 **Fluxo de chamadas ponto a ponto**

![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)

### <a name="online-user-on-your-network-joining-a-conference-that-is-hosted-online"></a>Usuário online de sua rede ingressando em uma conferência hospedada online
<a name="bk_Figure3"> </a>

No exemplo ponto a ponto, o tráfego de mídia sempre leva a rota mais direta para seu destino. No entanto, para uma conferência online, o destino está na nuvem. Isso significa que o tráfego de mídia para todos os usuários que ingressarem na conferência de dentro da sua rede atravessará a conexão do ExpressRoute e o tráfego de sinalização viajará para a nuvem. O gráfico a seguir mostra que a mídia e a sinalização percorrerão a conexão do ExpressRoute para um usuário em sua rede e percorrerão diretamente a Internet para usuários conectados à Internet de fora da sua rede, como de um café ou hotel.

Lembre-se de que o local de uma conferência é definido pelo organizador da reunião e não pelos participantes. Isso significa que, se a reunião fosse agendada por um cliente local, o tráfego de mídia não fluiria para a nuvem pelo ExpressRoute, mas atravessaria a Internet até o datacenter local do organizador da reunião.

O destino de mídia para conferências online será um datacenter dentro da nuvem do Microsoft 365 ou do Office 365, mas o datacenter pode estar em uma região geográfica diferente dos usuários que estão in joining na conferência. Isso pode acontecer de uma das duas maneiras:

- Se o organizador da reunião for de uma empresa diferente da dos participantes, e se a organização dele estiver hospedada em outra localização geográfica ou país/região.

- Se um usuário estiver participando de um país/região diferente de onde a organização da empresa está localizada, pelo fato de a empresa ser multinacional ou o usuário estar viajando.

A boa notícia sobre como usar o ExpressRoute neste cenário é que, com o complemento premium do ExpressRoute, os dados que seguem o caminho do ExpressRoute passarão automaticamente pelo backbone da Microsoft independentemente da região geográfica do organizador do datacenter da organização da reunião.

 **Usuário online com fluxo de chamadas de reunião online**

![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)

### <a name="joining-a-conference-hosted-by-on-premises-user-in-hybrid-deployment"></a>Ingressando em uma conferência hospedada por usuário local em implantação híbrida
<a name="bk_Figure3"> </a>

Lembre-se de que os servidores de conferência que suportam conferências hospedadas são determinados pelo local onde o organizador da reunião está hospedado. Nesse cenário, a mídia para todos os usuários que ingressarem em uma conferência agendada por um usuário local em uma implantação híbrida fluirá para um datacenter local. A sinalização para usuários em casa online será estabelecida por meio de sua organização na nuvem, enquanto a mídia tentará uma conexão direta. Nesse cenário, como os dois usuários estão se conectando de dentro da sua rede, uma conexão de mídia direta é possível, portanto, o ExpressRoute é usado apenas para tráfego de sinalização para o usuário conectado online. Se um usuário conectado online se conectar da Internet, a mídia poderá percorrer o ExpressRoute se um servidor de borda online for usado para se conectar.

 **Conferência hospedada por um fluxo de chamadas de usuário híbrido**

![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)

### <a name="on-premises-edge-server-with-microsoft-365-or-office-365-hosted-conferences"></a>Servidor de borda local com conferências hospedadas do Microsoft 365 ou office 365
<a name="bk_Figure5"> </a>

Quando um usuário híbrido participa de uma conferência hospedada online, sabemos que a sinalização e a mídia serão destinadas à nuvem do Microsoft 365 ou do Office 365 e, como o usuário está in joining pela Internet, normalmente um caminho direto para a Internet seria feito. No entanto, em alguns casos, como devido a restrições de firewall, um caminho direto da Internet não está disponível. Nesse caso, um servidor de borda local pode retransmitir o tráfego de mídia, o que faz com que o tráfego de mídia retorne à sua rede local antes de percorrer o circuito do ExpressRoute para a nuvem.

 **Usuário local ingressando em uma chamada em conferência online através de servidor de borda local**

![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)

### <a name="pstn-call-using-skype-for-business-cloud-connector-edition"></a>Chamada PSTN usando o Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

Usar o [Skype for Business Online Cloud Connector Edition](https://aka.ms/CloudConnectorInstaller) fornece conectividade PSTN usando recursos locais, como um tronco SIP ou um gateway PSTN, ou usando um dispositivo de hardware mínimo para integração com o Skype for Business. Com o Cloud Connector Edition, os usuários ficam online e agem como usuários normais online quando não envolvem Planos de Chamada. A sinalização de cenários PSTN viajará entre o cliente e a nuvem em uma conexão do ExpressRoute, se disponível, e o tráfego de mídia permanecerá dentro de sua WAN. Nesse caso, a sinalização gira na nuvem do Microsoft 365 ou do Office 365 e termina no Cloud Connector.

 **Chamada PSTN por meio do Sistema Telefônico no Microsoft 365 ou no Office 365 e no Cloud Connector**

![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)

### <a name="skype-meeting-broadcast-with-users-joining-from-customer-network"></a>Transmissão de Reunião do Skype com usuários ingressando pela rede do cliente
<a name="bk_Figure6"> </a>

A Transmissão de Reunião do Skype é um caso de uso especial, que consiste em uma reunião de duas partes com cada parte com perfis de transporte de rede diferentes. A primeira parte, e a mais importante de um ponto de vista de desempenho de rede, é a reunião interna. Essa é a parte em tempo real da reunião que inclui um ou mais pontos de extremidade de cliente que se conectam ao servidor de conferência na nuvem. Os dados transmitidos usando esta parte da reunião são exatamente como o exemplo acima, com um usuário participando de uma conferência online.

O que torna a Transmissão de Reunião do Skype exclusiva é que a reunião é distribuída para um grande número de participantes de conferência usando um serviço de streaming de transmissão. Este serviço de streaming de transmissão não é roueável pelo ExpressRoute, mas usa a Internet com o suporte opcional dos serviços de Rede de Distribuição de Conteúdo (CDN). É útil reconhecer que o streaming de transmissão é um fluxo de mídia unidirecional porque os participantes ouvem, mas não falam e têm suporte para armazenamento em buffer, portanto, é muito menos sensível a problemas de desempenho de rede, como latência, perda de pacotes e tremida. Em vez de otimizar o tráfego de transmissão para esses problemas, ele é otimizado para uso de largura de banda porque há potencialmente um número muito grande de participantes que recebem a mídia transmitida.

 **Transmissão de Reunião do Skype com usuários da rede do cliente**

![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)

## <a name="call-flow-patterns-by-deployment-type"></a>Padrões de fluxo de chamadas por tipo de implantação

Com os exemplos comuns de fluxo de chamada acima e um entendimento dos princípios gerais que controlam os padrões de tráfego, as tabelas a seguir fornecem um resumo dos padrões de tráfego para uma grande combinação de cenários de uso e implantação. Essas tabelas não capturam todas as combinações possíveis de fluxos de chamada, mas devem ajudá-lo a entender melhor os princípios gerais do fluxo de chamada.

Os dados são transmitidos e listados como locais para a organização; não sai da rede do cliente, da Internet ou do ExpressRoute. Os padrões listados abaixo se baseiam nas configurações de rede mais comuns, como firewalls, federação e Internet, e supõem que todas as organizações envolvidas em fluxos federados ou de vários participantes tenham o ExpressRoute. Na prática, ter configurações diferentes pode resultar em padrões de tráfego diferentes daqueles listados abaixo.

### <a name="call-flows-for-skype-for-business-online"></a>Fluxos de chamadas do Skype for Business Online

Os cenários de uso do Skype for Business Online envolvem usuários que estão em casa Online e podem estar ligando de sua rede interna ou da Internet. Os servidores locais não fazem parte desses cenários, portanto, todas as mídias relacionadas a PSTN ou conferência fluirão para a nuvem, e o servidor de borda de usuários online também estará na nuvem.

 **Resumo do fluxo de chamadas do Skype for Business Online**

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: ambos em sua rede.  <br/> |Rota Expressa  <br/> |local  <br/> |[Chamada ponto a ponto para o usuário do Microsoft 365 ou do Office 365 a partir da rede do cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> ||
|Chamada ponto a ponto  <br/> |Dois clientes, um em sua rede (interna) e o outro na Internet (externa).  <br/> |Usuário interno: Rota Expressa  <br/> Usuário externo: Internet  <br/> |Usuário interno: Rota Expressa  <br/> Usuário externo: Internet para o Microsoft 365 ou o servidor de borda do Office 365.  <br/> |[Chamada ponto a ponto para usuários do Microsoft 365 ou do Office 365 a partir da rede do cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Supõe que o firewall bloqueia conexões diretas entre clientes, o que requer um servidor de borda online. O tráfego do usuário interno para o servidor de borda online segue um caminho semelhante ao do servidor de conferência para chamada em conferência.  <br/> |
|Chamada ponto a ponto para um usuário em uma organização federada  <br/> |Dois clientes: em sua rede (interna) e no usuário online na rede da organização federada (federada).  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Supõe que o firewall bloqueia as conexões diretas entre os clientes, o que exige um servidor de borda online. O tráfego do usuário interno para o servidor de borda online segue um caminho similar ao do servidor de conferência para chamada em conferência.  <br/> |
|Ingressar em chamada em conferência por usuário na rede do cliente  <br/> |Cliente em sua rede e servidor de conferência na nuvem.  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Ingressar em chamada em conferência por usuário na Internet  <br/> |O cliente está na Internet e no servidor de conferência na nuvem.  <br/> |Internet  <br/> |Internet  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Ingressar em conferência hospedada por outro servidor local da empresa  <br/> |Cliente na sua rede e servidor de conferência em datacenter de terceiros.  <br/> |Internet  <br/> |Internet  <br/> |Não se aplica  <br/> |Como o servidor de conferência que hospeda a conferência está em uma rede local de outro cliente, nenhum dado passaria pela nuvem da Microsoft.  <br/> |
|Chamada PSTN  <br/> |Cliente na rede do cliente e servidores do Sistema de Telefonia na nuvem  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> ||
|Chamada PSTN  <br/> |Cliente nos servidores do Sistema de Internet e Telefone na nuvem  <br/> |Internet  <br/> |Internet  <br/> |Não se aplica  <br/> |A mídia e a sinalização fluirão para o datacenter do Microsoft 365 ou do Office 365. Como o ponto de extremidade do cliente está na Internet, todos os dados fluirão para o datacenter da Microsoft pela Internet (mesmo que seja necessário um servidor de borda online para conectividade).  <br/> |

> [!NOTE]
> O ExpressRoute será usado no caminho de mídia de um usuário localizado na rede corporativa para um Servidor de Borda online, mas não será usado se o servidor de borda para a implantação local de outro cliente for usado.

### <a name="call-flows-for-skype-for-business-hybrid"></a>Fluxos de chamadas do Skype for Business Híbrido

Os fluxos de chamadas híbridos são aplicados quando você tem uma implantação do Skype for Business que inclui pelo menos alguns usuários que estão instalados no local. Os fluxos de chamadas nesta seção incluem conferências locais e chamadas ponto a ponto ou PSTN com pelo menos um usuário local.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: na rede do cliente e hospedados localmente  <br/> |Local  <br/> |local  <br/> |[Chamada ponto a ponto para o usuário do Microsoft 365 ou do Office 365 a partir da rede do cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Como os usuários estão localizados no local, a sinalização flui localmente para o datacenter local em vez da nuvem.  <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: ambos se conectam pela rede do cliente. Um está hospedado online; o outro, localmente.  <br/> |Usuário online: Rota Expressa  <br/> Usuário local: local  <br/> |local  <br/> |[Chamada ponto a ponto para usuários do Microsoft 365 ou do Office 365 a partir da rede do cliente](call-flow-using-expressroute.md#bk_Figure2) <br/> |Somente o usuário íntefe online envia tráfego de sinalização para a nuvem.  <br/> |
|Chamada ponto a ponto para um usuário em uma organização federada  <br/> |Dois clientes: usuário local na rede do cliente (interna) e usuário online na rede da empresa federada (federada).  <br/> |Usuário interno: local  <br/> Usuário federado: Rota Expressa  <br/> |Internet ou Rota Expressa (depende se for usado o servidor de borda online ou local)  <br/> |Usuário online em sua rede in [joining a](call-flow-using-expressroute.md#bk_Figure3) conference that is hosted Online and part of Local Edge server with [Microsoft 365 or Office 365 hosted conferences](call-flow-using-expressroute.md#bk_Figure5) (for media traffic). <br/> |Supõe que um firewall bloqueia conexões diretas entre clientes, o que exige um servidor de borda online. A negociação ICE oferecerá servidores de borda online (pelo usuário online) e locais (pelo usuário local) para conectividade.  <br/> |
|Ingressar em chamada em conferência por usuário na rede do cliente (conferência agendada pelo usuário online)  <br/> |Usuário local em sua rede e servidor de conferência na nuvem.  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](call-flow-using-expressroute.md#bk_Figure3) <br/> |Os recursos do servidor para chamada em conferência são definidos pelo organizador da reunião. Nesse caso, ele foi agendado por um usuário online, portanto, os recursos estão na nuvem.  <br/> |
|Chamada PSTN  <br/> |Usuário local em sua rede e o datacenter local do Skype for Business.  <br/> |Local  <br/> |Local  <br/> |[Chamada PSTN usando o Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> |Cenário similar para uso do Cloud Connector Edition, exceto que o usuário está hospedado localmente. Portanto, a sinalização permanece dentro de sua rede.  <br/> |

### <a name="call-flows-for-skype-for-business-with-cloud-connector"></a>Fluxos de chamadas para Skype for Business com Cloud Connector

Os usuários que vão se conectar ao Cloud Connector Edition estão todos hospedados online. Isso significa que as conferências estarão online, e a sinalização seguirá os mesmos padrões que os dos usuários online. Para cenários que não são de chamadas PSTN, o fluxo de chamadas ocorrerá exatamente como descrito anteriormente para o Skype for Business Online.

|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada PSTN  <br/> |Usuário online em sua rede usando o Cloud Connector Edition.  <br/> |local  <br/> |local  <br/> |[Chamada PSTN usando o Skype for Business Cloud Connector Edition](call-flow-using-expressroute.md#bk_Figure6) <br/> ||
|Chamada PSTN  <br/> |Usuário online usando a Internet com o Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinação do servidor de borda local com conferências hospedadas do [Microsoft 365 ou Office 365](call-flow-using-expressroute.md#bk_Figure5) e chamada [PSTN](call-flow-using-expressroute.md#bk_Figure6)usando o Skype for Business Cloud Connector Edition.  <br/> |Os usuários de Internet se conectam pelo servidor de borda que é incluído no Cloud Connector, e o Cloud Connector se conecta à rede PSTN.  <br/> |

## <a name="related-topics"></a>Tópicos relacionados

[Documentação do ExpressRoute](https://go.microsoft.com/fwlink/?LinkId=690285)


