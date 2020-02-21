---
title: 'Lync Server 2013: requisitos de DNS para pools de front-ends'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: DNS requirements for Front End pools
ms:assetid: ba28919c-fbbe-4c54-8bf9-2b0cd3fa39c7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412910(v=OCS.15)
ms:contentKeyID: 48185228
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0ae56cdf07ae76ca0499050574793421864de818
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/21/2020
ms.locfileid: "42209317"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Requisitos de DNS para pools de front-ends no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-11-07_

Esta seção descreve os registros de DNS (Sistema de Nomes de Domínio) necessários para a implantação dos pools de Front-Ends.

<div>

## <a name="dns-records-for-front-end-pools"></a>Registros DNS para pools Front-End

A tabela a seguir especifica os requisitos de DNS para uma implantação de pool de front-ends do Lync Server 2013.

### <a name="dns-requirements-for-a-front-end-pool"></a>Requisitos DNS para um pool Front-End

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
<td><p>Pool Front-End com múltiplos servidores Front-End e um balanceador de carga de hardware (mesmo que o balanceamento de carga DNS também esteja implantado nesse pool)</p></td>
<td><p>Ao usar um balanceador de carga DNS e um balanceador de carga de hardware, é necessário Hospedar (A) registros. Criar um registro A interno que resolve o FQDN (nome de domínio totalmente qualificado) do pool de Front-ends para o balanceamento de carga DNS. Criar um registro de host interno (A) para os serviços da Web interno para o endereço de IP virtual (VIP) do balanceador de carga. Você deve usar o nome de serviços Web internos, conforme definido no construtor de topologias.</p>
<p>Por exemplo, se você usar o balanceamento de carga DNS e o balanceamento de carga de hardware, você terá um registro A para cada servidor de front-end em um pool para balanceamento de carga DNS e um registro A para os serviços Web internos apontando para o IP virtual do balanceador de carga de hardware :</p>
<ul>
<li><p>Balanceamento de carga DNS:   Pool01.contoso.net   Endereço IP do pool   10.10.10.5</p>
<div>

> [!WARNING]  
> Cada servidor de front-end também terá um registro A distinto:


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>Balanceamento de carga de hardware:   WebInternal.contoso.net   Endereço IP de HLB VIP   192.168.10.5</p></li>
</ul>
<p>Todo o tráfego, exceto o tráfego HTTP/HTTPS, usará o registro Pool01.contoso.net. O tráfego HTTP/HTTPS usará o endereço de serviço da Web interno definido de 192.168.10.5</p></td>
</tr>
<tr class="even">
<td><p>Pool Front-End com balanceamento de carga DNS implantado</p></td>
<td><p>Um conjunto de registros A internos que resolvem o FQDN do pool para o endereço IP de cada servidor no pool. É preciso ter um registro A para cada servidor no pool.</p></td>
</tr>
<tr class="odd">
<td><p>Pool Front-End com balanceamento de carga DNS implantando</p></td>
<td><p>Um conjunto de registros A internos que resolvem o FQDN de cada servidor no pool para o endereço IP desse servidor. Para obter detalhes, consulte <a href="lync-server-2013-dns-load-balancing.md">DNS Load Balancing in Lync Server 2013</a> na documentação de planejamento.</p></td>
</tr>
<tr class="even">
<td><p>Pool Front-End com um único Servidor Front-End e um banco de dados back-end dedicado, mas sem balanceador de carga</p></td>
<td><p>Um registro A interno que resolve o FQDN do pool Front-End para o endereço IP do Servidor Front-End Enterprise Edition único.</p></td>
</tr>
<tr class="odd">
<td><p>Entrada automática do cliente</p></td>
<td><p>Para cada domínio SIP com suporte, um registro SRV para _sipinternaltls. _tcp. &lt;domínio&gt; sobre a porta 5061 que mapeia para o FQDN do pool de front-ends que autentica e redireciona as solicitações do cliente para entrada. Para obter detalhes, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">DNS Requirements for Automatic Client Sign-in in Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>Descoberta do serviço Web de Atualização de Dispositivo por dispositivos de UC (comunicações unificadas)</p></td>
<td><p>Um registro A interno com o nome ucupdates-r2. &lt;Domínio&gt; SIP que resolve para o endereço IP do pool de front-ends que hospeda o serviço Web de atualização de dispositivo. Na situação na qual um dispositivo UC é ativado, mas um usuário nunca entrou no dispositivo, o registro A permite que o dispositivo descubra o pool Front-End que hospeda o Serviço Web de Atualização de Dispositivo e obtenha atualizações. Caso contrário, os dispositivos obtêm essas informações por meio do fornecimento em banda na primeira vez que um usuário faz login.</p>
<div>

> [!IMPORTANT]  
> Se você tiver uma implantação existente do serviço Web de atualização de dispositivo no Lync Server 2010, você já criou um registro A interno com o nome ucupdates. &lt;Domínio&gt;SIP. Para o Microsoft Office Communications Server 2007 R2, você deve criar um registro DNS A adicional com o nome ucupdates-r2. &lt;Domínio&gt;SIP.


</div></td>
</tr>
<tr class="odd">
<td><p>Um proxy reverso para dar suporte ao tráfego HTTP</p></td>
<td><p>Um registro A externo que resolva o FQDN da Web farm externa como o endereço IP externo do proxy reverso. Os clientes e os dispositivos de UC usam esse registro para se conectar ao proxy reverso. Para obter detalhes, consulte <a href="lync-server-2013-determine-dns-requirements.md">determine DNS Requirements for Lync Server 2013</a> na documentação de planejamento.</p></td>
</tr>
</tbody>
</table>


A tabela a seguir mostra um exemplo dos registros DNS exigidos para o FQDN da web farm interna.

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>Exemplos de registros DNS para FQDN da web farm interna

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN da web farm interna</th>
<th>FQDN do pool</th>
<th>Registro(s) A de DNS</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Registro A de DNS do ee-pool.contoso.com que se resolva como o endereço VIP do balanceador de carga usado pelos Servidores Front-End.</p>
<p>Registro A de DNS do webcon.contoso.com que se resolva como o endereço VIP do balanceador de carga usado pelos Servidores Front-End.</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>Registro A de DNS do ee-pool.contoso.com que se resolva como o endereço VIP (IP virtual) do balanceador de carga usado pelos servidores Enterprise Edition no pool Front-End.</p>
<p>Observe que se você estiver usando o balanceamento de carga DNS nesse pool, seu pool Front-End e web farm interna não poderão ter o mesmo FQDN.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

