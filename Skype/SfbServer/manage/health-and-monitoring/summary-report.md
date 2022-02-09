---
title: Relatório de Resumo de Diagnóstico de Chamada Skype for Business Server
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 9091de56-13e6-440e-9353-f57c10c906fe
description: 'Resumo: saiba mais sobre o Relatório de Resumo de Diagnóstico de Chamada usado em Skype for Business Server.'
ms.openlocfilehash: 76907a319f5e4d828829daf7bc0564a964eb7633
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62397695"
---
# <a name="call-diagnostic-summary-report-in-skype-for-business-server"></a>Relatório de Resumo de Diagnóstico de Chamada Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Resumo de Diagnóstico de Chamada usado Skype for Business Server.
  
O Relatório de Resumo de Diagnóstico de Chamadas fornece uma visão geral de sessões peer-to-peer e de conferências que falharam. O relatório mostra a taxa de falha geral para os dois tipos de sessão, e detalha as informações de falha por tipo de modalidade de sessão:
  
- Mensagens instantâneas
    
- Compartilhamento de aplicativos
    
- Transferência de arquivo
    
- Áudio
    
- Vídeo
    
## <a name="accessing-the-call-diagnostic-summary-report"></a>Como acessar o Relatório de resumo de diagnóstico de chamadas

O Relatório de resumo de diagnóstico de chamadas é acessado a partir da página inicial dos Relatórios de Monitoramento. No Relatório de Resumo de Diagnóstico de Chamada, você pode acessar o Relatório de Diagnóstico de Atividade Ponto a Ponto no Skype for Business Server clicando na métrica Taxa de Falha na seção Resumo de Sessão Ponto [a](peer-to-peer-activity-diagnostic-report.md) Ponto do relatório. Você também pode acessar o [Relatório](conference-diagnostic-report.md) de Diagnóstico de Conferência Skype for Business Server clicando em qualquer uma das seguintes métricas de conferência:
  
- Taxa de falha de sessão geral
    
- Taxa de falha de foco
    
- Taxa de falha de MCU
    
## <a name="making-the-best-use-of-the-call-diagnostic-summary-report"></a>Como usar melhor o Relatório de resumo de diagnóstico de chamadas

O Relatório de Resumo de Diagnóstico de Chamada inclui gráficos que comparam taxas de falha para as várias modalidades usadas no Skype for Business Server. As colunas nesses gráficos são, na verdade, hotlinks; por exemplo, se você clicar na coluna Mensagens Instantâneas para sessões ponto a ponto, você irá detalhar até uma instância do Relatório de Diagnóstico de Atividade Ponto a Ponto no [Skype for Business Server](peer-to-peer-activity-diagnostic-report.md), um relatório que fornece detalhes adicionais sobre todas as sessões de mensagens instantâneas incluídas no Relatório de Resumo de Diagnóstico de Chamada.
  
## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Diagnóstico de Chamadas permite filtrar por informações como pool do Registrador Avançado ou Servidor de Borda usado na sessão. Você também pode escolher como os dados serão agrupados. Neste caso, as chamadas são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Diagnóstico de Chamadas.
  
**Filtros do Relatório de Resumo de Diagnóstico de Chamadas**

|**Name**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/08/2015 12:00 a 7/09/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Pool** <br/> |Nome de domínio totalmente qualificado (FQDN) do pool do Registrador Avançado ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Todos]** para exibir dados para todos os pools. Esta lista suspensa é preenchida automaticamente, com base nos registros do banco de dados.<br/> |
   
## <a name="metrics-for-peer-to-peer-sessions"></a>Métricas para Sessões Ponto a Ponto

A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Diagnóstico de Chamadas para sessões ponto a ponto (ou seja, sessões envolvendo somente dois participantes).
  
**Métricas para Sessões Ponto a Ponto**

|**Name**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Total de sessões** <br/> |Não  <br/> |Número total de sessões ponto a ponto conduzidas.  <br/> |
|**Taxa de falha** <br/> |Não  <br/> |Percentual de sessões ponto a ponto que falharam. Ao clicar neste item, o relatório exibe o relatório de Diagnóstico de Atividades Ponto a Ponto, que mostra informações mais detalhadas sobre as sessões ponto a ponto com falha.  <br/> |
   
## <a name="metrics-for-conferencing-sessions"></a>Métricas para Sessões de Conferência

A tabela a seguir lista as informações fornecidas pelo Relatório de Diagnóstico de Chamadas para sessões de conferência (ou seja, sessões envolvendo três ou mais participantes).
  
**Métricas para Sessões de Conferência**

|**Name**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Total de conferências** <br/> |Não  <br/> |Número total de conferências conduzidas.  <br/> |
|**Sessões de conferência totais** <br/> |Não  <br/> |Número total de sessões de conferência conduzidas.  <br/> |
|**Taxa de falha de sessão geral** <br/> |Não  <br/> |Percentual de sessões de conferência totais que falharam.  <br/> |
|**Sessões de Foco** <br/> |Não  <br/> |Número total de sessões de conferência baseadas em Foco que falharam.  <br/> |
|**Taxa de falha de Foco** <br/> |Não  <br/> |Percentual de sessões de conferência baseadas em Foco que falharam.  <br/> |
|**Sessões MCU** <br/> |Não  <br/> |Número total de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.  <br/> |
|**Taxa de falha de MCU** <br/> |Não  <br/> |Percentual de conferências baseadas em servidor (anteriormente conhecidas como Unidade de Controle de Multipontos ou MCU) que falharam.  <br/> |
   

