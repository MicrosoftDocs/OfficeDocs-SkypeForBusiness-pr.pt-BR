---
title: Qualidade de mídia e o desempenho da conectividade de rede
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: mpottier, dougand
ms.topic: article
ms.assetid: 5fe3e01b-34cf-44e0-b897-b0b2a83f0917
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Optimization
description: Este tópico define o conjunto de requisitos de desempenho de rede para Skype para serviços corporativos Online e como você pode optar por usar o Internet ou ExpressRoute para a conectividade entre a rede e Skype para Business Online com base em sua avaliação da rede conectividade. Se você tiver decidido implantar ExpressRoute do Windows Azure para conectividade dedicada para o Office 365, este documento também fornece orientação sobre como planejar suas conexões ExpressRoute em diferente Skype para cenários de implantação de negócios Online.
ms.openlocfilehash: a3af3ac55d39089f2fa6146c93a92fcd174a8cb6
ms.sourcegitcommit: a0d3e7a177fcd0667ab0d7d0e904f4053b09a92d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/18/2018
---
# <a name="media-quality-and-network-connectivity-performance-in-skype-for-business-online"></a>Qualidade de mídia e o desempenho de conectividade de rede no Skype para negócios on-line

Este tópico define o conjunto de requisitos de desempenho de rede para Skype para serviços corporativos Online e como você pode optar por usar o Internet ou ExpressRoute para a conectividade entre a rede e Skype para Business Online com base em sua avaliação da rede conectividade. Se você tiver decidido implantar ExpressRoute do Windows Azure para conectividade dedicada para o Office 365, este documento também fornece orientação sobre como planejar suas conexões ExpressRoute em diferente Skype para cenários de implantação de negócios Online.
  
A qualidade de mídia em tempo real (áudio, vídeo e compartilhamento de aplicativos) sobre IP significativamente é afetada pela qualidade da conectividade de rede de ponta a ponta. Para obter uma excelente qualidade de mídia com o Skype for Business Online, é importante ter uma conexão de alta qualidade entre a rede da sua empresa e o Skype for Business Online. A melhor maneira de conseguir isso é configurar sua rede interna e a conectividade de nuvem com base na capacidade da sua rede para acomodar o volume de pico de tráfego do Skype for Business Online em todas as conexões.
  
Azure ExpressRoute não é um requisito para os serviços do Office 365 incluindo Skype para Business Online. No entanto, o Azure ExpressRoute é uma da implantação opções disponíveis que ajudará a garantir que a conectividade com o Office 365 atende o Skype para requisitos de desempenho de rede de negócios e garante o Skype mais ideal para mídia Business Online qualidade de experiência.
  
> [!TIP]
> Embora este tópico fornece orientações de desempenho de rede geral, uma orientação completa para avaliação da rede estiver fora do escopo deste documento. Para encontrar uma lista de Skype para parceiros de negócios Online que podem ajudá-lo com as medições de desempenho de rede como parte de uma avaliação abrangente e completo da rede, visite [Skype para soluções de parceiros de negócios](http://partnersolutions.skypeforbusiness.com/). 
  
## <a name="network-connectivity-requirements-to-skype-for-business-online"></a>Requisitos de conectividade de rede para Skype para Business Online

### <a name="factors-that-impact-skype-for-business-online-media-quality"></a>Fatores que afetam o Skype para qualidade de mídia Business Online

Há vários fatores diferentes que contribuem para o Skype para qualidade de mídia (áudio, vídeo e aplicativos compartilhamento) de negócios real-time Online que incluem os dispositivos que são usados, o ambiente e a conectividade de rede. 
  
#### <a name="devices"></a>Dispositivos

Em uma sessão de mídia em tempo real, mídia captura e o processamento de dispositivos que são usados por todos os participantes, como headsets e webcams tem um grande impacto na qualidade de vídeo e áudio geral. Dispositivos de qualidade inferior ou com drivers incorretos produzirão uma qualidade geral inferior de som e imagem. Por outro lado, dispositivos certificados ou de boa qualidade ajudam a eliminar o eco, filtram ruídos, aumentam a resolução de vídeo e reduzem a latência.
  
Embora o certificado para dispositivos de mídia de áudio e vídeo não são necessários, é altamente recomendável dispositivos certified para Skype for Business para a experiência de mídia ideal. Para obter uma lista de todos os Skype para negócios dispositivos de certificados, consulte [telefones e dispositivos para Skype para negócios](https://technet.microsoft.com/en-us/office/dn947482). Pode usar o [Skype para negócios Online chamada qualidade painel](../using-call-quality-in-your-organization/turning-on-and-using-call-quality-dashboard.md), encontrado no **Skype para Business admin center**, para verificar dispositivos em uso estão funcionando corretamente e monitorar a qualidade da mídia de áudio e vídeo.
  
> [!TIP]
> **Um dispositivo de certificados é necessário para o Skype mais ideal para a experiência de qualidade de mídia de negócios**.
  
É importante lembrar-se de que quaisquer dispositivos de mídia, Skype para clientes corporativos e Skype para servidores de negócios por meio do quais fluxos de mídia em tempo real, introduzem alguma quantidade de latência. O dispositivo e o software de processamento de latência, juntamente com a latência de rede, tem um impacto excelente em e contribuem para a latência geral de ponta a ponta e a experiência do usuário final.
  
#### <a name="environment"></a>Ambiente

O ambiente e a área vizinha onde os usuários estão fazendo a reunião e usando dispositivos de áudio e vídeo são outro fator importante para a qualidade. Os usuários que fizerem chamadas em um ambiente barulhento terão áudio com eco, abafado e indistinto. Os usuários que estiverem em um ambiente escuro ou com pouca luz não obterão uma qualidade de imagem clara e viva. Em uma sala de conferência, o local do microfone e do dispositivo de vídeo afeta diretamente a qualidade do som e da imagem que os participantes receberão.
  
Para obter uma imagem mais nítida de uso de áudio e vídeo de experiência do usuário do Skype para o aplicativo de negócios **Ferramentas** > **Opções** > **Dispositivo de áudio** ou **Dispositivo de vídeo** para fazer alterações para o dispositivo em uso e personalizar as configurações de TI. Você também pode verificar a qualidade de áudio de uma chamada ao clicar em **Verificar qualidade da chamada**. Quando você clica em **Verificar Qualidade da Chamada**, é possível reportar a qualidade e os problemas encontrados na chamada de teste.
  
![Testing audio in the Skype for Business client.](../images/1730a71e-a09d-4702-8eb6-ef1346a091fa.png)
  
#### <a name="network"></a>Rede

A qualidade da mídia em tempo real pela rede IP é afetada significativamente a qualidade da conectividade de rede, mas especialmente pela quantidade de:
  
- **Latência** Esse é o tempo que leva para obter um pacote IP do ponto A ponto b na rede. Esse atraso de propagação de rede essencialmente está vinculado à distância física entre os dois pontos e a velocidade da luz, incluindo a sobrecarga adicional tomada por vários roteadores entre si. Latência é medida em tempo de unidirecional ou de ida e volta (tempo de resposta).
    
- **Perda de pacote** Geralmente, isso é definido como uma porcentagem de pacotes que são perdidos em uma determinada janela de tempo. Perda de pacotes diretamente afeta a qualidade do áudio — de pequeno, indivíduo perdido pacotes tendo quase sem impacto, perdas em frente e verso intermitente que causam recorte áudio completa.
    
- **Tremulação de chegada de pacote entre ou simplesmente tremulação** Esta é a média alteração em atraso entre pacotes sucessivos. Mais moderno software de VoIP, incluindo Skype para negócios pode se adaptar a alguns níveis de tremulação por meio de armazenamento em buffer. É somente quando a tremulação excede o armazenamento em buffer que um participante perceberá os efeitos de variação.
    
> [!NOTE]
>  Armazenamento em buffer para tremulação aumentará a latência de ponta a ponta.
  
Com muitos Skype simultâneas para sessões de mídia em tempo real Online de negócios, bem como outros tráfegos de rede gerados por outros serviços do Office 365 e outros aplicativos de negócios, certificando-se de que haja largura de banda suficiente sobre o caminho de rede inteira que conecta-se sua rede para o Skype para Business Online service é fundamental para evitar congestionamento de rede e certifique-se de mídia excelente qualidade de mídia em tempo real (áudio, vídeo e aplicativos compartilhamento). 
  
#### <a name="implementing-quality-of-service-qos-across-congested-networks"></a>Implementando o Quality of Service (QoS) entre congestionamento de redes

Além disso, congestionamento de tráfego em uma rede muito afetará a qualidade da mídia. Para permitir que os pacotes de áudio e vídeos para a rede mais rápida de viagens e prioridade sobre outros tráfegos de rede em uma rede de congestionamento, Quality of Service (QoS) pode ser usado para ajudar a fornecer uma experiência de usuário final ideal para comunicações de áudio e vídeos.
  
QoS fornece uma maneira de atribuir prioridades mais altas aos pacotes de rede que são transmitir dados de áudio ou vídeos. Atribuindo uma prioridade mais alta para esses pacotes, as comunicações de áudio e vídeos tendem viajam através da rede rapidamente e com menos interrupção, que as sessões de rede envolvendo coisas como transferências de arquivos, navegação da web ou backups de banco de dados. Isso ocorre porque os pacotes de rede usado para transferências de arquivo ou backups de banco de dados por padrão são atribuídos "melhor esforço" como uma prioridade e congestionamento da rede não terá como grande impacto. Se você não atribuir uma prioridade mais alta aos pacotes de mídia (áudio, vídeo e aplicativos compartilhamento) e deixá-los também atribuída como "melhor esforço", eles também serão processados, juntamente com todos os outros tráfegos de rede. Dependendo da quantidade de congestionamento da rede, isso potencialmente terminarão em uma experiência geral de áudio e vídeo de qualidade inferior para seus usuários.
  
É altamente recomendável que você implemente o QoS em sua rede para certificar-se de que o congestionamento da rede dentro de sua rede não terá um impacto. No entanto, para que isso ter um impacto máximo, todos os pontos de extremidade de redes devem suportar QoS, indicando que todos os pontos de extremidade devem honram marcação de QoS e priorização de pacote. Skype para serviços corporativos Online respeitar marcação de QoS e priorização de dentro da rede da Microsoft. No entanto, o tráfego que é roteado por uma conexão pública como a Internet da rede da sua empresa à rede Microsoft não preserva as marcas de QoS e na priorização de pacote. Conexões particulares da sua rede para o Office 365 usando o [Windows Azure ExpressRoute](https://azure.microsoft.com/en-us/services/expressroute/) oferecem uma solução de implantação que preserva as marcas de QoS e priorização de pacote que por sua vez aumentarão geral áudio e a qualidade de vídeo para seus usuários finais.
  
## <a name="network-performance-requirements-to-connect-to-skype-for-business-online"></a>Requisitos de desempenho de rede para conectar Skype para Business Online
<a name="bkNetworkPerf"> </a>

Skype para a mídia em tempo real de negócios viaja por meio de muitos dispositivos diferentes, aplicativos de cliente, o software de servidor e nas redes diferentes. A latência de ponta a ponta de mídia em tempo real é a quantidade total de latência introduzida em todos os componentes e segmentos de rede. A qualidade da conexão de rede de ponta a ponta é determinada pelo segmento de rede com a qualidade pior. Esse segmento atua como um afunilamento para esse tráfego de rede.
  
O diagrama a seguir ilustra o fluxo de áudio unidirecional em uma conferência do um Skype de participante de negócios para outro.
  
![Fluxo de chamadas ExpressRoute.](../images/c026e8e5-ba09-42c0-9e03-60fbfda1cb02.png)
  
Neste cenário de conferência, o caminho de mídia consiste nas seguintes segmentos de rede:
  
1. **Conexão do usuário 1 até a borda da rede da Microsoft** Geralmente, isso inclui uma conexão de rede como WiFi ou Ethernet, a conexão WAN de usuário 1 para o ponto de saída da Internet (seu dispositivo de borda de rede) e a conexão de Internet da sua rede de borda Microsoft Network borda.
    
2. **Conexão dentro da rede da Microsoft** Isso é entre o Edge Microsoft para Skype para centro de dados corporativos Online, onde A / V Conferencing servidores são usados.
    
3. **Conexão dentro da rede da Microsoft** Isso é entre o Skype para data center Business Online e Microsoft network borda.
    
4. **Conexão de borda da rede Microsoft ao usuário 2** Isso inclui a conexão de Internet da sua rede de borda Microsoft Network borda, a conexão WAN do usuário 2 para o ponto de saída da Internet (sua rede borda) e a conexão de rede como um WiFi ou uma Ethernet.
    
O diagrama a seguir mostra a divisão dos componentes e segmentos de rede de um Skype para chamada PSTN Online de negócios:
  
![Fluxo de chamadas do PSTN ExpressRoute operadora.](../images/768a88df-c8a9-4171-a158-565a698f0193.png)
  
Em um cenário de chamada PSTN, o caminho de mídia cruza os segmentos de rede a seguir:
  
1. **Conexão de um Skype para o chamador do cliente de negócios até a borda da rede da Microsoft** Geralmente, isso inclui uma conexão de rede como WiFi ou Ethernet, a conexão WAN do Skype para o chamador do cliente de negócios para o ponto de saída da Internet (seu dispositivo de borda de rede) e a conexão de Internet da sua rede de borda Microsoft Network borda.
    
2. **Conexão dentro da rede da Microsoft** Isso é entre o Edge Microsoft para Skype para on-line do Business data center, onde um servidor de mediação é usado.
    
3. **Conexão dentro da rede da Microsoft** Isso é entre o Skype para data center Business Online e Microsoft network borda.
    
4. **Conexão entre o Microsoft Network e os parceiros de provedores de serviços PSTN** Esta é a conexão que existe para colocar uma chamada PSTN a partir do Skype para clientes corporativos que está fora da rede da Microsoft.
    
### <a name="network-performance-requirements-from-a-skype-for-business-client-to-microsoft-network-edge"></a>Requisitos de desempenho de rede a partir de um Skype para o cliente de negócios para Microsoft network borda
<a name="bkSfBClienttoEdge"></a>

Para melhor Skype para qualidade de mídia de negócios, as metas de métricas de desempenho de rede ou os limites a seguir são necessários para uma conexão de rede da sua empresa à rede Microsoft borda. Esse segmento de rede inclui a sua rede interna, isso inclui todas as conexões WiFi e Ethernet, o tráfego de qualquer site a site empresa através de uma conexão WAN, por exemplo Multiprotocol Label alternando (MPLS), bem como o parceiro de Internet ou ExpressRoute conexões com o Microsoft network borda.
  
> [!CAUTION]
> **Conectividade entre um Skype para o cliente de negócios em sua rede de empresa para serviços do Office 365 deve atender a esses requisitos de desempenho de rede seguintes e limites.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Destino** <br/> |
|Latência (uma maneira)  <br/> |< 50 ms  <br/> |
|Latência (tempo de resposta ou tempo de ida e volta)  <br/> |< 100 ms  <br/> |
|Perda de pacotes de intermitência  <br/> |<10% durante qualquer intervalo de 200 ms  <br/> |
|Perda de pacote  <br/> |<1% durante qualquer intervalo de 15 s  <br/> |
|Tremulação de entre chegada de pacotes  <br/> |<30 ms durante qualquer intervalo de 15 s  <br/> |
|Reordenar de pacotes  <br/> |<0,05% de pacotes com problemas  <br/> |
   
 **Outros requisitos de destino de desempenho:**
  
- Microsoft network tem mais de 160 locais de borda em todo o mundo. Trabalhamos com principais da Internet (provedores) em todo o mundo por meio desses sites de borda. O destino de métricas de latência pressupõe o site da sua empresa ou sites e Edges Microsoft do mesmo continente.
    
- O site da empresa ou sites para a conexão de borda de rede do Microsoft incluem primeiro salto acesso à rede, que pode ser WiFi ou outra tecnologia sem fio. 
    
- O destino de desempenho de rede pressupõe largura de banda adequada e/ou a qualidade do serviço de planejamento. Em outras palavras, isso se aplica diretamente ao Skype para o tráfego de mídia em tempo real de negócios quando a conexão de rede está sob uma carga de pico.
    
### <a name="network-performance-requirements-from-your-network-edge-to-microsoft-network-edge"></a>Requisitos de desempenho de rede da sua rede de borda Microsoft Network borda
<a name="bkYourNetworkEdge"> </a>

Estas são as metas de desempenho de rede ou limites necessários para a conexão entre a borda de rede e borda da rede da Microsoft. Esse segmento de rede exclui a rede interna do cliente ou WAN e destina-se como orientação ao testar o tráfego de rede que é enviado pela Internet ou por meio de uma rede de parceiros ExpressRoute e também pode ser usado ao negociar um desempenho Nível de contrato serviço (SLA) com seu provedor de ExpressRoute.
  
> [!CAUTION]
> **Conectividade entre a rede da sua empresa borda até a borda da rede Microsoft deve atender a esses requisitos de desempenho de rede seguintes e limites.**
  
|||
|:-----|:-----|
|**Métrica** <br/> |**Destino** <br/> |
|Latência (uma maneira)  <br/> |< 30 ms  <br/> |
|Latência (tempo de resposta)  <br/> |< 60 ms  <br/> |
|Perda de pacotes de intermitência  <br/> |<1% durante qualquer intervalo de 200 ms  <br/> |
|Perda de pacote  <br/> |<0,1% durante qualquer intervalo de 15 s  <br/> |
|Tremulação de entre chegada de pacotes  <br/> |<15 ms durante qualquer intervalo de 15 s  <br/> |
|Reordenar de pacotes  <br/> |<0,01% de pacotes com problemas  <br/> |
   
 **Outros requisitos de destino de desempenho:**
  
- O destino de desempenho exige conexão entre qualquer um dos borda da rede da empresa e sua rede de Microsoft mais próximo borda, estejam no mesmo continente.
    
- O destino de desempenho de rede pressupõe largura de banda adequada e/ou a qualidade do serviço de planejamento. Isso também é aplicado ao Skype para o tráfego de mídia em tempo real de negócios quando a conexão de rede está sob uma carga de pico. Para o planejamento de QoS e largura de banda adequada, consulte [ExpressRoute e QoS em Skype para negócios Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
    
## <a name="measuring-network-performance"></a>Medir o desempenho de rede
<a name="bkNetworkPerf"> </a>

Para medir o desempenho de rede reais, especialmente para latência e perda de pacotes, de qualquer site de rede de empresa para uma rede de borda, você pode usar ferramentas como o ping, testado em relação a um conjunto de Skype para serviços de retransmissão de mídia corporativos em execução do Microsoft Edge e dados sites do centro. 
  
Para testar conexões com a Internet para a rede Microsoft, é recomendável que você teste em relação a seguintes VIPs do Skype para retransmissões de mídia de negócios. O *VIP de difusão* serão resolvidos para um endereço IP de uma retransmissão de mídia em um site de borda de rede Microsoft que é mais próximo da localização de teste.
  
||||
|:-----|:-----|:-----|
|**Endereço IP** <br/> |**Tipo** <br/> |**Local** <br/> |
|13.107.8.2  <br/> |VIP  <br/> |IP de difusão todo o mundo  <br/> |
   
 **Aqui estão algumas recomendações de alto níveis a seguir para avaliar o desempenho da rede:**
  
- Você deve avaliar sua rede interna, bem como as conexões com o Office 365.
    
- Você deve avaliar e coletar dados para todas as redes durante um longo período de tempo. É recomendável para realizar seus testes de desempenho de rede para um mínimo de uma semana, para que você possa ver os padrões de uso para todos os dias úteis e horas. Isso mostrará os horários de pico.
    
- Você deve levar vários exemplos das medições de desempenho de rede. É recomendável fazer a cada 10 minutos de medição de um site da empresa durante todo o período de tempo de que coleta de dados. Para comparar o Skype para requisitos de desempenho de rede Business Online, tirar o valor de medida de percentil 90 deste conjunto de dados de exemplo. 
    
- Continuamente você deve avaliar o desempenho da rede. Utilização da rede varia ao longo do tempo devido às alterações de padrão de uso, novos aplicativos baseados no enterprise que usam uma grande quantidade de largura de banda e alterações aos locais físicos ou organizacional empresa. É importante que você continuamente monitorar o desempenho da sua rede contra esses requisitos de desempenho de rede e as metas/limites e faça ajustes em tempo hábil para garantir a qualidade de mídia em tempo real mais ideal. 
    
## <a name="measuring-network-performance-using-azure-vms"></a>Medir o desempenho de rede usando as máquinas virtuais do Windows Azure
<a name="bkNetworkPerf"> </a>

Em vez de testes com os sites de borda de rede da Microsoft, existem soluções de avaliação de rede do Skype para clientes de negócios e os parceiros que otimizam o teste de instalação para os serviços em nuvem Microsoft Azure. Essas soluções, as ferramentas de avaliação de rede testar latência, perda de pacote em tremulação contra os pontos de extremidade personalizados configurado como um serviço na nuvem Azure. Como resultado, o tráfego de rede de teste é encaminhado por meio de um segmento de rede adicionais, que é a conexão dentro da rede Microsoft entre as bordas de rede e centros de dados de Azure que hospeda o serviço de avaliação de rede.
  
Para esses rede soluções de avaliação com base no Windows Azure serviços hospedados do testes. Recomendamos a execução da avaliação de rede dentro do país e/ou a região. Por exemplo, para sites de cliente nos EUA east, a avaliação deve ser executada em relação a uma instância de serviço de teste hospedada na Leste do Azure região de centro de dados dos EUA. 
  
Abaixo está a latência destinos (tempo de resposta) para a instalação de avaliação de rede serviço Azure, com base. As metas de latência unidirecional será metade dos destinos de tempo de resposta correspondentes. As metas de tremulação e de perda de pacotes permanece o mesmo aquelas definidas para retransmissão de mídia do Skype com base em testes.
  
|||||
|:-----|:-----|:-----|:-----|
|**Região do cliente** <br/> |**Região do Azure** <br/> |**Sua rede borda - tempo de ida e volta do Windows Azure (RTT)** <br/> |**Seu Site - tempo de ida e volta Azure (tempo de resposta)** <br/> |
|Centro dos EUA  <br/> |Centro dos EUA  <br/> |99  <br/> |139  <br/> |
|Leste EUA  <br/> |Leste EUA  <br/> |86  <br/> |126  <br/> |
|Centro Norte dos EUA  <br/> |Centro Norte dos EUA  <br/> |97  <br/> |137  <br/> |
|Centro Sul dos EUA  <br/> |Centro Sul dos EUA  <br/> |94  <br/> |134  <br/> |
|Centro-Oeste dos Estados Unidos  <br/> |Centro-Oeste dos Estados Unidos  <br/> |94  <br/> |134  <br/> |
|Havaí dos EUA  <br/> |Centro-Oeste dos Estados Unidos  <br/> |116  <br/> |156  <br/> |
|Central do Canadá  <br/> |Central do Canadá  <br/> |138  <br/> |178  <br/> |
|Sudeste do Canadá  <br/> |Sudeste do Canadá  <br/> |131  <br/> |171  <br/> |
|Europa do Norte  <br/> |Europa do Norte  <br/> |99  <br/> |139  <br/> |
|Europa Ocidental  <br/> |Europa Ocidental  <br/> |95  <br/> |135  <br/> |
|Sudeste Asiático  <br/> |Sudeste Asiático  <br/> |118  <br/> |158  <br/> |
|Sudeste Asiático  <br/> |Sudeste Asiático  <br/> |97  <br/> |137  <br/> |
|Sudeste do Japão  <br/> |Sudeste do Japão  <br/> |111  <br/> |151  <br/> |
|Japão Oeste  <br/> |Japão Oeste  <br/> |118  <br/> |158  <br/> |
|Brasil Sul  <br/> |Brasil Sul  <br/> |70  <br/> |110  <br/> |
|Leste da Austrália  <br/> |Leste da Austrália  <br/> |124  <br/> |164  <br/> |
|Sudeste da Austrália  <br/> |Sudeste da Austrália  <br/> |124  <br/> |164  <br/> |
|Índia central  <br/> |Índia central  <br/> |103  <br/> |143  <br/> |
|Índia Sul  <br/> |Índia Sul  <br/> |103  <br/> |143  <br/> |
|Centro-Oeste Índia  <br/> |Centro-Oeste Índia  <br/> |103  <br/> |143  <br/> |
|Sudeste China  <br/> |Sudeste China  <br/> |120  <br/> |160  <br/> |
|Norte da China  <br/> |Norte da China  <br/> |120  <br/> |160  <br/> |
   
## <a name="media-quality-and-expressroute"></a>Qualidade de mídia e ExpressRoute
<a name="bkNetworkPerf"> </a>

ExpressRoute Azure para o Office 365 é uma conexão de rede dedicada para conectar-se ao Office 365. Ele permite que os clientes tenham controle sobre o caminho seus leva de tráfego de rede do Office 365. Eles não são mais precisam se preocupar com o imprevisível roteamento que acontece na Internet onde os dados são realizados por operadoras desconhecidas, provedores e os provedores. Tráfego de rede que é enviado por meio de ExpressRoute é enviado diretamente entre a rede do parceiro ExpressRoute à rede da Microsoft. Isso permite aos clientes trate o Office 365 como se ele está localizado em seu próprio Datacenter de fora da empresa com uma conexão dedicado.
  
Azure ExpressRoute está disponível para todas as ofertas de licenciamento do Office 365. No entanto, o complemento do Azure ExpressRoute Premium é necessário para Office 365 ativar o roteamento global. Clientes do Office 365 pelo menos 500 estações que estiver implementando ExpressRoute podem obter necessários *ExpressRoute Premium complemento* sem qualquer despesa adicionais.
  
### <a name="is-expressroute-required-for-good-media-quality"></a>ExpressRoute é necessário para qualidade de mídia boa?

Azure ExpressRoute não é um requisito para a obtenção do Skype mais ideal para qualidade de mídia Business Online. Entretanto, é uma da implantação opções que o ajudarão Certifique-se de que a conectividade com a nuvem cumpre o Skype para metas de desempenho de rede de negócios ou limites.
  
O Office 365 é um serviço seguro que utiliza a Internet e alto desempenho. Podemos continuar a investir em novos recursos de segurança e regionais nós da borda para melhorar continuamente a segurança e o desempenho. Azure ExpressRoute não é um requisito para os serviços do Office 365 incluindo Skype para Business Online. ExpressRoute Azure é aquele da implantação opções disponíveis que ajudará a garantir que a conectividade com o Office 365 atende o Skype para requisitos de desempenho de rede de negócios e garante o Skype mais ideal para qualidade de mídia Business Online experiência.
  
Por Skype para qualidade de mídia Business Online, é importante que a conexão entre os sites da empresa e as bordas de rede do Microsoft cumpre as metas de desempenho em requisitos de [o desempenho da rede a partir de um Skype para o cliente de negócios a rede Microsoft Borda](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge) e que a conexão entre suas bordas de rede e as bordas de rede Microsoft cumpre as metas de desempenho em [requisitos de desempenho de rede da sua rede de borda Microsoft Network borda](media-quality-and-network-connectivity-performance.md#bkYourNetworkEdge).  
  
Também é importante que a conectividade de rede física da sua empresa, incluindo a capacidade de conectividade de rede e em nuvem interna acomoda volume de tráfego de mídia de pico. ExpressRoute Azure é uma das muitas maneiras que ajudarão os clientes a garantir que seus Skype para conectividade de nuvem Business Online atende a todos esses requisitos de desempenho.
  
### <a name="is-expressroute-required-for-voice-quality-sla"></a>ExpressRoute é necessário para SLA de qualidade de voz?

Não, ExpressRoute não é necessária para Skype para negócios Online SLA de qualidade de voz. O [Skype para negócios Online SLA de qualidade de voz](http://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&amp;DocumentTypeId=37) se aplica a qualquer chamada elegível feita por qualquer Skype para o usuário de serviço de voz Online de negócios dentro da licença correta e uma assinatura que permite que o usuário fazer qualquer tipo de chamada VoIP ou PSTN. Um SLA de qualidade de voz deve incluir todas as condições a seguintes são tratadas:
  
- Chamadas da Microsoft certified telefones IP.
    
- Conexões de Ethernet com fio.
    
- Problemas de qualidade de voz devido a problemas de Microsoft Network.
    
> [!NOTE]
> O SLA de qualidade de voz exclui essas chamadas onde a qualidade da chamada de baixa é causada por problemas de redes de não-Microsoft, incluindo ExpressRoute parceiro e outras redes. 
  
### <a name="internet-or-azure-expressroute"></a>Internet ou ExpressRoute Azure?

Antes de tomar uma decisão em rede opções de conectividade para Skype para Business Online, os clientes devem avaliar a rede e conectividade de Internet atual com base nos requisitos de desempenho de rede descritos em requisitos de desempenho de rede [para se conectam ao Skype para Business Online](media-quality-and-network-connectivity-performance.md#bkNetworkPerf).
  
Se o desempenho de rede durante a conexão de Internet atual está definido para esse capacidade suficiente durante o horário de pico e que ele atenda os requisitos de desempenho de rede entre sites às bordas de rede Microsoft e suas bordas de rede às bordas de rede Microsoft, você poderá Continue a usar a conectividade com a Internet existente para se conectar ao Skype para negócios Online.
  
Para sites de empresa onde os requisitos de desempenho de rede não sejam atendidos, é altamente recomendável que você trabalhe com os prestadores de serviços de rede existentes para melhorar o desempenho geral da rede pela primeira vez. No entanto, se eles ainda não sejam atendidos, usar o Windows Azure ExpressRoute pode ajudar a garantir que sua Skype para conectividade de nuvem Business Online pode ajudá-lo a atender as exigências de desempenho de rede.
  
ExpressRoute Azure oferece os seguintes benefícios adicionais:
  
- Um contrato de serviço (SLA) sobre a disponibilidade da conexão entre a rede e a rede Microsoft. ExpressRoute tem um SLA de disponibilidade garantida de 99,9%.
    
- Largura de banda garantida e não planejado necessária para os serviços do Office 365. Você pode fazer isto, enviando apenas o tráfego do Office 365 ou Skype para o tráfego de negócios usando o ExpressRoute e faça com que todos os outro Internet tráfego passar por outros pontos de ingresso/saída da Internet para a sua rede.
    
- ExpressRoute foi projetado para preservar as marcas de QoS DSCP entre a rede e o Microsoft Network.
    
Para obter mais informações sobre o planejamento de capacidade e ExpressRoute QoS, consulte [ExpressRoute e QoS em Skype para negócios Online](https://support.office.com/en-us/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d?ui=en-US&amp;rs=en-US&amp;ad=US).
  
### <a name="can-i-setup-azure-expressroute-for-skype-for-business-online-only"></a>Posso configurar ExpressRoute do Windows Azure para Skype para negócios Online apenas?

Sim, você pode configurar ExpressRoute do Windows Azure para garantir conectividade de rede excelente da rede da sua empresa com apenas Skype para Business Online. Isso irá fornecer a qualidade de mídia em tempo real mais ideal para seus usuários, mas, em seguida, você pode continuar a se conectar a outros serviços do Office 365 pela Internet.
  
O Border Gateway Protocol (BGP) é um protocolo de roteamento na Internet que é usado para rotear o tráfego de rede pela Internet. Ele foi projetado para trocar informações de roteamento entre sistemas autônomos (AS) encontradas pela Internet. Valores de comunidades BGP são marcas de atributo que podem ser aplicadas e as rotas de entrada ou saídas. Comunidades BGP geralmente são usadas para sinalizar para o recebimento como qual link de saída será usada para acessar um destino determinado com base na área geográfica, tipo de serviço ou outros critérios.
  
Com suporte de comunidades BGP, Microsoft irá marcar os prefixos e rotas com valores de comunidade BGP apropriados com base no serviço que pertencem. Microsoft marca de prefixos divulgados por meio de correspondência pública e Microsoft correspondência com valores apropriados de comunidade BGP indicando a região os prefixos são hospedados em. Você pode confiar nos valores da comunidade para tomar decisões de roteamento apropriadas para oferecer o roteamento ideal. Você pode usar o Skype para o valor de comunidade BGP Online de negócios para a instalação de uma conexão ExpressRoute apenas para Skype para negócios Online. Você pode encontrar mais informações em [ExpressRoute requisitos de roteamento](https://azure.microsoft.com/en-us/documentation/articles/expressroute-routing/).
  
## <a name="expressroute-connectivity-scenarios-for-skype-for-business-online"></a>Cenários de conectividade de ExpressRoute para Skype para negócios Online
<a name="bkNetworkPerf"> </a>

Se você tiver decidido que ExpressRoute com base nas recomendações acima é para você, aqui estão as recomendações sobre onde e quantas conexões ExpressRoute você deve obter.
  
### <a name="online-only-deployment---single-site"></a>Implantação de somente online - site único

Se todos os seus usuários usam o Skype para serviço de Business Online e se sua escritórios são centralizados em torno de um único local físico e você decidir implantar ExpressRoute do Windows Azure, você deve configurar conexão único de ExpressRoute entre o site da sua empresa para o mais próximo [Local de correspondência ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/).
  
O gráfico a seguir mostra um exemplo desse tipo de implantação. Nesse exemplo, a Contoso é uma universidade localizada em Orlando, FL. A Contoso tem 10.000 membros de corpo docente e alunos. Os testes de Internet do seu local aos sites de borda do Microsoft mostraram maiores que 5% de perda de pacotes durante as horas de classe de pico. O tiver decidido fazer uma conexão dedicada ao Office 365 usando ExpressRoute com largura de banda exagerada provisionada para que eles possam evitar o congestionamento da rede para o Office 365 especialmente para Skype para tráfego de negócios real-time on-line. Eles se conectam à nuvem da Microsoft por meio de ExpressRoute no site Rio de janeiro, RJ MeetMe.
  
![Site único ExpressRoute.](../images/59fbca3c-a3ea-4568-8da5-3281096a7453.png)
  
### <a name="online-only-deployment---multiple-sites-on-the-same-continent"></a>Implantação de somente online - múltiplos sites em que o mesmo continente

Se sua empresa está usando Skype para os Serviços Online de negócios de vários escritórios na mesma região ou continente e você optou por implementar ExpressRoute do Windows Azure, é recomendável conectar seu site principal via ExpressRoute e, em seguida, opcionalmente adicionar adicionais ExpressRoute correspondência para outros locais que não atendem as metas de desempenho de rede recomendada.
  
No exemplo a seguir, a Contoso é uma empresa de serviços de viagens EUA que tem sede em Nova York, mas tem outros escritórios nos Estados Unidos. Seus escritórios estão entre conectados por meio de uma WAN que utilize MPLS para conexão com o Office 365. Eles inicialmente configurarem uma conexão de ExpressRoute do seu roteador de Internet em Hoboken, Nova Jersey até o site de Nova York MeetMe. 
  
Com esta configuração, o tráfego de rede da maioria dos seus sites para o Microsoft Network (site da borda de Nova York) pode atender ao Skype para metas de desempenho de rede do Business cliente conexão descritos em requisitos de desempenho da rede [de um Skype para o cliente de negócios Borda de rede para a Microsoft](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge). No entanto, a latência entre os escritórios de Costa Oeste da Contoso para Nova York será sobre 50 ms unidirecional. Além disso, Paulo é o escritório segundo maior para a Contoso, a latência de Paulo para Nova York excede 80ms unidirecional. Para garantir a qualidade de mídia bom para usuários nesses escritórios, a Contoso decidiu adicionar uma Costa Oeste ExpressRoute conexão entre seus sites de San José e o site de vale do silício ExpressRoute MeetMe.
  
![Express roteador multi-site em que o mesmo continente.](../images/bf57a473-01e1-4271-9675-385767bc58e1.png)
  
### <a name="online-only-deployment---multiple-sites-on-different-continents"></a>Implantação de somente online - vários sites em continentes diferentes

Se todos os usuários estão usando Skype para serviço de Business Online e se sua escritórios em vários locais físicos pelos vários continentes, se você decidir implantar ExpressRoute do Windows Azure, você deve configurar pelo menos uma conexão de ExpressRoute para cada continente entre o site principal do cada continente para seu [local de correspondência ExpressRoute](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/)de mais próximos. Dependendo do custo versus benefício, você pode optar por implantar conexões de ExpressRoute adicionais de sites onde as metas de desempenho de rede não forem atendidas.
  
No exemplo a seguir, a Contoso é uma empresa de grande jurídico corporativo com escritórios em cidades principais entre América do Norte e Europa. Com base em sua conexão de Internet e sua avaliação de desempenho da rede interna, Contoso decidiu implantar duas conexões ExpressRoute na América do Norte e um circuito ExpressRoute único para todos os seus escritórios europeus.
  
![ExpressRoute com vários continentes e sites.](../images/c967550b-dc85-4b37-a7bc-cd825ec86854.png)
  
### <a name="hybrid-deployment"></a>Implantação híbrida

Se você tiver um Lync local ou Skype para implantação de negócios e escolher implementar um híbrido Skype para integração de Business Online, recomendamos que, se você decidir implantar ExpressRoute do Windows Azure, você precisa ter pelo menos uma conexão de ExpressRoute para cada um local no Lync ou Skype para site de borda de negócios e pelo menos uma conexão de ExpressRoute para cada continente com escritórios. Dependendo do custo versus benefício, para cada continente, você pode optar por implantar conexões de ExpressRoute adicionais de escritórios onde as metas de desempenho de rede não sejam atendidas.
  
Se você tiver um Skype local para implantação de negócios, você deve seguir o [guia de implantação e planejamento do servidor de borda](https://technet.microsoft.com/en-us/library/mt346417.aspx). Especificamente, os servidores de borda devem ser acessados a partir de fora da sua rede. Geralmente, isso é obtido, atribuindo um endereço IP público roteável ao servidor de borda ou usando a conversão de endereço de rede (NAT).
  
No exemplo a seguir, a Contoso tem um Skype local existente para a implantação do Enterprise Voice de negócios. Eles querem migrar usuários locais para os serviços online do Office 365. Eles também decidiram usar uma implantação híbrida, para que eles podem continuar a usar sua infraestrutura existente do PSTN para todos os usuários online e no local. Centro de dados no local e do Skype para servidores de borda de negócios da Contoso estão em Chicago. Para sua implantação, a Contoso decidiu configurar uma conexão de ExpressRoute entre seu data center de Chicago e o ExpressRoute Chicago. Eles também adicionados a uma Costa Oeste ExpressRoute conexão para atender melhor aos seu office Paulo.
  
![ExpressRoute híbrido.](../images/a7467c56-642f-44e5-adfb-ecca91ba2dd3.png)
  
### <a name="online-deployment-with-cloud-connector-edition"></a>Implantação online com Edition do conector de nuvem

Skype para o conector de nuvem Online Business Edition é um híbrido oferecendo que consiste em um conjunto de Industrializados máquinas virtuais (VMs) implementar uma conectividade PSTN local. Implantando um Skype mínimo para a topologia de servidor de negócios em um ambiente virtualizado, você poderá enviar e receber chamadas com landlines e telefones móveis por meio da infra-estrutura de voz PSTN local existente.
  
Se você decidir implantar o Azure ExpressRoute e edição do conector de nuvem, é recomendável para configurar pelo menos uma conexão de rota Express para cada continente entre sites do cada continente principal para sua mais próximos [ExpressRoute local de correspondência](https://azure.microsoft.com/en-us/documentation/articles/expressroute-locations/). Dependendo do custo versus benefício, para cada continente, você pode optar por implantar conexões de ExpressRoute adicionais de sites onde as metas de desempenho de rede não sejam atendidas.
  
Se você tiver um Skype local para implantação de negócios, você deve seguir o [Guia de planejamento para Skype para o conector de nuvem Business Edition](https://technet.microsoft.com/EN-US/library/mt605227.aspx). Especificamente, a borda de acesso e uma / serviços de borda de V devem ser atribuídos endereços IP públicos e acessível a partir de centros de dados do Office 365.
  
No exemplo a seguir, a Contoso é uma empresa de contabilidade europeu com presença em alguns principais países europeu e cidades. Quando eles Inscreva-se para Skype Business Online para todas as suas necessidades de colaboração, eles decidiram colocar um conector de nuvem para cada país causam um local físico para continuar a usar sua infra-estrutura PSTN e contratos de operadora que já existem. Com base nos seus testes de todos os seus sites e Microsoft network borda, eles determinou que uma conexão ExpressRoute único em Londres ajudará a enfrentar o Skype para metas de desempenho de rede do Business cliente conexão descrito em [o desempenho da rede requisitos de um Skype para o cliente de negócios para a Microsoft de borda de rede](media-quality-and-network-connectivity-performance.md#bkSfBClienttoEdge).
  
![Conector de nuvem ExpressRoute um.](../images/ebdc96e5-b22a-4bf2-b668-062460b4b890.png)
  
A seguir, é outra opção de implantação para a Contoso. Nesse caso, decidiu configurar uma conexão ExpressRoute em cada site onde um conector de nuvem está implantado. 
  
![Conector de nuvem ExpressRoute dois.](../images/06d967a9-64f5-4d7d-98ed-3f3add1b7c2b.png)
  
## <a name="related-topics"></a>Tópicos relacionados

[ExpressRoute e QoS no Skype for Business Online](expressroute-and-qos-in-skype-for-business-online.md)

  
 