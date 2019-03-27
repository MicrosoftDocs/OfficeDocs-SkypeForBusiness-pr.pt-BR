---
title: Relatório de tempo de ingresso conferência no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
description: 'Resumo: Saiba mais sobre o conferência Join tempo relatório de resumo no Skype para Business Server.'
ms.openlocfilehash: 8264ac8df7a6299484c88121ac1352401833ebe9
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30874204"
---
# <a name="conference-join-time-report-in-skype-for-business-server"></a>Relatório de tempo de ingresso conferência no Skype para Business Server
 
**Resumo:** Saiba mais sobre o conferência Join tempo relatório de resumo no Skype para Business Server.
  
O Resumo do Tempo de Ingresso em Conferência permite que você determine quanto tempo demora para que seus usuários ingressarem em uma conferência. O relatório mostra o tempo médio de ingresso (em milissegundos) e também oferece um detalhamento que permite que você saiba quantos usuários foram capazes de se juntar a uma conferência em 2 segundos ou menos, quantos usuários necessitaram de 2 a 5 segundos para ingressar em uma conferência, etc.
  
## <a name="accessing-the-conference-join-time-report"></a>Acessando o Relatório do Tempo de Ingresso em Conferência

O Relatório do Tempo de Ingresso em Conferência é acessado pela página inicial dos Relatórios de Monitoramento.
  
## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais direcionado ou exibir os dados devolvidos em formas diferentes. A tabela a seguir lista os filtros que você pode usar com os Relatórios do Tempo de Ingresso em Conferência.
  
**Filtros de Relatório do Tempo de Ingresso em Conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 7/7/2015 e a data de término 28/2/2015, os dados serão exibidos para os dias de 7/8/2015 12:00 a 7/9/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Pool** <br/> |FQDN (Nome de domínio totalmente qualificado) do pool de Registradores Avançados ou Servidores de Borda. Você pode selecionar um pool individual ou clicar em **[Tudo]** para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.<br/> |
|**Sessões de conferência** <br/> | Tipo de sessão. Os valores permitidos são: <br/>  [Todos] <br/>  Sessões de Focus (Focus é o gerenciador central de políticas e estados para reuniões online e coordena todos os aspectos da conferência <br/>  Compartilhamento de aplicativos <br/>  Conferências de áudio/vídeo <br/>  Caso selecione [Todos], o tempo total de ingresso em conferência será exibido no topo do relatório. Observe que esses totais são apenas para conferências que foram agendadas usando o Microsoft Exchange ou o Microsoft Outlook. <br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Tempo de Ingresso em Conferência.
  
**Métricas do Relatório de Tempo de Ingresso em Conferência**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Data** <br/> O título para essa métrica varia dependendo do Intervalo selecionado.  <br/> |Não  <br/> |Data e horário em que aconteceu a conferência.  <br/> |
|**Total de sessões** <br/> |Não  <br/> |Número total de sessões, incluindo sessões bem-sucedidas, com falha (tanto falhas esperadas quanto inesperadas) e sessões não categorizadas.  <br/> |
|**Média (ms)** <br/> |Não  <br/> |Média de tempo (em milissegundos) que demorou para que os participantes ingressassem na conferência.  <br/> |
|**Sessões \< 2 segundos, Volume** <br/> |Não  <br/> |Número de participantes que conseguiram ingressar na conferência em menos de 2 segundos.  <br/> |
|**Sessões \< 2 segundos, porcentagem** <br/> |Não  <br/> ||
|**Sessões de 2 a 5 segundos, Volume** <br/> |Não  <br/> |Número de participantes que demoraram de 2 a 5 segundos para ingressar na conferência.  <br/> |
|**Sessões de 2 a 5 segundos, Porcentagem** <br/> |Não  <br/> |Porcentagem do total de participantes da chamada que demoraram entre 2 a 5 segundos para ingressar na conferência.  <br/> |
|**Sessões de 5 a 10 segundos, Volume** <br/> |Não  <br/> |Número de participantes que demoraram entre 5 a 10 segundos para ingressar na conferência.  <br/> |
|**Sessões de 5 a 10 segundos, Porcentagem** <br/> |Não  <br/> |Porcentagem do total de participantes de chamadas que demoraram entre 5 a 10 segundos para ingressar na conferência.  <br/> |
|**Sessões \> 10 segundos, Volume** <br/> |Não  <br/> |Número de participantes que precisaram de mais de 10 segundos para ingressar na conferência.  <br/> |
|**Sessões \> 10 segundos, porcentagem** <br/> |Não  <br/> |Porcentagem do total de participantes de chamadas que precisaram de mais de 10 segundos para ingressar na conferência.  <br/> |
   

