---
title: Relatório de Resumo de Conferência de PSTN no Skype for Business Server 2015
ms.author: jambirk
author: jambirk
manager: serdars
ms.date: 3/28/2016
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Resumo: Saiba mais sobre o PSTN conferência relatório de resumo no Skype para Business Server 2015.'
ms.openlocfilehash: 1897b6ebf25e4de4f60af91d76ada539ea3561f9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server-2015"></a>Relatório de Resumo de Conferência de PSTN no Skype for Business Server 2015
 
**Resumo:** Saiba mais sobre o PSTN conferência relatório de resumo no Skype para Business Server 2015.
  
Skype para Business Server 2015, uma conferência PSTN é qualquer conferência na qual pelo menos um participante disca para a parte de áudio usando um um telefone PSTN (rede telefônica pública comutada). (Um telefone PSTN é uma "linha de fixa", um telefone celular ou outro telefone que não faz uso de voz sobre IP.) Embora conhecido como conferências PSTN nos relatórios de monitoramento, essas conferências talvez são mais comumente conhecidas como conferências discadas.
  
O Relatório de resumo de conferência fornece informações sobre todas as conferências PSTN feitas em sua organização (isto é, todas as conferências que tenham pelo menos um usuário discado). O relatório contém informações sobre o número total de conferências PSTN, total de número de pessoas que participaram nessas conferências e, talvez, o mais importante, o número total de usuários discados (a métrica de Total de participantes PSTN).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Como acessar o Relatório de resumo de conferência PSTN

O Relatório de resumo de conferência PSTN pode ser acessado apenas da página inicial dos Relatórios de Monitoramento. Este relatório não está vinculado a nenhum outro. Observe que você não pode recuperar informações de chamadas detalhadas para uma conferência PSTN, em parte porque os pontos de extremidade individuais são responsáveis por enviar essas informações. Os telefones PSTN não são capazes de rastrear ou enviar informações de detalhes de chamada.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Como usar melhor o Relatório de resumo de conferência PSTN

Para determinar a porcentagem de todas as conferências que incluem usuários discados, compare o valor da métrica de conferências da PSTN Total com a métrica de Total de conferências, encontrada no [Conference Summary Report no Skype para Business Server 2015](conference-summary-report.md).
  
Se você não vir o número de conferências PSTN que esperava ver, saiba que a capacidade de organizar uma conferência que permita usuários discados depende da política de conferência que foi atribuída a um usuário: se poucos usuários tiverem permissão para hospedar conferências PSTN, você obviamente verá poucas conferências PSTN. Você pode verificar rapidamente a qual das suas políticas de conferência (se houver) permitem que os usuários agendem conferências PSTN, executando o seguinte comando dentro do Skype do Shell de gerenciamento do servidor de negócios:
  
```
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

Serão retornados dados semelhantes a estes:
  
```
Identity                                EnableDialInConferencing
--------                                ------------------------
Global                                                      True
site:Redmond                                               False
site:Dublin                                                False
Tag:RedmondDialInUsers                                      True
Tag:DublinDialInUsers                                       True

```

## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Relatório de Resumo de Conferências PSTN permite escolher como os dados devem ser agrupados. Neste caso, as conferências são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Conferências PSTN.
  
**Filtros do relatório de resumo de conferências PSTN**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 03/07/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 03/07/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 7/7/2015 e a data de término 28/2/2015, os dados serão exibidos para os dias de 7/8/2015, meia-noite, a 7/9/2015, meia-noite, (ou seja, um total de 31 dias de dados). <br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações no Relatório de Resumo de Conferências PSTN.
  
**Métricas do relatório de resumo de conferências PSTN**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Por hora** <br/> **Por dia** <br/> **Por semana** <br/> **Por mês** <br/> |Não  <br/> |Indica o intervalo de tempo selecionado. Quando aplicável, você pode clicar em um dado intervalo de tempo para exibir informações detalhadas para aquele intervalo. Por exemplo, se estiver usando um intervalo por dia e clicar em 07/07/2015, você verá uma divisão por hora das atividades de registro do usuário para aquela data.  <br/> |
|**Total de conferências PSTN** <br/> |Não  <br/> |Número total de conferências que permitiram acesso discado.  <br/> |
|**Total de participantes** <br/> |Não  <br/> |Número total de pessoas que participaram de conferências que permitiram acesso discado.  <br/> |
|**Total de minutos de conferências de A/V** <br/> |Não  <br/> |Quantidade total do tempo de conferências audiovisuais.  <br/> |
|**Total de minutos de participantes de conferências de A/V** <br/> |Não  <br/> |Quantidade total do tempo de participantes audiovisuais. Por exemplo, se um participante passou cinco minutos em uma conferência de A/V e outro passou três minutos na mesma conferência, o tempo de participantes de conferência de A/V total seria oito minutos.  <br/> |
|**Total de participantes PSTN** <br/> |Não  <br/> |Número total de usuários que discaram para conferências que permitiram acesso discado.  <br/> |
|**Total de minutos de participantes PSTN** <br/> |Não  <br/> |Quantidade total de tempo de conferência gasto por usuários discados. Por exemplo, se um participante discado passou cinco minutos em uma conferência e outro passou três minutos na mesma conferência, o tempo de participantes PSTN total seria oito minutos.  <br/> |
|**Organizadores de conferência exclusivas** <br/> |Não  <br/> |Número total de usuários que organizaram no mínimo uma conferência que permitia acesso discado. Usuários que organizaram mais de uma conferência são contados como um organizador exclusivo, assim como usuários que organizaram somente uma única conferência.  <br/> |
   

