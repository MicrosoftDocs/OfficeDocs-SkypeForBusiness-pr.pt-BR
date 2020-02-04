---
title: 'Lync Server 2013: Resumo do certificado-conectividade de mensagens instantâneas públicas'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate summary - Public instant messaging connectivity
ms:assetid: 2b3687ee-50c2-4c1c-880e-8dcf8bd4f309
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ618370(v=OCS.15)
ms:contentKeyID: 49105657
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c93e79eed643d608ac9ab04516222227fc7c1f6
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736631"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-summary---public-instant-messaging-connectivity-in-lync-server-2013"></a>Resumo do certificado-conectividade de mensagens instantâneas públicas no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2013-02-19_

Para configurar certificados para conectividade de mensagens instantâneas públicas, primeiro você deve observar que não há nada diferente de outros tipos de Federação SIP ou até mesmo dos certificados de servidor de borda padrão, exceto que o America Online (AOL) requer um único configuração de certificado. Além do uso de chave avançada (EKU) do servidor usual, a America Online exige que o certificado ou certificados (no caso de um pool de bordas) também contenham o EKU do cliente. O EKU do cliente é uma adição ao certificado e faz parte do certificado público externo atribuído ao seu servidor de borda.

<div>

## <a name="certificate-summary--public-instant-messaging-connectivity"></a>Resumo do certificado – conectividade de mensagens instantâneas públicas


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
<th>Nomes alternativos de assunto (SAN)/Order</th>
<th>Comentários</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Borda externa/de acesso</p></td>
<td><p>sip.contoso.com</p></td>
<td><p>sip.contoso.com</p>
<p>webcon.contoso.com</p>
<p>sip.fabrikam.com</p></td>
<td><p>O certificado deve ser de uma CA pública e deve ter o EKU do servidor e o cliente EKU se a conectividade de IM pública com AOL for implantada. O certificado é atribuído às interfaces do servidor de borda externo para:</p>
<ul>
<li><p>Serviço de Borda de Acesso</p></li>
<li><p>Serviço de Borda de Webconferência</p></li>
<li><p>Serviço de Borda A/V</p></li>
</ul>
<p>Observe que as SANs são adicionadas automaticamente ao certificado com base em suas definições no construtor de topologias. Você adiciona entradas de SAN conforme necessário para domínios SIP adicionais e outras entradas de que você precisa para dar suporte. O nome do requerente é replicado na SAN e deve estar presente para a operação correta.</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="see-also"></a>Confira também


[Cenários de acesso de usuário externo no Lync Server 2013](lync-server-2013-scenarios-for-external-user-access.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

