---
title: Relatório de Atividades de Conferência no Skype for Business Server
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
ms.assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
description: 'Resumo: saiba mais sobre o Relatório de Atividade de Conferência usado no Skype for Business Server.'
ms.openlocfilehash: 74cc303fc4347b81e66d855a3ca5a71e58cb9649
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49817131"
---
# <a name="conference-activity-report-in-skype-for-business-server"></a>Relatório de Atividades de Conferência no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Atividade de Conferência usado no Skype for Business Server.
  
O Relatório de Atividades de Conferência facilita a resposta a perguntas como estas: quantas conferências estão sendo realizadas todos os dias e quando essas conferências estão sendo realizadas? Informações como essas são úteis não apenas em seu próprio direito, mas também como uma ferramenta de solução de problemas. Por exemplo, suponha que os usuários estão reclamando que a rede parece particularmente lenta no meio do dia. Uma rápida olhada nos relatórios de Atividade de Conferência pode sugerir um motivo possível: muito mais conferências estão sendo agendadas entre as 10:00 e 14:00 pm em qualquer outro momento.
  
Se a rede lenta estiver causando problemas, você poderá incentivar os usuários a reagendar algumas de suas conferências durante os horários menos intensos de tráfego do dia.
  
## <a name="accessing-the-conference-activity-report"></a>Acessando o Relatório de Atividades de Conferência

O Relatório de Atividades de Conferência é acessado a partir do Relatório de Resumo de [Conferências](conference-summary-report.md) no Skype for Business Server clicando em uma das seguintes métricas:
  
- Total de conferências
    
- Total de participantes
    
## <a name="making-the-best-use-of-the-conference-activity-report"></a>Fazendo o melhor uso do Relatório de Atividades de Conferência

Por padrão, o Relatório de Atividade de Conferência mostra o número total de conferências para o período de tempo especificado (por exemplo, o número total de conferências por dia ou o número total de conferências por hora do dia). No entanto, você também pode optar por exibir o número total de participantes para esse período de tempo ou o número total de minutos do participante. Para fazer isso, clique no botão Mostrar/Ocultar Parâmetros para exibir as opções de filtragem e, em seguida, selecione um dos seguintes na lista suspenso Relatório por:
  
- Contagem de participantes
    
- Minutos dos participantes
    
- Contagem de conferências
    
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que você pode usar com o Relatório de Atividades de Conferência.
  
**Filtros do Relatório de Atividades de Conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione um dos seguintes: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/8/2015 12:00 a 7/9/2015 00:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Relatório por** <br/> | Indica os valores a serem usados no relatório. Você pode selecionar um dos seguintes: <br/>  Contagem de participantes <br/>  Minutos do participante <br/>  Contagem de conferências <br/> |
   
## <a name="metrics-for-conferences-by-pool"></a>Métricas para conferências por pool

A tabela a seguir lista as informações do Relatório de Atividade de Conferência para cada pool.
  
**Métricas para conferências por pool**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Pool** <br/> |Não  <br/> |Nome do pool do Registrador ou Servidor de Borda usado na conferência.  <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e hora em que a conferência foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Contagem total de participantes, minutos totais do participante ou contagem total de conferências.  <br/> |
   
## <a name="metrics-for-conferences-by-server-type"></a>Métricas para conferências por tipo de servidor

A tabela a seguir lista as informações do Relatório de Atividade de Conferência para cada tipo de servidor.
  
**Métricas para conferências por tipo de servidor**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de servidor de conferência** <br/> |Não  <br/> | Tipo de servidor usado na conferência, normalmente um dos seguintes: <br/>  Servidor de Webconferência <br/>  Servidor de Conferência de IM <br/>  Servidor de Conferência de Telefonia <br/>  Servidor de Conferência AV <br/>  Compartilhamento de aplicativo <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e hora em que a conferência foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Contagem total de participantes, minutos totais do participante ou contagem total de conferências.  <br/> |
   

