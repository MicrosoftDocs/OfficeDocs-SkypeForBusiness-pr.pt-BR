---
title: -A-ponto relatório de voz e vídeo no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
description: 'Resumo: Saiba mais sobre o relatório de vídeo no Skype para Business Server e voz ponto a ponto.'
ms.openlocfilehash: 74ab2f5056c66bbd819834a573a307bd8cf82773
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33898035"
---
# <a name="peer-to-peer-voice-and-video-report-in-skype-for-business-server"></a>-A-ponto relatório de voz e vídeo no Skype para Business Server
 
**Resumo:** Saiba mais sobre o relatório de vídeo no Skype para Business Server e voz ponto a ponto.
  
O Relatório de Vídeo e Voz Ponto a Ponto oferece uma visão detalhada da distribuição de chamadas de voz e vídeo por um período específico (por exemplo, chamadas por hora ou chamadas por dia). O relatório também oferece a opção de exibir todas as chamadas de voz e vídeo realizadas ou de exibir apenas as chamadas bem-sucedidas ou com falha. Os relatórios mostram as informações das chamadas divididas nos seguintes agrupamentos:
  
- Chamadas por pool
    
- Chamadas por tipo de chamada (por exemplo, um Skype for Business para Skype para chamada de negócios versus uma Skype para chamada de negócios para uma pessoa na rede PSTN)
    
- Chamadas por tipo de acesso (os usuários conectados na rede interna versus usuários conectados na rede externa)
    
- Chamadas por servidor de mediação
    
## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Para acessar o relatório de vídeo e voz ponto a ponto

É possível acessar o Relatório de Vídeo e Voz Ponto a Ponto apenas abrindo o Relatório de Resumo de Atividades Ponto a Ponto e clicando em qualquer uma das seguintes métricas:
  
- Total de sessões de áudio ponto a ponto
    
- Total de minutos de áudio ponto a ponto
    
- Total de sessões de vídeo ponto a ponto
    
- Total de minutos de vídeo ponto a ponto
    
## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Para aproveitar melhor o relatório de vídeo e voz ponto a ponto

Existem várias formas de filtrar o Relatório de Vídeo e Voz Ponto a Ponto. No entanto, essas opções de filtragem são ocultas da exibição por padrão. Para exibir as opções de filtragem disponíveis, clique no botão **Exibir/Ocultar Parâmetros** no canto superior direito da janela Relatório.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir dados de maneiras diferentes. A tabela a seguir lista os filtros que podem ser usados com o Relatório de Vídeo e Voz Ponto a Ponto.
  
**Filtros do relatório de vídeo e voz ponto a ponto**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data e hora de início do intervalo de tempo. Para ver os dados por hora, insira a data e hora de início desta forma:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 7/7/2015 e a data de término 28/2/2015, os dados serão exibidos para os dias de 7/8/2015, meia-noite, a 7/9/2015, meia-noite, (ou seja, um total de 31 dias de dados). <br/> |
|**Tipo de mídia** <br/> | Indica o tipo de mídia usado na sessão. Selecione uma das seguintes opções: <br/>  Ambos <br/>  Áudio <br/>  Vídeo <br/> |
|**Disposição da chamada** <br/> | Indica o sucesso ou fracasso da sessão. Selecione uma das seguintes opções: <br/>  [Todos] <br/>  Chamadas com Êxito <br/>  Chamadas com Falha <br/> |
|**Relatório por** <br/> | Indica os valores a serem usados no relatório. Selecione uma das seguintes opções: <br/>  Contagem de sessões <br/>  Minutos de chamadas <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Métricas para atividade de vídeo e voz ponto a ponto por pool

A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada pool.
  
**Métricas para atividade de vídeo e voz ponto a ponto por pool**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Pool** <br/> |Não  <br/> |Nome do pool de registrador ou servidor de borda usado para a chamada.  <br/> |
|**Data/Hora** <br/> |Não  <br/> |Período de data e hora durante o qual a chamada foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Número total de sessões ou contagem total de mensagens.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Métricas da atividade de vídeo e voz ponto a ponto por tipo de chamada

A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada tipo de chamada realizada.
  
**Métricas da atividade de vídeo e voz ponto a ponto por tipo de chamada**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de chamada** <br/> |Não  <br/> | Indica o tipo de chamada realizada. Os valores são um dos seguintes: <br/>  UC-para-UC <br/>  UC-para-PSTN <br/>  PSTN-para-UC <br/>  PSTN-para-PSTN <br/> |
|**Data/Hora** <br/> |Não  <br/> |Período de data e hora durante o qual a chamada foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Número total de sessões ou contagem total de mensagens.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Métricas da atividade de vídeo e voz ponto a ponto por tipo de acesso

A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada tipo de acesso à rede.
  
**Métricas da atividade de vídeo e voz ponto a ponto por tipo de acesso**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de atividade** <br/> |Não  <br/> | Indica se os clientes estavam conectados na rede interna ou rede externa quando a chamada foi realizada. Os valores são normalmente um dos seguintes: <br/>  Interno <br/>  Externo <br/>  Misto <br/> |
|**Data/Hora** <br/> |Não  <br/> |Período de data e hora durante o qual a chamada foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Número total de sessões ou contagem total de mensagens.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Métricas para atividade de vídeo e voz ponto a ponto por servidor de mediação

A tabela a seguir lista as informações fornecidas no relatório de vídeo e voz ponto a ponto para cada servidor de mediação.
  
**Métricas para atividade de vídeo e voz ponto a ponto por servidor de mediação**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Servidor de Mediação** <br/> |Não  <br/> |Nome do servidor de mediação.  <br/> |
|**Data/Hora** <br/> |Não  <br/> |Período de data e hora durante o qual a chamada foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Número total de sessões ou contagem total de mensagens.  <br/> |
   

