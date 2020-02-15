---
title: 'Lync Server 2013: relatório de inventário de telefones IP'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IP Phone Inventory Report
ms:assetid: aa7d6b31-cb09-4e68-b020-aa5dd0081c20
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615027(v=OCS.15)
ms:contentKeyID: 48185044
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0c99945626105282324202d1fd754cd5d966bc81
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42035093"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="ip-phone-inventory-report-in-lync-server-2013"></a>Relatório de inventário de telefone IP no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-12_

O Relatório de inventário de telefones IP relata informações sobre os telefones IP em uso no momento em sua organização. O Relatório de inventário de telefones IP fornece uma lista detalhada de telefones IP que foram usados durante o período de relatório especificado. Entre outras coisas, esse relatório permite que os administradores saibam se há algum telefone velho e desatualizado em uso que deveria ser substituído; ele também alerta os administradores para o fato de que há telefones caros na organização, que raramente são usados. Esse tipo de informação pode ser inestimável quando se trata de comprar novos telefones ou redistribuir os existentes. (Por exemplo, um usuário que raramente usa seu telefone caro pode pedir para trocar com um usuário que usa seu telefone com muito mais frequência).

Deve-se observar que esse relatório tem algumas limitações quando se trata de ser usado como um relatório de inventário verdadeiro. Por um motivo, o relatório de telefone IP simplesmente lista todos os telefones que fizeram logon no Lync Server durante o período de tempo especificado, classificados pelo último horário de logon. Se um telefone não fizer logon durante o período de tempo especificado, então ele não será listado no relatório de inventário. Isso inclui telefones que fizeram logon antes do período de tempo iniciar e que ainda estavam logados durante esse intervalo especificado. Por exemplo, suponha que você queira examinar todo o inventário de telefones de julho de 2012. Imagine, também, que vários telefones estejam conectados ao Lync Server em 30 de junho de 2012 e ainda estavam conectados a partir de 1º de julho. Esses telefones não serão exibidos no relatório de inventário do dia 1º de julho.

É também importante observar que o relatório de inventário pode incluir telefones que sua organização não usa mais. Por exemplo, suponha uma série de telefones da Fabrikam logados no sistema no dia 1 de julho de 2012; 5 dias mais tarde sua organização decide se livrar de todos esses telefones da Fabrikam e substituí-los por um novo modelo Contoso. Os telefones da Fabrikam ainda aparecerão no relatório de "inventário" simplesmente porque eles estavam logados no sistema durante o mês de julho.

Além disso, o Relatório de inventário de telefones IP não relata totais resumidos de diferentes tipos de telefones. Por exemplo, suponha que você tenha 105 telefones Polycom CX600. O relatório não dirá que você tem 105 desses telefones; em vez disso, ele simplesmente vê 105 entidades separadas do Polycom CX600. A unica maneira de saber que há 105 entradas do Polycom Cx600 seria contar cada uma dessas entradas manualmente.

<div>


> [!WARNING]  
> Ou exportar os dados e usar o Microsoft Excel ou Windows PowerShell para fazer essa contagem.



</div>

<div>

## <a name="accessing-the-ip-phone-inventory-report"></a>Como acessar o Relatório de inventário de telefones IP

O Relatório de inventário de telefones IP é acessado a partir da página inicial dos Relatórios de Monitoramento. Se você clicar na métrica URI do Usuário, você pode acessar o Relatório de atividades do usuário desse usuário. Clicar na métrica Última atividade para uma chamada ponto a ponto levará você ao Relatório de detalhes de sessão ponto a ponto; clicar na mesma métrica de uma conferência levará ao Relatório de detalhes de conferência.

</div>

<div>

## <a name="making-the-best-use-of-the-ip-phone-inventory-report"></a>Como usar melhor o Relatório de inventário de telefones IP

Se você estiver interessado apenas em informações de uso de um determinado tipo de telefone (por exemplo, "com que frequência os usuários usam um telefone Polycom CX600?"), você pode obter essas informações diretamente do relatório de inventário de telefone IP filtrando esse tipo específico de telefone. No entanto, se você deseja informações resumidas para todos os seus telefones (quantas pessoas estão usando um CX600 Polycom, quantos estão usando um LG-Nortel IP8540, etc.), será necessário exportar os dados e usar outro aplicativo (como o Windows PowerShell) para fazer esse tipo de analisa. Por exemplo, suponha que você exportou os dados para um arquivo de valores separados por\\vírgula\\(\_C\_:\_data IP Phone Inventory Report. csv). Nesse caso, você poderia usar esses dois comandos para fornecer dados de resumo para todos os telefones:

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones |Group-Object Manufacturer, "Hardware version" | Select-Object Count, Name | Sort-Object Count -Descending

Que retornará dados similares a esses:

    Count    Name
    -----    ----
      267    POLYCOM, CX700
      267    POLYCOM, CX600
      166    POLYCOM, C
       68    Microsoft, CPE
       64    LG-Nortel, IP8540
       59    Aastra, 6725ip
       37    LG-Nortel, IP
       22    POLYCOM, CX3000
       11    Microsoft, CPE_A
        9    POLYCOM, CX500
        7    Aastra, 6721ip

Similarmente, esses dois comandos dizem quais telefones fizeram logon no sistema, mas nunca foram realmente usados para fazer uma chamada (o valor da métrica Última atividade está em branco, indicando que nunca houve nenhuma última atividade):

    $phones = Import-Csv "C:\Data\IP_Phone_Inventory_Report.csv"
    $phones | Where-Object {$_."Last activity" -eq ""}

Isso retorna dados similares a esses para cada telefone que não foi usado:

    Manufacturer     : POLYCOM
    Hardware version : CX600
    MAC address      : 00-04-F2-00-01-76
    User URI         : 422
    User agent       : CPE/4.0.7423.1 OCPhone/4.0.7423.1 (Microsoft Lync 2010 (Beta) Phone Edition)
    Last logon time  : 8/30/2010 4:44:48 PM
    Last logoff time : 8/30/2010 5:59:07 PM
    Last activity    :

Outra maneira interessante de usar o Relatório de inventário de telefones IP é esse: se você tiver o endereço MAC de um telefone IP, você poderá descobrir o usuário que usou o telefone por último, simplesmente inserindo esse endereço na caixa de texto do endereço MAC. O Relatório de inventário de telefones IP irá então relatar de volta (entre outras coisas) o endereço SIP do usuário que fez o logon por último com esse telefone. Como alternativa, você pode inserir o endereço SIP do usuário (na caixa de prefixo do URI do usuário) para descobrir todos os telefones que foram usados por esse usuário.

</div>

<div>

## <a name="filters"></a>Filtros

Filtros fornecem uma forma de retornar um conjunto de dados mais focado ou exibir os dados retornados de diferentes formas. Por exemplo, o Inventário de Telefones IP permite exibir somente os telefones fabricados por uma empresa específica ou até mesmo uma versão específica desses telefones. Você também pode escolher como os dados serão agrupados. Neste caso, os registros são agrupados por hora, dia, semana ou mês.

A tabela seguir lista os filtros que podem ser usados com o Relatório de Inventário de Telefones IP.

### <a name="ip-phone-inventory-report-filters"></a>Filtros do Relatório de Inventário de Telefones IP

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
<p>As semanas sempre vão de domingo a sábado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Fabricantes</strong></p></td>
<td><p>Nome da empresa que fabricou o telefone IP. Os valores para este filtro são preenchidos automaticamente, com base nos telefones IP que estão atualmente no banco de dados.</p></td>
</tr>
<tr class="even">
<td><p><strong>Versão do hardware</strong></p></td>
<td><p>Número da versão to telefone IP; usando os filtros Fabricante e Versão do hardware, é possível identificar de forma única um tipo em particular de telefone. Os valores para este filtro são preenchidos automaticamente com base nos telefones IP que estão atualmente no banco de dados.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente de usuário</strong></p></td>
<td><p>Identificador do software usado pelo telefone IP. Os valores para este filtro são preenchidos automaticamente com base nos telefones IP que estão atualmente no banco de dados.</p></td>
</tr>
<tr class="even">
<td><p><strong>Endereço MAC</strong></p></td>
<td><p>Identificador único da interface de rede no telefone IP. O endereço de Controle de Acesso de Mídia (MAC) normalmente é atribuído no momento em que o telefone é fabricado e está programado no hardware do dispositivo.</p>
<p>Para pesquisar registros pertencentes a um endereço MAC específico, simplesmente insira o endereço. Por exemplo:</p>
<p>00-08-5D-16-16-48</p>
<p>Você deve inserir o endereço completo. Um endereço parcial (por exemplo, 00-08-5D) não retorna dados.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Dias antes da última atividade</strong></p></td>
<td><p>Selecione um dos seguintes valores:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>10 </p></li>
<li><p>508</p></li>
<li><p>até</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p><strong>Dias antes da hora do último logoff:</strong></p></td>
<td><p>Selecione um dos seguintes valores:</p>
<ul>
<li><p>Todos os</p></li>
<li><p>10 </p></li>
<li><p>508</p></li>
<li><p>até</p></li>
</ul></td>
</tr>
<tr class="odd">
<td><p><strong>Prefixo URI do usuário</strong></p></td>
<td><p>Endereço SIP do usuário que utilizou o telefone IP.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métricas

A tabela a seguir lista as informações fornecidas no Relatório de Inventário de Telefones IP.

### <a name="ip-phone-inventory-report-metrics"></a>Métricas do Relatório de Inventário de Telefones IP

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
<td><p><strong>Fabricantes</strong></p></td>
<td><p>Sim</p></td>
<td><p>Nome da empresa que fabricou o telefone IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Versão do hardware</strong></p></td>
<td><p>Sim</p></td>
<td><p>Número da versão do telefone IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Endereço MAC</strong></p></td>
<td><p>Sim</p></td>
<td><p>Identificador único da interface de rede no telefone IP. O endereço MAC normalmente é atribuído no momento em que o telefone é fabricado e está programado no hardware do dispositivo.</p></td>
</tr>
<tr class="even">
<td><p><strong>URI do usuário</strong></p></td>
<td><p>Sim</p></td>
<td><p>Endereço SIP do usuário que utilizou o telefone IP.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Agente do usuário</strong></p></td>
<td><p>Sim</p></td>
<td><p>Identificador do software usado pelo telefone IP.</p></td>
</tr>
<tr class="even">
<td><p><strong>Horário do último logon</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora em que o telefone IP foi conectado pela última vez no Lync Server.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Horário do último logoff</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora do último logoff do telefone IP do Lync Server.</p></td>
</tr>
<tr class="even">
<td><p><strong>Última atividade</strong></p></td>
<td><p>Sim</p></td>
<td><p>Data e hora em que o telefone IP foi utilizado pela última vez.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

