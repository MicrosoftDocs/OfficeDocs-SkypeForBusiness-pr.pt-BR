---
title: 'Lync Server 2013: Suporte a cliente e servidor para Roteamento Baseado em Local'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3791b359422c4b5bef463a612db6f0b74c07f096
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836565"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Suporte a cliente e servidor para Roteamento Baseado em Local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-06-18_

O roteamento baseado em local é imposto pelo Lync Server. O Lync Server pode identificar os sites de rede nos quais os usuários estão se conectando dentro da rede corporativa. Como os usuários remotos estão fora da rede corporativa, seu local é considerado desconhecido.

<div>

## <a name="lync-server-support"></a>Suporte ao Lync Server

O roteamento baseado em localização requer que o Lync Server 2013 CU1 seja implantado em todos os pools de front-end e servidores Standard Edition em uma determinada topologia. Se o Lync Server 2013 CU1 não estiver instalado em certos componentes do Lync na topologia, as restrições de roteamento baseadas em local não poderão ser totalmente impostas.

A tabela a seguir identifica a combinação de funções de servidor e versões com suporte para roteamento baseado em local.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Versão do pool</th>
<th>Versão do Servidor de Mediação</th>
<th>Com suporte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</p></td>
<td><p>Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</p></td>
<td><p>sim</p></td>
</tr>
<tr class="even">
<td><p>Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>não</p></td>
</tr>
<tr class="odd">
<td><p>Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>não</p></td>
</tr>
<tr class="even">
<td><p>Atualização cumulativa de fevereiro de 2013 do Lync Server 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>não</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>qualquer um</p></td>
<td><p>não</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>qualquer um</p></td>
<td><p>não</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>qualquer um</p></td>
<td><p>não</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Suporte ao cliente do Lync

A tabela a seguir identifica os clientes com suporte para o roteamento baseado em localização.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de cliente</th>
<th>Com suporte</th>
<th>Detalhes</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>sim</p></td>
<td><p>Incluindo a atualização cumulativa do Lync 2013 de fevereiro de 2013</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010</p></td>
<td><p>sim</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>não</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync Phone Edition</p></td>
<td><p>sim</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync Attendant</p></td>
<td><p>sim</p></td>
<td> </td>
</tr>
<tr class="even">
<td><p>Lync para Windows 8</p></td>
<td><p>não</p></td>
<td> </td>
</tr>
<tr class="odd">
<td><p>Lync móvel 2013</p></td>
<td><p>não</p></td>
<td><p>O VoIP deve ser desabilitado para os clientes do Lync Mobile 2013 se usado por usuários com roteamento baseado em local habilitado.</p></td>
</tr>
<tr class="even">
<td><p>Lync móvel 2010</p></td>
<td><p>sim</p></td>
<td> </td>
</tr>
</tbody>
</table>

  

<div>


> [!NOTE]  
> Para desabilitar o VoIP para clientes móveis do Lync 2013, atribua uma política de mobilidade com a configuração, áudio/vídeo IP, desabilitada para todos os usuários habilitados para roteamento baseado em localização. Para obter mais detalhes sobre política de mobilidade, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de Roteamento Baseado em Local no Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

