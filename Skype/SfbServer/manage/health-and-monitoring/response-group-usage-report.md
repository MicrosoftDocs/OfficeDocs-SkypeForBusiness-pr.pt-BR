---
title: Relatório de Uso do Grupo de Resposta Skype for Business Server
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
ms.assetid: 3248b320-a552-400a-8485-6891af4eb0f3
description: 'Resumo: saiba mais sobre o aplicativo grupo de resposta no Skype for Business Server.'
ms.openlocfilehash: 59f1e32a27fb11d5557ec82adde4d84885028db7
ms.sourcegitcommit: 59d209ed669c13807e38196dd2a2c0a4127d3621
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/05/2022
ms.locfileid: "62386609"
---
# <a name="response-group-usage-report-in-skype-for-business-server"></a>Relatório de Uso do Grupo de Resposta Skype for Business Server

**Resumo:** Saiba mais sobre o aplicativo grupo de resposta Skype for Business Server.

O aplicativo grupo de resposta fornece uma maneira de Skype for Business Server atender e rotear chamadas telefônicas com base no número que foi discado e, opcionalmente, nas respostas do chamador a uma série de perguntas. Normalmente, as chamadas do Grupo de Resposta não são roteadas a uma única pessoa, mas, em vez disso, são roteadas a uma equipe de pessoas chamada de grupo de agentes. Por exemplo, se alguém chamar o número de telefone do seu help desk, Skype for Business Server pode roteá-la automaticamente para o primeiro agente de atendimento de ajuda disponível. Como alternativa, Skype for Business Server poderia fazer uma série de perguntas ("Pressione 1 se você estiver com problemas de hardware. Pressione 2 se estiver com problemas de software. Pressione 3 se você estiver com problemas de rede.") e encaminhe a chamada para o agente de atendimento de ajuda mais apropriado com base na resposta a essas perguntas.

O Relatório de Uso de Grupo de Resposta oferece uma visão detalhada do número de chamadas telefônicas recebidas por todos os fluxos de trabalho do Grupo de Resposta e decompõe essas chamadas em categorias mais restritas, como Chamadas oferecidas, Chamadas respondidas e Chamadas abandonadas.

A chave para trabalhar com o Relatório de Uso do Grupo de Resposta é entender a diferença entre os tipos de chamada reportados:

- **Chamadas recebidas**. Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta.

- **Chamadas bem-sucedidas**. Número total de chamadas que foram atendendo ao aplicativo grupo de resposta.

- **Chamadas oferecidas**. Número total de chamadas que foram transferidas ao um agente do Grupo de Resposta.

- **Chamadas atendidas**. Número total de chamadas que foram verdadeiramente atendidas por um agente do Grupo de Resposta.

- **Porcentagem de chamadas abandonadas**. Porcentagem de chamadas que foram recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente. Este valor é calculado subtraindo as chamadas atendidas pelas chamadas recebidas e, entãi, dividindo esse valor pelo número de chamadas recebidas. Por exemplo, se 10 chamadas foram recebidas e 7 foram atendidas, você deve subtrair 7 de 10, restando 3 chamadas não atendidas. Esse valor deve ser dividido por 10, resultando em uma porcentagem de 30% de chamadas abandonadas.

- **Chamadas transferidas**. Número total de chamadas do Grupo de Resposta que foram transferidas em virtude do tempo limite ou do excedente da fila.

Se estiver analisando o Relatório de uso de Grupo de Resposta e não se lembrar da definição de qualquer um desses tipos de chamada, basta manter o mouse sobre a etiqueta do tipo de chamada apropriado. Uma dica de ferramenta será exibida oferecendo uma breve descrição do tipo de chamada.

O Relatório de Uso do Grupo de Resposta permite que você filtre em um URI de fluxo de trabalho (o endereço SIP associado a esse fluxo de trabalho). No entanto, os próprios URIs de fluxo de trablho não são exibidos no relatório. Se quiser saber, por exemplo, quais fluxos de trabalho estão respondendo à maioria das chamadas ou quais estão recebendo a maioria das chamadas transferidas, clique na medida apropriada para abrir o Relatório de Lista de Chamadas do Grupo de Resposta para o período. Esse relatório lista os URIs de fluxo de trabalho.

## <a name="accessing-the-response-group-usage-report"></a>Acessando o Relatório de Uso do Grupo de Resposta

O Relatório de Uso do Grupo de Resposta é acessado pela home page Relatórios de Monitoramento. Você pode detalhar [o Relatório de](call-list-report.md) Lista de Chamada do Grupo de Resposta Skype for Business Server clicando em qualquer uma das seguintes métricas:

- Chamadas recebidas

- Chamadas bem-sucedidas

- Chamadas oferecidas

- Chamadas atendidas

- Chamadas transferidas

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>Fazendo o melho uso do Relatório de Uso do Grupo de Resposta

Um dos usos mais interessantes do Relatório de Uso do Grupo de Resposta podem não estar imediatamente aparente: a capacidade de recuperar informações de uso de um fluxo de trabalho individual do Grupo de Resposta.

> [!CAUTION]
> Um fluxo de trabalho do Grupo de Resposta é basicamente um conjunto de instruções que determina o Skype for Business Server faz quando um usuário disca um determinado número de telefone. Para isso, cada fluxo de trabalho é associado exclusivamente a um número de telefone. Quando alguém liga para o número, o fluxo de trabalho determina como a chamada será tratada. Por exemplo, o fluxo de trabalho pode fazer com que a chamada seja roteada a uma série de perguntas de resposta interativa de voz (IVR), que solicitam que o chamador especifique informações adicionais ("Pressione 1 para suporte de hardware. Pressione 2 para suporte de software"). Como alternativa, o fluxo de trabalho pode fazer com que a chamada seja colocada em uma fila e o chamador colocado em espera até que um agente esteja disponível para atender a chamada. A disponibilidade dos agentes para atender chamadas também é determinada pelo fluxo de trabalho: eles são usados para configurar as horas comerciais (os dias da semana e as horas do dia em que os agentes estão disponíveis para atender chamadas) e feriados (dias em que nenhum agente está disponível para atender chamadas). Sempre que você liga para um número de telefone que pertence ao aplicativo Grupo de Resposta, você está essencialmente ligando para um fluxo de trabalho do Grupo de Resposta. 

Embora os URIs de fluxo de trabalho não sejam exibidos no Relatório de Uso do Grupo de Resposta, ainda é possível exibir as estatísticas de uso de um fluxo de trabalho individual, algo que sempre é extremamente útil. Por exemplo, suponha que você tenha divulgado uma nova campanha publicitária e esteja curioso para saber se as pessoas estão ligando para se informar sobre o produto. Se o fluxo de trabalho do Grupo de Resposta tiver sido associado ao número de telefone dado na campanha publicitária, será possível verificar com facilidade quantas pessoas (se houverem) estão ligando para o número.

É possível também usar uma abordagem semelhante para medir o número de chamadas que estão sendo tratadas pelo suporte técnico interno ou pelo departamento de atendimento ao cliente.

Para revisar as estatísticas de uso de determinado fluxo de trabalho, insira o URI do fluxo de trabalho na caixa URI do Fluxo de Trabalho. Obviamente, como observado, os URIs do fluxo de trabalho (o endereço SIP associado a um fluxo de trabalho) não são exibidos no relatório. Isso significa que é preciso encontrar uma forma de determinar o URI de um fluxo de trabalho. Uma maneira de fazer isso é usar Windows PowerShell e o Shell de Gerenciamento Skype for Business Server. Por exemplo, este comando retorna todos os URIs de todos os fluxos de trabalho do Grupo de Resposta:

```PowerShell
Get-CsRgsWorkflow | Select-Object Name, PrimaryUri
```

Isso retornará dados semelhantes a estes:

<pre>
Name                            PrimaryUri
----                            ----------
Customer Support                sip:support@litwareinc.com
Help Desk                       sip:helpdesk@litwareinc.com
New Ad Campaign                 sip:newads@litwareinc.com
</pre>

Este comando retorna informações sobre um fluxo de trabalho individual, cujo nome é Nova campanha publicitária:

```PowerShell
Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri
```

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Uso do Grupo de Resposta permite que você veja os dados dos fluxos de trabalho de todos os seus Grupos de Resposta ou que veja os dados de um fluxo de trabalho individual. Também é possível escolher como os dados devem ser agrupados. Nesse caso, os usos são agrupados por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o Relatório de Uso do Grupo de Resposta.

**Filtros do Relatório de Uso do Grupo de Resposta**


| **Name**               | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **De** <br/>         | Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/>                                                                                                                              |
| **To** <br/>           | Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:  <br/> 7/7/2015 13:00  <br/> Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 7/3/2015  <br/> As semanas são sempre de domingo a sábado.  <br/>                                                                                                                                     |
| **Intervalo** <br/>     | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com uma data de início de 7/7/2015 e uma data de término de 28/02/2015, os dados serão exibidos para os dias 7/08/2015 12:00 a 7/09/2015 12:00 (ou seja, um total de 31 dias de dados). <br/> |
| **URI do Fluxo de Trabalho** <br/> | Permite que você limite os dados retornados para o fluxo de trabalho do Grupo de Resposta especificado. Para usar esse filtro, digite o endereço SIP do Fluxo de Trabalho. Por exemplo:  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

## <a name="metrics"></a>Métrica

A tabela a seguir lista as informações fornecidas no Relatório de Uso do Grupo de Resposta.

**Métricas do Relatório de Uso do Grupo de Resposta**

|**Name**|**É possível classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**A cada hora** <br/> **Diariamente** <br/> **Semanalmente** <br/> **Mensal** <br/> |Não  <br/> |Indica o intervalo de tempo selecionado. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se você estiver usando o intervalo Diário e clicar em 7/7/2015, verá uma divisão por hora da atividade de registro do usuário para essa data.  <br/> |
|**Chamadas recebidas** <br/> |Não  <br/> |Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta. Quando você clica nesse item, o relatório mostra o relatório de Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.  <br/> |
|**Chamadas Bem-sucedidas** <br/> |Não  <br/> |Número total de chamadas atendidas pelo aplicativo Grupo de Resposta. Quando você clica nesse item, o relatório mostra o relatório de Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.  <br/> |
|**Chamadas oferecidas** <br/> |Não  <br/> |Número total de chamadas transferidas para um agente do Grupo de Resposta. Quando você clica nesse item, o relatório mostra o relatório de Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.  <br/> |
|**Chamadas atendidas** <br/> |Não  <br/> |Número total de chamadas atendidas por um agente do Grupo de Resposta. Quando você clica nesse item, o relatório mostra o relatório de Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.  <br/> |
|**Porcentagem de chamadas abandonadas** <br/> |Não  <br/> |Número total de chamadas recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente. Isso é calculado subtraindo as Chamadas atendidas das Chamadas recebidas e dividindo esse valor pelo número de chamadas recebidas. Por exemplo, se você tiver 10 chamadas recebidas e sete respondidas, subtraia sete de 10, deixando três chamadas não respondidas. Esse valor seria dividido por 10, proporcionando uma porcentagem de chamadas abandonadas de 30%.  <br/> |
|**Duração média em minutos de chamada por representante** <br/> |Não  <br/> |Duração média que um agente do Grupo de Resposta gasta em uma chamada.  <br/> |
|**Chamadas transferidas** <br/> |Não  <br/> |Número total de chamadas do Grupo de Resposta transferidas devido a um tempo limite ou estouro de fila. Ao clicar nesse item, o relatório mostra o relatório Lista de Chamadas do Grupo de Resposta para o período selecionado.  <br/> |


