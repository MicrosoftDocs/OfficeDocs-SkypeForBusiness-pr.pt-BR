---
title: Relatório de atividade de conferências no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 22ddb509-af16-4fc8-9b98-6f58caa6f37e
description: 'Resumo: Saiba mais sobre o relatório atividade de conferência usado no Skype for Business Server.'
ms.openlocfilehash: 790a9d5076a371dda7c8862a74f253fdb8508296
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34303874"
---
# <a name="conference-activity-report-in-skype-for-business-server"></a>Relatório de atividade de conferências no Skype for Business Server
 
**Resumo:** Saiba mais sobre o relatório atividade de conferência usado no Skype for Business Server.
  
O Relatório de Atividade de Conferência torna fácil responder perguntas como estas: quantas conferências estão sendo realizadas diariamente e quando estas conferências são realizadas? Informações como estas são úteis não apenas em seu próprio direito, mas também como uma ferramenta de resolução de problemas. Por exemplo, vamos supor que os usuários estão reclamando que a rede parece particularmente lenta no meio do dia. Uma rápida descrição dos relatórios de atividade de conferência pode sugerir um possível motivo: muito mais conferências estão sendo agendadas entre as horas de 10:00 AM e 2:00 PM em qualquer momento.
  
Se a rede lenta está causando problemas, é possível incentivar os usuários a reprogramar algumas de suas conferências durante horários com menos tráfego durante o dia.
  
## <a name="accessing-the-conference-activity-report"></a>Acessando o Relatório de Atividade da Conferência

O relatório atividade de conferência é acessado do [relatório de Resumo de conferências no Skype for Business Server](conference-summary-report.md) clicando em uma das seguintes métricas:
  
- Total de conferências
    
- Total de participantes
    
## <a name="making-the-best-use-of-the-conference-activity-report"></a>Fazendo o melhor uso do Relatório de Atividade de Conferência

Por padrão, o Relatório de Atividade de Conferência mostra o número total de conferências para um determinado período de tempo (por exemplo, o número total de conferências por dia ou o número total de conferências por hora do dia). No entanto, é possível escolher exibir o número total de participantes neste período de tempo ou o número total de participantes em minutos. Para fazer isso, clique no botão Exibir/Ocultar parâmetros para exibir as opções de filtragem e selecione um dos seguintes na lista suspensa Relatar por:
  
- Contagem de participantes
    
- Minutos dos participantes
    
- Contagem de conferência
    
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que você pode usar com o Relatório de Atividades de Conferência.
  
**Filtros de relatório de atividade de conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione qualquer um dos seguintes: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 7/7/2012 e a data de término 28/2/2011, os dados serão exibidos para os dias de 7/8/2012 00:00 a 7/9/2012 00:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Relatar por** <br/> | Indica os valores a serem usados no relatório. Você pode selecionar um dos seguintes: <br/>  Contagem de participantes <br/>  Minutos dos participantes <br/>  Contagem de conferência <br/> |
   
## <a name="metrics-for-conferences-by-pool"></a>Métricas para conferências por pool

A tabela a seguir lista as informações no Relatório de Atividade de Conferência para cada pool.
  
**Métricas para conferências por pool**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Pool** <br/> |Não  <br/> |Nome do pool do Registrador ou Servidor de Borda usado na conferência.  <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e hora de quando a conferência foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Contagem total de participantes, minutos totais de participantes ou contagem total da conferência.  <br/> |
   
## <a name="metrics-for-conferences-by-server-type"></a>Métricas para conferência por tipo de servidor

A tabela a seguir lista as informações no relatório de atividade de conferência para cada tipo de servidor.
  
**Métricas para conferência por tipo de servidor**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Tipo de servidor de conferência** <br/> |Não  <br/> | Tipo de servidor usado na conferência, geralmente um dos seguintes: <br/>  Servidor de conferência da Web <br/>  Servidor de conferência de IM <br/>  Servidor de conferência com telefonia <br/>  Servidor de conferência de AV <br/>  Compartilhamento de Aplicativos <br/> |
|**Data/Hora** <br/> |Não  <br/> |Data e hora de quando a conferência foi realizada.  <br/> |
|**Total** <br/> |Não  <br/> |Contagem total de participantes, minutos totais de participantes ou contagem total da conferência.  <br/> |
   

