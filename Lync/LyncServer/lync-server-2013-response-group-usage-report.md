---
title: 'Lync Server 2013: relatório de uso do grupo de resposta'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Response Group Usage Report
ms:assetid: 3248b320-a552-400a-8485-6891af4eb0f3
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg558632(v=OCS.15)
ms:contentKeyID: 48183811
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 702ab291955ef7c8ec992e3607de581dff52b6a1
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41723591"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="response-group-usage-report-in-lync-server-2013"></a>Relatório de uso do grupo de resposta no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

O aplicativo grupo de resposta fornece uma maneira para que o Microsoft Lync Server 2013 atenda e encaminhe chamadas telefônicas com base no número que foi discado e, opcionalmente, nas respostas do chamador para uma série de perguntas. Geralmente, as chamadas do Grupo de Resposta não são encaminhadas a uma pessoa específica, mas sim para uma equipe de pessoas referida como grupo de agentes. Por exemplo, se alguém ligar para o número de telefone de seu suporte técnico, o Lync Server 2013 poderá direcionar automaticamente essa chamada para o primeiro agente de suporte técnico disponível. Ou, se preferir, o Lync Server pode fazer uma série de perguntas ("Pressione 1 se estiver com problemas de hardware). Pressione 2 se tiver problemas de software. Pressione 3 se você estiver tendo problemas de rede. ") e, em seguida, encaminhar a chamada para o agente de suporte técnico mais apropriado com base na resposta a essas perguntas.

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

<div>

## <a name="accessing-the-response-group-usage-report"></a>Acessando o Relatório de Uso do Grupo de Resposta

O Relatório de Uso do Grupo de Resposta é acessado pela home page Relatórios de Monitoramento. Você pode fazer uma busca detalhada no [relatório de lista de chamadas em grupo de resposta no Lync Server 2013](lync-server-2013-response-group-call-list-report.md) clicando em qualquer uma das seguintes métricas:

  - Chamadas recebidas

  - Chamadas bem-sucedidas

  - Chamadas oferecidas

  - Chamadas atendidas

  - Chamadas transferidas

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>Fazendo o melhor uso do Relatório de Uso do Grupo de Resposta

Um dos usos mais interessantes do Relatório de Uso do Grupo de Resposta pode não estar imediatamente aparente: a capacidade de recuperar informações de uso de um fluxo de trabalho individual do Grupo de Resposta.

<div>


> [!WARNING]  
> Um fluxo de trabalho de grupo de resposta é basicamente um conjunto de instruções que determina o que o Lync Server faz quando um usuário disca para um número de telefone específico. Para isso, cada fluxo de trabalho é associado exclusivamente a um número de telefone. Quando alguém liga para o número, o fluxo de trabalho determina como a chamada será tratada. Por exemplo, o fluxo de trabalho pode fazer com que a chamada seja roteada para uma série de perguntas de resposta interativa de voz (IVR), que solicitam que o chamador especifique informações adicionais ("Pressione 1 para suporte de hardware. Pressione 2 para suporte de software"). Como alternativa, o fluxo de trabalho pode fazer com que a chamada seja colocada em uma fila e o chamador colocado em espera até que um agente esteja disponível para atender a chamada. A disponibilidade dos agentes para atender chamadas também é determinada pelo fluxo de trabalho: eles são usados para configurar as horas comerciais (os dias da semana e as horas do dia em que os agentes estão disponíveis para atender chamadas) e feriados (dias em que nenhum agente está disponível para atender chamadas). Sempre que você liga para um número de telefone que pertence ao aplicativo Grupo de Resposta, você está essencialmente ligando para um fluxo de trabalho do Grupo de Resposta.



</div>

Embora os URIs de fluxo de trabalho não sejam exibidos no Relatório de Uso do Grupo de Resposta, ainda é possível exibir as estatísticas de uso de um fluxo de trabalho individual, algo que sempre é extremamente útil. Por exemplo, suponhamos que você tenha divulgado uma nova campanha publicitária e esteja curioso para saber se as pessoas estão ligando para se informar sobre o produto. Se o fluxo de trabalho do Grupo de Resposta tiver sido associado ao número de telefone dado na campanha publicitária, será possível verificar com facilidade quantas pessoas (se houverem) estão ligando para o número.

É possível também usar uma abordagem semelhante para medir o número de chamadas que estão sendo tratadas pelo suporte técnico interno ou pelo departamento de atendimento ao cliente.

Para revisar as estatísticas de uso de determinado fluxo de trabalho, insira o URI do fluxo de trabalho na caixa URI do Fluxo de Trabalho. Obviamente, como observado, os URIs do fluxo de trabalho (o endereço SIP associado a um fluxo de trabalho) não são exibidos no relatório. Isso significa que é preciso encontrar uma forma de determinar o URI de um fluxo de trabalho. Uma maneira de fazer isso é usar o Windows PowerShell e o Shell de gerenciamento do Lync Server. Por exemplo, este comando retorna todos os URIs de todos os fluxos de trabalho do Grupo de Resposta:

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

Isso retornará dados similares a esses:

    Name                            PrimaryUri
    ----                            ----------
    Customer Support                sip:support@litwareinc.com
    Help Desk                       sip:helpdesk@litwareinc.com
    New Ad Campaign                 sip:newads@litwareinc.com

Este comando retorna informações sobre um fluxo de trabalho individual, cujo nome é Nova campanha publicitária:

    Get-CsRgsWorkflow -Name "New Ad Campaign" | Select-Object Name, PrimaryUri

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros fornecem uma maneira de retornar um conjunto de dados mais direcionado ou de exibir os dados retornados de maneiras diferentes. Por exemplo, o Relatório de Uso do Grupo de Resposta permite que você veja os dados dos fluxos de trabalho de todos os seus Grupos de Resposta ou que veja os dados de um fluxo de trabalho individual. Também é possível escolher como os dados devem ser agrupados. Nesse caso, os usos são agrupados por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o Relatório de Uso do Grupo de Resposta.

### <a name="response-group-usage-report-filters"></a>Filtros do Relatório de Uso do Grupo de Resposta

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>De</strong></p></td>
<td><p>Data/hora de início para o intervalo de tempo. Para ver os dados por horas, insira a data e hora de início conforme segue:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se você não inserir a hora de início, o relatório começará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Até</strong></p></td>
<td><p>Data/hora final de intervalo de tempo. Para ver os dados por horas, insira a data e hora final conforme segue:</p>
<p>7/7/2012 1:00 PM</p>
<p>Se você não inserir a hora final, o relatório terminará automaticamente à meia-noite do dia especificado. Para ver os dados por dia, insira somente a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Intervalo</strong></p></td>
<td><p>Intervalo de tempo. Selecione uma das seguintes opções:</p>
<ul>
<li><p>Por hora (é possível exibir no máximo 25 horas)</p></li>
<li><p>Diariamente (é possível exibir no máximo 31 dias)</p></li>
<li><p>Semanalmente (é possível exibir no máximo 12 semanas)</p></li>
<li><p>Mensalmente (é possível exibir no máximo 12 meses)</p></li>
</ul>
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo diário com uma data de início de 7/7/2012 e uma data de término de 2/28/2012, os dados serão exibidos para os dias 8/7/2012 12:00 AM a 9/7/2012 12:00 AM (ou seja, um total de 31 dias da importância dos dados).</p></td>
</tr>
<tr class="even">
<td><p><strong>URI do Fluxo de Trabalho</strong></p></td>
<td><p>Permite limitar os dados retornados ao fluxo de trabalho do Grupo de Resposta especificado. Para usar esse filtro, insira o endereço SIP do Fluxo de Trabalho. Por exemplo:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Uso do Grupo de Resposta.

### <a name="response-group-usage-report-metrics"></a>Métricas do Relatório de Uso do Grupo de Resposta

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>Você pode classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Por hora</strong></p>
<p><strong>Diário</strong></p>
<p><strong>Semanal</strong></p>
<p><strong>Mensal</strong></p></td>
<td><p>Não</p></td>
<td><p>Indica o intervalo de tempo selecionado. Quando aplicável, você pode clicar em um dado intervalo de tempo para exibir informações detalhadas para aquele intervalo. Por exemplo, se você estiver usando o intervalo diário e clicar em 7/7/2012, verá um detalhamento por hora da atividade de registro do usuário para essa data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chamadas recebidas</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chamadas bem-sucedidas</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas atendidas pelo aplicativo Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chamadas oferecidas</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas transferidas para um agente do Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chamadas atendidas</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas atendidas por um agente do Grupo de Resposta. Quando você clica nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Porcentagem de chamadas abandonadas</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente. Isso é calculado subtraindo as Chamadas atendidas das Chamadas recebidas e dividindo esse valor pelo número de chamadas recebidas. Por exemplo, se você tiver 10 chamadas recebidas e sete respondidas, subtraia sete de 10, deixando três chamadas não respondidas. Esse valor seria dividido por 10, proporcionando uma porcentagem de chamadas abandonadas de 30%.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Duração média em minutos de chamada por representante</strong></p></td>
<td><p>Não</p></td>
<td><p>Duração média que um agente do Grupo de Resposta gasta em uma chamada.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chamadas transferidas</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas do Grupo de Resposta transferidas devido a um tempo limite ou excedente de fila. Ao clicar nesse item, o relatório mostra a Lista de Chamadas do Grupo de Resposta para o período selecionado.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

