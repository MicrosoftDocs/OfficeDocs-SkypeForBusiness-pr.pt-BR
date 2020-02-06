---
title: Exibição AudioStreamDetail
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: b6a435b3-103c-41c4-96ed-33c3784534c0
description: A exibição AudioStreamDetail armazena informações sobre cada fluxo de áudio no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 14815a107654fc83fc2b71c5070b82617154677c
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810869"
---
# <a name="audiostreamdetail-view"></a>Exibição AudioStreamDetail
 
A exibição AudioStreamDetail armazena informações sobre cada fluxo de áudio no banco de dados. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
  
|**Coluna**|**Tipo de dados**|**Detalhes**|
|:-----|:-----|:-----|
|Sessiontime  <br/> |datetime  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|SessionSeq  <br/> |int  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|Streamid  <br/> |int  <br/> |ID exclusiva dentro de uma linha de mídia.  <br/> |
|StartTime   <br/> |datetime  <br/> |Hora de início da sessão.  <br/> |
|EndTime  <br/> |datetime  <br/> |Hora de término da sessão.  <br/> |
|DialogCategory  <br/> |bit  <br/> |Categoria do diálogo: 0 é o trecho do servidor do Skype for Business para o segmento do servidor de mediação; 1 é o servidor de mediação para a perna do gateway PSTN.  <br/> |
|MediationServerBypassFlag  <br/> |bit  <br/> |Sinalizador que indica se a chamada foi ignorada ou não.  <br/> |
|MediaBypassWarningFlag  <br/> |int  <br/> |Se presente, indica por que uma chamada não foi ignorada mesmo se as IDs de bypass forem atendidas. Somente um valor é definido:  <br/> 0x0001-ID de bypass desconhecido para o adaptador de rede padrão.  <br/> |
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
|CallerCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos da CPU no ponto de extremidade do chamador.  <br/> |
|CalleeCPUNumberOfCores  <br/> |smallint  <br/> |Número de núcleos da CPU no ponto de extremidade do chamador.  <br/> |
|CallerCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do chamador.  <br/> |
|CalleeCPUProcessorSpeed  <br/> |int  <br/> |Velocidade do processador da CPU do ponto de extremidade do chamador.  <br/> |
|CallerVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do chamador está em execução em um ambiente virtualizado. Consulte a [tabela de pontos de extremidade](endpoint.md) para obter mais informações. <br/> |
|CalleeVirtualizationFlag  <br/> |tinyint  <br/> |Indica se o sistema do chamador está em execução em um ambiente virtualizado. Consulte a [tabela de pontos de extremidade](endpoint.md) para obter mais informações. <br/> |
|CorrelationKey  <br/> ||Chave de correlação. Referenciado da [tabela SessionCorrelation](sessioncorrelation.md).  <br/> |
|ConnectivityIce  <br/> |tinyint  <br/> |Informações sobre o caminho de mídia, como direta ou retransmitida. Consulte a [tabela de mídia](medialine-0.md) para obter mais informações. <br/> |
|CallerIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador. Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.  <br/> |
|CalleeIceWarningFlags  <br/> |int  <br/> |Informações sobre o processo de estabelecimento de conectividade interativa (ICE) descrito em sinalizadores de bits para o chamador. Para obter detalhes, consulte a especificação de protocolo de servidor de monitoração de experiência de qualidade.  <br/> |
|SMTP  <br/> |tinyint  <br/> |Tipo de transporte: 0 é UDP; 1 é o TCP.  <br/> |
|CallerIPAddr  <br/> |var (50)  <br/> |Endereço IP do chamador. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CallerPort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CallerInside  <br/> |bit  <br/> |Indica se o chamador está dentro da rede de intervalo: 1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.  <br/> |
|CalleeIPAddr  <br/> |var (50)  <br/> |Endereço IP do chamador. Pode ser um endereço IPv4 ou IPv6.  <br/> |
|CalleePort  <br/> |int  <br/> |Porta usada pelo chamador.  <br/> |
|CalleeInside  <br/> |bit  <br/> |Indica se a chamada está dentro do intervalo de rede: 1 significa que a chamada está dentro da rede corporativa, 0 significa que o chamador está fora da rede.  <br/> |
|CallerUserSite  <br/> |nvarchar(128  <br/> |Nome do site do chamador.  <br/> |
|CallerRegion  <br/> |nvarchar(128  <br/> |Nome do país/região do site do chamador.  <br/> |
|CalleeUserSite  <br/> |nvarchar(128  <br/> |Nome do site do chamador.  <br/> |
|CalleeRegion  <br/> |nvarchar(128  <br/> |Nome do país/região do site do chamador.  <br/> |
|CallerRelayIPAddr  <br/> |var (50)  <br/> |Endereço IP do serviço de borda A/V usado pelo chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CallerRelayPort  <br/> |int  <br/> |Porta usada no serviço de borda A/V usado pelo chamador.  <br/> |
|CalleeRelayIPAddr  <br/> |var (50)  <br/> |Chave de endereço IP do serviço de borda A/V usado pelo chamador. Consulte a [tabela IPAddress](ipaddress.md) para obter mais informações. <br/> |
|CalleeRelayPort  <br/> |int  <br/> |Porta usada no serviço de borda A/V usado pelo chamador.  <br/> |
|CallerCaptureDev  <br/> |varchar (256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CallerRenderDev  <br/> |varchar (256)  <br/> |Nome do dispositivo de renderização do chamador.  <br/> |
|CallerCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CallerRenderDriver  <br/> |varchar (256)  <br/> |O nome do driver de dispositivo de renderização do chamador.  <br/> |
|CalleeCaptureDev  <br/> |varchar (256)  <br/> |Nome do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDev  <br/> |varchar (256)  <br/> |Nome do dispositivo de renderização do Calle.  <br/> |
|CalleeCaptureDevDriver  <br/> |varchar (256)  <br/> |Nome do driver do dispositivo de captura do chamador.  <br/> |
|CalleeRenderDevDriver  <br/> |varchar (256)  <br/> |Chame o nome do driver do dispositivo de processamento do recurso.  <br/> |
|CallerNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.  <br/> |
|CallerVPN  <br/> |bit  <br/> |Indica se o chamador está conectado por meio de uma rede privada virtual: 1 é uma rede virtual privada (VPN), 0 não é VPN.  <br/> |
|CallerLinkSpeed  <br/> |decimal (18, 0)  <br/> |Velocidade do link de rede para o ponto de extremidade do chamador em bps.  <br/> |
|CalleeNetworkConnectionType  <br/> |tinyint  <br/> |Tipo de conexão de rede do chamador: 0 é cabeado, 1 é sem fio.  <br/> |
|CalleeVPN  <br/> |bit  <br/> |Indica se o chamador está conectado por meio de uma rede privada virtual: 1 é uma rede virtual privada (VPN), 0 não é VPN.  <br/> |
|CalleeLinkSpeed  <br/> |decimal (18, 0)  <br/> |Velocidade do link de rede para o ponto de extremidade do chamador em bps.  <br/> |
|ConversationalMOS  <br/> |decimal (3; 2)  <br/> |O MOS de conversa de banda estreita das sessões de áudio (com base nos dois fluxos de áudio).  <br/> |
|AppliedBandwidthLimit  <br/> |int  <br/> |A largura de banda real aplicada ao fluxo de envio do lado fornecido tem várias configurações de política (ativar, API, SDP, servidor de política e assim por diante). Isso não deve ser confundido com a largura de banda efetiva porque pode haver uma largura de banda mais econômica com base na estimativa de largura de banda. Isso é basicamente a largura de banda máxima que o fluxo de envio pode ter limites de bloqueio impostos pela estimativa da largura de banda  <br/> |
|JitterInterArrival  <br/> |int  <br/> |Tremulação média de rede de estatísticas de protocolo de controle de tempo real (RTCP).  <br/> |
|JitterInterArrivalMax  <br/> |int  <br/> |Maior tremulação de rede durante a chamada.  <br/> |
|PacketLossRate  <br/> |decimal (5, 4)  <br/> |Taxa média de perda de pacotes durante a chamada.  <br/> |
|PacketLossRateMax  <br/> |decimal (5, 4)  <br/> |Perda máxima de pacote observado durante a chamada.  <br/> |
|BurstDensity  <br/> |decimal (9, 4)  <br/> |Densidade média de perda de pacote durante intermitências de perdas durante a chamada.  <br/> |
|BurstDuration  <br/> |int  <br/> |Duração média da perda de pacote durante intermitências de perdas durante a chamada.  <br/> |
|BurstGapDensity  <br/> |decimal (9, 4)  <br/> |Densidade média de perda de pacote durante intervalos entre intermitências de perda de pacote.  <br/> |
|BurstGapDuration  <br/> |int  <br/> |Duração média de lacunas entre intermitências de perda de pacote.  <br/> |
|PacketUtilization  <br/> |int  <br/> |Contagem de pacotes para o fluxo de áudio.  <br/> |
|Largura de banda  <br/> |int  <br/> |Estimativas de largura de banda para o fluxo de áudio.  <br/> |
|DegradationAvg  <br/> |decimal (3; 2)  <br/> |Degradação do MOS de rede para toda a chamada. O intervalo é de 0,0 a 5,0. Essa métrica mostra o valor que o MOS de rede foi reduzido devido à instabilidade e à perda de pacote. Para ter uma qualidade aceitável, ele deve ser menor do que 0,5.  <br/> |
|DegradationMax  <br/> |decimal (3; 2)  <br/> |Degradação do MOS de rede máxima durante a chamada.  <br/> |
|DegradationJitterAvg  <br/> |decimal (3; 2)  <br/> |Degradação de MOS de rede causada pela tremulação.  <br/> |
|DegradationPacketLossAvg  <br/> |decimal (3; 2)  <br/> |Degradação de MOS de rede causada por perda de pacote.  <br/> |
|PayloadDescription  <br/> |int  <br/> |O codec de áudio usado para a chamada, referenciada na [tabela PayloadDescription](payloaddescription.md).  <br/> |
|AudioSampleRate  <br/> |int  <br/> |Taxa de amostragem do fluxo de áudio.  <br/> |
|CallerSendSignalLevel  <br/> |int  <br/> |O nível de sinal de áudio pós-analógico de controle de ganho para o áudio enviado pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|CallerRecvSignalLevel  <br/> |int  <br/> |Nível de sinal de áudio para o áudio recebido pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|CallerSendNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio enviado pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|CallerRecvNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio recebido pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|CallerEchoReturn  <br/> |int  <br/> |Aprimoramento da perda de retorno de eco para o chamador. A unidade para essa métrica é dB. Valores inferiores representam menos eco. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|CallerSpeakerGlitchRate  <br/> |int  <br/> |Média de falhas por cinco minutos para a renderização de alto-falante do chamador. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.  <br/> |
|CallerMicGlitchRate  <br/> |int  <br/> |Média de falhas por cinco minutos para a captura de microfone do chamador. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.  <br/> |
|CallerTimestampDriftRateMic  <br/> |decimal (9; 2)  <br/> |Taxa de descompasso do relógio do dispositivo de microfone do chamador, relativa ao relógio da CPU.  <br/> |
|CallerTimestampDriftRateSpk  <br/> |decimal (9; 2)  <br/> |Taxa de descompasso do relógio do dispositivo de alto-falante do chamador em relação ao relógio da CPU.  <br/> |
|CallerTimestampErrorMicMs  <br/> |decimal (9; 2)  <br/> |Erro de carimbo de data/hora médio do fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CallerTimestampErrorSpkMs  <br/> |decimal (9; 2)  <br/> |Média do alto-falante do chamador processar carimbo de data/hora do fluxo, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CallerVsEntryCauses  <br/> |smallint  <br/> |A opção de voz é um modo Half-duplex com capacidade de interrupção reduzida. Consulte a [tabela de mídia](medialine-0.md) para obter mais informações. <br/> |
|CallerEchoEventCauses  <br/> |tinyint  <br/> |Causa de um evento de eco para o chamador. Consulte a [tabela de mídia](medialine-0.md) para obter mais informações. <br/> |
|CallerEchoPercentMicIn  <br/> |decimal (5; 2)  <br/> |Porcentagem de tempo em que o eco é detectado no fluxo de captura de microfone do chamador. Se o fone de ouvido estiver sendo usado, o valor deve ser baixo.  <br/> |
|CallerEchoPercentSend  <br/> |decimal (5; 2)  <br/> |Porcentagem de tempo em que o eco é detectado no fluxo de envio do chamador. Alta porcentagem de eco em enviar transmite uma indicação de vazamento de eco.  <br/> |
|CallerRxAGCSignalLevel  <br/> |int  <br/> |Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador; Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser de-30 a-18 dBoV.  <br/> |
|CallerRxAGCNoiseLevel  <br/> |int  <br/> |Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador. Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser menor do que-50 dBoV.  <br/> |
|CallerRxAGCGain  <br/> |int  <br/> |Controle de ganho automático (AGC) no lado do servidor de mediação aplicado ao áudio do chamador.  <br/> |
|CallerInitialSignalLevelRMS  <br/> |float  <br/> |A base média (RMS) do sinal de entrada para o chamador para até os primeiros 30 segundos da chamada.  <br/> |
|CalleeSendSignalLevel  <br/> |int  <br/> |Representa o nível de sinal de áudio de controle de ganho de cruz analógico para o áudio enviado pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|CalleeRecvSignalLevel  <br/> |int  <br/> |Nível de sinal de áudio para o áudio que o chama recebido. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|CalleeSendNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio enviado pelo chamador. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|CalleeRecvNoiseLevel  <br/> |int  <br/> |Nível de ruído de áudio de controle de ganho analógico-analógico para o áudio que o chamador recebeu. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|CalleeEchoReturn  <br/> |int  <br/> |Aprimoramento da perda de retorno de eco para o chamador. A unidade para essa métrica é dB. Valores inferiores representam menos eco. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|CalleeSpeakerGlitchRate  <br/> |int  <br/> |Média de falhas por cinco minutos para a renderização do alto-falante do chamador. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.  <br/> |
|CalleeMicGlitchRate  <br/> |int  <br/> |Média de falhas por cinco minutos para a captura de microfone do chamador. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.  <br/> |
|CalleeTimestampDriftRateMic  <br/> |decimal (9; 2)  <br/> |Taxa de descompasso do relógio do dispositivo de microfone do chamador, em relação ao relógio da CPU.  <br/> |
|CalleeTimestampDriftRateSpk  <br/> |decimal (9; 2)  <br/> |Taxa de descompasso do relógio do dispositivo de alto-falante do chamador, em relação ao relógio da CPU.  <br/> |
|CalleeTimestampErrorMicMs  <br/> |decimal (9; 2)  <br/> |Erro de carimbo de data/hora médio do fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CalleeTimestampErrorSpkMs  <br/> |decimal (9; 2)  <br/> |Média do erro de carimbo de data/hora do fluxo de processamento do palestrante em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|CalleeVsEntryCauses  <br/> |smallint  <br/> |A opção de voz é um modo Half-duplex com capacidade de interrupção reduzida. Consulte a [tabela de mídia](medialine-0.md) para obter mais informações. <br/> |
|CalleeEchoEventCauses  <br/> |tinyint  <br/> |Causas de um evento de eco para o chamador. Consulte a [tabela de mídia](medialine-0.md) para obter mais informações. <br/> |
|CalleeEchoPercentMicIn  <br/> |decimal (5; 2)  <br/> |Porcentagem de tempo em que o eco é detectado no fluxo de captura do microfone do chamador. Se o fone de ouvido estiver sendo usado, o valor deve ser baixo.  <br/> |
|CalleeEchoPercentSend  <br/> |decimal (5; 2)  <br/> |Porcentagem de tempo em que o eco é detectado no fluxo enviado do chamador. Alta porcentagem de eco em enviar transmite uma indicação de vazamento de eco.  <br/> |
|CalleeRxAGCSignalLevel  <br/> |int  <br/> |Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador; Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser [-30 a-18] dBoV.  <br/> |
|CalleeRxAGCNoiseLevel  <br/> |int  <br/> |Nível de sinal recebido no servidor de mediação do gateway para o áudio do chamador. Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser menor do que-50 dBoV.  <br/> |
|CalleeRxAGCGain  <br/> |int  <br/> |Controle de ganho automático (AGC) no lado do servidor de mediação aplicado ao áudio do chamador.  <br/> |
|CalleeInitialSignalLevelRMS  <br/> |float  <br/> |A base média (RMS) do sinal de entrada para o receptor para até os primeiros 30 segundos da chamada.  <br/> |
|RatioConcealedSamplesAvg  <br/> |decimal (5; 2)  <br/> |Índice médio de amostras ocultas geradas pelo reparo de áudio para amostras típicas.  <br/> |
|RatioStretchedSamplesAvg  <br/> |decimal (5; 2)  <br/> |Índice médio de amostras ampliadas geradas pelo reparo de áudio para amostras típicas.  <br/> |
|RatioCompressedSamplesAvg  <br/> |decimal (5; 2)  <br/> |Índice médio de amostras compactadas geradas pelo reparo de áudio para amostras típicas.  <br/> |
|RoundTrip  <br/> |int  <br/> |Tempo de ida e volta das estatísticas do RTCP.  <br/> |
|RoundTripMax  <br/> |int  <br/> |Tempo máximo de ida e volta do fluxo de áudio.  <br/> |
|OverallAvgNetworkMOS  <br/> |decimal (3; 2)  <br/> |Banda larga médio de um MOS de rede para a chamada. Essa métrica depende da perda de pacotes, da tremulação e do codec usados. O intervalo é de 1,0 a 5,0.  <br/> |
|OverallMinNetworkMOS  <br/> |decimal (3; 2)  <br/> |Banda larga de rede mínima para a chamada.  <br/> |
|SendListenMOS  <br/> |decimal (3; 2)  <br/> |Pontuação estimada banda larga de escuta da MOS para áudio enviado, incluindo o nível de fala, o nível de ruído e as características do dispositivo de captura.  <br/> |
|SendListenMOSMin  <br/> |decimal (3; 2)  <br/> |SendListenMOS mínima para a chamada.  <br/> |
|RecvListenMOS  <br/> |decimal (3; 2)  <br/> |Média prevista banda larga ouvindo a Pontuação do MOS para áudio recebido da rede, incluindo o nível de fala, o nível de ruído, o codec, as condições da rede e as características do dispositivo de captura.  <br/> |
|RecvListenMOSMin  <br/> |decimal (3; 2)  <br/> |RecvListenMOS mínima para a chamada.  <br/> |
|AudioFECUsed  <br/> |bit  <br/> |Indica se o FEC de áudio foi usado para a chamada.  <br/> |
|SenderIsCallerPAI  <br/> |bit  <br/> |Indica a direção das informações de identificação p-declaradas; 1 significa que a direção do fluxo é do chamador para o receptor; 0 significa que a direção do fluxo é do receptor para o chamador.  <br/> |
   

