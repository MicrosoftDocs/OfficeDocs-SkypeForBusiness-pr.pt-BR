---
title: Relatório de uso do grupo de resposta no Skype for Business Server
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
ms.assetid: 3248b320-a552-400a-8485-6891af4eb0f3
description: 'Resumo: Saiba mais sobre o aplicativo de grupo de resposta no Skype for Business Server.'
ms.openlocfilehash: a8b70b2cafae7a8710d87e9a1cd2c28ae6e57ef1
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41817720"
---
# <a name="response-group-usage-report-in-skype-for-business-server"></a>Relatório de uso do grupo de resposta no Skype for Business Server

**Resumo:** Saiba mais sobre o aplicativo de grupo de resposta no Skype for Business Server.

O aplicativo grupo de resposta fornece uma maneira para que o Skype for Business Server atenda e encaminhe chamadas telefônicas com base no número que foi discado e, opcionalmente, nas respostas do chamador para uma série de perguntas. Geralmente, as chamadas do Grupo de Resposta não são encaminhadas a uma pessoa específica, mas sim para uma equipe de pessoas referida como grupo de agentes. Por exemplo, se alguém ligar para o número de telefone de seu suporte técnico, o Skype for Business Server poderá direcionar automaticamente essa chamada para o primeiro agente de suporte técnico disponível. Como alternativa, o Skype for Business Server poderia fazer uma série de perguntas ("Pressione 1 se estiver com problemas de hardware. Pressione 2 se tiver problemas de software. Pressione 3 se você estiver com problemas de rede. ") e, em seguida, encaminhe a chamada para o agente de suporte técnico mais apropriado com base na resposta a essas perguntas.

O Relatório de Uso de Grupo de Resposta oferece uma visão detalhada do número de chamadas telefônicas recebidas por todos os fluxos de trabalho do Grupo de Resposta e decompõe essas chamadas em categorias mais restritas, como Chamadas oferecidas, Chamadas respondidas e Chamadas abandonadas.

A chave para trabalhar com o Relatório de Uso do Grupo de Resposta é entender a diferença entre os tipos de chamada reportados:

- **Chamadas recebidas**. Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta.

- **Chamadas bem-sucedidas**. Número total de chamadas atendidas pelo aplicativo Grupo de Resposta.

- **Chamadas oferecidas**. Número total de chamadas transferidas para um agente do Grupo de Resposta.

- **Chamadas atendidas**. Número total de chamadas atendidas por um agente do Grupo de Resposta.

- **Porcentagem de chamadas abandonadas**. Porcentagem de chamadas que foram recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente. Esse valor é calculado subtraindo as chamadas atendidas pelas chamadas recebidas e, então, dividindo esse valor pelo número de chamadas recebidas. Por exemplo, se 10 chamadas foram recebidas e 7 foram atendidas, você deve subtrair 7 de 10, restando 3 chamadas não atendidas. Esse valor deve ser dividido por 10, resultando em uma porcentagem de 30% de chamadas abandonadas.

- **Chamadas transferidas**. Número total de chamadas do Grupo de Resposta transferidas devido a um tempo limite ou excedente de fila.

Se estiver analisando o Relatório de Uso de Grupo de Resposta e não se lembrar da definição de qualquer um desses tipos de chamada, basta manter o mouse sobre o rótulo apropriado do tipo de chamada. Uma dica de ferramenta será exibida oferecendo uma breve descrição do tipo de chamada.

O Relatório de Uso do Grupo de Resposta permite que você filtre em um URI de fluxo de trabalho (o endereço SIP associado a esse fluxo de trabalho). No entanto, os próprios URIs de fluxo de trabalho não são exibidos no relatório. Se quiser saber, por exemplo, quais fluxos de trabalho estão respondendo à maioria das chamadas ou quais estão recebendo a maioria das chamadas transferidas, clique na métrica apropriada para abrir o Relatório de Lista de Chamadas do Grupo de Resposta para o período. Esse relatório lista os URIs de fluxo de trabalho.

## <a name="accessing-the-response-group-usage-report"></a>Acessando o Relatório de Uso do Grupo de Resposta

O Relatório de Uso do Grupo de Resposta é acessado pela home page Relatórios de Monitoramento. Você pode fazer uma busca detalhada no [relatório de lista de chamadas em grupo de resposta no Skype for Business Server](call-list-report.md) clicando em qualquer uma das seguintes métricas:

- Chamadas recebidas

- Chamadas bem-sucedidas

- Chamadas oferecidas

- Chamadas atendidas

- Chamadas transferidas

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>Fazendo o melhor uso do Relatório de Uso do Grupo de Resposta

Um dos usos mais interessantes do Relatório de Uso do Grupo de Resposta pode não estar imediatamente aparente: a capacidade de recuperar informações de uso de um fluxo de trabalho individual do Grupo de Resposta.

> [!CAUTION]
> Um fluxo de trabalho de grupo de resposta é basicamente um conjunto de instruções que determina o que o Skype for Business Server faz quando um usuário disca para um número de telefone específico. Para isso, cada fluxo de trabalho é associado exclusivamente a um número de telefone. Quando alguém liga para o número, o fluxo de trabalho determina como a chamada será tratada. Por exemplo, o fluxo de trabalho pode fazer com que a chamada seja roteada para uma série de perguntas de resposta interativa de voz (IVR), que solicitam que o chamador especifique informações adicionais ("Pressione 1 para suporte de hardware. Pressione 2 para suporte de software"). Como alternativa, o fluxo de trabalho pode fazer com que a chamada seja colocada em uma fila e o chamador colocado em espera até que um agente esteja disponível para atender a chamada. A disponibilidade dos agentes para atender chamadas também é determinada pelo fluxo de trabalho: eles são usados para configurar as horas comerciais (os dias da semana e as horas do dia em que os agentes estão disponíveis para atender chamadas) e feriados (dias em que nenhum agente está disponível para atender chamadas). Sempre que você liga para um número de telefone que pertence ao aplicativo Grupo de Resposta, você está essencialmente ligando para um fluxo de trabalho do Grupo de Resposta. 

Embora os URIs de fluxo de trabalho não sejam exibidos no Relatório de Uso do Grupo de Resposta, ainda é possível exibir as estatísticas de uso de um fluxo de trabalho individual, algo que sempre é extremamente útil. Por exemplo, suponhamos que você tenha divulgado uma nova campanha publicitária e esteja curioso para saber se as pessoas estão ligando para se informar sobre o produto. Se o fluxo de trabalho do Grupo de Resposta tiver sido associado ao número de telefone dado na campanha publicitária, será possível verificar com facilidade quantas pessoas (se houverem) estão ligando para o número.

É possível também usar uma abordagem semelhante para medir o número de chamadas que estão sendo tratadas pelo suporte técnico interno ou pelo departamento de atendimento ao cliente.

Para revisar as estatísticas de uso de determinado fluxo de trabalho, insira o URI do fluxo de trabalho na caixa URI do Fluxo de Trabalho. Obviamente, como observado, os URIs do fluxo de trabalho (o endereço SIP associado a um fluxo de trabalho) não são exibidos no relatório. Isso significa que é preciso encontrar uma forma de determinar o URI de um fluxo de trabalho. Uma maneira de fazer isso é usar o Windows PowerShell e o Shell de gerenciamento do Skype for Business Server. Por exemplo, este comando retorna todos os URIs de todos os fluxos de trabalho do Grupo de Resposta:

```PowerShell
Get-CsRgsWorkflow | Select-Object Name, PrimaryUri
```

Isso retornará dados similares a esses:

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


| **Nome**               | **Descrição**                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                     |
|:-----------------------|:----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **De** <br/>         | Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/>                                                                                                                              |
| **Até** <br/>           | Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:  <br/> 7/7/2015 13:00  <br/> Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:  <br/> 7/7/2015  <br/> Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):  <br/> 3/7/2015  <br/> As semanas sempre vão de domingo a sábado.  <br/>                                                                                                                                     |
| **Intervalo** <br/>     | Intervalo de tempo. Selecione uma das seguintes opções: <br/>  Por hora (é possível exibir no máximo 25 horas) <br/>  Diariamente (é possível exibir no máximo 31 dias) <br/>  Semanalmente (é possível exibir no máximo 12 semanas) <br/>  Mensalmente (é possível exibir no máximo 12 meses) <br/>  Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diário com a data de início 7/7/2015 e a data de término 28/2/2015, os dados serão exibidos para os dias de 7/8/2015 00:00 a 7/9/2012 00:00 (ou seja, um total de 31 dias de dados). <br/> |
| **URI do Fluxo de trabalho** <br/> | Permite limitar os dados retornados ao fluxo de trabalho do Grupo de Resposta especificado. Para usar esse filtro, insira o endereço SIP do Fluxo de Trabalho. Por exemplo:  <br/> sip:helpdesk@litwareinc.com  <br/>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                         |

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Uso do Grupo de Resposta.

**Métricas do Relatório de Uso do Grupo de Resposta**

|**Nome**|**Você pode classificar este item?**|**Descrição**|
|:-----|:-----|:-----|
|**Por hora** <br/> **Diário** <br/> **Semanal** <br/> **Mensal** <br/> |Não  <br/> |Indica o intervalo de tempo selecionado. Quando aplicável, você pode clicar em um dado intervalo de tempo para exibir informações detalhadas para aquele intervalo. Por exemplo, se estiver usando um intervalo por dia e clicar em 7/7/2015, você verá uma divisão por hora das atividades de registro do usuário para aquela data.  <br/> |
|**Chamadas recebidas** <br/> |Não  <br/> |Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.  <br/> |
|**Chamadas bem-sucedidas** <br/> |Não  <br/> |Número total de chamadas atendidas pelo aplicativo Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.  <br/> |
|**Chamadas oferecidas** <br/> |Não  <br/> |Número total de chamadas transferidas para um agente do Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.  <br/> |
|**Chamadas atendidas** <br/> |Não  <br/> |Número total de chamadas atendidas por um agente do Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.  <br/> |
|**Porcentagem de chamadas abandonadas** <br/> |Não  <br/> |Número total de chamadas recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente. Isso é calculado subtraindo as Chamadas atendidas das Chamadas recebidas e dividindo esse valor pelo número de chamadas recebidas. Por exemplo, se você tiver 10 chamadas recebidas e sete respondidas, subtraia sete de 10, deixando três chamadas não respondidas. Esse valor seria dividido por 10, proporcionando uma porcentagem de chamadas abandonadas de 30%.  <br/> |
|**Duração média em minutos de chamada por representante** <br/> |Não  <br/> |Duração média que um agente do Grupo de Resposta gasta em uma chamada.  <br/> |
|**Chamadas transferidas** <br/> |Não  <br/> |Número total de chamadas do Grupo de Resposta transferidas devido a um tempo limite ou excedente de fila. Ao clicar nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período selecionado.  <br/> |


