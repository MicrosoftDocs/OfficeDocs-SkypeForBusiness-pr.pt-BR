---
title: O Relatório de Distribuição de Métricas de Qualidade de Mídia no Skype for Business Server
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
ms.assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
description: 'Resumo: saiba mais sobre o Relatório de Distribuição de Métricas de Qualidade de Mídia Skype for Business Server.'
ms.openlocfilehash: 745f88a6943d9d369a104bf4bc42ffaa68138811
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62409964"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>O Relatório de Distribuição de Métricas de Qualidade de Mídia no Skype for Business Server 
 
**Resumo:** Saiba mais sobre o Relatório de Distribuição de Métricas de Qualidade de Mídia Skype for Business Server.
  
O Relatório de Distribuição da Métrica de Qualidade de Mídia permite ver um gráfico que mostra os valores de distribuição para a métrica Qualidade da Experiência como jitter ou perda do pacote. Por exemplo, suponha que seus usuários fazem um total de 10 ligações telefônicas; estas 10 chamadas relatam os seguintes tempos de ida e volta:
  
|**Número da chamada**|**Hora da viagem de ida e volta (milissegundos)**|
|:-----|:-----|
|1  <br/> |50  <br/> |
|2  <br/> |50  <br/> |
|3  <br/> |50  <br/> |
|4  <br/> |50  <br/> |
|5  <br/> |50  <br/> |
|6   <br/> |50  <br/> |
|7   <br/> |50  <br/> |
|8   <br/> |4550  <br/> |
|9   <br/> |50  <br/> |
|10   <br/> |50  <br/> |
   
A média para esses horários de ida e volta é de 500 milissegundos (5.000 divididos por 10). Quinhentos milissegundos é um tempo de viagem de ida e volta extremamente grande; como resultado, você pode acreditar que tem um problema sério com o congestionamento de rede. (Os tempos de ida e volta longos geralmente são o resultado de redes sobrecarregadas.)
  
Na realidade, claro,, 90% das suas chamadas possuem excelentes tempos de ida e volta; você mal tinha uma chamada em seus resultados gerais. Se você só olhar para o tempo médio de viagem de ida e volta, poderá chegar a uma conclusão muito errada.
  
O Relatório de Distribuição da Métrica de Qualidade de Mídia ajuda a evitar conclusões incorretas mostrando uma distribuição gráfica de uma métrica especificada (como o tempo de ida e volta). Estes gráficos ajudam a tornar claro que você possui nova chamadas muito boas e uma muito ruim. Você ainda pode desejar investigar mais que uma chamada. No entanto, o fato que 9 de 10 chamadas foram muito boas sugere que não há motivo para fazer qualquer mudança radical em sua rede, pelo menos não neste momento.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que você pode usar com o Relatório de Distribuição da Métrica de Qualidade de Mídia.
  
**Filtros do Relatório de Distribuição da Métrica de Qualidade de Mídia**

|**Name**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**To** <br/> |Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
|**Mínimo no eixo x** <br/> |Menor valor para ser exibido no eixo X do gráfico.  <br/> |
|**Máximo no eixo x** <br/> |Maior valor para ser exibido no eixo X do gráfico.  <br/> |
|**Tipo de acesso** <br/> | Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  Interno <br/>  Externo <br/> |
|**VPN** <br/> | Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  VPN <br/>  Não VPN <br/> |
|**Tipo de rede** <br/> | Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  Com fio <br/>  Sem fio <br/> |
   

