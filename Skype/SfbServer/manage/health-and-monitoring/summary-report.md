---
title: Relatório de resumo do diagnóstico de chamadas no Skype for Business Server
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
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 'Resumo: Saiba mais sobre o relatório de resumo do diagnóstico de chamadas usado no Skype for Business Server.'
ms.openlocfilehash: 00925ca15ca053fc85ee5719c8154a92cfb35fb4
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817660"
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server"></a>Relatório de resumo do diagnóstico de chamadas no Skype for Business Server
 
**Resumo:** Saiba mais sobre o relatório de Resumo de diagnóstico de chamadas usado no Skype for Business Server.
  
O Relatório de Resumo de Diagnóstico de Chamadas fornece uma visão geral de sessões peer-to-peer e de conferências que falharam. O relatório mostra a taxa de falha geral para os dois tipos de sessão, e detalha as informações de falha por tipo de modalidade de sessão:
  
- Mensagens instantâneas
    
- Compartilhamento de aplicativos
    
- Transferência de arquivos
    
- Áudio
    
- Vídeo
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>Como acessar o Relatório de resumo de diagnóstico de chamadas

O Relatório de resumo de diagnóstico de chamadas é acessado na página inicial dos Relatórios de Monitoramento. No relatório de resumo do diagnóstico de chamadas, você pode acessar o [relatório de diagnóstico de atividades ponto a ponto no Skype for Business Server](peer-to-peer-activity-diagnostic-report.md) clicando na métrica de Tarifa de falha na seção de Resumo de sessão ponto a ponto do relatório. Você também pode acessar o [relatório de diagnóstico de conferência no Skype for Business Server](conference-diagnostic-report.md) clicando em qualquer uma das seguintes métricas de conferência:
  
- Taxa de falha de sessão geral
    
- Taxa de falha de foco
    
- Taxa de falha de MCU
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Como usar melhor o Relatório de resumo de diagnóstico de chamadas

O relatório de resumo do diagnóstico de chamadas inclui gráficos que comparam as tarifas de falha para as diversas modalidades usadas no Skype for Business Server. As colunas nestes gráficos são na verdade hotlinks; por exemplo, se você clicar na coluna mensagens instantâneas para sessões ponto a ponto, fará Drill down até uma instância do [relatório de diagnóstico de atividade ponto a ponto no Skype for Business Server](peer-to-peer-activity-diagnostic-report.md), um relatório que fornece mais detalhes sobre todas as sessões de mensagens instantâneas incluídas no relatório de resumo do diagnóstico de chamadas.
  
## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Diagnóstico de Chamadas permite filtrar por informações como pool do Registrador Avançado ou Servidor de Borda usado na sessão. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Diagnóstico de Chamadas.
  
**Filtros do Relatório de Resumo de Diagnóstico de Chamadas**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 7/7/2015 e a data de término 28/2/2015, os dados serão exibidos para os dias de 7/8/2015 12:00 a 7/9/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Pool** <br/> |FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Tudo]** para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.<br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para sessões ponto a ponto

A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Diagnóstico de Chamadas para sessões ponto a ponto (ou seja, sessões envolvendo somente dois participantes).
  
**Métricas para sessões ponto a ponto**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Total de sessões** <br/> |Não  <br/> |Número total de sessões ponto a ponto conduzidas.  <br/> |
|**Taxa de falha** <br/> |Não  <br/> |Percentual de sessões ponto a ponto que falharam. Ao clicar neste item, o relatório exibe o relatório de Diagnóstico de Atividades Ponto a Ponto, que mostra informações mais detalhadas sobre as sessões ponto a ponto com falha.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Métricas para sessões de conferência

A tabela a seguir lista as informações fornecidas pelo Relatório de Diagnóstico de Chamadas para sessões de conferência (ou seja, sessões envolvendo três ou mais participantes).
  
**Métricas para sessões de conferência**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Conferências totais** <br/> |Não  <br/> |Número total de conferências conduzidas.  <br/> |
|**Sessões de conferência totais** <br/> |Não  <br/> |Número total de sessões de conferência conduzidas.  <br/> |
|**Taxa de falha de sessão geral** <br/> |Não  <br/> |Percentual de sessões de conferência totais que falharam.  <br/> |
|**Sessões de foco** <br/> |Não  <br/> |Número total de sessões de conferência baseadas em Foco que falharam.  <br/> |
|**Taxa de falha de foco** <br/> |Não  <br/> |Percentual de sessões de conferência baseadas em Foco que falharam.  <br/> |
|**Sessões MCU** <br/> |Não  <br/> |Número total de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.  <br/> |
|**Taxa de falha de MCU** <br/> |Não  <br/> |Percentual de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.  <br/> |
   

