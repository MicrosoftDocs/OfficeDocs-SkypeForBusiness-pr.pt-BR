---
title: Planejamento dos requisitos de rede para o Skype for Business 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 2/15/2018
ms.audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.collection: IT_Skype16
ms.custom: Strat_SB_Admin
ms.assetid: 35c7bb3f-8e0f-48b7-8a2c-857d4b42a4c4
description: 'Summary: Review the network component considerations below before implementing Skype for Business Server 2015.'
ms.openlocfilehash: 3d3fd2141da93a9b0b866fe44e2ed8dee6942f3b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="plan-network-requirements-for-skype-for-business-2015"></a>Planejamento dos requisitos de rede para o Skype for Business 2015
 
**Summary:** Review the network component considerations below before implementing Skype for Business Server 2015.
  
The information in these topics is also discussed in the whitepaper [Network Planning, Monitoring, and Troubleshooting with Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) with additional details and depth. While the content refers explicitly to Lync 2010 and Lync 2013, the considerations for Skype for Business Server 2015 are unchanged.
  
Likewise, if your network involves wi-fi as well as wired access, the whitepaper [Delivering Lync 2013 Real-Time Communications over Wi-Fi](http://www.microsoft.com/en-us/download/details.aspx?id=36494) is a good reference and is equally applicable to Skype for Business Server 2015.
  
Network performance and needs are directly linked to the traffic load placed on them. When planning your network and server implementations we recommend making use of the [Skype for Business Server 2015 Planning Tool](../../management-tools/planning-tool/planning-tool.md), the [Skype for Business Server 2015 Capacity Planning Calculator](../../management-tools/capacity-planning-calculator.md), and the [Skype for Business Server 2015 Stress and Performance Tool](../../management-tools/stress-and-performance-tool/stress-and-performance-tool.md).
  
## <a name="server-hardware"></a>Hardware de servidor
<a name="S_hard"> </a>

The network adapter of each server in the Skype for Business Server topology must support at least 1 gigabit per second (Gbps). In general, you should connect all server roles within the Skype for Business Server topology using a low latency and high bandwidth local area network (LAN). O tamanho da LAN depende do tamanho da topologia: 
  
- In Standard Edition topologies, servers should be in a network that supports 1 Gbps Ethernet or equivalent.
    
- In Enterprise Edition topologies, most servers should be in a network that supports more than 1 Gbps, especially when supporting audio/video (A/V) conferencing and application sharing.
    
Para a integração com Rede Telefônica Pública Comutada (PSTN), você pode usar linhas T1/E1 ou tronco SIP.
  
## <a name="audiovideo-network-requirements"></a>Requisitos de rede para áudio/vídeo
<a name="AV_req"> </a>

Network requirements for audio/video (A/V) in a Skype for Business Server deployment include the following:
  
- If you are deploying a single Edge Server or an Edge pool using DNS load balancing, you can configure the  _external_ firewall to perform network address translation (NAT). You can't configure the _internal_ firewall to perform NAT. For details, see [Determining Firewall and 50k Port Range Requirements](http://technet.microsoft.com/library/3b849dc7-175d-40d1-820d-80e6ade6d332.aspx).
    
    > [!IMPORTANT]
    > If you have an Edge pool and are using a hardware load balancer, you must use public IP addresses on the Edge Servers and you can't use NAT for the servers or the pool at your NAT-capable device (for example, a firewall appliance or LAN switch. For details, see [Port Summary - Scaled Consolidated Edge with Hardware Load Balancers](http://technet.microsoft.com/library/91213b1e-f875-464b-83e8-fe3a351595a4.aspx). 
  
- Se a sua organização usa uma infraestrutura de QoS (Qualidade de Serviço), o subsistema de mídia é projetado para funcionar com essa infraestrutura existente. 
    
- Caso você utilize o protocolo IPsec, é recomendável desabilitá-lo nos intervalos de portas usados para o tráfego de A/V. For details, see [IPsec Exceptions](http://technet.microsoft.com/library/241f1eca-6f2f-44de-90b1-2cb659cbe27c.aspx).
    
Para melhor qualidade da mídia, siga este procedimento:
  
- Provisione os links de rede para suportarem uma taxa de transferência de 65 quilobits por segundo (Kbps) por transmissão de áudio e 500 Kbps por transmissão de vídeo, se estiverem habilitadas, durante os períodos de pico. Uma sessão bidirecional de áudio ou vídeo usa duas transmissões, então uma simples conexão de áudio/vídeo exigirá 130K Kbps para cobrir cada transmissão. Video will likewise use 1000 Kbps total to carry an upstream and downstream connection. 
    
- To cope with unexpected spikes in traffic and increased usage over time, Skype for Business Server media endpoints can adapt to varying network conditions and support three times the throughput for audio and video while still maintaining acceptable quality. Não presuma que essa adaptabilidade mascarará o problema quando uma rede estiver sub-provisionada. In an under-provisioned network, the ability of the Skype for Business Server media endpoints to dynamically deal with varying network conditions (for example, temporary high packet loss) is reduced.
    
- Para vínculos de rede em que o provisionamento envolve alto custo e dificuldade, considere a opção de provisionar para um volume menor de tráfego. In this scenario, let the elasticity of the Skype for Business Server media endpoints absorb the difference between the traffic volume and the peak traffic level, at the cost of some reduction in the voice quality. Além disso, haverá uma diminuição na reserva dinâmica que, de outra forma, estaria disponível para absorver picos súbitos de tráfego.
    
- Para os vínculos que não podem ser provisionados corretamente a curto prazo (por exemplo, um local que usa vínculos de WAN de péssima qualidade), considere a possibilidade de desabilitar o vídeo para determinados usuários.
    
- Provisione a rede para assegurar um atraso máximo de ponta a ponta (latência) de 150 ms (milissegundos) sob carga máxima. Latency is the one network impairment that Skype for Business Server media components can't reduce, and it is important to find and eliminate the weak points.
    
- For servers that are running antivirus software, include all servers that are running Skype for Business Server in the exception list to provide optimal performance and audio quality. 
    
## <a name="conferencing-network-requirements"></a>Requisitos da rede de conferência
<a name="Conf_req"> </a>

The bandwidth used to download conference content from the Internet Information Services (IIS) server depends on the size of the content. Você pode optar por monitorar o uso real e ajustar a largura de banda conforme for necessário.
  
## <a name="network-bandwidth-requirements-for-media-traffic"></a>Requisitos de largura de banda de rede para tráfego de mídia
<a name="Conf_req"> </a>

An important part of network planning is ensuring that your network can handle the media traffic generated by Skype for Business Server. Esta seção ajuda a você a se planejar para esse tráfego. 
  
### <a name="media-traffic-network-usage"></a>Uso da rede de tráfego de mídia
<a name="Net_req"> </a>

O cálculo do uso da largura de banda do tráfego de mídia pode ser desafiador devido às diferentes variáveis, como o uso de codec, resolução e níveis de atividade. O uso da largura de banda é uma função do codec que é usado e da atividade do fluxo, que podem variar nos cenários. The following table lists the audio codecs typically used in Skype for Business Server scenarios.
  
**Audio codec bandwidth**

|**Audio codec**|**Scenario**|**Audio payload bit rate (KBPS)**|**Bandwidth audio payload and IP header only (Kbps)**|**Bandwidth audio payload, IP header, UDP, RTP and SRTP (Kbps)**|**Bandwidth audio payload, IP header, UDP, RTP, SRTP and forward error correction (Kbps)**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|Banda ampla RTAudio  <br/> |Ponto a ponto  <br/> |29.0  <br/> |45.0  <br/> |57.0  <br/> |86.0  <br/> |
|Banda estreita RTAudio  <br/> |PSTN ponto a ponto  <br/> |11.8  <br/> |27.8  <br/> |39.8  <br/> |51.6  <br/> |
|G.722  <br/> |Conferência  <br/> |64.0  <br/> |80.0  <br/> |95.6  <br/> |159.6  <br/> |
|Estéreo G.722  <br/> |Conferência ponto a ponto  <br/> |128.0  <br/> |144.0  <br/> |159.6  <br/> |223.6  <br/> |
|G.711  <br/> |Conferência PSTN  <br/> |64.0  <br/> |80.0  <br/> |92.0  <br/> |156.0  <br/> |
|Siren  <br/> |Conferência  <br/> |16.0  <br/> |32.0  <br/> |47.6  <br/> |63.6  <br/> |
|Banda larga SILK  <br/> |Ponto a ponto  <br/> |36.0  <br/> |52.0  <br/> |64.0  <br/> |100.0  <br/> |
|Banda larga SILK  <br/> |Ponto a ponto  <br/> |26.0  <br/> |42.0  <br/> |54.0  <br/> |80.0  <br/> |
|Banda larga SILK  <br/> |Ponto a ponto  <br/> |20.0  <br/> |36.0  <br/> |48.0  <br/> |68.0  <br/> |
|SILK wideband/narrowband  <br/> |Ponto a ponto  <br/> |13.0  <br/> |29.0  <br/> |41.0  <br/> |54.0  <br/> |
   
Os números da largura de banda na tabela anterior são baseados na geração de pacotes de 20 ms (50 pacotes por segundo) e para os codecs G.722 e Siren incluem a sobrecarga adicional do protocolo SRTP nos cenários de conferência e supõe que o fluxo está 100% ativo. O FEC (correção de erro de encaminhamento) é dinamicamente usado quando há uma perda de pacotes no link para ajudar a manter a qualidade dos fluxos de áudio. 
  
A versão estéreo do codec G.722 é usada pelos sistemas baseados no Lync Room System, que usa um único microfone estéreo ou um par de microfones mono para permitir que os ouvintes possam distinguir melhor várias pessoas falando na sala de reunião.
  
**Video Resolution Bandwidth**

|**Video codec**|**Resolution and aspect ratio**|**Maximum video payload bit rate (Kbps)**|**Minimum video payload bit rate (Kbps)**|
|:-----|:-----|:-----|:-----|
|H.264  <br/> |320 x 180 (16:9)  <br/> 212 x 160 (4:3)  <br/> |250  <br/> |15  <br/> |
|H.264/RTVideo  <br/> |424 x 240 (16:9)  <br/> 320 x 240 (4:3)  <br/> |350  <br/> |100  <br/> |
|H.264  <br/> |480 x 270 (16:9)  <br/> 424 x 320 (4:3)  <br/> |450  <br/> |200  <br/> |
|H.264/RTVideo  <br/> |640 x 360 (16:9)  <br/> 640 x 480 (4:3)  <br/> |800  <br/> |300  <br/> |
|H.264  <br/> |848 x 480 (16:9)  <br/> |1500  <br/> |400  <br/> |
|H.264  <br/> |960 x 540 (16:9)  <br/> |2000  <br/> |500  <br/> |
|H.264/RTVideo  <br/> |1280 x 720 (16:9)  <br/> |2500  <br/> |700  <br/> |
|H.264  <br/> |1920 x1080 (16:9)  <br/> |4000  <br/> |1500  <br/> |
|H.264/RTVideo  <br/> |960 x 144 (20:3)  <br/> |500  <br/> |15  <br/> |
|H.264  <br/> |1280 x 192 (20:3)  <br/> |1000  <br/> |250  <br/> |
|H.264  <br/> |1920 x 288 (20:3)  <br/> |2000  <br/> |500  <br/> |
   
Este codec padrão é o padrão de Codificação de Vídeo Avançada H.264/MPEG-4 Parte 10, juntamente suas extensões de codificação de vídeo escalonável para escalabilidade temporal. To maintain interoperability with legacy clients, the RTVideo codec is still used for peer-to-peer calls between Skype for Business Server and legacy clients. In conference sessions with both Skype for Business Server and legacy clients the Skype for Business Server endpoint may encode the video using both video codecs and send the H.264 bitstream to the Skype for Business Server clients and the RTVideo bitstream to legacy clients.
  
A largura de banda exigida depende da resolução, qualidade, taxa de quadros e quantidade de movimento ou alteração na imagem. Para cada resolução, há duas taxas de bits pertinentes:
  
- **Maximum payload bit rate** This is the bit rate that an endpoint will use for resolution at the maximum frame rate. Esse é o valor que permitirá a mais alta qualidade de som e vídeo.
    
- **Minimum payload bit rate** This is the bit rate below which a Skype for Business Server endpoint will switch to the next lower resolution. Para garantir um nível mínimo de resolução, a taxa de bits da carga do vídeo disponível não deve ser inferior a esta taxa de bits mínima para a resolução em questão. Este valor ajuda você a entender qual é o menor valor possível se a taxa de bits máxima não estiver disponível ou não for praticável. Para alguns usuários, vídeos com taxas de bits tão baixas proporcionar uma experiência inaceitável, portanto, tenha cuidado ao estabelecer a taxa de bits mínima para carga do vídeo. Observe que cenas do vídeo em que há pouco ou nenhum movimento, a taxa de bits real pode ficar temporariamente abaixo do limite mínimo.
    
Skype for Business Server supports many resolutions. This allows Skype for Business Server to adjust to different network bandwidth and receiving client capabilities. The default aspect ratio for Skype for Business Server is 16:9. The legacy 4:3 aspect ratio is still supported for webcams which don't allow capture in the 16:9 aspect ratio.
  
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
    
- Each participant that turns on the user's send video stream will send one or more video streams. Skype for Business Server has the capability of sending up to five video streams to optimize the video quality for all the receiving clients. A quantidade real de fluxos de vídeo enviados é determinada pelo remetente com base na capacidade da CPU, na largura de banda uplink disponível e na quantidade de clientes receptores que tenham selecionado um determinado fluxo de vídeo. O mais comum são os fluxos de vídeo H.264 e RTVideo enviados em caso de presença de clientes herdados na conferência. Outro cenário comum é o envio de diversos fluxos de vídeo H.264 (por exemplo, com a mesma resolução de vídeo) para acomodação de diferentes solicitações do receptor. 
    
Além da largura de banda necessária para o tráfego do protocolo de transporte em tempo real (RTP) para mídia em áudio e vídeo, a largura de banda é necessária também para o protocolo de controle de transporte em tempo real (RTCP). O RTCP é usado para obter estatísticas e controle fora da banda para o fluxo RTP. Para fins de planejamento, use os números de largura de banda da tabela a seguir para verificar o tráfego RTCP. Esses valores representam a largura de banda máxima usada para RTCP e são diferentes nos fluxos de áudio e vídeo devido às diferenças nos dados de controle 
  
**RTCP Bandwidth**

|**Media**|**RTCP maximum bandwidth (Kbps)**|
|:-----|:-----|
|Áudio  <br/> |5  <br/> |
|Vídeo (somente H.264 ou RTVideo enviado/recebido)  <br/> |10  <br/> |
|Vídeo (somente H.264 ou RTVideo enviado/recebido)  <br/> |15  <br/> |
   
Para planejamento da capacidade, as duas larguras de banda mencionadas a seguir são:
  
- **Maximum bandwidth without FEC** The maximum bandwidth that a stream will consume. Isso inclui a atividade típica do fluxo e o codec típico usado em cenário sem FEC. Trata-se da largura de banda quando o fluxo está 100% em atividade e não há perda de pacote que gere uso de FEC. É útil para a computação saber quanta largura de banda deve ser alocada para que o codec possa ser usado em um determinado cenário. O FEC não precisa ser um requisito em uma rede mapeada.
    
- **Maximum bandwidth with FEC** The maximum bandwidth that a stream consumes. Isso inclui a atividade típica do fluxo e o codec típico usado em cenário com FEC. Trata-se da largura de banda quando o fluxo está 100% em atividade e há perda de pacote que gere uso de FEC para aprimorar a qualidade. É útil para a computação saber quanta largura de banda deve ser alocada para que o codec possa ser usado em um determinado cenário e permitir ouso de FEC para preservar as condições de qualidade em caso de perda de pacotes.
    
A tabela a seguir também lista outro valor da largura de banda, a **Largura de banda típica**. Trata-se da largura de banda consumida pelo fluxo. Isso inclui a atividade típica do fluxo e o codec típico usado no cenário. Essa largura de banda pode ser usada para aproximar a largura de banda consumida pelo tráfego de mídia em determinado momento, mas não deve ser usada no planejamento da capacidade porque chamadas individuais ultrapassarão seu valor quando o nível da atividade for superior à média. A largura debanda típica para o fluxo de vídeo indicada nas tabelas abaixo baseia-se em diferentes resoluções de vídeo, conforme observado em dados medidos de clientes. For example, in peer-to-peer sessions most users would use the default video render window whereas some percentage of users would increase or maximize the Skype for Business Server application to allow better video resolutions.
  
As tabelas abaixo fornecem valores de largura de banda para diversos cenários.
  
**Audio/Video Capacity Planning for Peer-to-Peer Sessions**

|**Media**|**Codec**|**Typical stream bandwidth (Kbps)**|**Maximum stream bandwidth without FEC**|**Maximum stream bandwidth with FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |Banda ampla RTAudio  <br/> |39.8  <br/> |62  <br/> |91  <br/> |
|Áudio  <br/> |Banda estreita RTAudio  <br/> |29.3  <br/> |44.8  <br/> |56.6  <br/> |
|Áudio  <br/> |Banda larga SILK  <br/> |44.3  <br/> |69  <br/> |105  <br/> |
|Main video when calling Skype for Business Server endpoints  <br/> |H.264  <br/> |460  <br/> |4010 (para resolução máxima de 1920 x 1080)  <br/> |Já incluído  <br/> |
|Main video when calling Lync 2010 or Office Communicator 2007 R2 endpoints  <br/> |RTVideo  <br/> |460  <br/> |2510 (para resolução máxima de 1280 x 720)  <br/> |Já incluído  <br/> |
|Panoramic video when calling Skype for Business Server endpoints  <br/> |H.264  <br/> |190  <br/> |2010 (para resolução máxima de 1920 x 288)  <br/> |Já incluído  <br/> |
|Panoramic video when calling Lync 2010 endpoints  <br/> |RTVideo  <br/> |190  <br/> |510 (para resolução máxima de 960 x 144)  <br/> |Já incluído  <br/> |
   
**Audio/Video Capacity Planning for Conferences**

|**Media**|**Typical codec**|**Typical stream bandwidth (Kbps)**|**Largura de banda máxima sem FEC**|**Maximum stream bandwidth with FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |G.722  <br/> |46.1  <br/> |100.6  <br/> |164.6  <br/> |
|Áudio  <br/> |Siren  <br/> |25.5  <br/> |52.6  <br/> |68.6  <br/> |
|Recepção de vídeo principal  <br/> |H.264 e RTVideo¹  <br/> |260  <br/> |8015  <br/> |Não aplicável  <br/> |
|Envio de vídeo principal  <br/> |H.264 e RTVideo  <br/> |270  <br/> |8015  <br/> |Não aplicável  <br/> |
|Recepção de vídeo panorâmico  <br/> |H.264 e RTVideo  <br/> |190  <br/> |2010 (para resolução máxima de 1920 x 288)  <br/> |Não aplicável  <br/> |
|Envio de vídeo panorâmico  <br/> |H.264 e RTVideo  <br/> |190  <br/> |2515 ²  <br/> |Não aplicável  <br/> |
   
1. Vídeo de RT é enviado além para h. 264 quando os clientes do Lync 2010 estão conectados à conferência.
  
2. If there are multiple streams, they dynamically share the allocated bandwidth.
  
Para o vídeo principal, a largura de banda típica é a largura de banda agregada sobre todos os fluxos de vídeo recebidos, e o fluxo máximo é a largura de banda sobre todos os fluxos enviados. Mesmo com diversos fluxos de vídeo, a largura de banda típica de vídeo é inferior do que em cenários ponto a ponto porque muitas conferências de vídeo estão usando o compartilhamento de conteúdo, que usa janelas muito menores e, consequentemente, resoluções de vídeos menores. A largura de banda de carga máxima de vídeo agregada suportada é de 8000 Kbps para fluxos de envio e recebimento (por exemplo, se houver dois fluxos de entrada com resolução de 1920 x 1080p). Os valores máximos são raramente vistos em implementações reais.
  
When building out a multiparty conference that uses the gallery view feature, bandwidth utilization increases initially as participants join, then decreases as resolutions are dropped to fit within the maximum. 
  
||**2 Participants**|**3 Participants**|**4 Participants**|**5 participantes**|**6 participantes**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|**Resoluções máximas recebidas** <br/> |1920x1080  <br/> |1280x720  <br/> |640x360  <br/> |640x360 320x240  <br/> |640x360 320x240  <br/> |
|**Total da taxa média de bits** <br/> |2128  <br/> |4050  <br/> |1304  <br/> |1224  <br/> |1565  <br/> |
|**Total da taxa máxima de bits** <br/> |4063  <br/> |5890  <br/> |2860  <br/> |2699  <br/> |3017  <br/> |
   
A largura de banda típica do fluxo de vídeo panorâmico é baseada em dispositivos que conseguem transmitir vídeo panorâmico de 960x144, no máximo. A largura de banda típica do fluxo costuma aumentar quando são usados dispositivos com vídeo panorâmico de 1920x288. 
  
**Audio Capacity Planning for PSTN**

|**Media**|**Codec típico**|**Largura de banda de fluxo típico (Kbps)**|**Largura de banda máxima sem FEC**|**Largura de banda máxima com FEC**|
|:-----|:-----|:-----|:-----|:-----|
|Áudio  <br/> |G.711 (this includes PSTN participants in conferences)  <br/> |64.8  <br/> |97  <br/> |161  <br/> |
|Áudio  <br/> |Banda estreita RTAudio  <br/> |30,9  <br/> |44,8  <br/> |56.6  <br/> |
   
Os números de largura de banda da rede dessas tabelas representam apenas o tráfego de uma via e incluem 5 Kbps de sobrecarga de tráfego RTCP para cada fluxo. 
  
## <a name="managing-quality-of-service"></a>Gerenciando a Qualidade de Serviço
<a name="man_QOS"> </a>

A Qualidade de Serviço (QoS) é uma tecnologia de rede que é usada em algumas organizações para ajudar a fornecer a melhor experiência ao usuário final para comunicações de áudio e vídeo. A Qualidade de Serviço é usada mais frequentemente em redes com largura de banda limitada: com uma grande número de pacotes de rede para uma quantidade relativamente pequena de largura de banda disponível, a QoS permite que os administradores atribuam prioridades mais altas a pacotes que carregam dados de áudio e vídeo. Ao conceder uma prioridade mais alta a esses pacotes, as comunicações de áudio e vídeo têm uma probabilidade maior de serem concluídas mais rapidamente e com menos interrupções do que as sessões de rede envolvendo itens como transferências de arquivos, navegação na Web ou backups de bancos de dados. Isso ocorre porque os pacotes de rede usados para transferências de arquivos ou backups de bancos de dados recebem uma atribuição de prioridade de "melhor esforço".
  
> [!NOTE]
> Como regra, a QoS se aplica somente a sessões de comunicação na sua rede interna. Ao implementar a QoS, você configura seus servidores e roteadores para suportarem a marcação de pacotes de determinada maneira que pode não ser suportada na Internet ou em outras redes. Mesmo se a Qualidade de Serviço for suportada em outras redes, não há garantia de que a QoS será configurada exatamente da mesma maneira que você configurou o serviço. Se estiver usando MPLS, você terá que trabalhar com seu provedor de MPLS. 
  
Skype for Business Server does not require QoS, but it is strongly recommended. Se você tiver problemas de perda de pacotes na rede suas soluções disponíveis são para adicionar mais largura de banda ou para implementar o QoS. Se não for possível adicionar mais largura de banda, então a implementação da QoS pode ser a única opção para o resolver o problema.
  
Skype para Business Server oferece suporte completo para QoS: significa que as organizações que já estão usando o QoS podem facilmente integrar Skype para Business Server em sua infra-estrutura de rede existente. Para fazer isso, você precisa executar as seguintes etapa:
  
- [Habilitando QoS para dispositivos não-Windows](http://technet.microsoft.com/library/26f793df-aef8-4028-9e3b-6c2c37ea61b9.aspx). Por padrão, a QoS é desativada em computadores e outros dispositivos (como iPhones) que executam outros sistemas operacionais. Embora você possa usar Skype para Business Server para habilitar e desabilitar a QoS para dispositivos, você geralmente não é possível usar o produto para alterar os códigos DSCP usados por esses dispositivos.
    
- [Configurando intervalos de portas de conferência, aplicativo e os servidores de mediação](http://technet.microsoft.com/library/4d6eaa5d-0127-453f-be6a-e55384772d83.aspx). É necessário reservar um conjunto exclusivo de portas para tipos de pacotes diferentes, como áudio e vídeo. By using Skype for Business Server you do not enable or disable QoS by setting a property value to True or to False. Em vez disso, você ativa a QoS configurando intervalos de porta e, em seguida, criando e aplicando a Política de Grupo. Se posteriormente você decidir não usar a QoS você pode "Desativar" QoS, removendo os objetos de diretiva de grupo apropriados.
    
- [Configurando intervalos de portas para seus servidores de borda](http://technet.microsoft.com/library/6f0ae442-6624-4e3f-849a-5b9e387fb8cf.aspx). Embora não seja necessário, você pode configurar seus servidores de borda para usar os mesmos intervalos de porta que os outros servidores.
    
- [Configurando intervalos de portas para seus clientes Microsoft Lync](http://technet.microsoft.com/library/287d5cea-7ada-461c-9b4a-9da2af315e71.aspx). Esses intervalos de porta se aplicam somente a computadores cliente e, normalmente, são diferentes dos intervalos de porta configurados em seus servidores.
    
- [Configurando uma qualidade de serviço de política de conferência, aplicativo e os servidores de mediação](http://technet.microsoft.com/library/8adcbbc5-c9f5-476d-ab7f-72e61859cacf.aspx). Essas políticas determinam os códigos DSCP aplicados a tipos de pacotes diferentes.
    
- [Configurando uma política de qualidade de serviço para o seu A borda a / V servidores](http://technet.microsoft.com/library/119ee1f5-45b9-40ba-98e5-c694dd2fc5c2.aspx). Isso deve ser executado somente para o lado interno de seus servidores de borda. Isso ocorre pois a QoS foi projetada para uso em sua rede interna, e não na Internet.
    
- [Configuring Peer-to-Peer Quality of Service Policies for Clients Running on Windows 7 or Windows 8](http://technet.microsoft.com/library/efff2b98-b3fb-4183-a4f0-329a9105ce2c.aspx). Note that Skype for Business Server does not support QoS for other Windows operating systems, such as Windows Vista or Windows XP.
    
- [Configuring Quality of Service on Microsoft Lync Phone Edition Devices](http://technet.microsoft.com/library/a6eb2620-a512-4ab6-bdfd-eb76be43bbfe.aspx). Por padrão, a QoS está habilitada para dispositivos Lync Phone Edition. Talvez seja necessário alterar o valor padrão de DSCP para garantir que todos os pacotes de áudio em sua organização usem o mesmo código DSCP.
    
> [!NOTE]
> Se você estiver usando o Windows Server 2012 ou Windows Server 2012 R2, você pode estar interessado em um novo conjunto de cmdlets do Windows PowerShell disponíveis para gerenciamento de QoS nessa plataforma. Para obter mais informações, consulte [Rede Cmdlets de QoS no Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=285379). 
  
QoS também é discutido no whitepaper de [Planejamento de rede, monitoramento e solução de problemas com o Lync Server](https://www.microsoft.com/en-us/download/details.aspx?id=39084) com detalhes adicionais e profundidade. Enquanto o conteúdo refere-se explicitamente para o Lync 2010 e Lync 2013, as considerações para Skype para Business Server 2015 permanecem inalteradas.
  
## <a name="see-also"></a>Ver também
<a name="man_QOS"> </a>

#### 

[Planejar IPv6 no Skype for Business](ipv6.md)
  
[Requisitos do Skype para negócios de balanceamento de carga](load-balancing.md)
  
[Requisitos de DNS para Skype para Business Server 2015](dns.md)
  
[Requisitos de porta e protocolo para servidores](ports-and-protocols.md)

