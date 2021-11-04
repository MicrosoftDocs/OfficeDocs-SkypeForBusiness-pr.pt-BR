---
title: Relatório de Tempo de Junção de Conferência Skype for Business Server
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
ms.assetid: e64dc89a-25e4-4cb8-bcb1-51712e69ba5a
description: 'Resumo: saiba mais sobre o Relatório de Resumo do Tempo de Junção de Conferência Skype for Business Server.'
ms.openlocfilehash: b1208802aa82bfe93951919403882477aa608889
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/04/2021
ms.locfileid: "60740517"
---
# <a name="conference-join-time-report-in-skype-for-business-server"></a>Relatório de Tempo de Junção de Conferência Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Resumo do Tempo de Junção de Conferência Skype for Business Server.
  
O Sumário de Tempo de Ingresso em Conferência permite que você determine quanto tempo demora para que seus usuários ingressem em uma conferência. Um relatório mostra o tempo médio de ingresso (em milissegundos), e também oferece um detalhamento que permite que você saiba quantos usuários foram capazes de se juntar a uma conferência em 2 segundos ou menos, quantos usuários necessitaram de 2 a 5 segundos para ingressar em uma conferência, etc.
  
## <a name="accessing-the-conference-join-time-report"></a>Acessando o Relatório de Tempo de Ingresso em Conferência

O Relatório de Tempo de Ingresso em Conferência é acessado através da página inicial dos Relatórios de Monitoramento.
  
## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais direcionado ou exibir os dados devolvidos em formas diferentes. A tabela a seguir lista os filtros que você pode usar com o Relatórios de Tempo de Ingresso em Conferência.
  
**Filtros de Relatório de Tempo de Ingresso em Conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/08/2015 12:00 a 7/09/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Pool** <br/> |FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Tudo]** para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.<br/> |
|**Sessões de conferência** <br/> | Tipo de sessão. Os valores permitidos são: <br/>  [Todos] <br/>  Sessões de foco (o Foco é a política central e o gerente de estado para reuniões online e coordena todos os aspectos de uma conferência <br/>  Compartilhamento de aplicativos <br/>  Conferências A/V <br/>  Caso selecione [Todos], o tempo total de ingresso em conferência será exibido no topo do relatório. Observe que estes totais são apenas para conferências que foram agendadas usando o Microsoft Exchange ou o Microsoft Outlook. <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Tempo de Ingresso em Conferência.
  
**Métricas do Relatório de Tempo de Ingresso em Conferência**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Date** <br/> O título para essa métrica irá variar dependendo do Intervalo selecionado.  <br/> |Não  <br/> |Data e horário em que aconteceu a conferência.  <br/> |
|**Total de sessões** <br/> |Não  <br/> |Número total de sessões, incluindo sessões bem-sucedidas, com falha (tanto falhas esperadas quanto inesperadas) e sessões não categorizadas.  <br/> |
|**Média (ms)** <br/> |Não  <br/> |Média de tempo (em milissegundos) que demorou para que os participantes ingressassem na conferência.  <br/> |
|**Sessões \< 2 seconds, Volume** <br/> |Não  <br/> |Número de participantes que conseguiram ingressar na conferência em menos de 2 segundos.  <br/> |
|**Sessões \< 2 seconds, Percentage** <br/> |Não  <br/> ||
|**Sessões de 2 a 5 segundos, Volume** <br/> |Não  <br/> |Número de participantes que demoraram de 2 a 5 segundos para ingressar na conferência.  <br/> |
|**Sessões de 2 a 5 segundos, Porcentagem** <br/> |Não  <br/> |Porcentagem do total de participantes da chamada demoraram entre 2 a 5 segundos para ingressar na conferência.  <br/> |
|**Sessões de 5 a 10 segundos, Volume** <br/> |Não  <br/> |Número de participantes que demoraram entre 5 a 10 segundos para ingressar na conferência.  <br/> |
|**Sessões de 5 a 10 segundos, Porcentagem** <br/> |Não  <br/> |Porcentagem do total de participantes de chamadas que demoraram entre 5 a 10 segundos para ingressar na conferência.  <br/> |
|**Sessões \> 10 segundos, Volume** <br/> |Não  <br/> |Número de participantes que precisaram de mais de 10 segundos para ingressar na conferência.  <br/> |
|**Sessões \> de 10 segundos, Porcentagem** <br/> |Não  <br/> |Porcentagem do total de participantes de chamadas que precisaram de mais de 10 segundos para ingressar na conferência.  <br/> |
   

