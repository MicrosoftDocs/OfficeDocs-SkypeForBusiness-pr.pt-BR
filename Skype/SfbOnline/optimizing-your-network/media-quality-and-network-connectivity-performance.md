---
title: Qualidade de mídia e desempenho de conectividade de rede
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
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
description: Este tópico define o conjunto de requisitos de desempenho de rede para os serviços do Skype for Business Online e como você pode optar por usar a Internet ou o ExpressRoute para conectividade entre sua rede e o Skype for Business online com base na sua avaliação da conectividade de rede. Se você decidiu implantar o Azure ExpressRoute para conectividade dedicada com o Microsoft 365 ou o Office 365, este documento também fornece uma orientação sobre como planejar suas conexões do ExpressRoute em diferentes cenários de implantação do Skype for Business online.
ms.openlocfilehash: d49dd3e925c71a9e0f2b73bbe364ad4478566cad
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164760"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Qualidade de mídia e desempenho da conectividade de rede no Skype for Business Online

Este tópico define o conjunto de requisitos de desempenho de rede para os serviços do Skype for Business Online e como você pode optar por usar a Internet ou o ExpressRoute para conectividade entre sua rede e o Skype for Business online com base na sua avaliação da conectividade de rede. Se você decidiu implantar o Azure ExpressRoute para conectividade dedicada com o Microsoft 365 ou o Office 365, este documento também fornece uma orientação sobre como planejar suas conexões do ExpressRoute em diferentes cenários de implantação do Skype for Business online.
  
A qualidade da mídia em tempo real (compartilhamento de áudio, vídeo e aplicativos) por IP é bastante afetada pela qualidade da conectividade de rede de ponta a ponta. Para obter uma excelente qualidade de mídia com o Skype for Business Online, é importante ter uma conexão de alta qualidade entre a rede da sua empresa e o Skype for Business Online. A melhor maneira de conseguir isso é configurar sua rede interna e a conectividade de nuvem com base na capacidade da sua rede para acomodar o volume de pico de tráfego do Skype for Business Online em todas as conexões.
  
O Azure ExpressRoute não é um requisito para os serviços do Microsoft 365 e do Office 365, incluindo o Skype for Business online. No entanto, o Azure ExpressRoute é uma das opções de implantação disponíveis que ajudará a garantir que a conectividade com o Microsoft 365 ou o Office 365 atenda aos requisitos de desempenho de rede do Skype for Business e garanta a melhor experiência de qualidade de mídia do Skype for Business online.
  
> [!TIP]
> Embora este tópico forneça diretrizes gerais de desempenho de rede, a orientação completa para avaliação de rede está fora do escopo deste documento. Para encontrar uma lista de parceiros do Skype for Business online que podem ajudá-lo com as medidas de desempenho de rede como parte de uma avaliação de rede completa e completa, acesse [soluções de parceiros do Skype for Business](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisitos de conectividade de rede para o Skype for Business Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Fatores que afetam a qualidade da mídia do Skype for Business Online

Há muitos fatores diferentes que contribuem para a qualidade de mídia em tempo real do Skype for Business online (compartilhamento de áudio, vídeo e aplicativos) que incluem os dispositivos que são usados, o ambiente e a conectividade de rede. 
  
#### <a name="devices"></a>Dispositivos

Em uma sessão de mídia em tempo real, dispositivos de captura e renderização de mídia que são usados por todos os participantes, como fones de ouvido e Cams da Web, têm um grande impacto sobre a qualidade geral do áudio e do vídeo. Dispositivos de qualidade inferior ou com drivers incorretos produzirão uma qualidade geral inferior de som e imagem. Por outro lado, dispositivos certificados ou de boa qualidade ajudam a eliminar o eco, filtram ruídos, aumentam a resolução de vídeo e reduzem a latência.
  
Embora os dispositivos de mídia de áudio e vídeo certificados não sejam necessários, os dispositivos altamente recomendados são certificados para o Skype for Business para obter a melhor experiência de mídia. Para obter uma lista de todos os dispositivos certificados pelo Skype for Business, consulte [telefones e dispositivos do Skype for Business](https://technet.microsoft.com/office/dn947482). Você pode usar o [painel de qualidade de chamada do Skype for Business online](/microsoftteams/turning-on-and-using-call-quality-dashboard), encontrado no **centro de administração do Skype for Business**, para verificar se os dispositivos em uso estão funcionando corretamente e para monitorar a qualidade da mídia de áudio e vídeo.
  
> [!TIP]
> **É necessário um dispositivo certificado para obter a melhor experiência de qualidade de mídia do Skype for Business**.
  
É importante lembrar que qualquer dispositivo de mídia, clientes do Skype for Business e servidores do Skype for Business por meio do qual fluxos de mídia em tempo real fluem, apresentam uma certa latência. A latência de processamento do dispositivo e do software, juntamente com a latência da rede, tem um ótimo impacto sobre e contribuir com a latência geral completa e a experiência do usuário final.
  
#### <a name="environment"></a>Ambiente.

O ambiente e a área vizinha onde os usuários estão fazendo a reunião e usando dispositivos de áudio e vídeo são outro fator importante para a qualidade. Os usuários que fizerem chamadas em um ambiente barulhento terão áudio com eco, abafado e indistinto. Os usuários que estiverem em um ambiente escuro ou com pouca luz não obterão uma qualidade de imagem clara e viva. Em uma sala de conferência, o local do microfone e do dispositivo de vídeo afeta diretamente a qualidade do som e da imagem que os participantes receberão.
  
Para obter uma imagem mais clara da experiência de áudio e vídeo de um usuário, use as**Opções** > de **ferramentas** > de aplicativos do Skype for**Business ou o** **dispositivo de vídeo** para fazer alterações no dispositivo em uso e personalizar as configurações.

#### <a name="network"></a>Rede

A qualidade da mídia em tempo real em relação à rede IP é bastante afetada pela qualidade da conectividade de rede, mas especialmente pela quantidade de:
  
- **Latência** Esse é o tempo necessário para obter um pacote IP do ponto a ao ponto B na rede. Esse atraso de propagação de rede está essencialmente ligado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional sofrida pelos vários roteadores intermediários. A latência é medida como ponto-a-ponto ou RTT (tempo de ida e volta).
    
- **Perda de pacote** Isso geralmente é definido como uma porcentagem de pacotes perdidos em uma determinada janela de tempo. A perda de pacotes afeta diretamente a qualidade do áudio, desde pequenos pacotes perdidos individuais com quase nenhum impacto, até perdas de Burst back-to-back que causam o recorte de áudio completo.
    
- **Tremulação de chegada entre pacotes ou simplesmente tremulação** Esta é a alteração média no atraso entre pacotes sucessivos. O software VoIP mais moderno, incluindo o Skype for Business, pode adaptar-se a alguns níveis de tremulação por meio do buffer. É somente quando a tremulação excede o buffer que o participante nota os efeitos da tremulação.
    
> [!NOTE]
>  O buffer para tremulação aumenta a latência de ponto a ponto.
  
Com muitas sessões simultâneas de mídia em tempo real do Skype for Business Online, bem como outro tráfego de rede gerado por outros serviços do Microsoft 365 ou do Office 365 e outros aplicativos de negócios, certificar-se de que há largura de banda suficiente em todo o caminho da rede que conecta a sua rede ao serviço do Skype for Business Online é essencial para evitar o congestionamento da rede e garantir a mídia qualidade, vídeo e compartilhamento de aplicativos). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementação de QoS (qualidade de serviço) em redes congestionadas

Além disso, o congestionamento do tráfego em uma rede terá impacto na qualidade da mídia. Para permitir que pacotes de áudio e de vídeo façam a viagem mais rápida da rede e sejam priorizados sobre outros tráfegos de rede em uma rede congestionada, a qualidade do serviço (QoS) pode ser usada para ajudar a oferecer uma experiência ideal para o usuário final para comunicações de áudio e vídeo.
  
A QoS fornece uma maneira de atribuir prioridades maiores aos pacotes de rede que estão executando dados de áudio ou vídeo. Ao atribuir uma prioridade mais alta a esses pacotes, as comunicações de áudio e vídeo provavelmente viajam pela rede com mais rapidez e com menos interrupções do que as sessões de rede envolvendo itens como transferências de arquivos, navegação na Web ou backups de banco de dados. Isso ocorre porque os pacotes de rede usados para transferências de arquivo ou backups de banco de dados por padrão são atribuídos "melhor esforço" porque a prioridade e o congestionamento da rede não têm um grande impacto. Se você não atribuir uma prioridade maior aos pacotes mídia (áudio, vídeo e compartilhamento de aplicativos) e deixá-los também atribuídos como "melhor esforço", eles também serão processados com todos os outros tipos de tráfego de rede. Dependendo da quantidade de congestionamento da rede, isso poderá acabar em uma experiência de qualidade geral de áudio e vídeo para seus usuários.
  
É altamente recomendável que você implemente QoS na sua rede para garantir que o congestionamento da rede na sua rede não terá impacto. No entanto, para que isso tenha o impacto máximo, todos os pontos de extremidade de rede devem oferecer suporte a QoS, o que significa que todos os pontos de extremidade devem respeitar a marcação de QoS e a priorização do pacote. Os serviços do Skype for Business online honram a marcação e a priorização de QoS na rede da Microsoft. No entanto, o tráfego roteado por uma conexão pública, como a Internet, da rede da sua empresa para a rede Microsoft, não preserva as marcações de QoS e a priorização de pacotes. As conexões privadas da sua rede com o Microsoft 365 ou o Office 365 usando o [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) oferecem uma solução de implantação que preserva as marcações de QoS e a priorização de pacote, que, por sua vez, aumentará a qualidade geral de áudio e vídeo para seus usuários finais.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisitos de desempenho de rede para se conectar ao Skype for Business Online
<a name="bkNetworkPerf"> </a>

O Skype for Business Media-time Media viaja por vários dispositivos diferentes, aplicativos cliente, software de servidor e em redes diferentes. A latência de ponta a ponta da mídia em tempo real é a quantidade total de latência introduzida em todos os componentes e segmentos de rede. A qualidade da conexão de rede de ponta a ponta é determinada pelo segmento de rede com a pior qualidade. Este segmento age como um afunilamento para esse tráfego de rede.
  
O diagrama a seguir ilustra um fluxo de áudio unidirecional em uma conferência de um participante do Skype for Business para outro.
  
![Fluxo de chamadas do ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
Neste cenário de conferência, o caminho de mídia consiste nos seguintes segmentos de rede:
  
1. **Conexão do usuário 1 para a borda da rede Microsoft** Geralmente, isso inclui uma conexão de rede, como WiFi ou Ethernet, a conexão WAN do usuário 1 para o ponto de saída da Internet (seu dispositivo de borda de rede) e a conexão com a Internet da sua borda de rede com a borda de rede da Microsoft.
    
2. **Conexão na rede da Microsoft** Isso ocorre entre o Microsoft Edge para o Data Center do Skype for Business Online, onde os servidores de conferência a/V são usados.
    
3. **Conexão na rede da Microsoft** Isso se encontra entre o Data Center do Skype for Business Online e o Microsoft Network Edge.
    
4. **Conexão do Microsoft Network Edge para o usuário 2** Isso inclui a conexão à Internet da sua borda de rede com o Microsoft Network Edge, a conexão WAN do usuário 2 para o ponto de saída da Internet (sua borda de rede) e a conexão de rede, como WiFi ou Ethernet.
    
O diagrama a seguir mostra a divisão dos componentes e dos segmentos de rede de uma chamada PSTN do Skype for Business Online:
  
![Fluxo de chamadas de portadora PSTN do ExpressRoute.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
Em um cenário de chamada PSTN, o caminho de mídia cruza os seguintes segmentos de rede:
  
1. **Conexão de um cliente Skype for Business chamador para a borda da rede Microsoft** Isso geralmente inclui uma conexão de rede, como WiFi ou Ethernet, a conexão WAN do cliente Skype for Business para o ponto de saída da Internet (seu dispositivo de borda de rede) e a conexão com a Internet da sua borda de rede para a borda de rede da Microsoft.
    
2. **Conexão na rede da Microsoft** Isso ocorre entre o Microsoft Edge para o Data Center do Skype for Business Online, onde um servidor de mediação é usado.
    
3. **Conexão na rede da Microsoft** Isso se encontra entre o Data Center do Skype for Business Online e o Microsoft Network Edge.
    
4. **Conexão entre o Microsoft Network e os parceiros do provedor de serviços PSTN** Esta é a conexão que existe para fazer uma chamada PSTN do cliente Skype for Business que está fora da rede da Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisitos de desempenho de rede de um cliente Skype for Business para a borda de rede da Microsoft
<a name="bkSfBClienttoEdge"></a>

Para obter a melhor qualidade de mídia do Skype for Business, as seguintes metas ou limiares de métricas de desempenho de rede são necessárias para uma conexão da rede da sua empresa com a borda de rede da Microsoft. Este segmento da rede inclui a sua rede interna, incluindo todas as conexões WiFi e Ethernet, qualquer tráfego de site para site da empresa em uma conexão WAN, por exemplo, a alternância de rótulo de protocolos múltiplos (MPLS), bem como as conexões de parceiros da Internet ou do ExpressRoute à borda de rede da Microsoft.
  
> [!CAUTION]
> **A conectividade entre um cliente Skype for Business na rede da empresa para o Microsoft 365 ou os serviços do Office 365 deve atender aos seguintes requisitos e limites de desempenho de rede.**
  
|||
|:-----|:-----|
|**Indicador** <br/> |**Destino ** <br/> |
|Latência (unidirecional)  <br/> |< 50ms  <br/> |
|Latência (RTT ou tempo de viagem de ida e volta)  <br/> |< 100 milhões  <br/> |
|Perda de pacote de intermitência  <br/> |<10% durante qualquer intervalo de 200ms  <br/> |
|Perda de pacote  <br/> |<1% durante qualquer intervalo 15s  <br/> |
|Tremulação entre entradas do pacote  <br/> |<30ms durante qualquer intervalo 15s  <br/> |
|Reordenação de pacotes  <br/> |< 0,05% de pacotes com problemas  <br/> |
   
 **Outros requisitos de destino de desempenho:**
  
- A rede da Microsoft tem mais de 160 locais para a periferia do mundo todo. Trabalhamos com a maioria dos provedores de serviços de Internet (ISPs) do mundo todo por meio desses sites periféricos. O destino da métrica de latência assume que o site ou sites da sua empresa e as bordas da Microsoft estejam no mesmo continente.
    
- Seu site de empresa ou sites para a conexão de borda de rede da Microsoft incluem o acesso de rede de primeiro salto, que pode ser WiFi ou outra tecnologia sem fio. 
    
- O destino do desempenho de rede pressupõe largura de banda adequada e/ou planejamento de qualidade do serviço. Em outras palavras, isso se aplica diretamente ao tráfego de mídia em tempo real do Skype for Business quando a conexão de rede estiver sob uma carga de pico.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisitos de desempenho de rede da borda da rede para a borda de rede da Microsoft
<a name="bkYourNetworkEdge"> </a>

Estes são os destinos ou os limites de desempenho de rede necessários para a conexão entre sua borda de rede e a borda de rede da Microsoft. Este segmento da rede exclui a rede interna do cliente ou a WAN, e destina-se a uma orientação ao testar o tráfego de rede enviado pela Internet ou por meio de uma rede de parceiros do expressroute e também pode ser usado para negociar um contrato de nível de serviço (SLA) de desempenho com seu provedor do ExpressRoute.
  
> [!CAUTION]
> **A conectividade entre a borda da rede da sua empresa para a borda de rede da Microsoft deve atender a esses requisitos e limites de desempenho de rede seguintes.**
  
|||
|:-----|:-----|
|**Indicador** <br/> |**Destino ** <br/> |
|Latência (unidirecional)  <br/> |< 30ms  <br/> |
|Latência (RTT)  <br/> |< 60ms  <br/> |
|Perda de pacote de intermitência  <br/> |<1% durante qualquer 200 MS Interval  <br/> |
|Perda de pacote  <br/> |<0,1% durante qualquer intervalo 15s  <br/> |
|Tremulação entre entradas do pacote  <br/> |<15ms durante qualquer intervalo 15s  <br/> |
|Reordenação de pacotes  <br/> |< 0,01% de pacotes com problemas  <br/> |
   
 **Outros requisitos de destino de desempenho:**
  
- O destino de desempenho requer conexão entre qualquer borda de rede da sua empresa e sua borda de rede da Microsoft mais próxima, para estar no mesmo continente.
    
- O destino do desempenho de rede pressupõe largura de banda adequada e/ou planejamento de qualidade do serviço. Isso também se aplica ao tráfego de mídia em tempo real do Skype for Business quando a conexão de rede estiver sob uma carga de pico. Para obter largura de banda e planejamento de QoS adequados, consulte o [ExpressRoute e QoS no Skype for Business online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d).
    
## <a name="measuring-network-performance"></a>Avaliar o desempenho da rede
<a name="bkNetworkPerf"> </a>

Para medir o desempenho real da rede, especialmente para a latência e perda de pacotes, de qualquer site de rede de empresa para uma borda de rede, você pode usar ferramentas como ping, testar em um conjunto de serviços de mídia do Skype for Business em execução a partir dos sites do Microsoft Edge e do Data Center. 

>[!NOTE]
> Avaliar o desempenho da rede por meio de ping (ICMP) não é eficaz. Por esse motivo, a exposição de IP anycast abaixo deixará de responder às solicitações de ICMP a partir de Jan, 2020. Para medir a performace de rede de maneira eficaz, a Microsoft recomenda a [ferramenta de assesment de rede](https://www.microsoft.com/download/details.aspx?id=53885).
  
Para testar conexões à Internet com a rede Microsoft, é recomendável que você teste com os seguintes VIPs das retransmissões de mídia do Skype for Business. O *VIP anycast* será resolvido para um endereço IP de um retransmissão de mídia em um site de borda de rede da Microsoft mais próximo do local de teste.
  
||||
|:-----|:-----|:-----|
|**Endereço IP** <br/> |**Tipo** <br/> |**Local** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |IP de alta largura do mundo  <br/> |
   
 **Veja algumas recomendações de alto nível a serem seguidas para avaliar o desempenho da rede:**
  
- Você deve avaliar sua rede interna, bem como as conexões com o Microsoft 365 ou o Office 365.
    
- Você deve avaliar e coletar dados de todas as suas redes durante um longo período de tempo. Recomendamos que você realize o teste do desempenho da rede por um mínimo de uma semana, para que você possa ver padrões de uso para todos os dias úteis e horários. Isso mostrará horários de pico.
    
- Você deve fazer várias amostras de medidas de desempenho de rede. Recomendamos fazer uma medição a cada 10 minutos a partir de um site de empresa durante todo o período de tempo que você está coletando dados. Para comparar os requisitos de desempenho de rede do Skype for Business Online, tome o valor de medição 90th percentil deste conjunto de dados de exemplo. 
    
- Você deve avaliar continuamente o desempenho da rede. A utilização da rede varia ao longo do tempo devido a alterações no padrão de uso, novos aplicativos baseados em empresas que usam uma grande quantidade de largura de banda e mudanças em seus locais corporativos ou organizacionais. É importante que você monitore continuamente o desempenho da sua rede contra esses requisitos de desempenho de rede e destinos/limiares e faça ajustes oportunos para garantir a qualidade da mídia em tempo real mais eficiente. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Avaliar o desempenho da rede usando VMs do Azure
<a name="bkNetworkPerf"> </a>

Em vez de testar os sites de borda de rede da Microsoft, há soluções de avaliação de rede de clientes e parceiros do Skype for Business que utilizam a configuração de teste para serviços na nuvem do Microsoft Azure. Nessas soluções, a latência de teste de ferramentas de avaliação de rede, perda de pacotes e Tremulação em relação a pontos de extremidade personalizados configurados como um serviço na nuvem do Azure. Como resultado, o tráfego de rede de teste passa por um segmento de rede adicional, que é a conexão na rede da Microsoft entre as bordas de rede e os data centers do Azure que hospedam o serviço de avaliação de rede.
  
Para essas soluções de avaliação de rede baseadas nos serviços de teste hospedados do Azure. Recomendamos executar a avaliação de rede dentro do país e/ou região. Por exemplo, para sites de clientes nos EUA do leste, a avaliação deve ser realizada em relação a uma instância de serviço de teste hospedada na região do centro de dados dos EUA do leste dos EUA. 
  
Abaixo estão os destinos de latência (RTT) da configuração de avaliação de rede baseada em serviço do Azure. Os destinos de latência unidirecionais serão metade dos destinos de RTT correspondentes. As metas de perda de pacotes e Tremulação permanecem as mesmas definidas para testes baseados no Skype Media Relay.
  
|||||
|:-----|:-----|:-----|:-----|
|**Região do cliente** <br/> |**Região do Azure** <br/> |**Sua borda de rede-tempo de ida e volta do Azure (RTT)** <br/> |**Seu site-RTT (tempo de viagem de ida e volta) do Azure** <br/> |
|Centro dos EUA  <br/> |Centro dos EUA  <br/> |99  <br/> |139  <br/> |
|Leste dos EUA  <br/> |Leste dos EUA  <br/> |86  <br/> |126  <br/> |
|Centro Norte dos EUA  <br/> |Centro Norte dos EUA  <br/> |97  <br/> |137  <br/> |
|Centro-Sul dos EUA  <br/> |Centro-Sul dos EUA  <br/> |94  <br/> |134  <br/> |
|Oeste dos EUA  <br/> |Oeste dos EUA  <br/> |94  <br/> |134  <br/> |
|Havaí para nós  <br/> |Oeste dos EUA  <br/> |116  <br/> |156  <br/> |
|Centro-Canadá  <br/> |Centro-Canadá  <br/> |138  <br/> |178  <br/> |
|Leste do Canadá  <br/> |Leste do Canadá  <br/> |131  <br/> |171  <br/> |
|Norte da Europa  <br/> |Norte da Europa  <br/> |99  <br/> |139  <br/> |
|Oeste da Europa  <br/> |Oeste da Europa  <br/> |95  <br/> |135  <br/> |
|Leste da Ásia  <br/> |Leste da Ásia  <br/> |118  <br/> |158  <br/> |
|Sudeste Asiático  <br/> |Sudeste Asiático  <br/> |97  <br/> |137  <br/> |
|Japão oriental  <br/> |Japão oriental  <br/> |111  <br/> |151  <br/> |
|Oeste do Japão  <br/> |Oeste do Japão  <br/> |118  <br/> |158  <br/> |
|Sul do Brasil  <br/> |Sul do Brasil  <br/> |70  <br/> |110  <br/> |
|Leste da Austrália  <br/> |Leste da Austrália  <br/> |124  <br/> |164  <br/> |
|Sudeste da Austrália  <br/> |Sudeste da Austrália  <br/> |124  <br/> |164  <br/> |
|Índia central  <br/> |Índia central  <br/> |103  <br/> |143  <br/> |
|Sul da Índia  <br/> |Sul da Índia  <br/> |103  <br/> |143  <br/> |
|Oeste da Índia  <br/> |Oeste da Índia  <br/> |103  <br/> |143  <br/> |
|Leste da China  <br/> |Leste da China  <br/> |120  <br/> |160  <br/> |
|Norte da China  <br/> |Norte da China  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Qualidade de mídia e rota expressa
<a name="bkNetworkPerf"> </a>

O Azure ExpressRoute para Microsoft 365 ou o Office 365 é uma conexão de rede dedicada para conexão com o Microsoft 365 ou o Office 365. Ele oferece aos clientes a capacidade de controlar o caminho que o tráfego de rede tem. Eles não precisam mais se preocupar com o roteamento imprevisível que acontece na Internet, onde os dados são transportados por operadoras, provedores e ISPs desconhecidos. O tráfego de rede enviado por meio do ExpressRoute é enviado diretamente pela rede do parceiro do ExpressRoute para a rede da Microsoft. Isso permite que os clientes tratem o Microsoft 365 ou o Office 365 como se ele se encontra no próprio centro de dados fora do site com uma conexão dedicada.
  
O Azure ExpressRoute está disponível para todas as ofertas de licenciamento do Microsoft 365 e do Office 365. No entanto, o complemento do Azure ExpressRoute Premium é necessário para o Microsoft 365 e o Office 365 para habilitar o roteamento global. Os clientes com pelo menos 500 estações que estão implementando o ExpressRoute podem obter o *complemento necessário do Expressroute Premium* sem nenhuma despesa adicional.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>O ExpressRoute é necessário para uma boa qualidade de mídia?

O Azure ExpressRoute não é um requisito para obter a melhor qualidade de mídia do Skype for Business online. No entanto, é uma das opções de implantação que o ajudam a garantir que a conectividade da nuvem atenda aos limites ou aos limites de desempenho de rede do Skype for Business.
  
O Microsoft 365 e o Office 365 são de alto desempenho e serviços seguros que usam a Internet. Continuamos a investir em novos recursos de segurança e nós de extremidade regional para melhorar a segurança e o desempenho continuamente. O Azure ExpressRoute não é um requisito para os serviços do Microsoft 365 ou do Office 365, incluindo o Skype for Business online. O Azure ExpressRoute é uma das opções de implantação disponíveis que ajudará a garantir que a conectividade com o Microsoft 365 ou o Office 365 atenda aos requisitos de desempenho de rede do Skype for Business e garanta a melhor experiência de qualidade de mídia do Skype for Business online.
  
Para a qualidade da mídia do Skype for Business Online, é importante que a conexão entre seus sites da empresa e as bordas de rede da Microsoft atenda aos objetivos de desempenho em [requisitos de desempenho de rede de um cliente Skype for Business para a Microsoft Network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) e que a conexão entre as [bordas da rede](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)e as bordas de rede  
  
Também é importante que a conectividade da rede física da sua empresa, incluindo a rede interna e a capacidade de conectividade da nuvem, acomode o volume de tráfego de mídia de pico. O Azure ExpressRoute é uma das muitas maneiras de ajudar os clientes a garantir que a conectividade da nuvem do Skype for Business online atenda a todos esses requisitos de desempenho.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>O ExpressRoute é necessário para o SLA de qualidade de voz?

Não, o ExpressRoute não é necessário para o SLA de qualidade de voz do Skype for Business online. O [SLA de qualidade de voz do Skype for Business online](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) aplica-se a qualquer chamada qualificada feita por qualquer usuário do serviço de voz do Skype for Business online dentro da licença e assinatura corretas que permitem que o usuário faça qualquer tipo de chamada de VoIP ou PSTN. Um SLA de qualidade de voz deve incluir todas as seguintes condições:
  
- Chamadas de telefones IP certificados pela Microsoft.
    
- Conexões Ethernet com fio.
    
- Problemas de qualidade de voz devido a problemas de rede da Microsoft.
    
> [!NOTE]
> O SLA de qualidade de voz exclui essas chamadas onde a baixa qualidade da chamada é causada por problemas em redes não Microsoft, incluindo o parceiro do ExpressRoute e outras redes. 
  
### <a name="internet-or-azure-expressroute"></a>Internet ou Azure ExpressRoute?

Antes de tomar uma decisão sobre as opções de conectividade de rede para o Skype for Business Online, os clientes devem avaliar a rede e a conectividade com a Internet atual com base nos requisitos de desempenho de rede descritos em [requisitos de desempenho de rede para se conectar ao Skype for Business online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Se o desempenho da rede pela conexão atual à Internet estiver configurado para a capacidade suficiente durante o pico e se ele atender aos requisitos de desempenho de rede de sites para bordas de rede da Microsoft e de suas bordas de rede às bordas da rede da Microsoft, você pode continuar a usar sua conexão de Internet existente para se conectar ao Skype for Business online.
  
Para sites da empresa em que os requisitos de desempenho de rede não estão sendo atendidos, recomendamos que você primeiro trabalhe com seus provedores de serviços de rede existentes para melhorar o desempenho geral da rede. No entanto, se ainda não estiverem sendo atendidos, usar o Azure ExpressRoute pode ajudar a garantir que a conectividade de nuvem do Skype for Business online possa ajudá-lo a atender aos requisitos de desempenho de rede.
  
O Azure ExpressRoute oferece os seguintes benefícios adicionais:
  
- Um contrato de nível de serviço (SLA) sobre a disponibilidade da conexão entre a rede e a rede da Microsoft. O ExpressRoute tem um SLA de disponibilidade garantida de 99,9%.
    
- Requer largura de banda planejada e garantida necessária para os serviços do Microsoft 365 e do Office 365. Você pode conseguir isso enviando apenas o tráfego do Microsoft 365, do Office 365 ou do Skype for Business que usa o ExpressRoute e, em seguida, que todos os outros tráfegos da Internet passam por outros pontos de egresso/ingress da Internet para a sua rede.
    
- O ExpressRoute foi projetado para preservar as marcações de QoS de DSCP entre a rede e a rede da Microsoft.
    
Para obter mais informações sobre a QoS da rota e o planejamento da capacidade, consulte [rota expressa e QoS no Skype for Business online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Posso configurar o Azure ExpressRoute somente para o Skype for Business Online?

Sim, você pode configurar o Azure ExpressRoute para garantir uma excelente conectividade de rede da rede da sua empresa para o Skype for Business online. Isso fornecerá a qualidade de mídia em tempo real ideal para seus usuários, mas você poderá continuar se conectando a outros serviços do Microsoft 365 ou do Office 365 pela Internet.
  
O BGP (Border Gateway Protocol) é um protocolo de roteamento na Internet que é usado para rotear o tráfego de rede na Internet. Ele foi projetado para trocar informações de roteamento entre sistemas autônomos (AS) encontradas na Internet. Os valores de comunidades BGP são marcas de atributo que podem ser aplicadas a rotas de entrada ou de saída. As comunidades de BGP geralmente são usadas para sinalizar para o recebimento do link de entrada para usar para atingir um destino específico com base na geografia, tipo de serviço ou outros critérios.
  
Com o suporte às comunidades BGP, a Microsoft marcará prefixos e rotas com valores de comunidade BGP apropriados com base no serviço ao qual pertencem. A Microsoft marcará prefixos anunciados por meio de emparelhamento público e emparelhamento da Microsoft com valores de comunidade BGP apropriados que indicam a região na qual os prefixos são hospedados. Você pode contar com os valores da Comunidade para fazer decisões de roteamento adequadas para oferecer roteamento ideal. Você pode usar o valor da Comunidade do BGP do Skype for Business online para configurar uma conexão do ExpressRoute somente para o Skype for Business online. Você pode saber mais sobre [os requisitos de roteamento do ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-routing/).
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Cenários de conectividade do ExpressRoute para o Skype for Business Online
<a name="bkNetworkPerf"> </a>

Se você decidiu que o ExpressRoute foi baseado nas recomendações acima para você, aqui estão as recomendações sobre onde e quantas conexões do ExpressRoute você deve obter.
  
### <a name="online-only-deployment---single-site"></a>Implantação somente online-um único site

Se todos os seus usuários usarem o serviço Skype for Business Online e se os seus escritórios estiverem centralizados em um único local físico e você decidir implantar o Azure ExpressRoute, você deve configurar a conexão expressa única entre o site da sua empresa e o [local de emparelhamento do ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)mais próximo.
  
O gráfico a seguir mostra um exemplo desse tipo de implantação. Para este exemplo, a contoso é uma universidade localizada em Orlando, FL. A contoso tem 10.000 membros do corpo docente e estudantes. Os testes da Internet do local para sites do Microsoft Edge mostraram uma perda de pacotes superior a 5% durante horas de classe de pico. Elas decidiram obter uma conexão dedicada com o Microsoft 365 ou o Office 365 usando o ExpressRoute com largura de banda excessiva e para que possam evitar o congestionamento da rede para o Microsoft 365 ou o Office 365 especialmente para tráfego em tempo real do Skype for Business online. Elas se conectam ao Microsoft Cloud por meio do ExpressRoute no site de Atlanta, MeetMe GA.
  
![Site único do ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Implantação somente online – vários sites no mesmo continente

Se a sua empresa estiver usando os serviços do Skype for Business online de vários escritórios na mesma região ou continente, e você optar por implementar o Azure ExpressRoute, é recomendável conectar seu site principal via rota e, opcionalmente, adicionar um emparelhamento de ExpressRoute adicional para outros locais que não atendam aos objetivos de desempenho de rede recomendados.
  
No exemplo a seguir, a contoso é uma empresa de serviços de viagem EUA sediada em Nova York, mas tem outros escritórios nos Estados Unidos. Seus escritórios são interconectados por meio de uma WAN que usa a MPLS para conexão com o Microsoft 365 ou o Office 365. Inicialmente, ele configurou uma conexão expressa do roteador da Internet no Hoboken, Nova Jersey para o site MeetMe Nova York. 
  
Com essa configuração, o tráfego de rede da maioria dos seus sites para a rede da Microsoft (site de borda Nova York) pode atender aos destinos de desempenho de rede de conexão do cliente Skype for Business descritos em [requisitos de desempenho de rede de um cliente Skype for Business para a borda de rede da Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). No entanto, a latência entre os escritórios da costa oeste da Contoso e Nova York está indo pelo 50ms unidirecional. Além disso, Honolulu é o segundo maior Office para contoso, a latência de Honolulu para Nova York excede 80ms unidirecional. Para garantir uma boa qualidade de mídia para os usuários desses escritórios, a Contoso decidiu adicionar uma conexão de costa expressa do oeste entre o site da sua San José e o MeetMe do vale do silício do silício.
  
![O multi-site de roteador expresso no mesmo continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Implantação somente online – vários sites em diferentes continentes

Se todos os seus usuários estiverem usando o serviço Skype for Business Online e se seus escritórios estiverem em vários locais físicos entre vários continentes, se você decidir implantar o Azure ExpressRoute, deverá configurar pelo menos uma conexão ExpressRoute para cada continente entre o site principal de um continente em seu [local de emparelhamento do expressroute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)mais próximo. Dependendo do custo versus benefício, você pode optar por implantar conexões do ExpressRoute adicionais de sites em que os destinos de desempenho de rede não sejam atendidos.
  
No exemplo a seguir, a contoso é uma grande empresa de advocacia corporativa com escritórios em grandes cidades na América do Norte e na Europa. Com base na conexão à Internet e na avaliação de desempenho da rede interna, a Contoso decidiu implantar duas conexões do ExpressRoute na América do Norte e um único circuito do ExpressRoute para todos os seus escritórios europeus.
  
![Rota expressa com vários sites e continentes.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Implantação híbrida

Se você tiver uma implantação do Lync local ou do Skype for Business e optar por implementar uma integração híbrida do Skype for Business Online, recomendamos que, se decidir implantar o Azure ExpressRoute, você precise ter pelo menos uma conexão do ExpressRoute para cada continente do Lync ou do Skype for Business e, pelo menos, uma conexão do ExpressRoute para cada continente com escritórios. Dependendo do custo versus benefício, para cada continente, você pode optar por implantar conexões do ExpressRoute adicionais dos escritórios nos quais os destinos de desempenho de rede não sejam atendidos.
  
Se você tiver uma implantação local do Skype for Business, deverá seguir o guia de [planejamento e implantação do servidor de borda](https://technet.microsoft.com/library/mt346417.aspx). Especificamente, os servidores de borda devem ser atingíveis de fora da sua rede. Isso geralmente é obtido atribuindo um endereço IP público roteável ao servidor de borda ou usando a NAT (conversão de endereços de rede).
  
No exemplo a seguir, a contoso tem uma implantação do Skype for Business Enterprise Voice existente no local. Eles querem migrar os usuários locais para o Microsoft 365 ou os serviços online do Office 365. Eles também decidiram usar uma implantação híbrida para que possam continuar a usar sua infraestrutura PSTN existente para todos os usuários locais e online. O Data Center local da Contoso e os servidores de borda do Skype for Business estão em Chicago. Para a implantação, a Contoso decidiu configurar uma conexão do ExpressRoute entre seu data center de Chicago e o Chicago ExpressRoute. Eles também adicionaram uma conexão do oeste Coast ExpressRoute para atender melhor às suas Honolulu Office.
  
![Rota do ExpressRoute híbrida.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Implantação online com o Cloud Connector Edition

O Skype for Business online Cloud Connector Edition é uma oferta híbrida que consiste em um conjunto de máquinas virtuais compactadas (VMs) que implementam a conectividade PSTN local. Implantando uma topologia mínima do Skype for Business Server em um ambiente virtualizado, você poderá enviar e receber chamadas com telefones fixos e celulares por meio da infraestrutura de voz PSTN local existente.
  
Se você decidir implantar o Azure ExpressRoute e o Cloud Connector Edition, recomendamos que você configure pelo menos uma conexão de rota expressa para cada continente entre o site principal do continente para ele é o [local de emparelhamento do ExpressRoute](https://azure.microsoft.com/documentation/articles/expressroute-locations/)mais próximo. Dependendo do custo versus benefício, para cada continente, você pode optar por implantar conexões ExpressRoute adicionais de sites em que os destinos de desempenho de rede não sejam atendidos.
  
Se você tiver uma implantação local do Skype for Business, deverá seguir o [Guia de planejamento para o Skype for Business Cloud Connector Edition](https://technet.microsoft.com/library/mt605227.aspx). Especificamente, os serviços de borda de acesso e de borda A/V devem receber endereços IP públicos e acessar os centros de dados do Office 365 ou do Office 365.
  
No exemplo a seguir, a contoso é uma empresa de contabilidade européia com presença em alguns dos principais países europeus e cidades. Quando eles se inscrevem no Skype for Business online para todas as suas necessidades de colaboração, eles optaram por colocar um conector de nuvem para cada país e têm um local físico para continuar a usar sua infraestrutura PSTN e contratos de operadora que já existem. Com base nos testes dos seus sites e da Microsoft Network Edge, eles determinaram que uma única conexão do ExpressRoute em Londres ajudará a atender aos destinos de desempenho de rede de conexão do cliente do Skype for Business descritos em [requisitos de desempenho de rede de um cliente Skype for Business para a borda de rede da Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![Conector de nuvem do ExpressRoute One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Abaixo está outra opção de implantação para contoso. Nesse caso, ela decidiu configurar uma conexão do ExpressRoute em cada site em que um conector de nuvem é implantado. 
  
![Conector de nuvem do ExpressRoute dois.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Tópicos relacionados

[ExpressRoute e QoS no Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)

  
 
