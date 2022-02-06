---
title: Relatório de Resumo de Conferências em Skype for Business Server
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.assetid: 62f54812-5700-45a3-8526-8f58b0f77fbc
description: 'Resumo: saiba mais sobre o Relatório de Resumo de Conferências Skype for Business Server.'
---

# <a name="conference-summary-report-in-skype-for-business-server"></a>Relatório de Resumo de Conferências em Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Resumo de Conferência Skype for Business Server.
  
O Relatório de Resumo de Conferências traz uma visão geral de suas sessões de conferência online. Uma conferência geralmente envolve mais de 2 usuários e requer o uso de serviços de conferência. Por comparação, uma sessão ponto a ponto geralmente envolve apenas dois usuários e não exige o uso de serviços de Skype for Business Server de conferência. As atividades ponto a ponto são relatadas no Relatório de Resumo de Atividades Ponto a Ponto [no Skype for Business Server](peer-to-peer-activity-summary-report.md).
  
O Relatório de Resumo de Conferência não apenas informa quantas conferências foram realizadas durante um determinado período de tempo (por hora, diariamente, semanal, mensal), mas também informa o número total de pessoas que participaram dessas conferências e o número total de organizadores de conferências exclusivos.
  
Um organizador "exclusivo" é qualquer pessoa que agenda pelo menos uma conferência. Por exemplo, se Pilar Ackerman agendar uma conferência, ela será contabilizada como um organizador exclusivo. Se Ken Myer agendar 148 conferências, ele também será contabilizado como um único organizador exclusivo. Por exemplo, a tabela a seguir mostra 8 conferências agendadas, mas apenas três organizadores exclusivos (Ken Myer, Pilar Ackerman e David Ahs).
  
|**Organizador da conferência**|**Data da conferência**|
|:-----|:-----|
|Ken Myer  <br/> |7/07/2015 10:00  <br/> |
|David Ahs  <br/> |7/07/2015 10:00  <br/> |
|Ken Myer  <br/> |7/07/2015 11:00  <br/> |
|Pilar Ackerman  <br/> |7/07/2015 11:00  <br/> |
|Ken Myer  <br/> |7/7/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |7/07/2015 14:00  <br/> |
|Ken Myer  <br/> |2/07/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |2/07/2015 10:00  <br/> |
   
O Relatório de Resumo de Conferências também indica quantas conferências incluíram áudio e/ou vídeo.
  
## <a name="accessing-the-conference-summary-report"></a>Acessando o Relatório de Resumo de Conferências

O Relatório de Resumo de Conferências pode ser acessado na home page Relatórios de Monitoramento. Você pode filtrar pelo Relatório de Atividade de Conferência clicando em uma das métricas a seguir:
  
- Total de conferências
    
- Total de participantes
    
## <a name="making-the-best-use-of-the-conference-summary-report"></a>Usando o Relatório de Resumo de Conferências da melhor maneira possível

Os valores totais da maioria das métricas usadas no Relatório de Resumo de Conferência podem ser encontrados na parte inferior do relatório; role para baixo para ver valores como o número total de conferências realizadas durante o período especificado e o número total de pessoas que participaram dessas conferências. Uma métrica que não é totalada na parte inferior do relatório é Total de organizadores de conferência exclusivos. Por que não? Aqui está um motivo. Suponha que você está olhando para o valor de um mês de dados. No dia 1, você tinha 34 organizadores de conferência exclusivos; no dia 2, você tinha 27 organizadores de conferência exclusivos. Isso significa que você tinha 61 organizadores de conferência exclusivos para esses dois dias? Não necessariamente. Afinal, todas as 27 pessoas que organizaram conferências no dia 2 podem estar entre as 34 pessoas que organizaram conferências no dia 1. Por exemplo, neste relatório simples, observe que Ken Myer e Pilar Ackerman agendam conferências em 7/7/2015 e 02/07/2015:
  
|**Organizador da conferência**|**Data da conferência**|
|:-----|:-----|
|Ken Myer  <br/> |7/07/2015 10:00  <br/> |
|David Ahs  <br/> |7/07/2015 10:00  <br/> |
|Ken Myer  <br/> |7/07/2015 11:00  <br/> |
|Pilar Ackerman  <br/> |7/07/2015 11:00  <br/> |
|Ken Myer  <br/> |7/7/2015 13:00  <br/> |
|Pilar Ackerman  <br/> |7/07/2015 14:00  <br/> |
|Ken Myer  <br/> |2/07/2015 10:00  <br/> |
|Pilar Ackerman  <br/> |2/07/2015 10:00  <br/> |
   
Para ter uma ideia melhor do número total de usuários exclusivos que organizaram conferências, altere o intervalo de tempo. Por exemplo, exiba os dados por mês e não por dia.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de diferentes maneiras. Por exemplo, o Relatório de Resumo de Conferências permite que você escolha como os dados devem ser agrupados. Nesse caso, conferências agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que você pode usar com o Relatório de Resumo de Conferências.
  
**Filtros do Relatório de Resumo de Conferências**

|**Name**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Por mês (um máximo de 12 meses pode ser exibido) <br/>  Se as datas de início e término excedem o número máximo de valores permitidos para o intervalo selecionado, apenas o número máximo de valores (começando pela data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/08/2015 12:00 a 7/09/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir as informações fornecidas pelo 	Relatório de Resumo de Conferências.
  
**Métricas do Relatório de Resumo de Conferências**

|**Name**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**A cada hora** <br/> **Diariamente** <br/> **Semanalmente** <br/> **Mensal** <br/> |Não  <br/> |Indica o intervalo de tempo selecionado na barra de ferramentas de filtro. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se você estiver usando o intervalo Diário e clicar em 7/7/2015, verá uma divisão por hora da atividade de registro do usuário para essa data.  <br/> |
|**Total de conferências** <br/> |Não  <br/> |Número total de conferências (independentemente do tipo de conferência) que foram mantidas. Quando você clica nesse item, o relatório mostra o Relatório de Resumo de Conferências para o período de tempo selecionado.  <br/> |
|**Total de participantes** <br/> |Não  <br/> |Número total de pessoas que participaram nas conferências. Quando você clica nesse item, o relatório mostra o Relatório de Resumo de Conferências para o período de tempo selecionado.  <br/> |
|**Média de participantes por conferência** <br/> |Não  <br/> |Número médio de pessoas que participaram de uma determinada conferência. É determinado dividindo o total de conferências pelo total de participantes.  <br/> |
|**Total de conferências A/V** <br/> |Não  <br/> |Número total de conferências com áudio ou vídeo.  <br/> |
|**Total de minutos da conferência A/V** <br/> |Não  <br/> |Número total de minutos para a conferência de áudio/vídeo.  <br/> A métrica de minutos de conferência A/V total resume todos os tipos de conferências de áudio/visual, incluindo: conferências A/V; Conferências de IM; conferências de compartilhamento de aplicativos; conferências de dados; e conferências PSTN.  <br/> |
|**Total de minutos do participante da conferência A/V** <br/> |Não  <br/> |Número total de minutos do participante na conferência de áudio/vídeo. Por exemplo, suponha que um usuário gaste cinco minutos em uma conferência de áudio/vídeo e um segundo usuário gaste três minutos nessa mesma conferência. O que soma um total de oito minutos de participantes: cinco minutos mais três minutos.  <br/> |
|**Média de minutos da conferência A/V** <br/> |Não  <br/> |Número médio de minutos por conferência de áudio/vídeo.  <br/> |
|**Número total de organizadores exclusivos de conferências** <br/> |Não  <br/> |Número total de usuários que organizaram pelo menos uma conferência. Os usuários que organizaram mais de uma conferência são contados como um organizador exclusivo, assim como os usuários que só organizaram uma única conferência.  <br/> |
|**Total de mensagens de conferência** <br/> |Não  <br/> |Número total de mensagens instantâneas enviadas durante as conferências.  <br/> |
   

