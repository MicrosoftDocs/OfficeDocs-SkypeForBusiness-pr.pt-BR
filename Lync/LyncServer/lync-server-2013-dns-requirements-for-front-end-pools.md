---
title: 'Lync Server 2013: requisitos de DNS para pools front-end'
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
ms.openlocfilehash: 4b763f9b01e070fc434dae997bc1e2da68dcbc26
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41729411"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="dns-requirements-for-front-end-pools-in-lync-server-2013"></a>Requisitos de DNS para pools front-end no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-11-07_

Esta seção descreve os registros DNS (sistema de nomes de domínio) necessários para a implantação de pools de front-ends.

<div>

## <a name="dns-records-for-front-end-pools"></a>Registros de DNS para pools front-end

A tabela a seguir especifica requisitos de DNS para a implantação de pool de front-end do Lync Server 2013.

### <a name="dns-requirements-for-a-front-end-pool"></a>Requisitos de DNS para um pool de front-ends

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
<td><p>Pool de front-end com vários servidores front-end e balanceador de carga de hardware (se o balanceamento de carga de DNS também é implantado nesse pool)</p></td>
<td><p>Ao usar o balanceamento de carga de DNS e um balanceador de carga de hardware, você precisa hospedar (A) registros. Crie um registro interno que resolva o FQDN (nome de domínio totalmente qualificado) do pool de front-ends para o balanceamento de carga de DNS. Crie um registro de host interno (A) para os serviços internos da Web para o endereço VIP (IP virtual) do balanceador de carga. Você deve usar o nome interno dos serviços Web conforme definido no construtor de topologias.</p>
<p>Por exemplo, se você usar o balanceamento de carga de DNS e o balanceamento de carga de hardware, você teria um registro A para cada servidor front-end em um pool para balanceamento de carga de DNS e um registro A para os serviços Web internos apontando para o IP virtual do balanceador de carga de hardware :</p>
<ul>
<li><p>Balanceamento de carga de DNS: Pool01.contoso.net Endereço IP do pool 10.10.10.5</p>
<div>

> [!WARNING]  
> Cada servidor front-end também terá um registro distinto:


</div>
<ol>
<li><p>FE01.contoso.net 10.10.10.1</p></li>
<li><p>FE02.contoso.net 10.10.10.2</p></li>
<li><p>FE03.contoso.net 10.10.10.3</p></li>
<li><p>FE04.contoso.net 10.10.10.4</p></li>
</ol></li>
<li><p>Balanceamento de carga de hardware: WebInternal.contoso.net Endereço IP de HLB VIP 192.168.10.5</p></li>
</ul>
<p>Todo o tráfego, exceto o tráfego HTTP/HTTPS, usará o registro Pool01.contoso.net. O tráfego HTTP/HTTPS usará o endereço de serviços Web interno definido do 192.168.10.5</p></td>
</tr>
<tr class="even">
<td><p>Pool de front-ends com balanceamento de carga de DNS implantado</p></td>
<td><p>Um conjunto de registros internos que resolvem o FQDN do pool para o endereço IP de cada servidor no pool. Deve haver um registro para cada servidor do pool.</p></td>
</tr>
<tr class="odd">
<td><p>Pool de front-ends com balanceamento de carga de DNS implantado</p></td>
<td><p>Um conjunto de registros internos que resolvem o FQDN de cada servidor no pool para o endereço IP desse servidor. Para obter detalhes, consulte <a href="lync-server-2013-dns-load-balancing.md">balanceamento de carga de DNS no Lync Server 2013</a> na documentação de planejamento.</p></td>
</tr>
<tr class="even">
<td><p>Pool de front-end com um único servidor front-end e um banco de dados back-end dedicado, mas sem balanceador de carga</p></td>
<td><p>Um registro interno que resolve o FQDN do pool de front-end para o endereço IP do servidor front-end do single Enterprise Edition.</p></td>
</tr>
<tr class="odd">
<td><p>Entrada automática do cliente</p></td>
<td><p>Para cada domínio SIP compatível, um registro SRV para _sipinternaltls. _tcp. &lt;domínio&gt; na porta 5061 que mapeia para o FQDN do pool de front-end que autentica e redireciona solicitações do cliente para entrada. Para obter detalhes, consulte <a href="lync-server-2013-dns-requirements-for-automatic-client-sign-in.md">requisitos de DNS para entrada automática do cliente no Lync Server 2013</a>.</p></td>
</tr>
<tr class="even">
<td><p>Descoberta de serviços Web de atualização de dispositivo por dispositivos de comunicação unificada (UC)</p></td>
<td><p>Um registro interno de um com o nome ucupdates-r2. &lt;Domínio&gt; SIP que é resolvido para o endereço IP do pool de front-end que hospeda o serviço Web de atualização de dispositivo. Na situação em que um dispositivo UC está ativado, mas um usuário nunca se conectou ao dispositivo, o registro a permite que o dispositivo descubra o pool de front-end que hospeda o serviço Web de atualização de dispositivo e obtenha atualizações. Caso contrário, os dispositivos obtêm essas informações no modo de provisionamento em banda na primeira vez que um usuário faz logon.</p>
<div>

> [!IMPORTANT]  
> Se você tiver uma implantação existente do serviço Web de atualização de dispositivo no Lync Server 2010, você já criou um registro interno de um com o nome ucupdates. &lt;Domínio&gt;SIP. Para o Microsoft Office Communications Server 2007 R2, você deve criar um registro DNS adicional com o nome ucupdates-r2. &lt;Domínio&gt;SIP.


</div></td>
</tr>
<tr class="odd">
<td><p>Um proxy reverso para dar suporte ao tráfego HTTP</p></td>
<td><p>Um registro externo que resolve o FQDN do Web farm externo para o endereço IP externo do proxy reverso. Clientes e dispositivos UC usam esse registro para se conectar ao proxy reverso. Para obter detalhes, consulte <a href="lync-server-2013-determine-dns-requirements.md">determinar requisitos de DNS para o Lync Server 2013</a> na documentação de planejamento.</p></td>
</tr>
</tbody>
</table>


A tabela a seguir mostra um exemplo dos registros DNS necessários para o FQDN do Web farm interno.

### <a name="example-dns-records-for-internal-web-farm-fqdn"></a>Exemplo de registros DNS para FQDN do Web farm interno

<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>FQDN da Web farm interna</th>
<th>FQDN do pool</th>
<th>DNS A (s) registro (s)</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>webcon.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>DNS um registro para o ee-pool.contoso.com que é resolvido para o endereço VIP do balanceador de carga usado pelos servidores front-end.</p>
<p>DNS um registro para webcon.contoso.com que é resolvido para o endereço VIP do balanceador de carga usado pelos servidores front end.</p></td>
</tr>
<tr class="even">
<td><p>ee-pool.contoso.com</p></td>
<td><p>ee-pool.contoso.com</p></td>
<td><p>DNS um registro para ee-pool.contoso.com que é resolvido para o endereço VIP (IP virtual) do balanceador de carga usado pelos servidores front-end do Enterprise Edition no pool de front-ends.</p>
<p>Observe que, se você estiver usando o balanceamento de carga de DNS nesse pool, o pool de front-end e o Web farm interno não poderão ter o mesmo FQDN.</p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

