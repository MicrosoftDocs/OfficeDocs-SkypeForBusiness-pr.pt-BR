---
title: O Media Quality métricas distribuição Report no Skype para Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d07996e6-b0a5-4ff8-9512-ab707762b4e2
description: 'Resumo: Saiba mais sobre o Media Quality métricas distribuição Report no Skype para Business Server.'
ms.openlocfilehash: 65fc10e1adaa32c2538f49d7c41fe6ee45a51c1b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33902268"
---
# <a name="the-media-quality-metrics-distribution-report-in-skype-for-business-server"></a>O Media Quality métricas distribuição Report no Skype para Business Server 
 
**Resumo:** Saiba mais sobre o Media Quality métricas distribuição Report no Skype para Business Server.
  
O Relatório de Distribuição da Métrica de Qualidade de Mídia permite ver um gráfico que mostra os valores de distribuição para a métrica Qualidade da Experiência, como tremulação ou perda de pacotes. Por exemplo, suponha que seus usuários fazem um total de 10 ligações telefônicas; essas 10 chamadas relatam os seguintes tempos de ida e volta:
  
|**Número da chamada**|**Tempo de viagem de ida e volta (milissegundos)**|
|:-----|:-----|
|1  <br/> |50  <br/> |
|2  <br/> |50  <br/> |
|3  <br/> |50  <br/> |
|4  <br/> |50  <br/> |
|5  <br/> |50  <br/> |
|6  <br/> |50  <br/> |
|7  <br/> |50  <br/> |
|8  <br/> |4550  <br/> |
|9  <br/> |50  <br/> |
|10  <br/> |50  <br/> |
   
A média para esses tempos de ida e volta é de 500 milissegundos (5000 dividido por 10). Quinhentos milissegundos é um tempo de ida e volta extremamente grande; como resultado, você pode achar que tem um grave problema com congestionamento de rede. (Tempo de ida e volta longo geralmente é resultado de redes sobrecarregadas.)
  
Na realidade, claro, 90% das suas chamadas têm excelentes tempos de ida e volta; você teve uma única chamada ruim que distorceu os resultados gerais. Se procurar pelo tempo de ida e volta médio, pode chegar a uma conclusão errada.
  
O Relatório de Distribuição da Métrica de Qualidade de Mídia ajuda a evitar conclusões incorretas mostrando uma distribuição gráfica de uma métrica especificada (como o tempo de ida e volta). Estes gráficos ajudam a deixar claro que você teve nove chamadas muito boas e uma muito ruim. Você ainda pode desejar investigar melhor essa chamada. No entanto, o fato de 9 entre 10 chamadas terem sido muito boas sugere que não há motivo para fazer qualquer mudança radical em sua rede, pelo menos não neste momento.
  
## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionadas ou para exibir os dados retornados de diferentes maneiras. A tabela a seguir lista os filtros que você pode usar com o Relatório de Distribuição da Métrica de Qualidade de Mídia.
  
**Filtros do Relatório de Distribuição da Métrica de Qualidade de Mídia**

|**Nome**|**Descrição**|
|:-----|:-----|
|**De** <br/> |Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Até** <br/> |Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
|**Mínimo no eixo x** <br/> |Menor valor para ser exibido no eixo X do gráfico.  <br/> |
|**Máximo no eixo x** <br/> |Maior valor para ser exibido no eixo X do gráfico.  <br/> |
|**Tipo de acesso** <br/> | Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  Interno <br/>  Externo <br/> |
|**VPN** <br/> | Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  VPN <br/>  Não VPN <br/> |
|**Tipo de rede** <br/> | Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes: <br/>  [Todos] <br/>  Com fio <br/>  Sem fio <br/> |
   

