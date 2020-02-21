---
title: 'Lync Server 2013: suporte de cliente e servidor para roteamento baseado em local'
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
ms.openlocfilehash: daf0fb3656a5a57a5e4c7a6c25b7a08d29f79e86
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42197844"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="client-and-server-support-for-location-based-routing-in-lync-server-2013"></a>Suporte a cliente e servidor para roteamento baseado em local no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2013-06-18_

O roteamento baseado em local é imposto pelo Lync Server. O Lync Server pode identificar os sites de rede onde os usuários estão se conectando dentro da rede corporativa. Como os usuários remotos estão fora da rede corporativa, sua localização é considerada desconhecida.

<div>

## <a name="lync-server-support"></a>Suporte ao Lync Server

O roteamento baseado em local exige que o Lync Server 2013 CU1 seja implantado em todos os pools de front-ends e servidores Standard Edition em uma determinada topologia. Se o Lync Server 2013 CU1 não estiver instalado em determinados componentes do Lync na topologia, as restrições de roteamento baseadas em local não poderão ser totalmente impostas.

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

A tabela a seguir identifica os clientes com suporte para roteamento baseado em local.


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
<td><p>O VoIP deve estar desabilitado para clientes do Lync Mobile 2013 se for usado por usuários com roteamento baseado em local habilitado.</p></td>
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


[Planejamento de roteamento baseado em local no Lync Server 2013](lync-server-2013-planning-for-location-based-routing.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

