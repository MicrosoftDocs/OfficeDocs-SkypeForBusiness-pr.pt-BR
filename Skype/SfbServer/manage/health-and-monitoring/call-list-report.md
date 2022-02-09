---
title: Relatório de Lista de Chamada do Grupo de Resposta no Skype for Business Server
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
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: 'Resumo: saiba mais sobre o aplicativo grupo de resposta no Skype for Business Server.'
ms.openlocfilehash: 8f86e71606f09d5f2313578ef0ab90dfd20c654d
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62398935"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a>Relatório de Lista de Chamada do Grupo de Resposta no Skype for Business Server

**Resumo:** Saiba mais sobre o aplicativo grupo de resposta Skype for Business Server.

O aplicativo grupo de resposta fornece uma maneira de Skype for Business Server atender e rotear chamadas telefônicas com base no número que foi discado e, opcionalmente, nas respostas do chamador a uma série de perguntas. Normalmente, as chamadas do Grupo de Resposta não são roteadas a uma única pessoa, mas, em vez disso, são roteadas a uma equipe de pessoas chamada de grupo de agentes. Por exemplo, se alguém chamar o número de telefone do seu help desk, Skype for Business Server pode roteá-la automaticamente para o primeiro agente de atendimento de ajuda disponível. Como alternativa, Skype for Business Server poderia fazer uma série de perguntas ("Pressione 1 se você estiver com problemas de hardware. Pressione 2 se estiver com problemas de software. Pressione 3 se você estiver com problemas de rede.") e, em seguida, rotee a chamada para o agente de atendimento de ajuda mais apropriado com base na resposta a essas perguntas.

O Relatório de lista de chamadas do grupo de resposta representa uma coleção de chamadas feitas por um período específico de tempo e para um tipo específico de chamada. O Relatório de uso de grupo de resposta (que deve ser aberto primeiro, antes de abrir o Relatório de lista de chamadas do grupo de resposta) reconhece os seguintes tipos de chamadas:

- **Chamadas recebidas**. Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta.

- **Chamadas bem-sucedidas**. Número total de chamadas que foram atendendo ao aplicativo grupo de resposta.

- **Chamadas oferecidas**. Número total de chamadas que foram transferidas ao um agente do Grupo de Resposta.

- **Chamadas atendidas**. Número total de chamadas que foram verdadeiramente atendidas por um agente do Grupo de Resposta.

- **Porcentagem de chamadas abandonadas.** Porcentagem de chamadas que foram recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente. Este valor é calculado subtraindo as chamadas atendidas pelas chamadas recebidas e, entãi, dividindo esse valor pelo número de chamadas recebidas. Por exemplo, se 10 chamadas foram recebidas e 7 foram atendidas, você deve subtrair 7 de 10, restando 3 chamadas não atendidas. Esse valor seria dividido por 10, proporcionando uma porcentagem de chamadas abandonadas de 30%.

- **Chamadas transferidas**. Número total de chamadas do Grupo de Resposta transferidas devido a um tempo limite ou estouro de fila.

## <a name="accessing-the-response-group-call-list-report"></a>Como acessar o Relatório de Lista de Chamadas de Grupo de Resposta

O Relatório de Lista de Chamada do Grupo de Resposta só pode ser acessado clicando em uma das seguintes métricas encontradas no Relatório de Uso do Grupo de Resposta [no Skype for Business Server](response-group-usage-report.md):

- Chamadas recebidas

- Chamadas bem-sucedidas

- Chamadas oferecidas

- Chamadas atendidas

- Chamadas transferidas

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Como usar melhor o Relatório de Lista de Chamadas de Grupo de Resposta

O Relatório de Lista de Chamadas de Grupo de Resposta permite que você limite os dados exibidos para chamadas que envolvem um fluxo de trabalho específico de Grupo de Resposta. Para fazer isso, você precisa inserir o URI do fluxo de trabalho (o endereço SIP do fluxo de trabalho) na caixa do URI do fluxo de trabalho. Antes que você possa fazer isso, no entanto, é necessário realmente poder ver a caixa do URI do fluxo de trabalho. Para exibir as opções de filtragem do Relatório de Lista de Chamadas de Grupo de Resposta, clique no botão Exibir/Ocultar Parâmetros, na parte superior esquerda da janela do relatório.

Observe que a lista de chamadas do grupo de resposta não exibe informações sobre o código de Resposta nem do ID do Diagnóstico se você manter o mouse sobre uma dessas métricas. Se precisar de mais informações, você poderá observar o código de resposta e/ou a ID de Diagnóstico e, em seguida, pesquisar esses valores no Relatório de Principais Falhas [no Skype for Business Server](top-failures-report.md).

uma pergunta como esta: "Qual é o fluxo de trabalho individual que recebeu a maioria das chamadas?", é possível fazer o seguinte:

1. No Relatório de uso do grupo de resposta, defina o período desejado de tempo e depois clique na métrica Chamadas Recebidas. Isso abrirá o Relatório de lista de chamadas do grupo de resposta.

2. Exporte os dados exibidos no Relatório de lista de chamadas do grupo de resposta. Por exemplo, você poderá exportar os dados em formato Microsoft Excel, e depois usar o Excel para converter esses dados a um arquivo de valores separados por vírgula.

3. Execute suas análises usando o Windows PowerShell.

Por exemplo, se você salvou os dados para um arquivo chamado C:\Data\Response_Group_Call_List_Report.csv, você pode depois usar o seguinte comando para retornar o número total de chamadas recebidas para cada fluxo de trabalho listado no relatório:

```PowerShell
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

As informações serão similares a essas:

<pre>
Count    Name
-----    ----
  160    Redmond Help Desk
   47    Dublin Help Desk
   31    North America Customer Support
   16    EMEA Customer Support
   14    Employment Opportunities
</pre>

## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. A tabela a seguir lista os filtros que podem ser usados com o Relatório de Lista de Chamadas de Grupo de Resposta.

**Filtros do Relatório de Lista de Chamadas de Grupo de Respostas**


| **Name**               | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **De** <br/>         | Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/> |
| **To** <br/>           | Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/>        |
| **URI do Fluxo de trabalho** <br/> | Permite que você limite os dados retornados para o fluxo de trabalho do Grupo de Resposta especificado. Para usar esse filtro, digite o endereço SIP do Fluxo de Trabalho. Por exemplo:  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| **Chamadas** <br/>        | Você pode selecionar um dos seguintes tipos de chamadas: <br/>  Chamadas Recebidas <br/>  Chamadas com Êxito <br/>  Chamadas Oferecidas <br/>  Chamadas Atendidas <br/>  Chamadas Transferidas <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Lisa de Chamadas de Grupo de Resposta para cada chamada recebida pelo aplicativo do Grupo de Resposta.

**Métricas do Relatório de Lista de Chamadas de Grupo de Resposta**

|**Name**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Caller** <br/> |Não  <br/> |Endereço SIP do chamador.  <br/> |
|**Fluxo de trabalho** <br/> |Não  <br/> |Endereço SIP do fluxo de trabalho do Grupo de Resposta.  <br/> |
|**Horário de início** <br/> |Não  <br/> |Data e horário em que a chamada teve início.  <br/> |
|**Horário de término** <br/> |Não  <br/> |Data e horário em que a chamada terminou.  <br/> |
|**Código da resposta** <br/> |Não  <br/> |Código da resposta SIP enviado quando a sessão falhou.  <br/> |
|**ID do Diagnóstico** <br/> |Não  <br/> |Identificador único (na forma de um cabeçalho ms-diagnostics) anexado a uma mensagem SIP que geralmente fornece informações úteis para solucionar erros.  <br/> |


