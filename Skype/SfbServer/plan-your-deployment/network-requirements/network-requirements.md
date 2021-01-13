---
title: Planejar requisitos de rede para o Skype for Business
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
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Resumo: revise as considerações do componente de rede abaixo antes de implementar o Skype for Business Server.'
ms.openlocfilehash: 0b5d183ecc11d09569427e432121fab7de8f401b
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834351"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Planejar requisitos de rede para o Skype for Business

**Resumo:** Revise as considerações do componente de rede abaixo antes de implementar o Skype for Business Server.

As informações nesses tópicos também são discutidas no whitepaper [Network Planning, Monitoring, and Troubleshooting with Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) with additional details and depth. Embora o conteúdo se refira explicitamente ao Lync 2010 e ao Lync 2013, as considerações para o Skype for Business Server não foram alteradas.

Da mesma forma, se sua rede envolve wi-fi, bem como acesso com fio, o whitepaper Entrega de comunicações do [Lync 2013 Real-Time via Wi-Fi](https://www.microsoft.com/download/details.aspx?id=36494) é uma boa referência e é igualmente aplicável ao Skype for Business Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Hardware de servidor
<a name="S_hard"> </a>

O adaptador de rede de cada servidor na topologia do Skype for Business Server deve suportar pelo menos 1 gbps (gigabit por segundo). Em geral, você deve conectar todas as funções de servidor dentro da topologia do Skype for Business Server usando uma lan (rede local) de baixa latência e largura de banda alta. O tamanho da LAN depende do tamanho da topologia:

- Em topologias Standard Edition, os servidores devem estar em uma rede que dá suporte a Ethernet de 1 Gbps ou equivalente.

- Em topologias Enterprise Edition, a maioria dos servidores deve estar em uma rede que suporta mais de 1 Gbps, especialmente ao dar suporte a conferências de áudio/vídeo (A/V) e compartilhamento de aplicativos.

Para a integração com PSTN, você pode usar linhas T1/E1 ou troncos SIP.

## <a name="audiovideo-network-requirements"></a>Requisitos de rede de áudio/vídeo
<a name="AV_req"> </a>

Os requisitos de rede para áudio/vídeo (A/V) em uma implantação do Skype for Business Server incluem o seguinte:

- Se você estiver implantando um único Servidor de Borda ou um pool de Borda usando o balanceamento de carga DNS, poderá configurar o  _firewall_ externo para executar NAT (conversão de endereços de rede). Não é possível configurar o firewall _interno_ para executar NAT. Para obter detalhes, consulte [Port and firewall planning](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Se você tiver um pool de Borda e estiver usando um balanceador de carga de hardware, deverá usar endereços IP públicos nos Servidores de Borda e não poderá usar NAT para os servidores ou o pool em seu dispositivo com capacidade NAT (por exemplo, um dispositivo de firewall ou com opção de LAN. Para obter detalhes, [consulte Cenários do Servidor de Borda no Skype for Business Server.](../edge-server-deployments/scenarios.md)

- Caso sua organização use uma infraestrutura de QoS (Qualidade de Serviço), o subsistema de mídia estará projetado para operar dentro dessa infraestrutura existente.

- Caso você utilize o protocolo IPsec, é recomendável desabilitá-lo nos intervalos de portas usados para o tráfego de A/V. Para obter detalhes, consulte [exceções do IPsec.](#ipsec-exceptions)

Para fornecer a melhor qualidade de mídia, faça o seguinte:

- Provisione os links de rede para suportar a produtividade de 65 quilobits por segundo (Kbps) por fluxo de áudio e 500 Kbps por fluxo de vídeo, se eles estão habilitados, durante os períodos de pico de uso. Uma sessão de áudio ou vídeo de duas vias usa dois fluxos, portanto, uma conexão de áudio/telefone simples exigirá 130 Kbps para cobrir cada fluxo. O vídeo também usará 1000 Kbps no total para realizar uma conexão upstream e downstream.

- Para lidar com picos inesperados no tráfego e aumento do uso ao longo do tempo, os pontos de extremidade de mídia do Skype for Business Server podem se adaptar a diferentes condições de rede e dar suporte a três vezes a produtividade de áudio e vídeo, mantendo a qualidade aceitável. Não suponha que essa adaptabilidade mascara o problema quando uma rede está sub-provisionada. Em uma rede sub-provisionada, a capacidade dos pontos de extremidade de mídia do Skype for Business Server lidar dinamicamente com diferentes condições de rede (por exemplo, perda de pacotes alta temporária) é reduzida.

- Para links de rede em que o provisionamento é muito caro e difícil, talvez seja preciso considerar o provisionamento para um volume menor de tráfego. Nesse cenário, deixe a elasticidade dos pontos de extremidade de mídia do Skype for Business Server absorver a diferença entre o volume de tráfego e o nível de tráfego de pico, ao custo de alguma redução na qualidade da voz. Além disso, haverá uma diminuição na sala de reunião, caso contrário, disponível para absorver picos súbitos de tráfego.

- Para links que não podem ser provisionados corretamente a curto prazo (por exemplo, um site que usa links WAN muito ruins), considere desabilitar o vídeo para determinados usuários.

- Provisione a rede para garantir um atraso máximo de ponta a ponta (latência) de 150 milissegundos (ms) sob carga de pico. A latência é o único dano na rede que os componentes de mídia do Skype for Business Server não podem reduzir, e é importante encontrar e eliminar os pontos fracos.

- Para servidores que estão executando software antivírus, inclua todos os servidores que estão executando o Skype for Business Server na lista de exceções para fornecer melhor desempenho e qualidade de áudio.

## <a name="ipsec-exceptions"></a>Exceções do IPsec

Nas redes corporativas em que o protocolo IPsec (consulte a RFC 4301-4309 da IETF) foi implantado, o protocolo IPsec deverá ser desabilitado no intervalo de portas usado para a entrega de áudio, vídeo e vídeo panorama. A recomendação vem da necessidade de evitar qualquer atraso na alocação das portas de mídia por causa da negociação IPsec.

A tabela a seguir explica as configurações de exceções recomendadas do IPsec.

**Exceções recomendadas do IPsec**

|Nome da regra |IP de origem |IP de destino |Protocolo |Porta de origem |Porta de destino |Requisito de autenticação |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|Entrada interna do Servidor de Borda A/V|Qualquer  |Interno do Servidor de Borda A/V|UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Entrada externa do Servidor de Borda A/V|Qualquer  |Externo do Servidor de Borda A/V|UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Saída interna do Servidor de Borda A/V|Interno do Servidor de Borda A/V  |Externo do Servidor de Borda A/V |UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Saída externa do Servidor de Borda A/V|Externo do Servidor de Borda A/V |Qualquer |UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Entrada do Servidor de Mediação|Qualquer  |Servidor(es) de mediação |UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Saída do Servidor de Mediação|Servidor(es) de mediação  |Qualquer|UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Entrada do Atendedor de Conferência|Qualquer  |Servidor Front End executando o Atendedor de Conferência |UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Saída do Atendedor de Conferência|Servidor Front End executando o Atendedor de Conferência  |Qualquer|UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Entrada de Conferência A/V|Qualquer|Servidores Front-End|UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Saída de Conferência A/V|Servidores Front-End|Qualquer|UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Entrada do Exchange|Qualquer|Unificação de Mensagens do Exchange|UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Entrada dos Servidores de Compartilhamento de Aplicativo|Qualquer|Servidores de Compartilhamento de Aplicativos|UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Saída do Servidor de Compartilhamento de Aplicativos.|Servidores de Compartilhamento de Aplicativos| Qualquer |UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Saída do Exchange|Unificação de Mensagens do Exchange|Qualquer|UDP e TCP|Qualquer |Qualquer |Não autenticar|
|Clientes| Qualquer  |Qualquer|UDP e TCP|Qualquer |Qualquer |Não autenticar|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Requisitos de rede de conferência
<a name="Conf_req"> </a>

A largura de banda usada para baixar o conteúdo de conferência do servidor do IIS (Serviços de Informações da Internet) depende do tamanho do conteúdo. Você pode optar por monitorar o uso real e ajustar o planejamento da largura de banda de acordo.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de largura de banda de rede para tráfego de mídia
<a name="Conf_req"> </a>

Uma parte importante do planejamento de rede é garantir que sua rede possa lidar com o tráfego de mídia gerado pelo Skype for Business Server. Esta seção ajuda você a planejar esse tráfego de mídia.

### <a name="media-traffic-network-usage"></a>Uso da rede de tráfego de mídia
<a name="Net_req"> </a>

O uso da largura de banda do tráfego de mídia pode ser desafiador para calcular devido ao número de diferentes variáveis, como o uso de codec, resolução e níveis de atividade. O uso da largura de banda é uma função do codec usado e da atividade do fluxo, que pode variar entre os cenários. A tabela a seguir lista os codecs de áudio normalmente usados em cenários do Skype for Business Server.

**Largura de banda do codec de áudio**

|**Codec de áudio**|**Cenário**|**Taxa de bits de carga de áudio (KBPS)**|**Apenas carga de áudio da largura de banda e cabeçalho IP (Kbps)**|**Carga de áudio da largura de banda, cabeçalho IP, UDP, RTP e SRTP (Kbps)**|**Carga de áudio da largura de banda, cabeçalho IP, UDP, RTP, SRTP e correção de erro de encaminhamento (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda larga RTAudio  <br/> |Ponto a ponto  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|Banda estreita RTAudio  <br/> |PSTN ponto a ponto  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Conferência  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|Estéreo G.722  <br/> |Conferência ponto a ponto  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |PSTN, Conferência  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Conferência  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|BANDA LARGA  <br/> |Ponto a ponto  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|BANDA LARGA  <br/> |Ponto a ponto  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|BANDA LARGA  <br/> |Ponto a ponto  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|BANDA LARGA/banda estreita  <br/> |Ponto a ponto  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |

> [!NOTE]
> As chamadas PSTN do cliente Skype for Business geralmente usam o codec G.711, que exige uma largura de banda alta. Se a largura de banda suficiente não estiver disponível para esse codec, as chamadas poderão falhar com um erro semelhante ao seguinte nos logs de mídia: um codec deve estar **habilitado, hr: c0042004.** Os logs de mídia (arquivos .blog) são criptografados e podem ser decodificados somente pela equipe de suporte da Microsoft.

Os números de largura de banda na tabela anterior se baseiam na geração de pacotes de 20 ms (50 pacotes por segundo) e para os codecs Siren e G.722 incluem a sobrecarga adicional do SRTP (protocolo de transporte em tempo real seguro) nos cenários de conferência e supõem que o fluxo está 100% ativo. A Correção de Erro de Encaminhamento (FEC) é usada dinamicamente quando há perda de pacotes no link para ajudar a manter a qualidade do fluxo de áudio.

A versão estéreo do codec G.722 é usada por sistemas baseados no Lync Room System, que usa um único microfone estéreo ou um par de microfones mono para permitir que os ouvintes diferenciem melhor vários alto-falantes na sala de reunião.

**Largura de banda de resolução de vídeo**

|**Codec de vídeo**|**Resolução e taxa de proporção**|**Taxa de bits máxima de carga de vídeo (Kbps)**|**Taxa de bits mínima de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320x180 (16:9)  <br/> 212x160 (4:3)  <br/> |250  <br/> |15   <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480x270 (16:9)  <br/> 424x320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640x360 (16:9)  <br/> 640x480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848x480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960x540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280x720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960x144 (20:3)  <br/> |500  <br/> |15   <br/> |
|H.264  <br/> |1280x192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920x288 (20:3)  <br/> |2000  <br/> |500  <br/> |

O codec padrão para vídeo é o padrão H.264/MPEG-4 Part 10 Advanced Video Coding, juntamente com suas extensões escalonáveis de codificação de vídeo para escalabilidade temporal. Para manter a interoperabilidade com clientes herdado, o codec RTVideo ainda é usado para chamadas ponto a ponto entre o Skype for Business Server e clientes herdado. Em sessões de conferência com o Skype for Business Server e clientes herdado, o ponto de extremidade do Skype for Business Server pode codificar o vídeo usando codecs de vídeo e enviar o bitstream H.264 para os clientes do Skype for Business Server e o bitstream RTVideo para clientes herdado.

A largura de banda necessária depende da resolução, qualidade, taxa de quadros e quantidade de movimento ou alteração na imagem. Para cada resolução, há duas taxas de bits pertinentes:

- **Taxa de bits de carga máxima** Essa é a taxa de bits que um ponto de extremidade usará para resolução na taxa de quadros máxima. Esse é o valor que permite a maior qualidade de vídeo e som.

- **Taxa de bits de carga mínima** Esta é a taxa de bits abaixo da qual um ponto de extremidade do Skype for Business Server alterna para a próxima resolução inferior. Para garantir uma determinada resolução, a taxa de bits de carga de vídeo disponível não deve ficar abaixo dessa taxa de bits mínima para essa resolução. Esse valor ajuda você a entender o menor valor possível se a taxa de bits máxima não estiver disponível ou for prática. Para alguns usuários, um vídeo com taxa de bits tão baixa pode oferecer uma experiência de vídeo inaceitável, portanto, tenha cuidado com essas taxas de bits mínimas de carga de vídeo. Observe que, para cenas de vídeo estáticas e inalteráveis, a taxa de bits real pode ficar temporariamente abaixo da taxa de bits mínima.

O Skype for Business Server oferece suporte a muitas resoluções. Isso permite que o Skype for Business Server se ajuste a diferentes capacidades de cliente de recebimento e largura de banda de rede. A taxa de proporção padrão para o Skype for Business Server é 16:9. A taxa de proporção 4:3 herdada ainda tem suporte para webcams que não permitem a captura na taxa de proporção 16:9.

O FEC de vídeo é sempre incluído na taxa de bits de carga de vídeo quando usado para que não haja valores separados com FEC de vídeo e sem FEC de vídeo.

Os pontos de extremidade não transmitem pacotes de áudio ou vídeo continuamente. Dependendo do cenário, existem níveis diferentes de atividade de fluxo que indicam a frequência com que os pacotes são enviados por um fluxo. A atividade de um fluxo depende da mídia e do cenário e não depende do codec que está sendo usado. Em um cenário ponto a ponto:

- Os pontos de extremidade só enviam fluxos de áudio quando os usuários falam.

- Ambos os participantes recebem fluxos de áudio.

- Se o vídeo for usado, ambos os pontos de extremidade enviarão e receberão fluxos de vídeo durante a chamada.

- Para cenas de vídeo estáticas, a taxa de bits real pode ser temporariamente muito baixa, pois o codec de vídeo ignorará as regiões de codificação do vídeo sem uma alteração desde o exemplo anterior.

Em um cenário de conferência:

- Os pontos de extremidade enviam fluxos de áudio apenas quando os usuários falam.

- Todos os participantes recebem fluxos de áudio.

- Se o vídeo for usado, todos os participantes poderão receber até cinco fluxos de vídeo e um fluxo de vídeo panorâmico (por exemplo, taxa de proporção 20:3). Por padrão, os cinco fluxos de vídeo são baseados no histórico ativo do orador, mas os usuários também podem selecionar manualmente os participantes dos quais eles querem receber um fluxo de vídeo. Se vários vídeos estiver habilitado, o requisito de resolução e largura de banda para cada um dos fluxos de vídeo será menor.

- Cada participante que liga o fluxo de vídeo de envio do usuário enviará um ou mais fluxos de vídeo. O Skype for Business Server tem a capacidade de enviar até cinco fluxos de vídeo para otimizar a qualidade do vídeo para todos os clientes receptores. O número real de fluxos de vídeo enviados é determinado pelo remetente com base na capacidade da CPU, na largura de banda do uplink disponível e no número de clientes receptores que solicitam um determinado fluxo de vídeo. O caso mais comum é que um fluxo de vídeo H.264 e um fluxo de vídeo RTVideo estão sendo enviados caso um cliente herdado insisse na conferência. Outro cenário comum é que vários fluxos de vídeo H.264 (por exemplo, com resoluções de vídeo diferentes) são enviados para acomodar solicitações de receptores diferentes.

Além da largura de banda necessária par ao tráfego do protocolo de transporte em tempo real (RTP) para mídia de áudio e vídeo, a largura de banda é necessária para o protocolo de controle de transporte em tempo real (RTCP). O RTCP é usado para relatar diagnósticos e controle fora da banda do fluxo RTP. Para planejamento, use os números da largura de banda da seguinte tabela para tráfego RTCP. Esses valores representam a largura de banda máxima usada para RTCP e são diferentes para fluxos de áudio e vídeo devido às diferenças nos dados de controle

**Largura de banda RTCP**

|**Mídia**|**Largura de banda máxima RTCP (Kbps)**|
|:-----|:-----|
|Áudio  <br/> |5   <br/> |
|Vídeo (somente H.264 ou RTVideo sendo enviado/recebido)  <br/> |10   <br/> |
|Vídeo (H.264 e RTVideo enviados/recebidos)  <br/> |15   <br/> |

Para planejamento de capacidade, as duas estatísticas a seguir são de interesse:

- **Largura de banda máxima sem FEC** A largura de banda máxima que um fluxo consumirá. Isso inclui a atividade típica do fluxo e o codec típico que é usado no cenário sem FEC. Esta é a largura de banda quando o fluxo está a 100% de atividade e não há perda de pacotes acionando o uso do FEC. Isso é útil para calcular quanta largura de banda deve ser alocada para permitir que o codec seja usado em um determinado cenário. Não se espera que o FEC seja um requisito em uma rede gerenciada.

- **Largura de banda máxima com FEC** A largura de banda máxima que um fluxo consome. Isso inclui a atividade típica do fluxo e o codec típico usado no cenário com FEC. Esta é a largura de banda quando o fluxo está a 100% de atividade e há perda de pacote acionando o uso do FEC para melhorar a qualidade. Isso é útil para calcular quanta largura de banda deve ser alocada para permitir que o codec seja usado em um determinado cenário e permitir o uso do FEC para preservar a qualidade em condições de perda de pacotes.

As tabelas a seguir também lista um valor de largura de banda adicional, **Largura de banda típica**. Essa é a largura de banda média que um fluxo consome. Isso inclui a atividade típica do fluxo e o codec típico usado no cenário. Essa largura de banda pode ser usada para aproximar a largura de banda consumida pelo tráfego de mídia em um momento específico, mas não deve ser usada para planejamento de capacidade, pois as chamadas individuais excederão esse valor quando o nível de atividade for maior que a média. A largura de banda típica do fluxo de vídeo nas tabelas abaixo baseia-se em uma mistura de diferentes resoluções de vídeo conforme observado em dados medidos do cliente, e instalações menores provavelmente terão números reais que diferem dos dados da tabela. Por exemplo, em sessões ponto a ponto, a maioria dos usuários usaria a janela de renderização de vídeo padrão, enquanto alguma porcentagem de usuários aumentaria ou maximizaria o aplicativo Skype for Business Server para permitir melhores resoluções de vídeo.

As tabelas a seguir fornecem valores para os vários cenários.

**Planejamento de capacidade de áudio/vídeo para sessões ponto a ponto**

|**Mídia**|**Codec**|**Largura de banda de fluxo típico (Kbps)**|**Largura de banda de fluxo máximo sem FEC**|**Largura de banda de fluxo máximo com FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |Banda ampla RTAudio  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Áudio  <br/> |Banda estreita RTAudio  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Áudio  <br/> |BANDA LARGA  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Vídeo principal ao chamar pontos de extremidade do Skype for Business Server  <br/> |H.264  <br/> |460  <br/> |4010 (para resolução máxima de 1920x1080)  <br/> |Já incluído  <br/> |
|Vídeo principal ao chamar pontos de extremidade do Lync 2010 ou Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (para resolução máxima de 1280 x 720)  <br/> |Já incluído  <br/> |
|Vídeo panorâmico ao chamar pontos de extremidade do Skype for Business Server  <br/> |H.264  <br/> |190  <br/> |2010 (para resolução máxima de 1920x288)  <br/> |Já incluído  <br/> |
|Vídeo panorâmico ao chamar pontos de extremidade do Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (para resolução máxima de 960 x 144)  <br/> |Já incluído  <br/> |

**Planejamento de capacidade de áudio/vídeo para conferências**

|**Mídia**|**Codec típico**|**Largura de banda de fluxo típico (Kbps)**|**Largura de banda de fluxo máximo sem FEC**|**Largura de banda de fluxo máximo com FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Áudio  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|Recebimento de vídeo principal  <br/> |H.264 e RTVideo¹  <br/> |260  <br/> |8015  <br/> |Não aplicável  <br/> |
|Envio de vídeo principal  <br/> |H.264 e RTVideo  <br/> |270  <br/> |8015  <br/> |Não aplicável  <br/> |
|Recebimento de vídeo panorâmico  <br/> |H.264 e RTVideo  <br/> |190  <br/> |2010 (para resolução máxima de 1920x288)  <br/> |Não aplicável  <br/> |
|Envio de vídeo panorâmico  <br/> |H.264 e RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Não aplicável  <br/> |

1. O vídeo RT é enviado além de H.264 quando os clientes do Lync 2010 estão conectados à conferência.

2. Se houver vários fluxos, eles compartilharão dinamicamente a largura de banda alocada.

Para o vídeo principal, a largura de banda típica do fluxo é a largura de banda agregada sobre todos os fluxos de vídeo recebidos e o fluxo máximo é a largura de banda sobre todos os fluxos de vídeo de envio. Mesmo com vários fluxos de vídeo, a largura de banda típica de vídeo é menor do que no cenário ponto a ponto porque muitas conferências de vídeo estão usando o compartilhamento de conteúdo que leva a janelas de vídeo muito menores e, portanto, a resoluções de vídeo menores. A largura de banda de carga de vídeo agregada máxima suportada é de 8000 Kbps para fluxos de envio e recebimento que seriam usados (por exemplo, se houver dois fluxos de vídeo de 1920 x 1080p de entrada). Os valores máximos são raramente vistos em implementações reais.

Ao criar uma conferência com vários participantes que usa o recurso de modo de exibição de galeria, a utilização da largura de banda aumenta inicialmente à medida que os participantes participam e, em seguida, diminui à medida que as resoluções são retiradas para caber dentro do máximo.

||**2 Participantes**|**3 Participantes**|**4 Participantes**|**5 Participantes**|**6 Participantes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Resoluções máximas recebidas** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Taxa de bits média total** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Taxa de bits máxima total** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

A largura de banda típica do fluxo para vídeo panorâmico é baseada em dispositivos que só transmitem vídeo panorâmico de 960 x 144. Espere que a largura de banda típica do fluxo aumente ao usar dispositivos com vídeo panorâmico de 1920 x 288.

**Planejamento de capacidade de áudio para PSTN**

|**Mídia**|**Codec típico**|**Largura de banda de fluxo típico (Kbps)**|**Largura de banda de fluxo máximo sem FEC**|**Largura de banda de fluxo máximo com FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |G.711 (isso inclui participantes PSTN em conferências)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Áudio  <br/> |Banda estreita RTAudio  <br/> |30.9  <br/> |44.8  <br/> |56.6  <br/> |

Os números de largura de banda da rede nestas tabelas representam apenas o tráfego de uma via e inclui 5 Kbps de sobrecarga de tráfego RTCP para cada fluxo.

## <a name="managing-quality-of-service"></a>Gerenciando a Qualidade de Serviço
<a name="man_QOS"> </a>

A Qualidade de Serviço (QoS) é uma tecnologia de rede usada em algumas organizações para ajudar a proporcionar uma experiência ideal para comunicações de áudio e vídeo do usuário final. A QoS é usada com mais frequência em redes onde a largura de banda é limitada: com um grande número de pacotes de rede competendo por uma quantidade relativamente pequena de largura de banda disponível, a QoS permite que os administradores atribuam prioridades mais altas a pacotes que transportam dados de áudio ou vídeo. Ao dar a esses pacotes uma prioridade mais alta, é provável que as comunicações de áudio e vídeo sejam concluídas mais rapidamente e com menos interrupções do que sessões de rede envolvendo coisas como transferências de arquivos, navegação na Web ou backups de banco de dados. Isso ocorre porque os pacotes de rede usados para transferências de arquivos ou backups de bancos de dados recebem uma atribuição de prioridade de "melhor esforço".

> [!NOTE]
> Como regra, a QoS se aplica somente a sessões de comunicação em sua rede interna. Ao implementar a QoS, você configura seus servidores e roteadores para dar suporte à marcação de pacotes de uma maneira específica que pode não ter suporte na Internet ou em outras redes. Mesmo que a Qualidade de Serviço seja suportada em outras redes, não há garantia de que a QoS será configurada exatamente da mesma maneira que você configurou o serviço. Se você estiver usando MPLS, precisará trabalhar com seu provedor MPLS.

O Skype for Business Server não exige QoS, mas é altamente recomendável. Se você tiver problemas de perda de pacotes na rede, suas soluções disponíveis são para adicionar mais largura de banda ou implementar qoS. Se não for possível adicionar mais largura de banda, a implementação da QoS pode ser sua única tarifa para resolver o problema.

O Skype for Business Server oferece suporte total à QoS: isso significa que as organizações que já estão usando a QoS podem integrar facilmente o Skype for Business Server à infraestrutura de rede existente. Para fazer isso, você deve seguir estas etapas:

- [Habilitando a QoS no Skype for Business Server para dispositivos que não são baseados no Windows.](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md) Por padrão, a QoS está desativada para computadores e outros dispositivos (como iPhones) que executam outros sistemas operacionais. Embora você possa usar o Skype for Business Server para habilitar e desabilitar a Qualidade de Serviço para dispositivos, normalmente não é possível usar o produto para modificar os códigos DSCP usados por esses dispositivos.

- [Configurar intervalos de porta e uma política de Qualidade de Serviço para](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md)seus servidores de Conferência, Aplicativo e Mediação. É necessário reservar um conjunto exclusivo de portas para tipos de pacotes diferentes, como áudio e vídeo. Ao usar o Skype for Business Server, você não habilita ou desabilita a QoS definindo um valor de propriedade como True ou False. Em vez disso, você habilita a QoS configurando intervalos de porta e, em seguida, criando e aplicando a Política de Grupo. Se você decidir posteriormente não usar a QoS, poderá "desabilitar" a QoS removendo os objetos de Política de Grupo apropriados.

- [Configurando intervalos de portas e uma política de Qualidade de Serviço para seus Servidores de Borda.](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md) Embora não seja necessário, você pode configurar seus servidores de borda para usar os mesmos intervalos de porta que os outros servidores. A configuração de uma política de QoS só será feita para o lado interno dos servidores de Borda. Isso porque a QoS foi projetada para uso em sua rede interna e não na Internet.

- [Configurar intervalos de porta e uma política de Qualidade de Serviço para seus clientes no Skype for Business Server.](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md) Esses intervalos de porta se aplicam somente a computadores cliente e são normalmente diferentes dos intervalos de porta configurados em seus servidores. Observe que o Skype for Business Server não dá suporte a QoS para sistemas operacionais Windows diferentes do Windows 10.


> [!NOTE]
> Se você estiver usando o Windows Server 2012 ou o Windows Server 2012 R2, talvez esteja interessado no novo conjunto de cmdlets do Windows PowerShell disponível para gerenciar qoS nessa plataforma. Para obter mais informações, [consulte Cmdlets de QoS de rede no Windows PowerShell.](https://go.microsoft.com/fwlink/p/?LinkId=285379)

A QoS também é abordada no whitepaper [Network Planning, Monitoring, and Troubleshooting with Lync Server](https://www.microsoft.com/download/details.aspx?id=39084) with additional details and depth. Embora o conteúdo se refira explicitamente ao Lync 2010 e ao Lync 2013, as considerações para o Skype for Business Server não foram alteradas.

## <a name="see-also"></a>Confira também
<a name="man_QOS"> </a>

[Plano para IPv6 no Skype for Business](ipv6.md)

[Requisitos de balanceamento de carga para o Skype for Business](load-balancing.md)

[Requisitos de DNS para o Skype for Business Server](dns.md)
