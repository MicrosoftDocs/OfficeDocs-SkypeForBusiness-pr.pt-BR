---
title: Plan network requirements for Skype for Business
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
ms.openlocfilehash: b7b9c7e239aab5d395fcdadf0cb254df4e13cecd
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41802021"
---
# <a name="plan-network-requirements-for-skype-for-business"></a>Plan network requirements for Skype for Business

**Resumo:** Examine as considerações do componente de rede abaixo antes de implementar o Skype for Business Server.

As informações contidas nestes tópicos também são abordadas no White Paper [planejamento de rede, monitoramento e solução de problemas com o Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) , com detalhes adicionais e profundidade. Embora o conteúdo se refira explicitamente ao Lync 2010 e ao Lync 2013, as considerações para o Skype for Business Server não são alteradas.

Da mesma forma, se a sua rede envolver Wi-Fi, bem como acesso com fio, o White paper que [fornece comunicações em tempo real do Lync 2013 por Wi-Fi](https://www.microsoft.com/en-us/download/details.aspx?id=36494) é uma boa referência e é igualmente aplicável ao Skype for Business Server.

<!-- Deprecated tools
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).    -->

## <a name="server-hardware"></a>Hardware de servidor
<a name="S_hard"> </a>

O adaptador de rede de cada servidor na topologia do Skype for Business Server deve dar suporte a pelo menos 1 gigabit por segundo (Gbps). Em geral, você deve conectar todas as funções de servidor dentro da topologia do Skype for Business Server usando uma rede local de baixa latência e alta largura de banda (LAN). O tamanho da LAN depende do tamanho da topologia:

- Em topologias de edição padrão, os servidores devem estar em uma rede que suporte Ethernet de 1 Gbps ou equivalente.

- Nas topologias da Enterprise Edition, a maioria dos servidores deve estar em uma rede com suporte para mais de 1 Gbps, especialmente quando oferecer suporte à conferência de áudio/vídeo (A/V) e compartilhamento de aplicativos.

Para a integração com Rede Telefônica Pública Comutada (PSTN), você pode usar linhas T1/E1 ou tronco SIP.

## <a name="audiovideo-network-requirements"></a>Requisitos de rede para áudio/vídeo
<a name="AV_req"> </a>

Os requisitos de rede para o áudio/vídeo (A/V) em uma implantação do Skype for Business Server incluem o seguinte:

- Se você estiver implantando um servidor de borda único ou um pool de bordas usando o balanceamento de carga de DNS, poderá configurar o firewall _externo_ para executar a NAT (conversão de endereços de rede). Não é possível configurar o firewall _internal_ para executar NAT. Para obter detalhes, consulte [planejamento de portabilidade e firewall](../edge-server-deployments/edge-environmental-requirements.md#port-and-firewall-planning).

    > [!IMPORTANT]
    > Se você tiver um pool de bordas e estiver usando um balanceador de carga de hardware, será necessário usar endereços IP públicos nos servidores de borda e não poderá usar o NAT para os servidores ou o pool em seu dispositivo compatível com NAT (por exemplo, um utilitário de firewall ou uma opção de LAN. Para obter detalhes, consulte [cenários do servidor de borda no Skype for Business Server](../edge-server-deployments/scenarios.md).

- Se a sua organização usa uma infraestrutura de QoS (Qualidade de Serviço), o subsistema de mídia é projetado para funcionar com essa infraestrutura existente.

- Caso você utilize o protocolo IPsec, é recomendável desabilitá-lo nos intervalos de portas usados para o tráfego de A/V. Para obter detalhes, consulte [exceções de IPSec](#ipsec-exceptions).

Para melhor qualidade da mídia, siga este procedimento:

- Provisione os links de rede para suportarem uma taxa de transferência de 65 quilobits por segundo (Kbps) por transmissão de áudio e 500 Kbps por transmissão de vídeo, se estiverem habilitadas, durante os períodos de pico. Uma sessão bidirecional de áudio ou vídeo usa duas transmissões, então uma simples conexão de áudio/vídeo exigirá 130K Kbps para cobrir cada transmissão. O vídeo da mesma maneira vai usar o total de 1000 kbps para transportar uma conexão de upstream e downstream.

- Para lidar com picos inesperados de tráfego e maior utilização ao longo do tempo, os pontos de extremidade de mídia do Skype for Business Server podem adaptar-se a várias condições de rede e dar suporte a três vezes a taxa de transferência de áudio e vídeo mantendo ainda a qualidade aceitável. Não presuma que essa adaptabilidade mascarará o problema quando uma rede estiver sub-provisionada. Em uma rede subprovisionada, a capacidade dos pontos de extremidade de mídia do Skype for Business Server para lidar dinamicamente com condições de rede variáveis (por exemplo, perda de pacotes de alta capacidade temporária) é reduzida.

- Para vínculos de rede em que o provisionamento envolve alto custo e dificuldade, considere a opção de provisionar para um volume menor de tráfego. Nesse cenário, permita que a elasticidade dos pontos de extremidade de mídia do Skype for Business Server absorve a diferença entre o volume de tráfego e o nível de tráfego de pico, ao custo de uma redução na qualidade de voz. Além disso, haverá uma diminuição na reserva dinâmica que, de outra forma, estaria disponível para absorver picos súbitos de tráfego.

- Para os vínculos que não podem ser provisionados corretamente a curto prazo (por exemplo, um local que usa vínculos de WAN de péssima qualidade), considere a possibilidade de desabilitar o vídeo para determinados usuários.

- Provisione a rede para assegurar um atraso máximo de ponta a ponta (latência) de 150 ms (milissegundos) sob carga máxima. Latência é a única deficiência da rede que os componentes de mídia do Skype for Business Server não podem reduzir e é importante localizar e eliminar os pontos fracos.

- Para servidores que estão executando o software antivírus, inclua todos os servidores que estão executando o Skype for Business Server na lista de exceções para fornecer desempenho e qualidade de áudio ideais.

## <a name="ipsec-exceptions"></a>Exceções IPsec

Para redes corporativas onde a segurança do protocolo Internet (IPsec) (consulte IETF RFC 4301-4309) foi implantada, o IPsec deve ser desabilitado no intervalo de portas usado para a entrega de vídeo de áudio, vídeo e panorama. Essa recomendação existe porque é necessário evitar atrasos na alocação das portas de mídia por causa da negociação IPsec.

A tabela a seguir explica as configurações de exceções recomendadas do IPsec.

**Exceções recomendadas do IPsec**

|Nome da regra |IP de origem |IP de destino |Protocolo |Porta de origem |Porta de destino |Requisito de autenticação |
|:--- |:--- |:--- |:--- |:---|:---|:--- |
|Entrada interna do Servidor de Borda A/V|Qualquer um  |Interno do Servidor de Borda A/V|UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Entrada externa do Servidor de Borda A/V|Qualquer um  |Externo do Servidor de Borda A/V|UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Saída interna do Servidor de Borda A/V|Interno do Servidor de Borda A/V  |Externo do Servidor de Borda A/V |UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Saída externa do Servidor de Borda A/V|Externo do Servidor de Borda A/V |Qualquer um |UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Entrada do Servidor de Mediação|Qualquer um  |Servidor (es) de mediação |UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Saída do Servidor de Mediação|Servidor (es) de mediação  |Qualquer um|UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Entrada do Atendedor de Conferência|Qualquer um  |Servidor Front-End executando o Atendedor de Conferência |UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Saída do Atendedor de Conferência|Servidor Front-End executando o Atendedor de Conferência  |Qualquer um|UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Entrada de Conferência A/V|Qualquer um|Servidores Front-End|UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Saída de Conferência A/V|Servidores Front-End|Qualquer um|UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Entrada do Exchange|Qualquer um|Unificação de Mensagens do Exchange|UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Entrada dos Servidores de Compartilhamento de Aplicativo|Qualquer um|Servidores de Compartilhamento de Aplicativos|UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Saída do Servidor de Compartilhamento de Aplicativos|Servidores de Compartilhamento de Aplicativos| Qualquer um |UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Saída do Exchange|Unificação de Mensagens do Exchange|Qualquer um|UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|Clientes| Qualquer um  |Qualquer um|UDP e TCP|Qualquer um  |Qualquer um |Não autenticar|
|         |         |         |         |         |         |         |


## <a name="conferencing-network-requirements"></a>Requisitos da rede de conferência
<a name="Conf_req"> </a>

A largura de banda usada para baixar o conteúdo da conferência do servidor dos serviços de informações da Internet (IIS) depende do tamanho do conteúdo. Você pode optar por monitorar o uso real e ajustar a largura de banda conforme for necessário.

## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de largura de banda de rede para tráfego de mídia
<a name="Conf_req"> </a>

Uma parte importante do planejamento de rede é garantir que sua rede possa manipular o tráfego de mídia gerado pelo Skype for Business Server. Esta seção ajuda a você a se planejar para esse tráfego.

### <a name="media-traffic-network-usage"></a>Uso da rede de tráfego de mídia
<a name="Net_req"> </a>

O cálculo do uso da largura de banda do tráfego de mídia pode ser desafiador devido às diferentes variáveis, como o uso de codec, resolução e níveis de atividade. O uso da largura de banda é uma função do codec que é usado e da atividade do fluxo, que podem variar nos cenários. A tabela a seguir lista os codecs de áudio geralmente usados nos cenários do Skype for Business Server.

**Largura de banda do codec de áudio**

|**Codec de áudio**|**Cenário**|**Taxa de bits da carga de áudio (KBPS)**|**Apenas carga de áudio da largura de banda e cabeçalho IP (Kbps)**|**Carga de áudio da largura de banda, cabeçalho IP, UDP, RTP e SRTP (Kbps)**|**Carga de áudio da largura de banda, cabeçalho IP, UDP, RTP, SRTP e correção de erro de encaminhamento (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda ampla RTAudio  <br/> |Ponto a ponto  <br/> |29,0  <br/> |45,0  <br/> |57,0  <br/> |86,0  <br/> |
|Banda estreita RTAudio  <br/> |PSTN ponto a ponto  <br/> |11,8  <br/> |27,8  <br/> |39,8  <br/> |51,6  <br/> |
|G.722  <br/> |Conferência  <br/> |64,0  <br/> |80,0  <br/> |95,6  <br/> |159,6  <br/> |
|Estéreo G.722  <br/> |Conferência ponto a ponto  <br/> |128,0  <br/> |144,0  <br/> |159,6  <br/> |223,6  <br/> |
|G.711  <br/> |Conferência PSTN  <br/> |64,0  <br/> |80,0  <br/> |92,0  <br/> |156,0  <br/> |
|Siren  <br/> |Conferência  <br/> |16,0  <br/> |32,0  <br/> |47,6  <br/> |63,6  <br/> |
|Banda larga SILK  <br/> |Ponto a ponto  <br/> |36,0  <br/> |52,0  <br/> |64,0  <br/> |100,0  <br/> |
|Banda larga SILK  <br/> |Ponto a ponto  <br/> |26,0  <br/> |42,0  <br/> |54,0  <br/> |80,0  <br/> |
|Banda larga SILK  <br/> |Ponto a ponto  <br/> |20,0  <br/> |36,0  <br/> |48,0  <br/> |68,0  <br/> |
|SILK banda larga/banda estreita  <br/> |Ponto a ponto  <br/> |13,0  <br/> |29,0  <br/> |41,0  <br/> |54,0  <br/> |

> [!NOTE]
> As chamadas PSTN do cliente Skype for Business geralmente usam o codec G. 711, que requer uma alta largura de banda. Se não houver largura de banda suficiente disponível para esse codec, as chamadas poderão falhar com um erro semelhante ao seguinte nos logs de mídia: **pelo menos um codec deve estar habilitado, hr: c0042004**. Os logs de mídia (arquivos. Blogs) são criptografados e podem ser decodificados apenas pela equipe de suporte da Microsoft.

Os números da largura de banda na tabela anterior são baseados na geração de pacotes de 20 ms (50 pacotes por segundo) e para os codecs G.722 e Siren incluem a sobrecarga adicional do protocolo SRTP nos cenários de conferência e supõe que o fluxo está 100% ativo. O FEC (correção de erro de encaminhamento) é dinamicamente usado quando há uma perda de pacotes no link para ajudar a manter a qualidade dos fluxos de áudio.

A versão estéreo do codec G.722 é usada pelos sistemas baseados no Lync Room System, que usa um único microfone estéreo ou um par de microfones mono para permitir que os ouvintes possam distinguir melhor várias pessoas falando na sala de reunião.

**Largura de banda da resolução do vídeo**

|**Codec de vídeo**|**Resolução e taxa de proporção**|**Taxa de bits máxima de carga de vídeo (Kbps)**|**Taxa de bits mínima de carga de vídeo (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320 x 180 (16:9)  <br/> 212 x 160 (4:3)  <br/> |250  <br/> |15  <br/> |
|H.264/RTVideo  <br/> |424x240 (16:9)  <br/> 320x240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480 x 270 (16:9)  <br/> 424 x 320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640 x 360 (16:9)  <br/> 640 x 480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848 x 480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960 x 540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280 x 720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920 x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960 x 144 (20:3)  <br/> |500  <br/> |15  <br/> |
|H.264  <br/> |1280 x 192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |

Este codec padrão é o padrão de Codificação de Vídeo Avançada H.264/MPEG-4 Parte 10, juntamente suas extensões de codificação de vídeo escalonável para escalabilidade temporal. Para manter a interoperabilidade com clientes herdados, o codec RTVideo ainda é usado para chamadas ponto a ponto entre o Skype for Business Server e os clientes herdados. Em sessões de conferência com o Skype for Business Server e clientes herdados, o ponto de extremidade do Skype for Business Server pode codificar o vídeo usando os dois codecs de vídeo e enviar os Bitstream H. 264 para os clientes do Skype for Business Server e o RTVideo Bitstream para Legacy clientes.

A largura de banda exigida depende da resolução, qualidade, taxa de quadros e quantidade de movimento ou alteração na imagem. Para cada resolução, há duas taxas de bits pertinentes:

- **Taxa máxima de bits de carga** Esta é a taxa de bits que um ponto de extremidade usará para resolução na taxa de quadros máxima. Esse é o valor que permitirá a mais alta qualidade de som e vídeo.

- **Taxa mínima de bits de carga** Esta é a taxa de bits abaixo da qual um ponto de extremidade do Skype for Business Server mudará para a próxima resolução inferior. Para garantir um nível mínimo de resolução, a taxa de bits da carga do vídeo disponível não deve ser inferior a esta taxa de bits mínima para a resolução em questão. Este valor ajuda você a entender qual é o menor valor possível se a taxa de bits máxima não estiver disponível ou não for praticável. Para alguns usuários, vídeos com taxas de bits tão baixas proporcionar uma experiência inaceitável, portanto, tenha cuidado ao estabelecer a taxa de bits mínima para carga do vídeo. Observe que cenas do vídeo em que há pouco ou nenhum movimento, a taxa de bits real pode ficar temporariamente abaixo do limite mínimo.

O Skype for Business Server oferece suporte a muitas soluções. Isso permite que o Skype for Business Server seja ajustado para diferentes largura de banda de rede e recursos de cliente de recebimento. A taxa de proporção padrão do Skype for Business Server é o 16:9. A taxa de proporção 4:3 herdada ainda tem suporte para webcams que não permitem a captura na taxa de proporção de 16:9.

O FEC de vídeo é sempre incluído na taxa de bits de carga de vídeo quando é usado para que não haja valores separados com FEC de vídeo e sem FEC de vídeo.

Os pontos de extremidade não transmitem pacotes de áudio ou vídeo continuamente. De acordo com o cenário, existem níveis diferentes de atividade de fluxo que indicam a frequência com que os pacotes são enviados para um fluxo. A atividade de um fluxo depende da mídia e do cenário e não depende do codec que está sendo usado. Em um cenário ponto a ponto:

- Os pontos de extremidade enviam fluxos de áudio apenas quando os usuários falam.

- Ambos os participantes recebem fluxos de áudio.

- Se o vídeo for usado, ambos pontos de extremidade enviam e recebem fluxos de vídeo durante a chamada.

- Para cenas de vídeo estáticas, a taxa de bits real pode ficar muito baixa temporariamente, já que o codec de vídeo ignora regiões de codificação do vídeo se não houver alteração desde a amostra anterior.

Em um cenário de conferência:

- Os pontos de extremidade enviam fluxos de áudio apenas quando os usuários falam.

- Todos os participantes recebem fluxos de áudio.

- Se o vídeo for usado, todos os participantes podem receber até cinco fluxos de vídeo e um fluxo de vídeo panorâmico (por exemplo, taxa de proporção 20:3). Por padrão, os cinco fluxos de vídeo têm base no histórico do orador ativo, mas os usuários também podem selecionar manualmente os participantes de quem eles desejam receber fluxo de vídeo. Se a opção múltiplos vídeos for habilitada, o requisito de resolução e largura de banda para fluxo de vídeo será mais baixo.

- Cada participante que liga o fluxo de envio de vídeo do usuário envia um ou mais fluxos de vídeo. O Skype for Business Server tem a capacidade de enviar até cinco fluxos de vídeo para otimizar a qualidade de vídeo para todos os clientes de recebimento. A quantidade real de fluxos de vídeo enviados é determinada pelo remetente com base na capacidade da CPU, na largura de banda uplink disponível e na quantidade de clientes receptores que tenham selecionado um determinado fluxo de vídeo. O mais comum são os fluxos de vídeo H.264 e RTVideo enviados em caso de presença de clientes herdados na conferência. Outro cenário comum é o envio de diversos fluxos de vídeo H.264 (por exemplo, com a mesma resolução de vídeo) para acomodação de diferentes solicitações do receptor.

Além da largura de banda necessária para o tráfego do protocolo de transporte em tempo real (RTP) para mídia em áudio e vídeo, a largura de banda é necessária também para o protocolo de controle de transporte em tempo real (RTCP). O RTCP é usado para obter estatísticas e controle fora da banda para o fluxo RTP. Para fins de planejamento, use os números de largura de banda da tabela a seguir para verificar o tráfego RTCP. Esses valores representam a largura de banda máxima usada para RTCP e são diferentes nos fluxos de áudio e vídeo devido às diferenças nos dados de controle

**Largura de banda de RTCP**

|**Mídia**|**Largura de banda máxima de RTCP (Kbps)**|
|:-----|:-----|
|Áudio  <br/> |5  <br/> |
|Vídeo (somente H.264 ou RTVideo enviado/recebido)  <br/> |254  <br/> |
|Vídeo (somente H.264 ou RTVideo enviado/recebido)  <br/> |15  <br/> |

Para planejamento da capacidade, as duas larguras de banda mencionadas a seguir são:

- **Largura de banda máxima sem FEC** A largura de banda máxima que será consumida por um fluxo. Isso inclui a atividade típica do fluxo e o codec típico usado em cenário sem FEC. Trata-se da largura de banda quando o fluxo está 100% em atividade e não há perda de pacote que gere uso de FEC. É útil para a computação saber quanta largura de banda deve ser alocada para que o codec possa ser usado em um determinado cenário. O FEC não precisa ser um requisito em uma rede mapeada.

- **Largura de banda máxima com FEC** A largura de banda máxima que um fluxo consome. Isso inclui a atividade típica do fluxo e o codec típico usado em cenário com FEC. Trata-se da largura de banda quando o fluxo está 100% em atividade e há perda de pacote que gere uso de FEC para aprimorar a qualidade. É útil para a computação saber quanta largura de banda deve ser alocada para que o codec possa ser usado em um determinado cenário e permitir ouso de FEC para preservar as condições de qualidade em caso de perda de pacotes.

A tabela a seguir também lista outro valor da largura de banda, a **Largura de banda típica**. Trata-se da largura de banda consumida pelo fluxo. Isso inclui a atividade típica do fluxo e o codec típico usado no cenário. Essa largura de banda pode ser usada para aproximar a largura de banda consumida pelo tráfego de mídia em determinado momento, mas não deve ser usada no planejamento da capacidade porque chamadas individuais ultrapassarão seu valor quando o nível da atividade for superior à média. A largura debanda típica para o fluxo de vídeo indicada nas tabelas abaixo baseia-se em diferentes resoluções de vídeo, conforme observado em dados medidos de clientes. Por exemplo, em sessões ponto a ponto a maioria dos usuários usaria a janela de renderização de vídeo padrão, e alguma porcentagem dos usuários aumentaria ou maximizaria o aplicativo do Skype for Business Server para permitir melhor resolução de vídeo.

As tabelas abaixo fornecem valores de largura de banda para diversos cenários.

**Planejamento da capacidade de áudio/vídeo em sessões ponto a ponto**

|**Mídia**|**Codec**|**Largura de banda de fluxo típico (Kbps)**|**Largura de banda de fluxo máximo sem FEC**|**Largura de banda de fluxo máximo com FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |Banda ampla RTAudio  <br/> |39,8  <br/> |62  <br/> |91  <br/> |
|Áudio  <br/> |Banda estreita RTAudio  <br/> |29,3  <br/> |44,8  <br/> |56,6  <br/> |
|Áudio  <br/> |Banda larga SILK  <br/> |44,3  <br/> |69  <br/> |105  <br/> |
|Vídeo principal ao chamar pontos de extremidade do Skype for Business Server  <br/> |H.264  <br/> |460  <br/> |4010 (para resolução máxima de 1920 x 1080)  <br/> |Já incluído  <br/> |
|Vídeo principal ao ligar para os pontos de extremidade do Lync 2010 ou do Office Communicator 2007 R2  <br/> |RTVideo  <br/> |460  <br/> |2510 (para resolução máxima de 1280 x 720)  <br/> |Já incluído  <br/> |
|Vídeo panorâmico ao chamar pontos de extremidade do Skype for Business Server  <br/> |H.264  <br/> |190  <br/> |2010 (para resolução máxima de 1920 x 288)  <br/> |Já incluído  <br/> |
|Vídeo panorâmico ao ligar para pontos de extremidade do Lync 2010  <br/> |RTVideo  <br/> |190  <br/> |510 (para resolução máxima de 960 x 144)  <br/> |Já incluído  <br/> |

**Planejamento de capacidade de áudio/vídeo para conferências**

|**Mídia**|**Codec típico**|**Largura de banda de fluxo típico (Kbps)**|**Largura de banda de fluxo máximo sem FEC**|**Largura de banda de fluxo máximo com FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |G.722  <br/> |46,1  <br/> |100,6  <br/> |164,6  <br/> |
|Áudio  <br/> |Siren  <br/> |25,5  <br/> |52,6  <br/> |68,6  <br/> |
|Recepção de vídeo principal  <br/> |H.264 e RTVideo¹  <br/> |260  <br/> |8015  <br/> |Não aplicável  <br/> |
|Envio de vídeo principal  <br/> |H.264 e RTVideo  <br/> |270  <br/> |8015  <br/> |Não aplicável  <br/> |
|Recepção de vídeo panorâmico  <br/> |H.264 e RTVideo  <br/> |190  <br/> |2010 (para resolução máxima de 1920 x 288)  <br/> |Não aplicável  <br/> |
|Envio de vídeo panorâmico  <br/> |H.264 e RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Não aplicável  <br/> |

1. O vídeo RT é enviado além de H. 264 quando os clientes do Lync 2010 estão conectados à conferência.

2. Se houver vários fluxos, eles compartilharão dinamicamente a largura de banda alocada.

Para o vídeo principal, a largura de banda típica é a largura de banda agregada sobre todos os fluxos de vídeo recebidos, e o fluxo máximo é a largura de banda sobre todos os fluxos enviados. Mesmo com diversos fluxos de vídeo, a largura de banda típica de vídeo é inferior do que em cenários ponto a ponto porque muitas conferências de vídeo estão usando o compartilhamento de conteúdo, que usa janelas muito menores e, consequentemente, resoluções de vídeos menores. A largura de banda de carga máxima de vídeo agregada suportada é de 8000 Kbps para fluxos de envio e recebimento (por exemplo, se houver dois fluxos de entrada com resolução de 1920 x 1080p). Os valores máximos são raramente vistos em implementações reais.

Durante a criação de uma conferência com vários participantes que usa o recurso de exibição de galeria, a utilização da largura de banda aumenta inicialmente à medida que os participantes se unem e, em seguida, diminui à medida que as resoluções são liberadas para o máximo

||**2 Participantes**|**3 Participantes**|**4 Participantes**|**5 Participantes**|**6 Participantes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Resoluções máximas recebidas** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Total da taxa média de bits** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Total da taxa máxima de bits** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |

A largura de banda típica do fluxo de vídeo panorâmico é baseada em dispositivos que conseguem transmitir vídeo panorâmico de 960x144, no máximo. A largura de banda típica do fluxo costuma aumentar quando são usados dispositivos com vídeo panorâmico de 1920x288.

**Planejamento de capacidade de áudio para PSTN**

|**Mídia**|**Codec típico**|**Largura de banda de fluxo típico (Kbps)**|**Largura de banda de fluxo máximo sem FEC**|**Largura de banda de fluxo máximo com FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |G. 711 (inclui participantes PSTN em conferências)  <br/> |64,8  <br/> |97  <br/> |161  <br/> |
|Áudio  <br/> |Banda estreita RTAudio  <br/> |30,9  <br/> |44,8  <br/> |56,6  <br/> |

Os números de largura de banda da rede dessas tabelas representam apenas o tráfego de uma via e incluem 5 Kbps de sobrecarga de tráfego RTCP para cada fluxo.

## <a name="managing-quality-of-service"></a>Gerenciando a Qualidade de Serviço
<a name="man_QOS"> </a>

A Qualidade de Serviço (QoS) é uma tecnologia de rede que é usada em algumas organizações para ajudar a fornecer a melhor experiência ao usuário final para comunicações de áudio e vídeo. A Qualidade de Serviço é usada mais frequentemente em redes com largura de banda limitada: com uma grande número de pacotes de rede para uma quantidade relativamente pequena de largura de banda disponível, a QoS permite que os administradores atribuam prioridades mais altas a pacotes que carregam dados de áudio e vídeo. Ao conceder uma prioridade mais alta a esses pacotes, as comunicações de áudio e vídeo têm uma probabilidade maior de serem concluídas mais rapidamente e com menos interrupções do que as sessões de rede envolvendo itens como transferências de arquivos, navegação na Web ou backups de bancos de dados. Isso ocorre porque os pacotes de rede usados para transferências de arquivos ou backups de bancos de dados recebem uma atribuição de prioridade de "melhor esforço".

> [!NOTE]
> Como regra, a QoS se aplica somente a sessões de comunicação na sua rede interna. Ao implementar a QoS, você configura seus servidores e roteadores para suportarem a marcação de pacotes de determinada maneira que pode não ser suportada na Internet ou em outras redes. Mesmo que a qualidade do serviço seja compatível em outras redes, não há garantia de que a QoS será configurada exatamente da mesma maneira que você configurou o serviço. Se estiver usando MPLS, você terá que trabalhar com seu provedor de MPLS.

O Skype for Business Server não requer QoS, mas é altamente recomendável. Se você tiver problemas de perda de pacotes na rede, as soluções disponíveis serão adicionar mais largura de banda ou implementar QoS. Se não for possível adicionar mais largura de banda, então a implementação da QoS pode ser a única opção para o resolver o problema.

O Skype for Business Server oferece suporte total à QoS: isso significa que as organizações que já estão usando a QoS podem integrar facilmente o Skype for Business Server à infraestrutura de rede existente. Para fazer isso, você precisa executar as seguintes etapa:

- [Habilitando a QoS no Skype for Business Server para dispositivos que não são baseados no Windows](../../manage/network-management/qos/enabling-qos-for-devices-that-are-not-based-on-windows.md). Por padrão, a QoS é desativada em computadores e outros dispositivos (como iPhones) que executam outros sistemas operacionais. Embora você possa usar o Skype for Business Server para habilitar e desabilitar a qualidade do serviço para dispositivos, normalmente não é possível usar o produto para modificar os códigos DSCP usados por esses dispositivos.

- [Configurar intervalos de porta e uma política de qualidade de serviço para seus servidores de conferência, aplicativo e mediação](../../manage/network-management/qos/configuring-port-ranges-for-your-conferencing-application-and-mediation-servers.md). É necessário reservar um conjunto exclusivo de portas para tipos de pacotes diferentes, como áudio e vídeo. Usando o Skype for Business Server, você não habilita ou desabilita a QoS definindo um valor de propriedade como verdadeiro ou falso. Em vez disso, você ativa a QoS configurando intervalos de porta e, em seguida, criando e aplicando a Política de Grupo. Se, mais tarde, você decidir não usar o QoS, poderá "Desabilitar" a QoS removendo os objetos de política de grupo apropriados.

- [Configurar intervalos de porta e uma política de qualidade de serviço para seus servidores de borda](../../manage/network-management/qos/configuring-port-ranges-for-your-edge-servers.md). Embora não seja necessário, você pode configurar seus servidores de borda para usar os mesmos intervalos de porta que os outros servidores. A configuração de uma política de QoS só será feita para o lado interno dos seus servidores Edge. Isso ocorre pois a QoS foi projetada para uso em sua rede interna, e não na Internet.

- [Configurar intervalos de porta e uma política de qualidade de serviço para seus clientes no Skype for Business Server](../../manage/network-management/qos/configuring-port-ranges-for-your-skype-clients.md). Esses intervalos de porta se aplicam somente a computadores cliente e, normalmente, são diferentes dos intervalos de porta configurados em seus servidores. Observe que o Skype for Business Server não é compatível com QoS para sistemas operacionais Windows que não sejam o Windows 10.


> [!NOTE]
> Se você estiver usando o Windows Server 2012 ou o Windows Server 2012 R2, talvez esteja interessado no novo conjunto de cmdlets do Windows PowerShell disponíveis para gerenciar a QoS nessa plataforma. Para obter mais informações, consulte [cmdlets de QoS de rede no Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379).

A QoS também é abordada no White Paper [planejamento de rede, monitoramento e solução de problemas com o Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) , com detalhes adicionais e profundidade. Embora o conteúdo se refira explicitamente ao Lync 2010 e ao Lync 2013, as considerações para o Skype for Business Server não são alteradas.

## <a name="see-also"></a>Confira também
<a name="man_QOS"> </a>

[Planejamento para IPv6 no Skype for Business](ipv6.md)

[Requisitos de balanceamento de carga para o Skype for Business](load-balancing.md)

[Requisitos de DNS para o Skype for Business Server](dns.md)
