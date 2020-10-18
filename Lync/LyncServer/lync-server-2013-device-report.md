---
title: 'Lync Server 2013: relatório de dispositivos'
description: 'Lync Server 2013: relatório de dispositivos.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Device Report
ms:assetid: f42e4d60-699b-4870-8bb5-13b51bb6eb2b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg615049(v=OCS.15)
ms:contentKeyID: 48185807
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a8bff8e973d5c3e2d96c18992a2a2d917d4deb1c
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575117"
---
# <a name="device-report-in-lync-server-2013"></a>Relatório de dispositivos no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-11-12_

O Relatório de Dispositivos pode ser melhor chamado de Relatório de Microfones e Alto-Falantes; isso porque o Relatório de Dispositivos recupera métricas relacionadas às chamadas (tais como o percentual de chamadas ruins, eco e tempo de troca de voz) agrupadas por microfone e alto-falante usados na chamada. Se você estiver interessado em telefones IP (também conhecidos como "dispositivos"), use o relatório de [inventário de telefones IP no Lync Server 2013](lync-server-2013-ip-phone-inventory-report.md) em vez disso.

O Relatório de Dispositivos é extremamente útil para os administradores ao determinar se um tipo específico de dispositivo está experienciando mais chamadas de baixa qualidade do que outros. Por outro lado, pode influenciar decisões relacionadas à compra de novos dispositivos ou à substituição de dispositivos existentes.

Por padrão, as informações exibidas no Relatório de Dispositivos também se baseiam no microfone (o dispositivo de captura) e alto-falantes/headset (o dispositivo de renderização) usados na chamada. Por exemplo, suponha que você tem vários usuários que utilizam os seguintes dispositivos de captura e renderização: por padrão, as informações exibidas no Relatório de Dispositivos também se baseiam no microfone (o dispositivo de captura) e alto-falantes/headset (o dispositivo de renderização) usados na chamada. Por exemplo, suponha que você tem vários usuários que utilizam os seguintes dispositivos de captura e renderização:

  - Dispositivo de captura -- Microfone (SoundMAX Integrated Digital HD Audio)

  - Dispositivo de renderização -- Fone de ouvido com headset (Microsoft LifeChat LX-3000)

Se esses usuários fizerem um total de 254 chamadas, você verá uma entrada como esta no relatório:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Dispositivo de captura</th>
<th>Dispositivo de renderização</th>
<th>Volume da chamada</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microfone (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Fone de ouvido com headset (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
</tbody>
</table>


Agora, suponha que você tem um número de usuários que usam esse mesmo dispositivo de captura, mas usam um dispositivo de renderização diferente. Neste caso, você terá uma segunda linha no relatório, uma para uma para essa combinação única de dispositivo de captura e dispositivo de renderização:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Dispositivo de captura</th>
<th>Dispositivo de renderização</th>
<th>Volume da chamada</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microfone (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Fone de ouvido com headset (Microsoft LifeChat LX-3000)</p></td>
<td><p>254</p></td>
</tr>
<tr class="even">
<td><p>Microfone (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>Alto-falantes (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>319</p></td>
</tr>
</tbody>
</table>


Se você preferir ver os totais combinados para um determinado dispositivo (por exemplo, para o dispositivo de captura SoundMAX, independente do dispositivo de renderização usado), selecione a opção apropriada na lista suspensa de tipo de dispositivo (dispositivo de captura ou dispositivo de renderização). Se você selecionar dispositivo de captura neste exemplo, terá algo parecido com isso:


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Dispositivo de captura</th>
<th>Volume da chamada</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Microfone (SoundMAX Integrated Digital HD Audio)</p></td>
<td><p>573</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="accessing-the-device-report"></a>Acessando o relatório de dispositivos

O Relatório de Dispositivos é geralmente acessado na página inicial dos Relatórios de Monitoramento. No entanto, se você estiver exibindo o [relatório de detalhes de chamada no Lync Server 2013](lync-server-2013-call-detail-report.md) , poderá aprofundar até o relatório de dispositivo para um dispositivo específico clicando em uma das seguintes métricas:

  - Dispositivo de captura

  - Dispositivo de renderização

No relatório de dispositivos, você pode fazer uma busca detalhada [no relatório de lista de chamadas no Lync Server 2013](lync-server-2013-call-list-report.md) clicando em uma das seguintes métricas:

  - Volume da chamada

  - Percentual de chamadas ruins

</div>

<div>

## <a name="making-the-best-use-of-the-device-report"></a>Como usar melhor o Relatório de Dispositivos

Tratando-se de nomes de dispositivos, o Relatório de Dispositivos é extremamente detalhado. Por exemplo, suponha que você tem os seguintes dispositivos de captura:

  - Microfone Aastra 3002 (2- Aastra 3002)

  - Microfone Aastra 3002 (3- Aastra 3002)

  - Microfone Aastra 3002 (Aastra 3002)

  - Aastra 6725ip

  - Microfone Aastra 6725ip (10- Aastra 6725ip)

  - Microfone Aastra 6725ip (10- Aastra 6725ip)-V0

  - Microfone Aastra 6725ip (2- Aastra 6725ip)

  - Microfone Aastra 6725ip (3- Aastra 6725ip)

  - Microfone Aastra 6725ip (4- Aastra 6725ip)

  - Microfone Aastra 6725ip (5- Aastra 6725ip)

  - Microfone Aastra 6725ip (6- Aastra 6725ip)

  - Microfone Aastra 6725ip (7- Aastra 6725ip)

  - Microfone Aastra 6725ip (9- Aastra 6725ip)

  - Microfone Aastra 6725ip (9- Aastra 6725ip)-V0

  - Microfone Aastra 6725ip (Aastra 6725ip)

  - Microfone Aastra 6725ip (Aastra 6725ip)-V0

  - Microfone Aastra 6725ip (Dispositivo de áudio USB)

  - Microfone Aastra 6725ip (Dispositivo de áudio USB)-V0

<div>


> [!NOTE]  
> Tenha em mente que os nomes de dispositivos de captura podem não ser os mesmos se você estiver executando versões localizadas do Lync Server 2013. Um dispositivo denominado Microfone Aastra 6725ip (Aastra 6725ip)-V0 em português pode ter um nome diferente em francês ou espanhol.



</div>

Muitas vezes você desejará este nível de detalhe; mas em outros momentos, você só estará interessado na quantidade de chamadas que usam um microfone Aastra, independente do número do modelo. Uma maneira de obter informações como essa é para exportar os dados de relatório do dispositivo para o Microsoft Excel e, em seguida, salvar os dados em um arquivo de valores separados por vírgula (por exemplo, \\ os dispositivos de dados \\ \_Report.csv). É possível usar um conjunto de comandos parecidos com esses para importar o arquivo .CSV no Windows PowerShell e relatar o número total de chamadas feitas usando um dispositivo de captura Aastra:

    $devices = Import-Csv "C:\Data\Device_Report.csv
    $sum = $devices | Where-Object {$_."Capture device" -match "Aastra"}
    $sum | foreach-object {[Int]$x = [Int]$x + [Int]$_."call volume"}
    $x

Esse procedimento retornará um único valor que representa o número total de chamadas usando um dispositivo de captura Aastra. Por exemplo:

    384

</div>

<div>

## <a name="filters"></a>Filtros

Os filtros oferecem uma forma de retornar um conjunto de dados mais direcionado ou exibir os dados devolvidos em formas diferentes. Por exemplo, o Relatório de Dispositivo permite filtrar coisas como o tipo de chamada (isto é, a chamada foi realizada pelo cliente), uma chamada de conferência ou chamada PSTN. Também é possível escolher como os dados devem ser agrupados. Neste caso, os dispositivos são agrupados por hora, dia, semana ou mês.

A tabela a seguir lista os filtros que podem ser usados com o Relatório de Dispositivo.

### <a name="device-report-filters"></a>Filtros do Relatório de Dispositivo

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
<td><p><strong>Causa de troca de voz</strong></p></td>
<td><p>Motivo pelo qual uma chamada precisou ser colocada no modo half duplex para evitar o eco. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie. Selecione um dos seguintes:</p>
<dl>
<dt><span></span></dt>
<dd><p>Todos os</p>
</dd>
<dt><span></span></dt>
<dd><p>Nenhum</p>
</dd>
<dt><span></span></dt>
<dd><p>Carimbo de data/hora inválido</p>
</dd>
<dt><span></span></dt>
<dd><p>Eco</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (processador não linear dinâmico)</p>
</dd>
<dt><span></span></dt>
<dd><p>Baixa complexidade</p>
</dd>
<dt><span></span></dt>
<dd><p>Estado do dispositivo inválido</p>
</dd>
<dt><span></span></dt>
<dd><p>Eco pós-AEC (cancelamento do eco acústico)</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Causa do eco</strong></p></td>
<td><p>Motivo pelo qual o eco acima do aceitável foi detectado em uma chamada. (Em telecomunicações, o eco é um reflexo do som, o mesmo fenômeno que você ouvirá se gritar em um poço). Selecione um dos seguintes:</p>
<dl>
<dt><span></span></dt>
<dd><p>Todos os</p>
</dd>
<dt><span></span></dt>
<dd><p>Nenhum</p>
</dd>
<dt><span></span></dt>
<dd><p>Carimbo de data/hora inválido</p>
</dd>
<dt><span></span></dt>
<dd><p>Eco pós-AEC (cancelamento do eco acústico)</p>
</dd>
<dt><span></span></dt>
<dd><p>ANLP (processador não linear adaptado)</p>
</dd>
<dt><span></span></dt>
<dd><p>DNLP (processador não linear dinâmico)</p>
</dd>
<dt><span></span></dt>
<dd><p>Distorção do microfone</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de chamada</strong></p></td>
<td><p>Indica o tipo de chamada realizada. Selecione um dos seguintes:</p>
<dl>
<dt><span></span></dt>
<dd><p>Todos os</p>
</dd>
<dt><span></span></dt>
<dd><p>Chamada do cliente</p>
</dd>
<dt><span></span></dt>
<dd><p>Chamada PSTN</p>
</dd>
<dt><span></span></dt>
<dd><p>Chamada de conferência</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Tipo de acesso</strong></p></td>
<td><p>Indica se um cliente estava conectado na rede interna ou na rede externa quando a chamada foi realizada. Selecione um dos seguintes:</p>
<dl>
<dt><span></span></dt>
<dd><p>Todos os</p>
</dd>
<dt><span></span></dt>
<dd><p>Interno</p>
</dd>
<dt><span></span></dt>
<dd><p>Externo</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de rede</strong></p></td>
<td><p>Indica o tipo de rede que o cliente estava conectado quando a chamada foi realizada. Selecione um dos seguintes:</p>
<dl>
<dt><span></span></dt>
<dd><p>Todos os</p>
</dd>
<dt><span></span></dt>
<dd><p>Com fio</p>
</dd>
<dt><span></span></dt>
<dd><p>Conexão</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>VPN</strong></p></td>
<td><p>Indica se um cliente externo estava usando uma conexão de rede privada virtual (VPN) quando a chamada foi realizada. Selecione um dos seguintes:</p>
<dl>
<dt><span></span></dt>
<dd><p>Todos os</p>
</dd>
<dt><span></span></dt>
<dd><p>VPN</p>
</dd>
<dt><span></span></dt>
<dd><p>Não VPN</p>
</dd>
</dl></td>
</tr>
<tr class="odd">
<td><p><strong>Tipo de dispositivo</strong></p></td>
<td><p>Indica o tipo de dispositivo. Selecione um dos seguintes:</p>
<dl>
<dt><span></span></dt>
<dd><p>Dispositivo de captura</p>
</dd>
<dt><span></span></dt>
<dd><p>Dispositivo de renderização</p>
</dd>
<dt><span></span></dt>
<dd><p>Par de dispositivos de captura/renderização</p>
</dd>
</dl></td>
</tr>
<tr class="even">
<td><p><strong>Nome do dispositivo</strong></p></td>
<td><p>Nome do dispositivo de captura ou renderização. É possível inserir o nome completo do dispositivo ou qualquer parte do nome. Por exemplo para encontrar o dispositivo Microfone (Microsoft LifeCam VX-1000.), é possível inserir o nome completo do dispositivo, como a seguir:</p>
<p>Microfone (Microsoft LifeCam VX-1000.)</p>
<p>Em alternativa, é possível inserir apenas uma parte do nome. Por exemplo:</p>
<p>LifeCam</p>
<p>Observe que o filtro anterior retorna qualquer dispositivo que contenha a cadeia de caracteres &quot; LifeCam &quot; em qualquer lugar em seu nome.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="metrics"></a>Métrica

A tabela a seguir lista a informação oferecida no Relatório do Dispositivo.

### <a name="device-report-metrics"></a>Métricas do Relatório do Dispositivo

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
<td><p><strong>Dispositivo de captura</strong></p></td>
<td><p>Sim</p></td>
<td><p>Dispositivo (por exemplo, um microfone ou webcam) usado para transmitir áudio.</p></td>
</tr>
<tr class="even">
<td><p><strong>Dispositivos de renderização</strong></p></td>
<td><p>Sim</p></td>
<td><p>Dispositivo (por exemplo, um fone de ouvido ou alto falantes) usados para receber áudio.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Volume da chamada</strong></p></td>
<td><p>Sim</p></td>
<td><p>Número total de chamadas realizadas.</p></td>
</tr>
<tr class="even">
<td><p><strong>Percentual de chamadas ruins</strong></p></td>
<td><p>Sim</p></td>
<td><p>Porcentagem de chamadas classificadas como &quot; ruins. &quot; Uma chamada ruim é qualquer chamada que pelo menos uma das métricas medidas excedeu o valor permitido (por exemplo, uma chamada com tremulação excessiva).</p></td>
</tr>
<tr class="odd">
<td><p><strong>Usuários exclusivos</strong></p></td>
<td><p>Sim</p></td>
<td><p>Usuários exclusivos que utilizaram o dispositivo. Se um usuário utilizou o dispositivo 13 vezes, ele ou ela deve contar como um usuário exclusivo, o mesmo que um usuário que utilizou o dispositivo uma única vez.</p></td>
</tr>
<tr class="even">
<td><p><strong>Tempo de troca da taxa de voz</strong></p></td>
<td><p>Sim</p></td>
<td><p>Porcentagem da chamada que precisou ser conduzida no modo half duplex para evitar o eco. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Taxa de microfone não funcionando</strong></p></td>
<td><p>Sim</p></td>
<td><p>Porcentagem da chamada na qual o dispositivo de captura não estava funcionando em um nível aceitável. Um valor alto sugere que os problemas de qualidade da chamada ocorreram devido principalmente ao dispositivo de captura não estar funcionando conforme esperado.</p></td>
</tr>
<tr class="even">
<td><p><strong>Taxa de alto falante não funcionando</strong></p></td>
<td><p>Sim</p></td>
<td><p>Porcentagem da chamada na qual o dispositivo de renderização não estava funcionando em um nível aceitável. Um valor alto sugere que os problemas de qualidade da chamada ocorreram devido principalmente ao dispositivo de renderização não estar funcionando conforme esperado.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Chamadas com opção de voz (%)</strong></p></td>
<td><p>Sim</p></td>
<td><p>Porcentagem do total de chamadas que precisaram ser colocadas no modo half duplex. No modo half duplex, a comunicação pode passar apenas em uma direção por vez, semelhante a forma que os usuários revezam ao se comunicar com um walkie-talkie.</p></td>
</tr>
<tr class="even">
<td><p><strong>Eco do microfone em (%)</strong></p></td>
<td><p>Sim</p></td>
<td><p>Porcentagem de tempo em que o eco foi detectado no fluxo de captura do microfone. Normalmente, os valores são baixos para fones de ouvido ou fones, e mais altos para telefones do alto-falante ou alto-falantes autônomos. Para dispositivos que suportam cancelamento de eco acústico integrado, valores altos indicam vazamento de eco. Para outros dispositivos, essa métrica não deve ser usada para avaliar a qualidade do dispositivo.</p></td>
</tr>
<tr class="odd">
<td><p><strong>Envio de eco (%)</strong></p></td>
<td><p>Sim</p></td>
<td><p>Porcentagem de eco transmitido para outros usuários.</p></td>
</tr>
<tr class="even">
<td><p><strong>Chamadas com eco (%)</strong></p></td>
<td><p>Sim</p></td>
<td><p>Porcentagem do total de chamadas que tiveram eco excedendo o nível aceitável.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

