---
title: Exibição VideoStreamDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ec8c45e1-307d-40ec-a75e-6083306105f2
description: A exibição VideoStreamDetail armazena informações sobre cada fluxo de vídeo no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: ee342de919ffca8b62c60f8c7b724f3dc7be0205
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294527"
---
# <a name="videostreamdetail-view"></a>Exibição VideoStreamDetail
 
A exibição VideoStreamDetail armazena informações sobre cada fluxo de vídeo no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Descrição**|
|:-----|:-----|:-----|
|Sessiontime  <br/> |datetime  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|MediaLineLabel  <br/> |tinyint  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|Streamid  <br/> |int  <br/> |ID exclusiva dentro de uma linha de mídia.  <br/> |
|StartTime   <br/> |datetime  <br/> |Hora de início da sessão.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
|CallPriority  <br/> |int  <br/> |Prioridade da chamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |FQDN do pool de chamadas.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN do pool do chamador.  <br/> |
|Chamador  <br/> |nvarchar (450)  <br/> |URI do chamador.  <br/> |
|Receptor  <br/> |nvarchar (450)  <br/> |URI do chamador.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres do agente do usuário do chamador.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo de agente do usuário do chamador. Consulte a [tabela UserAgent](useragent.md) para obter detalhes. <br/> |
|CallerUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria do agente do usuário do chamador. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter detalhes. <br/> |
|CalleeUserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres do agente do usuário do chamador.  <br/> |
|CalleeUserAgentType  <br/> |smallint  <br/> |Tipo de agente do usuário do chamador. Consulte a [tabela UserAgent](useragent.md) para obter informações. <br/> |
|CalleeUserAgentCategory  <br/> |nvarchar (64)  <br/> |Categoria do agente do usuário do chamador. Consulte a [tabela UserAgentDef (QoE)](useragentdef-qoe.md) para obter informações. <br/> |
|CallerEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CalleeEndpoint  <br/> |nvarchar(256)  <br/> |Nome do ponto de extremidade do chamador.  <br/> |
|CallerOS  <br/> |nvarchar(128  <br/> |Sistema operacional (SO) do ponto de extremidade do chamador.  <br/> |
|CalleeOS  <br/> |nvarchar(128  <br/> |Sistema operacional (SO) do ponto de extremidade do chamador.  <br/> |
|CallerCPUName  <br/> |nvarchar(128  <br/> |Nome da CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUName  <br/> |nvarchar(128  <br/> |Nome da CPU do ponto de extremidade do chamador.  <br/> |
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos da CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos da CPU do ponto de extremidade do chamador.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do chamador.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do chamador está em execução em um ambiente virtualizado. Consulte a [tabela de pontos de extremidade](endpoint.md) para obter mais informações. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do chamador está em execução em um ambiente virtualizado. Consulte a [tabela de pontos de extremidade](endpoint.md) para obter mais informações. <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informações sobre o caminho de mídia, como direta ou retransmitida. Consulte a [tabela de mídia](medialine-0.md) para obter mais informações. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador. Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador. Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.  <br/> |
|SMTP  <br/> |int  <br/> |Tipo de transporte: 0 é UDP; 1 é o TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Endereço IP do chamador. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se o chamador está dentro da rede da organização. 1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Endereço IP do chamador. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica se o chamador está dentro da rede da organização. 1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.  <br/> |
|CallerUserSite  <br/> |nvarchar(128  <br/> |Nome do site do chamador.  <br/> |
|CallerRegion  <br/> |nvarchar(128  <br/> |Nome do país/região do site do chamador.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128  <br/> |Nome do site do chamador.  <br/> |
|CalleeRegion  <br/> |nvarchar(128  <br/> |Nome do país/região do site do chamador.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Endereço IP do serviço de borda A/V usado pelo chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Porta no serviço de borda A/V usado pelo chamador.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Chave de endereço IP do serviço de borda A/V usado pelo chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta no serviço de borda A/V usado pelo chamador.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CallerRenderDevDriver  <br/> |varchar (256)  <br/> |O nome do driver de dispositivo de renderização do chamador.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nome do dispositivo de renderização do Calle.  <br/> |
|CalleCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Chame o nome do driver do dispositivo de processamento do recurso.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se o chamador se conecta ou não a uma rede virtual privada. 1 é uma rede virtual privada (VPN), 0 não é VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal (18)  <br/> |Velocidade do link de rede para o ponto de extremidade do chamador em bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se o chamador se conecta em uma rede virtual privada. 1 é uma rede virtual privada (VPN), 0 não é VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal (18, 0)  <br/> |Velocidade do link de rede para o ponto de extremidade do chamador (em bps).  <br/> |
|ConversationalMOS  <br/> |decimal (3; 2)  <br/> |O MOS de conversa de banda estreita das sessões de áudio (com base nos dois fluxos de áudio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |A largura de banda real aplicada ao fluxo de envio do lado fornecido tem várias configurações de política (ativar, API, SDP, servidor de política e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda mais econômica com base na estimativa de largura de banda. Isso é basicamente a largura de banda máxima que o fluxo de envio pode ter limites de bloqueio impostos pela estimativa da largura de banda.  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Maior tremulação de rede durante a chamada.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tempo de ida e volta das estatísticas do RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tempo máximo de ida e volta do fluxo de áudio.  <br/> |
|PacketLossRate  <br/> |decimal (5, 4)  <br/> |Taxa média de perda de pacotes durante a chamada.  <br/> |
|PacketLossRateMax  <br/> |decimal (5, 4)  <br/> |Perda máxima de pacote observado durante a chamada.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Contagem de pacotes para o fluxo de vídeo (protocolo de transporte em tempo real, RTP).  <br/> |
|Largura de banda  <br/> |int  <br/> |Estimativas de largura de banda para o fluxo de áudio.  <br/> |
|PayloadDescription  <br/> |int  <br/> |Codec de áudio usado para a chamada, referenciado da [tabela PayloadDescription](payloaddescription.md).  <br/> |
|VideoResolution  <br/> |caractere (9)  <br/> |Resolução do vídeo em largura de pixels multiplicada pela altura de pixels. Relatado como uma cadeia de caracteres.  <br/> |
|VideoBitRateAvg  <br/> |int  <br/> |Taxa média de bits do fluxo de vídeo.  <br/> |
|InboundVideoFrameRateAvg  <br/> |decimal (9, 4)  <br/> |Taxa de quadro de vídeo recebida.  <br/> |
|OutboundVideoFrameRateAvg  <br/> |decimal (9, 4)  <br/> |Taxa de quadro de vídeo enviada.  <br/> |
|ViideoBitRateMax  <br/> |int  <br/> |Taxa máxima de bits de vídeo durante a sessão de vídeo.  <br/> |
|À  <br/> |decimal (9, 4)  <br/> |Taxa de perda de pacotes de vídeo.  <br/> |
|VideoFrameLossRate  <br/> |decimal (9.4)  <br/> |Porcentagem total de quadros de vídeo perdidos.  <br/> |
|VideoFEC  <br/> |bit  <br/> |Não usado.  <br/> |
|VideoAllocateBWAvg  <br/> |int  <br/> |Quantidade média de largura de banda alocada para vídeo.  <br/> |
|À  <br/> |decimal (9.4)  <br/> |Porcentagem total de quadros de vídeo perdidos.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Direção de fluxo para informações de identidades p-declaradas. 1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
   

