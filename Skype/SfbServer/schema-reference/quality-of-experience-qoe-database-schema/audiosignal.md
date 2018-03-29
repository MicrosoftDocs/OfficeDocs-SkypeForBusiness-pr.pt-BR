---
title: Tabela AudioSignal
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Cada registro representa métricas de sinal de áudio para um ponto de extremidade. Geralmente, cada chamada tem dois registros, um é do chamador e um é para o receptor.
ms.openlocfilehash: 25d565538ecdf7cae15ff23f539a2e2eddf8680f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="audiosignal-table"></a>Tabela AudioSignal
 
Cada registro representa métricas de sinal de áudio para um ponto de extremidade. Geralmente, cada chamada tem dois registros, um é do chamador e um é para o receptor. 
  
|**Coluna**|**Tipo de dados**|**Índice de chaves /**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |Referenciado de [MediaLine table](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primária  <br/> |0: dados do receptor  <br/> 1: dados do chamador  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Representa o nível de sinal de áudio de controle de ganho de pós-analógicos. A unidade para essa métrica é dBmo. Para obter uma qualidade aceitável, ele deve ser dBmo pelo menos 30. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Veja SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Representa o nível de ruído de áudio de controle de ganho de pós-analógicos. A unidade para essa métrica é dBmo. Para obter uma qualidade aceitável, ele deve ser menor que 35 dBmo. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Veja SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Métrica de aprimoramento de perda de retornar eco. A unidade para essa métrica é dB. Valores inferiores representam menos eco. Essa métrica não é relatada pela / V Conferencing Server ou IP telefones.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Falhas médios por cinco minutos para a renderização de alto-falante. Para obter uma boa qualidade, este deve ser menor do que um por cinco minutos. Não é relatado pela / V Conferencing Servers, servidores de mediação ou IP telefones.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Falhas médios por cinco minutos para a captura de microfone. Para boa qualidade este deve ser menor do que um por cinco minutos. Não é relatado pela / V Conferencing Servers, servidores de mediação ou IP telefones.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |Microfone relógio descompasso taxa dispositivo, relativo ao relógio da CPU.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |Alto-falante relógio taxa de descompasso dispositivo, em relação ao relógio da CPU.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |Alto-falante relógio taxa de descompasso dispositivo, em relação ao relógio da CPU.  <br/> Média de microfone captura stream carimbo erro em tempo, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |Erro de carimbo de hora de fluxo, em milissegundos, de renderização de alto-falante média nos últimos 20 segundos da chamada.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |Opção de voz é um modo half-duplex com capacidade de interrupção reduzida. Causas de entrada de comutador de voz:  <br/> ENTER_VS_BADTS 0X01  <br/> ENTER_VS_ECHO 0X02  <br/> ENTER_VS_FORCEORCONVERGENCE 0X04  <br/> ENTER_VS_DNLP 0X08  <br/> A causa pode ser uma combinação destas causas individuais. ENTER_VS_FORCEORCONVERGENCE só pode ser ativado pelo regkey finalidade de teste.  <br/> O tipo de dados para esta coluna foi alterado no Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causas de um evento de eco:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0X01  <br/> ECHO_EVENT_POSTAEC_ECHO 0X02  <br/> ECHO_EVENT_ANLP 0X04  <br/> ECHO_EVENT_DNLP 0X08  <br/> ECHO_EVENT_MIC_CLIPPING 0X10  <br/> ECHO_EVENT_BAD_STATE 0X20  <br/> A causa pode ser uma combinação destas causas individuais.  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone. Normalmente, os valores são baixos para fones de ouvido ou celulares e mais altos para viva voz e auto falante. Para dispositivos que suportam cancelamento de eco acústico na placa, os altos níveis indicam vazamento de eco. Para outros dispositivos, essa métrica não deve ser utilizada para avaliar a qualidade do dispositivo.  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||Porcentagem de tempo quando o eco seja detectado no stream enviado. Porcentagem de eco alta nos enviar fluxos uma indicação do vazamento de eco.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Nível de sinal no servidor de mediação recebido do Gateway; Isso se aplica somente ao servidor de mediação. A unidade dessa métrica é dBoV. Para obter uma boa qualidade, o intervalo aceitável deve ser [-30-18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Nível de sinal recebido no servidor de mediação do Gateway. Isso se aplica somente ao servidor de mediação. A unidade dessa métrica é dBoV. Para boa qualidade, o intervalo aceitável deve ser menor que-50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Controle (AGC) no lado do servidor de mediação de ganho automático.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |A raiz quadrada média (RMS) do sinal de entrada até dos primeiros 30 segundos da chamada.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Nível de sinal como recebido no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Nível de sinal como recebido no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Nível de ruído como recebido no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Nível de ruído como recebido no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Nível de sinal como enviado no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Nível de sinal como enviado no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Nível de ruído como enviado no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Nível de ruído como enviado no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
   

