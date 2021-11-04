---
title: Relatório de Atividades de Conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
description: 'Resumo: saiba mais sobre o Relatório de Atividade de Conferência usado Skype for Business Server.'
ms.openlocfilehash: fcbe28d031abc7803cd8b84a67c3baeef42eff08
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60774941"
---
# <a name="conference-activity-report-in-skype-for-business-server"></a>Relatório de Atividades de Conferência no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Atividades de Conferência usado Skype for Business Server.
  
O Relatório de Atividades de Conferência facilita a resposta a perguntas como estas: quantas conferências estão sendo realizadas por dia e quando essas conferências estão sendo realizadas? Informações como essa são úteis não apenas em seu próprio direito, mas também como uma ferramenta de solução de problemas. Por exemplo, suponha que os usuários estão reclamando que a rede parece particularmente lenta no meio do dia. Uma rápida olhada nos relatórios de Atividade de Conferência pode sugerir um motivo possível: muito mais conferências estão sendo agendadas entre 10:00 e 14:00, em seguida, a qualquer outro momento.
  
Se a rede lenta estiver causando problemas, você poderá incentivar os usuários a reagendar algumas de suas conferências durante os horários menos congestionados do dia.
  
## <a name="accessing-the-conference-activity-report"></a>Acessando o Relatório de Atividades de Conferência

O Relatório de Atividades de Conferência é acessado a partir do Relatório de Resumo de Conferência em [Skype for Business Server](conference-summary-report.md) clicando em uma das seguintes métricas:
  
- Total de conferências
    
- Total de participantes
    
## <a name="making-the-best-use-of-the-conference-activity-report"></a>Fazendo o melhor uso do Relatório de Atividades de Conferência

Por padrão, o Relatório de Atividades de Conferência mostra o número total de conferências para o período especificado (por exemplo, o número total de conferências por dia ou o número total de conferências por hora do dia). No entanto, você também pode optar por exibir o número total de participantes para esse período ou o número total de minutos do participante. Para fazer isso, clique no botão Mostrar/Ocultar Parâmetros para exibir as opções de filtragem e selecione uma das opções a seguir na lista lista suspenso Relatório por:
  
- Contagem de participantes
    
- Minutos do participante
    
- Contagem de conferências
    
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que você pode usar com o Relatório de Atividades de Conferência.
  
**Filtros do Relatório de Atividades de Conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione um dos seguintes: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/08/2015 12:00 a 7/09/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Relatório por** <br/> | Indica os valores a serem usados no relatório. Você pode selecionar um dos seguintes: <br/>  Contagem de participantes <br/>  Minutos do participante <br/>  Contagem de conferências <br/> |
   
## <a name="metrics-for-conferences-by-pool"></a>Métricas para Conferências por Pool

A tabela a seguir lista as informações no Relatório de Atividades de Conferência para cada pool.
  
**Métricas para Conferências por Pool**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Pool** <br/> |Não  <br/> |Nome do pool de Registradores ou Servidor de Borda usado na conferência.  <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e hora em que a conferência foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Contagem total de participantes, minutos totais do participante ou contagem total de conferências.  <br/> |
   
## <a name="metrics-for-conferences-by-server-type"></a>Métricas para conferências por tipo de servidor

A tabela a seguir lista as informações no Relatório de Atividades de Conferência para cada tipo de servidor.
  
**Métricas para conferências por tipo de servidor**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de servidor de conferência** <br/> |Não  <br/> | Tipo de servidor usado na conferência, normalmente um dos seguintes: <br/>  Servidor de WebConferência <br/>  Servidor de Conferência de IM <br/>  Servidor de Conferência de Telefonia <br/>  Servidor de Conferência AV <br/>  Compartilhamento de aplicativo <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e hora em que a conferência foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Contagem total de participantes, minutos totais do participante ou contagem total de conferências.  <br/> |
   

