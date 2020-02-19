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
ms.openlocfilehash: f7007c06835f0b942411d5200a20ef24c393e600
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42131804"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-standard-edition-servers-in-lync-server-2013"></a>Requisitos de DNS para servidores Standard Edition no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-19_

Esta seção descreve os registros DNS necessários para a implantação de servidores Standard Edition.

<div>

## <a name="dns-records-for-standard-edition-servers"></a>Registros DNS para servidores Standard Edition

A tabela a seguir especifica os requisitos de DNS para a implantação do servidor do Lync Server 2013 Standard Edition.

### <a name="dns-requirements-for-a-standard-edition-server"></a>Requisitos de DNS para um servidor Standard Edition

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cenário da implantação</th>
<th>Requisito de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servidor Standard Edition</p></td>
<td><p>Um registro A interno que resolva o FQDN (nome de domínio totalmente qualificado) do servidor como o respectivo endereço IP.</p></td>
</tr>
<tr class="even">
<td><p>Entrada automática do cliente</p></td>
<td><p>Para cada domínio SIP com suporte, um registro SRV para _sipinternaltls. _tcp. &lt;domínio&gt; sobre a porta 5061 que mapeia para o FQDN do servidor Standard Edition que autentica e redireciona as solicitações do cliente para entrada. Para obter detalhes, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS Requirements for Automatic Client Sign-in in Lync Server 2013</a>.</p></td>
</tr>
<tr class="odd">
<td><p>Descoberta do serviço Web de Atualização de Dispositivo por dispositivos de UC (comunicações unificadas)</p></td>
<td><p>Um registro A interno com o nome ucupdates-r2. &lt;Domínio&gt; SIP que resolve para o endereço IP do servidor Standard Edition que hospeda o serviço Web de atualização de dispositivo. Na situação em que um dispositivo de UC esteja ativado, mas um usuário nunca tenha feito logon no dispositivo, o registro A permite que o dispositivo descubra o servidor que hospeda o serviço Web de Atualização de Dispositivo e obtenha atualizações. Caso contrário, os dispositivos obtêm as informações do servidor através do provisionamento em banda na primeira vez que um usuário faz logon.</p></td>
</tr>
<tr class="even">
<td><p>Um proxy reverso para dar suporte ao tráfego HTTP</p></td>
<td><p>Um registro A externo que resolva o FQDN da Web farm externa como o endereço IP externo do proxy reverso. Os clientes e os dispositivos de UC usam esse registro para se conectar ao proxy reverso. Para obter detalhes, consulte <a href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</a> na documentação de planejamento.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

