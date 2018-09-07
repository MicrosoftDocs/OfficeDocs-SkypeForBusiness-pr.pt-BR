---
title: Fluxos de chamada de equipes da Microsoft Online
author: tonysmit
ms.author: tonysmit
manager: serdars
ms.date: 06/08/2018
ms.topic: article
ms.service: msteams
ms.reviewer: sonua
localization_priority: Priority
search.appverid: MET150
MS.collection: Strat_MT_TeamsAdmin
appliesto:
- Microsoft Teams
description: Descreve como a carga de trabalho de equipes utiliza fluxos do Office 365 em várias topologias.
ms.openlocfilehash: 69b4deb078a0626c8a7cc4dce808825f2d038bac
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23861813"
---
# <a name="microsoft-teams-online-call-flows"></a>Fluxos de chamada de equipes da Microsoft Online

## <a name="overview"></a>Visão geral
Este documento descreve como a carga de trabalho de equipes utiliza fluxos do Office 365 em várias topologias. Além disso, ele especifica exclusivos fluxos de equipes que são usados para comunicação de mídia ponto a ponto. O documento enumera esses fluxos e descreve suas finalidades e suas redes de origem/rescisão. Por exemplo, o fluxo de X é usado pelo cliente do Office 365 no local para se comunicar com o serviço Office 365 na nuvem, originada de rede do cliente e terminada por um ponto de extremidade na nuvem do Office 365, e Y do fluxo é usado pelo cliente do Office 365 no local para se comunicar com um serviço na Internet, que o Office 365 tem dependência em, originada de rede do cliente e é terminado por um ponto de extremidade na Internet.

O documento tem três seções principais. O primeiro fornece um informações básicas, como redes (que podem atravessar fluxos do Office 365), o tipo de tráfego, diretrizes de conectividade de rede do cliente para pontos de extremidade de serviço Office 365, interoperabilidade com componentes de terceiros e entidades que são usados pelas equipes para selecionar os fluxos de mídia. A segunda ilustra o uso desses fluxos em várias topologias. Para cada topologia, ele enumera todos os fluxos de suportados e ilustra como esses fluxos são usados por meio de vários casos de uso. Para cada caso de uso, ele descreve a sequência e seleção de fluxos por meio de um diagrama de fluxo. A terceira descreve como esses fluxos são utilizados quando Express rota será implantada para otimização, ilustrada por meio de uma topologia simples.

## <a name="background"></a>Plano de fundo
### <a name="network-segments"></a>Segmentos de rede
**Rede do cliente**: esse é o segmento de rede que faz parte da sua rede geral que você controlar e gerenciar. Isso inclui todas as conexões de cliente em escritórios de cliente, se com ou sem fio, entre prédios, em centros de dados local e as conexões estabelecidas com o Internet provedores, rota Express ou qualquer outro privada correspondência. 

Geralmente, uma rede de cliente tem várias perímetro de rede com firewalls e/ou servidores proxy, qual aplicar políticas de segurança de uma organização e que permitir apenas determinado tráfego de rede que você configure e configurou. Porque o cliente gerencia esta rede, o cliente tem controle direto sobre o desempenho da rede e é altamente recomendável que o cliente completo rede avaliações para validar o desempenho dentro dos sites em sua rede e de seu rede a rede do Office 365. Skype para negócios na implantação local e PSTN Session Border Controller para se conectar com PSTN por meio de sua rede (ou seja, direto roteamento) são opcionais.

**Internet**: esse é o segmento de rede que faz parte da sua rede geral que será usada pelos usuários que estiverem se conectando ao Office 365 na nuvem de fora da rede do cliente. Ele também é usado por alguns tráfego de rede do cliente para Office 365 na nuvem. 

**Visitado/convidado de rede privada**: esse é o segmento de rede fora da rede do cliente, mas não no Internet pública, que seus usuários e/ou seus convidados podem visitar. Por exemplo, rede privada residencial ou em uma rede privada, empresa, que não implante equipes, onde os seus usuários e/ou seus clientes que interagem com os serviços de equipes, podem residir.

>**Observação**: conectividade com o Office 365b também é aplicável a essas redes.

**Office 365 na nuvem**: esse é o segmento de rede que ofereça suporte a serviços do Office 365. Ele é distribuído em todo o mundo com bordas próximos de rede do cliente na maioria dos locais. Funções mencionadas neste documento incluem a retransmissão de transporte, o servidor de webconferência e o processador de mídia. 

**Rota Express (opcional)**: Este é o segmento de rede que faz parte da sua rede geral que fornecerá a você uma conexão dedicada, privada para a rede do Office 365.

### <a name="types-of-traffic"></a>Tipos de tráfego

**Mídia em tempo real**: dados encapsulados dentro RTP (real-time Transport Protocol) e suporte a áudio, vídeo e compartilhamento de cargas de trabalho de tela. Em geral, o tráfego de mídia é altamente latência minúsculas, portanto você gostaria que esse tráfego assuma o caminho mais direto possíveis e usar UDP versus TCP como o protocolo de camada de transporte, que é o transporte recomendado para a mídia de tempo de interativo real da perspectiva de qualidade. (Observação: como último recurso, mídia pode usar o TCP/IP e também ser encapsulada no protocolo HTTP, mas isso não é recomendável devido às implicações de qualidade ruim.) Fluxo RTP é protegido por meio do SRTP, no qual apenas a carga é criptografada.

**Sinalização**: O link de comunicação entre o cliente e servidor ou outros clientes que são usados para controlar as atividades (por exemplo, quando uma chamada é iniciada) e entregar mensagens instantâneas. Tráfego de sinalização mais usa as interfaces do REST baseada em HTTPS, embora em alguns cenários (por exemplo, a conexão entre o Office 365 na nuvem e um controlador de borda de sessão) usa o protocolo SIP. É importante entender que esse tráfego é muito menos sensível a latência, mas pode causar interrupções de serviço ou chamada tempos limite se latência entre os pontos de extremidade exceder vários segundos. 

### <a name="connectivity-to-office-365"></a>Conectividade com o Office 365

Serviço de equipes requer [conectividade à Internet](https://support.office.com/article/connectivity-to-the-internet-64b420ef-0218-48f6-8a34-74bb27633b10). Pontos de extremidade de equipes URLs e intervalos de endereços de IP são listados em [URLs do Office 365 e intervalos de endereços IP](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges). (Observação: exige a conectividade para as portas TCP 80 e 443 aberta e as portas UDP 3478 3481 até.) Além disso, o serviço de equipes tem dependência em Skype para serviço online de business, daí é necessária para conectar-se também esse serviço para a Internet.

Conectividade de fluxos de mídia de equipes é implementada por meio de procedimentos padrão da IETF ICE (estabelecimento de conectividade interativa).

### <a name="interoperability-restrictions"></a>Restrições de interoperabilidade
**Mídia de terceiros retransmite**: fluxo de mídia de equipes de uma (ou seja, um dos pontos de extremidade de mídia é equipes) pode atravessar somente equipes ou Skype retransmissões mídia nativo de negócios. Não há suporte para a interoperabilidade com uma retransmissão de mídia de terceiros. (Observação: um terceiro SBC o limite com PSTN deve encerrar o fluxo RTP/RTCP, protegido por meio do SRTP e não retransmiti-lo para o próximo salto.)

**Servidores Proxy SIP de terceiros**: equipes de uma caixa de diálogo SIP com um terceiro SBC e/ou Gateway de sinalização pode atravessar equipes ou Skype para proxies SIP nativos de negócios. Não há suporte para a interoperabilidade com terceiros Proxy SIP.

**B2BUA de terceiros (isto é, SBC)**: fluxo de mídia A equipes de/para PSTN é encerrado por um terceiro SBC. No entanto, interoperabilidade com terceiros SBC dentro da rede de equipes (ou seja, a terceira parte SBC Media dois pontos de extremidade de equipes/Skype For Business) não é suportada.

### <a name="technologies-that-are-strongly-not-recommended-with-microsoft-teams"></a>Tecnologias altamente não são recomendadas com Microsoft Teams

**Rede VPN**: altamente não é recomendado para o tráfego de mídia (ou seja, fluxo 2'). Cliente VPN deve utilizar divisão VPN e rotear tráfego de mídia como qualquer usuário externo não VPN, conforme especificado nahttps://blogs.technet.microsoft.com/nexthop/2011/11/14/enabling-lync-media-to-bypass-a-vpn-tunnel/ 

>**Observação**: Embora o título do Lync, é aplicável às equipes também.

**Pacote Shapers**: qualquer tipo de snippers de pacotes, inspeção de pacotes ou dispositivos de Modelador de pacotes altamente não são recomendados e pode reduzir significativamente a qualidade. 

### <a name="principles"></a>Princípios
Existem quatro princípios gerais que o ajudarão a entender fluxos de chamada for Microsoft Teams. 
1.  Uma conferência do Microsoft Teams é hospedada pelo Office 365 na nuvem na mesma região onde o primeiro participante entrou. (Observação: se haverá exceções a essa regra em algumas topologias, eles serão descritos neste documento, ilustrada por um fluxo de chamadas apropriada.)
2.  Uma empresa de mídia de equipes (MP) no Office 365 nuvem é usado com base em necessidades de processamento de mídia e não com base no tipo de chamada. (Por exemplo, uma chamada ponto a ponto pode usar um ponto de extremidade de mídia na nuvem para mídia de processo para transcrição e/ou gravação, enquanto uma conferência com dois participantes não pode usar qualquer ponto de extremidade de mídia na nuvem.) No entanto, a maioria das conferências usará um MP para misturar e roteamento finalidades, alocadas onde a conferência está hospedada. O tráfego de mídia enviado de um cliente para o MP poderão ser roteadas diretamente ou usar uma retransmissão de transporte, em nuvem do Office 365, se for necessário devido a restrições de firewall de rede do cliente. 
3.  Tráfego de mídia para chamadas ponto a ponto levar a rota mais direta que está disponível, supondo que a chamada não exige um MP na nuvem (consulte #2 acima). A rota preferencial é direta ao peer remoto (cliente), mas se essa rota não estiver disponível, um ou mais retransmissões de transporte irá retransmitir o tráfego. É recomendável que o tráfego de mídia deve servidores não transversal como shapers de pacotes, servidores VPN, etc., pois isso afetará a qualidade de mídia.
4.  Tráfego de sinalização sempre vai para o servidor mais próximo ao usuário. 

Para saber mais sobre os detalhes sobre o caminho de mídia for escolhido, consulte https://www.youtube.com/watch?v=aD5mUg2ZzLQ.

## <a name="call-flows-in-various-topologies"></a>Fluxos de chamada em várias topologias
### <a name="teams-online-pure-topology"></a>Topologia ("pura") Online de equipes
Esta topologia é usada por clientes que utilizam serviços de equipes da nuvem sem implantar qualquer servidor, como Skype para negócios e SBC para roteamento direto, no local. Além disso, a interface para o Office 365 é feita através da Internet sem rota Express do Azure. 

[![Figura 01 fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure01.png)](media/microsoft-teams-online-call-flows-figure01.png)

*Figura 1 - topologia ('puro') Online de equipes*

>**Observações**:
>- A direção das setas no diagrama acima refletem a direção de iniciação da comunicação que afeta o perímetro corporativo de conectividade. No caso de UDP para a mídia, o primeiro pacote pode fluir na direção contrária, mas esses pacotes poderão ser bloqueados até que os pacotes na outra direção fluirá.
>- As equipes Online será implantada lado a lado com Skype para Business Online, daí os clientes são exibidos como "User equipes/SFB".

- Skype opcional para negócios na implantação local é descrito neste documento na seção **Topologia híbrida Online de equipes**
- O roteamento direto opcional para o PSTN é descrito neste documento na seção **Equipes Online com topologia de roteamento direto**
- Roteiro de Express opcional é descrito neste documento na seção **equipes c / otimização de rota Express**

**Flui descrições**:
- **Fluxo 2** – representa um fluxo iniciado por um usuário na rede de cliente para a Internet como parte da sua experiência de equipes. Exemplos desses fluxos são DNS e mídia ponto a ponto.
- **Fluxo 2'** – representa um fluxo iniciado por um celular equipes usuário remoto, qual VPN para a rede do cliente. 
- **Fluxo de 3** – representa um fluxo iniciado por um usuário de equipes móvel remoto aos pontos de extremidade do Office 365/Teams. 
- **Fluxo de 4** – representa um fluxo iniciado por um usuário na rede do cliente para pontos de extremidade do Office 365/Teams.
- **Fluxo de 5** – representa um fluxo de mídia ponto a ponto entre o usuário de equipes e outro equipes ou Skype para usuário corporativos, dentro da rede do cliente.
- **Fluxo 6** – representa o fluxo de mídia de uma ponto a ponto entre um usuário remoto de equipes móvel e outro remoto equipes móveis ou Skype para o usuário de negócios, pela Internet.

#### <a name="use-case-one-to-one"></a>Caso de uso: um para um
Chamadas-to-usar um modelo comum que o chamador será obter um conjunto de candidatos consistindo endereços IP/portas; local, retransmissão e reflexiva (endereço IP público do cliente, como visto pela retransmissão). O chamador envia essas candidatos para a parte chamada no convite da, a parte chamada também obtém um conjunto similar de candidatos e as envia para o chamador. Verificação de conectividade STUN mensagens são usadas para localizar qual chamador/chamado funcionam de caminhos de mídia de terceiros e o melhor caminho de trabalho está selecionada. Mídia (ou seja, pacotes RTP/RTCP protegidos por meio do SRTP), em seguida, é enviadas usando o par de candidato selecionado. A retransmissão de transporte é implantada como parte do Office 365 nuvem.

Se o IP local endereço/porta candidatos ou os candidatos reflexivas tem conectividade, e em seguida, o caminho direto entre os clientes (ou por meio de um NAT) será selecionado para a mídia. Se os clientes estiverem na rede do cliente, o caminho direto deve ser selecionado. Isso requer conectividade direta de UDP dentro da rede do cliente. Se os clientes forem ambos os usuários na nuvem nômades, em seguida, dependendo do NAT/firewall, mídia pode usar conectividade direta.

Se um cliente é interno na rede do cliente e um cliente é externa (por exemplo, o usuário móvel nuvem), em seguida, ele é improvável que conectividade direta entre os candidatos locais ou reflexivas está funcionando. Nesse caso, uma opção é usar um dos candidatos transporte retransmissão de qualquer cliente (por exemplo, o cliente interno obtido um candidato a retransmissão da retransmissão de transporte no Office 365 na nuvem, o cliente externo deve ser capaz de enviar pacotes STUN/RTP/RTCP para o retransmissão de transporte). Outra opção é que o cliente interno envia para o candidato a retransmissão obtido pelo cliente móvel de nuvem. Observe que, embora conectividade UDP para a mídia é altamente recomendável, TCP é suportado.

**Etapas de alto nível**:
1. As equipes de usuário resolve URL nome de domínio (DNS) via Fluxo2
2. O usuário de equipes A porta de retransmissão em equipes transporte Relay via fluxo 4 de uma mídia aloca
3. As equipes de usuário A envia "convidar" com candidatos ICE via fluxo 4 para o Office 365
4. OFFICE 365 envia uma notificação para o usuário B equipes via fluxo 4
5. O usuário B equipes aloca uma mídia porta de retransmissão em equipes transporte Relay via fluxo 4
6. As equipes usuário B envia "answer" com candidatos ICE via fluxo 4, que é encaminhada de volta ao usuário equipes via fluxo 4
7. Equipes usuário B e equipes usuário invocam ICE testes de conectividade e o melhor caminho de mídia disponível está selecionado (consulte diagramas abaixo para diversas casos de uso)
8. Usuários de equipes enviam telemetria para Office 365 via fluxo 4

**Dentro da rede do cliente:**

[![Fluxos de chamada Online do Microsoft equipes Figura 02](media/microsoft-teams-online-call-flows-figure02-thumbnail.png)](media/microsoft-teams-online-call-flows-figure02.png)

*Figura 2 - dentro da rede do cliente*
 
Na etapa 7, o fluxo de mídia "peer-to-peer" 5 for selecionado 
>**Observação**: mídia é bidirecional. A direção do fluxo de 5 indica que um lado inicia a comunicação da perspectiva de conectividade, consistente com todos os fluxos neste documento. Nesse caso, não importa qual direção é usada porque os dois pontos de extremidade estão dentro da rede do cliente.

**Rede de cliente para usuários externos (retransmitidas por equipes transporte retransmissão de mídia):**

[![Figura 03 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure03-thumbnail.png)](media/microsoft-teams-online-call-flows-figure03.png)

*Figura 3 - rede do cliente para usuários externos (retransmitidas por equipes transporte retransmissão de mídia)*
 
Na etapa 7, fluxo 4, da rede de cliente para o Office 365 e fluxo de 3, do usuário remoto de equipes móvel para o Office 365, são selecionados. Esses fluxos são retransmitidos por equipes retransmissão de transporte no Office 365.

>**Observação**: mídia é bidirecional, onde a direção indica qual lado inicia a comunicação da perspectiva de conectividade. Nesse caso, esses fluxos são usados para a sinalização e mídia, por meio de endereços e protocolos de transporte diferentes.

**Rede de cliente para usuários externos (direct media):**

[![Figura 04 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure04-thumbnail.png)](media/microsoft-teams-online-call-flows-figure04.png)

*Figura 4 - rede do cliente para usuários externos (direct mídia)*
 
Na etapa 7, 2, de fluxo de rede do cliente para a Internet (peer do cliente), está selecionado.
>**Observações**: 
>- Direcionar mídia com o usuário móvel remoto (ou seja, não serão retransmitidas por meio do Office 365 na nuvem) é opcional. Em outras palavras, o cliente pode bloquear este caminho e fazendo isso, impor um caminho de mídia por meio de retransmissão de transporte no Office 365 na nuvem.
>- Mídia é bidirecional. A direção do fluxo de 2 para o usuário móvel remoto indica que um lado inicia a comunicação de uma perspectiva de conectividade. 

**Usuário de VPN para usuário interno (retransmitidas por equipes transporte retransmissão de mídia)**

[![Figura 05 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure05-thumbnail.png)](media/microsoft-teams-online-call-flows-figure05.png)

*Figura 5 - usuário VPN para usuário interno (retransmitidas por equipes transporte retransmissão de mídia)*
 
Sinalização VPN para a rede do cliente via fluxo 2' e fluxo de 4 para o Office 365. No entanto, bypass de mídia "" VPN e roteado por meio de fluxos de 3 e 4 a retransmissão de mídia de equipes no Office 365 na nuvem.

**Usuário de VPN para usuário interno (direct mídia)**

[![Figura 06 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure06-thumbnail.png)](media/microsoft-teams-online-call-flows-figure06.png)

*Figura 6 - usuário VPN para usuário interno (direct mídia)*

Sinalização VPN para a rede do cliente via fluxo 2' para a rede do cliente e fluxo de 4 para o Office 365. No entanto, bypass de mídia "" VPN e roteado por meio de fluxo 2 da rede do cliente para a internet.

>**Observação**: mídia é bidirecional. A direção do fluxo de 2 para o usuário móvel remoto indica que um lado inicia a comunicação de uma perspectiva de conectividade.

**Usuário de VPN para usuários externos (direct mídia)**

[![Figura 07 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure07-thumbnail.png)](media/microsoft-teams-online-call-flows-figure07.png)

*Figura 7 - usuário VPN para usuários externos (direct mídia)*

Sinalização VPN para a rede do cliente via fluxo 2' para a rede do cliente e fluxo de 4 para o Office 365. No entanto, bypass de mídia "" VPN e roteado por meio de fluxo de 6.

>**Observação**: mídia é bidirecional. A direção do fluxo de 6 para usuários móveis remotos indica que um lado inicia a comunicação de uma perspectiva de conectividade.

#### <a name="use-case-teams-to-pstn-through-office-365-trunk"></a>Caso de uso: As equipes PSTN através de tronco do Office 365
Nuvem do Office 365 tem um sistema telefônico que permite fazer e receber as chamadas da rede telefônica pública comutada. Se o tronco PSTN estiver conectado por meio do Office 365 na nuvem, existem requisitos especiais de conectividade para este caso de uso. Caso contrário, (roteamento direto é implantado), em seguida, consulte a seção **TBD**.

[![Figura 08 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure08-thumbnail.png)](media/microsoft-teams-online-call-flows-figure08.png)

*Figura 8 - as equipes de PSTN por meio de tronco do Office 365*

#### <a name="use-case-teams-meeting"></a>Caso de uso: Reunião de equipes

A áudio/vídeo/compartilhamento de tela (VBSS) o servidor de conferência é parte da nuvem Office 365. Ele tem um endereço IP público que deve ser alcançados da rede do cliente e deve ser acessível a partir de um cliente de nuvem nômades. Cada cliente/ponto de extremidade precisa ser capaz de conectar o servidor de conferência.

Os clientes internos obterão local, reflexiva e candidatos de retransmissão como da mesma maneira como descrito para chamadas de um para um. Os clientes enviará esses candidatos para o servidor de conferência em um convite. O servidor de conferência não usa uma retransmissão, pois ele tem um endereço IP publicamente acessível, para que ele responde com apenas seu local candidato de endereço IP. O servidor de conferência e o cliente verificar a conectividade da mesma forma descrita para chamadas de um para um. 

>**Observações**:
>- Clientes de equipes não conseguem ingressar Skype para reuniões de negócios e Skype para clientes corporativos não conseguem ingressar em reuniões de equipes.
>- Usuário PSTN opcionalmente "disca pol" ou "Discado check-OUT", depende da reunião organizador chamada PSTN e/ou o provisionamento de conferência. 
>- Um usuário convidado ou do cliente podem ingressar de uma rede privada convidado, que é protegida por meio de firmware/NAT com regras de estrita.

[![Figura 09 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure09-thumbnail.png)](media/microsoft-teams-online-call-flows-figure09.png)

*Figura 9 - às equipes de reunião*

#### <a name="use-case-federation-with-skype-for-business-on-premises"></a>Uso de caso: Federação com Skype for Business no local

**Mídia retransmitidas por equipes retransmissão de transporte na nuvem do Office 365**

[![Figura 10 fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure10-thumbnail.png)](media/microsoft-teams-online-call-flows-figure10.png)

*Figura 10 - mídia retransmitido por equipes retransmissão de transporte na nuvem do Office 365*

>**Observações**: 
>- "Federação" é, por definição, uma comunicação entre dois inquilinos. Nesse caso, o locatário A, que usa as equipes Online, agrupa com locatário B, que usa o Skype para negócios no local. Se locatário B também estiver usando o Office 365, em seguida, Skype para Business client teria que usar fluxo 3 para se conectar com o Office 365.
>- Sinalização e a mídia do cliente do Skype para negócios federado para sua Skype for Business no servidor local está fora do escopo deste documento. No entanto, ele é mostrado aqui para manter a clareza.

Sinalização entre equipes e Skype para negócios "com ponte" por um Gateway na nuvem do Office 365.

Nesse caso, mídia é retransmitida por equipes retransmissão de transporte no Office 365 na nuvem para a rede do cliente e do Skype remoto para o cliente de negócios via fluxos 4.

**Mídia retransmitidas por Skype para retransmissão de mídia de negócios no locatário federado**

[![Figura 11 fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure11-thumbnail.png)](media/microsoft-teams-online-call-flows-figure11.png)

*Figura 11 - mídia retransmitido por Skype para retransmissão de mídia de negócios no locatário federado*

>**Observação**: sinalização e mídia do cliente do Skype para negócios federado para sua Skype for Business no servidor local está fora do escopo deste documento. No entanto, ele é mostrado aqui para manter a clareza.

Sinalização entre equipes e Skype para negócios "com ponte" por um Gateway na nuvem do Office 365.

Nesse caso, mídia é retransmitida por Skype for Business no local de retransmissão de mídia para a rede do cliente via fluxo 2. (Observe que o tráfego de usuário de equipes para a retransmissão de mídia remoto na rede do cliente federado será inicialmente bloqueado pela retransmissão de mídia até que o tráfego na direção contrária começa a fluxo. No entanto, o fluxo bidirecional abrirá conectividade em ambas as direções.)

**Direto (ponto a ponto)**

[![Figura 12 fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure12-thumbnail.png)](media/microsoft-teams-online-call-flows-figure12.png)

*Figura 12 - direta (ponto a ponto)*

### <a name="teams-online-hybrid-topology"></a>Topologia híbrida Online de equipes
Esta topologia é semelhante ao padrão de equipes Online ("puro"), mas "adiciona nos" Skype para negócios no local.

[![Figura 13 fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure13-thumbnail.png)](media/microsoft-teams-online-call-flows-figure13.png)

*Figura 13 - topologia híbrida Online de equipes*
 
>**Observações**:
>- A direção das setas no diagrama acima refletem a direção de iniciação da comunicação que afeta o perímetro corporativo de conectividade. No caso de UDP para a mídia, o primeiro pacote pode fluir na direção contrária, mas esses pacotes poderão ser bloqueados até que os pacotes na outra direção fluirá.
>- As equipes Online será implantada lado a lado com Skype para Business Online, daí os clientes são exibidos como "User equipes/SFB".

Fluxos de adicionais (na parte superior de topologia "puro" equipes Online):
- **Fluxo 5A** – representa um fluxo de mídia ponto a ponto entre o usuário de equipes dentro da rede de cliente com um Skype for Business no retransmissão de mídia local na borda da rede do cliente.

#### <a name="use-case-teams-to-skype-for-business-one-to-one"></a>Caso de uso: Equipes Skype para negócios-para-um
**Híbrido dentro da rede do cliente**

[![Figura 14 fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure14-thumbnail.png)](media/microsoft-teams-online-call-flows-figure14.png)

*Figura 14 - híbrida dentro da rede do cliente*
 
Sinalização entre equipes e Skype para negócios "com ponte" por um Gateway na nuvem do Office 365. No entanto, mídia é roteada diretamente "peer-to-peer" dentro da rede do cliente via fluxo 5.

**Rede de cliente híbrido com Skype externa para usuário de negócios – retransmitido pelo Office 365**

[![Fluxos de chamada Online do Microsoft equipes Figura 15](media/microsoft-teams-online-call-flows-figure15-thumbnail.png)](media/microsoft-teams-online-call-flows-figure15.png)

*Figura 15 - rede de cliente híbrido com Skype externa para usuário comercial - retransmitidos pelo Office 365*
 
>**Observação**: sinalização e mídia do Skype para o cliente de negócios para Skype for Business no servidor local está fora do escopo deste documento. No entanto, ele é mostrado aqui para manter a clareza.

Sinalização entre equipes e Skype para negócios "com ponte" por um Gateway na nuvem do Office 365.

Mídia é retransmitida por meio de retransmissão de transporte de equipes no Office 365 para a rede do cliente por meio de fluxos de 4.

**Rede de cliente híbrido com Skype externa para usuário de negócios – retransmitido na borda de local**

[![Figura 16 fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure16-thumbnail.png)](media/microsoft-teams-online-call-flows-figure16.png)

*Figura 16 - rede de cliente híbrido com Skype externa para usuário comercial - retransmitidos na borda de local*
 
>**Observação**: sinalização e mídia do Skype para o cliente de negócios para Skype para negócios no servidor local está fora do escopo deste documento. No entanto, ele é mostrado aqui para manter a clareza.

Sinalização "com ponte" por um Gateway na nuvem do Office 365.

Mídia é retransmitida por Skype para retransmissão de mídia de negócios dentro do Skype for Business no local de borda para o usuário de equipes dentro da rede do cliente via 5A de fluxo de mídia.

### <a name="teams-online-with-direct-routing-topology"></a>Equipes Online com topologia "Roteamento direto"
Esta topologia é semelhante ao equipes Online ("puro"), mas "adiciona nos" roteamento direto. 

Direcione o roteamento, anteriormente conhecido como BYOT (trazer suas próprias tronco), com um provedor de serviço de telefônica comutada pública de terceiros. Esse método é possível emparelhamento um compatível e local do cliente de propriedade Session Border Controller dispositivo de hardware para Office 365 na nuvem, e conectando o tronco de telefonia a esse dispositivo. 

Para oferecer suporte a esse cenário, o cliente deve implantar certificados SBC(s) para roteamento direto de um dos parceiros certificados da Microsoft. O SBC deve ser configurado adequadamente, conforme recomendado pelo fornecedor e ser roteável da nuvem do Office 365 para direcionar o tráfego UDP. A mídia pode fluir diretamente a partir de equipes/Skype para o cliente de negócios para o SBC (ignorar equipes Gateway (ou seja, MP)) ou desviar por meio do Gateway de equipes. A conectividade com o SBC, quando tronco é configurado para ignorar o Gateway de equipes, se baseia em ICE, onde SBC suporta Lite ICE, enquanto as equipes/Skype para ponto de extremidade de mídia de negócios oferece suporte a ICE completo. 

[![Figura 17 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure17-thumbnail.png)](media/microsoft-teams-online-call-flows-figure17.png)

*Figura 17 - on-line equipes com topologia 'Roteamento direto'*

>**Observações**:
>- A direção das setas no diagrama acima refletem a direção de iniciação da comunicação que afeta o perímetro corporativo de conectividade. No caso de UDP para a mídia, o primeiro pacote pode fluir na direção contrária, mas esses pacotes poderão ser bloqueados até que os pacotes na outra direção fluirá.
>- As equipes Online será implantada lado a lado com Skype para Business Online, daí os clientes são exibidos como "User equipes/SFB".

Fluxos de adicionais (na parte superior de topologia "puro" equipes Online):
- **Fluxo 4'** - representa um fluxo do Office 365 na nuvem para rede do cliente, usada para estabelecer uma conexão entre o servidor de mídia de equipes na nuvem com o SBC no local.
- **Fluxo 5B** – representa um fluxo de mídia entre o usuário de equipes dentro da rede de cliente com SBC direto de roteamento no modo "Ignorar".
- **Fluxo 5c** – representa um fluxo de mídia entre SBC direto de roteamento para outra SBC roteamento direto no modo de "Ignorar" do chamada PSTN "hairpin".

**Usuário direto roteamento interno (mídia retransmitidas por equipes retransmissão de transporte no Office 365)**

[![Figura 18 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure18-thumbnail.png)](media/microsoft-teams-online-call-flows-figure18.png)

*Figura 18 - usuário direto roteamento interno (mídia retransmitidas por equipes retransmissão de transporte no Office 365)*
 
>**Observação**: SBC deve ter um endereço IP público que seja roteável do Office 365.

Sinalização e mídia de SBC para Office 365 e vice-versa usam fluxo 4 e/ou fluxo 4'.

Sinalização e a mídia do cliente dentro da rede do cliente para o Office 365 na nuvem usam fluxo 4.


**Remoto usuário direto roteamento (mídia é roteada por meio de um servidor de mídia (MP) no Office 365)**

[![Figura 19 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure19-thumbnail.png)](media/microsoft-teams-online-call-flows-figure19.png)

*Figura 19 - remoto usuário direto roteamento (mídia é roteada por meio de um servidor de mídia (MP) no Office 365)*
 
>**Observação**: SBC deve ter um endereço IP público que seja roteável do Office 365.

Sinalização e mídia de SBC para Office 365 e vice-versa usam fluxo 4 e/ou fluxo 4'.

Sinalização e a mídia do cliente na Internet para o Office 365 na nuvem usam fluxo 3.

**Usuário interno direto roteamento (bypass de mídia)**

[![Figura 20 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure20-thumbnail.png)](media/microsoft-teams-online-call-flows-figure20.png)

*Figura 20 - usuário interno direto roteamento (bypass de mídia)*
 
>**Observação**: SBC deve ter um endereço IP público que seja roteável do Office 365.

Uso de sinalização de SBC para o Office 365 e vice-versa flow 4 e/ou fluxo 4'.

Sinalização de cliente dentro da rede do cliente para o fluxo de uso do Office 365 nuvem 4.

Mídia do cliente dentro da rede do cliente para SBC dentro da rede do cliente use 5B fluxo.

**Usuário remoto direto roteamento (bypass de mídia retransmitidos por equipes retransmissão de transporte no Office 365)**

[![Figura 21 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure21-thumbnail.png)](media/microsoft-teams-online-call-flows-figure21.png)

*Figura 21 - direto (bypass de mídia retransmitidos por equipes retransmissão de transporte no Office 365) de roteamento de usuário remoto*
 
>**Observação**: SBC deve ter um endereço IP público que seja roteável do Office 365 e a Internet.

Uso de sinalização de SBC para o Office 365 e vice-versa flow 4 e/ou fluxo 4'.

Sinalização do cliente na Internet ao fluxo de uso do Office 365 nuvem 3.

Mídia do cliente na Internet para SBC dentro da rede do cliente use fluxos 3 e 4, retransmitidos por equipes retransmissão de transporte no Office 365 na nuvem. 

**Usuário remoto roteamento direto (direto de bypass de mídia)**

[![Figura 22 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure22-thumbnail.png)](media/microsoft-teams-online-call-flows-figure22.png)

*Figura 22 - usuário remoto roteamento direto (direto de bypass de mídia)*
 
>**Observação**: SBC deve ter um endereço IP público que seja roteável do Office 365 e a Internet.

Uso de sinalização de SBC para o Office 365 e vice-versa flow 4 e/ou fluxo 4'.

Sinalização do cliente na Internet ao fluxo de uso do Office 365 nuvem 3.

Mídia do cliente na Internet para SBC dentro da rede do cliente usam fluxo 2.

**Direcionar circulação (bypass de mídia) – chamada "hairpin" da PSTN (devido à transferência/encaminhamento de chamada)**

[![Figura 23 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure23-thumbnail.png)](media/microsoft-teams-online-call-flows-figure23.png)

*Chamada de "hairpin" Figura 23 - roteamento direto (bypass de mídia) - PSTN (devido à transferência/encaminhamento de chamada)*
 
>**Observação**: SBC deve ter um endereço IP público que seja roteável do Office 365.

Uso de sinalização de SBC para o Office 365 e vice-versa flow 4 e/ou fluxo 4'.

Cliente está sem a sinalização e mídia loop após a chamada "hairpin" do PSTN para PSTN.

Mídia de instância SBC uma dentro da rede do cliente para a instância SBC B dentro da rede do cliente (onde, A e B podem ser a mesma instância) usar fluxo c de 5.

**Direcionar roteamento (mídia por meio do Office 365) – chamada "hairpin" PSTN entre dois locatários**

[![Figura 24 fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure24-thumbnail.png)](media/microsoft-teams-online-call-flows-figure24.png)

*Chamada de "hairpin" Figura 24 - roteamento direto (mídia por meio do Office 365) – PSTN entre dois locatários*
 
>**Observação**: SBC deve ter um endereço IP público que seja roteável do Office 365.

Uso de sinalização de SBC para o Office 365 e vice-versa flow 4 e/ou fluxo 4'.

Cliente está sem a sinalização e mídia loop após a chamada "hairpin" do PSTN para PSTN.

Modo de desvio de mídia da instância SBC uma dentro da rede de cliente X à instância SBC B deve ser retransmitida por meio do servidor de mídia do O365 e não é possível usar.

## <a name="teams-w-express-route-optimization"></a>Equipes c / otimização de rota Express

[![Figura 25 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure25-thumbnail.png)](media/microsoft-teams-online-call-flows-figure25.png)

*Figura 25 - equipes com otimização de rota Express*
 
No caso em que a rota Express é justificada e implantada, em seguida, fluxos de equipes poderiam ser encaminhados novamente do fluxo 4 para fluxo 1 e do fluxo 4' para o fluxo 1'. No entanto, o aplicativo de equipes tem dependência difícil em outros fluxos do OFFICE 365 pela internet via fluxos 4 e 4'; Portanto, não precisa ser bloqueados esses fluxos. 

Observe que o Skype para tráfego de negócios híbrida borda é roteado para a Internet e não à rota de Express para se comunicar com usuários externos e "federação" com outros tenants. 

Para impedir que fluxos assimétricas, reroteamento deve ser em ambas as direções. Em outras palavras, um endereço de rede do cliente seja roteável através da Internet ou rota Express, com base em otimização, mas não por meio de ambos.

Por exemplo:

**Rede de cliente para usuários externos (retransmitidas por equipes transporte retransmissão de mídia):**

[![Figura 26 de fluxos de chamada Online do Microsoft equipes](media/microsoft-teams-online-call-flows-figure26-thumbnail.png)](media/microsoft-teams-online-call-flows-figure26.png)

*Figura 26 - rede do cliente para usuários externos (retransmitidas por equipes transporte retransmissão de mídia)*
 
**Etapas de alto nível:**
1. Equipes de usuário dentro da rede do cliente resolve o nome de domínio (DNS) URL via Fluxo2
2. As equipes de usuário dentro da rede do cliente aloca uma mídia porta de retransmissão em equipes transporte Relay via fluxo 1
3. As equipes de usuário dentro da rede de cliente envia "convidar" com candidatos ICE via fluxo 1 para o Office 365
4. OFFICE 365 envia uma notificação para usuários externos de equipes via fluxo 3
5. As equipes de usuário externo aloca uma mídia porta de retransmissão em equipes transporte Relay via fluxo 3
6. As equipes de usuário externo envia "answer" com candidatos ICE via fluxo 3, que é encaminhada de volta ao usuário equipes via fluxo 1
7. As equipes de usuário B e equipes usuário invocar testes de conectividade do ICE e seleciona fluxos 1 e 3, que serão retransmitidas por equipes retransmissão de transporte no Office 365 na nuvem.
8. Usuários de equipes enviam telemetria para Office 365 via fluxos 1 e 3

>**Observação**: fluxo 4 deve ser habilitado para suportar dependências do aplicativo de equipes em outros serviços de micro mandatos de fluem de 4.
