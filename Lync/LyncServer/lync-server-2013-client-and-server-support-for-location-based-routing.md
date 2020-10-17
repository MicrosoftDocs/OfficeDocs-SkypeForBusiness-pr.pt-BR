---
title: 'Lync Server 2013: suporte de cliente e servidor para roteamento de Location-Based'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Client and server support for Location-Based Routing
ms:assetid: 26c2ca3d-026d-4dd7-94fa-15ebb4406953
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ994024(v=OCS.15)
ms:contentKeyID: 51803933
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: d85e2ce1738ee5de9d4d542cedd7a9e544771938
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48529338"
---
# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Suporte a cliente e servidor para roteamento de Location-Based no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-06-18_

Location-Based roteamento é imposto pelo Lync Server. O Lync Server pode identificar os sites de rede onde os usuários estão se conectando dentro da rede corporativa. Como os usuários remotos estão fora da rede corporativa, sua localização é considerada desconhecida.

<div>

## <a name="lync-server-support"></a>Suporte ao Lync Server

Location-Based roteamento exige que o Lync Server 2013 CU1 seja implantado em todos os pools de front-ends e servidores Standard Edition em uma determinada topologia. Se o Lync Server 2013 CU1 não estiver instalado em determinados componentes do Lync na topologia, Location-Based restrições de roteamento não poderão ser totalmente impostas.

A tabela a seguir identifica a combinação de funções de servidor e versões compatíveis com o roteamento de Location-Based.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Versão do pool</th>
<th>Versão do servidor de mediação</th>
<th>Com suporte</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync Server 2013 atualização cumulativa de fevereiro de 2013</p></td>
<td><p>Lync Server 2013 atualização cumulativa de fevereiro de 2013</p></td>
<td><p>sim</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 atualização cumulativa de fevereiro de 2013</p></td>
<td><p>Lync Server 2013</p></td>
<td><p>não</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013 atualização cumulativa de fevereiro de 2013</p></td>
<td><p>Lync Server 2010</p></td>
<td><p>não</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2013 atualização cumulativa de fevereiro de 2013</p></td>
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>não</p></td>
</tr>
<tr class="odd">
<td><p>Lync Server 2013</p></td>
<td><p>qualquer</p></td>
<td><p>não</p></td>
</tr>
<tr class="even">
<td><p>Lync Server 2010</p></td>
<td><p>qualquer</p></td>
<td><p>não</p></td>
</tr>
<tr class="odd">
<td><p>Office Communications Server 2007 R2</p></td>
<td><p>qualquer</p></td>
<td><p>não</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="lync-client-support"></a>Suporte ao cliente do Lync

A tabela a seguir identifica os clientes aos quais Location-Based roteamento oferece suporte.


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
<td><p>Incluindo a atualização cumulativa do Lync 2013 fevereiro de 2013</p></td>
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
<td><p>Atendedor do Lync</p></td>
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
<td><p>O VoIP deve estar desabilitado para clientes do Lync Mobile 2013 se for usado por usuários com roteamento de Location-Based habilitado.</p></td>
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
> Para desabilitar o VoIP para clientes do Lync Mobile 2013, atribua uma política de mobilidade com a configuração, áudio/vídeo IP, desabilitada para todos os usuários habilitados para roteamento baseado em local. Para obter mais detalhes sobre a política de mobilidade, consulte <A href="https://docs.microsoft.com/powershell/module/skype/New-CsMobilityPolicy">New-CsMobilityPolicy</A>.



</div>

</div>

<div>

## <a name="see-also"></a>Confira também


[Planejamento de roteamento de Location-Based no Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

