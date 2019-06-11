---
title: 'Lync Server 2013: Configurando o Roteamento Baseado em Local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Configuring Location-Based Routing
ms:assetid: 63cdc474-e80f-43b1-a237-9d9ed673300a
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994036(v=OCS.15)
ms:contentKeyID: 51803946
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a682f6b550f982f929a83bc8c2f430e89b9452fe
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836243"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-location-based-routing-in-lync-server-2013"></a>Configurando o Roteamento Baseado em Local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-03-12_

Lync Server 2013 CU1, o roteamento baseado em local é um recurso do Enterprise Voice. Roteamento baseado em local é um recurso de gerenciamento de chamadas que controla como as chamadas são roteadas pelo Lync Server 2013 CU1. Ele impõe restrições sobre se as chamadas podem ser roteadas para destinos PBX ou PSTN com base na localização do chamador do Lync. O roteamento baseado em local aplica regras de autorização de chamada a chamadas PSTN com base no local de rede do chamador. O local do chamador é determinado com base no site de rede associado à sub-rede da rede na qual o chamador está conectado. Configurar o roteamento baseado em localização exige a primeira implantação do Enterprise Voice e, em seguida, a configuração de regiões de rede, sites e sub-redes. Isso configura a base para habilitar o roteamento baseado em local.

Antes de implantar o roteamento baseado em local, primeiro você deve implantar o Enterprise Voice e configurar regiões de rede, sites e associar sub-redes de rede a seus sites de rede. Uma vez concluído, você pode configurar o roteamento baseado no local. Para ver as etapas sobre como configurar regiões de rede, sites e sub-redes, consulte Implantando [recursos avançados do Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)

Esta seção orienta você na configuração do roteamento baseado em localização usando o exemplo a seguir como ilustração.

![Exemplo de roteamento baseado na localização do Enterprise Voice] (images/JJ994036.b6ef5afc-36ac-406f-8ec2-a87532b20612(OCS.15).png "Exemplo de roteamento baseado na localização do Enterprise Voice")

  
A tabela a seguir representa os usuários definidos neste exemplo.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de ponto de extremidade</th>
<th>Local</th>
<th>Usuários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Escritório corporativo da Délhi</p></td>
<td><p>DEL-LYNC-1, DEL-LYNC-2, DEL-LYNC-3</p></td>
</tr>
<tr class="even">
<td><p>Lync</p></td>
<td><p>Escritório corporativo Hyderabad</p></td>
<td><p>HYD-LYNC-1, HYD-LYNC-2, HYD-LYNC-3</p></td>
</tr>
<tr class="odd">
<td><p>Lync</p></td>
<td><p>Desconhecido (isto é, Hotel)</p></td>
<td><p>UNK-LYNC-1</p></td>
</tr>
<tr class="even">
<td><p>RESPECTIVA</p></td>
<td><p>Escritório corporativo da Délhi</p></td>
<td><p>DEL-PBX-1, DEL-PBX-2</p></td>
</tr>
<tr class="odd">
<td><p>RESPECTIVA</p></td>
<td><p>Escritório corporativo Hyderabad</p></td>
<td><p>HYD-PBX-1, HYD-PBX-2</p></td>
</tr>
<tr class="even">
<td><p>PSTN</p></td>
<td><p>Sabe</p></td>
<td><p>PSTN-1, PSTN-2, PSTN-3</p></td>
</tr>
</tbody>
</table>

  

A tabela a seguir representa os sistemas ilustrados neste ambiente de exemplo.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Sistema</th>
<th>Local</th>
<th>Nome</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Pool CU1 do Lync Server 2013</p></td>
<td><p>qualquer um</p></td>
<td><p>LS-PL1</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 CU1, servidor de mediação</p></td>
<td><p>qualquer um</p></td>
<td><p>MS-PL1</p></td>
</tr>
<tr class="odd">
<td><p>Gateway PSTN 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-GW</p></td>
</tr>
<tr class="even">
<td><p>Gateway PSTN 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>HYD-GW</p></td>
</tr>
<tr class="odd">
<td><p>PBX 1</p></td>
<td><p>Delhi</p></td>
<td><p>DEL-PBX</p></td>
</tr>
<tr class="even">
<td><p>PBX 2</p></td>
<td><p>Hyderabad</p></td>
<td><p>RED-PBX</p></td>
</tr>
</tbody>
</table>


<div>

## <a name="in-this-section"></a>Nesta seção

  - [Configurando o Enterprise Voice no Lync Server 2013](lync-server-2013-configuring-enterprise-voice.md)

  - [Implantando regiões de rede, sites e sub-redes no Lync Server 2013](lync-server-2013-deploying-network-regions-sites-and-subnets.md)

  - [Habilitando o roteamento baseado em local no Lync Server 2013](lync-server-2013-enabling-location-based-routing.md)

</div>

<div>

## <a name="see-also"></a>Confira também


[Implantação de recursos avançados do Enterprise Voice no Lync Server 2013](lync-server-2013-deploying-advanced-enterprise-voice-features.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

