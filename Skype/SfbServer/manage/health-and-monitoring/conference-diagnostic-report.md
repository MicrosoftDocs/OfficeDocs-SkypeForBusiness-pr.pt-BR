---
title: Relatório de diagnóstico conferência no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e9edc23c-8ce8-4ab8-8786-9d22e1e51e14
description: 'Resumo: Saiba mais sobre o relatório de diagnóstico de conferência usado na Skype para servidor de negócios.'
ms.openlocfilehash: b2cfd39ab3d6bdc6af8230bbed995e511719bf72
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33926568"
---
# <a name="conference-diagnostic-report-in-skype-for-business-server"></a>Relatório de diagnóstico conferência no Skype para Business Server
 
**Resumo:** Saiba mais sobre o relatório de diagnóstico de conferência usado na Skype para servidor de negócios.
  
O Relatório de Diagnóstico de Conferência oferece informações sobre o êxito e a falha de todas as sessões de conferência. Observe que Skype para Business Server faz distinção entre diferentes tipos de falha:
  
- **Falha esperada**. Uma falha esperada normalmente é uma falha apenas no sentido mais técnico. Por exemplo, suponhamos que alguém inicie uma conferência, mas desligue antes que alguém possa ingressar. Tecnicamente, é uma falha: a conferência foi iniciada, mas não foi concluída. No entanto, essa é uma falha que você poderia esperar que acontecesse: se o organizador cancela a conferência antes que alguém possa ingressar, não se poderia esperar que essa conferência fosse concluída.
    
- **Falha inesperada**. Uma falha inesperada é exatamente o que o nome diz: um erro que, baseado nas circunstâncias, você não esperaria que ocorresse. Por exemplo, suponhamos que uma conferência não tenha acontecido porque a política de reunião do organizador não pôde ser recuperada. Isso é um erro inesperado: afinal, sempre deve ser possível recuperar a política de reunião de um usuário.
    
Observe que a soma das métricas de Êxitos, Falhas esperadas e Falhas inesperadas podem não resultar na métrica de Total de sessões. Por exemplo, você pode ver os seguintes valores no Relatório:
  
|**Êxitos**|**Falhas esperadas**|**Falhas inesperadas**|**Total de sessões**|
|:-----|:-----|:-----|:-----|
|2024  <br/> |469  <br/> |16  <br/> |2521  <br/> |
   
Somando 2024 + 469 + 16, você obtém um total de 2.509 sessões e, no entanto, a coluna de Total de sessões mostra um total de 2.521 sessões. As 12 sessões que estão "faltando" são sessões que o sistema não conseguiu categorizar como êxito ou falha. Em alguns casos, que será o caso quando um produto de terceiros introduz um novo código de diagnóstico que está familiarizado ao Monitoring Server. Quando isso acontece, as chamadas efetuadas com o produto e o relatório desse código de diagnóstico nem sempre podem ser categorizados como Êxito, Falha esperada ou Falha inesperada.
  
## <a name="accessing-the-conference-diagnostic-report"></a>Acessando o Relatório de Diagnóstico de Conferência

O Relatório de Diagnóstico de Conferência é acessado na página inicial de Relatórios de Monitoramento. Você pode acessar o [Relatório de falha de distribuição no Skype para Business Server](failure-distribution-report.md) clicando em uma das seguintes métricas:
  
- Volume de falhas inesperadas
    
- Volume de falhas esperadas
    
## <a name="making-the-best-use-of-the-conference-diagnostic-report"></a>Como usar o Relatório de Diagnóstico de Conferência da melhor maneira possível

O Relatório de Diagnóstico de Conferência inclui uma série de gráficos. Cada uma das colunas exibidas no gráfico é, na verdade, um hiperlink. Se você clicar em uma coluna, você vai ver os detalhes do [Relatório de falha de distribuição no Skype para Business Server](failure-distribution-report.md) para esse período de tempo e que tipo de conferência.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Diagnóstico de Conferência permite que você filtre coisas como o tipo de conferência que está sendo conduzida (por exemplo, uma conferência baseada em Foco) ou pelo Servidor de Borda usado na conferência. Também é possível escolher como os dados devem ser agrupados. Nesse caso, as conferências são agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Diagnóstico de Conferência.
  
**Filtros do Relatório de Diagnóstico de Conferência**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 7/7/2015 e a data de término 28/2/2015, os dados serão exibidos para os dias de 7/8/2015 12:00 a 7/9/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
|**Pool** <br/> |FQDN (Nome de domínio totalmente qualificado) do pool de Registradores Avançados ou Servidores de Borda. Você pode selecionar um pool individual ou clicar em **[Tudo]** para ver os dados de todos os pools. Essa lista suspensa é automaticamente preenchida para você com base nos registros no banco de dados.<br/> |
|**Sessões de conferência** <br/> | Indica o tipo de sessão de conferência. Selecione uma das seguintes opções: <br/>  [Todos] <br/>  Sessões de foco <br/>  Todas as sessões MCU <br/>  Conferência de IM <br/>  Compartilhamento de aplicativos <br/>  Conferência de A/V <br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Diagnóstico de Conferência para cada tipo de sessão de conferência.
  
**Métricas do Relatório de Diagnóstico de Conferência**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Volume de sucesso** <br/> |Não  <br/> |Número total de conferências bem-sucedidas.  <br/> |
|**Porcentagem de sucesso** <br/> |Não  <br/> |Percentual de conferências concluídas com problemas consideráveis. Calculado dividindo o Volume de sucesso pelo Total de sessões.  <br/> |
|**Volume de falha esperado** <br/> |Não  <br/> |Número total de conferências nas quais uma "falha esperada" ocorreu.  <br/> Uma falha esperada é quando se sabe que a falha ocorrerá. Por exemplo, se um usuário tiver definido seu status como Não Incomodar, é esperado que qualquer chamada para esse usuário falhe.  <br/> |
|**Percentual de falhas esperadas** <br/> |Não  <br/> |Percentual de conferências que enfrentaram um erro esperado. Calculado pela divisão do Volume de falha esperado pelo Total de sessões.  <br/> |
|**Volume de falha inesperado** <br/> |Não  <br/> |Número total de conferências onde uma "falha inesperada" ocorreu.  <br/> Uma falha inesperada é uma falha que ocorre no que aparenta ser um sistema íntegro. Por exemplo, uma chamada não deve ser encerrada se o chamador for colocado em espera. Se isso ocorrer, isso seria sinalizado como uma falha inesperada.  <br/> |
|**Percentual de falhas inesperadas** <br/> |Não  <br/> |Percentual de conferências que enfrentaram um erro esperado. Calculado pela divisão do Volume de falha inesperado pelo Total de sessões.  <br/> |
|**Total de sessões** <br/> |Não  <br/> |Número total de conferências, incluindo conferências bem-sucedidas, conferências com falha (falhas esperadas e inesperadas) e conferências não categorizadas.  <br/> |
   

