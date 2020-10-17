---
title: 'Lync Server 2013: Resumo de certificado-proxy reverso'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Reverse proxy
ms:assetid: f2b9a53f-aead-413d-81e9-4a294a010fbb
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205381(v=OCS.15)
ms:contentKeyID: 48185820
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 25e83fb5857988396c3d13d2b07078c654972c92
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/16/2020
ms.locfileid: "48515738"
---
# <a name="certificate-summary---reverse-proxy-in-lync-server-2013"></a>Resumo de certificado-proxy reverso no Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-14_

Os requisitos de certificado para o proxy reverso são muito mais simples do que os servidores de borda. O fluxograma fornecido apresenta os requisitos necessários. A tabela a seguir apresenta os nomes de entidade de certificado típicos e os nomes alternativos da entidade em relação aos cenários que foram revisados nas discussões do servidor de borda. Para obter mais detalhes sobre os cenários de servidor de borda, consulte [cenários para acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md).

**Fluxograma de certificados para proxy reverso**

![Fluxograma de certificados do Servidor de Borda](images/JJ205381.026045d7-1b4b-4651-b32f-2d43a7161198(OCS.15).jpg "Fluxograma de certificados do Servidor de Borda")

### <a name="reverse-proxy-external-interface"></a>Proxy Reverso: Interface Externa

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
<th>Nome da entidade</th>
<th>Ordem/Nome de entidade alternativo (SAN)</th>
<th>Comments</th>
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
<td><p>O certificado deve ser emitido por um CA público e com o EKU do servidor. Os serviços incluem serviço de catálogo de endereços, expansão de grupo de distribuição do Office Web Apps para conferência e regras de publicação de dispositivo IP do Lync. Os nomes de entidade alternativos incluem:</p>
<ul>
<li><p>FQDN de serviços Web externos para o servidor front-end ou o pool de front-ends</p></li>
<li><p>FQDN de serviços Web externos para diretor ou pool de diretor</p></li>
<li><p>Conferência Discada</p></li>
<li><p>Regra de publicação da reunião online</p></li>
<li><p>Office Web Apps para conferência</p></li>
<li><p>Lyncdiscover (Descoberta automática)</p></li>
</ul>
<p>O curinga opcional substitui o SAN discado e reunião</p></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

