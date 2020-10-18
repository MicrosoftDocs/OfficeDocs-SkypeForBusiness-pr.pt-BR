---
title: 'Lync Server 2013: clientes com suporte de implantações anteriores'
description: 'Lync Server 2013: clientes com suporte de implantações anteriores.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Supported clients from previous deployments
ms:assetid: 69d427f8-57a5-4244-b2ed-f2eb7600285e
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398499(v=OCS.15)
ms:contentKeyID: 48184390
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5f83723a571bb63cb012d6ef8a8b502af2717213
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48575317"
---
# <a name="supported-clients-from-previous-deployments-in-lync-server-2013"></a>Clientes com suporte de implantações anteriores no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-12-14_

Em um cenário de coexistência, os clientes do Lync Server 2013 podem interagir com clientes de versões anteriores do Lync Server e Office Communications Server. Diferentemente das versões anteriores, o Lync Server 2010 oferece suporte aos novos clientes do Lync 2013. Isso permite que as organizações que estão atualizando do Lync Server 2010 distribuem novos clientes independentemente das atualizações do Lync Server.

<div>

## <a name="supported-server-and-client-combinations"></a>Combinações de servidor e cliente com suporte

A tabela a seguir mostra as combinações com suporte das versões de cliente e de servidor. O Lync Server 2013 oferece suporte a duas versões anteriores do cliente e o Lync Server 2010 oferece suporte ao novo cliente do Lync 2013.


<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Cliente</th>
<th>Lync Server 2013</th>
<th>Lync Server 2010</th>
<th>Office Communications Server 2007 R2</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Lync 2013</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2013</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="even">
<td><p>Lync 2010 Attendant</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="odd">
<td><p>Chat de grupo do Lync 2010</p></td>
<td><p>Não aplicável</p></td>
<td><p>Supported1</p></td>
<td><p>Não aplicável</p></td>
</tr>
<tr class="even">
<td><p>Lync Web App 2010</p></td>
<td><p>Não suportado</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="odd">
<td><p>Lync 2010 Attendee</p></td>
<td><p>Não Supported2</p></td>
<td><p>Com suporte</p></td>
<td><p>Não Suportado</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007 R2</p></td>
<td><p>Interoperable3</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
</tr>
<tr class="odd">
<td><p>Microsoft Office Communications Server 2007 R2 Attendant</p></td>
<td><p>Não suportado</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
</tr>
<tr class="even">
<td><p>Office Communicator 2007</p></td>
<td><p>Não suportado</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
</tr>
<tr class="odd">
<td><p>Office Live Meeting 2007</p></td>
<td><p>Não suportado</p></td>
<td><p>Com suporte</p></td>
<td><p>Com suporte</p></td>
</tr>
</tbody>
</table>


1In Microsoft Lync Server 2010, a funcionalidade de chat de grupo estava disponível com o servidor de chat de grupo, um aplicativo confiável de terceiros para o Lync Server 2010. Os clientes do Lync 2013 não são compatíveis com o Lync Server 2010, o chat de grupo.

o 2Lync Web App 2013 agora fornece uma experiência de reunião completa, incluindo áudio e vídeo do computador e é considerado como substituto para o participante do Lync 2010.

os recursos de presença e IM do 3The no Office Communicator 2007 R2 são compatíveis com o Lync Server 2013, mas os recursos de conferência não. Durante a migração do Office Communications Server 2007 R2, o Office Communicator 2007 R2 é adequado para a interoperabilidade de presença e de mensagens instantâneas, mas os usuários devem usar o Lync Web App 2013 para ingressar em reuniões do Lync Server 2013.

<div>


> [!NOTE]  
> Para obter detalhes sobre a capacidade dos clientes do Lync Server 2013 coexistirem e interagirem com clientes de versões anteriores do Lync Server e Office Communications Server, confira <A href="lync-server-2013-client-interoperability-in-lync-2013.md">interoperabilidade do cliente no Lync 2013</A> na documentação de planejamento.



</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

