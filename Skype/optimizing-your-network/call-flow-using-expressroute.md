---
title: "Fluxo de chamadas usando Rota Expressa"
ms.author: tonysmit
author: tonysmit
manager: scotv
ms.date: 11/9/2017
ms.audience: Admin
ms.topic: article
ms.prod: office-online-server
localization_priority: Normal
ms.collection: Adm_Skype4B_Online
ms.custom: Adm_O365_FullSet
ms.assetid: 413acb29-ad83-4393-9402-51d88e7561ab
description: "Este artigo ajuda a explicar os princípios centrais do fluxo de chamadas do Skype for Business Online e da Rota Expressa, além de fornecer alguns exemplos detalhados de fluxos de chamadas para que você possa entender e planejar corretamente."
---

# Fluxo de chamadas usando Rota Expressa

> [!IMPORTANT]
> Este artigo foi traduzido por um sistema de tradução automática, leia o aviso de isenção de responsabilidade.  
  
Este artigo ajuda a explicar os princípios centrais do fluxo de chamadas do Skype for Business Online e da Rota Expressa, além de fornecer alguns exemplos detalhados de fluxos de chamadas para que você possa entender e planejar corretamente.
  
Se você estiver implantando o Skype for Business Online como parte do Office 365, Skype for Business Server Hybrid ou Skype para Business Edition de conector de nuvem, você precisa compreender a comunicação entre o Skype para Business client e servidores e o fluxo de chamadas portanto Você pode efetivamente planejar, implantar, operar e solucionar o Skype for Business Online services.
  
## Visão geral do fluxo de chamadas

Este documento descreve a rede segmentos que podem conter dados para esses chamada flua e ajuda a entender qual tráfego permanecerá locais à sua rede em comparação com o tráfego que o acompanhará pela Internet ou por meio de rota expressa. Saber qual tráfego usa rota expressa ajudará você a avaliar os benefícios que sua empresa receberá usando rota expressa, bem como ajudam que você a compreender as diretrizes de implantação de rota expressa para validar e sua implantação de solução de problemas depois de decidir Para usar a rota expressa.
  
Os fluxos de chamadas descritos aqui podem ser afetados por uma série de fatores que você controla, inclusive as regras de firewall, a configuração NAT, proxies e a configuração do roteador. Este documento presume que as configurações recomendadas já estão aplicadas. Essas configurações recomendadas são descritas em:
  
- [Configurar o Skype for Business Online](../set-up-skype-for-business-online/set-up-skype-for-business-online.md)
    
- [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
    
- [ExpressRoute do Azure para Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd)
    
- [Rota Expressa do Azure](https://azure.microsoft.com/en-us/services/expressroute/)
    
Instalação e configurações que ainda não tiver seguido as etapas de configuração encontradas na documentação acima podem ter fluxos de chamadas diferentes daqueles que podemos ter documentadas aqui. Além disso, você pode encontrar-se com problemas de configuração como rotas de rede assimétrica e não ideal ou protocolos de transporte não ideal. Roteamento assimétrica é uma consideração importante sempre rota expressa estiver envolvida, porque a rota expressa apresenta um segundo caminho para o Office 365, que cria a possibilidade de um roteiro que utiliza a Internet em uma direção e outra rota que usa Rota expressa na outra direção. Isso pode resultar em tráfego sejam bloqueado na direção retorno se ele percorre um firewall dinâmico.
  
## Segmentos de rede e tipos de tráfego

### Segmentos de rede

Antes de explicar o fluxo de chamadas, precisamos definir alguns termos que ajudarão você a entender os segmentos de rede e os tipos de mídia usados no Skype for Business Online. 
  
Os diagramas de fluxo de chamada abaixo mostram a você quatro segmentos de rede diferentes, cada um deles são gerenciadas por organizações diferentes (sua rede interna, seu provedor de serviço de rede e seus Internet aos parceiros e Microsoft) que têm diferentes características de desempenho. Para obter diretrizes sobre metas de desempenho de rede, consulte [Qualidade de Mídia e Desempenho de Conectividade de Rede no Skype for Business Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
A seguir, apresentamos todos os segmentos de rede sobre os quais falaremos.
  
![Call Flow Network Segments.](../images/25689bf2-4753-4bea-b8d7-88dc8b6d2e2a.png)
  
 **Sua rede** Este é o segmento de rede que faz parte de sua rede geral que você controle e gerencie. Isso inclui todas as suas conexões dentro de seus escritórios, se com ou sem fio, entre edifícios do office, dos data centers local e suas conexões com provedores de Internet ou parceiros de rota expressa.
  
Normalmente, a borda da sua rede tem um ou mais DMZ com firewalls e/ou servidores proxy, qual aplicar políticas de segurança da sua organização e que só permitir determinado tráfego de rede que você configure e configurou. Porque você gerencia esta rede, você tem controle direto sobre o desempenho da sua rede e é altamente recomendável que você conclua avaliações de rede para validar o desempenho tanto em sites na sua rede e da sua rede para Skype for Business Online. Para ver os requisitos de desempenho, consulte [Qualidade de Mídia e Desempenho de Conectividade de Rede no Skype for Business Online](media-quality-and-network-connectivity-performance-in-skype-for-business-online.md).
  
 **Internet** Este é o segmento de rede que faz parte de sua rede geral que será usada pelos usuários que estão se conectando Skype for Business Online de fora da sua rede e são usados para todas as conexões quando rota expressa não está configurada. Internet e todas as suas conexões não são gerenciadas por você ou Microsoft, portanto desempenho e caminhos de roteamento não podem ser determinados, e isso terá o maior impacto sobre o fluxo de chamadas e qualidade geral.
  
 **Rota expressa** Este é o segmento de rede que faz parte de sua rede geral que lhe dará uma conexão dedicada, privada para a rede da Microsoft. Esta é a opção recomendada para conexão de rede com a rede da Microsoft (dos data centers do Office 365) para todas as cargas de trabalho que dependem a velocidade de rede e desempenho, como o Skype for Business Online comunicação em tempo real. Rota expressa conexões são feitas entre sua rede e o uso de rede do Microsoft[provedores de conectividade de rota expressa](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/) para fornecer uma rede privada e gerenciada, atividade de 99,9% e suporte a qualidade do serviço (QoS) que pode melhorar o desempenho de mídia em tempo real durante períodos de congestionamento da rede.
  
 **Rede Microsoft** Este é o segmento de rede que faz parte de sua rede geral que ofereça suporte a serviços do Office 365. Isso inclui todas as comunicações entre servidores Online para Office 365. Isso pode incluir o tráfego que percorre o backbone de rede da Microsoft e é transmitido entre regiões geográficas.
  
### Tipos de tráfego

O tráfego de rede para o Skype for Business Online se encaixa em duas grandes categorias, mostradas como caminhos separados no fluxo de chamada:
  
 **Mídia em tempo real** dados encapsulado em RTP (protocolo de transporte em tempo real) e compatível com áudio, vídeo, compartilhamento de aplicativos e cargas de trabalho de transferência de arquivo. Em geral, o tráfego de mídia é altamente latência confidencial, para que você desejaria esse tráfego para tirar o caminho mais direto possíveis e usar UDP como o protocolo de camada de transporte porque usando TCP introduz latência maior.
  
 **Sinalização** é o link de comunicação entre o cliente e servidor, ou outros clientes que são usados para controlar atividades (por exemplo, quando uma chamada é iniciada) e entregar mensagens instantâneas. A maioria dos sinalização de tráfego usa o protocolo SIP, embora alguns clientes usam interfaces baseado em HTTP restante. Para tornar mais simples, estamos considerando uma variedade de sinalização que podem ser transmitidos conexões HTTP e HTTPS ou TLS nesse tipo de tráfego. É importante entender que esse tráfego é muito menos sensível a latência, mas pode causar interrupções no serviço ou tempos limite de chamadas se latência entre os pontos de extremidade exceder vários segundos.
  
Os destinos para esse tráfego encontram-se no [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para todos os serviços do Office 365. Para cada URL, ele indica se a parte de tráfego pode percorrer a rota expressa para Office 365. Diagramas que mostram que Internet ainda é usada para algumas tráfego quando rota expressa está habilitada, consulte[ExpressRoute do Azure para Office 365](https://support.office.com/article/6d2534a2-c19c-4a99-be5e-33a0cee5d3bd). É importante entender que par URLs que estão listados como sendo roteáveis sobre rota expressa também são roteáveis pela Internet. Isso significa que em alguns cenários, a determinação sobre se Internet ou rota expressa será usada depende do local do cliente e configuração de servidores proxy e firewalls. Também é importante entender que desde que não todas as URLs associadas com o Office 365 são capazes de usar a rota expressa, uma conexão de Internet é necessário mesmo se você comprar rota expressa de um parceiro de rota expressa.
  
Tráfego que só pode ser enviado pela Internet inclui dependências de Internet comuns, como listas de certificados revogados (CRLs), pesquisas DNS e resolução de nomes, URLs para serviços compartilhados do Office 365, como para o Centro de administração do Office 365 e alguns não em tempo real recursos de comunicação do Skype for Business Online, como telemetria e federação para interoperabilidade com o Skype consumidor, como bem mídia que é transmitida para transmissão de reunião do Skype. Para ajudá-lo a tomar decisões, consulte [Roteamento com o ExpressRoute para Office 365](https://support.office.com/article/e1da26c6-2d39-4379-af6f-4da213218408) para obter mais considerações sobre quando você estiver planejando o roteamento de rede.
  
## Princípios para fluxos de chamadas com o Skype for Business

Antes de entrar em detalhes de específicos cenários de fluxo de chamadas, há seis princípios gerais que ajudam você entendam fluxos de chamada do Skype for Business.
  
1. Um Skype para conferência de negócios é hospedado na mesma região onde o organizador da conferência está hospedado. Isso é na nuvem Office 365 se o organizador for um usuário Online ou em um data center local se o organizador da reunião é um usuário local.
    
2. Tráfego de mídia enviado de um cliente para uma conferência hospedada sempre vai para o servidor em que a conferência está hospedada. Isso pode ser um servidor local em um data center que você gerencia ou Online dentro da nuvem do Office 365. No entanto, um servidor de borda é sempre usado para o fluxo de mídia para conferências on-line.
    
3. O tráfego de mídia para chamadas ponto a ponto usa a rota mais direta que estiver disponível. A rota preferencial é direta para o ponto (cliente) remoto, mas se a rota não estiver disponível, porque o firewall está bloqueando o tráfego ou algo parecido, então um ou mais servidores de borda transmitirão o tráfego.
    
4. O tráfego de sinalização sempre irá para o servidor onde o usuário está localizado, Online ou no local. Um servidor de borda será usado se não for possível conectar-se diretamente ao servidor Front-End.
    
5. Os usuários que participam de uma conferência hospedada online sempre usarão um servidor de borda (ou dois, se necessário, dependendo das configurações de firewall do cliente).
    
6. Os usuários que ingressam em uma conferência hospedada no local normalmente não usarão um servidor de borda se estiverem se conectando pela mesma rede que contém a implantação local, mas usarão um ou dois servidores de borda quando estiverem se conectando de fora da sua rede. 
    
Para saber mais sobre os detalhes sobre o caminho de mídia que é escolhido, consulte [ICE - conectividade de mídia de borda](https://aka.ms/AVEdge). Embora este vídeo faz sobre o Lync Server 2013, os princípios e protocolos ainda se aplicam ao Skype for Business.
  
## Fluxos de chamadas do Skype for Business com Rota Expressa

Agora que você tem uma compreensão das quatro segmentos de rede diferentes e alguns princípios gerais do Skype para fluxos de chamada de negócios, você pode usar que informações para ajudá-lo a compreender quais Skype para o tráfego de negócios irá desviar uma rota expressa segmento de rede.
  
Em geral, o tráfego de rede usará a conexão da Rota Expressa, caso um ponto de extremidade seja sua rede e o outro ponto de extremidade seja o datacenter do Office 365. Isso incluirá o tráfego de sinalização entre o cliente e o servidor, o tráfego de mídia usado durante as chamadas em conferência ou chamadas ponto a ponto que usam o servidor de borda online.
  
Tráfego não percorrer a conexão de rota expressa se ambos os pontos de extremidade são capazes de se comunicar diretamente através da internet ou estão localizados dentro de sua rede. Isso incluirá mídia para chamadas de ponto-a-ponto, o tráfego da Internet destinado a uma implantação local ou qualquer tráfego entre a Internet e os servidores de borda do Office 365. Um exemplo disso seria um usuário ingressar em uma conferência Online de um hotel.
  
## Como usar o fluxo de chamadas do Skype for Business

Para ajudá-lo a aplicar os princípios gerais de fluxos de chamadas do Skype for Business descritos anteriormente, a próxima seção deste artigo contém vários diagramas para referência. Não se trata de uma lista exaustiva de todos os fluxos de chamadas possíveis, mas tem como finalidade ajudá-lo a aplicar os princípios detalhados anteriormente. Além disso, os cenários nos diagramas foram selecionados para abranger tipos comuns de implantação, incluindo Online, Híbrido, Cloud Connector e um caso especial: a Transmissão de Reunião do Skype.
  
> [!NOTE]
> Um subconjunto de tráfego usado pelo Skype for Business não é roteável sobre rota expressa e sempre terá um caminho de Internet. Consulte as [URLs e intervalos de endereços IP do Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2) para determinar as URLs que podem ser afetadas.
  
### Chamada ponto-a-ponto para usuários do Office 365 de dentro de rede de clientes
<a name="bk_Figure2"> </a>

Para chamadas ponto a ponto, o tráfego de mídia sempre usa a rota mais direta até o seu destino. No entanto, o tráfego de sinalização vai para um datacenter do Office 365 onde o usuário online está localizado. Visto que os dois usuários estão na mesma WAN e nada impede a comunicação direta entre os clientes, a mídia flui diretamente entre eles. O tráfego de sinalização, dos dois usuários, usa a conexão da Rota Expressa que está destinada a cada datacenter da organização. Para mostrar o fluxo de chamadas neste cenário, veja isto.
  
 **Fluxo de chamadas ponto a ponto**
  
![Call Flow with Peer to Peer call.](../images/f460369e-bfce-4a03-a031-d7e92c4ace89.png)
  
### Usuário online de sua rede ingressando em uma conferência hospedada online
<a name="bk_Figure3"> </a>

No exemplo ponto-a-ponto, o tráfego de mídia sempre leva a rota mais direta para seu destino. No entanto, para uma conferência Online, o destino é na nuvem Office 365. Isso significa que o tráfego de mídia para todos os usuários ingressar na conferência de dentro de sua rede irá desviar a conexão de rota expressa e o tráfego de sinalização viaja na nuvem do Office 365. O gráfico a seguir mostra que sinalização e mídia irá desviar a conexão de rota expressa para um usuário em sua rede e diretamente irá desviar a Internet para usuários que estão conectados à Internet de fora da sua rede, como de um café comprar ou hotel.
  
Lembre-se de que o local de uma conferência é definido pelo organizador da reunião e não pelos participantes. Isso significa que se a reunião foi agendada por um cliente local, o tráfego de mídia não fluir na nuvem do Office 365 sobre rota expressa, mas em vez disso seria desviar a Internet ao data center local do organizador da reunião.
  
O destino da mídia de conferências online será um datacenter na nuvem do Office 365, mas esse datacenter pode estar em uma região geográfica diferente daquela dos usuários que estão participando da conferência. Isso pode acontecer de uma das seguintes maneiras:
  
- Se o organizador da reunião for de uma empresa diferente da dos participantes, e se a organização dele estiver hospedada em outra localização geográfica ou país/região.
    
- Se um usuário estiver participando de um país/região diferente de onde a organização da empresa está localizada, pelo fato de a empresa ser multinacional ou o usuário estar viajando.
    
A boa notícia sobre como usar a rota expressa neste cenário é que com complemento de premium rota expressa, dados que segue o caminho de rota expressa passará automaticamente em backbone da Microsoft, independentemente de área geográfica do organizador da reunião Centro de dados da organização.
  
 **Usuário online com fluxo de chamadas de reunião online**
  
![Call flow for an online hosted conference call.](../images/22d9ee64-b20c-4079-b3d1-a7a806b9a0bc.png)
  
### Ingressando em uma conferência hospedada por usuário local em implantação híbrida
<a name="bk_Figure3"> </a>

Lembre-se de que os servidores de conferência que oferecem suporte a conferências hospedadas são determinados por onde o organizador da reunião está hospedado. Neste cenário, a mídia para todos os usuários de ingresso em uma conferência agendada por um usuário local em uma implantação híbrida fluirá para um data center local. Sinalização para usuários homed Online será estabelecida por meio de sua organização na nuvem do Office 365, enquanto mídia tentará uma conexão direta. Neste cenário, desde que ambos os usuários estão se conectando dentro de sua rede, uma conexão direta de mídia é possível, portanto rota expressa é usada apenas para o tráfego para o usuário homed Online sinalização. Se um usuário homed Online se conecta da Internet, a mídia pode percorrer rota expressa se um servidor de borda Online é usado para conectar.
  
 **Conferência hospedada por um fluxo de chamadas de usuário híbrido**
  
![Call flow hosted onprem.](../images/9e669859-19f3-4a86-95b7-7185eb421ccd.png)
  
### Servidor de borda local com conferências hospedadas no Office 365
<a name="bk_Figure5"> </a>

Quando um usuário de híbrido junções um Online hospedado em conferência, sabemos que sinalização e mídia será ser destinadas a nuvem do Office 365 e desde que o usuário está ingressando da Internet, normalmente um caminho de internet direto poderia ser utilizado. No entanto, em alguns casos, como devido a restrições de firewall, um caminho de Internet direto não está disponível. Nesse caso, um servidor de borda local pode retransmissão o tráfego de mídia, o que faz com que o tráfego de mídia retornar à sua rede local antes de percorrer o circuito rota expressa na nuvem do Office 365.
  
 **Usuário local ingressando em uma chamada em conferência online através de servidor de borda local**
  
![Call flow for a conference call going through an edge server.](../images/0178c170-5837-430d-84f1-582784bfef55.png)
  
### Chamada PSTN usando o Skype for Business Cloud Connector Edition
<a name="bk_Figure6"> </a>

Usar o [Skype for Business Online nuvem conector Edition](https://aka.ms/CloudConnectorInstaller) fornece conectividade PSTN usando recursos de locais como um tronco SIP ou um gateway PSTN ou usando um dispositivo de hardware mínimas para integrar com o Skype para empresas. Com edição de conector de nuvem, os usuários são hospedados Online e atuam como usuários Online normais quando eles não envolvem chamando planos. Sinalização para cenários de PSTN será viajam entre o cliente e a nuvem em uma conexão de rota expressa se disponível, e o tráfego de mídia permanece dentro de sua WAN. Nesse caso, sinalização vira em nuvem do Office 365 e termina no conector nuvem.
  
 **Chamadas PSTN por meio do sistema de telefone no Office 365 e conector de nuvem**
  
![Call flow for a PSTN call using Cloud PBX Cloud Connector.](../images/e48d0f2b-fa1e-4b43-b3dd-d34a33dcdf36.png)
  
### Transmissão de Reunião do Skype com usuários ingressando pela rede do cliente
<a name="bk_Figure6"> </a>

Transmissão de reunião do Skype é um especial caso de uso, que consiste em uma reunião de duas partes com cada parte tendo perfis de transporte de rede diferente. A primeira parte e o que é mais importante da rede ponto de vista do desempenho, é a reunião interna. Esta é a parte em tempo real da reunião que inclui um ou mais pontos de extremidade do cliente se conectando ao servidor de conferência na nuvem do Office 365. Dados transmitidos usando essa parte da reunião são exatamente como no exemplo acima, com conferência Online e participar de usuário do Office 365.
  
O que torna a transmissão de reunião do Skype exclusivo é que a reunião é distribuída para um grande número de participantes de conferência usando uma transmissão de serviço de streaming. Esta transmissão de serviço de streaming não roteável sobre rota expressa, mas em vez disso, usa a Internet com o suporte opcional de serviços de rede de entrega de conteúdo (CDN). É útil reconhecer que o fluxo de difusão é um fluxo de mídia unidirecional porque os participantes ouvir, mas não falam e oferece suporte buffer, portanto, é muito menos confidencial para problemas de desempenho de rede como latência, perda de pacotes e variação. Em vez de otimizar o tráfego de difusão para estes problemas, ele é otimizado para utilização de largura de banda porque há potencialmente um grande número de participantes receber o fluxo de mídia.
  
 **Transmissão de Reunião do Skype com usuários da rede do cliente**
  
![Call flow for Skype Meeting Broadcast.](../images/cbe0e9f3-7eee-47e9-b61e-f2780b525dea.png)
  
## Padrões de fluxo de chamadas por tipo de implantação

Exemplos de fluxo acima de chamadas com o comum e uma compreensão geral dos princípios básicos que controlam padrões de tráfego, as tabelas a seguir fornecem um resumo dos padrões de tráfego para um grande combinação dos cenários de implantação e o uso. Estas tabelas não captura todas as combinações possíveis de fluxos de chamada, mas devem ajudá-lo a compreender melhor os princípios gerais de fluxo de chamadas.
  
Dados são transmitidos e são listados como sendo local à organização; ele não deixar a rede de clientes, Internet ou rota expressa. Os padrões listados abaixo se baseiam as configurações de rede mais comuns, como firewalls, Federação e Internet e presumem que organizações de todos os envolvidos nos fluxos de vários participantes ou federados tem rota expressa. Na prática, ter diferentes configurações pode resultar em padrões de tráfego diferentes daqueles que estão listadas abaixo.
  
### Fluxos de chamadas do Skype for Business Online

Skype for Business Online cenários de uso envolvem usuários que são hospedados Online e podem ser chamando a partir de sua rede interna ou na Internet. Servidores de local não fazem parte desses cenários, para que todas as conferências ou mídia relacionada PSTN fluirá para a nuvem do Office 365 e os usuários Online servidor de borda também será na nuvem.
  
 **Resumo do fluxo de chamadas do Skype for Business Online**
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: ambos em sua rede.  <br/> |Rota Expressa  <br/> |local  <br/> |[Chamada ponto-a-ponto para usuários do Office 365 de dentro de rede de clientes](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> ||
|Chamada ponto a ponto  <br/> |Dois clientes, na sua rede (interno) e outro cliente na Internet (externo).  <br/> |Usuário interno: Rota Expressa  <br/> Usuário externo: Internet  <br/> |Usuário interno: Rota Expressa  <br/> Usuário externo: Internet para servidor de borda do Office 365.  <br/> |[Chamada ponto-a-ponto para usuários do Office 365 de dentro de rede de clientes](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Pressupõe que o firewall bloqueia conexões diretas entre clientes, que requer um servidor de borda Online. Tráfego de usuário interno para servidor de borda Online segue semelhante caminho que o servidor de conferência para chamada em conferência.  <br/> |
|Chamada ponto a ponto para um usuário em uma organização federada  <br/> |Dois clientes: em sua rede (interna) e no usuário online na rede da organização federada (federada).  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |Supõe que o firewall bloqueia as conexões diretas entre os clientes, o que exige um servidor de borda online. O tráfego do usuário interno para o servidor de borda online segue um caminho similar ao do servidor de conferência para chamada em conferência.  <br/> |
|Ingressar em chamada em conferência por usuário na rede do cliente  <br/> |Cliente na sua rede e servidor de conferência na nuvem do Office 365.  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Ingressar em uma chamada em conferência por usuário na Internet  <br/> |Cliente é no servidor de Internet e conferências no Office 365 na nuvem.  <br/> |Internet  <br/> |Internet  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Ingressar em conferência hospedada por outro servidor local da empresa  <br/> |Cliente na sua rede e servidor de conferência em datacenter de terceiros.  <br/> |Internet  <br/> |Internet  <br/> |Não se aplica  <br/> |Como o servidor de conferência que hospeda a conferência está em uma rede local de outro cliente, nenhum dado passaria pela nuvem da Microsoft.  <br/> |
|Chamada PSTN  <br/> |Cliente na rede de clientes e servidores de sistema telefônico no Office 365 na nuvem  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> ||
|Chamada PSTN  <br/> |Cliente nos servidores de Internet e sistema telefônico na nuvem do Office 365  <br/> |Internet  <br/> |Internet  <br/> |Não se aplica  <br/> |A mídia e sinalização irá fluem para o Centro de dados do Office 365. Como o ponto de extremidade do cliente é na Internet, todos os dados fluirá ao data center Microsoft através da Internet (mesmo se um servidor de borda Online é necessário para conectividade).  <br/> |
   
> [!NOTE]
> Rota expressa será usada no caminho de mídia de um usuário localizado na rede corporativa para um servidor de borda online, mas não será usada se o servidor de borda na implantação local outro cliente for usado. 
  
### Fluxos de chamadas do Skype for Business Híbrido

Fluxos de chamadas híbrido aplicam quando você tiver um Skype para implantação de negócios que inclua pelo menos alguns usuários que estão homed local. Os fluxos de chamada nesta seção incluem conferências ambos os locais e ponto-a-ponto ou PSTN chama com pelo menos um usuário homed local.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: na rede do cliente e hospedados localmente  <br/> |Local  <br/> |local  <br/> |[Chamada ponto-a-ponto para usuários do Office 365 de dentro de rede de clientes](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Como os usuários estão hospedados localmente, a sinalização flui localmente até o datacenter local, em vez fluir para a nuvem do Office 365.  <br/> |
|Chamada ponto a ponto  <br/> |Dois clientes: ambos se conectam pela rede do cliente. Um está hospedado online; o outro, localmente.  <br/> |Usuário online: Rota Expressa  <br/> Usuário local: local  <br/> |local  <br/> |[Chamada ponto-a-ponto para usuários do Office 365 de dentro de rede de clientes](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure2) <br/> |Somente o usuário hospedado online envia tráfego de sinalização para a nuvem do Office 365.  <br/> |
|Chamada ponto a ponto para um usuário em uma organização federada  <br/> |Dois clientes: usuário local na rede do cliente (interna) e usuário online na rede da empresa federada (federada).  <br/> |Usuário interno: local  <br/> Usuário federado: Rota Expressa  <br/> |Internet ou Rota Expressa (depende se for usado o servidor de borda online ou local)  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) e parte do[Servidor de borda local com conferências hospedadas no Office 365](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5) (para tráfego de mídia). <br/> |Pressupõe um firewall bloqueia conexões diretas entre clientes, exigindo o servidor de borda Online. ICE negociação oferecerá Online (pelo usuário online) e servidores de borda de local (pelo usuário no local) para conectividade.  <br/> |
|Ingressar em chamada em conferência por usuário na rede do cliente (conferência agendada pelo usuário online)  <br/> |Usuário local na sua rede e servidor de conferência na nuvem do Office 365.  <br/> |Rota Expressa  <br/> |Rota Expressa  <br/> |[Usuário online de sua rede ingressando em uma conferência hospedada online](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure3) <br/> |Recursos de servidor para chamada de conferência são definidos pelo organizador da reunião. Nesse caso, ele foi agendado por um usuário Online, portanto recursos estão na nuvem do Office 365.  <br/> |
|Chamada PSTN  <br/> |Usuário local em sua rede e o datacenter local do Skype for Business.  <br/> |Local  <br/> |Local  <br/> |[Chamada PSTN usando o Skype for Business Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> |Cenário similar para uso do Cloud Connector Edition, exceto que o usuário está hospedado localmente. Portanto, a sinalização permanece dentro de sua rede.  <br/> |
   
### Fluxos de chamadas para Skype for Business com Cloud Connector

Os usuários que vão se conectar ao Cloud Connector Edition estão todos hospedados online. Isso significa que as conferências estarão online, e a sinalização seguirá os mesmos padrões que os dos usuários online. Para cenários que não são de chamadas PSTN, o fluxo de chamadas ocorrerá exatamente como descrito anteriormente para o Skype for Business Online.
  
|||||||
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Cenário de uso** <br/> |**Pontos de extremidade** <br/> |**Caminho de sinalização** <br/> |**Caminho de mídia** <br/> |**Fluxo de exemplo** <br/> |**Observações** <br/> |
|Chamada PSTN  <br/> |Usuário online em sua rede usando o Cloud Connector Edition.  <br/> |local  <br/> |local  <br/> |[Chamada PSTN usando o Skype for Business Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6) <br/> ||
|Chamada PSTN  <br/> |Usuário online usando a Internet com o Cloud Connector Edition.  <br/> |Internet  <br/> |Internet  <br/> |Combinação de [Servidor de borda local com conferências hospedadas no Office 365](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure5) e[Chamada PSTN usando o Skype for Business Cloud Connector Edition](413acb29-ad83-4393-9402-51d88e7561ab.md#bk_Figure6).  <br/> |Os usuários de Internet se conectam pelo servidor de borda que é incluído no Cloud Connector, e o Cloud Connector se conecta à rede PSTN.  <br/> |
   
## 
<a name="MT_Footer"> </a>

> [!NOTE]
> **Aviso de Isenção de Tradução Automática**: Este artigo foi traduzido por computador, sem intervenção humana. A Microsoft oferece essas traduções automáticas para ajudar as pessoas que não falam inglês a aproveitar os textos escritos sobre produtos, serviços e tecnologias da Microsoft. Como este artigo foi traduzido automaticamente, é possível que contenha erros de vocabulário, sintaxe ou gramática. 
  

