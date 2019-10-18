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
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
description: Descreve como o Microsoft Teams usa fluxos do Office 365 em várias topologias.
ms.openlocfilehash: 91be46f556419dfd1ba8c52a99b8f06a19c63542
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37573407"
---
# <a name="microsoft-teams-call-flows"></a>Fluxos de chamadas do Microsoft Teams

> [!Tip]
> Assista à sessão a seguir para saber como as equipes aproveitam a sua rede e como planejar a conectividade de rede ideal: [planejamento de rede do teams](https://aka.ms/teams-networking)

## <a name="overview"></a>Visão geral
Este artigo descreve como o Microsoft Teams usa fluxos de chamadas do Office 365 em várias topologias. Além disso, ele descreve fluxos exclusivos do teams que são usados para comunicação de mídia ponto a ponto. O documento descreve esses fluxos, sua finalidade e sua origem e rescisão na rede. Para fins deste artigo, assuma o seguinte:

- O fluxo X é usado pelo cliente do Office 365 local para se comunicar com o serviço do Office 365 na nuvem. Ele provém da rede do cliente e ele termina como um ponto de extremidade no Office 365.

- O fluxo Y é usado pelo cliente do Office 365 local para se comunicar com um serviço na Internet no qual o Office 365 tem uma dependência. Ele provém da rede do cliente e ele termina como um ponto de extremidade na Internet.

O artigo contém as seguintes seções:

- **Plano de fundo** : fornece informações em segundo plano, como redes que os fluxos do Office 365 podem atravessar, tipo de tráfego, orientação de conectividade da rede do cliente para pontos de extremidade do serviço do Office 365, interoperabilidade com componentes de terceiros e princípios usados por equipes para selecionar fluxos de mídia.

- **Fluxos de chamadas em várias topologias** – ilustra o uso de fluxos de chamadas em várias topologias. Para cada topologia, a seção enumera todos os fluxos compatíveis e ilustra como esses fluxos são usados por vários casos de uso. Para cada caso de uso, ele descreve a sequência e a seleção de fluxos por meio de um diagrama de fluxo. 

- **Teams com otimização de rota expressa** – descreve como esses fluxos são usados quando a rota expressa é implantada para otimização, ilustrada por meio de uma topologia simples.

## <a name="background"></a>Plano de fundo
### <a name="network-segments"></a>Segmentos de rede
**Rede do cliente**: Este é o segmento de rede que você controla e gerencia. Isso inclui todas as conexões do cliente nos escritórios do cliente, seja com fio ou sem fio, entre os prédios do Office, os datacenters locais e suas conexões com provedores de Internet, rota expressa ou qualquer outro ponto privado. 

Geralmente, uma rede de cliente tem vários perímetros de rede com firewalls e/ou servidores proxy, que impõem as políticas de segurança da sua organização e que só permitem certos tipos de tráfego de rede que você configurou e configurou. Como você gerencia essa rede, você tem controle direto sobre o desempenho da rede e é altamente recomendável que você conclua as avaliações de rede para validar o desempenho tanto dentro dos sites da sua rede quanto da rede para a rede do Office 365. 

**Internet**: é o segmento de rede que faz parte de sua rede geral que será usada pelos usuários que estão se conectando ao Office 365 de fora da rede do cliente. Ele também é usado por algum tráfego da rede do cliente para o Office 365. 

**Rede privada de visita/convidado**: Este é o segmento de rede fora da rede do cliente, mas não na Internet pública, que seus usuários e/ou seus convidados podem acessar. Por exemplo, rede privada residencial ou uma rede privada corporativa, que não implanta equipes, onde os usuários e/ou clientes que interagem com os serviços do teams podem residir.

>**Observação**: a conectividade com o Office 365 também se aplica a essas redes.

**Office 365**: Este é o segmento de rede que oferece suporte aos serviços do Office 365. Ele é distribuído no mundo inteiro com bordas em proximidade à rede do cliente na maioria dos locais. As funções mencionadas neste documento incluem retransmissão de transporte, servidor de conferência e processador de mídia. 

**Rota expressa (opcional)**: Este é o segmento de rede que faz parte de sua rede geral que lhe dará uma conexão privada dedicada à rede do Office 365.

### <a name="types-of-traffic"></a>Tipos de tráfego

**Mídia em tempo real**: dados encapsulados dentro do RTP (protocolo de transporte em tempo real) que dão suporte a cargas de trabalho de áudio, vídeo e compartilhamento de tela. Em geral, o tráfego de mídia é altamente sensível à latência, portanto, você quer que esse tráfego tome o caminho mais direto possível e use UDP versus TCP como o protocolo de camada de transporte, que é o melhor transporte para mídia interativa em tempo real de uma perspectiva de qualidade . (Observação: como último recurso, a mídia pode usar TCP/IP e também ser encapsulada no protocolo HTTP, mas não é recomendável devido a implicações de qualidade ruim.) O fluxo de RTP é protegido via SRTP, no qual somente a carga é criptografada.

**Sinalização**: o link de comunicação entre o cliente e o servidor, ou outros clientes que são usados para controlar atividades (por exemplo, quando uma chamada é iniciada) e entrega mensagens instantâneas. A maior parte do tráfego de sinalização usa as interfaces REST baseadas em HTTPS, mas em alguns cenários (por exemplo, conexão entre o Office 365 e um controlador de borda de sessão) ele usa o protocolo SIP. É importante entender que esse tráfego é muito menos sensível à latência, mas pode causar paralisações de serviço ou tempos limite de chamadas se a latência entre os pontos de extremidade exceder vários segundos. 

### <a name="connectivity-to-office-365"></a>Conectividade com o Office 365

O Microsoft Teams requer [conectividade com a Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10). Os intervalos de endereços IP e URLs do teams Endpoint estão listados nas [URLs e nos intervalos de endereços IP do Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). (Observação: abrir conectividade com as portas TCP 80 e 443 e para portas UDP 3478 a 3481 é necessária.) Além disso, o Microsoft Teams tem uma dependência do Skype for Business Online, que também deve estar conectado à Internet.

A conectividade de fluxos de mídia do teams é implementada por meio dos procedimentos padrão IETF ICE (estabelecimento de conectividade interativa).

### <a name="interoperability-restrictions"></a>Restrições de interoperabilidade
**Retransmissores de mídia de terceiros**: um fluxo de mídia do Teams (ou seja, um dos pontos de extremidade de mídia são equipes) pode atravessar apenas equipes ou retransmissões de mídia nativas do Skype for Business. Não há suporte para a interoperabilidade com uma transmissão de mídia de terceiros. (Observação: um SBC de terceiros no limite com PSTN deve encerrar o fluxo RTP/RTCP, protegido via SRTP e não retransmitir para o próximo nó.)

**Servidores proxy SIP de terceiros**: uma caixa de diálogo de SINALização SIP de equipes com um SBC e/ou gateway de terceiros pode atravessar equipes ou proxies SIP nativos do Skype for Business. Não há suporte para interoperabilidade com um proxy SIP de terceiros.

**B2BUA de terceiros (ou seja, SBC)**: um fluxo de mídia do teams de/para a PSTN é encerrado por um SBC de terceiros. No entanto, a interoperabilidade com um SBC de terceiros na rede de equipes (ou seja, um SBC SBC de terceiros/Skype for Business não é compatível com o Microsoft Media Teams).

### <a name="technologies-that-are-not-recommended-with-microsoft-teams"></a>Tecnologias que não são recomendadas com o Microsoft Teams

**Rede VPN**: não é recomendável para tráfego de mídia (ou seja, fluxo 2 '). O cliente VPN deve usar a VPN dividida e direcionar o tráfego de mídia como qualquer usuário não VPN externo, https://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/conforme especificado em.

>**Observação**: embora o título seja o Lync, ele também se aplica ao Teams.

**Formas de pacote**: qualquer tipo de recorte de pacote, inspeção de pacote ou dispositivos de forma de pacote não são recomendados e podem degradar a qualidade de modo significativo. 

### <a name="principles"></a>Básicos
Há quatro princípios gerais que ajudam você a entender os fluxos de chamadas do Microsoft Teams:
 
1.  Uma conferência do Microsoft Teams é hospedada pelo Office 365 na mesma região onde o primeiro participante ingressou. (Observação: se houver exceções a essa regra em algumas topologias, elas serão descritas neste documento e são ilustradas por um fluxo de chamadas apropriado.)

2.  Um ponto de extremidade de mídia do Microsoft Teams no Office 365 é usado com base nas necessidades de processamento de mídia e não com base no tipo de chamada. (Por exemplo, uma chamada ponto a ponto pode usar um ponto de extremidade de mídia na nuvem para processar mídia para transcrição e/ou gravação, enquanto uma conferência com dois participantes pode não usar qualquer ponto de extremidade de mídia na nuvem.) No entanto, a maioria das conferências usará um ponto de extremidade de mídia para fins de mixagem e roteamento, alocado onde a conferência está hospedada. O tráfego de mídia enviado de um cliente para o ponto de extremidade de mídia pode ser roteado diretamente ou usar uma retransmissão de transporte no Office 365, se necessário, devido às restrições de firewall de rede do cliente. 

3.  O tráfego de mídia para chamadas ponto a ponto leva a rota mais direta que está disponível, pressupondo que a chamada não seja obrigatória para um ponto de extremidade de mídia na nuvem (Veja #2 acima). A rota preferida é direto para o par remoto (cliente), mas se essa rota não estiver disponível, uma ou mais retransmissões de transporte retransmitirão o tráfego. É recomendável que o tráfego de mídia não entre em um servidor, como formas de pacote, servidores VPN e assim por diante, pois isso afetará a qualidade da mídia.

4.  O tráfego de sinalização sempre vai para o servidor mais próximo ao usuário. 

Para saber mais sobre os detalhes no caminho de mídia escolhido, consulte https://www.youtube.com/watch?v=1tmHMIlAQdo.

## <a name="call-flows-in-various-topologies"></a>Fluxos de chamadas em várias topologias
### <a name="teams-topology"></a>Topologia de equipes
Essa topologia é usada por clientes que aproveitam os serviços do Team da nuvem sem nenhuma implantação local, como o Skype for Business Server ou o roteamento direto do sistema telefônico. Além disso, a interface para o Office 365 é feita pela Internet sem a rota do Azure Express. 

[![Fluxos de chamadas online do Microsoft Teams figura 01](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Figura 1: topologia da equipe*

Observe que:

- A direção das setas no diagrama acima refletem a direção de início da comunicação que afeta a conectividade nos perímetros da empresa. No caso do UDP para mídia, o primeiro pacote (s) pode fluir na direção inversa, mas esses pacotes podem ser bloqueados até que os pacotes na outra direção fluam.
- O Microsoft Teams é implantado lado a lado com o Skype for Business Online, portanto, os clientes são exibidos como "Teams/usuários do SFB".

Você pode encontrar mais informações sobre as seguintes topologias opcionais mais adiante neste artigo:

- A implantação do Skype for Business local é descrita na **topologia híbrida do teams**.
- O roteamento direto do sistema telefônico (para conectividade PSTN) é descrito em **equipes com a topologia de roteamento direto**.
- A rota expressa é descrita em **equipes com otimização de rota expressa**.

**Descrições do fluxo**:
- **Fluxo 2** – representa um fluxo iniciado por um usuário na rede do cliente para a Internet, como parte da experiência de equipes do usuário. Exemplos desses fluxos são mídias de DNS e ponto a ponto.
- **Flow 2 '** – representa um fluxo iniciado por um usuário remoto do teams Mobile, com VPN para a rede do cliente. 
- **Fluxo 3** – representa um fluxo iniciado por um usuário remoto do teams Mobile para pontos de extremidade do Office 365/Teams. 
- **Fluxo 4** – representa um fluxo iniciado por um usuário na rede do cliente para pontos de extremidade do Office 365/Teams.
- **Fluxo 5** – representa um fluxo de mídia ponto a ponto entre um usuário do Teams e outras equipes ou usuário do Skype for Business na rede do cliente.
- **Fluxo 6** – representa um fluxo de mídia ponto a ponto entre um usuário remoto do Microsoft Teams e outras equipes móveis remotas ou usuários do Skype for Business pela Internet.

#### <a name="use-case-one-to-one"></a>Caso de uso: um-para-um
As chamadas um para um usam um modelo comum em que o chamador obterá um conjunto de candidatos que consistem em endereços IP/portas, incluindo local, retransmissão e reflexiva (endereço IP público do cliente, como visto pelos candidatos à retransmissão). O chamador envia esses candidatos para a parte chamada; a parte chamada também obtém um conjunto de candidatos semelhante e envia-o para o chamador. As mensagens de verificação de conectividade STUN são usadas para localizar quais chamadas de caminhos de mídia do chamador/chamadas funcionam e o melhor caminho de trabalho está selecionado. Mídia (ou seja, pacotes RTP/RTCP protegidos via SRTP) são enviadas usando o par de candidatos selecionado. A retransmissão de transporte é implantada como parte do Office 365.

Se os candidatos a portas/endereços IP locais ou os candidatos reflexivo tiverem conectividade, o caminho direto entre os clientes (ou via NAT) será selecionado para mídia. Se os clientes estiverem na rede do cliente, o caminho direto deve ser selecionado. Isso requer conectividade UDP direta na rede do cliente. Se os clientes forem usuários de nuvem do Nomadic, dependendo do NAT/Firewall, a mídia poderá usar a conectividade direta.

Se um cliente for interno na rede do cliente e um cliente for externo (por exemplo, um usuário da nuvem móvel), é improvável que a conectividade direta entre os candidatos locais ou reflexivas está funcionando. Nesse caso, uma opção é usar um dos candidatos de retransmissão de transporte do cliente (por exemplo, o cliente interno obteve um candidato de retransmissão do Office 365; o cliente externo precisa ser capaz de enviar pacotes STUN/RTP/RTCP para o retransmissão de transporte). Outra opção é o cliente interno que envia ao candidato de retransmissão obtido pelo cliente de nuvem móvel. Observe que, embora a conectividade UDP para mídia seja altamente recomendável, o TCP tem suporte.

**Etapas de alto nível**:
1. O usuário do teams A resolve o nome de domínio (DNS) da URL via flow2
2. O usuário do teams aloca uma porta de retransmissão de mídia no Teams Transport Relay via fluxo 4
3. O usuário do teams A envia "convite" com candidatos para ICE via fluxo 4 para o Office 365
4. O Office 365 envia uma notificação para o usuário do teams B via fluxo 4
5. O usuário do teams B aloca uma porta de retransmissão de mídia no Teams Transport Relay via fluxo 4
6. O usuário do teams B envia "Answer" com candidatos A ICE via fluxo 4, que é encaminhado ao usuário do teams A via fluxo 4
7. Os usuários do teams A e do Team usuário B chamam testes de conectividade do ICE e o melhor caminho de mídia disponível está selecionado (veja os diagramas abaixo para vários casos de uso)
8. Os usuários do teams enviam telemetria ao Office 365 via fluxo 4

**Na rede do cliente:**

[![Fluxos de chamadas online do Microsoft Teams Figura 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Figura 2-na rede do cliente*
 
Na etapa 7, o fluxo de mídia ponto a ponto 5 é selecionado.
 
Mídia bidirecional. A direção do fluxo 5 indica que um dos dois lados inicia a comunicação a partir de uma perspectiva de conectividade, consistente com todos os fluxos neste documento. Nesse caso, não importa qual direção será usada porque os dois pontos de extremidade estão dentro da rede do cliente.

**Rede do cliente para usuário externo (mídia retransmitida pela retransmissão de transporte do Teams):**

[![Fluxos de chamadas online do Microsoft Teams Figura 03](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Figura 3: rede do cliente para usuário externo (mídia retransmitida pela retransmissão de transporte do Teams)*
 
Na etapa 7, fluxo 4, da rede do cliente para o Office 365 e fluxo 3, do usuário remoto do Microsoft Mobile Teams para o Office 365, estão selecionadas. Esses fluxos são retransmitidos pela retransmissão de transporte do teams dentro do Office 365.

Mídia é bidirecional, em que a direção indica qual lado inicia a comunicação de uma perspectiva de conectividade. Nesse caso, esses fluxos são usados para sinalização e mídia, por meio de diferentes protocolos e endereços de transporte.

**Rede do cliente para usuário externo (mídia direta):**

[![Fluxos de chamadas online do Microsoft Teams figura 04](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Figura 4: rede de cliente para usuário externo (mídia direta)*
 
Na etapa 7, fluxo 2, da rede do cliente para a Internet (par do cliente), está selecionado.
- A mídia direta com usuário remoto remoto (isto é, não retransmitido por meio do Office 365) é opcional. Em outras palavras, o cliente pode bloquear esse caminho para impor um caminho de mídia por meio da retransmissão de transporte no Office 365.

- Mídia bidirecional. A direção do fluxo 2 para o usuário móvel remoto indica que um dos dois usuários inicia a comunicação a partir de uma perspectiva de conectividade. 

**Usuário da VPN para usuário interno (mídia retransmitida pela retransmissão de transporte do Teams)**

[![Fluxos de chamadas online do Microsoft Teams figura 05](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Figura 5-usuário da VPN para usuário interno (mídia retransmitida pelo retransmissor de transporte de equipes)*
 
A sinalização entre a VPN para a rede do cliente está via fluxo 2 '. Sinalizar entre a rede do cliente e o Office 365 é por meio do fluxo 4. No entanto, a mídia ignora a VPN e é roteada via fluxos 3 e 4 por meio do teams Media Relay no Office 365.

**Usuário VPN para usuário interno (mídia direta)**

[![Fluxos de chamadas online do Microsoft Teams figura 06](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Figura 6-usuário da VPN para usuário interno (mídia direta)*

A sinalização entre a VPN para a rede do cliente está via fluxo 2 '. Sinalizar entre a rede do cliente e o Office 365 é por meio do fluxo 4. No entanto, a mídia ignora a VPN e é roteada via fluxo 2 da rede do cliente para a Internet.

Mídia bidirecional. A direção do fluxo 2 para o usuário móvel remoto indica que um lado inicia a comunicação a partir de uma perspectiva de conectividade.

**Usuário VPN para usuário externo (mídia direta)**

[![Fluxos de chamadas do Microsoft Teams figura 07](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Figura 7-usuário da VPN para usuário externo (mídia direta)*

A sinalização entre o usuário da VPN para a rede do cliente é via fluxo 2 ' e via fluxo 4 para o Office 365. No entanto, a mídia ignora a VPN e é roteada via fluxo 6.

Mídia bidirecional. A direção do fluxo 6 para o usuário remoto do celular indica que um lado inicia a comunicação de uma perspectiva de conectividade.

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>Caso de uso: equipes para PSTN por meio do tronco do Office 365
O Office 365 tem um sistema telefônico que permite a colocação e o recebimento de chamadas da PSTN (rede telefônica pública comutada). Se o tronco PSTN estiver conectado pelo plano de chamadas do sistema telefônico, não haverá requisitos de conectividade especiais para esse caso de uso. (Se você quiser conectar seu próprio tronco PSTN local ao Office 365, poderá usar o roteamento direto do sistema telefônico.)

[![Fluxos de chamadas online do Microsoft Teams Figura 08](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Figura 8: equipes para PSTN por meio do tronco do Office 365*

#### <a name="use-case-teams-meeting"></a>Caso de uso: reunião do teams

O servidor de conferência de VBSS (áudio/vídeo/tela) é parte do Office 365. Ele tem um endereço IP público que deve ser alcançável na rede do cliente e deve ser alcançável a partir de um cliente de nuvem do Nomadic. Cada cliente/ponto de extremidade precisa ser capaz de se conectar ao servidor de conferência.

Os clientes internos obterão candidatos locais, reflexivas e de retransmissão da mesma maneira descritas para chamadas individuais. Os clientes enviarão esses candidatos para o servidor de conferência em um convite. O servidor de conferência não usa uma retransmissão porque tem um endereço IP alcançável publicamente, portanto responde com o seu endereço IP local candidato. O cliente e o servidor de conferência verificarão a conectividade da mesma maneira descrita para chamadas individuais. 

Observe que:

- Os clientes do Teams não podem ingressar em reuniões do Skype for Business e os clientes do Skype for Business não podem ingressar em reuniões de equipe

- Um usuário PSTN, opcionalmente, "disca para" ou "discada", dependendo da configuração PSTN do organizador da reunião e/ou do provisionamento de conferência. 

- Um usuário convidado ou um usuário do cliente pode ingressar de uma rede privada convidada, que é protegida via FW/NAT com regras estritas.

[![Fluxos de chamadas online do Microsoft Teams figura 09](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Figura 9-reunião do teams*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Caso de uso: Federação com o Skype for Business no local

**Mídia retransmitida pela retransmissão de transporte do teams no Office 365**

[![Fluxos de chamadas online do Microsoft Teams Figura 10](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Figura 10: mídia retransmitida pela retransmissão de transporte do teams no Office 365*

Observe que:

- A Federação é, por definição, uma comunicação entre dois locatários. Nesse caso, locatário A, que usa o Microsoft Teams com locatário B, que usa o Skype for Business no local. Se o locatário B também estiver usando o Office 365, o cliente Skype for Business teria usado o fluxo 3 para se conectar ao Office 365.

- A sinalização e a mídia do cliente Skype for Business federado para o Skype for Business Server local estão fora do escopo deste documento. No entanto, ele é ilustrado aqui para fins de esclarecimento.

- A sinalização entre o Teams e o Skype for Business é ligada por um gateway no Office 365.

- Nesse caso, a mídia é retransmitida pela retransmissão de transporte do teams no Office 365 para a rede do cliente e cliente Skype for Business remoto via fluxo 4.

**Mídia retransmitida pelo Skype for Business Media Relay no locatário federado**

[![Fluxos de chamadas online do Microsoft Teams Figura 11](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Figura 11-mídia retransmitida pelo Skype for Business Media Relay no locatário federado*

Observe que:

- A sinalização e a mídia do cliente federado Skype for Business para um servidor local do Skype for Business estão fora do escopo deste documento. No entanto, ele é ilustrado aqui para fins de esclarecimento.

- A sinalização entre o Teams e o Skype for Business é ligada por um gateway no Office 365.

- A mídia nesse caso é retransmitida pelo Skype for Business retransmissão de mídia local para a rede do cliente via fluxo 2. (Observe que o tráfego do teams User para o retransmissor de mídia remota na rede do cliente federado será inicialmente bloqueado pelo Media Relay até que o tráfego na direção inversa comece a fluir. No entanto, o fluxo bidirecional abrirá a conectividade em ambas as direções.)

**Direto (ponto a ponto)**

[![Fluxos de chamadas online do Microsoft Teams Figura 12](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Figura 12-direto (ponto a ponto)*

### <a name="teams-hybrid-topology"></a>Topologia híbrida do teams
Essa topologia inclui o Microsoft Teams com uma implantação local do Skype for Business.

[![Fluxos de chamadas online do Microsoft Teams Figura 13](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Figura 13-topologia híbrida do teams*
 
- A direção das setas no diagrama acima refletem a direção de início da comunicação que afeta a conectividade nos perímetros da empresa. No caso do UDP para mídia, o primeiro pacote (s) pode fluir na direção inversa, mas esses pacotes podem ser bloqueados até que os pacotes na outra direção fluam.

- O Microsoft Teams é implantado lado a lado com o Skype for Business Online, portanto, os clientes são exibidos como "Teams/usuários do SFB".

Fluxos adicionais (na parte superior da topologia do Teams):
- **Fluxo 5a** – representa um fluxo de mídia ponto a ponto entre um usuário do teams na rede do cliente e um retransmissor de mídia local do Skype for Business na borda de rede do cliente.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Caso de uso: Teams para Skype for Business One-to-One
**Híbrido dentro da rede do cliente**

[![Fluxos de chamadas online do Microsoft Teams Figura 14](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Figura 14 – híbrido na rede do cliente*
 
A sinalização entre o Teams e o Skype for Business é ligada por um gateway no Office 365. No entanto, a mídia é roteada diretamente no ponto-a-ponto na rede do cliente via fluxo 5.

**Rede de cliente híbrida com usuário externo do Skype for Business – retransmitido pelo Office 365**

[![Fluxos de chamadas online do Microsoft Teams Figura 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Figura 15-rede de cliente híbrida com Skype for Business usuário externo-retransmitido pelo Office 365*

Observe que:

- A sinalização e a mídia do cliente Skype for Business para um servidor local do Skype for Business estão fora do escopo deste documento. No entanto, ele é ilustrado aqui para fins de esclarecimento.

- A sinalização entre o Teams e o Skype for Business é ligada por um gateway no Office 365.

- A mídia é retransmitida pela retransmissão de transporte do teams no Office 365 para a rede do cliente por meio do fluxo 4.

**Rede de cliente híbrida com usuário externo do Skype for Business – retransmitido pela borda local**

[![Fluxos de chamadas online do Microsoft Teams Figura 16](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Figura 16-rede de cliente híbrida com Skype for Business usuário externo-retransmitido pela borda local*
 
Observe que:

- A sinalização e a mídia do cliente Skype for Business para um servidor local do Skype for Business estão fora do escopo deste documento. No entanto, ele é ilustrado aqui para fins de esclarecimento.

- A sinalização é ligada por um gateway no Office 365.

- A mídia é retransmitida pelo Skype for Business Media Relay dentro do Skype for Business no local para o usuário do teams na rede do cliente via fluxo de mídia 5A.

### <a name="teams-with-phone-system-direct-routing-topology"></a>Teams com a topologia de roteamento direto do sistema telefônico
Essa topologia inclui equipes com roteamento direto do sistema telefônico. 

O roteamento direto permite que você use um provedor de serviços de rede de telefonia pública comutada (PSTN) de terceiros ao emparelhar um dispositivo de hardware do controlador de borda de sessão (SBC) com suporte do cliente para o Office 365 e, em seguida, conectar o tronco de telefonia a Esse dispositivo. 

Para dar suporte a esse cenário, o cliente deve implantar um SBC certificado para roteamento direto de um dos parceiros certificados da Microsoft. O SBC deve ser configurado como recomendado pelo fornecedor e ser roteável do Office 365 para tráfego UDP direto. A mídia pode fluir diretamente do Teams e/ou do cliente Skype for Business para o SBC (ignorando o gateway do Teams) ou percorrendo o gateway do teams. A conectividade com o SBC, quando o tronco está configurado para ignorar o gateway de equipe, é baseada em ICE, em que o SBC suporta ICE-Lite, enquanto o ponto de extremidade do teams/Skype for Business é compatível com a ICE cheia. 

[![Fluxos de chamadas online do Microsoft Teams figura 17](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

* Figura 17-equipes com a topologia de roteamento direto do sistema telefônico

Observe que:

- A direção das setas no diagrama acima refletem a direção de início da comunicação que afeta a conectividade nos perímetros da empresa. No caso do UDP para mídia, o primeiro pacote (s) pode fluir na direção inversa, mas esses pacotes podem ser bloqueados até que os pacotes na outra direção fluam.

- O Microsoft Teams é implantado lado a lado com o Skype for Business Online, portanto, os clientes são exibidos como "Teams/usuários do SFB".

Fluxos adicionais (na parte superior da topologia do teams online):
- **Flow 4 '** -representa um fluxo do Office 365 para a rede do cliente, usado para estabelecer uma conexão entre o servidor de mídia do teams na nuvem com o SBC local.
- **Fluxo 5b** – representa um fluxo de mídia entre o usuário do teams na rede do cliente com o SBC Routing direto no modo ignorar.
- **5C de fluxo** – representa um fluxo de mídia entre o SBC de roteamento direto para outro SBC de roteamento direto em um modo de bypass de chamada Conecte PSTN.

**Usuário interno com roteamento direto (mídia retransmitida pela retransmissão de transporte do teams no Office 365)**

[![Fluxos de chamadas online do Microsoft Teams Figura 18](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Figura 18-usuário interno com roteamento direto (mídia retransmitida pelo retransmissor de transporte do teams no Office 365)*

Observe que:
 
- O SBC deve ter um endereço IP público que seja roteável do Office 365.

- Sinalização e mídia do SBC para o Office 365 e vice-versa Use o fluxo 4 e/ou o fluxo 4 '.

- Sinalizar e mídia do cliente na rede do cliente para o Office 365 use o fluxo 4.


**Usuário remoto com roteamento direto (a mídia é roteada por meio de um servidor de mídia (MP) no Office 365)**

[![Fluxos de chamadas online do Microsoft Teams Figura 19](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Figura 19-usuário remoto com roteamento direto (a mídia é roteada por meio de um servidor de mídia (MP) no Office 365)*
 
Observe que:

- O SBC deve ter um endereço IP público que seja roteável do Office 365.

- Sinalização e mídia do SBC para o Office 365 e vice-versa Use o fluxo 4 e/ou o fluxo 4 '.

- Sinalizar e mídia do cliente na Internet para o Office 365 use o fluxo 3.

**Roteamento direto do usuário interno (ignorar mídia)**

[![Fluxos de chamadas online do Microsoft Teams figura 20](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Figura 20-roteamento direto do usuário interno (ignorar mídia)*
 
Observe que:

- O SBC deve ter um endereço IP público que seja roteável do Office 365.

- Sinalizar de SBC para o Office 365 e vice-versa Use o fluxo 4 e/ou o fluxo 4 '.

- A sinalização do cliente na rede do cliente para o Office 365 usa o fluxo 4.

- Mídia do cliente dentro da rede do cliente até o SBC na rede do cliente use o fluxo 5B.

**Usuário remoto com roteamento direto (bypass de mídia retransmitida pela retransmissão de transporte do teams no Office 365)**

[![Fluxos de chamadas online do Microsoft Teams figura 21](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Figura 21-usuário remoto com roteamento direto (bypass de mídia retransmitida pela retransmissão de transporte do teams no Office 365)*

Observe que:

- O SBC deve ter um endereço IP público que seja roteável do Office 365 e Internet.

- A sinalização do SBC para o Office 365 e vice-versa usa o fluxo 4 e/ou o fluxo 4 '.

- A sinalização do cliente na Internet para o Office 365 usa o fluxo 3.

- Mídia do cliente na Internet para o SBC dentro da rede do cliente usa fluxos 3 e 4 retransmitidos pelo Teams Transport Relay no Office 365. 

**Roteamento direto de usuário remoto (bypass de mídia direta)**

[![Fluxos de chamadas online do Microsoft Teams Figura 22](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Figura 22-roteamento direto do usuário remoto (ignorar mídias diretas)*
 
Observe que:

- O SBC deve ter um endereço IP público que seja roteável do Office 365 e da Internet.

- A sinalização do SBC para o Office 365 e vice-versa usa o fluxo 4 e/ou o fluxo 4 '.

- A sinalização do cliente na Internet para o Office 365 usa o fluxo 3.

- Mídia do cliente na Internet para o SBC dentro da rede do cliente usa o fluxo 2.

**Roteamento direto (bypass de mídia) – chamada de conecte PSTN (devido a encaminhamento de chamadas/transferência)**

[![Fluxos de chamadas online do Microsoft Teams Figura 23](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Figura 23-roteamento direto (bypass de mídia)-chamada Conecte PSTN (devido a chamadas para encaminhamento/transferência)*
 
Observe que:

- O SBC deve ter um endereço IP público que seja roteável do Office 365.

- A sinalização do SBC para o Office 365 e vice-versa usa o fluxo 4 e/ou o fluxo 4 '.

- O cliente está fora do loop de sinalização e de mídia após a chamada ser hairpinned de PSTN para PSTN.

- Mídia da instância de SBC A na rede do cliente para a instância do SBC B dentro da rede do cliente (onde, A e B podem ser a mesma instância) usa o fluxo 5C.

**Roteamento direto (mídia por meio do Office 365) – chamada de conecte PSTN em dois locatários**

[![Fluxos de chamadas online do Microsoft Teams figura 24](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Figura 24: roteamento direto (mídia por meio do Office 365) – chamada de conecte PSTN em dois locatários*
 
Observe que:

- O SBC deve ter um endereço IP público que seja roteável do Office 365.

- A sinalização do SBC para o Office 365 e vice-versa usa o fluxo 4 e/ou o fluxo 4 '.

- O cliente está fora do loop de sinalização e de mídia após a chamada ser hairpinned de PSTN para PSTN.

- Mídia da instância SBC A na rede do cliente X para a instância do SBC B deve ser retransmitida pelo servidor de mídia do Office 365 e não pode usar o modo ignorar.

## <a name="teams-with-express-route-optimization"></a>Equipes com otimização de rota expressa

[![Fluxos de chamadas online do Microsoft Teams figura 25](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Figura 25-equipes com otimização de rota expressa*
 
Caso a rota expressa seja justificada e implantada, os fluxos de equipe podem ser roteados novamente do fluxo 4 para o fluxo 1 e do fluxo 4 ' para o fluxo 1 '. No entanto, o aplicativo Teams tem uma dependência sólida em outros fluxos do Office 365 pela Internet via fluxos 4 e 4 '; Portanto, esses fluxos não devem ser bloqueados. 

Observe que o tráfego de borda híbrida do Skype for Business é roteado para a Internet e não para expressar a rota para se comunicar com usuários externos e federar-se com outros locatários. 

Para evitar fluxos assimétricos, o redirecionamento deve estar em ambas as direções. Em outras palavras, um endereço na rede do cliente é roteável pela Internet ou rota expressa, com base na otimização, mas não através de ambos.

Por exemplo:

**Rede do cliente para usuário externo (mídia retransmitida pela retransmissão de transporte do Teams):**

[![Fluxos de chamadas online do Microsoft Teams Figura 26](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*Figura 26-rede de cliente para usuário externo (mídia retransmitida pelo Teams Transport Relay)*
 
**Etapas de alto nível:**
1. O usuário do teams na rede do cliente resolve o nome de domínio de URL (DNS) via flow2
2. O usuário do teams na rede do cliente aloca uma porta de retransmissão de mídia no Teams Transport Relay via fluxo 1
3. O usuário do teams na rede do cliente envia "convite" com candidatos para ICE via fluxo 1 para o Office 365
4. O OFFICE 365 envia uma notificação para o usuário da equipe externa via fluxo 3
5. O usuário externo do teams aloca uma porta de retransmissão de mídia no Teams Transport Relay via fluxo 3
6. O usuário externo do teams envia "Answer" com candidatos A ICE via fluxo 3, que é encaminhado ao usuário do teams A via fluxo 1
7. Os usuários do teams A e do Team usuário B chamam testes de conectividade do ICE e seleciona fluxos 1 e 3, que são retransmitidos pelo Teams Transport Relay no Office 365
8. Os usuários do teams enviam telemetria ao Office 365 via fluxos 1 e 3

>**Observação**: o fluxo 4 deve ser habilitado para dar suporte a dependências do aplicativo Teams em outros micro serviços que exigem fluxo 4.
