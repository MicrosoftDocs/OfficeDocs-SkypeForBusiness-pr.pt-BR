---
title: Relatório de Resumo de atividade ponto a ponto no Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: e829a21e-9dfa-46ba-9b5b-077c175d6586
description: 'Resumo: Saiba mais sobre o relatório de Resumo de atividades ponto a ponto no Skype for Business Server.'
ms.openlocfilehash: 001298b948f3a3b8b9b404387fe4d93843297c8a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817780"
---
# <a name="peer-to-peer-activity-summary-report-in-skype-for-business-server"></a>Relatório de Resumo de atividade ponto a ponto no Skype for Business Server
 
**Resumo:** Saiba mais sobre o relatório de Resumo de atividades ponto a ponto no Skype for Business Server.
  
O Relatório de Resumo de Atividades Ponto a Ponto fornece uma visão geral de suas sessões de comunicação ponto a ponto. Uma sessão ponto a ponto geralmente envolve apenas dois usuários e não requer o uso dos serviços de conferência do Skype for Business Server. Por comparação, uma conferência geralmente envolve mais de dois usuários e requer o uso de serviços de conferência do Skype for Business Server. As atividades de conferência são relatadas no Relatório de Resumo de Conferências.
  
O Relatório de Resumo de Atividades Ponto a Ponto ajuda você a responder perguntas como as seguintes:
  
- Quantas mensagens instantâneas ponto a ponto meus usuários enviam em um dia normal?
    
- Algum dos meus usuários realmente aproveita os recursos de compartilhamento de aplicativos e transferência de arquivos do Skype for Business Server?
    
- Os usuários têm reclamado que a rede parece devagar em certos horários do dia. Quantos minutos são dedicados às sessões de áudio e vídeo durante esses períodos?
    
## <a name="accessing-the-peer-to-peer-activity-summary-report"></a>Acessando o Relatório de Resumo de Atividades Ponto a Ponto

O Relatório de Resumo de Atividades Ponto a Ponto é acessado na página inicial de Relatórios de Monitoramento. Você abre o [relatório de im ponto a ponto no Skype for Business Server](im-report.md) clicando em uma das seguintes métricas:
  
- Total de sessões de mensagens instantâneas ponto a ponto
    
- Total de mensagens instantâneas ponto a ponto
    
Da mesma forma, você pode abrir o Relatório de Vídeo e Voz Ponto a Ponto clicando em qualquer uma destas métricas:
  
- Total de sessões de áudio ponto a ponto
    
- Total de minutos de sessão de áudio ponto a ponto
    
- Total de sessões de áudio ponto a ponto
    
- Total de minutos de sessão de áudio ponto a ponto
    
## <a name="making-the-best-use-of-the-peer-to-peer-activity-summary-report"></a>Como usar o Relatório de Resumo de Atividades Ponto a Ponto da melhor maneira possível

No final do Relatório de Resumo de Atividades Ponto a Ponto, você encontrará os totais de métricas como Total de sessões de mensagens instantâneas ponto a ponto e Total de mensagens instantâneas ponto a ponto. Isso oferece um resumo rápido das informações detalhadas encontradas no corpo do relatório.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Resumo de Atividades Ponto a Ponto permite que você escolha como os dados devem ser agrupados. Nesse caso, atividades agrupadas por hora, dia, semana ou mês.
  
A tabela a seguir lista os filtros que podem ser usados com o Relatório de Resumo de Atividades Ponto a Ponto.
  
**Filtros do Relatório de Resumo de Atividades Ponto a Ponto**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data e hora de início do intervalo de tempo. Para ver os dados por hora, insira a data e hora de início desta forma:  <br/> 17/7/12015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 17/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 13/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data e hora de término do intervalo de tempo. Para ver os dados por hora, insira a data e hora de término desta forma:  <br/> 17/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 17/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 13/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Intervalo** <br/> | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensal (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com a data de início 17/7/2015 e uma data de término de 28/2/2015, os dados serão exibidos para os dias 7/8/2015, meia-noite, até 7/9/2015, meia-noite (ou seja, um total de 31 dias de dados). <br/> |
   
## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Resumo de Atividades Ponto a Ponto.
  
**Métricas do Relatório de Resumo de Atividades Ponto a Ponto**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Por hora** <br/> **Diário** <br/> **Semanal** <br/> **Mensal** <br/> |Não  <br/> |Indica o intervalo de tempo selecionado na barra de ferramentas do filtro. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se você estiver usando o intervalo Diário e clicar em 17/7/2015, você verá uma divisão por hora da atividade de registro do usuário para essa data.  <br/> |
|**Total de sessões ponto a ponto** <br/> |Não  <br/> |Número total de sessões ponto a ponto conduzidas, independentemente do tipo de sessão.  <br/> |
|**Total de sessões de mensagens instantâneas ponto a ponto** <br/> |Não  <br/> |Número total de sessões de mensagens instantâneas (IM) ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.  <br/> |
|**Total de mensagens instantâneas ponto a ponto** <br/> |Não  <br/> |Número total de mensagens instantâneas enviadas em sessões ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Mensagens Instantâneas Ponto a Ponto para o período selecionado.  <br/> |
|**Total de sessões de áudio ponto a ponto** <br/> |Não  <br/> |Número total de chamadas de áudio ponto a ponto. Quando você clica nesse campo, o relatório mostra o Relatório de Voz e Vídeo Ponto a Ponto para o período selecionado.  <br/> |
|**Total de minutos de sessão de áudio ponto a ponto** <br/> |Não  <br/> |Tempo total gasto em sessões de áudio ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Vídeo e Voz Ponto a Ponto do período selecionado.  <br/> |
|**Média de minutos de sessão de áudio ponto a ponto** <br/> |Não  <br/> |Tempo médio gasto em sessões de áudio ponto a ponto. Calculado dividindo o tempo total de sessão de áudio pelo número total de sessões de áudio.  <br/> |
|**Total de sessões de vídeo ponto a ponto** <br/> |Não  <br/> |Número total de chamadas de vídeo ponto a ponto. Observe que as sessões de vídeo também contam como sessões de áudio: cada sessão de vídeo conta como uma sessão de vídeo e uma sessão de áudio. Quando você clica nesse item, o relatório mostra o Relatório de Vídeo e Voz Ponto a Ponto do período selecionado.  <br/> |
|**Total de minutos de sessão de vídeo ponto a ponto** <br/> |Não  <br/> |Tempo total gasto em sessões de vídeo ponto a ponto. Quando você clica nesse item, o relatório mostra o Relatório de Vídeo e Voz Ponto a Ponto do período selecionado.  <br/> |
|**Média de minutos de sessão de vídeo ponto a ponto** <br/> |Não  <br/> |Tempo médio gasto em sessões de vídeo ponto a ponto. Calculado dividindo o tempo total de sessão de vídeo pelo número total de sessões de áudio.  <br/> |
|**Total de sessões de transferência de arquivo ponto a ponto** <br/> |Não  <br/> |Número total de sessões ponto a ponto que incluem transferências de arquivo.  <br/> |
|**Total de sessões de compartilhamento de arquivo ponto a ponto** <br/> |Não  <br/> |Número total de sessões ponto a ponto que incluem compartilhamento de aplicativos.  <br/> |
   

