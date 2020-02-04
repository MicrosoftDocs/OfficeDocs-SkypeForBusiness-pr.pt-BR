---
title: 'Lync Server 2013: requisitos de DNS para entrada automática do cliente'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for automatic client sign-in
ms:assetid: 3bcd4bb3-a022-4ffa-b005-1a95ad2b1796
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg425884(v=OCS.15)
ms:contentKeyID: 48183873
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6d033621382587367630d9119c2176e976cb2c2d
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41739151"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Requisitos de DNS para entrada automática do cliente no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-19_

Esta seção explica os registros de sistema de nome de domínio (DNS) necessários para a entrada automática do cliente. Ao implantar seus servidores Standard Edition ou pools front-end, você pode configurar seus clientes para usar a descoberta automática para entrar no servidor padrão da edição ou no pool de front-end apropriado. Se você planeja exigir que seus clientes se conectem manualmente ao Lync Server 2013, poderá ignorar este tópico.

Para dar suporte à entrada automática do cliente, você deve:

  - Designe um único servidor ou pool para distribuir e autenticar solicitações de entrada do cliente. Pode ser um servidor ou pool existente em sua organização que hospeda usuários ou você pode designar um servidor ou pool dedicado para essa finalidade que não hospede usuários. Para alta disponibilidade, recomendamos que você designe um pool de front-ends para essa função.

  - Crie um registro SRV DNS interno para dar suporte à entrada automática do cliente para este servidor ou pool.
    
    <div>
    

    > [!NOTE]  
    > Nos seguintes requisitos de registro, o domínio SIP refere-se à porção host dos URIs SIP atribuídos aos usuários. Por exemplo, se URIs SIP forem do formato * @contoso. com, contoso.com será o domínio SIP. O domínio SIP muitas vezes é diferente do domínio interno do Active Directory. Uma organização também pode dar suporte a vários domínios SIP.

    
    </div>

Para habilitar a configuração automática para seus clientes, você deve criar um registro SRV DNS interno que mapeie um dos seguintes registros para o nome de domínio totalmente qualificado (FQDN) do pool de front-ends ou do servidor Standard Edition que distribui solicitações de entrada do Lync clientes

  - \_sipinternaltls. \_TCP. \<domínio\> – para conexões de TLS internas

Você só precisa criar um único registro SRV para o pool de front-end ou o servidor Standard Edition, ou isso distribuirá solicitações de entrada.

A tabela a seguir mostra alguns exemplos de registros necessários para a contoso da empresa fictícia, que oferece suporte a domínios SIP do contoso.com e do retail.contoso.com.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Exemplo de registros DNS necessários para a entrada automática do cliente com vários domínios SIP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN do pool de front-end usado para distribuir solicitações de entrada</th>
<th>Domínio SIP</th>
<th>Registro SRV de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Um registro SRV para o domínio _sipinternaltls. _tcp. contoso. com na porta 5061 que mapeia para pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Um registro SRV para o domínio _sipinternaltls. _tcp. Retail. contoso. com na porta 5061 que mapeia para pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Por padrão, as consultas de registros DNS aderem à correspondência de nome de domínio estrito entre o domínio no nome de usuário e o registro SRV. Se você preferir que as consultas DNS do cliente usem a correspondência de sufixo em vez disso, você pode configurar a política de grupo DisableStrictDNSNaming. Para obter detalhes, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">planejando para clientes e dispositivos no Lync Server 2013</A> na documentação de planejamento.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Exemplo dos certificados e dos registros DNS necessários para a entrada automática do cliente

Este exemplo usa os mesmos nomes de exemplo na tabela anterior. A organização Contoso suporta os domínios SIP do contoso.com e do retail.contoso.com, e todos os seus usuários têm um URI SIP em um dos seguintes formatos:

  - \<usuário\>@retail. contoso.com

  - \<usuário\>@contoso. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

