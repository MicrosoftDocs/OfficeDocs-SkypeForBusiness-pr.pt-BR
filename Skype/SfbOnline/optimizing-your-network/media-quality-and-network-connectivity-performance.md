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
description: Este tópico define o conjunto de requisitos de desempenho de rede para serviços Skype for Business Online e como você pode optar por usar a Internet ou o ExpressRoute para conectividade entre sua rede e o Skype for Business Online com base em sua avaliação da conectividade de rede. Se você decidiu implantar o Azure ExpressRoute para conectividade dedicada ao Microsoft 365 ou ao Office 365, este documento também fornece orientações sobre como planejar suas conexões ExpressRoute em diferentes cenários de implantação Skype for Business Online.
ms.openlocfilehash: 1ab00ad969b7de6432607abfdd0b9a7d4adaa579ca7274eedb98890291a615d5
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/05/2021
ms.locfileid: "54326677"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Qualidade de mídia e desempenho da conectividade de rede no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

Este tópico define o conjunto de requisitos de desempenho de rede para serviços Skype for Business Online e como você pode optar por usar a Internet ou o ExpressRoute para conectividade entre sua rede e o Skype for Business Online com base em sua avaliação da conectividade de rede. Se você decidiu implantar o Azure ExpressRoute para conectividade dedicada ao Microsoft 365 ou ao Office 365, este documento também fornece orientações sobre como planejar suas conexões ExpressRoute em diferentes cenários de implantação Skype for Business Online.
  
A qualidade da mídia Real-Time (áudio, vídeo e compartilhamento de aplicativos) sobre IP é muito impactada pela qualidade da conectividade de rede de ponta a ponta. Para obter uma excelente qualidade de mídia com o Skype for Business Online, é importante ter uma conexão de alta qualidade entre a rede da sua empresa e o Skype for Business Online. A melhor maneira de conseguir isso é configurar sua rede interna e a conectividade de nuvem com base na capacidade da sua rede para acomodar o volume de pico de tráfego do Skype for Business Online em todas as conexões.
  
O Azure ExpressRoute não é um requisito para serviços Microsoft 365 e Office 365, incluindo Skype for Business Online. No entanto, o Azure ExpressRoute é uma das opções de implantação disponíveis que ajudarão a garantir que a conectividade com o Microsoft 365 ou o Office 365 atenda aos requisitos de desempenho de rede do Skype for Business e garanta a melhor experiência de qualidade de mídia Skype for Business Online.
  
> [!TIP]
> Embora este tópico fornece diretrizes gerais de desempenho de rede, as diretrizes completas para avaliação de rede estão fora do escopo deste documento. Para encontrar uma lista de parceiros Skype for Business Online que podem ajudá-lo com as medições de desempenho da rede como parte de uma avaliação completa e completa da rede, visite [Skype for Business Partner Solutions.](http://partnersolutions.skypeforbusiness.com/) 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisitos de conectividade de rede para Skype for Business Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Fatores que impactam Skype for Business qualidade da mídia online

Há muitos fatores diferentes que contribuem para Skype for Business qualidade de mídia do Real-Time Online (áudio, vídeo e compartilhamento de aplicativos) que incluem os dispositivos usados, o ambiente e a conectividade de rede. 
  
#### <a name="devices"></a>Dispositivos

Em uma Real-Time de mídia, a captura de mídia e a renderização de dispositivos usados por todos os participantes, como fones de ouvido e câmeras da Web, têm um grande impacto na qualidade geral de áudio e vídeo. Dispositivos de qualidade inferior ou com drivers incorretos produzirão uma qualidade geral inferior de som e imagem. Por outro lado, dispositivos certificados ou de boa qualidade ajudam a eliminar o eco, filtram ruídos, aumentam a resolução de vídeo e reduzem a latência.
  
Embora os dispositivos de mídia de áudio e vídeo certificados não sejam necessários, são dispositivos altamente recomendados certificados para Skype for Business para a experiência de mídia mais ideal. Para ver uma lista de todos os Skype for Business certificados, consulte [Telefones e Dispositivos para Skype for Business](../../SfbPartnerCertification/certification/devices-ip-phones.md). Você pode usar o Painel Skype for Business qualidade de chamada online [,](/microsoftteams/turning-on-and-using-call-quality-dashboard)encontrado no centro de administração do **Skype for Business,** para verificar se os dispositivos em uso estão funcionando corretamente e monitorar a qualidade da mídia de áudio e vídeo.
  
> [!TIP]
> **Um dispositivo certificado é necessário para** a melhor experiência de qualidade Skype for Business mídia.
  
É importante lembrar que todos os dispositivos de mídia, clientes Skype for Business e servidores Skype for Business por meio dos quais Real-Time de mídia fluem, introduzem alguma latência. A latência de processamento de dispositivos e softwares, juntamente com a latência da rede, têm um grande impacto e contribuem para a latência geral de ponta a ponta e a experiência do usuário final.
  
#### <a name="environment"></a>Ambiente.

O ambiente e a área vizinha onde os usuários estão fazendo a reunião e usando dispositivos de áudio e vídeo são outro fator importante para a qualidade. Os usuários que fizerem chamadas em um ambiente barulhento terão áudio com eco, abafado e indistinto. Os usuários que estiverem em um ambiente escuro ou com pouca luz não obterão uma qualidade de imagem clara e viva. Em uma sala de conferência, o local do microfone e do dispositivo de vídeo afeta diretamente a qualidade do som e da imagem que os participantes receberão.
  
Para obter uma imagem mais clara da experiência de áudio e vídeo de um usuário, use o dispositivo de áudio ou dispositivo de vídeo de opções de ferramentas do aplicativo Skype for Business para fazer alterações no dispositivo em uso e personalizar suas  >    >   configurações. 

#### <a name="network"></a>Rede

A qualidade da mídia Real-Time pela rede IP é muito impactada pela qualidade da conectividade de rede, mas especialmente pela quantidade de:
  
- **Latência** Este é o tempo necessário para obter um pacote IP do ponto A ao ponto B na rede. Esse atraso de propagação de rede está essencialmente ligado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional sofrida pelos vários roteadores intermediários. A latência é medida como tempo de ida e volta (RTT).
    
- **Perda de pacote** Isso é geralmente definido como uma porcentagem de pacotes perdidos em uma determinada janela de tempo. A perda de pacotes afeta diretamente a qualidade do áudio, desde pacotes perdidos pequenos e individuais que quase não têm impacto, até perdas de estouro de back-to-back que causam o corte total do áudio.
    
- **Tremidos de chegada entre pacotes ou simplesmente tremidos** Essa é a alteração média de atraso entre pacotes sucessivos. A maioria dos softwares VoIP modernos, incluindo Skype for Business pode se adaptar a alguns níveis de tremedeira por meio do buffer. É somente quando a tremulação excede o buffer que o participante nota os efeitos da tremulação.
    
> [!NOTE]
>  O buffer para tremedeira aumentará a latência de ponta a ponta.
  
Com muitas sessões de mídia simultâneas do Skype for Business Online Real-Time, bem como outros tráfegos de rede gerados por outros serviços Microsoft 365 ou Office 365 e outros aplicativos de negócios, garantir que haja largura de banda suficiente em todo o caminho de rede que conecta sua rede ao serviço do Skype for Business Online é fundamental para evitar congestionamento de rede e garantir excelente qualidade de mídia Real-Time mídia (áudio, vídeo e compartilhamento de aplicativo). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementando a QoS (Qualidade de Serviço) em redes congestionadas

Além disso, o congestionamento de tráfego em uma rede afetará muito a qualidade da mídia. Para permitir que os pacotes de áudio e vídeo viajem mais rapidamente pela rede e sejam priorizados em relação a outros tráfegos de rede em uma rede congestionada, a QoS (Qualidade do Serviço) pode ser usada para ajudar a fornecer uma experiência de usuário final ideal para comunicações de áudio e vídeo.
  
O QoS fornece uma maneira de atribuir prioridades maiores a pacotes de rede que estão carregando dados de áudio ou vídeo. Ao atribuir uma prioridade maior a esses pacotes, as comunicações de áudio e vídeo provavelmente viajarão pela rede mais rapidamente e com menos interrupção do que sessões de rede envolvendo coisas como transferências de arquivos, navegação na Web ou backups de banco de dados. Isso porque os pacotes de rede usados para transferências de arquivos ou backups de banco de dados por padrão são atribuídos "melhor esforço" como prioridade e o congestionamento de rede não terá um impacto tão grande. Se você não atribuir uma prioridade maior aos pacotes de mídia (áudio, vídeo e compartilhamento de aplicativos) e deixá-los também atribuídos como "melhor esforço", eles também serão processados juntamente com todos os outros tráfegos de rede. Dependendo da quantidade de congestionamento de rede, isso poderá acabar em uma experiência de qualidade de áudio e vídeo mais baixa para seus usuários.
  
É altamente recomendável implementar a QoS em sua rede para garantir que o congestionamento de rede em sua rede não tenha impacto. No entanto, para que isso tenha o impacto máximo, todos os pontos de extremidade de rede devem dar suporte à QoS, o que significa que todos os pontos de extremidade devem honrar a marcação de QoS e a priorização de pacotes. Skype for Business Os serviços online honram a marcação de QoS e a priorização na rede da Microsoft. No entanto, o tráfego roteado por uma conexão pública, como a Internet, da rede da sua empresa para a rede da Microsoft, não preserva as marcações de QoS e a priorização de pacotes. As conexões privadas de sua rede para Microsoft 365 ou Office 365 usando o [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) oferecem uma solução de implantação que preserva as marcações de QoS e a priorização de pacotes que, por sua vez, aumentarão a qualidade geral de áudio e vídeo para os usuários finais.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisitos de desempenho de rede para se conectar ao Skype for Business Online
<a name="bkNetworkPerf"> </a>

Skype for Business Real-Time mídia percorre vários dispositivos diferentes, aplicativos cliente, software de servidor e redes diferentes. A latência de ponta a ponta da mídia Real-Time é a quantidade total de latência introduzida em todos os componentes e segmentos de rede. A qualidade da conexão de rede de ponta a ponta é determinada pelo segmento de rede com a pior qualidade. Esse segmento atua como um a gargalo para esse tráfego de rede.
  
O diagrama a seguir ilustra o fluxo de áudio de uma conferência de um Skype for Business para outro.
  
![ExpressRoute Call Flow.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
Neste cenário de conferência, o caminho de mídia consiste nos seguintes segmentos de rede:
  
1. **Conexão do Usuário 1 à borda da rede da Microsoft** Isso geralmente inclui uma conexão de rede, como WiFi ou Ethernet, a conexão WAN do Usuário 1 ao ponto de saída da Internet (seu dispositivo de Borda de rede) e a conexão com a Internet de sua Borda de rede para o Microsoft Network Edge.
    
2. **Conexão na rede da Microsoft** Isso é entre o Microsoft Edge para Skype for Business Online, onde os servidores de Conferência A/V são usados.
    
3. **Conexão no Microsoft Network** Isso é entre o data center Skype for Business Online e o Microsoft Network Edge.
    
4. **Conexão da borda de rede da Microsoft com o Usuário 2** Isso inclui a conexão com a Internet do Edge de rede para o Microsoft Network Edge, a conexão WAN do Usuário 2 ao ponto de saída da Internet (sua Borda de rede) e a conexão de rede, como wi-fi ou ethernet.
    
O diagrama a seguir mostra a divisão de componentes e segmentos de rede de uma chamada PSTN Skype for Business Online:
  
![Chamada de operadora PSTN expressRoute Flow.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
Em um cenário de chamada PSTN, o caminho de mídia cruza os seguintes segmentos de rede:
  
1. **Conexão de um Skype for Business de cliente para a borda da Microsoft Network** Isso geralmente inclui uma conexão de rede, como WiFi ou Ethernet, a conexão WAN do chamador de cliente Skype for Business para o ponto de saída da Internet (seu dispositivo de Borda de Rede) e a conexão com a Internet da borda da rede para o Microsoft Network Edge.
    
2. **Conexão na rede da Microsoft** Isso é entre o Microsoft Edge para Skype for Business Online, onde um Servidor de Mediação é usado.
    
3. **Conexão no Microsoft Network** Isso é entre o data center Skype for Business Online e o Microsoft Network Edge.
    
4. **Conexão entre a Microsoft Network e os parceiros do provedor de serviços PSTN** Essa é a conexão que existe para colocar uma chamada PSTN do cliente Skype for Business que está fora da rede da Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisitos de desempenho de rede de um cliente Skype for Business para o Microsoft Network Edge
<a name="bkSfBClienttoEdge"></a>

Para obter Skype for Business de mídia, as seguintes metas ou limites de desempenho de rede são necessários para uma conexão da rede da sua empresa com o Microsoft Network Edge. Esse segmento da rede inclui sua rede interna, isso inclui todas as conexões WiFi e Ethernet, qualquer tráfego de site para site da empresa em uma conexão WAN, por exemplo, MPLS (Multiprotocol Label Switching), bem como as conexões de parceiros Internet ou ExpressRoute com o Microsoft Network Edge.
  
> [!CAUTION]
> **A conectividade entre um cliente Skype for Business em sua rede da empresa para serviços Microsoft 365 ou Office 365 deve atender aos seguintes requisitos e limites de desempenho de rede.**
  
|||
|:-----|:-----|
|**Indicador** <br/> |**Destino** <br/> |
|Latência (unidirecional)  <br/> |< 50ms  <br/> |
|Latência (RTT ou Hora de Ida e volta)  <br/> |< 100ms  <br/> |
|Perda de pacote de intermitência  <br/> |<10% durante qualquer intervalo de 200ms  <br/> |
|Perda de pacote  <br/> |<1% durante qualquer intervalo de 15s  <br/> |
|Tremeamento de inter-chegada do pacote  <br/> |<30ms durante qualquer intervalo de 15s  <br/> |
|Reordenação de pacotes  <br/> |< 0,05% de pacotes com problemas  <br/> |
   
 **Outros requisitos de destino de desempenho:**
  
- A rede da Microsoft tem mais de 160 locais de Borda em todo o mundo. Trabalhamos com os principais Provedores de Serviços da Internet (ISPs) em todo o mundo por meio desses sites de Borda. O destino da métrica de latência supõe que seu site ou sites da empresa e as Bordas da Microsoft estão no mesmo continente.
    
- Seu site da empresa ou sites para a conexão do Microsoft Network Edge incluem acesso à rede de primeiro salto, que pode ser WiFi ou outra tecnologia sem fio. 
    
- O destino do desempenho da rede pressuimos largura de banda adequada e/ou qualidade do planejamento do serviço. Em outras palavras, isso se aplica diretamente Skype for Business Real-Time tráfego de mídia quando a conexão de rede está sob uma carga de pico.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisitos de desempenho de rede do Edge de rede para o Microsoft Network Edge
<a name="bkYourNetworkEdge"> </a>

A seguir estão os destinos ou limites de desempenho de rede necessários para a conexão entre o Edge de rede e o Microsoft Network Edge. Esse segmento da rede exclui a rede interna ou WAN do cliente e se destina como orientação ao testar o tráfego de rede enviado pela Internet ou por meio de uma rede de parceiros expressRoute e também pode ser usado ao negociar um Contrato de Nível de Serviço de desempenho (SLA) com seu provedor ExpressRoute.
  
> [!CAUTION]
> **A conectividade entre a borda da rede da sua empresa e a borda da rede da Microsoft deve atender aos seguintes requisitos e limites de desempenho de rede.**
  
|||
|:-----|:-----|
|**Indicador** <br/> |**Destino** <br/> |
|Latência (unidirecional)  <br/> |< 30ms  <br/> |
|Latência (RTT)  <br/> |< 60ms  <br/> |
|Perda de pacote de intermitência  <br/> |<1% durante qualquer intervalo de 200 ms  <br/> |
|Perda de pacote  <br/> |<0,1% durante qualquer intervalo de 15s  <br/> |
|Tremeamento de inter-chegada do pacote  <br/> |<15ms durante qualquer intervalo de 15s  <br/> |
|Reordenação de pacotes  <br/> |< 0,01% de pacotes com problemas  <br/> |
   
 **Outros requisitos de destino de desempenho:**
  
- O destino de desempenho requer conexão entre qualquer borda de rede da sua empresa e seu Microsoft network Edge mais próximo, para estar no mesmo continente.
    
- O destino do desempenho da rede pressuimos largura de banda adequada e/ou qualidade do planejamento do serviço. Isso também se aplica Skype for Business Real-Time tráfego de mídia quando a conexão de rede está sob uma carga de pico. Para um planejamento adequado de largura de banda e QoS, consulte [ExpressRoute e QoS no Skype for Business Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>Medir o desempenho da rede
<a name="bkNetworkPerf"> </a>

Para medir o desempenho real da rede, especialmente para latência e perda de pacotes, de qualquer site de rede da empresa para uma Borda de rede, você pode usar ferramentas como ping, testar em um conjunto de serviços de retransmissão de mídia Skype for Business executados a partir dos sites do Microsoft Edge e do data center. 

>[!NOTE]
> Medir o desempenho da rede por meio de ping (ICMP) não é eficaz. Por esse motivo, a exposição de IP de qualquercast abaixo para de responder a solicitações ICMP a partir de janeiro de 2020. Para medir o desempenho da rede efetivamente, a Microsoft recomenda a [Ferramenta de Proteção de Rede](https://www.microsoft.com/download/details.aspx?id=53885).
  
Para testar conexões com a Internet na rede da Microsoft, é recomendável testar os seguintes VIPs das retransmissão de mídia Skype for Business de mídia. O *VIP anycast*  resolverá para um endereço IP de um Retransmissão de Mídia em um site de Borda de rede da Microsoft mais próximo do local de teste.
  
||||
|:-----|:-----|:-----|
|**Endereço IP** <br/> |**Tipo** <br/> |**Local** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |IP anycast em todo o mundo  <br/> |
   
 **Aqui estão algumas recomendações de alto nível a seguir para avaliar o desempenho da rede:**
  
- Você deve avaliar sua rede interna, bem como as conexões para Microsoft 365 ou Office 365.
    
- Você deve avaliar e coletar dados de todas as suas redes por um longo período de tempo. Recomendamos que você execute seus testes de desempenho de rede por um mínimo de uma semana, para que você possa ver padrões de uso para todos os dias e horas úteis. Isso mostrará os horários de pico.
    
- Você deve levar vários exemplos de medidas de desempenho de rede. Recomendamos fazer uma medida a cada 10 minutos de um site da empresa durante todo o período de tempo em que você está coletando dados. Para comparar os requisitos Skype for Business desempenho da rede online, leve o valor de medida de percentil 90 deste conjunto de dados de exemplo. 
    
- Você deve avaliar continuamente o desempenho da rede. A utilização da rede varia ao longo do tempo devido a alterações de padrão de uso, novos aplicativos baseados em empresa que usam uma grande quantidade de largura de banda e alterações nos locais organizacionais ou físicos da empresa. É importante que você monitore continuamente o desempenho da rede em relação a esses requisitos de desempenho de rede e metas/limites e faça ajustes em tempo há tempo para garantir a melhor qualidade de mídia Real-Time. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Medir o desempenho da rede usando VMs do Azure
<a name="bkNetworkPerf"> </a>

Em vez de testar nos sites do Microsoft Network Edge, há soluções de avaliação de rede de clientes e parceiros Skype for Business que aproveitam a configuração de teste para serviços na Microsoft Azure nuvem. Nessas soluções, as ferramentas de avaliação de rede testam latência, perda de pacotes e tremência em relação a pontos de extremidade personalizados definidos como um serviço na nuvem do Azure. Como resultado, o tráfego de rede de teste percorre um segmento de rede adicional, que é a conexão dentro da rede da Microsoft entre as bordas da rede e os data centers do Azure que hospedam o serviço de avaliação de rede.
  
Para essas soluções de avaliação de rede com base nos serviços de teste hospedados pelo Azure. Recomendamos executar a avaliação de rede no país e/ou região. Por exemplo, para sites de clientes no leste dos EUA, a avaliação deve ser realizada em uma instância de serviço de teste hospedada na região do data center leste dos EUA do Azure. 
  
Abaixo estão as metas de latência (RTT) para a configuração de avaliação de rede baseada em serviço do Azure. Os destinos de latência de ida serão metade dos destinos RTT correspondentes. As metas de perda e tremulação de pacotes permanecem as mesmas definidas para o teste baseado Skype Media Relay.
  
|||||
|:-----|:-----|:-----|:-----|
|**Região do cliente** <br/> |**Região do Azure** <br/> |**Borda de rede - Hora de Ida e volta do Azure (RTT)** <br/> |**Seu Site - Hora de Ida e Volta do Azure (RTT)** <br/> |
|Central US  <br/> |Central US  <br/> |99  <br/> |139  <br/> |
|Leste dos EUA  <br/> |Leste dos EUA  <br/> |86  <br/> |126  <br/> |
|Norte-Central dos EUA  <br/> |Norte-Central dos EUA  <br/> |97  <br/> |137  <br/> |
|Centro-Sul dos EUA  <br/> |Centro-Sul dos EUA  <br/> |94  <br/> |134  <br/> |
|Oeste dos EUA  <br/> |Oeste dos EUA  <br/> |94  <br/> |134  <br/> |
|Havaí EUA  <br/> |Oeste dos EUA  <br/> |116  <br/> |156  <br/> |
|Central do Canadá  <br/> |Central do Canadá  <br/> |138  <br/> |178  <br/> |
|Leste do Canadá  <br/> |Leste do Canadá  <br/> |131  <br/> |171  <br/> |
|Norte da Europa  <br/> |Norte da Europa  <br/> |99  <br/> |139  <br/> |
|Europa Ocidental  <br/> |Europa Ocidental  <br/> |95  <br/> |135  <br/> |
|Leste asiático  <br/> |Leste asiático  <br/> |118  <br/> |158  <br/> |
|Sudeste Asiático  <br/> |Sudeste Asiático  <br/> |97  <br/> |137  <br/> |
|Leste do Japão  <br/> |Leste do Japão  <br/> |111  <br/> |151  <br/> |
|Japão Ocidental  <br/> |Japão Ocidental  <br/> |118  <br/> |158  <br/> |
|Brasil Sul  <br/> |Brasil Sul  <br/> |70  <br/> |110  <br/> |
|Austrália Leste  <br/> |Austrália Leste  <br/> |124  <br/> |164  <br/> |
|Austrália Sudeste  <br/> |Austrália Sudeste  <br/> |124  <br/> |164  <br/> |
|Índia Central  <br/> |Índia Central  <br/> |103  <br/> |143  <br/> |
|Sul da Índia  <br/> |Sul da Índia  <br/> |103  <br/> |143  <br/> |
|Índia Ocidental  <br/> |Índia Ocidental  <br/> |103  <br/> |143  <br/> |
|China East  <br/> |China East  <br/> |120  <br/> |160  <br/> |
|China North  <br/> |China North  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Qualidade de mídia e ExpressRoute
<a name="bkNetworkPerf"> </a>

O Azure ExpressRoute para Microsoft 365 ou Office 365 é uma conexão de rede dedicada para se conectar a Microsoft 365 ou Office 365. Ele oferece aos clientes a capacidade de ter controle sobre o caminho que o tráfego de rede leva. Eles não precisam mais se preocupar com o roteamento imprevisível que acontece na Internet onde os dados são carregados por operadoras, provedores e ISPs desconhecidos. O tráfego de rede enviado pelo ExpressRoute é enviado diretamente pela rede do parceiro ExpressRoute para a rede da Microsoft. Isso permite que os clientes tratem Microsoft 365 ou Office 365 como se ele estivesse localizado em seu próprio data center fora do site com uma conexão dedicada.
  
O Azure ExpressRoute está disponível para todas as Microsoft 365 e Office 365 de licenciamento. No entanto, o complemento do Azure ExpressRoute Premium é necessário para Microsoft 365 e Office 365 para habilitar o roteamento global. Os clientes com pelo menos 500 assentos que estão implementando o ExpressRoute podem obter o Complemento *expressRoute Premium* necessário sem custo adicional.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>O ExpressRoute é necessário para uma boa qualidade de mídia?

O Azure ExpressRoute não é um requisito para obter a melhor qualidade de mídia Skype for Business Online. No entanto, é uma das opções de implantação que ajudam você a garantir que sua conectividade na nuvem atenda aos limites Skype for Business de desempenho da rede.
  
Microsoft 365 e Office 365 são serviços seguros e de alto desempenho que usam a Internet. Continuamos investindo em novos recursos de segurança e nós regionais de Borda para melhorar continuamente a segurança e o desempenho. O Azure ExpressRoute não é um requisito para serviços Microsoft 365 ou Office 365, incluindo Skype for Business Online. O Azure ExpressRoute é uma das opções de implantação disponíveis que ajudarão a garantir que a conectividade com o Microsoft 365 ou o Office 365 atenda aos requisitos de desempenho de rede do Skype for Business e garanta a melhor experiência de qualidade de mídia Skype for Business Online.
  
Para a qualidade da mídia online do Skype for Business, é importante que a conexão entre os sites da sua empresa e as Bordas da rede da Microsoft atenda às metas de desempenho nos requisitos de desempenho de rede de um cliente Skype for Business para [o Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) Network Edge e que a conexão entre as bordas da rede e as bordas da rede da Microsoft atenda aos objetivos de desempenho nos requisitos de desempenho da rede, desde o Edge da rede até o Microsoft Network [Edge.](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)  
  
Também é importante que a conectividade de rede física da sua empresa, incluindo sua capacidade interna de conectividade de rede e nuvem, acomode o volume de tráfego de mídia de pico. O Azure ExpressRoute é uma das muitas maneiras que ajudarão os clientes a garantir Skype for Business conectividade de nuvem online atendam a todos esses requisitos de desempenho.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute é necessário para SLA de qualidade de voz?

Não, o ExpressRoute não é necessário para Skype for Business SLA de qualidade de voz online. O [Skype for Business SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) de Qualidade de Voz Online se aplica a qualquer chamada qualificada feita por qualquer usuário do serviço de voz online Skype for Business dentro da licença e assinatura corretas que permitem que o usuário faça qualquer tipo de chamada VoIP ou PSTN. Um SLA de qualidade de voz deve incluir que todas as seguintes condições são abordadas:
  
- Chamadas de telefones IP certificados pela Microsoft.
    
- Conexões Ethernet com fio.
    
- Problemas de qualidade de voz devido a problemas do Microsoft Network.
    
> [!NOTE]
> O SLA de qualidade de voz exclui as chamadas em que a baixa qualidade da chamada é causada por problemas em redes que não são da Microsoft, incluindo o parceiro ExpressRoute e outras redes. 
  
### <a name="internet-or-azure-expressroute"></a>Internet ou Azure ExpressRoute?

Antes de tomar uma decisão sobre as opções de conectividade de rede para o Skype for Business Online, os clientes devem avaliar sua rede e a conectividade atual com a Internet com base nos requisitos de desempenho de rede descritos em Requisitos de desempenho de rede para se conectarem [ao Skype for Business Online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Se o desempenho da rede na conexão de Internet atual estiver definido para capacidade suficiente durante o horário de pico e atender aos requisitos de desempenho de rede de sites para Bordas de rede da Microsoft e de bordas de rede para Bordas de rede da Microsoft, você poderá continuar a usar sua conectividade existente com a Internet para se conectar ao Skype for Business Online.
  
Para sites da empresa em que os requisitos de desempenho de rede não estão sendo atendidos, recomendamos que você primeiro trabalhe com seus provedores de serviços de rede existentes para melhorar o desempenho geral da rede. No entanto, se eles ainda não estão sendo atendidos, o uso do Azure ExpressRoute pode ajudar a garantir que Skype for Business conectividade de nuvem online possa ajudá-lo a atender aos requisitos de desempenho da rede.
  
O Azure ExpressRoute oferece os seguintes benefícios adicionais:
  
- Um contrato de nível de serviço (SLA) sobre a disponibilidade da conexão entre sua rede e a rede da Microsoft. ExpressRoute tem um SLA de disponibilidade garantido de 99,9%.
    
- Largura de banda planejada e garantida necessária para Microsoft 365 e Office 365 serviços. Você pode fazer isso enviando apenas Microsoft 365, Office 365 ou Skype for Business usando o ExpressRoute e, em seguida, fazer com que todos os outros tráfegos da Internet acessem outros pontos de entrada/saída da Internet para sua rede.
    
- O ExpressRoute foi projetado para preservar as marcações de QoS DSCP entre sua rede e a Microsoft Network.
    
Para obter mais informações sobre o QoS do ExpressRoute e o planejamento de capacidade, consulte [ExpressRoute e QoS em Skype for Business Online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Posso configurar o Azure ExpressRoute somente Skype for Business Online?

Sim, você pode configurar o Azure ExpressRoute para garantir uma excelente conectividade de rede da rede da sua empresa para somente Skype for Business Online. Isso fornecerá a melhor Real-Time de mídia para seus usuários, mas você poderá continuar se conectando a outros serviços Microsoft 365 ou Office 365 pela Internet.
  
O Protocolo de Gateway de Borda (BGP) é um protocolo de roteamento na Internet que é usado para rotear o tráfego de rede pela Internet. Ele foi projetado para trocar informações de roteamento entre sistemas autônomos (AS) encontradas na Internet. Os valores de comunidades BGP são marcas de atributo que podem ser aplicadas a rotas de entrada ou saída. As comunidades BGP geralmente são usadas para sinalizar para o receptor AS qual link de saída usar para chegar a um determinado destino com base em geografia, tipo de serviço ou outros critérios.
  
Com o suporte às comunidades BGP, a Microsoft marcará prefixos e rotas com valores de comunidade BGP apropriados com base no serviço ao que pertencem. A Microsoft marcará prefixos anunciados por meio do paramento público e da Microsoft com valores de comunidade BGP apropriados indicando a região em que os prefixos estão hospedados. Você pode contar com os valores da comunidade para tomar decisões de roteamento apropriadas para oferecer um roteamento ideal. Você pode usar o valor da comunidade Skype for Business BGP Online para configurar uma conexão ExpressRoute somente para Skype for Business Online. Você pode saber mais em [Requisitos de roteamento expressRoute.](/azure/expressroute/expressroute-routing)
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Cenários de conectividade expressRoute para Skype for Business Online
<a name="bkNetworkPerf"> </a>

Se você decidiu que o ExpressRoute com base nas recomendações acima é para você, aqui estão as recomendações sobre onde e quantas conexões ExpressRoute você deve obter.
  
### <a name="online-only-deployment---single-site"></a>Implantação somente online - Site único

Se todos os seus usuários usam o serviço Skype for Business Online e se seus escritórios estão centralizados em torno de um único local físico e você decide implantar o Azure ExpressRoute, você deve configurar uma única conexão ExpressRoute entre seu site da empresa para o local de paração [expressRoute](/azure/expressroute/expressroute-locations)mais próximo.
  
O gráfico a seguir mostra um exemplo desse tipo de implantação. Para este exemplo, Contoso é uma universidade localizada em Orlando, FL. A Contoso tem 10.000 professores e alunos. Os testes da Internet de sua localização para sites de borda da Microsoft mostraram perda de pacotes superior a 5% durante o horário de pico da classe. Eles decidiram obter uma conexão dedicada ao Microsoft 365 ou Office 365 usando o ExpressRoute com largura de banda sobre provisionada para que eles possam evitar o congestionamento de rede para Microsoft 365 ou Office 365 Skype for Business especialmente para o tráfego Real-Time Online. Eles se conectam à nuvem da Microsoft por meio do ExpressRoute no site Atlanta, GA MeetMe.
  
![Site Único expressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Implantação somente online - Vários sites no mesmo continente

Se sua empresa estiver usando serviços do Skype for Business Online de vários escritórios na mesma região ou continente e você optar por implementar o Azure ExpressRoute, é recomendável conectar seu site principal por meio do ExpressRoute e, opcionalmente, adicionar paring expressRoute adicional para outros locais que não atendem às metas de desempenho de rede recomendadas.
  
No exemplo a seguir, a Contoso é uma empresa de serviços de viagens dos EUA com sede em Nova York, mas que tem outros escritórios nos Estados Unidos. Seus escritórios são interconectados por meio de uma WAN que usa o MPLS para se conectar a Microsoft 365 ou Office 365. Inicialmente, eles configuraram uma conexão ExpressRoute de seu roteador da Internet em Hoboken, Nova Jérsei para o site MeetMe de Nova York. 
  
Com essa configuração, o tráfego de rede da maioria de seus sites para o Microsoft Network (site do New York Edge) pode atender aos destinos de desempenho da rede de conexão do cliente Skype for Business descritos em Requisitos de desempenho de rede de um cliente Skype for Business para o [Microsoft Network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). No entanto, a latência entre os escritórios da costa oeste da Contoso para Nova York tem mais de 50ms de ida e volta. Além disso, Honolulu é o segundo maior escritório da Contoso, a latência de Honolulu para Nova York excede 80ms de ida e volta. Para garantir uma boa qualidade de mídia para os usuários nesses escritórios, a Contoso decidiu adicionar uma conexão expressRoute da costa oeste entre seu site de San Jose e o site meetMe do Silicon Valley ExpressRoute.
  
![Roteador Expresso Multi-site no mesmo continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Implantação somente online - Vários sites em diferentes continentes

Se todos os seus usuários estão usando o serviço online do Skype for Business e se seus escritórios estão em vários locais físicos em vários continentes, se você decidir implantar o Azure ExpressRoute, deverá configurar pelo menos uma conexão ExpressRoute para cada continente entre o site principal de cada continente para seu local de paração [expressRoute](/azure/expressroute/expressroute-locations)mais próximo. Dependendo do custo versus benefício, você pode optar por implantar conexões expressRoute adicionais de sites onde os destinos de desempenho da rede não são atendidos.
  
No exemplo a seguir, a Contoso é uma grande empresa de advocacia corporativa com escritórios nas principais cidades da América do Norte e europa. Com base em sua conexão com a Internet e na avaliação de desempenho de rede interna, a Contoso decidiu implantar duas conexões ExpressRoute na América do Norte e um único circuito ExpressRoute para todos os escritórios europeus.
  
![ExpressRoute com vários sites e continentes.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Implantação híbrida

Se você tiver uma implantação local do Lync ou Skype for Business e optar por implementar uma integração híbrida do Skype for Business Online, recomendamos que, se você decidir implantar o Azure ExpressRoute, precisará ter pelo menos uma conexão ExpressRoute para cada site de Borda local do Lync ou Skype for Business e pelo menos uma conexão ExpressRoute para cada continente com escritórios. Dependendo do custo versus benefício, para cada continente, você pode optar por implantar conexões expressRoute adicionais de escritórios onde os destinos de desempenho da rede não estão sendo atendidos.
  
Se você tiver uma implantação Skype for Business local, siga o Guia de Planejamento e Implantação do Servidor de [Borda.](../../SfbServer/plan-your-deployment/edge-server-deployments/edge-server-deployments.md) Especificamente, os servidores de Borda devem ser acessíveis de fora da rede. Geralmente, isso é obtido atribuindo um endereço IP público instável ao servidor de Borda ou usando NAT (conversão de endereço de rede).
  
No exemplo a seguir, a Contoso tem uma implantação local Skype for Business Enterprise Voice local. Eles querem migrar usuários locais para serviços Microsoft 365 ou Office 365 online. Eles também decidiram usar uma implantação híbrida para que eles possam continuar a usar sua infraestrutura PSTN existente para todos os usuários locais e online. O data center local da Contoso e os Skype for Business de Borda estão em Chicago. Para sua implantação, a Contoso decidiu configurar uma conexão ExpressRoute entre o data center de Chicago e o Chicago ExpressRoute. Eles também adicionaram uma conexão expressRoute da costa oeste para atender melhor seu escritório em Honolulu.
  
![ExpressRoute Híbrido.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Implantação online com o Cloud Connector Edition

Skype for Business O Online Cloud Connector Edition é uma oferta híbrida que consiste em um conjunto de VMs (Máquinas Virtuais) empacotados que implementam a conectividade PSTN local. Ao implantar uma topologia mínima Skype for Business Server em um ambiente virtualizado, você poderá enviar e receber chamadas com telefones fixos e celulares por meio da infraestrutura de voz PSTN local existente.
  
Se você decidir implantar o Azure ExpressRoute e o Cloud Connector Edition, recomendamos configurar pelo menos uma conexão de Rota Expressa para cada continente entre o site principal de cada continente e o local de paração [expressRoute](/azure/expressroute/expressroute-locations)mais próximo. Dependendo do custo versus benefício, para cada continente, você pode optar por implantar conexões expressRoute adicionais de sites onde os destinos de desempenho da rede não estão sendo atendidos.
  
Se você tiver uma implantação Skype for Business local, siga o Guia de Planejamento [para](../../SfbServer/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition.md)Skype for Business Cloud Connector Edition . Especificamente, os serviços de Borda de Acesso e Borda A/V devem ser atribuídos a endereços IP públicos e data centers Microsoft 365 ou Office 365 acessíveis.
  
No exemplo a seguir, a Contoso é uma empresa de contabilidade europeia com presença em alguns dos principais países e cidades europeus. Quando se ins inscreverem no Skype for Business Online para todas as suas necessidades de colaboração, eles decidiram colocar um Cloud Connector para cada país que têm um local físico para continuar a usar sua infraestrutura PSTN e contratos de operadora que já existem. Com base em seus testes de todos os sites e do Microsoft Network Edge, eles determinaram que uma única conexão ExpressRoute em Londres ajudará a atender aos destinos de desempenho da rede de conexão do cliente Skype for Business descritos em Requisitos de Desempenho de Rede de um cliente Skype for Business para o [Microsoft Network Edge](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![ExpressRoute Cloud Connector One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Abaixo está outra opção de implantação para Contoso. Nesse caso, eles decidiram configurar uma conexão ExpressRoute em cada site onde um Cloud Connector é implantado. 
  
![ExpressRoute Cloud Connector Two.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Tópicos relacionados

[ExpressRoute e QoS no Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)

  
