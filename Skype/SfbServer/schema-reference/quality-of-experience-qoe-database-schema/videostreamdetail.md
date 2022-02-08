---
title: Exibição VideoStreamDetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: A Exibição VideoStreamDetail armazena informações sobre cada stream de vídeo no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 0e34791bd3081497c4c8501dbd01d2e9d39503f1
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62393533"
---
# <a name="videostreamdetail-view"></a>Exibição VideoStreamDetail
 
A Exibição VideoStreamDetail armazena informações sobre cada stream de vídeo no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Descrição**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |Identificação exclusiva em uma linha de mídia.  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora de início da sessão.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
|CallPriority  <br/> |int  <br/> |Prioridade da chamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Pool FQDN do chamador.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN do pool do receptor de chamada.  <br/> |
|Chamador  <br/> |nvarchar(450)  <br/> |URI do chamador.  <br/> |
|Chamador  <br/> |nvarchar(450)  <br/> |URI do chamador.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres de agente de usuário do chamador.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuário do chamador. Consulte a [tabela UserAgent para](useragent.md) obter detalhes. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoria do agente de usuário do chamador. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter detalhes. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres de agente de usuário do chamador.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente de usuário do chamador. Consulte a [tabela UserAgent para](useragent.md) obter informações. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar(64)  <br/> |Categoria do agente de usuário do chamador. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter informações. <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CallerOS  <br/> |nvarchar(128)  <br/> |Sistema operacional (OS) do ponto de extremidade do chamador.  <br/> |
|CalleeOS  <br/> |nvarchar(128)  <br/> |Sistema operacional (OS) do ponto de extremidade do chamador.  <br/> |
|CallerCPUName  <br/> |nvarchar(128)  <br/> |Nome da CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128)  <br/> |Nome da CPU do ponto de extremidade do chamador.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU do ponto de extremidade do chamador.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do chamador.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do chamador está em execução em um ambiente virtualizado. Consulte a [tabela Ponto de Extremidade](endpoint.md) para obter mais informações. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do chamador está sendo executado em um ambiente virtualizado. Consulte a [tabela Ponto de Extremidade](endpoint.md) para obter mais informações. <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informações sobre o caminho de mídia, como direto ou transmitido. Consulte a [tabela MediaLine para](medialine-0.md) obter mais informações. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do autor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do receptor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.  <br/> |
|Transport  <br/> |int  <br/> |Tipo de transporte: 0 é UDP, 1 é TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Endereço IP do autor da chamada. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se o chamador está dentro da rede da organização. 1 significa que o chamador está dentro da rede da empresa, 0 significa que o chamador está fora da rede.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Endereço IP do receptor. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta usada pelo receptor.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica se o chamado está dentro da rede da organização. 1 significa que o chamado está dentro da rede da empresa, 0 significa que o chamado está fora da rede.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Nome do site do chamador.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Nome do país/região do site do chamador.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Nome do site do chamador.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Nome do país/região do site do chamador.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Endereço IP do serviço de borda A/V usado pelo chamador. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Porta no serviço de borda A/V usado pelo chamador.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Chave de endereço IP do serviço de borda A/V usado pelo receptor. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta no serviço de borda A/V usada pelo chamado.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CallerRenderDevDriver  <br/> |varchar(256)  <br/> |Nome do driver de dispositivo de renderização do chamador.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de renderização do chamador.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexão de rede do chamador: 0 é com fio, 1 é sem fio.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se o chamador está conectado ou não através de uma rede virtual privada. 1 é para rede virtual privada (VPN), 0 é para não-VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,)  <br/> |Velocidade do link de rede do ponto de extremidade do chamador em bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexão de rede do chamador: 0 é com fio, 1 é sem fio.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se o chamado está conectado ou não através de uma rede virtual privada. 1 é para rede virtual privada (VPN), 0 é para não-VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidade do link de rede para o ponto de extremidade do chamador (em bps).  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Largura de banda real aplicada a um determinado stream lateral de envio de acordo com várias configurações de política (TURN, API, SDP, Servidor de políticas, e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda efetiva menor com base na estimativa de largura de banda. Esta é basicamente a largura de banda máxima que o stream de envio pode utilizar dos limites impostos pela estimativa de largura de banda.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Média de tremulação de rede a partir da estatística do protocolo RTCP.  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Instabilidade máxima da rede durante a chamada.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tempo de ida e volta de estatísticas RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tempo máximo de viagem de ida e volta do stream de áudio.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Taxa média de perda de pacotes durante a chamada.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Perda máxima de pacotes observada durante a chamada.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Contagem de pacotes do stream de vídeo (Protocolo de Transporte em Tempo Real, RTP).  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimativas de largura de banda do stream de áudio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec de áudio usado para a chamada, referenciado da [tabela PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |char(9)  <br/> |Resolução de vídeo obtida através da multiplicação dos pixel de altura e de largura. Relatada como uma sequência de caracteres.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Taxa de transmissão do stream de vídeo.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Taxa de frames de vídeo recebidos.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal(9,4)  <br/> |Taxa de frames de vídeo enviados.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Taxa de transmissão máxima de vídeo durante a sessão de vídeo.  <br/> |
|VideoPacketLossRate  <br/> |decimal(9,4)  <br/> |Taxa de perda dos pacotes de vídeo.  <br/> |
|VideoFrameLossRate  <br/> |decimal(9,4)  <br/> |Percentual do total de frames de vídeo perdidos.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Não usado.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Valor médio da largura de banda alocada para vídeo.  <br/> |
|VideoLocalFrameLossPercentageAvg  <br/> |decimal(9,4)  <br/> |Percentual do total de frames de vídeo perdidos.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Direção de stream das informações de identidade declarada. 1 significa que a direção do stream é do chamador para o chamado; 0 significa que a direção do stream é do chamado para o chamador.  <br/> |
   

