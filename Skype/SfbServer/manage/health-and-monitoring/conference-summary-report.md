---
title: Relatório de resumo de conferência no Skype para Business Server
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
description: 'Resumo: Saiba mais sobre o relatório de resumo de conferência no Skype para Business Server.'
ms.openlocfilehash: c2a31665bb8c3f10bf14a936ca32dde08d3ea5aa
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "20990225"
---
# <a name="conference-summary-report-in-skype-for-business-server"></a>Relatório de resumo de conferência no Skype para Business Server
 
**Resumo:** Saiba mais sobre o relatório de resumo de conferência no Skype para Business Server.
  
O Relatório de Resumo de Conferências traz uma visão geral de suas sessões de conferência online. Normalmente, uma conferência envolve mais de 2 usuários e exige o uso de serviços de conferência. Por comparação, uma sessão ponto a ponto normalmente envolve 2 apenas usuários e não requer o uso do Skype para serviços de conferência Business Server. Atividades ponto a ponto informadas sobre o [relatório de resumo de atividade ponto a ponto no Skype para Business Server](peer-to-peer-activity-summary-report.md).
  
O relatório de resumo de conferência não apenas informa quantos conferências conduzidas durante um período de tempo determinado (cada hora, diariamente, semanalmente, mensalmente), mas também informa o número total de pessoas que participou dessas conferências e o número total de conferência exclusivas organizadores.
  
Um organizador "exclusivo" é qualquer pessoa que agenda a conferência de pelo menos um. Por exemplo, se Pilar Ackerman agendar uma conferência, ela será contabilizada como um organizador exclusivo. Se Ken Myer agendar 148 conferências, ele também será contabilizado como um único organizador exclusivo. Por exemplo, a tabela a seguir mostra oito conferências agendadas, mas apenas três organizadores exclusivos (Ken Myer, Pilar Ackerman e David Ahs).
  
|**Organizador da conferência**|**Data da conferência**|
|:-----|:-----|
|Ken Myer  <br/> |7/7/2015 10:00  <br/> |
|David Ahs  <br/> |7/7/2015 10:00  <br/> |
|Ken Myer  <br/> |7/7/2015 11:00  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 11:00  <br/> |
|Ken Myer  <br/> |7/7/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 14:00  <br/> |
|Ken Myer  <br/> |2/7/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |2/7/2015 10:00  <br/> |
   
O Relatório de Resumo de Conferências também indica quantas conferências incluíram áudio e/ou vídeo.
  
## <a name="accessing-the-conference-summary-report"></a>Acessando o Relatório de Resumo de Conferências

O Relatório de Resumo de Conferências pode ser acessado na home page Relatórios de Monitoramento. Você pode filtrar pelo Relatório de Atividade de Conferência clicando em uma das métricas a seguir:
  
- Total de conferências
    
- Total de participantes
    
## <a name="making-the-best-use-of-the-conference-summary-report"></a>Usando o Relatório de Resumo de Conferências da melhor maneira possível

Valores de total para a maioria das métricas usadas no relatório de resumo de conferência podem ser encontrados na parte inferior do relatório; Role para baixo até consulte valores, como o número total de pessoas que participaram dessas conferências e o número total de conferências conduzidas durante o período de tempo especificado. Uma métrica que não é total na parte inferior do relatório é organizadores de conferência exclusivas Total. Por que não? Aqui está um motivo. Suponha que você está vendo a importância de um mês de dados. No dia 1, você tinha 34 organizadores de conferência exclusivas; no dia 2, você tinha 27 organizadores de conferência exclusivas. Isso significa que você tinha 61 organizadores de conferência exclusivas para esses dois dias? Não necessariamente. Afinal, todas as 27 pessoas que organizou conferências no dia 2 podem ser entre as 34 pessoas que organizou conferências no dia 1. Por exemplo, nesse relatório simples, observe que Ken Myer e Pilar Ackerman agendado conferências ambas diante 7/7/2015 e em 7/2/2015:
  
|**Organizador da conferência**|**Data da conferência**|
|:-----|:-----|
|Ken Myer  <br/> |7/7/2015 10:00  <br/> |
|David Ahs  <br/> |7/7/2015 10:00  <br/> |
|Ken Myer  <br/> |7/7/2015 11:00  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 11:00  <br/> |
|Ken Myer  <br/> |7/7/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |7/7/2015 14:00  <br/> |
|Ken Myer  <br/> |2/7/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |2/7/2015 10:00  <br/> |
   
Para ter uma ideia melhor do número total de usuários exclusivos que organizaram conferências, altere o intervalo de tempo. Por exemplo, exiba os dados por mês e não por dia.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de diferentes maneiras. Por exemplo, o Relatório de Resumo de Conferências permite que você escolha como os dados devem ser agrupados. Nesse caso, conferências agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que você pode usar com o Relatório de Resumo de Conferências.
  
**Filtros do Relatório de Resumo de Conferências**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 03/07/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 03/07/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, apenas o número máximo de valores (começando pela data de início) será exibido. Por exemplo, se você selecionar o intervalo Por dia com a data de início 7/7/2015 e a data de término 28/2/2015, os dados serão exibidos para o intervalo de 7/8/2015 00:00 a 7/9/2015 00:00 (ou seja, um total de 31 dias de dados). <br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir as informações fornecidas pelo Relatório de Resumo de Conferências.
  
**Métricas do Relatório de Resumo de Conferências**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Por hora** <br/> **Por dia** <br/> **Por semana** <br/> **Por mês** <br/> |Não  <br/> |Indica o intervalo de tempo selecionado na barra de ferramentas de filtro. Quando aplicável, é possível clicar em determinado intervalo de tempo para exibir informações detalhadas sobre ele. Por exemplo, se você estiver usando o intervalo Diário e clicar em 7/7/2015, verá um detalhamento por hora da atividade de registro do usuário para a data em questão.  <br/> |
|**Total de conferências** <br/> |Não  <br/> |Número total de conferências (independentemente do tipo de conferência) que foram mantidas. Quando você clica nesse item, o relatório mostra o Relatório de Resumo de Conferências para o período de tempo selecionado.  <br/> |
|**Total de participantes** <br/> |Não  <br/> |Número total de pessoas que participaram nas conferências. Quando você clica nesse item, o relatório mostra o Relatório de Resumo de Conferências para o período de tempo selecionado.  <br/> |
|**Média de participantes por conferência** <br/> |Não  <br/> |Número médio de pessoas que participaram de uma determinada conferência. É determinado dividindo o total de conferências pelo total de participantes.  <br/> |
|**Total de conferências A/V** <br/> |Não  <br/> |Número total de conferências com áudio ou vídeo.  <br/> |
|**Total de minutos de conferências de A/V** <br/> |Não  <br/> |Número total de minutos para a conferência de áudio/vídeo.  <br/> A Total / métrica de minutos de conferência V resume todos os tipos de conferência de áudio/vídeo, incluindo: uma / conferências V; Conferências de mensagens Instantâneas; conferências; de compartilhamento de aplicativo conferências de dados; e conferências PSTN.  <br/> |
|**Total de minutos de participantes de conferências de A/V** <br/> |Não  <br/> |Número total de minutos do participante na conferência de áudio/vídeo. Por exemplo, suponha que um usuário gaste cinco minutos em uma conferência de áudio/vídeo e um segundo usuário gaste três minutos nessa mesma conferência. O que soma um total de oito minutos de participantes: cinco minutos mais três minutos.  <br/> |
|**Média de minutos da conferência A/V** <br/> |Não  <br/> |Número médio de minutos por conferência de áudio/vídeo.  <br/> |
|**Número total de organizadores exclusivos de conferências** <br/> |Não  <br/> |Número total de usuários que organizaram pelo menos uma conferência. Os usuários que organizaram mais de uma conferência são contados como um organizador exclusivo, assim como os usuários que só organizaram uma única conferência.  <br/> |
|**Total de mensagens de conferência** <br/> |Não  <br/> |Número total de mensagens instantâneas enviadas durante as conferências.  <br/> |
   

