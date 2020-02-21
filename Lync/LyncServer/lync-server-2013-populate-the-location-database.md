---
title: 'Lync Server 2013: preencher o banco de dados de localização'
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
ms.openlocfilehash: 0216cada44f2512e33a0b33b627ed9a6d6582cda
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42208807"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="populate-the-location-database-in-lync-server-2013"></a><span data-ttu-id="165d0-102">Preencher o banco de dados de localização no Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="165d0-102">Populate the location database in Lync Server 2013</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="165d0-103">_**Última modificação do tópico:** 2012-09-17_</span><span class="sxs-lookup"><span data-stu-id="165d0-103">_**Topic Last Modified:** 2012-09-17_</span></span>

<span data-ttu-id="165d0-p101">Para localizar clientes automaticamente em uma rede, primeiro você precisa preencher o banco de dados de localização com um *mapa de conexões* de rede, que mapeia os elementos de rede para endereços residenciais (ou seja, ruas). Você pode usar subredes, pontos de acesso sem fio, opções e portas para definir o mapa de conexões.</span><span class="sxs-lookup"><span data-stu-id="165d0-p101">To automatically locate clients within a network, you first need to populate the location database with a network *wiremap*, which maps network elements to civic (that is, street) addresses. You can use subnets, wireless access points, switches, and ports to define the wiremap.</span></span>

<span data-ttu-id="165d0-106">É possível adicionar endereços ao banco de dados local individualmente ou em massa usando um arquivo CSV contendo os formatos de coluna descritos na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="165d0-106">You can add addresses to the location database individually, or in bulk by using a CSV file that contains the column formats described in the following table.</span></span>

<span data-ttu-id="165d0-p102">Se você usa um gateway de número da chamada de emergência (Emergency Location Identification Number - ELIN), inclua o ELIN no campo **CompanyName** para cada local. Você pode incluir diversos ELINs para cada local, separados por ponto e vírgula.</span><span class="sxs-lookup"><span data-stu-id="165d0-p102">If you use an Emergency Location Identification Number (ELIN) gateway, include the ELIN in the **CompanyName** field for each location. You can include multiple ELINs for each location, each separated by a semicolon.</span></span>


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="165d0-109">Elemento de rede</span><span class="sxs-lookup"><span data-stu-id="165d0-109">Network Element</span></span></th>
<th><span data-ttu-id="165d0-110">Colunas obrigatórias</span><span class="sxs-lookup"><span data-stu-id="165d0-110">Required Columns</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="165d0-111"><strong>Ponto de acesso sem fio </strong></span><span class="sxs-lookup"><span data-stu-id="165d0-111"><strong>Wireless access point</strong></span></span></p></td>
<td><p><span data-ttu-id="165d0-112">&lt;BSSID&gt;,&lt;Descrição&gt;,&lt;local&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="165d0-112">&lt;BSSID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="165d0-113">... &lt;Streetname&gt;,&lt;StreetSuffix&gt;,&lt;&gt;-direcional&lt;, cidade&gt;,&lt;estado&gt;,&lt;CEP&gt;, país&lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="165d0-113">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="165d0-114"><strong>-</strong></span><span class="sxs-lookup"><span data-stu-id="165d0-114"><strong>Subnet</strong></span></span></p></td>
<td><p><span data-ttu-id="165d0-115">&lt;Sub&gt;-&lt;rede&gt;,&lt;Descrição&gt;,&lt;local&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix, predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="165d0-115">&lt;Subnet&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="165d0-116">... &lt;Streetname&gt;,&lt;StreetSuffix&gt;,&lt;&gt;-direcional&lt;, cidade&gt;,&lt;estado&gt;,&lt;CEP&gt;, país&lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="165d0-116">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="165d0-117"><strong>Port</strong></span><span class="sxs-lookup"><span data-stu-id="165d0-117"><strong>Port</strong></span></span></p></td>
<td><p><span data-ttu-id="165d0-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;portid&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,...</span><span class="sxs-lookup"><span data-stu-id="165d0-118">&lt;ChassisID&gt;,&lt;PortIDSubType&gt;,&lt;PortID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,…</span></span></p>
<p><span data-ttu-id="165d0-119">... &lt;Predirectional&gt;,&lt;streetname&gt;,&lt;StreetSuffix&gt;,&lt;multidirecional&gt;,&lt;cidade&gt;,&lt;estado&gt;,&lt;CEP&gt;,&lt;país&gt;</span><span class="sxs-lookup"><span data-stu-id="165d0-119">…&lt;PreDirectional&gt;,&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="165d0-120"><strong>Switch</strong></span><span class="sxs-lookup"><span data-stu-id="165d0-120"><strong>Switch</strong></span></span></p></td>
<td><p><span data-ttu-id="165d0-121">&lt;ChassisID&gt;,&lt;Descrição&gt;,&lt;local&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;predirectional&gt;,...</span><span class="sxs-lookup"><span data-stu-id="165d0-121">&lt;ChassisID&gt;,&lt;Description&gt;,&lt;Location&gt;,&lt;CompanyName&gt;,&lt;HouseNumber&gt;,&lt;HouseNumberSuffix&gt;,&lt;PreDirectional&gt;,…</span></span></p>
<p><span data-ttu-id="165d0-122">... &lt;Streetname&gt;,&lt;StreetSuffix&gt;,&lt;&gt;-direcional&lt;, cidade&gt;,&lt;estado&gt;,&lt;CEP&gt;, país&lt;&gt;</span><span class="sxs-lookup"><span data-stu-id="165d0-122">…&lt;StreetName&gt;,&lt;StreetSuffix&gt;,&lt;PostDirectional&gt;,&lt;City&gt;,&lt;State&gt;,&lt;PostalCode&gt;,&lt;Country&gt;</span></span></p></td>
</tr>
</tbody>
</table>


<span data-ttu-id="165d0-123">Se você não preencher o banco de dados local e o \*\*Local necessário \*\*na Política de Localização está definido para \*\*Sim \*\* ou **Isenção de Responsabilidade**, o cliente solicitará que o usuário insira um local manualmente.</span><span class="sxs-lookup"><span data-stu-id="165d0-123">If you do not populate the location database, and the **Location Required** in the Location Policy is set to **Yes** or **Disclaimer**, the client will prompt the user to enter a location manually.</span></span>

<span data-ttu-id="165d0-124">Para obter detalhes sobre como preencher o banco de dados de localização, consulte a documentação do Shell de gerenciamento do Lync Server para os seguintes cmdlets:</span><span class="sxs-lookup"><span data-stu-id="165d0-124">For details about populating the location database, see the Lync Server Management Shell documentation for the following cmdlets:</span></span>

  - <span data-ttu-id="165d0-125">**Get-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="165d0-125">**Get-CsLisSubnet**</span></span>

  - <span data-ttu-id="165d0-126">**Set-CsLisSubnet**</span><span class="sxs-lookup"><span data-stu-id="165d0-126">**Set-CsLisSubnet**</span></span>

  - <span data-ttu-id="165d0-127">Remove-CsLisSubnet</span><span class="sxs-lookup"><span data-stu-id="165d0-127">Remove-CsLisSubnet</span></span>

  - <span data-ttu-id="165d0-128">**Get-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="165d0-128">**Get-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="165d0-129">**Set-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="165d0-129">**Set-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="165d0-130">**Remove-CsLisWirelessAccessPoint**</span><span class="sxs-lookup"><span data-stu-id="165d0-130">**Remove-CsLisWirelessAccessPoint**</span></span>

  - <span data-ttu-id="165d0-131">**Get-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="165d0-131">**Get-CsLisSwitch**</span></span>

  - <span data-ttu-id="165d0-132">**Set-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="165d0-132">**Set-CsLisSwitch**</span></span>

  - <span data-ttu-id="165d0-133">**Remove-CsLisSwitch**</span><span class="sxs-lookup"><span data-stu-id="165d0-133">**Remove-CsLisSwitch**</span></span>

  - <span data-ttu-id="165d0-134">**Get-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="165d0-134">**Get-CsLisPort**</span></span>

  - <span data-ttu-id="165d0-135">**Set-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="165d0-135">**Set-CsLisPort**</span></span>

  - <span data-ttu-id="165d0-136">**Remove-CsLisPort**</span><span class="sxs-lookup"><span data-stu-id="165d0-136">**Remove-CsLisPort**</span></span>

<div>

## <a name="to-add-network-elements-to-the-location-database"></a><span data-ttu-id="165d0-137">Para adicionar elementos de rede no banco de dados de localização</span><span class="sxs-lookup"><span data-stu-id="165d0-137">To add network elements to the location database</span></span>

1.  <span data-ttu-id="165d0-138">Execute o seguinte cmdlet para adicionar um local de subrede ao banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="165d0-138">Run the following cmdlet to add a subnet location to the location database.</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="165d0-p103">Para gateways de ELIN, informe o ELIN no campo CompanyName. Você pode incluir mais de um ELIN. Exemplo:</span><span class="sxs-lookup"><span data-stu-id="165d0-p103">For ELIN gateways, put the ELIN in the CompanyName field. You can include more than one ELIN. For example:</span></span>
    
        Set-CsLisSubnet -Subnet 157.56.66.0 -Description "Subnet 1" -Location Location1 -CompanyName 425-555-0100; 425-555-0200; 425-555-0300 -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="165d0-142">Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "subnets.csv" para atualização em massa de locais de subrede.</span><span class="sxs-lookup"><span data-stu-id="165d0-142">Alternately, you can run the following cmdlets and use a file named "subnets.csv" to bulk update subnet locations.</span></span>
    
        $g = Import-Csv subnets.csv
        $g | Set-CsLisSubnet

2.  <span data-ttu-id="165d0-143">Execute o seguinte cmdlet para adicionar locais sem fio ao banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="165d0-143">Run the following cmdlet to add wireless locations to the location database.</span></span>
    
        Set-CsLisWirelessAccessPoint -BSSID 0A-23-CD-16-AA-2E -Description "Wireless1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="165d0-144">Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "waps.csv" para atualização em massa de locais sem fio.</span><span class="sxs-lookup"><span data-stu-id="165d0-144">Alternately, you can run the following cmdlets and use a file named "waps.csv" to bulk update wireless locations.</span></span>
    
        $g = Import-Csv waps.csv
        $g | Set-CsLisWirelessAccessPoint

3.  <span data-ttu-id="165d0-145">Execute o seguinte cmdlet para adicionar locais de opções ao banco de dados de localização.</span><span class="sxs-lookup"><span data-stu-id="165d0-145">Run the following cmdlet to add switch locations to the location database.</span></span>
    
        Set-CsLisSwitch-ChassisID 0B-23-CD-16-AA-BB -Description "Switch1" -Location Location1 -CompanyName "Litware" -HouseNumber 1234 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Redmond -State WA -PostalCode 99123 -Country US
    
    <span data-ttu-id="165d0-146">Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "switches.csv" para atualização em locais de switch.</span><span class="sxs-lookup"><span data-stu-id="165d0-146">Alternately, you can run the following cmdlets and use a file named "switches.csv" to bulk update switch locations.</span></span>
    
        $g = Import-Csv switches.csv
        $g | Set-CsLisSwitch

4.  <span data-ttu-id="165d0-147">Execute o seguinte cmdlet para adicionar locais de porta ao banco de dados de localização</span><span class="sxs-lookup"><span data-stu-id="165d0-147">Run the following cmdlet to add port locations to the location database</span></span>
    
        Set-CsLisPort -ChassisID 0C-23-CD-16-AA-CC -PortID 0A-abcd -Description "Port1" -Location Location2 -CompanyName "Litware" -HouseNumber 2345 -HouseNumberSuffix "" -PreDirectional "" -StreetName 163rd -StreetSuffix Ave -PostDirectional NE -City Bellevue -State WA -PostalCode 99234 -Country US
    
    <span data-ttu-id="165d0-p104">O padrão de PortIDSubType é LocallyAssigned. Você também pode definir para InterfaceAlias ou InterfaceName</span><span class="sxs-lookup"><span data-stu-id="165d0-p104">The default for PortIDSubType is LocallyAssigned. You can also set it to InterfaceAlias or InterfaceName</span></span>
    
    <span data-ttu-id="165d0-150">Alternativamente, é possível executar os cmdlets a seguir e usar um arquivo denominado "ports.csv" para atualização em massa de locais de porta.</span><span class="sxs-lookup"><span data-stu-id="165d0-150">Alternately, you can run the following cmdlets and use a file named "ports.csv" to bulk update port locations.</span></span>
    
        $g = Import-Csv ports.csv
        $g | Set-CsLisPort

</div>

</div>

<span> </span>

</div>

</div>

</div>

