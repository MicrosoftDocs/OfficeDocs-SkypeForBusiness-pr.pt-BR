---
title: Planejar os requisitos de rede para o Skype for Business
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
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Resumo: revise as considerações do componente de rede abaixo antes de implementar o Skype for Business Server.'
ms.openlocfilehash: 709da2ddd60b5b6ee69c22264c159d5d94ab91e3
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42025792"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Planejar os requisitos de rede para o Skype for Business

**Resumo:** Revise as considerações do componente de rede abaixo antes de implementar o Skype for Business Server.

As informações nesses tópicos também são discutidas no planejamento de [rede de whitepaper, monitoramento e solução de problemas com o Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) com detalhes e profundidade adicionais. Embora o conteúdo se refira explicitamente para Lync 2010 e Lync 2013, as considerações para o Skype for Business Server não são alteradas.

Da mesma forma, se sua rede envolver o Wi-Fi, bem como acesso com fio, o White paper que [fornece comunicações em tempo real do Lync 2013 por Wi-Fi](https://www.microsoft.com/download/details.aspx?id=36494) é uma boa referência e é igualmente aplicável ao Skype for Business Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Hardware de servidor
<a name="S_hard"> </a>

O adaptador de rede de cada servidor na topologia do Skype for Business Server deve suportar pelo menos 1 gigabit por segundo (Gbps). Em geral, você deve conectar todas as funções de servidor dentro da topologia do Skype for Business Server usando uma rede local de baixa latência e alta largura de banda (LAN). O tamanho da LAN depende do tamanho da topologia:

- Nas topologias do Standard Edition, os servidores devem estar em uma rede que ofereça suporte a Ethernet de 1 Gbps ou equivalente.

- Nas topologias do Enterprise Edition, a maioria dos servidores deve estar em uma rede que ofereça suporte a mais de 1 Gbps, especialmente quando houver suporte para conferência de áudio/vídeo (A/V) e compartilhamento de aplicativos.

Para a integração com PSTN, você pode usar linhas T1/E1 ou troncos SIP.

## <a name="audiovideo-network-requirements"></a>Requisitos de rede de áudio/vídeo
<a name="AV_req"> </a>

Os requisitos de rede para o áudio/vídeo (A/V) em uma implantação do Skype for Business Server incluem o seguinte:

- Se você estiver implantando um único servidor de borda ou um pool de borda usando o balanceamento de carga DNS, é possível configurar o firewall _externo_ para executar NAT (conversão de endereço de rede). Você não pode configurar o firewall _interno_ para executar o NAT. Para obter detalhes, consulte [Port and firewall Planning](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Se você tiver um pool de borda e estiver usando um balanceador de carga de hardware, você deverá usar endereços IP públicos nos servidores de borda e não poderá usar o NAT para os servidores ou o pool em seu dispositivo com capacidade de NAT (por exemplo, um dispositivo de firewall ou uma opção de LAN. Para obter detalhes, consulte [Edge Server Scenarios in Skype for Business Server](../edge-server-deployments/scenarios.md).

- Caso sua organização use uma infraestrutura de QoS (Qualidade de Serviço), o subsistema de mídia estará projetado para operar dentro dessa infraestrutura existente.

- Caso você utilize o protocolo IPsec, é recomendável desabilitá-lo nos intervalos de portas usados para o tráfego de A/V. Para obter detalhes, consulte [exceções de IPSec](#ipsec-exceptions).

Para fornecer a qualidade de mídia ideal, faça o seguinte:

- Provisione os links de rede para dar suporte à taxa de transferência de 65 kilobits por segundo (Kbps) por fluxo de áudio e 500 kbps por fluxo de vídeo, se estiverem habilitados, durante períodos de pico de uso. Uma sessão de áudio ou vídeo bidirecional usa dois fluxos, portanto, uma conexão de áudio/telefone simples exigirá o 130Kbps para cobrir cada fluxo. O vídeo de forma semelhante usará 1000 kbps no total para transportar uma conexão de upstream e downstream.

- Para lidar com picos inesperados de tráfego e maior uso com o passar do tempo, os pontos de extremidade de mídia do Skype for Business Server podem se adaptar às diferentes condições de rede e dar suporte a uma taxa de transferência de áudio e vídeo, mantendo a qualidade aceitável. Não presuma que essa adaptabilidade irá mascarar o problema quando uma rede estiver em provisionamento. Em uma rede subvisionada, a capacidade dos pontos de extremidade de mídia do Skype for Business Server para lidar dinamicamente com condições de rede variáveis (por exemplo, perda de pacote de alta capacidade temporária) é reduzida.

- Para os links de rede em que o provisionamento é muito dispendioso e difícil, talvez seja necessário considerar o provisionamento para um volume menor de tráfego. Neste cenário, deixe a elasticidade dos pontos de extremidade de mídia do Skype for Business Server absorver a diferença entre o volume de tráfego e o nível de tráfego de pico, ao custo de alguma redução na qualidade de voz. Além disso, haverá uma redução no espaço, caso contrário, disponível para absorver picos repentinos no tráfego.

- Para links que não podem ser provisionados corretamente no curto prazo (por exemplo, um site que usa links WAN muito ruins), considere desabilitar o vídeo para determinados usuários.

- Provisione a rede para garantir um atraso máximo de ponta a ponta (latência) de 150 milissegundos (MS) em carga de pico. Latência é a única deficiência da rede que os componentes de mídia do Skype for Business Server não podem reduzir e é importante encontrar e eliminar os pontos fracos.

- Para servidores que executam software antivírus, inclua todos os servidores que estão executando o Skype for Business Server na lista exceção para fornecer desempenho e qualidade de áudio ideais.

## <a name="ipsec-exceptions"></a>Exceções IPsec

Nas redes corporativas em que o protocolo IPsec (consulte a RFC 4301-4309 da IETF) foi implantado, o protocolo IPsec deverá ser desabilitado no intervalo de portas usado para a entrega de áudio, vídeo e vídeo panorama. A recomendação vem da necessidade de evitar qualquer atraso na alocação das portas de mídia por causa da negociação IPsec.

A tabela a seguir explica as configurações de exceções recomendadas do IPsec.

**Exceções recomendadas do IPsec**

|Nome da regra |IP de origem |IP de destino |Protocolo |Porta de origem |Porta de destino |Requisito de autenticação |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|Entrada interna do Servidor de Borda A/V|Qualquer tamanho  |Interno do Servidor de Borda A/V|UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Entrada externa do Servidor de Borda A/V|Qualquer tamanho  |Externo do Servidor de Borda A/V|UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Saída interna do Servidor de Borda A/V|Interno do Servidor de Borda A/V  |Externo do Servidor de Borda A/V |UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Saída externa do Servidor de Borda A/V|Externo do Servidor de Borda A/V |Qualquer tamanho |UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Entrada do Servidor de Mediação|Qualquer tamanho  |Servidor (es) de mediação |UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Saída do Servidor de Mediação|Servidor (es) de mediação  |Qualquer tamanho|UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Entrada do Atendedor de Conferência|Qualquer tamanho  |Servidor Front End executando o Atendedor de Conferência |UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Saída do Atendedor de Conferência|Servidor Front End executando o Atendedor de Conferência  |Qualquer tamanho|UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Entrada de Conferência A/V|Qualquer tamanho|Servidores Front-End|UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Saída de Conferência A/V|Servidores Front-End|Qualquer tamanho|UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Entrada do Exchange|Qualquer tamanho|Unificação de Mensagens do Exchange|UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Entrada dos Servidores de Compartilhamento de Aplicativo|Qualquer tamanho|Servidores de Compartilhamento de Aplicativos|UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Saída do Servidor de Compartilhamento de Aplicativos.|Servidores de Compartilhamento de Aplicativos| Qualquer tamanho |UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Saída do Exchange|Unificação de Mensagens do Exchange|Qualquer tamanho|UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|Clientes| Qualquer tamanho  |Qualquer tamanho|UDP e TCP|Qualquer tamanho |Qualquer tamanho |Não autenticar|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Requisitos de rede de conferência
<a name="Conf_req"> </a>

A largura de banda usada para baixar o conteúdo da conferência do servidor de serviços de informações da Internet (IIS) depende do tamanho do conteúdo. Você pode optar por monitorar o uso real e ajustar o planejamento de largura de banda de acordo.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de largura de banda de rede para tráfego de mídia
<a name="Conf_req"> </a>

Uma parte importante do planejamento de rede é garantir que sua rede possa lidar com o tráfego de mídia gerado pelo Skype for Business Server. Esta seção ajuda você a planejar esse tráfego de mídia.

### <a name="media-traffic-network-usage"></a>Uso da rede de tráfego de mídia
<a name="Net_req"> </a>

O uso da largura de banda do tráfego de mídia pode ser desafiador para calcular devido ao número de diferentes variáveis, como o uso de codec, resolução e níveis de atividade. O uso da largura de banda é uma função do codec usado e da atividade do Stream, que pode variar entre cenários. A tabela a seguir lista os codecs de áudio normalmente usados nos cenários do Skype for Business Server.

**Largura de banda do codec de áudio**

|**Codec de áudio**|**Cenário**|**Taxa de bits de carga de áudio (KBPS)**|**Apenas carga de áudio da largura de banda e cabeçalho IP (Kbps)**|**Carga de áudio da largura de banda, cabeçalho IP, UDP, RTP e SRTP (Kbps)**|**Carga de áudio da largura de banda, cabeçalho IP, UDP, RTP, SRTP e correção de erro de encaminhamento (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda larga RTAudio  <br/> |Ponto a ponto  <br/> |29,0  <br/> |45,0  <br/> |57,0  <br/> |86,0  <br/> |
|Banda estreita RTAudio  <br/> |PSTN ponto a ponto  <br/> |11,8  <br/> |27,8  <br/> |39,8  <br/> |51,6  <br/> |
|G. 722  <br/> |Conferências  <br/> |64,0  <br/> |80,0  <br/> |95,6  <br/> |159,6  <br/> |
|Estéreo G. 722  <br/> |Conferência ponto a ponto  <br/> |128,0  <br/> |144,0  <br/> |159,6  <br/> |223,6  <br/> |
|G. 711  <br/> |PSTN, conferência  <br/> |64,0  <br/> |80,0  <br/> |92,0  <br/> |156,0  <br/> |
|Siren  <br/> |Conferências  <br/> |16,0  <br/> |32,0  <br/> |47,6  <br/> |63,6  <br/> |
|SILK banda larga  <br/> |Ponto a ponto  <br/> |36,0  <br/> |52,0  <br/> |64,0  <br/> |100,0  <br/> |
|SILK banda larga  <br/> |Ponto a ponto  <br/> |26,0  <br/> |42,0  <br/> |54,0  <br/> |80,0  <br/> |
|SILK banda larga  <br/> |Ponto a ponto  <br/> |20,0  <br/> |36,0  <br/> |48,0  <br/> |68,0  <br/> |
|SILK banda larga/banda estreita  <br/> |Ponto a ponto  <br/> |13,0  <br/> |29,0  <br/> |41,0  <br/> |54,0  <br/> |

> [!NOTE]
> As chamadas PSTN do cliente do Skype for Business geralmente usam o codec G. 711, que requer uma alta largura de banda. Se não houver largura de banda suficiente disponível para esse codec, as chamadas poderão falhar com um erro semelhante ao seguinte nos logs de mídia: **pelo menos um codec deve ser habilitado, hr: c0042004**. Os logs de mídia (arquivos. Blogs) são criptografados e podem ser decodificados apenas pela equipe de suporte da Microsoft.

Os números de largura de banda na tabela anterior são baseados em pacotes de 20 ms (pacotes 50 por segundo) e os codecs Siren e G. 722 incluem a sobrecarga de SRTP (Secure real-time Transport Protocol) adicional de cenários de conferência e pressupõe que o Stream seja 100% ativa. A correção de erro de encaminhamento (FEC) é usada dinamicamente quando há perda de pacote no link para ajudar a manter a qualidade do fluxo de áudio.

A versão estéreo do codec G. 722 é usada por sistemas baseados no sistema de salas do Lync, que usa um único microfone estéreo ou um par de microfones mono para permitir que os ouvintes diferenciem melhor vários alto-falantes na sala de reunião.

**Largura de banda de resolução de vídeo**

|**Codec de vídeo**|**Resolução e taxa de proporção**|**Taxa máxima de bits de carga de vídeo (Kbps)**|**Taxa de bits mínima de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H. 264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15   <br/> |
|H. 264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H. 264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H. 264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H. 264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H. 264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H. 264/RTVideo  <br/> |1280 x 720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H. 264  <br/> |1920 x 1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H. 264/RTVideo  <br/> |960 x 144 (20:3)  <br/> |500  <br/> |15   <br/> |
|H. 264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H. 264  <br/> |1920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |

O codec padrão para vídeo é o padrão de codificação de vídeo avançado H. 264/MPEG-4 parte 10, juntamente com suas extensões escalonáveis de codificação de vídeo para escalabilidade temporal. Para manter a interoperabilidade com clientes herdados, o codec RTVideo ainda é usado para chamadas ponto a ponto entre o Skype for Business Server e clientes herdados. Em sessões de conferência com o Skype for Business Server e clientes herdados, o ponto de extremidade do Skype for Business Server pode codificar o vídeo usando os codecs de vídeo e enviar o H. 264 Bitstream para os clientes do Skype for Business Server e o RTVideo Bitstream para Legacy nos.

A largura de banda necessária depende da resolução, qualidade, taxa de quadros e a quantidade de movimento ou alteração na imagem. Para cada resolução, há duas taxas de bits pertinentes:

- **Taxa máxima de bits de carga** Esta é a taxa de bits que um ponto de extremidade usará para resolução na taxa de quadros máxima. Esse é o valor que permite a melhor qualidade de vídeo e som.

- **Taxa de bits de carga mínima** Esta é a taxa de bits abaixo da qual um ponto de extremidade do Skype for Business Server mudará para a próxima resolução mais baixa. Para garantir uma determinada resolução, a taxa de bits de carga de vídeo disponível não deve ficar abaixo dessa taxa de bits mínima para essa resolução. Esse valor é o ajuda a entender o menor valor possível se a taxa de bits máxima não estiver disponível ou prática. Para alguns usuários, um vídeo de baixa taxa de bits pode fornecer uma experiência de vídeo inaceitável, portanto, cuidado com essas taxas de bits de carga de vídeo mínimas. Observe que, para cenas de vídeo estáticos não alteradas, a taxa de bits real pode ficar temporariamente abaixo da taxa de bits mínima.

O Skype for Business Server oferece suporte a várias soluções. Isso permite que o Skype for Business Server se ajuste para diferentes largura de banda de rede e recursos de cliente de recebimento. A taxa de proporção padrão para o Skype for Business Server é 16:9. A taxa de proporção 4:3 herdada ainda tem suporte para webcams que não permitem a captura na taxa de proporção de 16:9.

O FEC de vídeo é sempre incluído na taxa de bits de carga de vídeo quando é usado para que não haja valores separados com o FEC de vídeo e sem o FEC de vídeo.

Os pontos de extremidade não transmitem pacotes de áudio ou vídeo continuamente. Dependendo do cenário, existem níveis diferentes de atividade de fluxo que indicam a frequência com que os pacotes são enviados por um fluxo. A atividade de um fluxo depende da mídia e do cenário e não depende do codec que está sendo usado. Em um cenário ponto a ponto:

- Os pontos de extremidade enviam fluxos de áudio apenas quando os usuários falam.

- Ambos os participantes recebem fluxos de áudio.

- Se o vídeo for usado, os dois pontos de extremidade enviam e recebem fluxos de vídeo durante a chamada.

- Para cenas de vídeo estáticos, a taxa de bits real pode ser temporariamente muito baixa, pois o codec de vídeo ignorará a codificação de regiões do vídeo sem uma alteração desde o exemplo anterior.

Em um cenário de conferência:

- Os pontos de extremidade enviam fluxos de áudio apenas quando os usuários falam.

- Todos os participantes recebem fluxos de áudio.

- Se o vídeo for usado, todos os participantes poderão receber até cinco fluxos de vídeo de recebimento e um fluxo de vídeo panorâmico (por exemplo, taxa de proporção 20:3). Por padrão, os cinco fluxos de vídeo de recebimento são baseados no histórico de alto-falantes ativos, mas os usuários também podem selecionar manualmente os participantes dos quais desejam receber um fluxo de vídeo. Se houver vários vídeos habilitados, a resolução e a necessidade de largura de banda para cada um dos fluxos de vídeo serão menores.

- Cada participante que liga o fluxo de vídeo de envio do usuário enviará um ou mais fluxos de vídeo. O Skype for Business Server tem a capacidade de enviar até cinco fluxos de vídeo para otimizar a qualidade de vídeo de todos os clientes de recebimento. O número real de fluxos de vídeo sendo enviados é determinado pelo remetente com base no recurso de CPU, na largura de banda de uplink disponível e no número de clientes de recebimento que solicitam um determinado fluxo de vídeo. O caso mais comum é que um e um fluxo de vídeo do RTVideo estão sendo enviados, caso um cliente herdado ingresse na conferência. Outro cenário comum é que vários fluxos de vídeo H. 264 (por exemplo, com diferentes resoluções de vídeo) são enviados para acomodar diferentes solicitações de destinatário.

Além da largura de banda necessária par ao tráfego do protocolo de transporte em tempo real (RTP) para mídia de áudio e vídeo, a largura de banda é necessária para o protocolo de controle de transporte em tempo real (RTCP). O RTCP é usado para relatar diagnósticos e controle fora da banda do fluxo RTP. Para planejamento, use os números da largura de banda da seguinte tabela para tráfego RTCP. Esses valores representam a largura de banda máxima usada para RTCP e são diferentes para fluxos de áudio e vídeo devido às diferenças nos dados de controle

**Largura de banda RTCP**

|**Mídia**|**Largura de banda máxima RTCP (Kbps)**|
|:-----|:-----|
|Áudio  <br/> |5   <br/> |
|Vídeo (somente H. 264 ou RTVideo sendo enviado/recebido)  <br/> |10   <br/> |
|Vídeo (H. 264 e RTVideo sendo enviado/recebido)  <br/> |15   <br/> |

Para o planejamento de capacidade, as duas estatísticas a seguir são de interesse:

- **Largura de banda máxima sem FEC** A largura de banda máxima que um fluxo consumirá. Isso inclui a atividade típica do fluxo e o codec típico usado no cenário sem o FEC. Esta é a largura de banda quando o fluxo está a 100% de atividade e não há perda de pacotes acionando o uso do FEC. Isso é útil para calcular a quantidade de largura de banda que deve ser alocada para permitir que o codec seja usado em um determinado cenário. O FEC não deve ser um requisito em uma rede gerenciada.

- **Largura de banda máxima com FEC** A largura de banda máxima consumida por um fluxo. Isso inclui a atividade típica do fluxo e o codec típico usado no cenário com o FEC. Esta é a largura de banda quando o fluxo está a 100% de atividade e há perda de pacote acionando o uso do FEC para melhorar a qualidade. Isso é útil para calcular a quantidade de largura de banda que deve ser alocada para permitir que o codec seja usado em um determinado cenário e permitir o uso de FEC para preservar a qualidade sob condições de perda de pacotes.

As tabelas a seguir também lista um valor de largura de banda adicional, **Largura de banda típica**. Esta é a largura de banda média que um fluxo consome. Isso inclui a atividade típica do fluxo e o codec típico usado no cenário. Essa largura de banda pode ser usada para aproximando a quantidade de largura de banda que está sendo consumida pelo tráfego de mídia em um momento específico, mas não deve ser usada para o planejamento de capacidade, pois as chamadas individuais excederão esse valor quando o nível de atividade for maior que a média. A largura de banda de fluxo de vídeo típica nas tabelas abaixo baseia-se em uma mistura de diferentes resoluções de vídeo, conforme observado em dados de clientes medidos, e as instalações menores provavelmente têm números reais diferentes dos dados da tabela. Por exemplo, em sessões ponto a ponto, a maioria dos usuários usaria a janela de renderização de vídeo padrão, enquanto alguma porcentagem de usuários aumentaria ou maximizaria o aplicativo Skype for Business Server para permitir melhores resoluções de vídeo.

As tabelas a seguir fornecem valores para os vários cenários.

**Planejamento de capacidade de áudio/vídeo para sessões ponto a ponto**

|**Mídia**|**Codec**|**Largura de banda de fluxo típico (Kbps)**|**Largura de banda de fluxo máximo sem FEC**|**Largura de banda de fluxo máximo com FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |Banda ampla RTAudio  <br/> |39,8  <br/> |62  <br/> |91  <br/> |
|Áudio  <br/> |Banda estreita RTAudio  <br/> |29,3  <br/> |44,8  <br/> |56,6  <br/> |
|Áudio  <br/> |SILK banda larga  <br/> |44,3  <br/> |69  <br/> |105  <br/> |
|Vídeo principal ao chamar os pontos de extremidade do Skype for Business Server  <br/> |H. 264  <br/> |460  <br/> |4010 (para resolução máxima de 1920 x 1080)  <br/> |Já incluída  <br/> |
|Vídeo principal ao chamar os pontos de extremidade do Lync 2010 ou do Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (para resolução máxima de 1280 x 720)  <br/> |Já incluída  <br/> |
|Vídeo panorâmico ao chamar os pontos de extremidade do Skype for Business Server  <br/> |H. 264  <br/> |190  <br/> |2010 (para resolução máxima de 1920 x 288)  <br/> |Já incluída  <br/> |
|Vídeo panorâmico ao chamar pontos de extremidade do Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (para resolução máxima de 960 x 144)  <br/> |Já incluída  <br/> |

**Planejamento de capacidade de áudio/vídeo para conferências**

|**Mídia**|**Codec típico**|**Largura de banda de fluxo típico (Kbps)**|**Largura de banda de fluxo máximo sem FEC**|**Largura de banda de fluxo máximo com FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |G. 722  <br/> |46,1  <br/> |100,6  <br/> |164,6  <br/> |
|Áudio  <br/> |Siren  <br/> |25,5  <br/> |52,6  <br/> |68,6  <br/> |
|Recebimento de vídeo principal  <br/> |H. 264 e RTVideo ¹  <br/> |260  <br/> |8015  <br/> |Não aplicável  <br/> |
|Envio de vídeo principal  <br/> |H. 264 e RTVideo  <br/> |270  <br/> |8015  <br/> |Não aplicável  <br/> |
|Recebimento de vídeo panorâmico  <br/> |H. 264 e RTVideo  <br/> |190  <br/> |2010 (para resolução máxima de 1920 x 288)  <br/> |Não aplicável  <br/> |
|Envio de vídeo panorâmico  <br/> |H. 264 e RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Não aplicável  <br/> |

1. O vídeo RT é enviado além da H. 264 quando os clientes do Lync 2010 estão conectados à conferência.

2. Se houver vários fluxos, eles compartilharão dinamicamente a largura de banda alocada.

Para o vídeo principal, a largura de banda de fluxo típica é a largura de banda agregada em todos os fluxos de vídeo recebidos e o fluxo máximo é a largura de banda sobre todos os fluxos de vídeo de envio. Mesmo com vários fluxos de vídeo, a largura de banda de vídeo típica é menor do que no cenário ponto a ponto, pois muitas conferências de vídeo estão usando o compartilhamento de conteúdo que leva a janelas de vídeo muito menores e, portanto, as resoluções de vídeo menores. A largura de banda máxima suportada de carga de vídeo agregada é de 8000 kbps para os fluxos de envio e recebimento, que seriam usados (por exemplo, se houver dois fluxos de vídeo de entrada 1920x1080p). Os valores máximos são raramente vistos em implementações reais.

Ao criar uma conferência de vários participantes que usa o recurso de exibição de galeria, a utilização da largura de banda aumenta inicialmente à medida que os participantes ingressam e, em seguida, diminui à medida que as resoluções são removidas para o máximo.

||**2 participantes**|**3 participantes**|**4 participantes**|**5 participantes**|**6 participantes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Máximo de resoluções recebidas** <br/> |1920 x 1080  <br/> |1280 x 720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Taxa de bits média total** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Taxa de bits máxima total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

A largura de banda de fluxo típica para o vídeo panorâmico é baseada em dispositivos que só transmitem vídeo panorâmico no 960 x 144. Espere a largura de banda típica do fluxo para aumentar ao usar dispositivos com vídeo panorâmico do 1920 x 288.

**Planejamento de capacidade de áudio para PSTN**

|**Mídia**|**Codec típico**|**Largura de banda de fluxo típico (Kbps)**|**Largura de banda de fluxo máximo sem FEC**|**Largura de banda de fluxo máximo com FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |G. 711 (inclui participantes PSTN em conferências)  <br/> |64,8  <br/> |97  <br/> |161  <br/> |
|Áudio  <br/> |Banda estreita RTAudio  <br/> |30,9  <br/> |44,8  <br/> |56,6  <br/> |

Os números de largura de banda da rede nestas tabelas representam apenas o tráfego de uma via e inclui 5 Kbps de sobrecarga de tráfego RTCP para cada fluxo.

## <a name="managing-quality-of-service"></a>Gerenciando a qualidade de serviço
<a name="man_QOS"> </a>

A qualidade de serviço (QoS) é uma tecnologia de rede que é usada em algumas organizações para ajudar a fornecer uma experiência ideal para o usuário final para comunicações de áudio e vídeo. A QoS é usada com mais frequência em redes nas quais a largura de banda é limitada: com um grande número de pacotes de rede competindo por uma quantidade muito pequena de largura de banda, a QoS permite que os administradores atribuam prioridades maiores aos pacotes que contenham dados de áudio ou vídeo. Ao fornecer esses pacotes, é provável que as comunicações de áudio e vídeo sejam concluídas com mais rapidez e com menos interrupção do que as sessões de rede que envolvem coisas como transferências de arquivos, navegação na Web ou backups de banco de dados. Isso ocorre porque os pacotes de rede usados para transferências de arquivos ou backups de bancos de dados recebem uma atribuição de prioridade de "melhor esforço".

> [!NOTE]
> Como regra, a QoS só se aplica a sessões de comunicação em sua rede interna. Ao implementar a QoS, você configura seus servidores e roteadores para suportar a marcação de pacotes de uma maneira específica que pode não ser suportada na Internet ou em outras redes. Mesmo se a qualidade do serviço for suportada em outras redes, não haverá garantia de que a QoS será configurada exatamente da mesma maneira que você configurou o serviço. Se estiver usando o MPLS, você precisará trabalhar com seu provedor de MPLS.

O Skype for Business Server não requer QoS, mas é altamente recomendável. Se você tiver problemas de perda de pacotes na rede, as soluções disponíveis serão adicionar mais largura de banda ou implementar QoS. Se não for possível adicionar mais largura de banda, a possibilidade de implementar a QoS poderá ser a única chamada para resolver o problema.

O Skype for Business Server oferece suporte completo para QoS: isso significa que as organizações que já estão usando a QoS podem integrar facilmente o Skype for Business Server à sua infraestrutura de rede existente. Para fazer isso, você deve seguir estas etapas:

- [Habilitando a QoS no Skype for Business Server para dispositivos que não são baseados no Windows](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). Por padrão, a QoS está desativada para computadores e outros dispositivos (como iPhones) que executam outros sistemas operacionais. Embora você possa usar o Skype for Business Server para habilitar e desabilitar a qualidade do serviço para dispositivos, normalmente não é possível usar o produto para modificar os códigos de DSCP usados por esses dispositivos.

- [Configurar intervalos de porta e uma política de qualidade de serviço para seus servidores de conferência, aplicativos e mediação](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). É necessário reservar um conjunto exclusivo de portas para tipos de pacotes diferentes, como áudio e vídeo. Usando o Skype for Business Server, não é possível habilitar ou desabilitar a QoS definindo um valor de propriedade como true ou false. Em vez disso, você habilita a QoS Configurando intervalos de porta e criando e aplicando a política de grupo. Se, posteriormente, você decidir não usar a QoS, poderá "Desabilitar" a QoS removendo os objetos de política de grupo apropriados.

- [Configurar intervalos de porta e uma política de qualidade de serviço para seus servidores de borda](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Embora não seja necessário, você pode configurar seus servidores de borda para usar os mesmos intervalos de porta que os outros servidores. A configuração de uma política de QoS só será feita para o lado interno de seus servidores de borda. Isso se deve ao fato de o QoS ser usado em sua rede interna e não na Internet.

- [Configurando intervalos de porta e uma política de qualidade de serviço para seus clientes no Skype for Business Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Esses intervalos de porta se aplicam somente a computadores clientes e são normalmente diferentes dos intervalos de porta configurados em seus servidores. Observe que o Skype for Business Server não oferece suporte a QoS para sistemas operacionais Windows diferentes do Windows 10.


> [!NOTE]
> Se você estiver usando o Windows Server 2012 ou o Windows Server 2012 R2, pode estar interessado no novo conjunto de cmdlets do Windows PowerShell disponíveis para o gerenciamento de QoS nessa plataforma. Para obter mais informações, consulte [cmdlets QoS de rede no Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

A QoS também é discutida no [planejamento, monitoramento e solução de problemas de rede com o Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) com detalhes e profundidade adicionais. Embora o conteúdo se refira explicitamente para Lync 2010 e Lync 2013, as considerações para o Skype for Business Server não são alteradas.

## <a name="see-also"></a>Confira também
<a name="man_QOS"> </a>

[Planejar o IPv6 no Skype for Business](ipv6.md)

[Requisitos de balanceamento de carga para o Skype for Business](load-balancing.md)

[Requisitos de DNS para o Skype for Business Server](dns.md)
