---
title: Relatório de Resumo de Conferência PSTN no Skype for Business Server
ms.reviewer: ''
ms.author: v-mahoffman
author: HowlinWolf-92
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: 8e2f0862-4dfa-4c2b-bf8d-ad71419f15d2
description: 'Resumo: saiba mais sobre o Relatório de Resumo da Conferência PSTN no Skype for Business Server.'
ms.openlocfilehash: 19038b29f46e33026e3ef865226aa4d087b0a0da
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60862288"
---
# <a name="pstn-conference-summary-report-in-skype-for-business-server"></a>Relatório de Resumo de Conferência PSTN no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Resumo da Conferência PSTN no Skype for Business Server.
  
Em Skype for Business Server, uma conferência PSTN é qualquer conferência na qual pelo menos um participante disca para a parte de áudio usando um telefone PSTN (rede telefônica pública comutado). (Um telefone PSTN é um "telefone fixo", um telefone celular ou qualquer outro telefone que não faça uso do Voice sobre IP.) Embora sejam conhecidas como conferências PSTN nos Relatórios de Monitoramento, essas conferências talvez sejam mais conhecidas como conferências discadas.
  
O Relatório de Resumo de Conferência PSTN fornece informações sobre todas as conferências PSTN realizadas em sua organização (ou seja, todas as conferências que tinham pelo menos um usuário discado). O relatório inclui informações sobre o número total de conferências PSTN, o número total de pessoas que participaram dessas conferências e, talvez, o mais importante, o número total de usuários discados (a métrica total de participantes PSTN).
  
## <a name="accessing-the-pstn-conference-summary-report"></a>Acessando o Relatório de Resumo de Conferência PSTN

O Relatório de Resumo de Conferência PSTN só pode ser acessado na home page Relatórios de Monitoramento. Este relatório não está vinculado a nenhum outro relatório. Observe que você não pode recuperar informações detalhadas de chamada para uma conferência PSTN, em parte porque os pontos de extremidade individuais são responsáveis por enviar essas informações. Os telefones PSTN não são capazes de rastrear ou enviar informações detalhadas de chamada.
  
## <a name="making-the-best-use-of-the-pstn-conference-summary-report"></a>Fazendo o melhor uso do Relatório de Resumo de Conferência PSTN

Para determinar a porcentagem de todas as conferências que incluem usuários discados, compare o valor da métrica total de conferências PSTN com a métrica Total de conferências encontrada no Relatório de Resumo de Conferências [em Skype for Business Server](conference-summary-report.md).
  
Se você não vir tantas conferências PSTN como você pode esperar ver, lembre-se de que a capacidade de organizar uma conferência que permite que os usuários de discagem dependam da política de conferência atribuída a um usuário: se muito poucos dos seus usuários têm permissão para realizar conferências PSTN, obviamente, você verá muito poucas conferências PSTN. Você pode verificar rapidamente quais das suas políticas de conferência (se alguma) permitem que os usuários agendem conferências PSTN executando o seguinte comando no Shell de Gerenciamento do Skype for Business Server:
  
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

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Resumo de Conferência PSTN permite que você escolha como os dados devem ser agrupados. Nesse caso, as conferências são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que você pode usar com o Relatório de Resumo de Conferência PSTN.
  
**Filtros de relatório de resumo de conferência PSTN**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/08/2015 12:00 a 7/09/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações no Relatório de Resumo de Conferência PSTN.
  
**Métricas do Relatório de Resumo de Conferência PSTN**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**A cada hora** <br/> **Diariamente** <br/> **Semanalmente** <br/> **Mensal** <br/> |Não  <br/> |Indica o intervalo de tempo selecionado. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se você estiver usando o intervalo Diário e clicar em 7/7/2015, verá uma divisão por hora da atividade de registro do usuário para essa data.  <br/> |
|**Total de conferências PSTN** <br/> |Não  <br/> |Total de conferências de número que permitiram o acesso de discagem.  <br/> |
|**Total de participantes** <br/> |Não  <br/> |Número total de pessoas que participaram de conferências que permitiam o acesso de discagem.  <br/> |
|**Total de minutos da conferência A/V** <br/> |Não  <br/> |Quantidade total de tempo de conferência áudio/visual.  <br/> |
|**Total de minutos do participante da conferência A/V** <br/> |Não  <br/> |Quantidade total de tempo do participante áudio/visual. Por exemplo, se um participante passou cinco minutos em uma conferência A/V e outro passou três minutos na mesma conferência, o tempo total de participantes da conferência A/V seria de oito minutos.  <br/> |
|**Total de participantes PSTN** <br/> |Não  <br/> |Número total de usuários discados para conferências que permitiram o acesso de discagem.  <br/> |
|**Total de minutos de participantes PSTN** <br/> |Não  <br/> |Quantidade total de tempo de conferência gasto pelos usuários discados. Por exemplo, se um participante discado passou cinco minutos em uma conferência e outro passou três minutos na mesma conferência, o tempo total de participantes PSTN seria de oito minutos.  <br/> |
|**Organizadores exclusivos de conferência** <br/> |Não  <br/> |Número total de usuários que organizaram pelo menos uma conferência que permitia acesso discado. Os usuários que organizaram mais de uma conferência são contados como um organizador exclusivo, assim como os usuários que só organizaram uma única conferência.  <br/> |
   

