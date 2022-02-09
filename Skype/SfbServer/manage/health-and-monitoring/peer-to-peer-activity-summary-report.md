---
title: Relatório de resumo de atividades ponto a ponto no Skype for Business Server
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
ms.assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
description: 'Resumo: saiba mais sobre o Relatório de Resumo de Atividades Ponto a Ponto no Skype for Business Server.'
ms.openlocfilehash: 3db7a69bb0460337e56ee7e4ce43d4c1ce4b240e
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62411544"
---
# <a name="peer-to-peer-activity-summary-report-in-skype-for-business-server"></a>Relatório de resumo de atividades ponto a ponto no Skype for Business Server
 
**Resumo:** Saiba mais sobre o Relatório de Resumo de Atividades Ponto a Ponto no Skype for Business Server.
  
O Relatório de Resumo de Atividades Ponto a Ponto fornece uma visão geral de suas sessões de comunicação ponto a ponto. Uma sessão ponto a ponto geralmente envolve apenas dois usuários e não exige o uso dos serviços de Skype for Business Server de conferência. Por comparação, uma conferência geralmente envolve mais de dois usuários e requer o uso de serviços Skype for Business Server conferência. Atividades de conferência são relatadas no Relatório de Resumo de Conferência.
  
O Relatório de Resumo de Atividade Ponto a Ponto ajuda você a responder perguntas como as seguintes:
  
- Quantas mensagens instantâneas ponto a ponto meus usuários enviam em um dia normal?
    
- Algum dos meus usuários está realmente aproveitando os recursos de compartilhamento Skype for Business Server de aplicativos e transferência de arquivos?
    
- Usuários tem reclamado que a rede parece devagar em certos horários do dia. Quantos minutos são devotados para sessões de áudio e video durante estes períodos de tempo?
    
## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Acessando o Relatório de Resumo de Atividade Ponto a Ponto

O Relatório de Resumo de Atividade Ponto a Ponto é acessado a partir da página inicial de Relatórios de Monitoramento. Você abre o [Relatório de IM Ponto a](im-report.md) Ponto no Skype for Business Server clicando em uma das seguintes métricas:
  
- Total de sessões de mensagens instantâneas ponto a ponto
    
- Total de mensagens instantâneas ponto a ponto
    
De modo parecido, você pode abrir o Relatório de Vídeo e Voz Ponto a Ponto clicando em qualquer uma destas métricas:
  
- Total de sessões de áudio ponto a ponto
    
- Total de minutos de sessão de áudio ponto a ponto
    
- Total de sessões de áudio ponto a ponto
    
- Total de minutos de sessão de áudio ponto a ponto
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Fazendo o Melhor Uso do Relatório de Resumo de Atividade Ponto a Ponto

Ao final do Relatório de Resumo de Atividade Ponto a Ponto, você encontrará os totais para métricas tais como Total de sessões de mensagens instantâneas ponto a ponto e Total de mensagens instantâneas ponto a ponto. Isso oferece um resumo rápido das informações detalhadas encontradas no corpo do relatório.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Resumos de Atividades Ponto a Ponto permite que você escolha como os dados devem ser agrupados. Nesse caso, atividades agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumos de Atividades Ponta a Ponta.
  
**Filtros do Relatório de Resumos de Atividades Ponto a Ponto**

|**Name**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data e hora de início para o intervalo de tempo. Para exibir os dados por horas, digite a data e a hora de início da seguinte maneira:  <br/> 17/07/12015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/17/12015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/13/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data e hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 17/07/12015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/17/12015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/13/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 17/07/12015 e uma data final de 28/02/2015, os dados serão exibidos para os dias 07/08/12015 12:00 a 7/09/12015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
   
## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Resumos de Atividades Ponto a Ponto.
  
**Métricas do Relatório de Resumos de Atividades Ponto a Ponto**

|**Name**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**A cada hora** <br/> **Diariamente** <br/> **Semanalmente** <br/> **Mensal** <br/> |Não  <br/> |Indica o intervalo de tempo selecionado na barra de ferramentas de filtro. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se você estiver usando o intervalo Diário e clicar em 17/07/12015, verá uma divisão por hora da atividade de registro do usuário para essa data.  <br/> |
|**Total de sessões ponto a ponto** <br/> |Não  <br/> |Número total de sessões ponto a ponto conduzidas, independentemente do tipo de sessão.  <br/> |
|**Total de sessões de mensagens instantâneas ponto a ponto** <br/> |Não  <br/> |Número total de sessões de mensagens instantâneas (IM) ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.  <br/> |
|**Total de mensagens instantâneas ponto a ponto** <br/> |Não  <br/> |Número total de mensagens instantâneas enviadas em sessões ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.  <br/> |
|**Total de sessões de áudio ponto a ponto** <br/> |Não  <br/> |Número total de chamadas de áudio ponto a ponto. Quando você clica nesse campo, o relatório mostra o Relatório de de Voz e Vídeo Ponto a Ponto para o período selecionado.  <br/> |
|**Total de minutos de sessão de áudio ponto a ponto** <br/> |Não  <br/> |Tempo total gasto em sessões de áudio ponto a ponto. Quando você clica nesse item, o relatório mostra o relatório de vídeo e voz ponto a ponto para o período de tempo selecionado.  <br/> |
|**Média de minutos de sessão de áudio ponto a ponto** <br/> |Não  <br/> |Tempo médio gasto em sessões de áudio ponto a ponto. Calculado dividindo o tempo de sessão de áudio total pelo número total de sessões de áudio.  <br/> |
|**Total de sessões de vídeo ponto a ponto** <br/> |Não  <br/> |Número total de chamadas de vídeo ponto a ponto. Observe que as sessões de vídeo também são contadas como sessões de áudio: cada sessão de vídeo é contada como uma sessão de vídeo e uma sessão de áudio. Quando você clica nesse item, o relatório mostra o relatório de vídeo e voz ponto a ponto para o período de tempo selecionado.  <br/> |
|**Total de minutos de sessão de vídeo ponto a ponto** <br/> |Não  <br/> |Tempo total gasto em sessões de vídeo ponto a ponto. Quando você clica nesse item, o relatório mostra o relatório de vídeo e voz ponto a ponto para o período de tempo selecionado.  <br/> |
|**Média de minutos de sessão de vídeo ponto a ponto** <br/> |Não  <br/> |Tempo médio gasto em sessões de vídeo ponto a ponto. Calculado dividindo o tempo de sessão de vídeo total pelo número total de sessões de áudio.  <br/> |
|**Total de sessões de transferência de arquivo ponto a ponto** <br/> |Não  <br/> |Número total de sessões ponto a ponto que incluem transferências de arquivo.  <br/> |
|**Total de sessões de compartilhamento de arquivo ponto a ponto** <br/> |Não  <br/> |Número total de sessões ponto a ponto que incluem compartilhamento de aplicativo.  <br/> |
   

