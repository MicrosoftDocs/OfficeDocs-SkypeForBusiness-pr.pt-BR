---
title: 'Lync Server 2013: Requisitos de certificado para mobilidade'
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
ms.openlocfilehash: 680eaf205959b67d8fef93ff56d379ae8cd293bf
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41736771"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="certificate-requirements-for-mobility-in-lync-server-2013"></a>Requisitos de certificado para mobilidade no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-06-24_

Se você implantar o recurso de mobilidade e oferecer suporte à descoberta automática para clientes móveis, será necessário incluir certas entradas de nomes alternativos de entidades nos certificados para dar suporte a conexões seguras de clientes móveis.

Você precisa incluir entradas de nomes alternativos de entidades para descoberta automática nos seguintes certificados:

  - Pool de diretores

  - Pool de Front-Ends

  - Proxy reverso

Esta seção descreve as entradas de nome alternativo do assunto que são necessárias em seus certificados para descoberta automática.

<div>


> [!NOTE]  
> A emissão de certificados por meio de uma autoridade de certificação interna geralmente é um processo simples, mas adicionar várias entradas de nome alternativo à entidade para certificados públicos usados pelo proxy reverso pode ser caro. Se você tiver muitos domínios SIP, o que faz com que a adição dos nomes alternativos de assunto seja muito cara, você pode configurar o proxy reverso para usar HTTP para a solicitação inicial de serviço de descoberta automática, em vez de usar HTTPS (a configuração padrão). Para obter detalhes, consulte <A href="lync-server-2013-technical-requirements-for-mobility.md">requisitos técnicos de mobilidade no Lync Server 2013</A>.



</div>

### <a name="director-pool-certificate-requirements"></a>Requisitos de certificado do pool do director

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Entrada de nome alternativo do assunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interna do serviço de descoberta automática</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL do serviço de descoberta automática externo</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Você também pode usar SAN = *. &lt;sipdomain&gt;



</div>

### <a name="front-end-pool-certificate-requirements"></a>Requisitos de certificado de pool de front-end

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Descrição</th>
<th>Entrada de nome alternativo do assunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL interna do serviço de descoberta automática</p></td>
<td><p>SAN = lyncdiscoverinternal. &lt;sipdomain&gt;</p></td>
</tr>
<tr class="even">
<td><p>URL do serviço de descoberta automática externo</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Você também pode usar SAN = *. &lt;sipdomain&gt;



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
<th>Entrada de nome alternativo do assunto</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>URL do serviço de descoberta automática externo</p></td>
<td><p>SAN = lyncdiscover. &lt;sipdomain&gt;</p></td>
</tr>
</tbody>
</table>


<div>


> [!NOTE]  
> Você atribui esta SAN ao certificado atribuído ao ouvinte SSL no proxy reverso.



</div>

<div>


> [!NOTE]  
> Seu ouvinte de proxy reverso terá nomes alternativos de entidades para seus serviços Web externos (por exemplo, SAN = lyncwebextpool01. contoso. com e dirwebexternal.contoso.com se você tiver implantado o diretor opcional).



</div>

</div>

<span> </span>

</div>

</div>

</div>

