---
title: Relatório de Vídeo e Voz Ponto a Ponto no Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e17c36b5-5a2f-4673-9696-3b2d31c2bb2f
description: 'Resumo: saiba mais sobre o Relatório de Vídeo e Voz Ponto a Ponto no Skype for Business Server.'
ms.openlocfilehash: 7e07c5778f43c3a0cac4ff162ed3d7dd1108eb43
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816611"
---
# <a name="peer-to-peer-voice-and-video-report-in-skype-for-business-server"></a>Relatório de Vídeo e Voz Ponto a Ponto no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Vídeo e Voz Ponto a Ponto no Skype for Business Server.
  
O Relatório de Vídeo e Voz Ponto a Ponto fornece uma análise detalhada da distribuição de chamadas de voz e vídeo durante um período de tempo especificado (por exemplo, chamadas por hora ou chamadas por dia). O relatório também oferece a opção de exibir todas as chamadas de voz e vídeo que foram feitas ou de exibir apenas as chamadas bem-sucedidas ou com falha. Os relatórios mostram informações de chamada divididas nos seguintes grupos:
  
- Chamadas por pool
    
- Chamadas por tipo de chamada (por exemplo, uma chamada do Skype for Business para o Skype for Business versus uma chamada do Skype for Business para uma pessoa na rede PSTN)
    
- Chamadas por tipo de acesso (usuários conectados à rede interna vs. usuários conectados à rede externa)
    
- Chamadas por Servidor de Mediação
    
## <a name="to-access-the-peer-to-peer-voice-and-video-report"></a>Para acessar o relatório de vídeo e voz ponto a ponto

Você pode acessar o Relatório de Vídeo e Voz Ponto a Ponto apenas abrindo o Relatório de Resumo de Atividades Ponto a Ponto e clicando em qualquer uma das seguintes métricas:
  
- Total de sessões de áudio ponto a ponto
    
- Total de minutos de áudio ponto a ponto
    
- Total de sessões de vídeo ponto a ponto
    
- Total de minutos de vídeo ponto a ponto
    
## <a name="to-make-the-best-use-of-the-peer-to-peer-voice-and-video-report"></a>Para fazer o melhor uso do relatório de vídeo e voz ponto a ponto

Há várias maneiras de filtrar o Relatório de Vídeo e Voz Ponto a Ponto. No entanto, essas opções de filtragem ficam ocultas da exibição por padrão. Para exibir as opções de filtragem disponíveis, clique no botão **Mostrar/Ocultar Parâmetros** no canto superior direito da janela Relatório.
  
## <a name="filters"></a>Filtros

Filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou exibir os dados de maneiras diferentes. A tabela a seguir lista os filtros que você pode usar com o Relatório de Vídeo e Voz Ponto a Ponto.
  
**Filtros de relatório de vídeo e voz ponto a ponto**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data e hora de início para o intervalo de tempo. Para exibir os dados por horas, digite a data e a hora de início da seguinte maneira:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/8/2015 12:00 a 7/9/2015 00:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Tipo de mídia** <br/> | Indica o tipo de mídia usada na sessão. Selecione uma destas opções: <br/>  Ambos <br/>  Áudio <br/>  Vídeo <br/> |
|**Disposição da chamada** <br/> | Indica o sucesso ou falha da sessão. Selecione uma das seguintes opções: <br/>  [Tudo] <br/>  Chamadas de Sucesso <br/>  Chamadas com Falha <br/> |
|**Relatório por** <br/> | Indica os valores a serem usados no relatório. Selecione um dos seguintes valores: <br/>  Contagem de sessão <br/>  Minutos de chamada <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-pool"></a>Métricas para atividade de vídeo e voz ponto a ponto por pool

A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada pool.
  
**Métricas para atividade de vídeo e voz ponto a ponto por pool**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Pool** <br/> |Não  <br/> |Nome do pool do Registrador ou Servidor de Borda usado para a chamada.  <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e período de tempo em que a chamada ocorreu.  <br/> |
|**Total** <br/> |Não  <br/> |Número total de sessões ou de contagem total de mensagens.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-call-type"></a>Métricas para atividade de vídeo e voz ponto a ponto por tipo de chamada

A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada tipo de chamada realizada.
  
**Métricas para atividade de vídeo e voz ponto a ponto por tipo de chamada**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de chamada** <br/> |Não  <br/> | Indica o tipo de chamada realizada. Os valores são um dos seguintes: <br/>  UC-para-UC <br/>  UC-para-PSTN <br/>  PSTN-para-UC <br/>  PSTN para PSTN <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e período de tempo em que a chamada ocorreu.  <br/> |
|**Total** <br/> |Não  <br/> |Número total de sessões ou de contagem total de mensagens.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-access-type"></a>Métricas para atividade de vídeo e voz ponto a ponto por tipo de acesso

A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada tipo de acesso à rede.
  
**Métricas para atividade de vídeo e voz ponto a ponto por tipo de acesso**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de atividade** <br/> |Não  <br/> | Indica se os clientes estavam conectados à rede interna ou à rede externa quando a chamada foi realizada. Normalmente, os valores são um dos seguintes: <br/>  Interno <br/>  Externo <br/>  Mistos <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e período de tempo em que a chamada ocorreu.  <br/> |
|**Total** <br/> |Não  <br/> |Número total de sessões ou de contagem total de mensagens.  <br/> |
   
## <a name="metrics-for-peer-to-peer-voice-and-video-activity-by-mediation-server"></a>Métricas para atividade de vídeo e voz ponto a ponto pelo servidor de mediação

A tabela a seguir lista as informações fornecidas no Relatório de Vídeo e Voz Ponto a Ponto para cada Servidor de Mediação.
  
**Métricas para atividade de vídeo e voz ponto a ponto pelo servidor de mediação**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Servidor de mediação** <br/> |Não  <br/> |Nome do Servidor de Mediação.  <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e período de tempo em que a chamada ocorreu.  <br/> |
|**Total** <br/> |Não  <br/> |Número total de sessões ou de contagem total de mensagens.  <br/> |
   

