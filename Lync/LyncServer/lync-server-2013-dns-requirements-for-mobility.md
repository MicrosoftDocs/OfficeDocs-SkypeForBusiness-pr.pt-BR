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
ms.openlocfilehash: bc11c79c291f7db7ad9e9e3228644ee27d42e555
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41737381"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-mobility-with-lync-server-2013"></a>Requisitos de DNS para mobilidade com o Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-13_

Ao implantar o recurso de mobilidade do Lync Server 2013, você pode usar as novas URLs disponíveis com o serviço de descoberta automática do Microsoft Lync Server 2013 ou pode usar suas URLs de serviços Web existentes. Se você usar suas URLs existentes, os usuários precisarão inserir manualmente as URLs nas configurações do dispositivo móvel. Essa opção geralmente é usada para solução de problemas. Quando você usa as novas URLs, os clientes móveis podem descobrir automaticamente os recursos do Lync Server 2013. Ao oferecer suporte à descoberta automática, você precisa adicionar novos registros de sistema de nome de domínio (DNS). Esta seção descreve os registros DNS necessários para a descoberta automática.

Para dar suporte à descoberta automática, você precisa criar os seguintes registros DNS para cada domínio SIP:

  - Um registro DNS interno para dar suporte a usuários móveis que se conectam dentro da rede da sua organização

  - Um registro DNS externo ou público para dar suporte a usuários móveis que se conectam à Internet

A URL de descoberta automática interna não deve ser endereçável de fora da rede. A URL de descoberta automática externa não deve ser endereçada dentro da sua rede. No entanto, se você não puder atender a esse requisito para a URL externa, a funcionalidade do cliente móvel não deve ser afetada.

Os registros DNS podem ser registros CNAME ou registros (host).

**Registros DNS internos**

Você precisa criar um dos seguintes registros de DNS interno:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nome do host ou definição de SRV</th>
<th>Resolve para</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>FQDN (nome de domínio totalmente qualificado) dos serviços Web internos para o seu pool de directors, se você tiver um ou para o seu pool de front-end se não tiver um director</p></td>
</tr>
<tr class="even">
<td><p>A (host)</p></td>
<td><p>lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
<td><p>Endereço IP interno dos serviços Web (VIP) se você usar um balanceador de carga) do seu pool de director, se você tiver um ou do seu pool Front-End se não tiver um director</p></td>
</tr>
</tbody>
</table>


**Registros DNS externos**

Você precisa criar um dos seguintes registros de DNS externo:


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Tipo de registro</th>
<th>Nome do host</th>
<th>Resolve para</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CNAME</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>FQDN de serviços Web externos para o seu pool de directors, se você tiver um ou para o seu pool de front-end se não tiver um director</p></td>
</tr>
<tr class="even">
<td><p>A (host)</p></td>
<td><p>lyncdiscover. &lt;sipdomain&gt;</p></td>
<td><p>Endereço IP externo ou público (endereço VIP se você usar um balanceador de carga) do proxy reverso</p></td>
</tr>
<tr class="odd">
<td><p>SRV</p></td>
<td><p>_sipfederationtls._tcp. &lt;sipdomain&gt;</p>
<p>Resolve para registro de host (A ou AAAA) do serviço de borda de acesso</p></td>
<td><p>Para dar suporte ao serviço de notificação por push e ao Apple Push Notification Service, crie um registro SRV para cada domínio SIP que tenha clientes móveis do Microsoft Lync.</p>
<div>

> [!IMPORTANT]  
> Este requisito aplica-se somente aos clientes móveis do Microsoft Lync em dispositivos móveis baseados em Apple ou Microsoft. Os dispositivos Android e Nokia Symbian não usam notificações por push.


</div></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Lyncdiscover, também conhecido como descoberta automática, o tráfego passa pelo proxy reverso. O registro SRV aponta para um registro que é resolvido por meio do serviço de borda de acesso.



</div>

</div>

<span> </span>

</div>

</div>

</div>

