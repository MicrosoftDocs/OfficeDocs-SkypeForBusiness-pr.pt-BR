---
title: 'Lync Server 2013: Resumo de certificado - Proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b9a10259ac4a0beb6d79897b26bf446b109801a8
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34836642"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Resumo de certificado - Proxy reverso no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-14_

Os requisitos de certificado para o proxy reverso são muito mais simples do que os servidores de borda. O fluxograma fornecido apresenta os requisitos necessários. A tabela a seguir apresenta nomes de entidades de certificado típicos e nomes alternativos de assunto em relação aos cenários em que foi revisado nas discussões do servidor de borda. Para obter mais detalhes sobre os cenários do servidor de borda, consulte [cenários para acesso de usuários externos no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Fluxograma de certificados para proxy reverso**

![Fluxograma de certificados do servidor de borda] (images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Fluxograma de certificados do servidor de borda")

### <a name="reverse-proxy-external-interface"></a>Proxy inverso: interface externa

<table>
<colgroup>
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
<col style="width: 25%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente</th>
<th>Nome do assunto</th>
<th>Nome alternativo do assunto (SAN)/Order</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Proxy reverso</p></td>
<td><p>webext.contoso.com</p></td>
<td><p>webext.contoso.com</p>
<p>webdirext.contoso.com</p>
<p>dialin.contoso.com</p>
<p>meet.contoso.com</p>
<p>officewebapps01.contoso.com</p>
<p>lyncdiscover.contoso.com</p>
<p>(Opcional):*. contoso.com</p></td>
<td><p>O certificado deve ser emitido por uma CA pública e com o EKU do servidor. Serviços incluem serviço de catálogo de endereços, expansão do grupo de distribuição Office Web Apps para conferência e regras de publicação de dispositivo IP do Lync. O nome alternativo para o assunto inclui:</p>
<ul>
<li><p>FQDN de serviços Web externos para servidor front-end ou pool de front-end</p></li>
<li><p>FQDN de serviços Web externos para o diretor ou pool do diretor</p></li>
<li><p>Conferência discada</p></li>
<li><p>Regra de publicação de reunião online</p></li>
<li><p>Office Web Apps para conferência</p></li>
<li><p>Lyncdiscover (descoberta automática)</p></li>
</ul>
<p>O curinga opcional substitui a SAN e a discagem</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

