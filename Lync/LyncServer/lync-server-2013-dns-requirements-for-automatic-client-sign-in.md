---
title: 'Lync Server 2013: requisitos de DNS para entrada automática de cliente'
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
ms.openlocfilehash: 5464fbef2586467ee922d61bdaa3a09b591c88b4
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42150660"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-automatic-client-sign-in-in-lync-server-2013"></a>Requisitos de DNS para entrada de cliente automática no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-19_

Esta seção explica os registros do DNS (Sistema de Nomes de Domínio) que são necessários para entrada automática de clientes. Quando você implanta servidores Standard Edition ou pools de Front-Ends, é possível configurar os clientes para que eles usem a descoberta automática para entrar no servidor Standard Edition ou no pool Front-End. Se você planeja exigir que seus clientes se conectem manualmente ao Lync Server 2013, você pode ignorar este tópico.

Para dar suporte à entrada automática de clientes, você deve:

  - Designar um único servidor ou pool para distribuir e autenticar as solicitações de entrada dos clientes. Ele pode ser um servidor ou pool existente em sua organização que hospede usuários, ou você pode designar para essa finalidade um servidor ou pool dedicado que não hospede usuários. Para que haja alta disponibilidade, recomendamos que você designe um pool Front-End para essa função.

  - Criar um registro SRV de DNS interno para dar suporte à entrada automática de clientes nesse servidor ou pool.
    
    <div>
    

    > [!NOTE]  
    > Nos requisitos de registro a seguir, o domínio SIP se refere à parte de host dos URIs do SIP atribuídos aos usuários. Por exemplo, se os URIs do SIP estiverem no formato *@contoso.com, contoso.com será o domínio SIP. O domínio SIP é geralmente diferente do domínio interno do Active Directory. Uma organização também poderá oferecer suporte a vários domínios SIP.

    
    </div>

Para habilitar a configuração automática para seus clientes, você deve criar um registro SRV de DNS interno que mapeia um dos seguintes registros para o nome de domínio totalmente qualificado (FQDN) do pool de front-ends ou servidor Standard Edition que distribui solicitações de entrada do Lync nos

  - \_sipinternaltls. \_TCP. \<domínio\> -para conexões TLS internas

Você só precisa criar um único registro SRV para o pool Front-End ou servidor Standard Edition que distribuirá as solicitações de entrada.

A tabela a seguir mostra alguns exemplos de registros necessários para a empresa fictícia Contoso, que oferece suporte aos domínios SIP contoso.com e retail.contoso.com.

### <a name="example-of-dns-records-required-for-automatic-client-sign-in-with-multiple-sip-domains"></a>Exemplo de registros DNS necessários para entrada automática de clientes com vários domínios SIP

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN do pool Front-End usado para distribuir solicitações de entrada</th>
<th>Domínio SIP</th>
<th>Registro SRV de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>pool01.contoso.com</p></td>
<td><p>contoso.com</p></td>
<td><p>Um registro SRV para o domínio _sipinternaltls._tcp.contoso.com através da porta 5061 que mapeie para pool01.contoso.com</p></td>
</tr>
<tr class="even">
<td><p>pool01.contoso.com</p></td>
<td><p>retail.contoso.com</p></td>
<td><p>Um registro SRV para o domínio _sipinternaltls._tcp.retail.contoso.com através da porta 5061 que mapeie para pool01.contoso.com</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Por padrão, as consultas de registros DNS seguem uma correspondência estrita de nomes de domínio entre o domínio no nome do usuário e o registro SRV. Se, em vez disso, você preferir que as consultas de DNS dos clientes usem a correspondência de sufixo, poderá configurar a política de grupo DisableStrictDNSNaming. Para obter detalhes, consulte <A href="lync-server-2013-planning-for-clients-and-devices.md">Planning for clients and Devices in Lync Server 2013</A> na documentação de planejamento.



</div>

<div>

## <a name="example-of-the-certificates-and-dns-records-required-for-automatic-client-sign-in"></a>Exemplo dos certificados e dos registros DNS necessários para a entrada automática de clientes

Esse exemplo usa os mesmos nomes de exemplo da tabela anterior. A organização Contoso oferece suporte aos domínios SIP contoso.com e retail.contoso.com, e todos os seus usuários têm um URI do SIP em um dos seguintes formatos:

  - \<@retail\>de usuário. contoso.com

  - \<usuário\>@contoso. com

</div>

</div>

<span> </span>

</div>

</div>

</div>

