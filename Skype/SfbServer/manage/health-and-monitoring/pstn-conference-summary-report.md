---
title: Relatório de Resumo de Conferência PSTN no Skype for Business Server
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
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Resumo: saiba mais sobre o Relatório de Resumo de ConferênciaS PSTN no Skype for Business Server.'
ms.openlocfilehash: aab91995a2c987e1a6e3a10d1f6fc8791b19a4b1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49814371"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>Relatório de Resumo de Conferência PSTN no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Resumo de ConferênciaS PSTN no Skype for Business Server.
  
No Skype for Business Server, uma conferência PSTN é qualquer conferência na qual pelo menos um participante disca para a parte de áudio usando um telefone PSTN (rede telefônica pública comutado). (Um telefone PSTN é uma "linha fixa", um telefone celular ou qualquer outro telefone que não use o Voice over IP.) Embora referidas como conferências PSTN nos Relatórios de Monitoramento, essas conferências são talvez mais comumente conhecidas como conferências discadas.
  
O Relatório de Resumo de Conferências PSTN fornece informações sobre todas as conferências PSTN realizadas em sua organização (ou seja, todas as conferências que tinham pelo menos um usuário discado). O relatório inclui informações sobre o número total de conferências PSTN, o número total de pessoas que participaram dessas conferências e, talvez, o mais importante, o número total de usuários discados (a métrica Total de participantes PSTN).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Acessando o Relatório de Resumo de ConferênciaS PSTN

O Relatório de Resumo de ConferênciaS PSTN só pode ser acessado a partir da página inicial dos Relatórios de Monitoramento. Este relatório não está vinculado a nenhum outro relatório. Observe que não é possível recuperar informações de chamada detalhadas para uma conferência PSTN, em parte porque os pontos de extremidade individuais são responsáveis por enviar essas informações. Os telefones PSTN não são capazes de rastrear ou enviar informações de detalhes de chamada.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Fazendo o melhor uso do Relatório de Resumo de Conferências PSTN

Para determinar a porcentagem de todas as conferências que incluem usuários discados, compare o valor da métrica Total de conferências PSTN com a métrica Total de conferências encontrada no Relatório de Resumo de Conferências no [Skype for Business Server.](conference-summary-report.md)
  
Se você não vir tantas conferências PSTN que espera ver, tenha em mente que a capacidade de organizar uma conferência que permite usuários de discagem depende da política de conferência que foi atribuída a um usuário: se poucos usuários têm permissão para realizar conferências PSTN, você obviamente verá poucas conferências PSTN. Você pode verificar rapidamente quais das suas políticas de conferência (se alguma) permitem que os usuários agendem conferências PSTN executando o seguinte comando no Shell de Gerenciamento do Skype for Business Server:
  
```PowerShell
Get-CsConferencingPolicy | Select-Object Identity, EnableDialInConferencing
```

That will return data similar to this:
  
<pre>
Identity                                EnableDialInConferencing
--------                                ------------------------
Global                                                      True
site:Redmond                                               False
site:Dublin                                                False
Tag:RedmondDialInUsers                                      True
Tag:DublinDialInUsers                                       True
</pre>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Resumo de Conferências PSTN permite escolher como os dados devem ser agrupados. Nesse caso, as conferências são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que você pode usar com o Relatório de Resumo de Conferências PSTN.
  
**Filtros do Relatório de Resumo de ConferênciaS PSTN**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/8/2015 12:00 a 7/9/2015 00:00 (ou seja, um total de 31 dias de dados). <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações do Relatório de Resumo de Conferências PSTN.
  
**Métricas do Relatório de Resumo de ConferênciaS PSTN**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**A cada hora** <br/> **Diariamente** <br/> **Semanalmente** <br/> **Mensal** <br/> |Não  <br/> |Indica o intervalo de tempo selecionado. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se você estiver usando o intervalo Diário e clicar em 7/7/2015, verá uma divisão por hora da atividade de registro do usuário para essa data.  <br/> |
|**Total de conferências PSTN** <br/> |Não  <br/> |Número total de conferências que permitiram acesso discado.  <br/> |
|**Total de participantes** <br/> |Não  <br/> |Número total de pessoas que participaram de conferências que permitiram acesso discado.  <br/> |
|**Total de minutos da conferência A/V** <br/> |Não  <br/> |Quantidade total de tempo de conferência de áudio/visual.  <br/> |
|**Total de minutos do participante da conferência A/V** <br/> |Não  <br/> |Quantidade total de tempo do participante audiovisual. Por exemplo, se um participante passou cinco minutos em uma conferência A/V e outro passou três minutos na mesma conferência, o tempo total de participantes da conferência A/V seria oito minutos.  <br/> |
|**Total de participantes PSTN** <br/> |Não  <br/> |Número total de usuários que discam para conferências que permitiram acesso discado.  <br/> |
|**Total de minutos de participantes PSTN** <br/> |Não  <br/> |Quantidade total de tempo de conferência gasto por usuários discados. Por exemplo, se um participante discado passou cinco minutos em uma conferência e outro passou três minutos na mesma conferência, o tempo total de participantes PSTN seria oito minutos.  <br/> |
|**Organizadores exclusivos da conferência** <br/> |Não  <br/> |Número total de usuários que organizaram pelo menos uma conferência que permitiu acesso discado. Os usuários que organizaram mais de uma conferência são contados como um organizador exclusivo, assim como os usuários que só organizaram uma única conferência.  <br/> |
   

