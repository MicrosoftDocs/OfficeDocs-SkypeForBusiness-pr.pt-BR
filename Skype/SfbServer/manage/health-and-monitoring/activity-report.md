---
title: Relatório de atividade de conferência no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
description: 'Resumo: Saiba mais sobre o relatório de atividade de conferência usado no Skype for Business Server.'
ms.openlocfilehash: b9ea4112d144bff88ae72e5805d79f17e655d8f3
ms.sourcegitcommit: 693205da865111380b55c514955ac264031eb2fd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/02/2020
ms.locfileid: "41818172"
---
# <a name="conference-activity-report-in-skype-for-business-server"></a>Relatório de atividade de conferência no Skype for Business Server
 
**Resumo:** Saiba mais sobre o relatório de atividade de conferência usado no Skype for Business Server.
  
O relatório de atividade de conferência facilita a resposta a perguntas como estas: quantas conferências estão sendo mantidas por dia e quando as conferências são mantidas? As informações, como esta, são úteis não apenas em seu próprio direito, mas também como uma ferramenta de solução de problemas. Por exemplo, suponha que os usuários estão reclamando que a rede parece ser especialmente lenta no meio do dia. Uma rápida visão geral dos relatórios de atividade de conferência pode sugerir uma possível razão: muito mais conferências estão sendo agendadas entre as horas de 10:00 AM e 2:00 PM em qualquer outro momento.
  
Se a rede lenta está causando problemas, é possível incentivar os usuários a reagendar algumas de suas conferências durante os horários menos pesados do dia.
  
## <a name="accessing-the-conference-activity-report"></a>Acessar o relatório de atividade de conferência

O relatório de atividade de conferência é acessado do [relatório de Resumo de conferências no Skype for Business Server](conference-summary-report.md) clicando em uma das seguintes métricas:
  
- Total de conferências
    
- Total de participantes
    
## <a name="making-the-best-use-of-the-conference-activity-report"></a>Fazendo o melhor uso do relatório de atividade de conferência

Por padrão, o relatório de atividade de conferência mostra o número total de conferências para o período de tempo especificado (por exemplo, o número total de conferências por dia ou o número total de conferências por hora do dia). No entanto, você também pode optar por exibir o número total de participantes desse período de tempo ou o número total de minutos do participante. Para fazer isso, clique no botão Mostrar/ocultar parâmetros para exibir as opções de filtragem e selecione uma das seguintes opções na lista suspensa relatório por:
  
- Contagem de participantes
    
- Minutos do participante
    
- Contagem de conferência
    
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que podem ser usados com o relatório atividade de conferência.
  
**Filtros de relatório de atividade de conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 1:00 PM  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas sempre são de Domingo a Sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 1:00 PM  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione qualquer um dos seguintes: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2015 e uma data de término de 2/28/2015, os dados são exibidos para os dias 8/7/2015 12:00 AM a 9/7/2015 12:00 AM (ou seja, um total de 31 dias de dados). <br/> |
|**Relatório por** <br/> | Indica os valores a serem usados no relatório. Você pode selecionar um dos seguintes: <br/>  Contagem de participantes <br/>  Minutos do participante <br/>  Contagem de conferência <br/> |
   
## <a name="metrics-for-conferences-by-pool"></a>Métricas para conferências por pool

A tabela a seguir lista as informações no relatório de atividade de conferência para cada pool.
  
**Métricas para conferências por pool**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Pool** <br/> |Não  <br/> |Nome do pool de registradores ou servidor de borda usado na conferência.  <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e hora em que a conferência foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Contagem total de participantes, minutos totais de participantes ou contagem total de conferências.  <br/> |
   
## <a name="metrics-for-conferences-by-server-type"></a>Métricas para conferências por tipo de servidor

A tabela a seguir lista as informações no relatório de atividade de conferência para cada tipo de servidor.
  
**Métricas para conferências por tipo de servidor**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de servidor de conferência** <br/> |Não  <br/> | Tipo de servidor usado na conferência, geralmente um dos seguintes: <br/>  Servidor de Webconferência <br/>  Servidor de conferência de IM <br/>  Servidor de conferência telefônica <br/>  Servidor de conferência AV <br/>  Compartilhamento de aplicativo <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e hora em que a conferência foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Contagem total de participantes, minutos totais de participantes ou contagem total de conferências.  <br/> |
   

