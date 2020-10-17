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
ms.openlocfilehash: 649fb55f6c7b698986c4c31057b3a0a8f1b00a76
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48511618"
---
# <a name="response-group-usage-report-in-lync-server-2013"></a>Relatório de uso do grupo de resposta no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-02-22_

O aplicativo grupo de resposta oferece uma maneira de o Microsoft Lync Server 2013 responder e rotear chamadas telefônicas com base no número que foi discado e, opcionalmente, nas respostas do chamador para uma série de perguntas. Normalmente, as chamadas do Grupo de Resposta não são roteadas a uma única pessoa, mas, em vez disso, são roteadas a uma equipe de pessoas chamada de grupo de agentes. Por exemplo, se alguém ligar para o número de telefone de seu suporte técnico, o Lync Server 2013 pode encaminhar automaticamente a chamada para o primeiro agente de suporte técnico disponível. Como alternativa, o Lync Server pode fazer uma série de perguntas ("Pressione 1 se estiver com problemas de hardware. Pressione 2 se estiver com problemas de software. Pressione 3 se você estiver tendo problemas de rede. ") e, em seguida, encaminhe a chamada para o agente de suporte técnico mais apropriado, com base na resposta a essas perguntas.

O Relatório de Uso de Grupo de Resposta oferece uma visão detalhada do número de chamadas telefônicas recebidas por todos os fluxos de trabalho do Grupo de Resposta e decompõe essas chamadas em categorias mais restritas, como Chamadas oferecidas, Chamadas respondidas e Chamadas abandonadas.

A chave para trabalhar com o Relatório de Uso do Grupo de Resposta é entender a diferença entre os tipos de chamada reportados:

  - **Chamadas recebidas**. Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta.

  - **Chamadas bem-sucedidas**. Número total de chamadas que foram escolhidas pelo aplicativo grupo de resposta.

  - **Chamadas oferecidas**. Número total de chamadas que foram transferidas ao um agente do Grupo de Resposta.

  - **Chamadas atendidas**. Número total de chamadas que foram verdadeiramente atendidas por um agente do Grupo de Resposta.

  - **Porcentagem de chamadas abandonadas**. Porcentagem de chamadas que foram recebidas pelo aplicativo Grupo de Resposta, mas que nunca foram atendidas por um agente. Este valor é calculado subtraindo as chamadas atendidas pelas chamadas recebidas e, entãi, dividindo esse valor pelo número de chamadas recebidas. Por exemplo, se 10 chamadas foram recebidas e 7 foram atendidas, você deve subtrair 7 de 10, restando 3 chamadas não atendidas. Esse valor deve ser dividido por 10, resultando em uma porcentagem de 30% de chamadas abandonadas.

  - **Chamadas transferidas**. Número total de chamadas do Grupo de Resposta que foram transferidas em virtude do tempo limite ou do excedente da fila.

Se estiver analisando o Relatório de uso de Grupo de Resposta e não se lembrar da definição de qualquer um desses tipos de chamada, basta manter o mouse sobre a etiqueta do tipo de chamada apropriado. Uma dica de ferramenta será exibida oferecendo uma breve descrição do tipo de chamada.

O Relatório de Uso do Grupo de Resposta permite que você filtre em um URI de fluxo de trabalho (o endereço SIP associado a esse fluxo de trabalho). No entanto, os próprios URIs de fluxo de trablho não são exibidos no relatório. Se quiser saber, por exemplo, quais fluxos de trabalho estão respondendo à maioria das chamadas ou quais estão recebendo a maioria das chamadas transferidas, clique na medida apropriada para abrir o Relatório de Lista de Chamadas do Grupo de Resposta para o período. Esse relatório lista os URIs de fluxo de trabalho.

<div>

## <a name="accessing-the-response-group-usage-report"></a>Acessando o Relatório de Uso do Grupo de Resposta

O Relatório de Uso do Grupo de Resposta é acessado pela home page Relatórios de Monitoramento. Você pode detalhar o [relatório de lista de chamadas de grupo de resposta no Lync Server 2013](lync-server-2013-response-group-call-list-report.md) clicando em qualquer uma das seguintes métricas:

  - Chamadas recebidas

  - Chamadas bem-sucedidas

  - Chamadas oferecidas

  - Chamadas atendidas

  - Chamadas transferidas

</div>

<div>

## <a name="making-the-best-use-of-the-response-group-usage-report"></a>Fazendo o melho uso do Relatório de Uso do Grupo de Resposta

Um dos usos mais interessantes do Relatório de Uso do Grupo de Resposta podem não estar imediatamente aparente: a capacidade de recuperar informações de uso de um fluxo de trabalho individual do Grupo de Resposta.

<div>


> [!WARNING]  
> Um fluxo de trabalho do grupo de resposta é basicamente um conjunto de instruções que determinam o que o Lync Server faz quando um usuário disca um número de telefone específico. Para isso, cada fluxo de trabalho é associado exclusivamente a um número de telefone. Quando alguém liga para o número, o fluxo de trabalho determina como a chamada será tratada. Por exemplo, o fluxo de trabalho pode fazer com que a chamada seja roteada a uma série de perguntas de resposta interativa de voz (IVR), que solicitam que o chamador especifique informações adicionais ("Pressione 1 para suporte de hardware. Pressione 2 para suporte de software"). Como alternativa, o fluxo de trabalho pode fazer com que a chamada seja colocada em uma fila e o chamador colocado em espera até que um agente esteja disponível para atender a chamada. A disponibilidade dos agentes para atender chamadas também é determinada pelo fluxo de trabalho: eles são usados para configurar as horas comerciais (os dias da semana e as horas do dia em que os agentes estão disponíveis para atender chamadas) e feriados (dias em que nenhum agente está disponível para atender chamadas). Sempre que você liga para um número de telefone que pertence ao aplicativo Grupo de Resposta, você está essencialmente ligando para um fluxo de trabalho do Grupo de Resposta.



</div>

Embora os URIs de fluxo de trabalho não sejam exibidos no Relatório de Uso do Grupo de Resposta, ainda é possível exibir as estatísticas de uso de um fluxo de trabalho individual, algo que sempre é extremamente útil. Por exemplo, suponha que você tenha divulgado uma nova campanha publicitária e esteja curioso para saber se as pessoas estão ligando para se informar sobre o produto. Se o fluxo de trabalho do Grupo de Resposta tiver sido associado ao número de telefone dado na campanha publicitária, será possível verificar com facilidade quantas pessoas (se houverem) estão ligando para o número.

É possível também usar uma abordagem semelhante para medir o número de chamadas que estão sendo tratadas pelo suporte técnico interno ou pelo departamento de atendimento ao cliente.

Para revisar as estatísticas de uso de determinado fluxo de trabalho, insira o URI do fluxo de trabalho na caixa URI do Fluxo de Trabalho. Obviamente, como observado, os URIs do fluxo de trabalho (o endereço SIP associado a um fluxo de trabalho) não são exibidos no relatório. Isso significa que é preciso encontrar uma forma de determinar o URI de um fluxo de trabalho. Uma maneira de fazer isso é usar o Windows PowerShell e o Shell de gerenciamento do Lync Server. Por exemplo, este comando retorna todos os URIs de todos os fluxos de trabalho do Grupo de Resposta:

    Get-CsRgsWorkflow | Select-Object Name, PrimaryUri

Isso retornará dados semelhantes a estes:

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
<td><p>Data/hora inicial para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora inicial como a seguir:</p>
<p>7/7/2012 13:00 horas</p>
<p>Se você não inserir uma hora inicial, o relatório começa automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas são sempre de domingo a sábado.</p></td>
</tr>
<tr class="even">
<td><p><strong>To</strong></p></td>
<td><p>Data/hora final para o intervalo de tempo. Para exibir os dados por hora, insira a data e hora final como a seguir:</p>
<p>7/7/2012 13:00 horas</p>
<p>Se você não inserir uma hora final, o relatório termina automaticamente as 12:00 AM no dia especificado. Para exibir os dados por dia, insira apenas a data:</p>
<p>7/7/2012</p>
<p>Para exibir por semana ou mês, insira uma data que está dentro da semana ou mês que deseja exibir (não é necessário inserir o primeiro dia da semana ou mês):</p>
<p>7/3/2012</p>
<p>As semanas são sempre de domingo a sábado.</p></td>
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
<p>Se as datas de início e término excederem o número máximo de valores permitidos para o intervalo selecionado, somente o número máximo de valores (a partir da data de início) será exibido. Por exemplo, se você selecionar o intervalo Diariamente com data de início em 7/7/12 e data de término de 28/2/12, os dados serão exibidos do dia 7/8/12, às 12:00, até o dia 7/9/12, às 12:00 (ou seja, um total de 31 dias de dados).</p></td>
</tr>
<tr class="even">
<td><p><strong>URI do Fluxo de Trabalho</strong></p></td>
<td><p>Permite que você limite os dados retornados para o fluxo de trabalho do Grupo de Resposta especificado. Para usar esse filtro, digite o endereço SIP do Fluxo de Trabalho. Por exemplo:</p>
<p>sip:helpdesk@litwareinc.com</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métrica

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
<th>É possível classificar este item?</th>
<th>Descrição</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>A cada hora</strong></p>
<p><strong>Diariamente</strong></p>
<p><strong>Semanalmente</strong></p>
<p><strong>Mensal</strong></p></td>
<td><p>Não</p></td>
<td><p>Indica o intervalo de tempo selecionado. Quando aplicável, é possível clicar em um determinado intervalo de tempo para exibir informações detalhadas desse intervalo. Por exemplo, se estiver usando o intervalo Diário e clicar em 7/7/12, você verá uma divisão por hora da atividade de registro do usuário para essa data.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chamadas recebidas</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas recebidas por todas as instâncias do aplicativo Grupo de Resposta. Quando você clica nesse item, o relatório mostra o relatório de Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chamadas Bem-sucedidas</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas atendidas pelo aplicativo Grupo de Resposta. Quando você clica nesse item, o relatório mostra o relatório de Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chamadas oferecidas </strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas transferidas para um agente do Grupo de Resposta. Quando você clica nesse item, o relatório mostra o relatório de Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chamadas atendidas</strong></p></td>
<td><p>Não</p></td>
<td><p>Número total de chamadas atendidas por um agente do Grupo de Resposta. Quando você clica nesse item, o relatório mostra o relatório de Lista de Chamadas do Grupo de Resposta para o período de tempo selecionado.</p></td>
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
<td><p>Número total de chamadas do Grupo de Resposta transferidas devido a um tempo limite ou estouro de fila. Ao clicar nesse item, o relatório mostra o relatório Lista de Chamadas do Grupo de Resposta para o período selecionado.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

