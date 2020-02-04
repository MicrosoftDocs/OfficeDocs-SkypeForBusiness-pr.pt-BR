---
title: 'Lync Server 2013: Requisitos de DNS para servidor Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for a Standard Edition server
ms:assetid: 5d1daf54-6e60-4ce0-9254-7d57a0835fa4
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204936(v=OCS.15)
ms:contentKeyID: 48184259
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3ab4280ca3ed329d0dc926756f6bfd933595ca08
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739171"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-a-standard-edition-server-in-lync-server-2013"></a>Requisitos de DNS para servidor Standard Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-22_

Esta seção descreve os registros de sistema de nomes de domínio (DNS) necessários para a implantação de servidores Standard Edition.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Registros de DNS para servidores Standard Edition

A tabela a seguir especifica requisitos de DNS para a implantação do servidor do Lync Server 2013 Standard Edition.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cenário da implantação</th>
<th>Requisitos de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor Standard Edition</p></td>
<td><p>Um registro A interno que resolve o nome de domínio totalmente qualificado (FQDN) do servidor para seu endereço IP.</p></td>
</tr>
<tr class="even">
<td><p>Entrada automática do cliente</p></td>
<td><p>Para cada domínio SIP compatível, um registro SRV para _sipinternaltls. _tcp. &lt;domínio&gt; na porta 5061 que mapeia para o FQDN do servidor Standard Edition que autentica e redireciona solicitações do cliente para entrar. Para obter detalhes, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisitos de DNS para entrada automática do cliente no Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Descoberta de serviços Web de atualização de dispositivo por dispositivos de comunicação unificada (UC)</p></td>
<td><p>Um registro interno de um com o nome ucupdates-r2. &lt;Domínio&gt; SIP que é resolvido para o endereço IP do servidor Standard Edition que hospeda o serviço Web de atualização de dispositivo. Na situação em que um dispositivo de comunicação unificada está ativado, mas um usuário nunca se conectou ao dispositivo, o registro a permite que o dispositivo descubra o serviço Web de Hospedagem de dispositivo de hospedagem do servidor e obtenha atualizações. Caso contrário, os dispositivos obtêm essas informações por meio do provisionamento em banda na primeira vez que o usuário faz logon. Para obter detalhes, consulte <a href="lync-server-2013-device-update-web-service.md">serviço Web de atualização de dispositivo no Lync Server 2013</a> na documentação de operações.</p></td>
</tr>
<tr class="even">
<td><p>Um proxy reverso para dar suporte ao tráfego HTTP</p></td>
<td><p>Um registro externo que resolve o FQDN do Web farm externo para o endereço IP externo do proxy reverso. Clientes e dispositivos UC usam esse registro para se conectar ao proxy reverso. Para obter detalhes, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar requisitos de DNS para o Lync Server 2013</a> na documentação de planejamento.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Requisitos de DNS para entrada automática do cliente no Lync Server 2013](lync-server-2013-dns-requirements-for-automatic-client-sign-in.md)  
[Determinar requisitios de DNS para Lync Server 2013](lync-server-2013-determine-dns-requirements.md)  


[Serviço Web de Atualização de Dispositivo no Lync Server 2013](lync-server-2013-device-update-web-service.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

