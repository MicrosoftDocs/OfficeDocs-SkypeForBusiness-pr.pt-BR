---
title: 'Lync Server 2013: requisitos de certificado para mobilidade'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Certificate requirements for mobility
ms:assetid: bb0e97af-cf60-4271-a0ab-654429d884ea
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Hh690044(v=OCS.15)
ms:contentKeyID: 48185251
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 5c3bf95f87fa663331f05861f91cd7f7f19a2728
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42135247"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Requisitos de certificado para mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-06-24_

Se você implantar o recurso de mobilidade e suportar a descoberta automática para clientes móveis, será necessário incluir determinadas entradas de nome de entidade alternativo nos certificados a fim de suportar conexões seguras de clientes móveis.

É necessário incluir entradas de nome de entidade alternativo para a descoberta automática nos certificados a seguir:

  - Director pool

  - Pool de Front-Ends

  - Proxy reverso

Esta seção descreve as entradas de nome de entidade alternativo necessárias em seus certificados para descoberta automática.

<div>


> [!NOTE]  
> A reemissão de certificados usando uma autoridade de certificação interna é normalmente um processo simples, mas a adição de múltiplas entradas de nome de entidade alternativo aos certificados públicos usados pelo proxy reverso pode ser cara. Se você tiver muitos domínios SIP, tornando a adição de nomes de entidade alternativos muito cara, será possível configurar o proxy reverso para usar HTTP para a solicitação do Serviço de Descoberta Automática, em vez de usar HTTPS (a configuração padrão). Para obter detalhes, consulte <A href="lync-server-2013-technical-requirements-for-mobility.md">Technical Requirements for Mobility in Lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Requisitos de certificado do Pool de Diretores

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Entrada de nome de entidade alternativo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interna do serviço de Descoberta Automática</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL externa do serviço de Descoberta Automática</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Como alternativa, você pode usar SAN = *. &lt;sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisitos de certificado do pool Front-End

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Entrada de nome de entidade alternativo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interna do serviço de Descoberta Automática</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL externa do serviço de Descoberta Automática</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Como alternativa, você pode usar SAN = *. &lt;sipdomain&gt;



</div>

### <a name="reverse-proxy-public-ca-certificate-requirements"></a>Requisitos de certificado de proxy reverso (CA pública)

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Entrada de nome de entidade alternativo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL externa do serviço de Descoberta Automática</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Atribua esse SAN ao certificado atribuído ao Ouvinte de SSL no proxy reverso.



</div>

<div>


> [!NOTE]  
> Seu ouvinte de proxy reverso terá nomes alternativos de entidade para suas URLs de serviços Web externos (por exemplo, SAN = lyncwebextpool01. contoso. com e dirwebexternal.contoso.com se você tiver implantado o diretor opcional).



</div>

</div>

<span> </span>

</div>

</div>

</div>

