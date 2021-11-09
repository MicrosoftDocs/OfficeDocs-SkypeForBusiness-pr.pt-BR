---
title: Tabela AudioSignal
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Cada registro representa métricas de sinal de áudio para um ponto de extremidade. Normalmente, cada chamada tem dois registros, um é para chamador e um é para chamador.
ms.openlocfilehash: ee9029992e925fd43cc55da85bc4a7c127793e54
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60843594"
---
# <a name="audiosignal-table"></a>Tabela AudioSignal
 
Cada registro representa métricas de sinal de áudio para um ponto de extremidade. Normalmente, cada chamada tem dois registros, um é para chamador e um é para chamador. 
  
|**Column**|**Tipo de dados**|**Chave/Índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primário  <br/> |Referenciado na tabela [MediaLine](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primário  <br/> |0: Dados do chamador  <br/> 1: Dados do chamador  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Representa o nível de sinal de áudio do Controle de Ganho Pós-Analógico. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser ao menos 30 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Consulte SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Representa o nível de ruído de áudio do Controle de Ganho Pós-Analógico. A unidade desta medida é o dBmo. Para uma qualidade aceitável, deve ser menor que 35 dBmo. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Consulte SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Métrica de Aprimoramento de Perda de Eco. A unidade desta medida é o dB. Valores mais baixos representam menos eco. Essa medida não é relatada pelo Servidor de Conferência A/V ou telefones IP.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Média de falhas por cinco minutos para a renderização do alto-falante. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Média de falhas por cinco minutos para a captura do microfone. Para uma boa qualidade, deve ser menos de um a cada cinco minutos. Não relatado pelos Servidores de Conferência A/V, Servidores de Mediação ou telefones IP.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal(9,2)  <br/> | <br/> |Taxa de desvio do relógio do dispositivo de microfone, em relação ao relógio da CPU.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal(9,2)  <br/> | <br/> |Taxa de desvio do relógio do dispositivo de alto-falante, em relação ao relógio da CPU.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal(9,2)  <br/> | <br/> |Taxa de desvio do relógio do dispositivo de alto-falante, em relação ao relógio da CPU.  <br/> Média de erro de registro de hora de fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal(9,2)  <br/> | <br/> |Erro médio do carimbo de data/hora do fluxo de renderização do alto-falante, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |Opção de voz é um modo meio-duplex com capacidade de interrupção reduzida. Causas da entrada da opção de voz:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> A causa pode ser uma combinação dessas causas individuais. ENTER_VS_FORCEORCONVERGENCE só pode ser habilitado por regkey para fins de teste.  <br/> O tipo de dados dessa coluna foi alterado no Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causas de um evento de eco:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> A causa pode ser uma combinação dessas causas individuais.  <br/> |
|**EchoPercentMicIn** <br/> |decimal(5,2)  <br/> | <br/> |Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone. Normalmente, os valores são baixos para fones de ouvido ou fones de ouvido e superiores para alto-falantes ou alto-falantes autônomos. Para dispositivos que suportam o cancelamento de eco acústico a bordo, valores altos indicam vazamento de eco. Para outros dispositivos, essa métrica não deve ser usada para avaliar a qualidade do dispositivo.  <br/> |
|**EchoPercentSend** <br/> |decimal(5,2)  <br/> ||Porcentagem de tempo em que o eco é detectado em fluxo enviado. Uma alta porcentagem de eco em fluxos enviados indica um vazamento de eco.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Nível de sinal recebido no Servidor de Mediação do Gateway; isso só se aplica ao Servidor de Mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser de [-30 a -18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Nível de sinal recebido no Servidor de Mediação do Gateway. Se aplica apenas ao Servidor de Mediação. A unidade desta medida é o dBoV. Para uma boa qualidade, a faixa aceitável deve ser menor do que -50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Controle de ganho automático (AGC) no lado do Servidor de Mediação.  <br/> |
|**InitialSignalLevelRMS** <br/> |flutuação  <br/> | <br/> |O quadrado da média raiz (RMS) do sinal de entrada de até os primeiros 30 segundos da chamada.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Nível do sinal recebido no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Nível do sinal recebido no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Nível de ruído recebido no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Nível de ruído recebido no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Nível de sinal conforme enviado no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Nível de sinal conforme enviado no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Nível de ruído conforme enviado no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Nível de ruído conforme enviado no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Nível em dBFS do sinal enviado ao alto-falante para reprodução. Contas para quaisquer ajustes de ganho feitos no sinal recebido. <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Nível em dBFS do conteúdo de ruído no sinal enviado ao alto-falante para reprodução <br/> |

