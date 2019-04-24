---
title: Relatório de lista de chamada o grupo de resposta no Skype para Business Server
ms.reviewer: ''
ms.author: jambirk
author: jambirk
manager: serdars
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a2d3e08b-511b-4507-abba-8ff71aa27c8e
description: 'Resumo: Saiba mais sobre o aplicativo de grupo de resposta no Skype para Business Server.'
ms.openlocfilehash: 5fe2665a90d5a2122965dd89fdf58087d910de47
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32197952"
---
# <a name="response-group-call-list-report-in-skype-for-business-server"></a>Relatório de lista de chamada o grupo de resposta no Skype para Business Server

**Resumo:** Saiba mais sobre o aplicativo de grupo de resposta no Skype para Business Server.

Aplicativo grupo de resposta fornece uma maneira de Skype para Business Server atender e rotear as chamadas telefônicas com base no número discado e, opcionalmente, em que as respostas do chamador para uma série de perguntas. Geralmente, as chamadas do Grupo de Resposta não são encaminhadas a uma pessoa específica, mas sim para uma equipe de pessoas referida como grupo de agentes. Por exemplo, se alguém liga para o número de telefone para seu help desk, Skype para Business Server pode rotear automaticamente chamada ao primeiro operador mesa ajuda disponíveis. Como alternativa, Skype para Business Server pode pedir que uma série de perguntas ("Pressione 1 se você estiver tendo problemas de hardware. Pressione 2 se tiver problemas de software. Pressione 3 se você estiver tendo problemas de rede.") e, em seguida, rotear a chamada para o agente de mesa ajuda mais apropriada com base na responder a essas perguntas.

O Relatório da Lista de Chamadas de Grupo de Resposta representa uma coleção de chamadas feitas por um período específico de tempo e para um tipo específico de chamada. O Relatório de Uso do Grupo de Resposta (que deve ser aberto primeiro, antes de abrir o Relatório da Lista de Chamadas de Grupo de Resposta) reconhece os seguintes tipos de chamadas:

- **Chamadas recebidas**. Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta.

- **Chamadas bem-sucedidas**. Número total de chamadas atendidas pelo aplicativo Grupo de Resposta.

- **Chamadas oferecidas**. Número total de chamadas transferidas para um agente do Grupo de Resposta.

- **Chamadas atendidas**. Número total de chamadas atendidas por um agente do Grupo de Resposta.

- **Porcentagem de chamadas abandonadas.** Porcentagem de chamadas recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente. Esse valor é calculado subtraindo as Chamadas atendidas das Chamadas recebidas e dividindo esse valor pelo número de Chamadas recebidas. Por exemplo, se você receber 10 chamadas e 7 forem atendidas, subtraia 7 de 10, deixando 3 chamadas não atendidas. Esse valor seria dividido por 10, proporcionando uma porcentagem de chamadas abandonadas de 30%.

- **Chamadas transferidas**. Número total de chamadas do Grupo de Resposta transferidas devido a um tempo limite ou estouro de fila.

## <a name="accessing-the-response-group-call-list-report"></a>Como acessar o Relatório da Lista de Chamadas de Grupo de Resposta

O relatório de lista de chamadas grupo de resposta pode ser acessado apenas clicando em uma das seguintes métricas encontradas no [Response Group Usage Report no Skype para Business Server](response-group-usage-report.md):

- Chamadas recebidas

- Chamadas bem-sucedidas

- Chamadas oferecidas

- Chamadas atendidas

- Chamadas transferidas

## <a name="making-the-best-use-of-the-response-group-call-list-report"></a>Como usar o Relatório da Lista de Chamadas de Grupo de Resposta da melhor maneira possível

O Relatório da Lista de Chamadas de Grupo de Resposta permite que você limite os dados exibidos para chamadas que envolvem um fluxo de trabalho específico de Grupo de Resposta. Para fazer isso, você precisa inserir o URI do fluxo de trabalho (o endereço SIP do fluxo de trabalho) na caixa URI do Fluxo de Trabalho. Antes que você possa fazer isso, no entanto, é necessário realmente poder ver a caixa URI do Fluxo de Trabalho. Para exibir as opções de filtragem do Relatório da Lista de Chamadas de Grupo de Resposta, clique no botão Exibir/Ocultar Parâmetros, na parte superior esquerda da janela do relatório.

Observe que a Lista de Chamadas de Grupo de Resposta não exibe informações sobre o Código de resposta nem da ID do Diagnóstico se você manter o mouse sobre uma dessas métricas. Se você precisar de mais informações, você talvez Observe o código de resposta e/ou ID de diagnóstico e procure esses valores no [Relatório de falhas principais no Skype para Business Server](top-failures-report.md).

uma pergunta como esta: "Qual é o fluxo de trabalho individual que recebeu a maioria das chamadas?", é possível fazer o seguinte:

1. No Relatório de Uso do Grupo de Resposta, defina o período desejado de tempo e depois clique na métrica Chamadas Recebidas. Isso abrirá o Relatório da Lista de Chamadas de Grupo de Resposta.

2. Exporte os dados exibidos no Relatório da Lista de Chamadas de Grupo de Resposta. Por exemplo, você poderá exportar os dados em formato Microsoft Excel, e depois usar o Excel para converter esses dados a um arquivo de valores separados por vírgula.

3. Execute suas análises usando o Windows PowerShell.

Por exemplo, se você salvou os dados em um arquivo chamado C:\Data\Response_Group_Call_List_Report.csv, o seguinte comando pode ser usado para retornar o número total de chamadas recebidas para cada fluxo de trabalho listado no relatório:

```
$calls = Import-Csv -Path "C:\ Data\Response_Group_Call_List_Report.csv"
$calls | Group-Object Workflow | Select-Object Count, Name | Sort-Object Count -Descending
```

As informações serão similares a estas:

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

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. A tabela a seguir lista os filtros que podem ser usados com o Relatório da Lista de Chamadas de Grupo de Resposta.

**Filtros do Relatório da Lista de Chamadas de Grupo de Resposta**


| **Nome**               | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                        |
|:-----------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **De** <br/>         | Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/> |
| **Até** <br/>           | Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/>        |
| **URI do Fluxo de Trabalho** <br/> | Permite limitar os dados retornados ao fluxo de trabalho do Grupo de Resposta especificado. Para usar esse filtro, insira o endereço SIP do Fluxo de Trabalho. Por exemplo:  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                            |
| **Chamadas** <br/>        | Você pode selecionar um dos seguintes tipos de chamadas: <br/>  Chamadas Recebidas <br/>  Chamadas Bem-sucedidas <br/>  Chamadas Oferecidas <br/>  Chamadas Atendidas <br/>  Chamadas Transferidas <br/>                                                                                                                                                                                                                                                                                                                                                                                                |

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório da Lista de Chamadas de Grupo de Resposta para cada chamada recebida pelo aplicativo Grupo de Resposta.

**Métricas do Relatório da Lista de Chamadas de Grupo de Resposta**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Chamador** <br/> |Não  <br/> |Endereço SIP do chamador.  <br/> |
|**Fluxo de Trabalho** <br/> |Não  <br/> |Endereço SIP do fluxo de trabalho do Grupo de Resposta.  <br/> |
|**Hora de início** <br/> |Não  <br/> |Data e horário em que a chamada teve início.  <br/> |
|**Hora de término** <br/> |Não  <br/> |Data e horário em que a chamada terminou.  <br/> |
|**Código de resposta** <br/> |Não  <br/> |Código da resposta SIP enviado quando a sessão falhou.  <br/> |
|**ID do Diagnóstico** <br/> |Não  <br/> |Identificador exclusivo (na forma de cabeçalho ms-diagnostics) anexado a uma mensagem SIP que fornece informações úteis para solucionar erros.  <br/> |


