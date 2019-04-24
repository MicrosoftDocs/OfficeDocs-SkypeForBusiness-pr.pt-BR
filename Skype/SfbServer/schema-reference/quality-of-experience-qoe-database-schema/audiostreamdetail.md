---
title: Exibir audiostreamdetail
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: A exibir Audiostreamdetail armazena informações sobre cada transmissão de áudio no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: c5078a0d936cce0dec29ddfee3813db7334aba71
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212288"
---
# <a name="audiostreamdetail-view"></a>Exibir audiostreamdetail
 
A exibir Audiostreamdetail armazena informações sobre cada transmissão de áudio no banco de dados. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |ID exclusiva dentro de uma linha de mídia.  <br/> |
|StartTime   <br/> |datetime  <br/> |Hora de início de sessão.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoria do diálogo: 0 é o Skype para Business Server para a perna do servidor de mediação; 1 é o servidor de mediação para o trecho de gateway PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Sinalizador que indica se a chamada foi ignorada ou não.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Se presente, indica por que uma chamada não foi ignorada, mesmo se o desvio de correspondem de IDs. Somente um valor é definido:  <br/> 0x0001 - ID de desvio desconhecida adaptador de rede padrão.  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU no ponto de extremidade do chamador.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU no ponto de extremidade do receptor.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do receptor.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do chamador está sendo executado em um ambiente virtualizado. Consulte a [tabela de ponto de extremidade](endpoint.md) para obter mais informações. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do receptor da chamada está sendo executado em um ambiente virtualizado. Consulte a [tabela de ponto de extremidade](endpoint.md) para obter mais informações. <br/> |
|CorrelationKey  <br/> ||Chave de correlação. Referenciado da [tabela SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informações sobre o caminho de mídia, como direto ou retransmitido. Consulte a [tabela MediaLine](medialine-0.md) para obter mais informações. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de conectividade ICE (estabelecimento interativa) descritas em bits sinalizadores para o chamador. Para obter detalhes, consulte a qualidade da experiência do Monitoring Server especificação do protocolo.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de conectividade ICE (estabelecimento interativa) descritas em bits sinalizadores para o receptor. Para obter detalhes, consulte a qualidade da experiência do Monitoring Server especificação do protocolo.  <br/> |
|Transporte  <br/> |tinyint  <br/> |Tipo de transporte: 0 é UDP, 1 é TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Endereço IP do chamador. Isso pode ser um IPv4 ou um endereço IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se o chamador está dentro da rede de intervalo: 1 chamador de significa está dentro da rede corporativa, 0 significa que o chamador está fora da rede.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Endereço IP do receptor. Isso pode ser um IPv4 ou um endereço IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta usada pelo receptor.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica se o receptor está na rede de intervalo: 1 significa que está dentro da rede corporativa, 0 significa que o receptor está fora da rede.  <br/> |
|CallerUserSite  <br/> |nvarchar (128)  <br/> |Nome do site do chamador.  <br/> |
|CallerRegion  <br/> |nvarchar (128)  <br/> |Nome do país/região do site do chamador.  <br/> |
|CalleeUserSite  <br/> |nvarchar (128)  <br/> |Nome do site do receptor.  <br/> |
|CalleeRegion  <br/> |nvarchar (128)  <br/> |Nome do país/região do site do receptor.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Endereço IP do / serviço de borda V usado pelo chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Porta usada no / serviço de borda V usado pelo chamador.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Chave de endereço IP do / serviço de borda V usado pelo receptor. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usada no / serviço de borda V usado pelo receptor.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome de driver de dispositivo de captura do chamador.  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de renderização do chamador.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de captura do receptor.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do receptor.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome de driver de dispositivo de captura do receptor.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de renderização do receptor.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexão de rede do chamador: 0 é por fio, 1 é sem fio.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se o chamador conectou por uma rede privada virtual: 1 é a rede virtual privada (VPN), 0 é não VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidade do link de rede para o ponto de extremidade do chamador em bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |O tipo de conexão de rede do receptor: 0 é por fio, 1 é sem fio.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se o chamador conectou por uma rede privada virtual: 1 é a rede virtual privada (VPN), 0 é não VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidade do link de rede para o ponto de extremidade do receptor em bps.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS da conversa de banda estreita sessões de áudio (com base em dois fluxos de áudio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Largura de banda real aplicada ao envio determinado lado fluxo dado várias configurações de política (ativar, API, SDP, servidor de políticas e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda efetiva inferior com base na estimativa de largura de banda. Isto é, basicamente, a largura de banda máxima, que o fluxo de envio pode demorar limites impostos pela estimativa de largura de banda de bloqueio  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Instabilidade média da rede estatísticas do protocolo de controle de Tempo Real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Tremulação máxima da rede durante a chamada.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Taxa de perda média de pacotes durante a chamada.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Perda máxima de pacotes observada durante a chamada.  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |Densidade média de perda de pacote durante picos de perdas durante a chamada.  <br/> |
|BurstDuration  <br/> |int  <br/> |Duração média de perda de pacote durante picos de perdas durante a chamada.  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |Densidade média de perda de pacote durante intervalos entre picos de perda de pacotes.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Duração média de intervalos entre picos de perda de pacotes.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Contagem de pacotes para o fluxo de áudio.  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimativas de largura de banda para o fluxo de áudio.  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |Degradação de MOS de rede para a chamada inteira. O intervalo é 0,0 para 5.0. Essa métrica mostra a quantidade que de MOS de rede foi reduzido devido a tremulação e perda de pacotes. Para qualidade aceitável deveria menos que 0,5.  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |Degradação de MOS de rede máxima durante a chamada.  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |Degradação de MOS de rede causada por tremulação.  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |Degradação de MOS de rede causada por perda de pacotes.  <br/> |
|PayloadDescription  <br/> |int  <br/> |O codec de áudio usado para a chamada, referenciada de [PayloadDescription table](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Taxa de amostragem para o fluxo de áudio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Nível de sinal de áudio de controle de ganho POST-analógico para o áudio enviado do chamador. A unidade para essa métrica é dBmo. Para obter uma qualidade aceitável, ele deve ser dBmo pelo menos 30. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Nível de sinal de áudio para o áudio do chamador recebido. A unidade para essa métrica é dBmo. Para obter uma qualidade aceitável, ele deve ser dBmo pelo menos 30. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho POST-analógico para o áudio do chamador enviado. A unidade para essa métrica é dBmo. Para obter uma qualidade aceitável, ele deve ser menor que 35 dBmo. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho POST-analógico para o áudio do chamador recebido. A unidade para essa métrica é dBmo. Para obter uma qualidade aceitável, ele deve ser menor que 35 dBmo. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Eco retornar perda aprimoramento para o chamador. A unidade para essa métrica é dB. Valores inferiores representam menos eco. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Falhas médios por cinco minutos para renderização de alto-falante do chamador. Para obter uma boa qualidade, este deve ser menor do que um por cinco minutos. Não é relatado pela / V Conferencing Servers, servidores de mediação ou IP telefones.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Capturam de falhas médios por cinco minutos para microfone do chamador. Para boa qualidade este deve ser menor do que um por cinco minutos. Não é relatado pela / V Conferencing Servers, servidores de mediação ou IP telefones.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Microfone dispositivo taxa relógio do chamador deriva, relativo ao clock de CPU.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Alto-falante dispositivo taxa relógio do chamador deriva, relativo ao clock de CPU.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Média de microfone captura stream carimbo erro em tempo, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Média de alto-falante do chamador renderização de erro de carimbo de hora de fluxo, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |Opção de voz é um modo half-duplex com capacidade de interrupção reduzida. Consulte a [tabela MediaLine](medialine-0.md) para obter mais informações. <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Causas de um evento de eco para o chamador. Consulte a [tabela MediaLine](medialine-0.md) para obter mais informações. <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Porcentagem de tempo quando o eco seja detectado no fluxo de captura de microfone do chamador. Se headset for usado, o valor deve ser baixo.  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |Porcentagem de tempo quando o eco é detectado no chamador do enviadas stream. Porcentagem de eco alta nos enviar fluxos uma indicação do vazamento de eco.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Nível de sinal recebido no servidor de mediação do Gateway para o áudio do chamador; Isso se aplica somente ao servidor de mediação. A unidade dessa métrica é dBoV. Para obter uma boa qualidade, do intervalo aceitável deve ser -30 para-18 dBoV.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Nível de sinal recebido no servidor de mediação do Gateway para o chamador 's áudio. Isso se aplica somente ao servidor de mediação. A unidade dessa métrica é dBoV. Para boa qualidade, o intervalo aceitável deve ser menor que-50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Ganho automático (AGC) do controle no lado do servidor de mediação aplicado ao áudio do chamador.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |Raiz quadrada média (RMS) do sinal de entrada para o chamador pelos 30 primeiros segundos da chamada.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Representa o nível de sinal de áudio pós-analógico controle de ganho do áudio enviado do receptor. A unidade para essa métrica é dBmo. Para obter uma qualidade aceitável, ele deve ser dBmo pelo menos 30. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Nível de sinal de áudio para o áudio do receptor de chamada recebida. A unidade para essa métrica é dBmo. Para obter uma qualidade aceitável, ele deve ser dBmo pelo menos 30. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho POST-analógico para o receptor enviado de áudio. A unidade para essa métrica é dBmo. Para obter uma qualidade aceitável, ele deve ser menor que 35 dBmo. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho POST-analógico para o áudio do receptor de chamada recebida. A unidade para essa métrica é dBmo. Para obter uma qualidade aceitável, ele deve ser menor que 35 dBmo. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Eco retornar perda aprimoramento para o receptor. A unidade para essa métrica é dB. Valores inferiores representam menos eco. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Falhas médios por cinco minutos para renderização de alto-falante do receptor. Para obter uma boa qualidade, este deve ser menor do que um por cinco minutos. Não é relatado pela / V Conferencing Servers, servidores de mediação ou IP telefones.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Capturam de falhas médios por cinco minutos para microfone do receptor. Para boa qualidade este deve ser menor do que um por cinco minutos. Não é relatado pela / V Conferencing Servers, servidores de mediação ou IP telefones.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Do microfone dispositivo relógio taxa de descompasso receptor, relativa ao relógio da CPU.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Do alto-falante dispositivo relógio taxa de descompasso receptor, relativa ao relógio da CPU.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Média de microfone captura stream carimbo erro em tempo, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Média de alto-falante do receptor renderização de erro de carimbo de hora de fluxo, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |Opção de voz é um modo half-duplex com capacidade de interrupção reduzida. Consulte a [tabela MediaLine](medialine-0.md) para obter mais informações. <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Causas de um evento de eco para o receptor. Consulte a [tabela MediaLine](medialine-0.md) para obter mais informações. <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Porcentagem de tempo quando o eco seja detectado no fluxo de captura de microfone do receptor. Se headset for usado, o valor deve ser baixo.  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |Porcentagem de tempo quando o eco seja detectado no receptor do enviadas stream. Porcentagem de eco alta nos enviar fluxos uma indicação do vazamento de eco.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Nível de sinal recebido no servidor de mediação do Gateway para o áudio do receptor; Isso se aplica somente ao servidor de mediação. A unidade dessa métrica é dBoV. Para obter uma boa qualidade, o intervalo aceitável deve ser [-30-18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Nível de sinal recebido no servidor de mediação do Gateway para o receptor 's áudio. Isso se aplica somente ao servidor de mediação. A unidade dessa métrica é dBoV. Para boa qualidade, o intervalo aceitável deve ser menor que-50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Ganho automático (AGC) do controle no lado do servidor de mediação aplicado ao áudio do receptor.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |Raiz quadrada média (RMS) do sinal de entrada para o receptor durante os 30 primeiros segundos da chamada.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |Taxa média de amostras escondidas geradas pelo Reparo de áudio para exemplos típicos.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |Taxa média de amostras corrigidas geradas pelo Reparo de áudio para exemplos típicos.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |Taxa média de amostras compactadas geradas pelo Reparo de áudio para exemplos típicos.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tempo de ida e volta de estatísticas RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tempo máximo de ida e volta para o fluxo de áudio.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |Média de banda larga MOS de rede para a chamada. Essa métrica depende de perda de pacotes, tremulação e codec usado. O intervalo é 1.0 para 5.0.  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |Mínimo de banda ampla MOS de rede para a chamada.  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |Média prevista de MOS de escuta pontuação para áudio enviado, incluindo nível de fala, nível de ruído e características do dispositivo de captura de banda ampla.  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |SendListenMOS mínimo para a chamada.  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |Pontuação de MOS de escuta de média prevista de banda ampla para áudio recebido da rede, incluindo nível de fala, nível de ruído, codec, condições de rede e características do dispositivo de captura.  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |RecvListenMOS mínimo para a chamada.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indica se o FEC de áudio foi usado para a chamada.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indica a direção do declarada p identificar informações; 1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
   

