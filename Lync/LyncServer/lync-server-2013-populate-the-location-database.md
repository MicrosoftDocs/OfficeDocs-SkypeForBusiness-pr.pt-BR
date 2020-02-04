---
title: 'Lync Server 2013: popular o local do banco de dados'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Populate the location database
ms:assetid: fb84f5b6-c991-4893-bdbf-f195b4b7d28e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg413069(v=OCS.15)
ms:contentKeyID: 48185939
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a93cee85afec1e3943af692d598d0d02ab678d58
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41747641"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a>Preencher o banco de dados de localização no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-09-17_

Para localizar clientes automaticamente em uma rede, primeiro você precisa preencher o banco de dados de localização com um *mapa de conexões* de rede, que mapeia os elementos de rede para endereços residenciais (ou seja, ruas). Você pode usar sub-redes, pontos de acesso sem fio, opções e portas para definir o mapa de conexões.

É possível adicionar endereços ao banco de dados local individualmente ou em massa usando um arquivo CSV contendo os formatos de coluna descritos na tabela a seguir.

Se você usa um gateway de número da chamada de emergência (Emergency Location Identification Number - ELIN), inclua o ELIN no campo **CompanyName** para cada local. Você pode incluir diversos ELINs para cada local, separados por ponto e vírgula.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Elemento de rede</th>
<th>Colunas obrigatórias</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><strong>Ponto de acesso sem fio</strong></p></td>
<td><p>&lt;BSSID&gt;,&lt;Descrição&gt;,&lt;local&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</p>
<p>... &lt;Streetname&gt;,&lt;StreetSuffix&gt;,&lt;monodirecional&gt;,&lt;cidade&gt;,&lt;estado&gt;,&lt;CEP&gt;,&lt;país&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Sub-rede</strong></p></td>
<td><p>&lt;Sub-rede&gt;,&lt;Descrição&gt;,&lt;local&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</p>
<p>... &lt;Streetname&gt;,&lt;StreetSuffix&gt;,&lt;monodirecional&gt;,&lt;cidade&gt;,&lt;estado&gt;,&lt;CEP&gt;,&lt;país&gt;</p></td>
</tr>
<tr class="odd">
<td><p><strong>Porta</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;portid&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,...</p>
<p>... &lt;Predirectional&gt;,&lt;streetname&gt;,&lt;StreetSuffix&gt;,&lt;monodirecional&gt;,&lt;cidade&gt;,&lt;estado&gt;,&lt;CEP&gt;,&lt;país&gt;</p></td>
</tr>
<tr class="even">
<td><p><strong>Opção</strong></p></td>
<td><p>&lt;ChassisID&gt;,&lt;Descrição&gt;,&lt;local&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</p>
<p>... &lt;Streetname&gt;,&lt;StreetSuffix&gt;,&lt;monodirecional&gt;,&lt;cidade&gt;,&lt;estado&gt;,&lt;CEP&gt;,&lt;país&gt;</p></td>
</tr>
</tbody>
</table>


Se você não preencher o banco de dados local e o **Local necessário** na Política de Localização está definido para **Sim** ou **Isenção de Responsabilidade**, o cliente solicitará que o usuário insira um local manualmente.

Para obter detalhes sobre como preencher o banco de dados de localização, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:

  - **Get-CsLisSubnet**

  - **Set-CsLisSubnet**

  - Remove-CsLisSubnet

  - **Get-CsLisWirelessAccessPoint**

  - **Set-CsLisWirelessAccessPoint**

  - **Remove-CsLisWirelessAccessPoint**

  - **Get-CsLisSwitch**

  - **Set-CsLisSwitch**

  - **Remove-CsLisSwitch**

  - **Get-CsLisPort**

  - **Set-CsLisPort**

  - **Remove-CsLisPort**

<div>

## <a name="to-add-network-elements-to-the-location-database"></a>Para adicionar elementos de rede no banco de dados de localização

1.  Execute o seguinte cmdlet para adicionar um local de sub-rede ao banco de dados de localização.
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Para gateways de ELIN, informe o ELIN no campo CompanyName. Você pode incluir mais de um ELIN. Exemplo:
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "subnets.csv" para atualização em massa de locais de sub-rede.
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  Execute o seguinte cmdlet para adicionar locais sem fio ao banco de dados de localização.
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "waps.csv" para atualização em massa de locais sem fio.
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  Execute o seguinte cmdlet para adicionar locais de opções ao banco de dados de localização.
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "switches.csv" para atualização em locais de switch.
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  Execute o seguinte cmdlet para adicionar locais de porta ao banco de dados de localização
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    O padrão de PortIDSubType é LocallyAssigned. Você também pode definir para InterfaceAlias ou InterfaceName
    
    Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "ports.csv" para atualização em massa de locais de porta.
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

