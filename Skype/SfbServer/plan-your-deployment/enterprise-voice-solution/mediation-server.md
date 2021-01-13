---
title: Componente do Servidor de Mediação no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: Saiba mais sobre os Servidores de Mediação no Skype for Business Server, incluindo suas topologias com suporte e suas relações com troncos M:N, bypass de mídia e controle de admissão de chamadas.
ms.openlocfilehash: 14cf5fff38146622467698ffa58ccb244fac8fad
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813671"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Componente do Servidor de Mediação no Skype for Business Server
 
Saiba mais sobre os Servidores de Mediação no Skype for Business Server, incluindo suas topologias com suporte e suas relações com troncos M:N, bypass de mídia e controle de admissão de chamadas.
  
Para implantar o Enterprise Voice, você deve implantar um ou mais Servidores de Mediação. 
  
O Servidor de Mediação converte a sinalização entre sua infraestrutura interna do Enterprise Voice e um gateway PSTN (rede telefônica pública comutado) ou um tronco SIP. Em algumas implantações, ele também converte a própria mídia entre esses pontos.
  
No lado do Skype for Business Server, o Servidor de Mediação escuta um único endereço de transporte MTLS (TLS mútuo). No lado do gateway, o Servidor de Mediação escuta em todas as portas de escuta associadas aos troncos. Todos os gateways qualificados devem oferecer suporte a TLS, mas também podem habilitar TCP. TCP tem suporte em gateways que não oferecem suporte a TLS.
  
Se você também tiver um PBX (Public Branch Exchange) existente em seu ambiente, o Servidor de Mediação lidará com chamadas entre usuários do Enterprise Voice e o PBX. Se o PBX for um IP-PBX, você poderá criar uma conexão SIP direta entre o PBX e o Servidor de Mediação. Se o PBX for um TDM (Multiplex de Divisão de Tempo) PBX, você também deverá implantar um gateway PSTN entre o Servidor de Mediação e o PBX.
  
O Servidor de Mediação é alocado com o Servidor front-end por padrão. O Servidor de Mediação também pode ser implantado em um pool autônomo.
  
## <a name="what-mediation-server-does"></a>O que o Servidor de Mediação faz

As principais funções do Servidor de Mediação são as seguinte:
  
- Criptografar e descriptografar SRTP no lado do Skype for Business Server. 
    
- Traduzindo SIP sobre TCP (para gateways que não suportam TLS) para SIP sobre TLS mútuo.
    
- Translating media streams between Skype for Business Server and the gateway peer of the Mediation Server.
    
- Conexão de clientes que estão fora da rede a componentes internos de ICE, que permitem o deslizamento de mídia de NAT e firewalls.
    
- Agindo como intermediário para fluxos de chamada que um gateway não suporta, como chamadas de funcionários remotos em um enterprise Voice clien.t
    
- Em implantações que incluem tronco SIP, trabalhando com o provedor de serviços de tronco SIP para fornecer suporte a PSTN, o que elimina a necessidade de um gateway PSTN.
    
A figura a seguir mostra os protocolos de sinalização e mídia usados pelo Servidor de Mediação ao se comunicar com um gateway PSTN básico e a infraestrutura do Enterprise Voice.
  
**Protocolos de sinalização e a mídia usados pelo Servidor de Mediação**

![Diagrama de Protocolos do Servidor de Mediação](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Se você estiver usando TCP ou RTP/RTCP (em vez de SRTP ou SRTCP) na rede entre o gateway PSTN e o Servidor de Mediação, recomendamos que você tome medidas para ajudar a garantir a segurança e a privacidade da rede. 
  
## <a name="mn-trunk"></a>Tronco M:N

O Skype for Business Server oferece suporte à flexibilidade na definição de um tronco para fins de roteamento de chamadas. Um tronco é uma associação lógica entre um Servidor de Mediação e um número de porta de escuta, com um gateway e um número de porta de escuta. Isso implica em várias coisas: um Servidor de Mediação pode ter vários troncos para o mesmo gateway; um Servidor de Mediação pode ter vários troncos para gateways diferentes; por outro lado, um gateway pode ter vários troncos para diferentes Servidores de Mediação.
  
Você ainda deve criar um tronco raiz ao adicionar um gateway à sua topologia do Skype for Business usando o Construtor de Topologias. O número de gateways que um determinado Servidor de Mediação pode manipular depende da capacidade de processamento do servidor durante horários de pico de pico. Se você implantar um Servidor de Mediação no hardware que atenda aos requisitos mínimos de hardware para o Skype for Business Server, conforme descrito nos requisitos de servidor do [Skype for Business Server 2015,](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md)um Servidor de Mediação autônomo poderá lidar com aproximadamente 1.000 chamadas. O Servidor de Mediação executa a transcodificação, mas ainda encaminha chamadas para vários gateways, mesmo que os gateways não deem suporte ao bypass de mídia.
  
Ao definir uma rota de chamada, especifique os troncos associados a essa rota, mas não especifique quais Servidores de Mediação estão associados a essa rota. Em vez disso, você usa o Construtor de Topologias para associar troncos aos Servidores de Mediação. Em outras palavras, o roteamento determina qual tronco usar para uma chamada e, subsequentemente, o Servidor de Mediação associado a esse tronco recebe a sinalização dessa chamada.
  
O Servidor de Mediação pode ser implantado como um pool; esse pool pode ser alocado com um pool de Front-End ou pode ser implantado como um pool autônomo. Quando um Servidor de Mediação é alocado com um pool de Front-End, o tamanho do pool pode ser no máximo 12 (o limite do tamanho do pool do Registrador). Juntos, esses recursos aumentam a confiabilidade e a flexibilidade de implantação dos Servidores de Mediação, mas exigem recursos semelhantes nos seguintes:
  
- **Gateway PSTN.** Um gateway qualificado do Skype for Business Server deve implementar o balanceamento de carga DNS, que permite que um gateway PSTN (rede telefônica pública comutado) qualificado atue como um balanceador de carga para um pool de Servidores de Mediação e, assim, balancee a carga de chamadas no pool.
    
- **Controlador de borda da sessão.** Para um tronco SIP, a entidade de mesmo par é um Controlador de Borda de Sessão (SBC) em um provedor de serviços de telefonia da Internet. Na direção do pool do Servidor de Mediação para o SBC, o SBC pode receber conexões de qualquer Servidor de Mediação no pool. Na direção do SBC para o pool, o tráfego pode ser enviado para qualquer Servidor de Mediação no pool. Um método para conseguir isso é por meio do balanceamento de carga DNS, se suportado pelo provedor de serviços e pelo SBC. Uma alternativa é dar ao provedor de serviços os endereços IP de todos os Servidores de Mediação no pool, e o provedor de serviços provisioná-los em seu SBC como um tronco SIP separado para cada Servidor de Mediação. Em seguida, o provedor de serviços manipulará o balanceamento de carga para seus próprios servidores. Nem todos os provedores de serviços ou SBCs podem dar suporte a esses recursos. Além disso, o provedor de serviços pode cobrar mais por essa funcionalidade. Normalmente, cada tronco SIP para o SBC incorre em uma taxa mensal.
    
- **IP-PBX.** Na direção do pool do Servidor de Mediação para a terminação SIP IP-PBX, o IP-PBX pode receber conexões de qualquer Servidor de Mediação no pool. Na direção do IP-PBX para o pool, o tráfego pode ser enviado para qualquer Servidor de Mediação no pool. Como a IP-PBXs não suporta o balanceamento de carga DNS, recomendamos que as conexões SIP diretas individuais sejam definidas do IP-PBX para cada Servidor de Mediação no pool. Em seguida, o IP-PBX lidará com seu próprio balanceamento de carga distribuindo o tráfego sobre o grupo de troncos. A suposição é de que o grupo de troncos tem um conjunto consistente de regras de roteamento no IP-PBX. Se um DETERMINADO IP-PBX oferece suporte a esse conceito de grupo de troncos e como ele se cruza com a própria redundância do IP-PBX e a arquitetura de clustering precisa ser determinada antes que você possa decidir se um cluster do Servidor de Mediação pode interagir corretamente com um IP-PBX.
    
Um pool do Servidor de Mediação deve ter uma exibição uniforme do gateway de par com o qual ele interage. Isso significa que todos os membros do pool acessam a mesma definição do gateway par do armazenamento de configuração e têm a mesma probabilidade de interagir com ele para chamadas de saída. Portanto, não há como segmentar o pool para que alguns Servidores de Mediação se comuniquem apenas com determinados pares de gateway para chamadas de saída. Se essa segmentação for necessária, um pool separado de Servidores de Mediação deverá ser usado. Isso seria o caso, por exemplo, se os recursos associados em gateways PSTN, troncos SIP ou IP-PBXs interagir com um pool conforme detalhado anteriormente neste tópico não estão presentes.
  
Um gateway PSTN específico, IP-PBX ou ponto de tronco SIP pode ser roteada para vários Servidores de Mediação ou troncos. O número de gateways que um pool específico de Servidores de Mediação pode controlar depende do número de chamadas que usam bypass de mídia. Se um grande número de chamadas usar bypass de mídia, um Servidor de Mediação no pool poderá lidar com muitas outras chamadas, pois somente o processamento da camada de sinalização é necessário. 
  
## <a name="call-admission-control-and-mediation-server"></a>Controle de admissão de chamadas e Servidor de Mediação

Controle de admissão de chamada (CAC), gerencia o estabelecimento de sessão em tempo real, com base na largura de banda disponível, para ajudar a evitar qoE (qualidade da experiência) ruim para usuários em redes congestionadas. Para dar suporte a isso, o Servidor de Mediação é responsável pelo gerenciamento de largura de banda por suas duas interações no lado do Skype for Business Server e no lado do gateway. No controle de admissão de chamadas, a entidade de terminação de uma chamada lida com a reserva da largura de banda. Os pares de gateway (gateway PSTN, IP-PBX, SBC) com os que o Servidor de Mediação interage no lado do gateway não suportam o controle de admissão de chamadas do Skype for Business Server. Assim, o Servidor de Mediação precisa lidar com as interações de largura de banda em nome de seu par de gateway. Sempre que possível, o Servidor de Mediação reserva largura de banda com antecedência. Se isso não for possível (por exemplo, a localidade do ponto de extremidade da mídia final no lado do gateway for desconhecido para uma chamada feita para o par de gateway), a largura de banda será reservada quando a chamada for feita. Esse comportamento pode resultar em uma inscrição em excesso da largura de banda, mas é a única maneira de impedir anéis falsos.
  
O bypass de mídia e o modo de reserva da largura de banda são mutuamente exclusivos. Se o bypass de mídia for empregado para uma chamada, o controle de admissão de chamada não será executado para essa chamada. O pressuposto é que não há links com largura de banda restrita envolvidos na chamada. Se o controle de admissão de chamada for usado para uma chamada específica que envolva o Servidor de Mediação, essa chamada não poderá empregar bypass de mídia.
  
Para obter detalhes sobre bypass de mídia ou controle de [admissão](call-admission-control.md)de chamadas, consulte [Plan for media bypass in Skype for Business](media-bypass.md) or Plan for call admission control in Skype for Business Server .
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>Enhanced 9-1-1 (E9-1-1) e Servidor de Mediação

O Servidor de Mediação ampliou suas capacidades para poder interagir corretamente com os provedores de serviço do E9-1-1. Nenhuma configuração especial é necessária no Servidor de Mediação. As extensões SIP necessárias para a interação do E9-1-1 são, por padrão, incluídas no protocolo SIP do Servidor de Mediação para suas interações com um par de gateway (gateway PSTN, IP-PBX ou o SBC de um Provedor de Serviços de Telefonia da Internet, incluindo provedores de serviços E9-1-1)
  
Se o tronco SIP para um provedor de serviço de E9-1-1 pode ser encerrado em um pool do Servidor de Mediação existente ou precisar de Servidores de Mediação autônomos dependerá se o E9-1-1 SBC pode interagir com um pool de Servidores de Mediação. Para obter detalhes, [consulte tronco M:N no Skype for Business Server.](m-n-trunk.md)
  
## <a name="media-bypass-and-mediation-server"></a>Bypass de mídia e Servidor de Mediação

O bypass de mídia é um recurso do Skype for Business Server que permite que um administrador configure o roteamento de chamadas para fluir diretamente entre o ponto de extremidade do usuário e o gateway PSTN sem atravessar o Servidor de Mediação. O bypass de mídia melhora a qualidade da chamada reduzindo a latência, conversão desnecessária, possibilidade de perda de pacotes e o número de possíveis pontos de falha. Quando um site remoto sem um Servidor de Mediação é conectado a um site central por um ou mais links WAN com largura de banda restrita, o bypass de mídia reduz o requisito de largura de banda, permitindo que a mídia de um cliente em um site remoto flua diretamente para seu gateway local sem antes ter que fluir pelo link WAN para um Servidor de Mediação no site central e voltar. Essa redução no processamento de mídia também complementa a capacidade do Servidor de Mediação de controlar vários gateways.
  
O bypass de mídia e o CAC (controle de admissão de chamada) são mutuamente exclusivos. Se o bypass de mídia for empregado para uma chamada, o CAC não será executado para essa chamada. A suposição é de que não há links com largura de banda restrita envolvidos na chamada.
  
## <a name="topologies-for-mediation-server"></a>Topologias para o Servidor de Mediação

O Skype for Business Server, Servidor de Mediação, é por padrão alocado com o servidor Standard Edition, um pool de Front-End ou Aparelho de FilialVivível. Todos os Servidores de Mediação em um pool de Front-End devem ser configurados de forma idêntica.
  
Quando o desempenho é um problema, pode ser preferível implantar um ou mais Servidores de Mediação em um pool autônomo dedicado. Definitivamente, recomendamos um pool autônomo se você estiver implantando o tronco SIP. 
  
Se você implantar conexões SIP diretas com um gateway PSTN qualificado que oferece suporte a bypass de mídia e balanceamento de carga DNS, um pool do Servidor de Mediação autônomo não será necessário. Isso porque os gateways qualificados são capazes de balanceamento de carga DNS para um pool de Servidores de Mediação e podem receber tráfego de qualquer Servidor de Mediação em um pool.
  
Também recomendamos que você collocate o Servidor de Mediação em um pool de Front-End quando tiver implantado o IP-PBXs ou se conectar ao Controlador de Borda de Sessão (SBC) de um Provedor de Servidor de Telefonia da Internet, desde que qualquer uma das seguintes condições seja atendida:
  
- O IP-PBX ou SBC está configurado para receber tráfego de qualquer Servidor de Mediação no pool e pode rotear tráfego uniformemente para todos os Servidores de Mediação no pool.
    
- O IP-PBX não suporta bypass de mídia, mas o pool de Front End que está hospedando o Servidor de Mediação pode manipular a transcodificação de voz para chamadas às quais o bypass de mídia não se aplica.
    
Você pode usar a Ferramenta de Planejamento do Microsoft Lync Server 2013 para avaliar se o pool de Front-End onde você deseja colocar o Servidor de Mediação pode lidar com a carga. Se o seu ambiente não pode cumprir estes requisitos, você deve implantar um pool do Servidor de Mediação autônomo.
  
A figura a seguir mostra uma topologia simples que consiste em dois sites conectados por um link WAN. O Servidor de Mediação é alocado em um pool de Front-End no Site 1. Os Servidores de Mediação no Local 1 controlam o gateway PSTN no Local 1 e o gateway no Local 2. Nessa topologia, o bypass de mídia é habilitado globalmente para usar informações de site e região, e os troncos para cada gateway PSTN (GW1 e GW2) têm o bypass habilitado.
  
**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um gateway PSTN no Site 2**

![Topologia de voz com Gateway WAN do Servidor de Mediação](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
A próxima figura mostra uma topologia simples em que o Servidor de Mediação é alocado no pool de Front-End no Site 1 e possui uma conexão SIP Direta com o IP-PBX no Site 1. Nesta figura, o Servidor de Mediação também controla um gateway PSTN no Local 2. Suponha que os usuários do Skype for Business existam nos Sites 1 e 2. Suponha também que o IP-PBX tenha um processador de mídia associado que deve ser percorrido por todas as mídias provenientes dos pontos de extremidade do Skype for Business antes de serem enviados aos pontos de extremidade de mídia controlados pelo IP-PBX. Nessa topologia, o bypass de mídia é habilitado globalmente para usar informações de site e região, e os troncos para o PBX e o gateway PSTN têm o bypass de mídia habilitado.
  
**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um PBX no Site 2**

![PBX WAN do Servidor de Mediação de Topologia de Voz](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
A última figura deste tópico mostra uma topologia onde o Servidor de Mediação está conectado ao SBC de um Provedor de Serviços de Telefonia da Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Planejando decisões para o Servidor de Mediação

Este tópico descreve as decisões de planejamento que você precisa tomar para sua implantação do Servidor de Mediação,
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de Mediação Autônomo ou Autônomo?

O Servidor de mediação é colocado por padrão no servidor Standard Edition ou no servidor Front-End em um pool de Front-End em locais centrais. O número de chamadas PSTN que podem ser tratadas e o número de máquinas necessárias no pool dependerá do seguinte:
  
- O número de pares de gateway que o pool do Servidor de Mediação controla
    
- Os períodos de tráfego de alto volume por meio desses gateways
    
- A porcentagem de chamadas cuja mídia ignora o Servidor de Mediação
    
Ao planejar, certifique-se de levar em conta os requisitos de processamento de mídia para chamadas PSTN e conferências A/V que não estão configuradas para bypass de mídia, bem como o processamento necessário para lidar com as interações de sinalização para o número de chamadas em horário de pico que precisam de suporte. Se não houver CPU suficiente, você deverá implantar um pool autônomo de Servidores de Mediação; e gateways PSTN, IP-PBXs e SBCs precisarão ser divididos em subconjuntos controlados pelos Servidores de Mediação em um pool e os Servidores de Mediação autônomos em um ou mais pools autônomos.
  
Se você implantou gateways PSTN, IP-PBXs ou Controladores de Borda de Sessão (SBCs) que não suportam os recursos corretos para interagir com um pool de Servidores de Mediação, incluindo o seguinte, eles precisarão ser associados a um pool autônomo que consiste em um único Servidor de Mediação:
  
- Execute o balanceamento de carga DNS (Sistema de Nomes de Domínio) da camada de rede nos Servidores de Mediação em um pool (ou roteia o tráfego uniformemente para todos os Servidores de Mediação em um pool)
    
- Aceitar tráfego de qualquer servidor de mediação em um pool
    
Você pode usar a Ferramenta de Planejamento do Microsoft Lync Server 2013 para avaliar se a colocar o Servidor de Mediação com seu pool de Front-End pode lidar com a carga. Se o seu ambiente não pode cumprir estes requisitos, você deve implantar um pool do Servidor de Mediação autônomo.
  
### <a name="central-site-and-branch-site-considerations"></a>Considerações sobre o site central e site de filial

 Os servidores de mediação no site central podem ser usados para rotear chamadas para gateways IP PBXs ou PSTN em sites de flial. Se você implantar os troncos SIP, no entanto, é necessário implantar um servidor de mediação no site onde termina cada tronco. Com um servidor de mediação no site central para rotear chamadas a um gateway PBX IP ou PSTN de uma filial não requer o uso de bypass de mídia. No entanto, se você puder habilitar o bypass de mídia, isso reduzirá a latência do caminho de mídia e melhorará a qualidade da mídia porque o caminho de mídia não é mais necessário para seguir o caminho de sinalização. O bypass de mídia também diminui a carga de processamento no pool.
  
> [!NOTE]
> O desvio de mídia não irá interoperar com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com parceiros certificados e realizou alguns testes com o IP-PBXs da Cisco. O bypass de mídia só tem suporte com produtos e versões listados no Programa de Interoperabilidade Aberta de Comunicações [Unificadas - Lync Server.](https://go.microsoft.com/fwlink/p/?LinkId=268730) 
  
Se a flexibilidade do site de filial for necessária, um Aparelho de Filial Persistente ou uma combinação de um servidor Front-End, um servidor de mediação e um gateway devem ser implantados na filial. (A suposição com a resiliência do site de filial é que a presença e a conferência não são resilientes no site.) Para obter orientação sobre o planejamento de voz no site de filial, consulte Plano de [resiliência](enterprise-voice-resiliency.md)do Enterprise Voice no Skype for Business Server.
  
Para interações com um IP-PBX, se o IP-PBX não suportar corretamente interações de mídia inicial com várias caixas de diálogo e interações RFC 3960, poderá haver corte das primeiras palavras da saudação para chamadas de entrada do IP-PBX para os pontos de extremidade do Skype for Business. Esse problema poderá ser mais grave se um Servidor de Mediação em um site central estiver encaminhando chamadas para um IP-PBX onde a rota termina em um site de filial, pois é necessário mais tempo para a sinalização ser concluída. Se você experimentar esse comportamento, implantar um Servidor de Mediação no site de filial é a única maneira de reduzir o recorte das primeiras palavras.
  
Finalmente, se o site central tiver um PBX TDM ou se o IP-PBX não elimina a necessidade de um gateway PSTN, você deve implantar um gateway na rota de chamada que conecta o servidor de mediação e o PBX.
  
> [!NOTE]
> Para melhorar o desempenho de mídia do Servidor de Mediação autônomo, você deve habilitar o RSS (receive-side scaling) nos adaptadores de rede nesses servidores. O RSS permite que pacotes recebidos sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, [consulte "Receive-Side Scaling Enhancements in Windows Server"](https://go.microsoft.com/fwlink/p/?LinkId=268731). Para obter detalhes sobre como habilitar o RSS, consulte a documentação do adaptador de rede. 
  

