---
title: Exibição AudioStreamDetail
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: A exibição AudioStreamDetail armazena informações sobre cada fluxo de áudio no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 3485ac8e8f2f38e7440ef723dfa40b3530589fc8
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60741857"
---
# <a name="audiostreamdetail-view"></a>Exibição AudioStreamDetail
 
A exibição AudioStreamDetail armazena informações sobre cada fluxo de áudio no banco de dados. Essa exibição foi introduzida no Microsoft Lync Server 2013.
  
|**Column**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|SessionTime  <br/> |datetime  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|StreamId  <br/> |int  <br/> |Identificação exclusiva em uma linha de mídia.  <br/> |
|StartTime  <br/> |datetime  <br/> |Hora de início da sessão.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoria de caixa de diálogo: 0 é a Skype for Business Server para o Servidor de Mediação; 1 é a etapa de gateway do Servidor de Mediação para PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Sinalizador que indica se a chamada foi ignorada ou não.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Se presente, indica porque uma chamada não foi ignorada, mesmo se as IDs de desvio correspondem. Apenas um valor é definido:  <br/> 0x0001 - ID de bypass desconhecido para adaptador de rede padrão.  <br/> |
|CallPriority  <br/> |int  <br/> |Prioridade da chamada.  <br/> |
|CallerPool  <br/> |nvarchar(256)  <br/> |Pool FQDN do chamador.  <br/> |
|CalleePool  <br/> |nvarchar(256)  <br/> |FQDN do pool do receptor de chamada.  <br/> |
|Chamador  <br/> |nvarchar(450)  <br/> |URI do chamador.  <br/> |
|Chamador  <br/> |nvarchar(450)  <br/> |URI do chamador.  <br/> |
|CallerUserAgent  <br/> |nvarchar(256)  <br/> |Cadeia de caracteres de agente de usuário do chamador.  <br/> |
|CallerUserAgentType  <br/> |smallint  <br/> |Tipo do agente de usuário do chamador. Consulte a [tabela UserAgent para](useragent.md) obter detalhes. <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU no ponto de extremidade do chamador.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos de CPU no ponto de extremidade do chamador.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do chamador.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do chamador está em execução em um ambiente virtualizado. Consulte a [tabela Ponto de Extremidade](endpoint.md) para obter mais informações. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do chamador está sendo executado em um ambiente virtualizado. Consulte a [tabela Ponto de Extremidade](endpoint.md) para obter mais informações. <br/> |
|CorrelationKey  <br/> ||Chave de correlação. Referenciado da tabela [SessionCorrelation.](sessioncorrelation.md)  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informações sobre o caminho de mídia, como direto ou retransmitido. Consulte a [tabela MediaLine para](medialine-0.md) obter mais informações. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do autor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de ICE (Estabelecimento de Conectividade Interativa) descrito em sinalizadores de bits do receptor da chamada. Para obter detalhes, consulte a Especificação de protocolo do servidor de monitoramento de Qualidade da Experiência.  <br/> |
|Transport  <br/> |tinyint  <br/> |Tipo de transporte: 0 é UDP, 1 é TCP.  <br/> |
|CallerIPAddr  <br/> |var(50)  <br/> |Endereço IP do autor da chamada. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se o chamador está na rede de intervalo: 1 significa que o chamador está na rede empresarial, 0 significa que está fora da rede.  <br/> |
|CalleeIPAddr  <br/> |var(50)  <br/> |Endereço IP do receptor. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta usada pelo receptor.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica se o receptor está na rede de intervalo: 1 significa que o receptor está na rede empresarial, 0 significa que está fora da rede.  <br/> |
|CallerUserSite  <br/> |nvarchar(128)  <br/> |Nome do site do chamador.  <br/> |
|CallerRegion  <br/> |nvarchar(128)  <br/> |Nome do país/região do site do chamador.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128)  <br/> |Nome do site do chamador.  <br/> |
|CalleeRegion  <br/> |nvarchar(128)  <br/> |Nome do país/região do site do chamador.  <br/> |
|CallerRelayIPAddr  <br/> |var(50)  <br/> |Endereço IP do serviço de borda A/V usado pelo chamador. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Port used on the A/V Edge service used by the caller.  <br/> |
|CalleeRelayIPAddr  <br/> |var(50)  <br/> |Chave de endereço IP do serviço de borda A/V usado pelo receptor. Consulte a [tabela IPAddress para](ipaddress.md) obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usada no serviço de borda A/V usado pelo receptor.  <br/> |
|CallerCaptureDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CallerRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CallerRenderDriver  <br/> |varchar(256)  <br/> |Nome do driver de dispositivo de renderização do chamador.  <br/> |
|CalleeCaptureDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDev  <br/> |varchar(256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar(256)  <br/> |Nome do driver do dispositivo de renderização do chamador.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexão de rede do chamador: 0 é com fio, 1 é sem fio.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se o autor da chamada se conectou por uma rede privada virtual: 1 é a rede privada virtual (VPN), 0 é não VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidade da rede dos pontos de extremidade do chamador em bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexão de rede do chamador: 0 é com fio, 1 é sem fio.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se o autor da chamada se conectou por uma rede privada virtual: 1 é a rede privada virtual (VPN), 0 é não VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal(18,0)  <br/> |Velocidade de rede do ponto de extremidade do receptor em bps.  <br/> |
|ConversationalMOS  <br/> |decimal(3,2)  <br/> |MOS da Conversa de Banda Estreita das sessões de áudio (com base nos dois fluxos de áudio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |Largura de banda aplicada a determinado fluxo de envio considerando várias configurações de política (TURN, API, SDP, Servidor de política etc.). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma menor largura de banda efetiva com base na estimativa de largura de banda. Isso é basicamente a largura de banda máxima a qual o fluxo de envio pode aceitar limites de bloqueio impostos pela estimativa de largura de banda  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Média de tremulação de rede a partir da estatística do protocolo RTCP.  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Tremulação máxima da rede durante a chamada.  <br/> |
|PacketLossRate  <br/> |decimal(5,4)  <br/> |Taxa média de perda de pacotes durante a chamada.  <br/> |
|PacketLossRateMax  <br/> |decimal(5,4)  <br/> |Perda máxima de pacotes observada durante a chamada.  <br/> |
|BurstDensity  <br/> |decimal(9,4)  <br/> |Densidade média de perda de pacote durante picos de perdas em uma chamada.  <br/> |
|BurstDuration  <br/> |int  <br/> |Duração média de perda de pacote durante picos de perdas durante a chamada.  <br/> |
|BurstGapDensity  <br/> |decimal(9,4)  <br/> |Densidade média de perda de pacote durante intervalos entre picos de perda de pacotes.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Duração média de intervalos entre picos de perda de pacotes.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Contagem de pacotes para o fluxo de áudio.  <br/> |
|BandwidthEst  <br/> |int  <br/> |Estimativas de largura de banda para o fluxo de áudio.  <br/> |
|DegradationAvg  <br/> |decimal(3,2)  <br/> |Degradação de MOS de rede para a chamada completa. O intervalo vai de 0,0 a 5,0. Essa métrica mostra o quanto o MOS de rede foi reduzido por causa de tremulação e perda de pacote. Para obter a qualidade aceitável, o MOS da rede deve ser menor que 0,5.  <br/> |
|DegradationMax  <br/> |decimal(3,2)  <br/> |Degradação máxima de MOS de rede durante a chamada.  <br/> |
|DegradationJitterAvg  <br/> |decimal(3,2)  <br/> |Degradação de MOS de rede causada por tremulação.  <br/> |
|DegradationPacketLossAvg  <br/> |decimal(3,2)  <br/> |Degradação de MOS de rede causada por perda de pacote.  <br/> |
|PayloadDescription  <br/> |int  <br/> |O codec de áudio usado para a chamada, referenciado da [tabela PayloadDescription](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Taxa de amostragem para o fluxo de áudio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |Nível do sinal de áudio de controle de ganho pós-analógico do áudio enviado pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Nível do sinal de áudio do áudio recebido pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho pós-analógico do áudio enviado pelo chamador. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho pós-analógico do áudio recebido pelo chamado. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Aprimoramento de perda e retorno de eco do chamador. A unidade desta medida é o dB. Valores mais baixos representam menos eco. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Média de falhas por cinco minutos para a renderização do alto-falante do chamador. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Média de falhas por cinco minutos para a captura de microfone do chamador. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Taxa de desvio do relógio do dispositivo de microfone do chamador, em relação ao relógio da CPU.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Taxa de desvio do relógio do dispositivo de alto-falante do chamador, em relação ao relógio da CPU.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Média do erro de carimbo de data/hora do fluxo de renderização do alto-falante do chamador, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida. Consulte a [tabela MediaLine para](medialine-0.md) obter mais informações. <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Causas de um evento de eco para o chamador. Consulte a [tabela MediaLine para](medialine-0.md) obter mais informações. <br/> |
|CallerEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Porcentagem de tempo em que o eco é detectado no fluxo de captura de microfone do chamador. Caso seja utilizado headset, o valor deve ser baixo.  <br/> |
|CallerEchoPercentSend  <br/> |decimal(5,2)  <br/> |Porcentagem de tempo em que o eco é detectado no fluxo enviado do chamador. Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Nível de sinal recebido no Servidor de Mediação do Gateway para o áudio do chamador; isso só se aplica ao Servidor de Mediação. A unidade desta medida é o dBoV. Para obter uma boa qualidade, o intervalo aceitável deve ser entre -30 a -18 dBoV.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Nível de sinal recebido no Servidor de Mediação do Gateway para o áudio do chamador. Se aplica apenas ao Servidor de Mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Controle de ganho automático (AGC) no lado do Servidor de Mediação aplicado ao áudio do chamador.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |flutuação  <br/> |Raiz quadrada média (RMS) o sinal de entrada para o chamador pelos 30 primeiros segundos da chamada.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Representa o nível de sinal de áudio de controle de ganho pós-analógico do áudio enviado pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Nível do sinal de áudio do áudio recebido pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho pós-analógico do áudio enviado pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho pós-analógico do áudio recebido pelo receptor. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Aprimoramento de perda e retorno de eco do receptor. A unidade desta medida é o dB. Valores mais baixos representam menos eco. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Média de falhas por cinco minutos para a renderização do alto-falante do chamador. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Média de falhas por cinco minutos para a captura de microfone do chamador. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal(9,2)  <br/> |Taxa de desvio do relógio do dispositivo de microfone do chamador, em relação ao relógio da CPU.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal(9,2)  <br/> |Taxa de desvio do relógio do dispositivo de alto-falante do chamador, em relação ao relógio da CPU.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal(9,2)  <br/> |Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal(9,2)  <br/> |Média do erro de carimbo de data/hora de renderização do alto-falante do chamador, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida. Consulte a [tabela MediaLine para](medialine-0.md) obter mais informações. <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Causa um evento de eco para o receptor. Consulte a [tabela MediaLine para](medialine-0.md) obter mais informações. <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal(5,2)  <br/> |Porcentagem de tempo em que o eco é detectado no fluxo de captura de microfone do chamador. Caso seja utilizado headset, o valor deve ser baixo.  <br/> |
|CalleeEchoPercentSend  <br/> |decimal(5,2)  <br/> |Porcentagem de tempo em que o eco é detectado no fluxo enviado do chamador. Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Nível de sinal recebido no Servidor de Mediação do Gateway para o áudio do chamador; isso só se aplica ao Servidor de Mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser de [-30 a -18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Nível de sinal recebido no Servidor de Mediação do Gateway para o áudio do chamador. Se aplica apenas ao Servidor de Mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Controle de ganho automático (AGC) no lado do Servidor de Mediação aplicado ao áudio do chamador.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |flutuação  <br/> |Raiz quadrada média (RMS) do sinal de entrada para o receptor durante os 30 primeiros segundos da chamada.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal(5,2)  <br/> |Taxa média de amostras escondidas geradas pelo reparo de áudio para exemplos típicos.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal(5,2)  <br/> |Taxa média de amostras corrigidas geradas pelo reparo de áudio para exemplos típicos.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal(5,2)  <br/> |Taxa média de amostras compactadas geradas pelo reparo de áudio para exemplos típicos.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tempo de ida e volta de estatísticas RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tempo máximo de ida e volta para o fluxo de áudio.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal(3,2)  <br/> |Média de MOS de rede de banda ampla para a chamada. Essa métrica depende da perda de pacote, da tremulação e do codec usado. O intervalo é de 1.0 a 5.0.  <br/> |
|OverallMinNetworkMOS  <br/> |decimal(3,2)  <br/> |Mínimo de MOS de rede de banda ampla para a chamada.  <br/> |
|SendListenMOS  <br/> |decimal(3,2)  <br/> |Pontuação média prevista de MOS de escuta de banda larga do áudio enviado, incluindo nível de fala, nível de ruído e características de dispositivo de captura.  <br/> |
|SendListenMOSMin  <br/> |decimal(3,2)  <br/> |SendListenMOS mínimo da chamada.  <br/> |
|RecvListenMOS  <br/> |decimal(3,2)  <br/> |Pontuação média prevista de MOS de escuta de banda larga do áudio recebido da rede, incluindo nível de fala, nível de ruído, codec, condições da rede e características do dispositivo de captura.  <br/> |
|RecvListenMOSMin  <br/> |decimal(3,2)  <br/> |RecvListenMOS mínimo da chamada.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indica se o FEC de áudio foi usado para a chamada.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indica a direção das informações de identidade declarada; 1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
   

