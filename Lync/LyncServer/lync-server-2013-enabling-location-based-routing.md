---
title: 'Lync Server 2013: habilitando roteamento baseado em local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Enabling Location-Based Routing
ms:assetid: 029ede7e-0c4e-4ad2-af99-909ae674d6fe
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994014(v=OCS.15)
ms:contentKeyID: 51803920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: e21e1a285fa5b2129d4d0ed0b5d75e8dcee42f2f
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41735801"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="enabling-location-based-routing-in-lync-server-2013"></a>Habilitando o roteamento baseado em local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-04-26_

Depois que o Enterprise Voice é implantado e as regiões de rede, sites e sub-redes são definidas, você pode habilitar o roteamento baseado em localização. O roteamento baseado em local deve ser habilitado para os seguintes elementos da Enterprise Voice:

  - Sites de rede

  - Configurações de tronco

  - Políticas de voz

  - Configuração de roteamento

<div>

## <a name="enable-location-based-routing-to-network-sites"></a>Habilitar o roteamento baseado em local para sites de rede

Depois de implantar o Enterprise Voice e configurar sites de rede, você estará pronto para configurar o roteamento baseado no local. Primeiro, crie uma política de roteamento de voz para associar o site de rede com os usos de PSTN apropriados. Ao atribuir usos de PSTN a uma política de roteamento de voz, certifique-se de usar somente os usos de PSTN associados a rotas de voz que usam um gateway PSTN local para o site ou um gateway PSTN localizado em uma região onde restrições de roteamento baseadas em localização não são necessárias. Use o comando do Windows PowerShell do Lync Server, o New-CsVoiceRoutingPolicy ou o painel de controle do Lync Server para criar políticas de roteamento de voz.

    New-CsVoiceRoutingPolicy -Identity <voice routing policy ID> -Name <voice routing policy name> -PstnUsages <usages>

Para obter mais informações, consulte [New-CsVoiceRoutingPolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoiceRoutingPolicy).

Para este exemplo, a tabela a seguir e os comandos do Windows PowerShell ilustram duas políticas de roteamento de voz e seus usos de PSTN associados definidos nesse cenário. Somente as configurações específicas do roteamento baseado em localização são incluídas na tabela para fins de ilustração.

    New-CsVoiceRoutingPolicy -Identity "DelhiVoiceRoutingPolicy" -Name "Delhi voice routing policy" -PstnUsages @{add="Delhi usage", "PBX Del usage", "PBX Hyd usage"}
    New-CsVoiceRoutingPolicy -Identity "HyderabadVoiceRoutingPolicy" -Name " Hyderabad voice routing policy" -PstnUsages @{add="Hyderabad usage", "PBX Del usage", "PBX Hyd usage"}


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Política de roteamento de voz 1</th>
<th>Política de roteamento de voz 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID da política de voz</p></td>
<td><p>Política de roteamento de voz Delhi</p></td>
<td><p>Política de roteamento de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usos de PSTN</p></td>
<td><p>Uso de Delhi, uso do PBX, uso do PBX Hyd</p></td>
<td><p>Uso do Hyderabad, Hyd do PBX, uso do PBX</p></td>
</tr>
</tbody>
</table>

  

Em seguida, configure o roteamento baseado em local para os sites de rede aplicáveis e associe suas políticas de roteamento de voz a eles. Use o comando do Windows PowerShell do Lync Server, New-CsNetworkSite, para habilitar o roteamento baseado em local e associar políticas de roteamento de voz a seus sites de rede que devem impor restrições de roteamento.

    Set-CsNetworkSite -Identity <site ID> -EnableLocationBasedRouting <$true|$false> -VoiceRoutingPolicy <voice routing policy ID>

Neste exemplo, a tabela a seguir ilustra o roteamento baseado em localização para dois locais de rede diferentes, Delhi e Hyderabad, definidos neste cenário usando o Windows PowerShell do Lync Server. Somente as configurações específicas do roteamento baseado em localização são incluídas na tabela para fins de ilustração.

    Set-CsNetworkSite -Identity "Delhi" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "DelhiVoiceRoutingPolicy"
    Set-CsNetworkSite -Identity "Hyderabad" -EnableLocationBasedRouting $true -VoiceRoutingPolicy "HyderabadVoiceRoutingPolicy"


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Site 1 (Déli)</th>
<th>Site 2 (Hyderabad)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nome do site</p></td>
<td><p>Site 1 (Déli)</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="even">
<td><p>EnableLocationBasedRouting</p></td>
<td><p>Verdadeiro</p></td>
<td><p>Verdadeiro</p></td>
</tr>
<tr class="odd">
<td><p>Política de roteamento de voz</p></td>
<td><p>Política de roteamento de voz Delhi</p></td>
<td><p>Política de roteamento de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Sub-redes</p></td>
<td><p>Sub-rede 1 (Déli)</p></td>
<td><p>Sub-rede 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-trunks"></a>Habilitar roteamento baseado em local para troncos

Antes que uma configuração de tronco possa ser habilitada para roteamento baseado em localização, você precisará criar uma configuração de tronco para cada tronco ou cada site de rede. Use o comando do Windows PowerShell do Lync Server, New-CsTrunkConfiguration, para criar uma configuração de tronco. Se vários troncos estiverem associados a um determinado sistema (ou seja, gateway ou PBX), cada configuração de tronco deve ser modificada para habilitar restrições de roteamento baseado em localização.

    New-CsTrunkConfiguration -Identity < trunk configuration ID>

Para obter mais informações, consulte [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

Para este exemplo, os comandos do Windows PowerShell a seguir ilustram a criação de uma configuração de tronco para cada tronco na implantação definido neste cenário.

    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 1 DEL-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 2 HYD-GW>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 3 DEL-PBX>"
    New-CsTrunkConfiguration -Identity Service:PstnGateway:"<Trunk 4 HYD-PBX>"

Depois que uma configuração de tronco é configurada por tronco, você pode usar o comando do Windows PowerShell do Lync Server, Set-CsTrunkConfiguration, para habilitar o roteamento baseado em local para seus troncos que devem impor restrições de roteamento. Habilite o roteamento baseado em local para troncos que roteiam chamadas para gateways PSTN que roteiam chamadas para a PSTN e associe o site de rede onde o gateway está localizado.

    Set-CsTrunkConfiguration -Identity <trunk configuration ID> -EnableLocationRestriction $true -NetworkSiteID <site ID>

Para obter mais informações, consulte [New-CsTrunkConfiguration](https://docs.microsoft.com/powershell/module/skype/New-CsTrunkConfiguration).

Neste exemplo, o roteamento baseado em localização está habilitado para cada tronco associado a gateways PSTN em Delhi e Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 1 DEL-GW -EnableLocationRestriction $true -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 2 HYD-GW -EnableLocationRestriction $true -NetworkSiteID "Hyderabad"

  

Não habilite o roteamento baseado em local para troncos que não roteiam chamadas para a PSTN; no entanto, você ainda deve associar o tronco ao site de rede onde o sistema está localizado como as restrições de roteamento baseadas em localização precisam ser impostas para que as chamadas PSTN atinjam pontos de extremidade conectados por meio desse tronco. Para este exemplo, o roteamento baseado em local não está habilitado para cada tronco associado a sistemas PBX em Delhi e Hyderabad:

    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 3 DEL-PBX -EnableLocationRestriction $false -NetworkSiteID "Delhi"
    Set-CsTrunkConfiguration -Identity Service:PstnGateway:Trunk 4 HYD-PBX -EnableLocationRestriction $false -NetworkSiteID "Hyderabad"

  
Os pontos de extremidade conectados a sistemas que não roteiam chamadas para o PSTN (ou seja, um PBX) terão restrições semelhantes aos pontos de extremidade do Lync dos usuários habilitados para roteamento baseado em local. Isso significa que esses usuários poderão fazer e receber chamadas de e para o usuário do Lync, independentemente da localização do usuário. Eles também poderão fazer um recebimento de chamadas para e de outros sistemas que não roteiam chamadas para a rede PSTN (ou seja, um ponto de extremidade conectado a um PBX diferente), independentemente do site de rede ao qual o sistema está associado. Todas as chamadas recebidas, chamadas de saída, transferências de chamadas e encaminhamento de chamadas que envolvem pontos de extremidade PSTN estarão sujeitas a enforcementos de roteamento baseados em local. Essas chamadas devem usar somente gateways PSTN definidos como locais para tais sistemas.

A tabela a seguir ilustra a configuração de troncos de quatro troncos em dois locais de rede diferentes: dois conectados a gateways PSTN e dois conectados a sistemas PBX.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Nome</th>
<th>EnableLocationRestriction</th>
<th>NetworkSiteID</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>PstnGateway: tronco 1 DEL-GW</p></td>
<td><p>Verdadeiro</p></td>
<td><p>Site 1 (Déli)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: tronco 2 HYD-GW</p></td>
<td><p>Verdadeiro</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
<tr class="odd">
<td><p>PstnGateway: tronco 3 DEL-PBX</p></td>
<td><p>Falso</p></td>
<td><p>Site 1 (Déli)</p></td>
</tr>
<tr class="even">
<td><p>PstnGateway: trunk 4 HYD-PBX</p></td>
<td><p>Falso</p></td>
<td><p>Site 2 (Hyderabad)</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-to-voice-policies"></a>Habilitar o roteamento baseado em local para políticas de voz

Para impor o roteamento baseado em localização a usuários específicos, configure a política de voz dos usuários para impedir que a chamada em PSTN seja ignorada. Use o comando do Windows PowerShell do Lync Server, New-CsVoicePolicy, para criar uma nova política de voz ou Set-CsVoicePolicy, se estiver usando uma política existente, para habilitar o roteamento baseado em local, impedindo o bypass de chamada PSTN.

    Set-CsVoicePolicy -Identity <voice policy ID> -PreventPSTNTollBypass <$true|$false>

Para obter mais informações, consulte [New-CsVoicePolicy](https://docs.microsoft.com/powershell/module/skype/New-CsVoicePolicy).

Para este exemplo, a tabela a seguir e os comandos do Windows PowerShell ilustram a prevenção de bypass de chamada PSTN para as políticas de voz Delhi e Hyderabad definidas nesse cenário. Somente as configurações específicas do roteamento baseado em localização são incluídas na tabela para fins de ilustração.

    Set-CsVoicePolicy -Identity "Delhi voice policy" -PreventPSTNTollBypass $true
    Set-CsVoicePolicy -Identity "Hyderabad voice policy" -PreventPSTNTollBypass $true


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th></th>
<th>Política de voz 1</th>
<th>Política de voz 2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>ID da política de voz</p></td>
<td><p>Política de voz de Délhi</p></td>
<td><p>Política de voz Hyderabad</p></td>
</tr>
<tr class="even">
<td><p>Usos de PSTN</p></td>
<td><p>Uso de Delhi, uso do PBX, uso do PBX Hyd</p></td>
<td><p>Uso do Hyderabad, Hyd do PBX, uso do PBX</p></td>
</tr>
<tr class="odd">
<td><p>PreventPSTNTollBypass</p></td>
<td><p>Verdadeiro</p></td>
<td><p>Verdadeiro</p></td>
</tr>
</tbody>
</table>


<div>


</div>

</div>

<div>

## <a name="enable-location-based-routing-in-the-routing-configuration"></a>Habilitar o roteamento baseado em local na configuração de roteamento

Por fim, habilite globalmente o roteamento baseado em local para sua configuração de roteamento. Use o comando do Windows PowerShell do Lync Server, New-CsRoutingConfiguration, para habilitar o roteamento baseado em local.

    Set-CsRoutingConfiguration -EnableLocationBasedRouting $true

Para obter mais informações, consulte [set-CsRoutingConfiguration](https://docs.microsoft.com/powershell/module/skype/Set-CsRoutingConfiguration).

<div>


> [!NOTE]  
> Embora o roteamento baseado em localização deva ser habilitado por meio de uma configuração global, o conjunto de regras a ser aplicado só será imposto para os sites, os usuários e os troncos para os quais foram configurados conforme especificado nesta documentação.



</div>

<div>


</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Configurando o Roteamento Baseado em Local no Lync Server 2013](lync-server-2013-configuring-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

