---
title: Exibir videostreamdetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: A exibir Videostreamdetail armazena informações sobre cada transmissão de vídeo no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: 6bafdbed3152bc73b2988e31877d8b7203557d46
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32211994"
---
# <a name="videostreamdetail-view"></a>Exibir videostreamdetail
 
A exibir Videostreamdetail armazena informações sobre cada transmissão de vídeo no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Descrição**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID exclusiva dentro de uma linha de mídia.  <br/> |
|StartTime   <br/> |datetime  <br/> |Hora de início de sessão.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
|CallPriority  <br/> |int  <br/> |Prioridade da chamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN do pool do chamador.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN do pool do receptor.  <br/> |
|Chamador  <br/> |nvarchar(450)  <br/> |URI do chamador.  <br/> |
|Receptor  <br/> |nvarchar(450)  <br/> |URI do receptor.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |String de agente de usuário do chamador.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuário do chamador. Consulte a [tabela UserAgent](useragent.md) para obter detalhes. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoria do agente do usuário do chamador. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter detalhes. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |String de agente do usuário do receptor.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuário do receptor. Consulte a [tabela UserAgent](useragent.md) para obter informações. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoria do agente do usuário do receptor. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter informações. <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do receptor.  <br/> |
|CallerOS  <br/> |nvarchar (128)  <br/> |Sistema operacional (SO) do ponto de extremidade do chamador.  <br/> |
|CalleeOS  <br/> |nvarchar (128)  <br/> |Sistema operacional (SO) do ponto de extremidade do receptor.  <br/> |
|CallerCPUName  <br/> |nvarchar (128)  <br/> |Nome da CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUName  <br/> |nvarchar (128)  <br/> |Nome da CPU do ponto de extremidade do receptor.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU do ponto de extremidade do receptor.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do receptor.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do chamador está sendo executado em um ambiente virtualizado. Consulte a [tabela de ponto de extremidade](endpoint.md) para obter mais informações. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do receptor da chamada está sendo executado em um ambiente virtualizado. Consulte a [tabela de ponto de extremidade](endpoint.md) para obter mais informações. <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informações sobre o caminho de mídia, como direto ou retransmitido. Consulte a [tabela MediaLine](medialine-0.md) para obter mais informações. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de conectividade ICE (estabelecimento interativa) descritas em bits sinalizadores para o chamador. Para obter detalhes, consulte a qualidade da experiência do Monitoring Server especificação do protocolo.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de conectividade ICE (estabelecimento interativa) descritas em bits sinalizadores para o receptor. Para obter detalhes, consulte a qualidade da experiência do Monitoring Server especificação do protocolo.  <br/> |
|Transporte  <br/> |int  <br/> |Tipo de transporte: 0 é UDP, 1 é TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Endereço IP do chamador. Isso pode ser um IPv4 ou um endereço IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se o chamador está dentro da rede da organização. 1 significa que o chamador está dentro da rede corporativa, 0 significa que o chamador está fora da rede.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Endereço IP do receptor. Isso pode ser um IPv4 ou um endereço IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta usada pelo receptor.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica que se o chamador está dentro do network.1 organização significa receptor está na rede corporativa, 0 significa que o receptor está fora da rede.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nome do site do chamador.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nome do país/região do site do chamador.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nome do site do receptor.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nome do país/região do site do receptor.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Endereço IP do / serviço de borda V usado pelo chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Porta no / serviço de borda V usado pelo chamador.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Chave de endereço IP do / serviço de borda V usado pelo receptor. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta no / serviço de borda V usado pelo receptor.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome de driver de dispositivo de captura do chamador.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de renderização do chamador.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de captura do receptor.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do receptor.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome de driver de dispositivo de captura do receptor.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de renderização do receptor.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexão de rede do chamador: 0 é por fio, 1 é sem fio.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se ou não o chamador se conectou por uma rede virtual privada. 1 é a rede virtual privada (VPN), 0 é não VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Velocidade do link de rede para o ponto de extremidade do chamador em bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |O tipo de conexão de rede do receptor: 0 é por fio, 1 é sem fio.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se ou não o receptor da chamada conectada por uma rede privada virtual. 1 é a rede virtual privada (VPN), 0 é não VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidade do link de rede para o ponto de extremidade do receptor da chamada (em bps).  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS da conversa de banda estreita sessões de áudio (com base em dois fluxos de áudio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Largura de banda real aplicada ao envio determinado lado fluxo dado várias configurações de política (ativar, API, SDP, servidor de políticas e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda efetiva inferior com base na estimativa de largura de banda. Isto é, basicamente, a largura de banda máxima, que o fluxo de envio pode demorar limites impostos pela estimativa de largura de banda de bloqueio.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Instabilidade média da rede estatísticas do protocolo de controle de Tempo Real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Tremulação máxima da rede durante a chamada.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tempo de ida e volta de estatísticas RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tempo máximo de ida e volta para o fluxo de áudio.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Taxa de perda média de pacotes durante a chamada.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Perda máxima de pacotes observada durante a chamada.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Contagem de pacotes para o fluxo de vídeo (protocolo de transporte de Tempo Real, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimativas de largura de banda para o fluxo de áudio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec de áudio usado para a chamada, referenciada de [PayloadDescription table](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |Resolução do vídeo em pixels de largura multiplicado pelo pixels de altura. Relatado como uma cadeia de caracteres.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Taxa de bits média do fluxo de vídeo.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Taxa de quadros de vídeo recebidos.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Taxa de quadros de vídeo enviados.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Taxa de bits de vídeo máxima durante a sessão de vídeo.  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |Taxa em que os pacotes de vídeo foram perdidos.  <br/> |
|VideoFrameLossRate  <br/> |decimal(9.4)  <br/> |Porcentagem do total de frames de vídeo perdidos.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Não usado.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Quantidade média de largura de banda alocada para vídeo.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9.4)  <br/> |Porcentagem do total de frames de vídeo perdidos.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Direção do fluxo de informações de identidade declarada p. 1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
   

