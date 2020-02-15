---
title: 'Lync Server 2013: requisitos de DNS para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for mobility
ms:assetid: df6962bc-2a16-440e-a333-022ebd14f957
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690040(v=OCS.15)
ms:contentKeyID: 48185624
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0201a9e8870a1b7d8cc579eb270ca67c929cae5d
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42029602"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Requisitos de DNS para mobilidade com o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-13_

Ao implantar o recurso de mobilidade do Lync Server 2013, você pode usar as novas URLs que estão disponíveis com o serviço de descoberta automática do Microsoft Lync Server 2013 ou você pode usar suas URLs de serviços da Web existentes. Se você usar suas URLs existentes, os usuários precisarão inserir manualmente as URLs em suas configurações de dispositivo móvel. Essa opção normalmente é usada para a solução de problemas. Quando você usa as novas URLs, os clientes móveis podem descobrir automaticamente os recursos do Lync Server 2013. Quando você dá suporte à descoberta automática, precisa adicionar novos registros de DNS (sistema de nomes de domínio). Esta seção descreve os registros DNS necessários para a descoberta automática.

Para oferecer suporte à descoberta automática, você precisa criar os seguintes registros DNS para cada domínio SIP:

  - Um registro DNS interno para suportar usuários móveis que se conectam de dentro da rede da organização

  - Um registro DNS externo ou público para suportar usuários móveis que se conectam pela Internet

A URL de descoberta automática interna não deve ser endereçável de fora da rede. A URL de descoberta automática externa não deve ser endereçável de dentro da rede. No entanto, se você não puder atender a esse requisito para a URL externa, o cliente móvel não deve ser afetado.

Os registros DNS podem ser registros CNAME ou registros A (host).

**Registros DNS internos**

Você precisa criar um dos seguintes registros DNS internos:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nome do host ou definição SRV</th>
<th>Resolve para</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>FQDN (nome de domínio totalmente qualificado) dos serviços Web internos para o seu pool de diretores, se você tiver um, ou para seu pool de front-ends, se não tiver um diretor</p></td>
</tr>
<tr class="even">
<td><p>A (host)</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>Endereço IP de serviços Web interno (endereço IP virtual (VIP) se você usar um balanceador de carga) do seu pool de diretores, se você tiver um, ou do seu pool de front-ends, se não tiver um diretor</p></td>
</tr>
</tbody>
</table>


**Registros DNS externos**

É necessário criar um dos seguintes registros DNS externos:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nome do Host</th>
<th>Resolve para</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>FQDN de serviços Web externos para seu pool de diretor, se você tiver um, ou para seu pool de front-ends se não tiver um diretor</p></td>
</tr>
<tr class="even">
<td><p>A (host)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Endereço IP externo ou público (endereço VIP se você usar um balanceador de carga) do proxy reverso</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls. _tcp. &lt;sipdomain&gt;</p>
<p>Resolve para registro de host (A ou AAAA) do serviço de borda de acesso</p></td>
<td><p>Para dar suporte ao serviço de notificação por push e ao Apple Push Notification Service, você cria um registro SRV para cada domínio SIP que tenha clientes móveis do Microsoft Lync.</p>
<div>

> [!IMPORTANT]  
> Esse requisito aplica-se somente aos clientes móveis do Microsoft Lync em dispositivos móveis baseados em Apple ou Microsoft. Os dispositivos Andriod e Nokia Symbian não usam a notificação por push.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, também conhecido como descoberta automática, o tráfego passa pelo proxy reverso. O registro SRV aponta para um registro que resolve através do serviço de borda de acesso.



</div>

</div>

<span> </span>

</div>

</div>

</div>

