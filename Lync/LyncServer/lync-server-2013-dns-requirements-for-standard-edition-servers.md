---
title: 'Lync Server 2013: requisitos de DNS para servidores Standard Edition'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Standard Edition servers
ms:assetid: 3d6bbe65-e7ce-491b-a0bd-d2f7197f240d
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425900(v=OCS.15)
ms:contentKeyID: 48183920
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 3132ec1e18d27564f0077e83d411c5b3930c241b
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737361"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a>Requisitos de DNS para servidores de edição padrão no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-19_

Esta seção descreve os registros de sistema de nomes de domínio (DNS) necessários para a implantação de servidores Standard Edition.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Registros de DNS para servidores Standard Edition

A tabela a seguir especifica requisitos de DNS para a implantação do servidor do Lync Server 2013 Standard Edition.

### <a name="dns-requirements-for-a-standard-edition-server"></a>Requisitos de DNS para um servidor Standard Edition

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
<td><p>Um registro interno de um com o nome ucupdates-r2. &lt;Domínio&gt; SIP que é resolvido para o endereço IP do servidor Standard Edition que hospeda o serviço Web de atualização de dispositivo. Na situação em que um dispositivo de comunicação unificada está ativado, mas um usuário nunca se conectou ao dispositivo, o registro a permite que o dispositivo descubra o serviço Web de Hospedagem de dispositivo de hospedagem do servidor e obtenha atualizações. Caso contrário, os dispositivos obtêm essas informações por meio do provisionamento em banda na primeira vez que o usuário faz logon.</p></td>
</tr>
<tr class="even">
<td><p>Um proxy reverso para dar suporte ao tráfego HTTP</p></td>
<td><p>Um registro externo que resolve o FQDN do Web farm externo para o endereço IP externo do proxy reverso. Clientes e dispositivos UC usam esse registro para se conectar ao proxy reverso. Para obter detalhes, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar requisitos de DNS para o Lync Server 2013</a> na documentação de planejamento.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

