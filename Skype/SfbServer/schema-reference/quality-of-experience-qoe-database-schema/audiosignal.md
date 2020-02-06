---
title: Tabela AudioSignal
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0013c8c6-cdf9-4d70-bc2a-cddd1560f66b
description: Cada registro representa as métricas do sinal de áudio para um ponto de extremidade. Geralmente, cada chamada tem dois registros, um é para o chamador e um é para o receptor.
ms.openlocfilehash: d1b35aa4111feb77ae905e833d7bb1f4d4acd01e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41810669"
---
# <a name="audiosignal-table"></a>Tabela AudioSignal
 
Cada registro representa as métricas do sinal de áudio para um ponto de extremidade. Geralmente, cada chamada tem dois registros, um é para o chamador e um é para o receptor. 
  
|**Coluna**|**Tipo de dados**|**Chave/índice**|**Detalhes**|
|:-----|:-----|:-----|:-----|
|**ConferenceDateTime** <br/> |datetime  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**SessionSeq** <br/> |int  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**MediaLineLabel** <br/> |tinyint  <br/> |Primária  <br/> |Referenciado da [tabela de mídia](medialine-0.md).  <br/> |
|**FromCaller** <br/> |bit  <br/> |Primária  <br/> |0: dados do chamador  <br/> 1: dados do chamador  <br/> |
|**SendSignalLevel** <br/> |int  <br/> | <br/> |Representa o nível de sinal de áudio de controle de ganho de cruz analógico. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, ele deve ter pelo menos 30 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|**RecvSignalLevel** <br/> |int  <br/> | <br/> |Consulte SendSignalLevel.  <br/> |
|**SendNoiseLevel** <br/> |int  <br/> | <br/> |Representa o nível de ruído de áudio de controle de ganho analógicos. A unidade para essa métrica é dBmo. Para ter uma qualidade aceitável, deve ser menor do que 35 dBmo. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|**RecvNoiseLevel** <br/> |int  <br/> | <br/> |Consulte SendNoiseLevel.  <br/> |
|**EchoReturn** <br/> |int  <br/> | <br/> |Métrica de aprimoramento de perda de retorno de eco. A unidade para essa métrica é dB. Valores inferiores representam menos eco. Essa métrica não é reportada pelo servidor de conferência A/V ou por telefones IP.  <br/> |
|**AudioSpeakerGlitchRate** <br/> |int  <br/> | <br/> |Média de falhas por cinco minutos para a renderização de alto-falante. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.  <br/> |
|**AudioMicGlitchRate** <br/> |int  <br/> | <br/> |Média de falhas por cinco minutos para a captura de microfone. Para ter uma boa qualidade, isso deve ser inferior a um por cinco minutos. Não relatado por servidores de conferência A/V, servidores de mediação ou telefones IP.  <br/> |
|**AudioTimestampDriftRateMic** <br/> |decimal (9; 2)  <br/> | <br/> |Taxa de descompasso do relógio do dispositivo de microfone, relativa ao relógio da CPU.  <br/> |
|**AudioTimestampDriftRateSpk** <br/> |decimal (9; 2)  <br/> | <br/> |Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.  <br/> |
|**AudioTimestampErrorMicMs** <br/> |decimal (9; 2)  <br/> | <br/> |Taxa de descompasso do relógio do dispositivo de alto-falante, relativa ao relógio da CPU.  <br/> Erro de carimbo de data/hora médio do fluxo de captura de microfone, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|**AudioTimestampErrorSpkMs** <br/> |decimal (9; 2)  <br/> | <br/> |Média de um erro de carimbo de data/hora do fluxo de alto-falante, em milissegundos, nos últimos 20 segundos da chamada.  <br/> |
|**VsEntryCauses** <br/> |smallint  <br/> | <br/> |A opção de voz é um modo Half-duplex com capacidade de interrupção reduzida. Causas da entrada da opção de voz:  <br/> ENTER_VS_BADTS 0x01  <br/> ENTER_VS_ECHO 0x02  <br/> ENTER_VS_FORCEORCONVERGENCE 0x04  <br/> ENTER_VS_DNLP 0x08  <br/> A causa pode ser uma combinação dessas causas individuais. ENTER_VS_FORCEORCONVERGENCE só pode ser habilitado pela RegKey para fins de teste.  <br/> O tipo de dados para esta coluna foi alterado no Microsoft Lync Server 2013.  <br/> |
|**EchoEventCauses** <br/> |tinyint  <br/> | <br/> |Causas de um evento de eco:  <br/> ECHO_EVENT_BAD_TIMESTAMP 0x01  <br/> ECHO_EVENT_POSTAEC_ECHO 0x02  <br/> ECHO_EVENT_ANLP 0x04  <br/> ECHO_EVENT_DNLP 0x08  <br/> ECHO_EVENT_MIC_CLIPPING 0x10  <br/> ECHO_EVENT_BAD_STATE 0x20  <br/> A causa pode ser uma combinação dessas causas individuais.  <br/> |
|**EchoPercentMicIn** <br/> |decimal (5; 2)  <br/> | <br/> |Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone. Normalmente, os valores são baixos para fones de ouvido ou celulares e mais altos para viva voz e auto falante. Para dispositivos que suportam cancelamento de eco acústico na placa, os altos níveis indicam vazamento de eco. Para outros dispositivos, essa métrica não deve ser utilizada para avaliar a qualidade do dispositivo.  <br/> |
|**EchoPercentSend** <br/> |decimal (5; 2)  <br/> ||Porcentagem de tempo em que o eco é detectado no fluxo de envio. Alta porcentagem de eco em enviar transmite uma indicação de vazamento de eco.  <br/> |
|**RxAGCSignalLevel** <br/> |int  <br/> | <br/> |Nível de sinal recebido no servidor de mediação do gateway; Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser [-30 a-18] dBoV.  <br/> |
|**RxAGCNoiseLevel** <br/> |int  <br/> | <br/> |Nível de sinal recebido no servidor de mediação do gateway. Isso se aplica apenas ao servidor de mediação. A unidade desta métrica é dBoV. Para ter uma boa qualidade, o intervalo aceitável deve ser menor do que-50 dBoV.  <br/> |
|**RxAvgAGCGain** <br/> |int  <br/> | <br/> |Controle de ganho automático (AGC) no lado do servidor de mediação.  <br/> |
|**InitialSignalLevelRMS** <br/> |float  <br/> | <br/> |O quadrado de raiz média (RMS) do sinal de entrada de até os primeiros 30 segundos da chamada.  <br/> |
|**RecvSignalLevelCh1** <br/> |int  <br/> ||Nível de sinal como recebido no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvSignalLevelCh2** <br/> |int  <br/> ||Nível de sinal como recebido no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh1** <br/> |int  <br/> ||Nível de ruído como recebido no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RecvNoiseLevelCh2** <br/> |int  <br/> ||Nível de ruído como recebido no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh1** <br/> |int  <br/> ||Nível de sinal como enviado no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendSignalLevelCh2** <br/> |int  <br/> ||Nível de sinal como enviado no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh1** <br/> |int  <br/> ||Nível de ruído enviado no canal 1.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**SendNoiseLevelCh2** <br/> |int  <br/> ||Nível de ruído enviado no canal 2.  <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |
|**RenderLoopbackSignalLevel** <br/> |int  <br/> ||Nível em dBFS do sinal enviado ao alto-falante para reprodução. Contas para qualquer ajuste de ganho feito no sinal recebido. <br/> Esta coluna foi introduzida no Microsoft Lync Server 2013.  <br/> |   
|**RenderNoiseLevel** <br/> |int  <br/> ||Nível em dBFS do conteúdo de ruído no sinal enviado ao alto-falante para reprodução <br/> |

