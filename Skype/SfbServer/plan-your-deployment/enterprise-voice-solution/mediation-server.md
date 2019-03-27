---
title: Componente do servidor de mediação no Skype para Business Server
ms.reviewer: ''
ms.author: crowe
author: CarolynRowe
manager: serdars
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection:
- IT_Skype16
- Strat_SB_Admin
ms.custom: ''
ms.assetid: 5b19edef-4a54-43c9-aa12-5643b8108355
description: Saiba mais sobre servidores de mediação no Skype para Business Server, incluindo suas topologias suportadas e suas relações M:N troncos, bypass de mídia e controle de admissão de chamada.
ms.openlocfilehash: 237892f446250332e00616dcc8a08abf9c59d741
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30889165"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Componente do servidor de mediação no Skype para Business Server
 
Saiba mais sobre servidores de mediação no Skype para Business Server, incluindo suas topologias suportadas e suas relações M:N troncos, bypass de mídia e controle de admissão de chamada.
  
Para implantar o Enterprise Voice, você deve implantar um ou mais servidores de mediação. 
  
O servidor de mediação converte a sinalização entre sua infraestrutura interna do Enterprise Voice e um gateway PSTN (rede) telefônica comutada pública ou um tronco de protocolo de iniciação de sessão (SIP). Em algumas implantações, ele também converte a própria mídia entre esses pontos.
  
No Skype para lado Business Server, servidor de mediação escuta um único endereço de transporte TLS (MTLS) mútuo. No lado do gateway, o servidor de mediação escuta em todas as portas de escuta associadas associadas troncos. Todos os gateways qualificados devem dar suporte a TLS, mas também podem habilitar o TCP. O TCP é aceito para gateways que não dão suporte a TLS.
  
Se você também tiver um público Branch Exchange (PBX existente) em seu ambiente, o servidor de mediação processa as chamadas entre usuários do Enterprise Voice e o PBX. Se seu PBX for um IP-PBX, você pode criar uma conexão SIP direta entre o PBX e o servidor de mediação. Se seu PBX for uma divisão Multiplex TDM (Time) PBX, você também deve implantar um gateway PSTN entre o servidor de mediação e o PBX.
  
Por padrão, o servidor de mediação está colocado com o servidor Front-End. O servidor de mediação também podem ser implantado em um pool autônomo.
  
## <a name="what-mediation-server-does"></a>Qual é a função do Servidor de Mediação

As principais funções do servidor de mediação são:
  
- Criptografando e descriptografando SRTP no Skype do lado do servidor de negócios. 
    
- Conversão do SIP sobre TCP (para gateways que não oferecem suporte a TLS) em SIP sobre MTLS (TLS mútuo).
    
- Conversão de fluxos de mídia entre Skype para Business Server e o par de gateway do servidor de mediação.
    
- Conexão de clientes fora da rede com componentes internos de ICE, que permitem a passagem de mídia do NAT e de firewalls.
    
- Atuação como intermediário para fluxos de chamada que um gateway não oferece suporte, como chamadas de funcionários remotos em um clien.t do Enterprise Voice
    
- Em implantações que incluem tronco SIP, trabalho conjunto com o provedor de serviços de tronco SIP para oferecer suporte à PSTN, eliminando a necessidade de um gateway PSTN.
    
A figura a seguir mostra os protocolos de sinalização e de mídia usados pelo servidor de mediação durante a comunicação com um gateway PSTN básico e a infraestrutura do Enterprise Voice.
  
**Protocolos de sinalização e a mídia usados pelo Servidor de Mediação**

![Diagrama dos protocolos do servidor de mediação](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Se você estiver usando TCP ou RTP/RTCP (em vez de SRTP ou SRTCP) da rede entre o gateway PSTN e o servidor de mediação, recomendamos que você tomar medidas para ajudar a garantir a segurança e privacidade da rede. 
  
## <a name="mn-trunk"></a>Tronco M:N

Skype para Business Server oferece suporte a flexibilidade na definição de um tronco para fins de roteamento de chamada. Um tronco é uma associação lógica entre um servidor de mediação e o número da porta de escuta, com um gateway e um número de porta de escuta. Isso implica várias coisas: um servidor de mediação pode ter vários troncos para o mesmo gateway; um servidor de mediação pode ter vários troncos para gateways diferentes; Por outro lado, um gateway pode ter vários troncos para diferentes servidores de mediação.
  
Quando você adiciona um gateway para seu Skype para topologia de negócios usando o construtor de topologia, você ainda deve criar um tronco de raiz. O número de gateways que um determinado servidor de mediação pode lidar depende a capacidade de processamento do servidor durante o horário de pico ocupado. Se você implantar um servidor de mediação no hardware que atende os requisitos mínimos de hardware para Skype para Business Server, conforme descrito em [requisitos de servidor para Skype para Business Server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), em seguida, um servidor de mediação autônomo pode manipular aproximadamente chamadas de 1000. O servidor de mediação é executa a transcodificação, mas ainda rotear as chamadas para vários gateways, mesmo se os gateways não suportam bypass de mídia.
  
Ao definir uma rota de chamada, você especificar os troncos associados a essa rota, mas você não especificar quais servidores de mediação estão associados essa rota. Em vez disso, use o construtor de topologias para associar troncos com servidores de mediação. Em outras palavras, roteamento determina qual tronco a ser usado para uma chamada e, subsequentemente, o servidor de mediação associado a esse tronco é enviado a sinalização para essa chamada.
  
O servidor de mediação pode ser implantado como um pool; Este pool pode ser colocado com um pool de Front-End ou ele pode ser implantado como um pool autônomo. Quando um servidor de mediação é colocado com um pool de Front-End, o tamanho do pool pode ter no máximo 12 (o limite do tamanho do pool de registrador). Juntos, esses recursos aumentam a confiabilidade e a flexibilidade de implantação de servidores de mediação, mas eles exigem recursos semelhantes a seguir:
  
- **Gateway PSTN.** Um Skype para gateway qualificado do Business Server deve implementar balanceamento de carga DNS, que permite que um gateway PSTN (rede) qualificado telefônica comutada pública agir como um balanceador de carga para um pool de servidores de mediação e, portanto, para chamadas de balanceamento de carga todo o pool .
    
- **Controlador de Borda da Sessão.** Para um tronco SIP, a entidade par é um SBC (Controlador de Borda da Sessão) no provedor de serviços de telefonia da Internet. Na direção do pool de servidores de mediação para o SBC, o SBC pode receber conexões de qualquer servidor de mediação no pool. Na direção do SBC para o pool, o tráfego pode ser enviado para qualquer servidor de mediação no pool. Um método que permite isso é através do balanceamento de carga DNS, se ele tiver suporte do provedor de serviços e do SBC. Uma alternativa é dar os endereços IP de todos os servidores de mediação no pool de provedor de serviços e o provedor de serviço provisionará esses no seu SBC como um tronco SIP separado para cada servidor de mediação. O provedor de serviços tratará o balanceamento de carga de seus próprios servidores. Nem todos os provedores de serviços ou SBCs podem dar suporte a essas funcionalidades. Além disso, o provedor de serviços pode cobrar mais por essa funcionalidade. Geralmente, cada tronco SIP até o SBC é tarifado mensalmente.
    
- **IP-PBX.** Na direção do pool de servidores de mediação para a terminação SIP IP-PBX, IP-PBX pode receber conexões de qualquer servidor de mediação no pool. Na direção do IP-PBX para o pool, o tráfego pode ser enviado para qualquer servidor de mediação no pool. Porque a maioria dos IP-PBXs não suportam o balanceamento de carga do DNS, recomendamos que individuais conexões SIP diretas ser definidos de IP-PBX para cada servidor de mediação no pool. Depois disso, o IP-PBX tratará seu próprio balanceamento de carga distribuindo o tráfego pelo grupo de troncos. Presume-se que o grupo de troncos tenha um conjunto de regras de roteamento consistente no IP-PBX. Se um determinado IP-PBX oferece suporte a esse conceito de grupo do tronco e como ele faz interseção com a redundância do IP-PBX próprio e arquitetura de cluster precisa ser determinada antes de você pode decidir se um cluster de servidor de mediação pode interagir corretamente com um IP-PBX.
    
Um pool de servidores de mediação deve ter um modo de exibição uniforme do gateway ponto com a qual ele interage. Isso significa que todos os membros do pool acessam a mesma definição do gateway par a partir do repositório de configurações e têm a mesma probabilidade de interagir com ele para as chamadas de saída. Portanto, não há um meio para segmentar o pool para que alguns servidores de mediação se comunicar com apenas determinados pares de gateway para chamadas de saída. Se tais segmentação for necessária, um pool separado dos servidores de mediação deve ser usado. Isso seria o caso, por exemplo, se as funcionalidades associadas nos gateways PSTN, nos troncos SIP ou nos IP-PBXs para interagir com um pool, conforme detalhado anteriormente neste tópico, não estivessem presentes.
  
Um gateway específico do PSTN, IP-PBX ou ponto de tronco SIP pode rotear para vários servidores de mediação ou troncos. O número de gateways que um determinado pool de servidores de mediação pode controlar depende do número de chamadas que usam bypass de mídia. Se um grande número de chamadas usa bypass de mídia, um servidor de mediação no pool pode manipular várias chamadas mais, porque o processamento de camada de sinalização somente é necessário. 
  
## <a name="call-admission-control-and-mediation-server"></a>Controle de admissão de chamadas e Servidor de Mediação

O CAC (controle de admissão de chamadas) gerencia o estabelecimento de sessão em tempo real com base na largura de banda disponível para ajudar a evitar uma QoE (Qualidade da Experiência) ruim para os usuários em redes congestionadas. Para suportar isso, o servidor de mediação é responsável pelo gerenciamento de largura de banda para suas dois interações no Skype para lado Business Server e no lado do gateway. No controle de admissão de chamadas, a entidade de terminação de uma chamada lida com a reserva de largura de banda. Os pares de gateway (gateway PSTN, IP-PBX, SBC) que o servidor de mediação interage com no lado do gateway não suportam o Skype para controle de admissão de chamada do servidor de negócios. Assim, o servidor de mediação tem que lidar com as interações de largura de banda em nome de seu ponto de gateway. Sempre que possível, o servidor de mediação será reservar a largura de banda com antecedência. Se isso não for possível (por exemplo, se a localidade do ponto de extremidade de mídia final no lado do gateway for desconhecido de uma chamada de saída para o par de gateway), a largura de banda será reservada quando a chamada for feita. Esse comportamento poderá resultar em uma inscrição em excesso de assinatura da largura de banda, mas é a única maneira de impedir anéis falsos.
  
O bypass de mídia e a reserva de largura de banda são mutuamente exclusivos. Se um bypass de mídia for empregado para uma chamada, o controle de admissão de chamadas não será executado para essa chamada. Presume-se que não haja links envolvidos na chamada com a largura de banda restrita. Se o controle de admissão de chamada é usado para uma chamada específica que envolve o servidor de mediação, a chamada não pode empregar bypass de mídia.
  
Para obter detalhes sobre a mídia bypass ou controle de admissão de chamada, consulte [Planejar media bypass no Skype para negócios](media-bypass.md) ou a [Planejar o controle de admissão de chamada no Skype para Business Server](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>E9-1-1 (9-1-1 Avançado) e Servidor de Mediação

O servidor de mediação tem recursos estendidos para que ele corretamente possa interagir com provedores de serviços do Enhanced 9-1-1 (E9-1-1). Nenhuma configuração especial é necessária no servidor de mediação. As extensões de SIP necessárias para interação de E9-1-1 são, por padrão, incluído no protocolo SIP do servidor de mediação para suas interações com um par de gateway (gateway PSTN, IP-PBX ou o SBC de um provedor de serviços de telefonia da Internet, incluindo o serviço de E9-1-1 Provedores)
  
Se o tronco SIP para um provedor de serviço E9-1-1 pode ser encerrado em um pool existente do servidor de mediação ou exigirá que os servidores de mediação autônomos dependerá se o SBC E9-1-1 pode interagir com um pool de servidores de mediação. Para obter detalhes, consulte [tronco M:N no Skype para Business Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Bypass de mídia e Servidor de Mediação

Bypass de mídia é um Skype para o recurso de Business Server, que permite que um administrador configurar o roteamento de chamadas para o fluxo diretamente entre o ponto de extremidade do usuário e o gateway PSTN (rede) telefônica comutada pública sem passar pelo servidor de mediação. Bypass de mídia melhora a qualidade da chamada, reduzindo a latência, tradução desnecessária, possibilidade de perda de pacotes e o número de pontos de falha potenciais. Onde um site remoto sem um servidor de mediação está conectado a um site central por um ou mais links de WAN com largura de banda restrita, o bypass de mídia abaixa o requisito de largura de banda, permitindo que a mídia a partir de um cliente em um site remoto flua diretamente para o seu gateway local sem primeiro precisar fluxo pela WAN vincular a um servidor de mediação no site central e novamente. Essa redução no processamento de mídia também complementa a capacidade do servidor de mediação para controlar vários gateways.
  
O bypass de mídia e o CAC (controle de admissão de chamadas) são mutuamente exclusivos. Se o bypass de mídia for empregado para uma chamada, o CAC não será executado para essa chamada. Presume-se que não haja links com largura de banda restrita envolvidos na chamada.
  
## <a name="topologies-for-mediation-server"></a>Topologias do Servidor de Mediação

O Skype para Business Server, servidor de mediação é por padrão colocado com um aparelho de filial, um pool de Front-End ou servidor Standard Edition. Todos os servidores de mediação em um pool de Front-End deve ser configurados de forma idêntica.
  
Onde o desempenho é um problema, talvez seja preferível implantar um ou mais servidores de mediação em um pool autônomo dedicado. Se você estiver implantando um tronco SIP, recomendamos certamente um pool autônomo. 
  
Se você implantar conexões SIP diretas com um gateway PSTN qualificado que suporta bypass de mídia e DNS com carga balanceamento, um servidor de mediação autônomo pool não é necessário. Isso acontece porque gateways qualificados são capazes de DNS com carga balanceada para um pool de servidores de mediação e eles podem receber tráfego de qualquer servidor de mediação em um pool.
  
Também recomendamos que você colocar o servidor de mediação em um pool de Front-End quando você tiver implantado o IP-PBXs ou se conectar a de um Internet Server provedor de telefonia borda controlador sessão (SBC), desde que qualquer uma das seguintes condições forem atendida:
  
- O IP-PBX ou SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear tráfego uniformemente para todos os servidores de mediação no pool.
    
- O IP-PBX não suporta bypass de mídia, mas o pool de Front-End que está hospedando o servidor de mediação pode manipular a transcodificação de voz para chamadas aos quais o bypass de mídia não é aplicável.
    
Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se o pool de Front-End, onde você deseja colocar o servidor de mediação pode manipular a carga. Se seu ambiente não pode atender a esses requisitos, você deve implantar um pool do servidor de mediação autônomo.
  
A figura a seguir mostra uma topologia simples que consiste em dois locais conectados por um link WAN. Servidor de mediação é colocado em um pool de Front-End no Site 1. Os servidores de mediação no Site 1 controla o gateway PSTN no Site 1 e o gateway no Site 2. Nessa topologia, o bypass de mídia está habilitado globalmente para usar as informações do local e da região, e os troncos até cada gateway PSTN (GW1 e GW2) têm bypass habilitado.
  
**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um gateway PSTN no Site 2**

![Topologia de voz com Gateway WAN do servidor de mediação](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
A próxima figura mostra uma topologia simple onde o servidor de mediação é colocado no pool de Front-End no Site 1 e tem uma conexão SIP direto para o IP-PBX no Site 1. Nessa figura, o servidor de mediação também controla um gateway PSTN no Site 2. Suponha que Skype para usuários comerciais existir em Sites 1 e 2. Também pressupõem que o IP-PBX possui um processador de mídia associado que deve ser desviado pela todas as mídias provenientes de Skype para pontos de extremidade de negócios antes de serem enviados aos pontos de extremidade de mídia controlados pelo IP-PBX. Nessa topologia, o bypass de mídia está habilitado globalmente para usar as informações do local e da região, e os troncos até o PBX e o gateway PSTN têm o bypass de mídia habilitado.
  
**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um PBX no Site 2**

![PBX WAN do servidor de mediação de topologia de voz](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
A figura a última neste tópico mostra uma topologia onde o servidor de mediação é conectado o SBC de um provedor de serviços de telefonia da Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Planejando decisões para o Servidor de Mediação

Este tópico descreve as decisões de planejamento, que você precisará fazer para sua implantação de servidor de mediação,
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de mediação autônomos ou colocados?

Servidor de mediação é por padrão colocado no servidor Standard Edition ou servidor Front-End em um pool de Front-End em locais centrais. O número de chamadas PSTN (Rede Telefônica Pública Comutada) que podem ser tratadas e o número de máquinas necessárias no pool dependerá do seguinte:
  
- O número de pares de gateway que controla o pool do servidor de mediação
    
- Dos períodos de alto volume de tráfego por meio desses gateways
    
- A porcentagem de chamadas queque ignoram o servidor de mediação
    
Durante o planejamento, considere os requisitos de processamento de mídia das chamadas PSTN e das conferências A/V não configuradas para bypass de mídia, além do processamento necessário para lidar com as interações de sinalização em relação ao número de chamadas em horário de pico que precisam de suporte. Se não for suficiente CPU, em seguida, você deve implantar um pool autônomo dos servidores de mediação; e gateways PSTN, IP-PBXs e SBCs precisará ser dividido em subconjuntos são controlados pelos servidores de mediação colocado em um pool e os servidores de mediação autônomo em um ou mais pools autônomos.
  
Se você implantou os gateways PSTN, IP-PBXs ou controladores de borda de sessão (SBCs) que não suportam os recursos corretos para interagir com um pool de servidores de mediação, incluindo o seguinte, e em seguida, eles precisarão ser associado a um pool autônomo consistindo de um único servidor de mediação:
  
- Executar o sistema de nome de domínio (DNS) balanceamento de carga em servidores de mediação em um pool de camada de rede (ou caso contrário, rotear tráfego uniformemente para todos os servidores de mediação em um pool)
    
- Aceitar tráfego de qualquer servidor de mediação em um pool
    
Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se colocando o servidor de mediação com seu pool de Front-End pode manipular a carga. Se seu ambiente não pode atender a esses requisitos, você deve implantar um pool do servidor de mediação autônomo.
  
### <a name="central-site-and-branch-site-considerations"></a>Considerações sobre o local central e o local da filial

 Servidores de mediação no site central podem ser usado para rotear chamadas para o IP-PBXs ou gateways PSTN em filiais. No entanto, se você implantar troncos SIP, você deve implantar um servidor de mediação no site onde finaliza a cada tronco. Ter um servidor de mediação em que o site central rotear chamadas para um IP-PBX ou gateway PSTN em um site de filial não exige o uso de media bypass. Porém, se você puder habilitar o bypass de mídia, isso reduzirá a latência do caminho de mídia e melhorará a qualidade da mídia, pois o caminho de mídia não será mais necessário para seguir o caminho de sinalização. Bypass de mídia também diminui a carga de processamento no pool.
  
> [!NOTE]
> O bypass de mídia não interoperará com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. Bypass de mídia é suportado somente com produtos e versões listadas em [Unified Communications programa de interoperabilidade aberta - Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730). 
  
Se a resiliência de site de filial for necessária, um aparelho de filial persistente ou a combinação de um servidor Front-End, um servidor de mediação e um gateway deve ser implantada no site da filial. (A pressuposição com resiliência de site de filial é que presença e conferência não são resilientes no site.) Para obter orientação sobre o site de filial Planejando o voice, consulte [Planejar a resiliência do Enterprise Voice em Skype para Business Server](enterprise-voice-resiliency.md).
  
Para interações com um IP-PBX, se o IP-PBX não suporta corretamente interações de mídia inicial com várias caixas de diálogo iniciais e interações do RFC 3960, pode haver corte da primeira primeiras palavras da saudação de chamadas de entrada do IP-PBX para Skype para Pontos de extremidade de negócios. Esse problema pode ser mais grave se um servidor de mediação em um site central for onde a rota será encerrada em um site de filial, roteamento de chamadas para um IP-PBX por mais tempo é necessário para a conclusão de sinalização. Se você enfrentar esse comportamento, implantar um servidor de mediação no site da filial é a única maneira de reduzir o corte da primeira algumas palavras.
  
Finalmente, se o site central tiver um PBX TDM, ou se o IP-PBX não elimina a necessidade de um gateway PSTN, você deve implantar um gateway de rota de chamada conectando o servidor de mediação e o PBX.
  
> [!NOTE]
> Para aprimorar o desempenho de mídia do Servidor de Mediação autônomo, você deve habilitar o RSS (receive-side scaling) nos adaptadores de rede nesses servidores. O RSS permite que pacotes de entrada sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte ["Receive-Side dimensionamento aprimoramentos no Windows Server"](https://go.microsoft.com/fwlink/p/?LinkId=268731). Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede. 
  

