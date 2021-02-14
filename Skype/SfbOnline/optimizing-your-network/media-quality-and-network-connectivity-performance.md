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
description: Este tópico define o conjunto de requisitos de desempenho de rede para os serviços do Skype for Business Online e como você pode optar por usar a Internet ou o ExpressRoute para conectividade entre sua rede e o Skype for Business Online com base em sua avaliação da conectividade de rede. Se você decidiu implantar o Azure ExpressRoute para conectividade dedicada com o Microsoft 365 ou o Office 365, este documento também fornece orientações sobre como planejar suas conexões do ExpressRoute em diferentes cenários de implantação do Skype for Business Online.
ms.openlocfilehash: d49dd3e925c71a9e0f2b73bbe364ad4478566cad
ms.sourcegitcommit: 36f7ec432090683aedb77a5bd7856e1b10af2a81
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/08/2020
ms.locfileid: "44164760"
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Qualidade de mídia e desempenho da conectividade de rede no Skype for Business Online

Este tópico define o conjunto de requisitos de desempenho de rede para os serviços do Skype for Business Online e como você pode optar por usar a Internet ou o ExpressRoute para conectividade entre sua rede e o Skype for Business Online com base em sua avaliação da conectividade de rede. Se você decidiu implantar o Azure ExpressRoute para conectividade dedicada com o Microsoft 365 ou o Office 365, este documento também fornece orientações sobre como planejar suas conexões do ExpressRoute em diferentes cenários de implantação do Skype for Business Online.
  
A qualidade Real-Time mídia (áudio, vídeo e compartilhamento de aplicativos) por IP é muito impactada pela qualidade da conectividade de rede de ponta a ponta. Para obter uma excelente qualidade de mídia com o Skype for Business Online, é importante ter uma conexão de alta qualidade entre a rede da sua empresa e o Skype for Business Online. A melhor maneira de conseguir isso é configurar sua rede interna e a conectividade de nuvem com base na capacidade da sua rede para acomodar o volume de pico de tráfego do Skype for Business Online em todas as conexões.
  
O Azure ExpressRoute não é um requisito para os serviços do Microsoft 365 e do Office 365, incluindo o Skype for Business Online. No entanto, o Azure ExpressRoute é uma das opções de implantação disponíveis que ajudarão a garantir que a conectividade com o Microsoft 365 ou o Office 365 atenda aos requisitos de desempenho de rede do Skype for Business e garanta a melhor experiência de qualidade de mídia do Skype for Business Online.
  
> [!TIP]
> Embora este tópico fornece diretrizes gerais de desempenho de rede, a orientação completa para a avaliação da rede está fora do escopo deste documento. Para encontrar uma lista de parceiros do Skype for Business Online que podem ajudá-lo com as medidas de desempenho da rede como parte de uma avaliação completa e completa da rede, visite o [Skype for Business Partner Solutions.](http://partnersolutions.skypeforbusiness.com/) 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisitos de conectividade de rede para o Skype for Business Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Fatores que impactam a qualidade da mídia do Skype for Business Online

Há muitos fatores diferentes que contribuem com a qualidade de mídia do Skype for Business Real-Time Online (áudio, vídeo e compartilhamento de aplicativos) que incluem os dispositivos usados, o ambiente e a conectividade de rede. 
  
#### <a name="devices"></a>Dispositivos

Em uma Real-Time de mídia, dispositivos de captura e renderização de mídia que são usados por todos os participantes, como fones de ouvido e webcams, têm um grande impacto sobre a qualidade geral de áudio e vídeo. Dispositivos de qualidade inferior ou com drivers incorretos produzirão uma qualidade geral inferior de som e imagem. Por outro lado, dispositivos certificados ou de boa qualidade ajudam a eliminar o eco, filtram ruídos, aumentam a resolução de vídeo e reduzem a latência.
  
Embora dispositivos de mídia de áudio e vídeo certificados não sejam necessários, são dispositivos altamente recomendados certificados para o Skype for Business para obter a melhor experiência de mídia. Para ver uma lista de todos os dispositivos certificados pelo Skype for Business, consulte Telefones e [Dispositivos para Skype for Business.](https://technet.microsoft.com/office/dn947482) Você pode usar o Painel de Qualidade de Chamada do [Skype for Business Online,](/microsoftteams/turning-on-and-using-call-quality-dashboard)encontrado no Centro de administração do **Skype for Business,** para verificar se os dispositivos em uso estão funcionando corretamente e monitorar a qualidade da mídia de áudio e vídeo.
  
> [!TIP]
> **Um dispositivo certificado é necessário para a** melhor experiência de qualidade de mídia do Skype for Business.
  
É importante lembrar que todos os dispositivos de mídia, clientes do Skype for Business e servidores do Skype for Business por meio dos quais Real-Time mídia fluem, introduzem uma certa latência. A latência de processamento de dispositivo e software, juntamente com a latência da rede, têm um grande impacto e contribuem com a latência geral de ponta a ponta e a experiência do usuário final.
  
#### <a name="environment"></a>Ambiente.

O ambiente e a área vizinha onde os usuários estão fazendo a reunião e usando dispositivos de áudio e vídeo são outro fator importante para a qualidade. Os usuários que fizerem chamadas em um ambiente barulhento terão áudio com eco, abafado e indistinto. Os usuários que estiverem em um ambiente escuro ou com pouca luz não obterão uma qualidade de imagem clara e viva. Em uma sala de conferência, o local do microfone e do dispositivo de vídeo afeta diretamente a qualidade do som e da imagem que os participantes receberão.
  
Para obter uma imagem mais clara da experiência de áudio e vídeo de um usuário, use o dispositivo de áudio opções de áudio ou dispositivo de vídeo de ferramentas do aplicativo Skype for Business para fazer alterações no dispositivo em uso e personalizar suas  >    >   configurações. 

#### <a name="network"></a>Rede

A qualidade da mídia Real-Time sobre a rede IP é muito impactada pela qualidade da conectividade de rede, mas especialmente pela quantidade de:
  
- **Latência** Esse é o tempo necessário para obter um pacote IP do ponto A para o ponto B na rede. Esse atraso de propagação de rede está essencialmente ligado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional sofrida pelos vários roteadores intermediários. A latência é medida como RTT (tempo de ida e volta) ou de ida e volta.
    
- **Perda de pacote** Isso geralmente é definido como uma porcentagem de pacotes que são perdidos em um determinado período de tempo. A perda de pacote afeta diretamente a qualidade do áudio, desde pacotes perdidos pequenos e individuais que quase não têm impacto, até perdas de estouro de retorno para trás que causam corte total do áudio.
    
- **Tremidação de chegada entre pacotes ou simplesmente tremida** Essa é a alteração média de atraso entre pacotes sucessivos. Os softwares VoIP mais modernos, incluindo o Skype for Business, podem se adaptar a alguns níveis de tremagem por meio do armazenamento em buffer. É somente quando a tremulação excede o buffer que o participante nota os efeitos da tremulação.
    
> [!NOTE]
>  O armazenamento em buffer para tremagem aumentará a latência de ponta a ponta.
  
Com muitas sessões de mídia simultâneas do Skype for Business Real-Time Online, bem como outro tráfego de rede gerado por outros serviços do Microsoft 365 ou do Office 365 e outros aplicativos de negócios, é fundamental garantir uma largura de banda suficiente em todo o caminho de rede que conecta sua rede ao serviço skype for Business Online para evitar congestionamento de rede e garantir uma excelente qualidade de mídia Real-Time mídia (áudio, vídeo e compartilhamento de aplicativos). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementando qoS (Qualidade de Serviço) em redes congestionadas

Além disso, o congestionamento de tráfego em toda a rede afetará muito a qualidade da mídia. Para permitir que pacotes de áudio e vídeo viajem mais rapidamente pela rede e sejam priorizados em relação a outros tráfegos de rede em uma rede congestionada, a QoS (Qualidade do Serviço) pode ser usada para ajudar a fornecer uma ótima experiência do usuário final para comunicações de áudio e vídeo.
  
A QoS fornece uma maneira de atribuir prioridades mais altas a pacotes de rede que estão carregando dados de áudio ou vídeo. Ao atribuir uma prioridade mais alta a esses pacotes, as comunicações de áudio e vídeo provavelmente viajarão pela rede mais rapidamente e com menos interrupções do que sessões de rede que envolvem transferências de arquivos, navegação na Web ou backups de banco de dados. Isso porque os pacotes de rede usados para transferências de arquivos ou backups de banco de dados por padrão são atribuídos como "melhor esforço" como prioridade e o congestionamento da rede não terá um impacto tão grande. Se você não atribuir uma prioridade mais alta aos pacotes de mídia (áudio, vídeo e compartilhamento de aplicativos) e deixá-los também atribuídos como "melhor esforço", eles também serão processados juntamente com todos os outros tráfegos de rede. Dependendo da quantidade de congestionamento de rede, isso poderá acabar em uma experiência geral de qualidade de áudio e vídeo mais baixa para os usuários.
  
É altamente recomendável que você implemente a QoS em sua rede para garantir que o congestionamento de rede dentro da rede não tenha impacto. No entanto, para que isso tenha o máximo impacto, todos os pontos de extremidade de rede devem dar suporte à QoS, o que significa que todos os pontos de extremidade devem honrar a marcação de QoS e a priorização de pacotes. Os serviços do Skype for Business Online honrarão a marcação e a priorização de QoS dentro da rede da Microsoft. No entanto, o tráfego roteado em uma conexão pública, como a Internet da rede da sua empresa para a rede da Microsoft, não preserva as marcações de QoS e a priorização de pacotes. As conexões privadas de sua rede com o Microsoft 365 ou o Office 365 usando o [Azure ExpressRoute](https://azure.microsoft.com/services/expressroute/) oferecem uma solução de implantação que preserva marcações QoS e priorização de pacotes que, por sua vez, aumentarão a qualidade geral de áudio e vídeo para os usuários finais.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisitos de desempenho de rede para se conectar ao Skype for Business Online
<a name="bkNetworkPerf"> </a>

O Skype for Business Real-Time mídia viaja por vários dispositivos diferentes, aplicativos cliente, software de servidor e em diferentes redes. A latência de ponta a ponta Real-Time mídia é a quantidade total de latência introduzida em todos os componentes e segmentos de rede. A qualidade da conexão de rede de ponta a ponta é determinada pelo segmento de rede com a pior qualidade. Este segmento atua como um gargalo para esse tráfego de rede.
  
O diagrama a seguir ilustra o fluxo de áudio único em uma conferência de um participante do Skype for Business para outro.
  
![Fluxo de Chamada do ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
Nesse cenário de conferência, o caminho da mídia consiste nos seguintes segmentos de rede:
  
1. **Conexão do Usuário 1 com a borda da rede da Microsoft** Isso geralmente inclui uma conexão de rede, como WiFi ou Ethernet, a conexão WAN do Usuário 1 com o ponto de saída da Internet (seu dispositivo de borda de rede) e a conexão de Internet de sua borda de rede com a borda de rede da Microsoft.
    
2. **Conexão dentro da rede da Microsoft** Isso está entre o Microsoft Edge e o data center do Skype for Business Online, onde os servidores de Conferência A/V são usados.
    
3. **Conexão dentro do Microsoft Network** Isso está entre o data center do Skype for Business Online e a borda de rede da Microsoft.
    
4. **Conexão da borda de rede da Microsoft com o Usuário 2** Isso inclui a conexão com a Internet de sua borda de rede com a borda de rede da Microsoft, a conexão WAN do Usuário 2 com o ponto de saída da Internet (sua borda de rede) e a conexão de rede, como um WiFi ou Ethernet.
    
O diagrama a seguir mostra a divisão de componentes e segmentos de rede de uma chamada PSTN do Skype for Business Online:
  
![Fluxo de chamada da operadora PSTN do ExpressRoute.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
Em um cenário de chamada PSTN, o caminho da mídia cruza os seguintes segmentos de rede:
  
1. **Conexão de um chamador do** cliente Skype for Business com a borda da Rede da Microsoft Isso geralmente inclui uma conexão de rede, como WiFi ou Ethernet, a conexão WAN do chamador cliente Skype for Business com o ponto de saída da Internet (seu dispositivo de borda de rede) e a conexão com a Internet de sua borda de rede com a borda de rede da Microsoft.
    
2. **Conexão dentro da rede da Microsoft** Isso está entre o Microsoft Edge e o data center do Skype for Business Online, onde um Servidor de Mediação é usado.
    
3. **Conexão dentro do Microsoft Network** Isso está entre o data center do Skype for Business Online e a borda de rede da Microsoft.
    
4. **Conexão entre a Microsoft Network e os parceiros de provedores de serviços PSTN** Essa é a conexão existente para fazer uma chamada PSTN do cliente Skype for Business que está fora da rede da Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisitos de desempenho de rede de um cliente Skype for Business para a borda de rede da Microsoft
<a name="bkSfBClienttoEdge"></a>

Para obter uma ótima qualidade de mídia do Skype for Business, as seguintes metas ou limites de métricas de desempenho de rede são necessários para uma conexão da rede da sua empresa com a borda de rede da Microsoft. Este segmento da rede inclui sua rede interna, que inclui todas as conexões WiFi e Ethernet, qualquer tráfego de site da empresa em uma conexão WAN, por exemplo, MPLS (Multiprotocol Label Switching), bem como as conexões de parceiros da Internet ou do ExpressRoute com a borda de rede da Microsoft.
  
> [!CAUTION]
> **A conectividade entre um cliente Skype for Business na rede da empresa e os serviços do Microsoft 365 ou do Office 365 deve atender aos seguintes requisitos e limites de desempenho de rede a seguir.**
  
|||
|:-----|:-----|
|**Indicador** <br/> |**Destino** <br/> |
|Latência (unidirecional)  <br/> |< 50ms  <br/> |
|Latência (RTT ou Tempo de Ida e Volta)  <br/> |< 100ms  <br/> |
|Perda de pacote de intermitência  <br/> |<10% durante qualquer intervalo de 200ms  <br/> |
|Perda de pacote  <br/> |<1% durante qualquer intervalo de 15s  <br/> |
|Trem tremida de inter-chegada de pacote  <br/> |<30ms durante qualquer intervalo de 15s  <br/> |
|Reordenação de pacotes  <br/> |< 0,05% de pacotes com problemas  <br/> |
   
 **Outros requisitos de meta de desempenho:**
  
- A rede da Microsoft tem mais de 160 locais de borda em todo o mundo. Trabalhamos com os principais ISPs (Provedores de Serviços de Internet) em todo o mundo por meio desses sites de borda. A meta da métrica de latência pressuém que seu site ou sites da empresa e as Bordas da Microsoft estão no mesmo continente.
    
- O site ou os sites da sua empresa para a conexão de borda de rede da Microsoft incluem acesso à rede de primeiro salto, que pode ser WiFi ou outra tecnologia sem fio. 
    
- A meta de desempenho de rede supõe largura de banda adequada e/ou planejamento de qualidade do serviço. Em outras palavras, isso se aplica diretamente ao tráfego de mídia do Skype for Business Real-Time quando a conexão de rede está sob uma carga de pico.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisitos de desempenho de rede da borda de rede para a borda de rede da Microsoft
<a name="bkYourNetworkEdge"> </a>

A seguir estão as metas ou limites de desempenho de rede necessários para a conexão entre a borda de rede e a borda de rede da Microsoft. Este segmento da rede exclui a rede interna ou WAN do cliente e se destina como orientação ao testar o tráfego de rede que é enviado pela Internet ou por meio de uma rede de parceiro do ExpressRoute e também pode ser usado durante a negociação de um SLA (Contrato de Nível de Serviço) de desempenho com seu provedor do ExpressRoute.
  
> [!CAUTION]
> **A conectividade entre a borda de rede da sua empresa com a borda de rede da Microsoft deve atender a estes seguintes requisitos e limites de desempenho de rede.**
  
|||
|:-----|:-----|
|**Indicador** <br/> |**Destino** <br/> |
|Latência (unidirecional)  <br/> |< 30ms  <br/> |
|Latência (RTT)  <br/> |< 60ms  <br/> |
|Perda de pacote de intermitência  <br/> |<1% durante qualquer intervalo de 200 ms  <br/> |
|Perda de pacote  <br/> |<0,1% durante qualquer intervalo de 15s  <br/> |
|Trem tremida de inter-chegada de pacote  <br/> |<15ms durante qualquer intervalo de 15s  <br/> |
|Reordenação de pacotes  <br/> |< 0,01% de pacotes com problemas  <br/> |
   
 **Outros requisitos de meta de desempenho:**
  
- A meta de desempenho requer conexão entre qualquer borda de rede da sua empresa e sua borda de rede da Microsoft mais próxima, para estar no mesmo continente.
    
- A meta de desempenho de rede supõe largura de banda adequada e/ou planejamento de qualidade do serviço. Isso também se aplica ao tráfego de mídia do Skype for Business Real-Time quando a conexão de rede está sob uma carga de pico. Para um planejamento adequado de largura de banda e QoS, consulte [ExpressRoute e QoS no Skype for Business Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
    
## <a name="measuring-network-performance"></a>Medir o desempenho da rede
<a name="bkNetworkPerf"> </a>

Para medir o desempenho real da rede, especialmente para a latência e a perda de pacotes, de qualquer site de rede da empresa a uma borda de rede, você pode usar ferramentas como ping, testar em um conjunto de serviços de media relay do Skype for Business executados a partir do Microsoft Edge e sites de data center. 

>[!NOTE]
> Medir o desempenho da rede por meio de ping (ICMP) não é eficaz. Por esse motivo, a exposição de IP decast abaixo não responderá a solicitações ICMP a partir de janeiro de 2020. Para medir a desempenho da rede de forma eficaz, a Microsoft recomenda a [Ferramenta de Desajuste de Rede.](https://www.microsoft.com/download/details.aspx?id=53885)
  
Para testar conexões de Internet com a rede da Microsoft, é recomendável que você teste em relação aos seguintes VIPs das retransmissão de mídia do Skype for Business. O *ANYCAST VIP*  resolverá um endereço IP de um Media Relay em um site de borda de rede da Microsoft mais próximo do local de teste.
  
||||
|:-----|:-----|:-----|
|**Endereço IP** <br/> |**Tipo** <br/> |**Local** <br/> |
|13.107.8.2  <br/> |Vip  <br/> |IP Anycast em todo o mundo  <br/> |
   
 **Veja algumas recomendações de alto nível a seguir para avaliar o desempenho da rede:**
  
- Você deve avaliar sua rede interna, bem como as conexões com o Microsoft 365 ou o Office 365.
    
- Você deve avaliar e coletar dados para todas as suas redes por um longo período de tempo. Recomendamos que você execute seus testes de desempenho de rede por um mínimo de uma semana, para que você possa ver os padrões de uso para todos os dias e horas úteis. Isso mostrará os horários de pico.
    
- Você deve tirar várias amostras de medidas de desempenho de rede. Recomendamos fazer uma medida a cada 10 minutos de um site da empresa durante todo o período em que você está coletando dados. Para comparar os requisitos de desempenho de rede do Skype for Business Online, pegue o valor de medida do 90º percentil desse conjunto de dados de exemplo. 
    
- Você deve avaliar continuamente o desempenho da rede. O uso da rede varia ao longo do tempo devido a alterações no padrão de uso, novos aplicativos baseados na empresa que usam uma grande quantidade de largura de banda e alterações em locais organizacionais ou físicos da empresa. É importante que você monitore continuamente o desempenho da rede em relação a esses requisitos e metas/limites de desempenho de rede e faça ajustes pontuais para garantir a melhor Real-Time de mídia. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Medir o desempenho da rede usando VMs do Azure
<a name="bkNetworkPerf"> </a>

Em vez de testar nos sites de borda de rede da Microsoft, há soluções de avaliação de rede de clientes e parceiros do Skype for Business que aproveitam a configuração de teste para serviços na nuvem do Microsoft Azure. Nessas soluções, as ferramentas de avaliação de rede testam a latência, a perda de pacotes e a tremida em relação aos pontos de extremidade personalizados definidos como um serviço na nuvem do Azure. Como resultado, o tráfego de rede de teste percorre um segmento de rede adicional, que é a conexão dentro da rede da Microsoft entre as bordas de rede e data centers do Azure que hospeda o serviço de avaliação de rede.
  
Para essas soluções de avaliação de rede com base nos serviços de teste hospedados pelo Azure. Recomendamos executar a avaliação de rede dentro do país e/ou região. Por exemplo, para sites de clientes no leste dos EUA, a avaliação deve ser executada em uma instância de serviço de teste hospedada na região do data center do Azure no leste dos EUA. 
  
Abaixo estão as metas de latência (RTT) para a configuração de avaliação de rede baseada em serviço do Azure. As metas de latência de ida serão metade das metas de RTT correspondentes. As metas de perda de pacote e tremulamento permanecem as mesmas definidas para os testes baseados no Skype Media Relay.
  
|||||
|:-----|:-----|:-----|:-----|
|**Região do cliente** <br/> |**Região do Azure** <br/> |**Sua borda de rede – RTT (Tempo de Ida e Volta) do Azure** <br/> |**Seu Site – Tempo de Ida e Volta do Azure (RTT)** <br/> |
|Central dos EUA  <br/> |Central dos EUA  <br/> |99  <br/> |139  <br/> |
|Leste dos EUA  <br/> |Leste dos EUA  <br/> |86  <br/> |126  <br/> |
|North Central US  <br/> |North Central US  <br/> |97  <br/> |137  <br/> |
|Centro Sul dos EUA  <br/> |Centro Sul dos EUA  <br/> |94  <br/> |134  <br/> |
|Oeste dos EUA  <br/> |Oeste dos EUA  <br/> |94  <br/> |134  <br/> |
|Havaí EUA  <br/> |Oeste dos EUA  <br/> |116  <br/> |156  <br/> |
|Central do Canadá  <br/> |Central do Canadá  <br/> |138  <br/> |178  <br/> |
|Leste do Canadá  <br/> |Leste do Canadá  <br/> |131  <br/> |171  <br/> |
|Norte da Europa  <br/> |Norte da Europa  <br/> |99  <br/> |139  <br/> |
|Europa Ocidental  <br/> |Europa Ocidental  <br/> |95  <br/> |135  <br/> |
|Leste da Ásia  <br/> |Leste da Ásia  <br/> |118  <br/> |158  <br/> |
|Sudeste Asiático  <br/> |Sudeste Asiático  <br/> |97  <br/> |137  <br/> |
|Leste do Japão  <br/> |Leste do Japão  <br/> |111  <br/> |151  <br/> |
|Oeste do Japão  <br/> |Oeste do Japão  <br/> |118  <br/> |158  <br/> |
|Sul do Brasil  <br/> |Sul do Brasil  <br/> |70  <br/> |110  <br/> |
|Leste da Austrália  <br/> |Leste da Austrália  <br/> |124  <br/> |164  <br/> |
|Sudeste da Austrália  <br/> |Sudeste da Austrália  <br/> |124  <br/> |164  <br/> |
|Índia Central  <br/> |Índia Central  <br/> |103  <br/> |143  <br/> |
|Sul da Índia  <br/> |Sul da Índia  <br/> |103  <br/> |143  <br/> |
|Oeste da Índia  <br/> |Oeste da Índia  <br/> |103  <br/> |143  <br/> |
|Leste da China  <br/> |Leste da China  <br/> |120  <br/> |160  <br/> |
|China North  <br/> |China North  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Qualidade da mídia e Rota Expressa
<a name="bkNetworkPerf"> </a>

O Azure ExpressRoute para Microsoft 365 ou Office 365 é uma conexão de rede dedicada para se conectar ao Microsoft 365 ou ao Office 365. Ele oferece aos clientes a capacidade de ter controle sobre o caminho que seu tráfego de rede leva. Eles não precisam mais se preocupar com o roteamento imprevisível que acontece na Internet onde os dados são carregados por operadoras, provedores e ISPs desconhecidos. O tráfego de rede enviado pelo ExpressRoute é enviado diretamente pela rede do parceiro do ExpressRoute para a rede da Microsoft. Isso permite que os clientes tratem o Microsoft 365 ou o Office 365 como se ele estivesse localizado em seu próprio data center fora do site com uma conexão dedicada.
  
O Azure ExpressRoute está disponível para todas as ofertas de licenciamento do Microsoft 365 e do Office 365. No entanto, o complemento Premium do Azure ExpressRoute é necessário para que o Microsoft 365 e o Office 365 habilitam o roteamento global. Os clientes com pelo menos 500 assentos que estão implementando o ExpressRoute podem obter o complemento *Do ExpressRoute Premium* necessário sem custos adicionais.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>O ExpressRoute é necessário para uma boa qualidade de mídia?

O Azure ExpressRoute não é um requisito para obter a melhor qualidade de mídia do Skype for Business Online. No entanto, ela é uma das opções de implantação que ajudam você a garantir que sua conectividade de nuvem atenda às metas ou limites de desempenho de rede do Skype for Business.
  
O Microsoft 365 e o Office 365 são serviços seguros e de alto desempenho que usam a Internet. Continuamos investindo em novos recursos de segurança e nós regionais de borda para melhorar continuamente a segurança e o desempenho. O Azure ExpressRoute não é um requisito para os serviços do Microsoft 365 ou do Office 365, incluindo o Skype for Business Online. A Rota Expressa do Azure é uma das opções de implantação disponíveis que ajudarão a garantir que a conectividade com o Microsoft 365 ou o Office 365 atenda aos requisitos de desempenho de rede do Skype for Business e garanta a melhor experiência de qualidade de mídia do Skype for Business Online.
  
Para a qualidade da mídia do Skype for Business Online, é importante que a conexão entre os sites da sua empresa e as bordas de rede da Microsoft atenda às metas de desempenho em requisitos de desempenho de rede de um cliente [Skype for Business](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) para a borda de rede da Microsoft e que a conexão entre as bordas de rede e as bordas de rede da Microsoft atenda às metas de desempenho de rede de requisitos de desempenho de sua borda de rede para a borda de rede da [Microsoft.](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge)  
  
Também é importante que a conectividade de rede física da sua empresa, incluindo sua rede interna e a capacidade de conectividade de nuvem acomodem o volume máximo de tráfego de mídia. O Azure ExpressRoute é uma das muitas maneiras que ajudará os clientes a garantir que sua conectividade de nuvem do Skype for Business Online atenda a todos esses requisitos de desempenho.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>O ExpressRoute é necessário para o SLA de qualidade de voz?

Não, o ExpressRoute não é necessário para o SLA de qualidade de voz do Skype for Business Online. O [SLA](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) de Qualidade de Voz do Skype for Business Online aplica-se a qualquer chamada qualificada feita por qualquer usuário do serviço de voz do Skype for Business Online dentro da licença e assinatura corretas que permitem que esse usuário faça qualquer tipo de chamada VoIP ou PSTN. Um SLA de qualidade de voz deve incluir que todas as seguintes condições sejam abordadas:
  
- Chamadas de telefones IP certificados pela Microsoft.
    
- Conexões Ethernet com fio.
    
- Problemas de qualidade de voz devido a problemas de Rede da Microsoft.
    
> [!NOTE]
> O SLA de qualidade de voz exclui as chamadas em que a baixa qualidade da chamada é causada por problemas em redes que não são da Microsoft, incluindo o parceiro do ExpressRoute e outras redes. 
  
### <a name="internet-or-azure-expressroute"></a>Internet ou Rota Expressa do Azure?

Antes de tomar uma decisão sobre as opções de conectividade de rede com o Skype for Business Online, os clientes devem avaliar sua rede e a conectividade atual com a Internet com base nos requisitos de desempenho de rede descritos nos requisitos de desempenho de rede para se conectar ao [Skype for Business Online.](media-quality-and-network-connectivity-performance.md#bkNetworkPerf)
  
Se o desempenho da rede na conexão de Internet atual estiver definido para capacidade suficiente durante o horário de pico e atender aos requisitos de desempenho de rede de sites para bordas de rede da Microsoft e de suas bordas de rede para bordas de rede da Microsoft, você poderá continuar a usar sua conectividade de Internet existente para se conectar ao Skype for Business Online.
  
Para sites da empresa em que os requisitos de desempenho de rede não estão sendo atendidos, recomendamos que você primeiro trabalhe com seus provedores de serviços de rede existentes para melhorar o desempenho geral da rede. No entanto, se eles ainda não estão sendo atendidos, usar o Azure ExpressRoute pode ajudar a garantir que sua conectividade de nuvem do Skype for Business Online possa ajudá-lo a atender aos requisitos de desempenho de rede.
  
O Azure ExpressRoute oferece os seguintes benefícios adicionais:
  
- Um SLA (contrato de nível de serviço) sobre a disponibilidade da conexão entre sua rede e a rede da Microsoft. O ExpressRoute tem um SLA de disponibilidade garantido de 99,9%.
    
- Largura de banda planejada e garantida necessária para os serviços do Microsoft 365 e do Office 365. Você pode fazer isso enviando apenas o tráfego do Microsoft 365, do Office 365 ou do Skype for Business usando o ExpressRoute e, em seguida, fazer com que todos os outros tráfegos de Internet acessem outros pontos de saída/entrada da Internet para sua rede.
    
- O ExpressRoute foi projetado para preservar as marcações de QoS do DSCP entre sua rede e a Rede da Microsoft.
    
Para obter mais informações sobre qoS do ExpressRoute e o planejamento de capacidade, consulte [ExpressRoute e QoS no Skype for Business Online.](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d)
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Posso configurar o Azure ExpressRoute apenas para o Skype for Business Online?

Sim, você pode configurar o Azure ExpressRoute para garantir uma excelente conectividade de rede da rede da sua empresa para somente o Skype for Business Online. Isso fornecerá a melhor Real-Time de mídia para seus usuários, mas você poderá continuar se conectando a outros serviços do Microsoft 365 ou do Office 365 pela Internet.
  
O protocolo BGP (Border Gateway Protocol) é um protocolo de roteamento na Internet usado para rotear o tráfego de rede pela Internet. Ele foi projetado para trocar informações de roteamento entre sistemas autônomos (AS) encontrados na Internet. Os valores de comunidades BGP são marcas de atributo que podem ser aplicadas a rotas de entrada ou saída. As comunidades BGP geralmente são usadas para sinalizar para a as receptora qual link de saída usar para chegar a um determinado destino com base em geografia, tipo de serviço ou outros critérios.
  
Com o suporte às comunidades BGP, a Microsoft marcará prefixos e rotas com valores de comunidade BGP apropriados com base no serviço ao que pertencem. A Microsoft marcará prefixos anunciados por meio do paramento público e do peering da Microsoft com valores de comunidade BGP apropriados indicando a região em que os prefixos estão hospedados. Você pode contar com os valores da comunidade para tomar as decisões de roteamento apropriadas para oferecer um roteamento ideal. Você pode usar o valor de comunidade BGP do Skype for Business Online para configurar uma conexão do ExpressRoute somente para o Skype for Business Online. Você pode saber mais sobre os [requisitos de roteamento do ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-routing/)
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Cenários de conectividade do ExpressRoute para Skype for Business Online
<a name="bkNetworkPerf"> </a>

Se você decidiu que o ExpressRoute com base nas recomendações acima é para você, aqui estão as recomendações sobre onde e quantas conexões do ExpressRoute você deve obter.
  
### <a name="online-only-deployment---single-site"></a>Implantação somente online - Site único

Se todos os seus usuários usam o serviço Skype for Business Online e se seus escritórios estão centralizados em torno de um único local físico e você decide implantar o Azure ExpressRoute, você deve configurar uma única conexão do ExpressRoute entre o site da sua empresa para o local de pares mais próximo do [ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-locations/)
  
O gráfico a seguir mostra um exemplo desse tipo de implantação. Neste exemplo, a Contoso é uma universidade localizada em Orlando, FL. A Contoso tem 10.000 membros e alunos do corpo docente. Os testes de Internet de sua localização para sites de borda da Microsoft mostraram perda de pacotes maior que 5% durante o horário de pico da classe. Eles decidiram obter uma conexão dedicada com o Microsoft 365 ou o Office 365 usando o ExpressRoute com largura de banda provisionada para evitar o congestionamento de rede do Microsoft 365 ou do Office 365 especialmente para o tráfego de Real-Time Skype for Business Online. Eles se conectam à nuvem da Microsoft por meio do ExpressRoute no site MeetMe de Atlanta, GA.
  
![Site Único do ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Implantação somente online – Vários sites no mesmo continente

Se sua empresa estiver usando os serviços do Skype for Business Online de vários escritórios na mesma região ou continente e você optar por implementar o Azure ExpressRoute, é recomendável conectar seu site principal por meio do ExpressRoute e, opcionalmente, adicionar outros pares do ExpressRoute para outros locais que não atendem às metas de desempenho de rede recomendadas.
  
No exemplo a seguir, a Contoso é uma empresa de serviços de viagens dos EUA que tem sede em Nova York, mas tem outros escritórios nos Estados Unidos. Seus escritórios são interconectados por meio de uma WAN que usa MPLS para se conectar ao Microsoft 365 ou ao Office 365. Inicialmente, eles configuraram uma conexão do ExpressRoute do roteador de Internet em Hoboken, Nova Jersey para o site MeetMe de Nova York. 
  
Com essa configuração, o tráfego de rede da maioria de seus sites para o Microsoft Network (site de borda de Nova York) pode atender às metas de desempenho de rede de conexão do cliente Skype for Business descritas nos requisitos de desempenho de rede de um cliente Skype for Business para a borda de rede da [Microsoft.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) No entanto, a latência entre os escritórios da costa oeste da Contoso para Nova York está acima de 50ms ida e voltada. Além disso, Honolulu é o segundo maior escritório da Contoso, a latência de Honolulu para Nova York excede 80ms ida e volta. Para garantir uma boa qualidade de mídia para os usuários nesses escritórios, a Contoso decidiu adicionar uma conexão do ExpressRoute da costa oeste entre o site de San Jose e o site MeetMe do ExpressRoute do Vale do Silício.
  
![Multi-site do Roteador Express no mesmo continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Implantação somente online – Vários sites em continentes diferentes

Se todos os seus usuários estão usando o serviço Skype for Business Online e se seus escritórios estão em vários locais físicos em vários continentes, se você decidir implantar o Azure ExpressRoute, deverá configurar pelo menos uma conexão do ExpressRoute para cada continente entre o site principal de cada continente para o seu local de paramento mais próximo do [ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-locations/) Dependendo do custo versus benefício, você pode optar por implantar conexões adicionais do ExpressRoute a partir de sites em que as metas de desempenho de rede não são atendidas.
  
No exemplo a seguir, a Contoso é um grande escritório de direito corporativo com escritórios nas principais cidades da América do Norte e da Europa. Com base na conexão com a Internet e na avaliação de desempenho de rede interna, a Contoso decidiu implantar duas conexões do ExpressRoute na América do Norte e um único circuito do ExpressRoute para todos os escritórios europeus.
  
![Rota Expressa com vários sites e continentes.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Implantação híbrida

Se você tiver uma implantação local do Lync ou skype for Business e optar por implementar uma integração híbrida do Skype for Business Online, recomendamos que, se você decidir implantar o Azure ExpressRoute, precisará ter pelo menos uma conexão do ExpressRoute para cada site de borda local do Lync ou Skype for Business e pelo menos uma conexão do ExpressRoute para cada continente com escritórios. Dependendo do custo versus benefício, para cada continente, você pode optar por implantar conexões adicionais do ExpressRoute de escritórios onde as metas de desempenho de rede não estão sendo atendidas.
  
Se você tiver uma implantação local do Skype for Business, deverá seguir o Guia de Planejamento e Implantação do Servidor de [Borda.](https://technet.microsoft.com/library/mt346417.aspx) Especificamente, os servidores de borda devem estar acessíveis de fora da sua rede. Isso geralmente é obtido atribuindo um endereço IP público roueável ao servidor de borda ou usando NAT (conversão de endereço de rede).
  
No exemplo a seguir, a Contoso tem uma implantação existente no Skype for Business Enterprise Voice. Eles querem migrar usuários locais para os serviços online do Microsoft 365 ou do Office 365. Eles também decidiram usar uma implantação híbrida para que possam continuar a usar sua infraestrutura PSTN existente para todos os usuários locais e online. O data center local da Contoso e os Servidores de Borda do Skype for Business estão em Chicago. Para a implantação, a Contoso decidiu configurar uma conexão do ExpressRoute entre o data center de Chicago e o Chicago ExpressRoute. Eles também adicionaram uma conexão do ExpressRoute da costa oeste para atender melhor ao escritório de Honolulu.
  
![Rota Expressa Híbrida.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Implantação online com o Cloud Connector Edition

O Skype for Business Online Cloud Connector Edition é uma oferta híbrida que consiste em um conjunto de VMs (Máquinas Virtuais) empacotados que implementam a conectividade PSTN local. Ao implantar uma topologia mínima do Skype for Business Server em um ambiente virtualizado, você poderá enviar e receber chamadas com telefones fixos e celulares por meio da infraestrutura de voz PSTN existente no local.
  
Se você decidir implantar o Azure ExpressRoute e o Cloud Connector Edition, recomendamos configurar pelo menos uma conexão de Rota Expressa para cada continente entre o site principal de cada continente e o local de paridade mais próximo do [ExpressRoute.](https://azure.microsoft.com/documentation/articles/expressroute-locations/) Dependendo do custo versus benefício, para cada continente, você pode optar por implantar conexões adicionais do ExpressRoute de sites onde as metas de desempenho de rede não estão sendo atendidas.
  
Se você tiver uma implantação local do Skype for Business, deverá seguir o Guia de Planejamento do [Skype for Business Cloud Connector Edition.](https://technet.microsoft.com/library/mt605227.aspx) Especificamente, os serviços de Borda do Access e A/V Edge devem ter endereços IP públicos e data centers acessíveis do Microsoft 365 ou do Office 365.
  
No exemplo a seguir, a Contoso é uma empresa de contabilidade europeia com presença em alguns dos principais países e cidades europeias. Ao se inscrever no Skype for Business Online para todas as suas necessidades de colaboração, eles decidiram colocar um Cloud Connector para cada país com um local físico para continuar a usar sua infraestrutura PSTN e contratos de operadora que já existem. Com base em seus testes de todos os seus sites e da borda de rede da Microsoft, eles determinaram que uma única conexão do ExpressRoute em Londres ajudará a atender às metas de desempenho de rede de conexão do cliente Skype for Business descritas nos requisitos de Desempenho de Rede de um cliente Skype for Business para a borda de rede da [Microsoft.](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge)
  
![Conector de Nuvem do ExpressRoute One.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
Veja a seguir outra opção de implantação para a Contoso. Nesse caso, eles decidiram configurar uma conexão do ExpressRoute em cada site onde um Cloud Connector é implantado. 
  
![Conector de Nuvem Do ExpressRoute Dois.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Tópicos relacionados

[ExpressRoute e QoS no Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)

  
 
