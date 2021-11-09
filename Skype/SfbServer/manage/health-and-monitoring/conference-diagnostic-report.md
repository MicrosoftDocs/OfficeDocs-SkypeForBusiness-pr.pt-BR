---
title: Relatório de Diagnóstico de Conferência Skype for Business Server
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
ms.assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
description: 'Resumo: saiba mais sobre o Relatório de Diagnóstico de Conferência usado Skype for Business Server.'
ms.openlocfilehash: 4e15819e220459664875e6a868c2644262885060
ms.sourcegitcommit: 67324fe43f50c8414bb65c52f5b561ac30b52748
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/08/2021
ms.locfileid: "60837553"
---
# <a name="conference-diagnostic-report-in-skype-for-business-server"></a>Relatório de Diagnóstico de Conferência Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Diagnóstico de Conferência usado Skype for Business Server.
  
O Relatório de Diagnóstico de Conferência oferece informações sobre êxito e falha de todas as sessões de conferência. Observe que Skype for Business Server diferencia entre diferentes tipos de falha:
  
- **Falha esperada**. Uma falha esperada normalmente é uma falha apenas no sentido mais técnico. Por exemplo, suponha que alguém inicie uma conferência mas desligue antes que alguém possa ingressar. Tecnicamente, é uma falha: a conferência foi iniciadas mas não concluída. No entanto, essa é uma falha que você poderia esperar que acontecesse: se o organizador cancela a conferência antes que alguém possa ingressar, você não esperaria que essa conferência fosse concluída.
    
- **Falha inesperada**. Uma falha inesperada é exatamente o que o nome diz: um erro que, baseado nas circunstâncias, você não esperaria que ocorrese. Por exemplo, suponha que uma conferência não tenha acontecido porque a política de reunião do organizador não pôde ser recuperada. Isso é um erro inesperado: afinal, sempre deve ser possível recuperar a política de reunião de um usuário.
    
Obseve que a soma das métricas de Êxitos, Falhas esperadas e Falhas inesperadas podem não resultar na métrica de Total de sessões. Por exemplo, você pode ver os seguines valores no Relatório:
  
|**Sucessos**|**Falhas esperadas**|**Falhas inesperadas**|**Total de sessões**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Se somar 2024 + 469 + 16 você obtém um total de 2.509 sessões, e no entanto a coluna de Total de sessões mostra um total de 2.521 sessões. As 12 sessões "faltando" são sessões que o sistema não foi capaz de categorizar como êxito ou falha. Às vezes, esse será o caso quando um produto de terceiros introduz um novo código de diagnóstico que não é familiar para o Monitoring Server. Quando isso acontece, chamadas feitas usando o produto, e os relatórios sobre o código de diagnóstico nem sempre podem ser categorizados como Êxitos, Falhas esperadas ou Falhas inesperadas.
  
## <a name="accessing-the-conference-diagnostic-report"></a>Acessando o Relatório de Diagnóstico de Conferência

O Relatório de Diagnóstico de Conferência é acessado a partir da página inicial de Relatórios de Monitoramento. Você pode acessar o [Relatório de Distribuição](failure-distribution-report.md) de Falhas Skype for Business Server clicando em uma das seguintes métricas:
  
- Volume de falhas inesperadas
    
- Volume de falhas esperadas
    
## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Usando o Relatório de Diagnóstico de Conferência da melhor maneira possível

O Relatório de Diagnóstico de Conferência inclui uma série de gráficos. Cada uma das colunas exibidas no gráfico é, na verdade, um hiperlink. Se você clicar em uma coluna, [](failure-distribution-report.md) será analisado o Relatório de Distribuição de Falhas no Skype for Business Server para esse período e esse tipo de conferência.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Diagnóstico de Conferência permite que você filtre coisas como o tipo de conferência que está sendo conduzida (por exemplo, uma conferência baseada em Foco) ou pelo Servidor de Borda usado na conferência. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as conferências são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Diagnóstico de Conferência.
  
**Filtros do Relatório de Diagnóstico de Conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/08/2015 12:00 a 7/09/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Pool** <br/> |FQDN (Nome de domínio totalmente qualificado) do pool de Registradores ou Servidor de Borda. Você pode selecionar um pool individual ou clicar em **[Tudo]** para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.<br/> |
|**Sessões de conferência** <br/> | Indica o tipo de sessão de conferência. Selecione uma das seguintes opções: <br/>  [Todos] <br/>  Sessões de foco <br/>  Todas as sessões MCU <br/>  Conferência de IM <br/>  Compartilhamento de aplicativos <br/>  Conferências A/V <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Diagnóstico de Conferência para cada tipo de sessão de conferência.
  
**Métricas do Relatório de Diagnóstico de Conferência**

|**Nome**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Volume de sucesso** <br/> |Não  <br/> |Número total de conferências bem-sucedidas.  <br/> |
|**Porcentagem de sucesso** <br/> |Não  <br/> |Percentual de conferências concluídas com problemas consideráveis. Calculado dividindo o volume de Sucesso pelo Total de sessões.  <br/> |
|**Volume de falha esperado** <br/> |Não  <br/> |Número total de conferências nas quais uma "falha esperada" ocorreu.  <br/> Uma falha esperada é quando se sabe que a falha ocorrerá. Por exemplo, se um usuário tiver definido seu status como Não perturbe, é esperado que qualquer chamada para esse usuário falhe.  <br/> |
|**Percentual de falha esperada** <br/> |Não  <br/> |Percentual de conferências que enfrentaram um erro esperado. Calculado pela divisão do Volume de falha esperado pelo Total de sessões.  <br/> |
|**Volume de falha esperado** <br/> |Não  <br/> |Número total de conferências onde uma "falha inesperada" ocorreu.  <br/> Uma falha inesperada é uma falha que ocorre no que aparenta ser um sistema íntegro. Por exemplo, uma chamada não deve ser encerrada se o chamador for colocado em espera. Se isso ocorrer, isso seria sinalizado como uma falha inesperada.  <br/> |
|**Percentual de falha inesperada** <br/> |Não  <br/> |Percentual de conferências que enfrentaram um erro esperado. Calculado pela divisão do Volume de falha inesperado pelo Total de sessões.  <br/> |
|**Total de sessões** <br/> |Não  <br/> |Número total de conferências, incluindo conferências bem-sucedidas, conferências com falha (falhas esperadas e inesperadas) e conferências não categorizadas.  <br/> |
   

