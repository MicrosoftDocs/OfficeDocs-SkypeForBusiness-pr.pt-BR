---
title: Componente do servidor de mediação no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
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
description: Saiba mais sobre os servidores de mediação no Skype for Business Server, incluindo topologias compatíveis e suas relações com troncos M:N, bypass de mídia e controle de admissão de chamadas.
ms.openlocfilehash: 5a8e9d7728f8c78643869a6f816ade9431229751
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802691"
---
# <a name="mediation-server-component-in-skype-for-business-server"></a>Componente do servidor de mediação no Skype for Business Server
 
Saiba mais sobre os servidores de mediação no Skype for Business Server, incluindo topologias compatíveis e suas relações com troncos M:N, bypass de mídia e controle de admissão de chamadas.
  
Para implantar o Enterprise Voice, você deve implantar um ou mais servidores de mediação. 
  
O servidor de mediação traduz a sinalização entre sua infraestrutura interna de voz corporativa e um gateway PSTN (rede telefônica pública comutada) ou um tronco SIP (Session Initiation Protocol). Em algumas implantações, ele também converte a própria mídia entre esses pontos.
  
No lado do Skype for Business Server, o servidor de mediação escuta em um único endereço de transporte de single NNTP (MTLS) mútuo. No lado do gateway, o servidor de mediação escuta todas as portas de escuta associadas a troncos associadas. Todos os gateways qualificados devem dar suporte a TLS, mas também podem habilitar o TCP. O TCP é aceito para gateways que não dão suporte a TLS.
  
Se você também tiver um PBX (Exchange Branch Exchange) existente em seu ambiente, o servidor de mediação manipulará chamadas entre usuários do Enterprise Voice e o PBX. Se o seu PBX for um PBX IP, você poderá criar uma conexão SIP direta entre o PBX e o servidor de mediação. Se o seu PBX for um PBX TDM (Time Division multiplex), você também deve implantar um gateway PSTN entre o servidor de mediação e o PBX.
  
O servidor de mediação é posicionado com o servidor front-end por padrão. O servidor de mediação também pode ser implantado em um pool autônomo.
  
## <a name="what-mediation-server-does"></a>Qual é a função do Servidor de Mediação

As principais funções do servidor de mediação são as seguintes:
  
- Criptografar e descriptografar o SRTP no lado do Skype for Business Server. 
    
- Conversão do SIP sobre TCP (para gateways que não oferecem suporte a TLS) em SIP sobre MTLS (TLS mútuo).
    
- Tradução de fluxos de mídia entre o Skype for Business Server e o peer do gateway do servidor de mediação.
    
- Conexão de clientes fora da rede com componentes internos de ICE, que permitem a passagem de mídia do NAT e de firewalls.
    
- Atuar como intermediário para fluxos de chamadas aos quais um gateway não oferece suporte, como chamadas de trabalhadores remotos em um clien de voz da empresa. t
    
- Em implantações que incluem tronco SIP, trabalho conjunto com o provedor de serviços de tronco SIP para oferecer suporte à PSTN, eliminando a necessidade de um gateway PSTN.
    
A figura a seguir mostra os protocolos de sinalização e mídia usados pelo servidor de mediação durante a comunicação com um gateway PSTN básico e com a infraestrutura Enterprise Voice.
  
**Protocolos de sinalização e a mídia usados pelo Servidor de Mediação**

![Diagrama de protocolos do servidor de mediação](../../media/c3d39ba0-e323-4a58-8f07-4e80d3278af2.jpg)
  
> [!NOTE]
> Se você estiver usando TCP ou RTP/RTCP (em vez do SRTP ou SRTCP) na rede entre o gateway PSTN e o servidor de mediação, recomendamos que você tome medidas para ajudar a garantir a segurança e a privacidade da rede. 
  
## <a name="mn-trunk"></a>Tronco M:N

O Skype for Business Server dá suporte à flexibilidade na definição de um tronco para fins de roteamento de chamadas. Um tronco é uma associação lógica entre um servidor de mediação e um número de porta de escuta, com um gateway e um número de porta de escuta. Isso implica várias coisas: um servidor de mediação pode ter vários troncos para o mesmo gateway; um servidor de mediação pode ter vários troncos para gateways diferentes; por outro lado, um gateway pode ter vários troncos para diferentes servidores de mediação.
  
Você ainda deve criar um tronco raiz quando adicionar um gateway à sua topologia do Skype for Business usando o construtor de topologias. O número de gateways que um determinado servidor de mediação pode manipular depende da capacidade de processamento do servidor durante o pico de horas de ocupação. Se você implantar um servidor de mediação em hardware que atenda aos requisitos mínimos de hardware do Skype for Business Server, conforme descrito em [requisitos do servidor para o Skype for Business server 2015](../../plan-your-deployment/requirements-for-your-environment/server-requirements.md), um servidor de mediação autônomo poderá lidar com aproximadamente 1000 chamadas. O servidor de mediação é executado em transcodificação, mas ainda roteia chamadas para vários gateways, mesmo que os gateways não tenham suporte para bypass de mídia.
  
Ao definir um roteiro de chamada, especifique os troncos associados a essa rota, mas você não especifica quais servidores de mediação estão associados a essa rota. Em vez disso, use o construtor de topologias para associar troncos a servidores de mediação. Em outras palavras, o roteamento determina qual tronco usar para uma chamada e, subsequentemente, o servidor de mediação associado a esse tronco é enviado à sinalização para essa chamada.
  
O servidor de mediação pode ser implantado como um pool; esse pool pode ser colocado em um pool de front-ends ou pode ser implantado como um pool autônomo. Quando um servidor de mediação é posicionado com um pool de front-end, o tamanho do pool pode ser no máximo 12 (o limite do tamanho do pool do registrador). Juntos, esses recursos aumentam a confiabilidade e a flexibilidade de implantação para servidores de mediação, mas exigem recursos semelhantes nos seguintes:
  
- **Gateway PSTN.** Um gateway qualificado do Skype for Business Server deve implementar o balanceamento de carga de DNS, que permite que um gateway PSTN (rede telefônica pública comutada) compatível atue como um balanceador de carga para um pool de servidores de mediação e, portanto, para balancear a carga nas chamadas no pool .
    
- **Controlador de Borda da Sessão.** Para um tronco SIP, a entidade par é um SBC (Controlador de Borda da Sessão) no provedor de serviços de telefonia da Internet. Na direção do pool do servidor de mediação para o SBC, o SBC pode receber conexões de qualquer servidor de mediação no pool. Na direção do SBC para o pool, o tráfego pode ser enviado para qualquer servidor de mediação no pool. Um método que permite isso é através do balanceamento de carga DNS, se ele tiver suporte do provedor de serviços e do SBC. Uma alternativa é conceder ao provedor de serviços os endereços IP de todos os servidores de mediação do pool, e o provedor de serviço provisionará esses endereços no SBC como um tronco SIP separado para cada servidor de mediação. O provedor de serviços tratará o balanceamento de carga de seus próprios servidores. Nem todos os provedores de serviços ou SBCs podem dar suporte a essas funcionalidades. Além disso, o provedor de serviços pode cobrar mais por essa funcionalidade. Geralmente, cada tronco SIP até o SBC é tarifado mensalmente.
    
- **IP-PBX.** Na direção do pool do servidor de mediação para o cancelamento SIP IP-PBX, o IP-PBX pode receber conexões de qualquer servidor de mediação no pool. Na direção do PBX IP para o pool, o tráfego pode ser enviado para qualquer servidor de mediação no pool. Como a maioria dos PBXs IP não é compatível com o balanceamento de carga de DNS, recomendamos que as conexões SIP diretas SIP sejam definidas a partir do IP-PBX para cada servidor de mediação do pool. Depois disso, o IP-PBX tratará seu próprio balanceamento de carga distribuindo o tráfego pelo grupo de troncos. Presume-se que o grupo de troncos tenha um conjunto de regras de roteamento consistente no IP-PBX. Se um IP-PBX específico dá suporte a esse conceito de grupo de troncos e como ele faz a interseção entre a redundância do IP-PBX e a arquitetura de clustering precisa ser determinada antes que você possa decidir se um cluster do servidor de mediação pode interagir corretamente com um IP-PBX.
    
Um pool de servidores de mediação deve ter uma exibição uniforme do gateway de par com o qual ele interage. Isso significa que todos os membros do pool acessam a mesma definição do gateway par a partir do repositório de configurações e têm a mesma probabilidade de interagir com ele para as chamadas de saída. Portanto, não há nenhuma maneira de segmentar o pool para que alguns servidores de mediação se comuniquem somente em determinados pares de gateway para chamadas feitas. Se tal segmentação for necessária, um pool separado de servidores de mediação deve ser usado. Isso seria o caso, por exemplo, se as funcionalidades associadas nos gateways PSTN, nos troncos SIP ou nos IP-PBXs para interagir com um pool, conforme detalhado anteriormente neste tópico, não estivessem presentes.
  
Um determinado gateway PSTN, IP-PBX ou par de tronco SIP podem ser roteados para vários servidores de mediação ou troncos. O número de gateways que um determinado pool de servidores de mediação pode controlar depende do número de chamadas que usam bypass de mídia. Se um grande número de chamadas usar bypass de mídia, um servidor de mediação no pool pode manipular muitas outras chamadas, pois somente o processamento da camada de sinalização é necessário. 
  
## <a name="call-admission-control-and-mediation-server"></a>Controle de admissão de chamadas e Servidor de Mediação

O CAC (controle de admissão de chamadas) gerencia o estabelecimento de sessão em tempo real com base na largura de banda disponível para ajudar a evitar uma QoE (Qualidade da Experiência) ruim para os usuários em redes congestionadas. Para dar suporte a isso, o servidor de mediação é responsável pelo gerenciamento da largura de banda das duas interações no lado do Skype for Business Server e no lado do gateway. No controle de admissão de chamadas, a entidade de terminação de uma chamada lida com a reserva de largura de banda. Os pares de gateway (gateway PSTN, IP-PBX, SBC) com o qual o servidor de mediação interage no lado do gateway não dão suporte ao controle de admissão de chamadas do Skype for Business Server. Portanto, o servidor de mediação precisa manipular interações de largura de banda em nome de seu peer de gateway. Sempre que possível, o servidor de mediação reservará largura de banda antecipadamente. Se isso não for possível (por exemplo, se a localidade do ponto de extremidade de mídia final no lado do gateway for desconhecido de uma chamada de saída para o par de gateway), a largura de banda será reservada quando a chamada for feita. Esse comportamento poderá resultar em uma inscrição em excesso de assinatura da largura de banda, mas é a única maneira de impedir anéis falsos.
  
O bypass de mídia e a reserva de largura de banda são mutuamente exclusivos. Se um bypass de mídia for empregado para uma chamada, o controle de admissão de chamadas não será executado para essa chamada. Presume-se que não haja links envolvidos na chamada com a largura de banda restrita. Se o controle de admissão de chamadas for usado para uma chamada específica que envolva o servidor de mediação, essa chamada não poderá empregar o bypass de mídia.
  
Para obter detalhes sobre o bypass de mídia ou o controle de admissão de chamadas, consulte [planejar a bypass de mídia no Skype for Business](media-bypass.md) ou [planejar o controle de admissão de chamadas no Skype for Business Server](call-admission-control.md).
  
## <a name="enhanced-9-1-1-e9-1-1-and-mediation-server"></a>E9-1-1 (9-1-1 Avançado) e Servidor de Mediação

O servidor de mediação tem recursos estendidos para que ele possa interagir corretamente com provedores de serviços Enhanced 9-1-1 (E9-1-1). Nenhuma configuração especial é necessária no servidor de mediação. As extensões SIP necessárias para a interação do E9-1-1 são, por padrão, incluídas no protocolo SIP do servidor de mediação para suas interações com um peer de gateway (gateway PSTN, PBX IP ou SBC de um provedor de serviços de telefonia pela Internet, incluindo o serviço E9-1-1 Provedor
  
Se o tronco SIP para um provedor de serviços E9-1-1 pode ser encerrado em um pool do servidor de mediação existente ou exigir servidores de mediação autônomos dependerá se o E9-1-1 SBC pode interagir com um pool de servidores de mediação. Para obter detalhes, consulte [tronco M:N no Skype for Business Server](m-n-trunk.md).
  
## <a name="media-bypass-and-mediation-server"></a>Bypass de mídia e Servidor de Mediação

O bypass de mídia é um recurso do Skype for Business Server que permite que um administrador configure o roteamento de chamadas para fluir diretamente entre o ponto de extremidade do usuário e o gateway PSTN (rede telefônica pública comutada) sem atravessar o servidor de mediação. O bypass de mídia melhora a qualidade da chamada reduzindo a latência, a tradução desnecessária, a possibilidade de perda de pacotes e a quantidade de pontos de falha em potencial. Quando um site remoto sem um servidor de mediação está conectado a um site central por um ou mais links de WAN com largura de banda restrita, o bypass de mídia reduz a necessidade de largura de banda habilitando a mídia de um cliente em um site remoto para fluir diretamente para seu gateway local sem Primeiro, é necessário fluir pelo link de WAN para um servidor de mediação no site central e para trás. Essa redução no processamento de mídia também complementa a capacidade do servidor de mediação de controlar vários gateways.
  
O bypass de mídia e o CAC (controle de admissão de chamadas) são mutuamente exclusivos. Se o bypass de mídia for empregado para uma chamada, o CAC não será executado para essa chamada. Presume-se que não haja links com largura de banda restrita envolvidos na chamada.
  
## <a name="topologies-for-mediation-server"></a>Topologias do Servidor de Mediação

O servidor do Skype for Business, Mediation Server, é posicionado por padrão com o servidor Standard Edition, um pool de front-end ou um aparelho de ramificação sobreviventes. Todos os servidores de mediação em um pool Front-end devem ser configurados de maneira idêntica.
  
Onde o desempenho é um problema, pode ser preferível implantar um ou mais servidores de mediação em um pool autônomo dedicado. Se você estiver implantando um tronco SIP, recomendamos certamente um pool autônomo. 
  
Se você implantar conexões SIP diretas em um gateway PSTN qualificado que ofereça suporte ao bypass de mídia e ao balanceamento de carga de DNS, um pool autônomo do servidor de mediação não será necessário. Isso ocorre porque os gateways qualificados são capazes de balanceamento de carga de DNS para um pool de servidores de mediação e podem receber tráfego de qualquer servidor de mediação em um pool.
  
Também recomendamos que você colocar o servidor de mediação em um pool de front-end quando tiver implantado PBXs de IP ou conectar-se a um controlador de borda de sessão (SBC) do provedor de servidor de telefonia pela Internet, contanto que qualquer uma das seguintes condições seja atendida:
  
- O IP-PBX ou o SBC está configurado para receber tráfego de qualquer servidor de mediação no pool e pode rotear o tráfego uniformemente para todos os servidores de mediação no pool.
    
- O IP-PBX não é compatível com o bypass de mídia, mas o pool de front-end que hospeda o servidor de mediação pode manipular a transcodificação de voz para chamadas para as quais o bypass de mídia não se aplica.
    
Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se o pool de front-ends em que você deseja colocar o servidor de mediação pode manipular a carga. Se o seu ambiente não puder atender a esses requisitos, você deve implantar um pool autônomo do servidor de mediação.
  
A figura a seguir mostra uma topologia simples que consiste em dois locais conectados por um link WAN. O servidor de mediação está posicionado em um pool de front-ends no site 1. Os servidores de mediação no site 1 controlam o gateway PSTN no site 1 e o gateway no site 2. Nessa topologia, o bypass de mídia está habilitado globalmente para usar as informações do local e da região, e os troncos até cada gateway PSTN (GW1 e GW2) têm bypass habilitado.
  
**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um gateway PSTN no Site 2**

![Topologia de voz com gateway de WAN servidor de mediação](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanGwy.jpg)
  
A próxima figura mostra uma topologia simples em que o servidor de mediação está posicionado no pool de front-end no site 1 e tem uma conexão SIP direta com o IP-PBX no site 1. Nesta figura, o servidor de mediação também controla um gateway PSTN no site 2. Suponha que os usuários do Skype for Business existem nos dois locais: 1 e 2. Além disso, presumir que o IP-PBX tem um processador de mídia associado que deve ser percorrido por todas as mídias originadas dos pontos de extremidade do Skype for Business antes de ser enviado a pontos de extremidade de mídia controlados pelo IP-PBX. Nessa topologia, o bypass de mídia está habilitado globalmente para usar as informações do local e da região, e os troncos até o PBX e o gateway PSTN têm o bypass de mídia habilitado.
  
**Exemplo de sites conectados por um link WAN com um Servidor de Mediação no Site 1 e um PBX no Site 2**

![WAN Topology Mediation Server PBX PBX](../../media/Plan_LyncServer_Voice_Topo_MedSvrWanPbx.jpg)
  
O último número neste tópico mostra uma topologia em que o servidor de mediação está conectado ao SBC de um provedor de serviços de telefonia pela Internet. 
  
## <a name="planning-decisions-for-mediation-server"></a>Planejando decisões para o Servidor de Mediação

Este tópico descreve decisões de planejamento que você precisa fazer para a implantação do servidor de mediação,
  
### <a name="collocated-or-stand-alone-mediation-server"></a>Servidor de mediação autônomo ou posicionado?

O servidor de mediação é posicionado por padrão no servidor Standard Edition ou no servidor front-end em um pool de front-ends em sites centrais. O número de chamadas PSTN (Rede Telefônica Pública Comutada) que podem ser tratadas e o número de máquinas necessárias no pool dependerá do seguinte:
  
- O número de pares de gateway que o pool do servidor de mediação controla
    
- Dos períodos de alto volume de tráfego por meio desses gateways
    
- A porcentagem de chamadas que são chamadas cuja mídia ignora o servidor de mediação
    
Durante o planejamento, considere os requisitos de processamento de mídia das chamadas PSTN e das conferências A/V não configuradas para bypass de mídia, além do processamento necessário para lidar com as interações de sinalização em relação ao número de chamadas em horário de pico que precisam de suporte. Se não houver CPU suficiente, você deve implantar um pool autônomo de servidores de mediação; e os gateways PSTN, PBXs IP e SBCs precisarão ser divididos em subconjuntos controlados pelos servidores de mediação posicionados em um pool e os servidores de mediação autônomos em um ou mais pools autônomos.
  
Se você implantou gateways PSTN, PBXs de IP ou controladores de borda de sessão (SBCs) que não são compatíveis com os recursos corretos para interagir com um pool de servidores de mediação, incluindo o seguinte, eles precisarão estar associados a um pool autônomo que consiste em de um servidor de mediação único:
  
- Executar o balanceamento de carga de DNS (sistema de nomes de domínio) de camada de rede em servidores de mediação em um pool (ou de outra forma rotear uniformemente para todos os servidores de mediação em um pool)
    
- Aceitar o tráfego de qualquer servidor de mediação em um pool
    
Você pode usar o Microsoft Lync Server 2013, ferramenta de planejamento para avaliar se colocar o servidor de mediação no seu pool de front-end pode manipular a carga. Se o seu ambiente não puder atender a esses requisitos, você deve implantar um pool autônomo do servidor de mediação.
  
### <a name="central-site-and-branch-site-considerations"></a>Considerações sobre o local central e o local da filial

 Os servidores de mediação no site central podem ser usados para direcionar chamadas para IP-PBXs ou gateways PSTN em sites de filiais. No entanto, se você implantar troncos SIP, deve implantar um servidor de mediação no site em que cada tronco termina. Ter um servidor de mediação no site central chamadas de rota para um IP-PBX ou um gateway PSTN em um site de filial não requer o uso do bypass de mídia. Porém, se você puder habilitar o bypass de mídia, isso reduzirá a latência do caminho de mídia e melhorará a qualidade da mídia, pois o caminho de mídia não será mais necessário para seguir o caminho de sinalização. O bypass de mídia também diminui a carga de processamento no pool.
  
> [!NOTE]
> O bypass de mídia não interoperará com cada gateway PSTN, IP-PBX e SBC. A Microsoft testou um conjunto de gateways PSTN e SBCs com os parceiros certificados e realizou alguns testes com IP-PBXs da Cisco. O bypass de mídia só tem suporte com produtos e versões listados no [programa de interoperabilidade aberta da comunicação unificada-Lync Server](https://go.microsoft.com/fwlink/p/?LinkId=268730). 
  
Se a resiliência do site de ramificação for necessária, um aparelho de ramificação sobreviventes ou uma combinação de um servidor front-end, um servidor de mediação e um gateway devem ser implantados no site da filial. (A pressuposição da resiliência do site da ramificação é que a presença e a conferência não são resistentes no site.) Para obter orientação sobre o planejamento de sites de filiais, consulte [planejar a resiliência do Enterprise Voice no Skype for Business Server](enterprise-voice-resiliency.md).
  
Para interações com um PBX IP, se o IP-PBX não suportar corretamente interações de mídia antigas com várias caixas de diálogo iniciais e interações RFC 3960, pode haver o recorte das primeiras palavras da saudação para as chamadas recebidas do IP-PBX para o Skype for Pontos de extremidade comerciais. Esse problema pode ser mais sério se um servidor de mediação em um site central estiver encaminhando chamadas para um PBX IP em que a rota termina em um site de filial, pois é necessária mais tempo para a sinalização ser concluída. Se você tiver esse comportamento, a implantação de um servidor de mediação no site da filial é a única maneira de reduzir o recorte das primeiras palavras.
  
Por fim, se o seu site central tiver um PBX de TDM, ou se o seu PBX IP não eliminar a necessidade de um gateway PSTN, você deve implantar um gateway no servidor de mediação conectando o servidor de mediação da chamada e o PBX.
  
> [!NOTE]
> Para aprimorar o desempenho de mídia do Servidor de Mediação autônomo, você deve habilitar o RSS (receive-side scaling) nos adaptadores de rede nesses servidores. O RSS permite que pacotes de entrada sejam manipulados em paralelo por vários processadores no servidor. Para obter detalhes, consulte ["aprimoramentos de dimensionamento no lado do Windows Server"](https://go.microsoft.com/fwlink/p/?LinkId=268731). Para obter detalhes sobre como habilitar o RSS, consulte a documentação do seu adaptador de rede. 
  

