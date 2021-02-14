---
title: Fluxos de chamadas do Microsoft Teams
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.date: 06/08/2018
ms.topic: conceptual
ms.service: msteams
ms.reviewer: sonua
audience: admin
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Saiba como o Teams usa fluxos do Office 365 em várias topologias, bem como fluxos de equipe exclusivos usados para comunicação de mídia ponto a ponto.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 13bd0479436963402124e7edea049bcc250d3515
ms.sourcegitcommit: 3323c86f31c5ab304944a34892601fcc7b448025
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "44638660"
---
# <a name="microsoft-teams-call-flows"></a>Fluxos de chamadas do Microsoft Teams

> [!TIP]
> Assista a esta sessão para saber como o Teams aproveita sua rede e como planejar uma conectividade de rede ideal: [Planejamento de rede do Teams.](https://aka.ms/teams-networking)

## <a name="overview"></a>Visão Geral

Este artigo descreve como o Teams usa o Microsoft 365 ou o Office 365 fluxos de chamada em várias topologias. Além disso, descreve fluxos exclusivos do Teams que são usados para comunicação de mídia ponto a ponto. O documento descreve esses fluxos, sua finalidade, sua origem e rescisão na rede. Para fins deste artigo, suponha o seguinte:

- O Flow X é usado pelo cliente local para se comunicar com o serviço do Microsoft 365 ou do Office 365 na nuvem. Ela se origina da rede do cliente e termina como ponto de extremidade no Microsoft 365 ou no Office 365.

- O Fluxo Y é usado pelo cliente local para se comunicar com um serviço na Internet com o que o Microsoft 365 ou o Office 365 tem dependência. Ela se origina da rede do cliente e termina como ponto de extremidade na Internet.

Este artigo aborda as seguintes informações:

- **Plano de fundo.** Fornece informações de plano de fundo, como redes que os fluxos podem percorrer, tipos de tráfego, diretrizes de conectividade da rede do cliente para os pontos de extremidade de serviço do Microsoft 365 ou office 365, interoperabilidade com componentes de terceiros e princípios que são usados pelo Teams para selecionar fluxos de mídia.

- **Fluxos de chamada em várias topologias.** Ilustra o uso de fluxos de chamada em várias topologias. Para cada topologia, a seção enumera todos os fluxos com suporte e ilustra como esses fluxos são usados em vários casos de uso. Para cada caso de uso, descreve a sequência e a seleção de fluxos usando um diagrama de fluxo.

- **Equipes com otimização de Rota Expressa.** Descreve como esses fluxos são usados quando a Rota Expressa é implantada para otimização, ilustrada usando uma topologia simples.

## <a name="background"></a>Plano de fundo

### <a name="network-segments"></a>Segmentos de rede

**Rede do cliente.** Esse é o segmento de rede que você controla e gerencia. Isso inclui todas as conexões do cliente nos escritórios de clientes, seja com fio ou sem fio, conexões entre edifícios de escritório, conexões com datacenters locais e suas conexões com provedores de Internet, Rota Expressa ou qualquer outro peering particular.

Normalmente, uma rede do cliente tem vários perímetros de rede com firewalls e/ou servidores proxy, que impõem as políticas de segurança da sua organização e que só permitem determinado tráfego de rede que você configurou e configurou. Como você gerencia essa rede, tem controle direto sobre o desempenho da rede e recomendamos concluir avaliações de rede para validar o desempenho dentro de sites em sua rede e de sua rede para a rede do Microsoft 365 ou do Office 365.

**Internet.** Esse é o segmento de rede que faz parte de sua rede geral que será usado por usuários que estão se conectando ao Microsoft 365 ou ao Office 365 de fora da rede do cliente. Ele também é usado por algum tráfego da rede do cliente para o Microsoft 365 ou o Office 365.

**Rede privada visitada ou convidada.** Esse é o segmento de rede fora da sua rede do cliente, mas não na Internet pública, que seus usuários e seus convidados podem visitar (por exemplo, uma rede privada de casa ou uma rede privada corporativa, que não implanta o Teams, onde seus usuários e seus clientes que interagem com os serviços do Teams podem residir).

> [!NOTE]
> A conectividade com o Microsoft 365 ou o Office 365 também é aplicável a essas redes.

**Microsoft 365 ou Office 365.** Esse é o segmento de rede compatível com os serviços do Microsoft 365 ou do Office 365. Ele é distribuído em todo o mundo com bordas próximas à rede do cliente na maioria dos locais. As funções incluem Retransmissão de Transporte, servidor de conferência e Processador de Mídia.

**Rota Expressa (opcional).** Esse é o segmento de rede que faz parte de sua rede geral que lhe dará uma conexão dedicada e privada com a rede do Microsoft 365 ou do Office 365.

### <a name="types-of-traffic"></a>Tipos de tráfego

**Mídia em tempo real.** Dados encapsulados em RTP (Protocolo de Transporte em Tempo Real) que suportam cargas de trabalho de áudio, vídeo e compartilhamento de tela. Em geral, o tráfego de mídia é altamente sensível à latência, portanto, você deseja que esse tráfego pegue o caminho mais direto possível e use UDP versus TCP como protocolo de camada de transporte, que é o melhor transporte para mídias interativas em tempo real a partir de uma perspectiva de qualidade. (Observe que, como último recurso, a mídia pode usar TCP/IP e também ser túnel dentro do protocolo HTTP, mas não é recomendável devido a implicações de má qualidade.) O fluxo RTP é protegido usando SRTP, no qual somente a carga é criptografada.

**Sinalização.** O vínculo de comunicação entre o cliente e o servidor ou outros clientes que são usados para controlar atividades (por exemplo, quando uma chamada é iniciada) e entregar mensagens instantâneas. A maioria do tráfego de sinalização usa as interfaces REST baseadas em HTTPS, embora em alguns cenários (por exemplo, a conexão entre o Microsoft 365 ou o Office 365 e um Controlador de Borda de Sessão) use protocolo SIP. É importante compreender que esse tráfego é muito menos sensível à latência, mas pode causar interrupções de serviço ou tempos limite de chamada se a latência entre os pontos de extremidade exceder vários segundos.

### <a name="connectivity-to-microsoft-365-or-office-365"></a>Conectividade com o Microsoft 365 ou o Office 365

O Teams [requer conectividade com a Internet.](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity) UrLs do ponto de extremidade e intervalos de endereços IP do Teams são listados em URLs e intervalos de [endereços IP do Office 365.](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges) (Observe que a conectividade aberta para portas TCP 80 e 443 e para portas UDP 3478 a 3481 é necessária.) Além disso, o Teams tem uma dependência com o Skype for Business Online, que também deve estar conectado à Internet.

A conectividade de fluxos de mídia do Teams é implementada usando os procedimentos padrão de Estabelecimento de Conectividade Interativa (ICE) IETF.

### <a name="interoperability-restrictions"></a>Restrições de interoperabilidade

**Retransmissão de mídia de terceiros.** Um fluxo de mídia do Teams (ou seja, onde um dos pontos de extremidade de mídia é o Teams) pode passar apenas por retransmissão de mídia nativa do Teams ou skype for Business. Não há suporte para interoperabilidade com retransmissão de mídia de terceiros. (Observe que um SBC de terceiros no limite com PSTN deve encerrar o fluxo RTP/RTCP, protegido usando SRTP e não retransmiti-lo para o próximo salto.)

**Servidores proxy SIP de terceiros.** Uma caixa de diálogo SIP de sinalização do Teams com um SBC de terceiros e/ou gateway pode percorrer proxies sip nativos do Teams ou skype for Business. Não há suporte para interoperabilidade com um proxy SIP de terceiros.

**B2BUA (ou SBC)** de terceiros. Um fluxo de mídia do Teams de e para o PSTN é encerrado por um SBC de terceiros. No entanto, não há suporte para interoperabilidade com um SBC de terceiros na rede do Teams (onde um SBC de terceiros media dois pontos de extremidade do Teams ou skype for Business).

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Tecnologias que não são recomendadas com o Microsoft Teams

**Rede VPN.** Não é recomendável para tráfego de mídia (ou fluxo 2'). O cliente VPN deve usar a VPN dividida e rotear o tráfego de mídia como qualquer usuário externo que não seja VPN, conforme especificado na habilitação de mídia do [Lync](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Enabling-Lync-Media-to-Bypass-a-VPN-Tunnel/ba-p/620210)para ignorar um túnel VPN.

> [!NOTE]
> Embora o título indique o Lync, ele também é aplicável ao Teams.

**Shapers de pacote.** Qualquer tipo de equipamento de pacote, inspeção de pacotes ou dispositivos de modelador de pacotes não são recomendados e podem prejudicar significativamente a qualidade.

### <a name="principles"></a>Princípios

Há quatro princípios gerais que ajudam você a entender os fluxos de chamada do Microsoft Teams:

- Uma conferência do Microsoft Teams é hospedada pelo Microsoft 365 ou pelo Office 365 na mesma região em que o primeiro participante ingressou. (Observe que, se houver exceções a essa regra em algumas topologias, elas serão descritas neste documento e ilustradas por um fluxo de chamada apropriado.)

- Um ponto de extremidade de mídia do Teams no Microsoft 365 ou no Office 365 é usado com base nas necessidades de processamento de mídia e não com base no tipo de chamada. (Por exemplo, uma chamada ponto a ponto pode usar um ponto de extremidade de mídia na nuvem para processar mídia para transcrição ou gravação, enquanto uma conferência com dois participantes pode não usar nenhum ponto de extremidade de mídia na nuvem.) No entanto, a maioria das conferências usará um ponto de extremidade de mídia para fins de combinação e roteamento, alocados onde a conferência está hospedada. O tráfego de mídia enviado de um cliente para o ponto de extremidade de mídia pode ser roteado diretamente ou usar uma Retransmissão de Transporte no Microsoft 365 ou no Office 365, se necessário, devido a restrições de firewall de rede do cliente.

- O tráfego de mídia para chamadas ponto a ponto assume a rota mais direta que está disponível, supondo que a chamada não resumente um ponto de extremidade de mídia na nuvem (veja o princípio anterior). A rota preferencial é direta para o ponto remoto (cliente), mas se essa rota não estiver disponível, uma ou mais Retransmissão de Transporte retransmiti o tráfego. É recomendável que o tráfego de mídia não transversa servidores, como shapers de pacotes, servidores VPN e assim por diante, pois isso afetará a qualidade da mídia.

- O tráfego de sinalização sempre vai para o servidor mais próximo do usuário.

Para saber mais sobre os detalhes sobre o caminho de mídia escolhido, consulte Noções básicas sobre fluxos de mídia no [Microsoft Teams - BRK4016.](https://www.youtube.com/watch?v=1tmHMIlAQdo)

## <a name="call-flows-in-various-topologies"></a>Fluxos de chamada em várias topologias

### <a name="teams-topology"></a>Topologia do Teams

Essa topologia é usada pelos clientes que aproveitam os serviços do Teams na nuvem sem qualquer implantação local, como o Skype for Business Server ou o Roteamento Direto do Sistema de Telefonia. Além disso, a interface do Microsoft 365 ou do Office 365 é feita pela Internet sem a Rota Expressa do Azure.

[![Fluxos de chamada do Microsoft Teams Online Figura 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Figura 1 - topologia do Teams*

Observe que:

- A direção das setas no diagrama acima refletem a direção inicial da comunicação que afeta a conectividade nos perímetros da empresa. No caso de UDP para mídia, o primeiro(s) pacote(s) pode fluir na direção inversa, mas esses pacotes podem ser bloqueados até que os pacotes na outra direção fluam.
- O Teams é implantado lado a lado com o Skype for Business Online, portanto, os clientes são exibidos como "Usuário do Teams/SFB".

Você pode encontrar mais informações sobre as seguintes topologias opcionais mais adiante no artigo:

- A implantação local do Skype for Business é descrita na **topologia híbrida do Teams.**
- O Roteamento Direto do Sistema telefônico (para conectividade PSTN) é descrito no **Teams com topologia de Roteamento Direto.**
- Rota Expressa é descrita no **Teams com otimização de Rota Expressa.**

**Descrições de fluxo:**

- **Fluxo 2** – Representa um fluxo iniciado por um usuário na rede do cliente para a Internet como parte da experiência do Teams do usuário. Exemplos desses fluxos são DNS e mídia ponto a ponto.
- **Flow 2'** – Representa um fluxo iniciado por um usuário remoto do Teams móvel, com VPN para a rede do cliente.
- **Flow 3** – Representa um fluxo iniciado por um usuário remoto do Teams móvel para os pontos de extremidade do Microsoft 365 ou do Office 365/Teams.
- **Flow 4** – Representa um fluxo iniciado por um usuário na rede do cliente para os pontos de extremidade do Microsoft 365 ou Office 365/Teams.
- **Flow 5** – Representa um fluxo de mídia ponto a ponto entre um usuário do Teams e outro usuário do Teams ou skype for Business dentro da rede do cliente.
- **Flow 6** – Representa um fluxo de mídia ponto a ponto entre um usuário remoto do Teams móvel e outro usuário remoto do Teams ou skype for Business pela Internet.

#### <a name="use-case-one-to-one"></a>Caso de uso: Um para um

As chamadas um para um usam um modelo comum no qual o chamador obterá um conjunto de candidatos consistindo em endereços IP/portas, incluindo candidatos locais, retransmissão e reflexivos (endereço IP público do cliente, como visto pela retransmissão). O chamador envia esses candidatos para o chamador; a parte chamada também obtém um conjunto semelhante de candidatos e os envia para o chamador. As mensagens de verificação de conectividade STUN são usadas para descobrir qual chamador/chamador de caminhos de mídia de festa funcionam e o melhor caminho de trabalho é selecionado. Mídia (ou seja, pacotes RTP/RTCP protegidos usando SRTP) são enviados usando o par de candidatos selecionado. A retransmissão de transporte é implantada como parte do Microsoft 365 e do Office 365.

Se os candidatos locais de endereço IP/porta ou os candidatos reflexivos têm conectividade, o caminho direto entre os clientes (ou usando um NAT) será selecionado para mídia. Se os clientes estão ambos na rede do cliente, o caminho direto deve ser selecionado. Isso requer conectividade UDP direta dentro da rede do cliente. Se os clientes são ambos usuários de nuvem mônica, então, dependendo do NAT/firewall, a mídia pode usar conectividade direta.

Se um cliente for interno na rede do cliente e um cliente for externo (por exemplo, um usuário de nuvem móvel), é improvável que a conectividade direta entre os candidatos locais ou reflexivos está funcionando. Nesse caso, uma opção é usar um dos candidatos à Retransmissão de Transporte de um dos clientes (por exemplo, o cliente interno obteve um candidato à retransmissão de transporte no Microsoft 365 ou no Office 365; o cliente externo precisa ser capaz de enviar pacotes STUN/RTP/RTCP para a retransmissão de transporte). Outra opção é o cliente interno enviar para o candidato à retransmissão obtido pelo cliente de nuvem móvel. Observe que, embora a conectividade UDP para mídia seja altamente recomendável, o TCP tem suporte.

**Etapas de alto nível:**

1. O Usuário A do Teams resolve o DNS (nome de domínio da URL) usando o fluxo 2.
1. O Usuário do Teams A aloca uma porta de Media Relay no Teams Transport Relay usando o fluxo 4.
1. O Usuário A do Teams envia "convite" com candidatos ICE usando o fluxo 4 para o Microsoft 365 ou o Office 365.
1. O Microsoft 365 ou o Office 365 envia uma notificação ao usuário B do Teams usando o fluxo 4.
1. O Usuário B do Teams aloca uma porta de Media Relay na Retransmissão de Transporte do Teams usando o fluxo 4.
1. O Usuário B do Teams envia "resposta" com candidatos ICE usando o fluxo 4, que é encaminhado de volta ao Usuário A do Teams usando o Flow 4.
1. O Usuário A do Teams e o Usuário B do Teams invocam testes de conectividade ICE e o melhor caminho de mídia disponível está selecionado (consulte os diagramas abaixo para ver vários casos de uso).
1. Os usuários do Teams enviam telemetria para o Microsoft 365 ou o Office 365 usando o fluxo 4.

**Na rede do cliente:**

[![Fluxos de chamada do Microsoft Teams Online Figura 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Figura 2 – Na rede do cliente*

Na etapa 7, o fluxo de mídia ponto a ponto 5 está selecionado.

A mídia é bidirecional. A direção do fluxo 5 indica que um lado inicia a comunicação a partir de uma perspectiva de conectividade, consistente com todos os fluxos neste documento. Nesse caso, não importa qual direção é usada porque os dois pontos de extremidade estão dentro da rede do cliente.

**Rede do cliente para usuário externo (mídia retransmitida pela Retransmissão de Transporte do Teams):**

[![Fluxos de chamada do Microsoft Teams Online Figura 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Figura 3 - Rede do cliente para usuário externo (mídia retransmitida pela Retransmissão de Transporte do Teams)*

Na etapa 7, o fluxo 4, da rede do cliente para o Microsoft 365 ou o Office 365 e o fluxo 3, do usuário móvel remoto do Teams para o Microsoft 365 ou o Office 365, estão selecionados. Esses fluxos são retransmitir pela Retransmissão de Transporte do Teams no Microsoft 365 ou no Office 365.

A mídia é bidirecional, onde a direção indica qual lado inicia a comunicação a partir de uma perspectiva de conectividade. Nesse caso, esses fluxos são usados para sinalização e mídia, usando diferentes protocolos de transporte e endereços.

**Rede do cliente para usuário externo (mídia direta):**

[![Fluxos de chamada do Microsoft Teams Online Figura 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Figura 4 – Rede do cliente para usuário externo (mídia direta)*

Na etapa 7, o fluxo 2, da rede do cliente para a Internet (ponto do cliente), está selecionado.

- A mídia direta com o usuário móvel remoto (não repassado pelo Microsoft 365 ou pelo Office 365) é opcional. Em outras palavras, o cliente pode bloquear esse caminho para impor um caminho de mídia por meio da Retransmissão de Transporte no Microsoft 365 ou no Office 365.

- A mídia é bidirecional. A direção do fluxo 2 para o usuário móvel remoto indica que um lado inicia a comunicação a partir de uma perspectiva de conectividade.

**Usuário VPN para usuário interno (mídia retransmitida pela Retransmissão de Transporte do Teams)**

[![Fluxos de chamada do Microsoft Teams Online Figura 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Figura 5 – Usuário VPN para usuário interno (mídia retransmitida pela Retransmissão de Transporte do Teams)*

A sinalização entre a VPN para a rede do cliente está usando o fluxo 2'. A sinalização entre a rede do cliente e o Microsoft 365 ou o Office 365 está usando o fluxo 4. No entanto, a mídia ignora a VPN e é roteada usando os fluxos 3 e 4 por meio da retransmissão de mídia do Teams no Microsoft 365 ou no Office 365.

**Usuário VPN para usuário interno (mídia direta)**

[![Fluxos de chamada do Microsoft Teams Online Figura 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Figura 6 – usuário VPN para usuário interno (mídia direta)*

A sinalização entre a VPN para a rede do cliente está usando o fluxo 2'. A sinalização entre a rede do cliente e o Microsoft 365 ou o Office 365 está usando o fluxo 4. No entanto, a mídia ignora a VPN e é roteada usando o fluxo 2 da rede do cliente para a Internet.

A mídia é bidirecional. A direção do fluxo 2 para o usuário móvel remoto indica que um lado inicia a comunicação a partir de uma perspectiva de conectividade.

**Usuário VPN para usuário externo (mídia direta)**

[![Fluxos de chamada do Microsoft Teams Figura 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Figura 7 – usuário VPN para usuário externo (mídia direta)*

A sinalização entre o usuário VPN para a rede do cliente está usando o fluxo 2' e usando o fluxo 4 para o Microsoft 365 ou o Office 365. No entanto, a mídia ignora VPN e é roteada usando o fluxo 6.

A mídia é bidirecional. A direção do fluxo 6 para o usuário móvel remoto indica que um lado inicia a comunicação a partir de uma perspectiva de conectividade.

#### <a name="use-case-teams-to-pstn-through-microsoft-365-or-office-365-trunk"></a>Caso de uso: Teams para PSTN por meio do Microsoft 365 ou do Tronco do Office 365

O Microsoft 365 e o Office 365 têm um sistema telefônico que permite fazer e receber chamadas da PSTN (Rede Telefônica Pública Comutado). Se o tronco PSTN estiver conectado usando o Plano de Chamada do Sistema de Telefonia, não haverá requisitos de conectividade especiais para esse caso de uso. (Se quiser conectar seu próprio tronco PSTN local ao Microsoft 365 ou ao Office 365, você pode usar o Roteamento Direto do Sistema de Telefonia.)

[![Fluxos de chamada do Microsoft Teams Online Figura 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Figura 8 – Teams para PSTN por meio do Tronco do Office 365*

#### <a name="use-case-teams-meeting"></a>Caso de uso: Reunião do Teams

O servidor de conferência de áudio/vídeo/compartilhamento de tela (VBSS) faz parte do Microsoft 365 e do Office 365. Ele tem um endereço IP público que deve estar acessível a partir da rede do cliente e deve estar acessível a partir de um cliente cloudic cloud. Cada cliente/ponto de extremidade precisa ser capaz de se conectar ao servidor de conferência.

Os clientes internos obterão candidatos locais, reflexivos e retransmitirão da mesma maneira que descrito para chamadas um para um. Os clientes enviarão esses candidatos para o servidor de conferência em um convite. O servidor de conferência não usa uma retransmissão porque tem um endereço IP publicamente acessível, portanto, ele responde com seu candidato a endereço IP local. O cliente e o servidor de conferência verificarão a conectividade da mesma maneira descrita para chamadas um para um.

Observe que:

- Os clientes do Teams não podem ingressar em reuniões do Skype for Business, e os clientes do Skype for Business não podem ingressar em reuniões do Teams.

- Um usuário PSTN opcionalmente "Disca" ou é "Discado", dependendo do provisionamento de Chamada PSTN e/ou conferência do organizador da reunião.

- Um usuário convidado ou um usuário cliente pode ingressar de uma rede privada de convidado, que está protegida usando FW/NAT com regras estritas.

[![Fluxos de chamada do Microsoft Teams Online Figura 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Figura 9 – Reunião do Teams*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Caso de uso: Federação com o Skype for Business local

**Mídia retransmitida pela Retransmissão de Transporte do Teams no Microsoft 365 ou no Office 365**

[![Fluxos de chamada do Microsoft Teams Online Figura 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Figura 10 – Mídia retransmitida pelo Teams Transport Relay no Office 365*

Observe que:

- A federação é, por definição, uma comunicação entre dois locatários. Nesse caso, o locatário A, que usa o Teams, federa com o locatário B, que usa o Skype for Business no local. Se o locatário B também estiver usando o Microsoft 365 ou o Office 365, o cliente Skype for Business teria usado o fluxo 3 para se conectar ao Microsoft 365 ou ao Office 365.

- A sinalização e a mídia do cliente federado do Skype for Business para o Skype for Business Server local estão fora do escopo deste documento. No entanto, ele é ilustrado aqui para esclarecer.

- A sinalização entre o Teams e o Skype for Business é ponteada por um gateway.

- A mídia nesse caso é retransmitida pela Retransmissão de Transporte do Teams para a rede do cliente e cliente remoto do Skype for Business usando o fluxo 4.

**Mídia retransmitida pelo Skype for Business Media Relay em locatário federado**

[![Fluxos de chamada do Microsoft Teams Online Figura 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Figura 11 – Mídia retransmitida pelo Skype for Business Media Relay em locatário federado*

Observe que:

- A sinalização e a mídia do cliente federado do Skype for Business para um Skype for Business Server local estão fora do escopo deste documento. No entanto, ele é ilustrado aqui para esclarecer.

- A sinalização entre o Teams e o Skype for Business é ponteada por um Gateway.

- A mídia nesse caso é retransmitida pelo Skype for Business Media Relay local para a rede do cliente usando o fluxo 2. (Observe que o tráfego do usuário do Teams para o Media Relay remoto na rede federada do cliente será inicialmente bloqueado pelo Media Relay até que o tráfego na direção inversa comece a fluir. No entanto, o fluxo bidirecional abrirá a conectividade em ambas as direções.)

**Direto (ponto a ponto)**

[![Fluxos de chamada do Microsoft Teams Online Figura 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Figura 12 – Direta (ponto a ponto)*

### <a name="teams-hybrid-topology"></a>Topologia híbrida do Teams

Esta topologia inclui o Teams com uma implantação local do Skype for Business.

[![Fluxos de chamada do Microsoft Teams Online Figura 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Figura 13 - Topologia híbrida do Teams*

- A direção das setas no diagrama acima refletem a direção inicial da comunicação que afeta a conectividade nos perímetros da empresa. No caso de UDP para mídia, o primeiro(s) pacote(s) pode fluir na direção inversa, mas esses pacotes podem ser bloqueados até que os pacotes na outra direção fluam.

- O Teams é implantado lado a lado com o Skype for Business Online, portanto, os clientes são exibidos como "Usuário do Teams/SFB".

Fluxo adicional (em cima da topologia do Teams):

- **Flow 5A** – Representa um fluxo de mídia ponto a ponto entre um usuário do Teams dentro da rede do cliente e uma retransmissão de mídia local do Skype for Business na borda da rede do cliente.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Caso de uso: Teams para Skype for Business um para um

**Híbrido dentro da rede do cliente**

[![Fluxos de chamada do Microsoft Teams Online Figura 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Figura 14 – Híbrido na rede do cliente*

A sinalização entre o Teams e o Skype for Business é ponteada por um gateway. No entanto, a mídia é roteada diretamente ponto a ponto na rede do cliente usando o fluxo 5.

**Rede de cliente híbrida com usuário externo do Skype for Business – ressada pelo Microsoft 365 ou pelo Office 365**

[![Fluxos de chamada do Microsoft Teams Online Figura 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Figura 15 – Rede híbrida do cliente com usuário externo do Skype for Business – ressada pelo Office 365*

Observe que:

- A sinalização e a mídia do cliente Skype for Business para um Skype for Business Server local estão fora do escopo deste documento. No entanto, ele é ilustrado aqui para esclarecer.

- A sinalização entre o Teams e o Skype for Business é ponteada por um gateway.

- A mídia é retransmitida por meio da Retransmissão de Transporte do Teams para a rede do cliente por meio do fluxo 4.

**Rede híbrida do cliente com usuário externo do Skype for Business – reeddia pelo Edge local**

[![Fluxos de chamada do Microsoft Teams Online Figura 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Figura 16 – Rede híbrida do cliente com usuário externo do Skype for Business – reeddia pelo Edge local*

Observe que:

- A sinalização e a mídia do cliente Skype for Business para um Servidor Local do Skype for Business estão fora do escopo deste documento. No entanto, ele é ilustrado aqui para esclarecer.

- A sinalização é ponteada por um gateway.

- A mídia é retransmitida pelo Skype for Business Media Relay no Edge local do Skype for Business para o usuário do Teams dentro da rede do cliente usando o fluxo de mídia 5A.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Teams com topologia de Roteamento Direto do Sistema de Telefonia

Esta topologia inclui o Teams com Roteamento Direto do Sistema de Telefonia.

O Roteamento Direto permite usar um provedor de serviços PSTN (Rede Telefônica Pública Comutado) de terceiros emparelhando um dispositivo de hardware SBC (Controlador de Borda de Sessão) de propriedade do cliente com suporte para o Microsoft 365 ou o Office 365 e conectando o tronco de telefonia a esse dispositivo.

Para dar suporte a esse cenário, o cliente deve implantar um SBC certificado para Roteamento Direto de um dos parceiros certificados da Microsoft. O SBC deve ser configurado conforme recomendado pelo fornecedor e ser roueável do Microsoft 365 ou do Office 365 para tráfego UDP direto. A mídia pode fluir diretamente do Teams e/ou do cliente Skype for Business para o SBC (ignorar o gateway do Teams) ou percorrer o gateway do Teams. A conectividade com o SBC, quando o tronco está configurado para ignorar o gateway do Teams, é baseada no ICE, onde o SBC dá suporte ao ICE-Lite, enquanto o ponto de extremidade de mídia do Teams/Skype for Business dá suporte ao ICE Full Form.

[![Fluxos de chamada do Microsoft Teams Online Figura 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*Figura 17 – Topologia do Teams with Phone System Direct Routing

Observe que:

- A direção das setas no diagrama acima refletem a direção inicial da comunicação que afeta a conectividade nos perímetros da empresa. No caso de UDP para mídia, o primeiro(s) pacote(s) pode fluir na direção inversa, mas esses pacotes podem ser bloqueados até que os pacotes na outra direção fluam.

- O Teams é implantado lado a lado com o Skype for Business Online, portanto, os clientes são exibidos como "Usuário do Teams/SFB".

Fluxos adicionais (na parte superior da topologia online do Teams):

- **Flow 4'** - Representa um fluxo do Microsoft 365 ou do Office 365 para a rede do cliente, usado para estabelecer uma conexão entre o servidor de mídia do Teams na nuvem com o SBC local.
- **Flow 5B** – Representa um fluxo de mídia entre o usuário do Teams dentro da rede do cliente com o SBC de Roteamento Direto no modo de bypass.
- **Flow 5C** – Representa um fluxo de mídia entre o SBC de Roteamento Direto para outro SBC de Roteamento Direto em um modo de bypass de chamada de cabeamento PSTN.

**Usuário interno com Roteamento Direto (mídia retransmitida pela Retransmissão de Transporte do Teams)**

[![Fluxos de chamada do Microsoft Teams Online Figura 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Figura 18 – Usuário interno com Roteamento Direto (mídia retransmitida pela Retransmissão de Transporte do Teams)*

Observe que:

- O SBC deve ter um endereço IP público que seja roueável do Microsoft 365 ou do Office 365.

- A sinalização e a mídia do SBC para o Microsoft 365 ou Office 365 e vice-versa usam o fluxo 4 e/ou o fluxo 4'.

- A sinalização e a mídia do cliente dentro da rede do cliente para o Microsoft 365 ou o Office 365 usam o fluxo 4.

**Usuário remoto com Roteamento Direto (a mídia é roteada por meio de um servidor de mídia (MP))**

[![Fluxos de chamada do Microsoft Teams Online Figura 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Figura 19 – Usuário remoto com Roteamento Direto (a mídia é roteada por meio de um servidor de mídia (MP))*

Observe que:

- O SBC deve ter um endereço IP público que seja roueável do Microsoft 365 ou do Office 365.

- A sinalização e a mídia do SBC para o Microsoft 365 ou Office 365 e vice-versa usam o fluxo 4 e/ou o fluxo 4'.

- A sinalização e a mídia do cliente na Internet para o Microsoft 365 ou o Office 365 usam o fluxo 3.

**Roteamento Direto do usuário interno (bypass de mídia)**

[![Fluxos de chamada do Microsoft Teams Online Figura 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Figura 20 - Roteamento Direto do usuário interno (bypass de mídia)*

Observe que:

- O SBC deve ter um endereço IP público que seja roueável do Microsoft 365 ou do Office 365.

- A sinalização de SBC para o Microsoft 365 ou o Office 365 e vice-versa usam o fluxo 4 e/ou o fluxo 4'.

- A sinalização do cliente na rede do cliente para o Microsoft 365 ou o Office 365 usam o fluxo 4.

- A mídia do cliente dentro da rede do cliente para a SBC dentro da rede do cliente usa o fluxo 5B.

**Usuário remoto com Roteamento Direto (ignorar mídia retransmitida pela Retransmissão de Transporte do Teams)**

[![Fluxos de chamada do Microsoft Teams Online Figura 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Figura 21 – Usuário remoto com Roteamento Direto (bypass de mídia retransmitida pela Retransmissão de Transporte do Teams)*

Observe que:

- O SBC deve ter um endereço IP público que seja roueável do Microsoft 365 ou do Office 365 e da Internet.

- A sinalização do SBC para o Microsoft 365 ou o Office 365 e vice-versa usa o fluxo 4 e/ou o fluxo 4'.

- A sinalização do cliente na Internet para o Microsoft 365 ou o Office 365 usa o fluxo 3.

- A mídia do cliente na Internet para o SBC dentro da rede do cliente usa os fluxos 3 e 4, retransmitida pela Retransmissão de Transporte do Teams.

**Roteamento direto do usuário remoto (ignorar a mídia diretamente)**

[![Fluxos de chamada do Microsoft Teams Online Figura 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Figura 22 – Roteamento Direto do usuário remoto (ignorar a mídia diretamente)*

Observe que:

- O SBC deve ter um endereço IP público que seja roueável do Microsoft 365 ou do Office 365 e da Internet.

- A sinalização do SBC para o Microsoft 365 ou o Office 365 e vice-versa usa o fluxo 4 e/ou o fluxo 4'.

- A sinalização do cliente na Internet para o Microsoft 365 ou o Office 365 usa o fluxo 3.

- A mídia do cliente na Internet para o SBC dentro da rede do cliente usa o fluxo 2.

**Roteamento direto (bypass de mídia) – chamada de corte de pelos PSTN (devido ao encaminhamento/transferência de chamadas)**

[![Fluxos de chamada do Microsoft Teams Online Figura 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Figura 23 - Roteamento Direto (bypass de mídia) - chamada de corte de pelos PSTN (devido ao encaminhamento/transferência de chamadas)*

Observe que:

- O SBC deve ter um endereço IP público que seja roueável do Microsoft 365 ou do Office 365.

- A sinalização do SBC para o Microsoft 365 ou o Office 365 e vice-versa usa o fluxo 4 e/ou o fluxo 4'.

- O cliente fica fora da sinalização e do loop de mídia depois que a chamada é enéreçada de PSTN para PSTN.

- A mídia da instância A da rede do cliente para a instância B do SBC dentro da rede do cliente (onde A e B podem ser a mesma instância) usa o fluxo 5C.

**Roteamento direto (mídia através do Microsoft 365 ou do Office 365) – chamada de corte de pelos PSTN entre dois locatários**

[![Fluxos de chamada do Microsoft Teams Online Figura 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Figura 24 – Roteamento Direto (mídia através do Microsoft 365 ou do Office 365) – chamada de corte de pelos PSTN entre dois locatários*

Observe que:

- O SBC deve ter um endereço IP público que seja roueável do Microsoft 365 ou do Office 365.

- A sinalização do SBC para o Microsoft 365 ou o Office 365 e vice-versa usa o fluxo 4 e/ou o fluxo 4'.

- O cliente fica fora da sinalização e do loop de mídia depois que a chamada é enéreçada de PSTN para PSTN.

- A mídia da instância A da rede do cliente X para a instância B do SBC deve ser repassada pelo Microsoft 365 ou pelo Office 365 Media Server e não pode usar o modo de bypass.

## <a name="teams-with-express-route-optimization"></a>Equipes com otimização de Rota Expressa

[![Fluxos de chamada do Microsoft Teams Online Figura 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Figura 25 – Equipes com otimização de Rota Expressa*

Caso a Rota Expressa seja justificada e implantada, os fluxos do Teams poderão ser roteados do fluxo 4 para o fluxo 1 e do fluxo 4' para o fluxo 1'. No entanto, o aplicativo Teams tem uma dependência difícil com outros fluxos do Microsoft 365 ou do Office 365 pela Internet usando os fluxos 4 e 4'; portanto, esses fluxos não devem ser bloqueados.

Observe que o tráfego de borda híbrida do Skype for Business é roteado para a Internet e não para Rota Expressa para se comunicar com usuários externos e federar com outros locatários.

Para evitar fluxos assimétricos, o roteamento re-roteamento deve estar em ambas as direções. Em outras palavras, um endereço dentro da rede do cliente é roteável por meio da Internet ou da Rota Expressa, com base na otimização, mas não por meio de ambos.


**Rede do cliente para usuário externo (mídia retransmitida pela Retransmissão de Transporte do Teams):**

[![Fluxos de chamada do Microsoft Teams Online Figura 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*Figura 26 – Rede do cliente para usuário externo (mídia retransmitida pela Retransmissão de Transporte do Teams)*

**Etapas de alto nível:**

1. O Usuário do Teams na rede do cliente resolve o DNS (nome de domínio da URL) usando o flow2.
1. O Usuário do Teams na rede do cliente aloca uma porta de Media Relay na Retransmissão de Transporte do Teams usando o fluxo 1.
1. O Usuário do Teams na rede do cliente envia "convite" com candidatos ICE usando o fluxo 1 para o Microsoft 365 ou o Office 365.
1. O Microsoft 365 ou o Office 365 envia uma notificação para usuários externos do Teams usando o fluxo 3.
1. O usuário externo do Teams aloca uma porta de Media Relay no Teams Transport Relay usando o fluxo 3.
1. O usuário externo do Teams envia "resposta" com candidatos ICE usando o fluxo 3, que é encaminhado de volta para o usuário A do Teams usando o Flow 1.
1. O Usuário A do Teams e o Usuário B do Teams invocam testes de conectividade ICE e seleciona os fluxos 1 e 3, que são retransmitir pela Retransmissão de Transporte do Teams.
1. Os usuários do Teams enviam telemetria para o Microsoft 365 ou o Office 365 usando os fluxos 1 e 3.

> [!NOTE]
> O Flow 4 deve ser habilitado para dar suporte às dependências do aplicativo Teams em outros micros serviços que ordenam o fluxo 4.
