---
title: 'Lync Server 2013: requisitos de hardware e software para o diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 32c4e241c7fd991fc217aaf2e1f2bd0ee9e37aab
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/15/2020
ms.locfileid: "42030324"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Requisitos de hardware e software para o diretor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2012-10-20_

Esta seção detalha os requisitos de hardware e software para o diretor e os cenários de colocação com suporte para o diretor.

<div>

## <a name="hardware-requirements-for-the-director"></a>Requisitos de hardware por Diretor

A tabela a seguir lista os requisitos de hardware para o diretor:

### <a name="hardware-requirements-for-the-director"></a>Requisitos de hardware por Diretor

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Componente de hardware</th>
<th>Requisitos mínimos</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>CPU</p></td>
<td><ul>
<li><p>Processador de 64 bits, quad-core, 2.0 GHz ou superior</p></li>
<li><p>Processador 64 bits dual, dual-core, 2.0 GHz ou superior</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memória</p></td>
<td><p>4 GB</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>Disco rígido (HDD) de10K de RPM</p></li>
<li><p>Drive de estado sólido (SSD) de alto desempenho com desempenho igual ou superior a 10K RPM HDD</p></li>
<li><p>Discos para arquivos de dados do banco de dados de 2 x RAID 10 (distribuídos e espelhados), 15.000 de RPM</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rede</p></td>
<td><ul>
<li><p>Adaptadores de rede Dual 1 Gbps (recomendado)</p></li>
<li><p>Adaptador de rede de 1 Gbps único (suportado)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Requisitos de software para o diretor

A função diretor pode ser implantada somente em servidores que executam o Lync Server 2013 Enterprise Edition.

Um dos seguintes sistemas operacionais de 64 bits é necessário para os diretores:

  - O sistema operacional Windows Server 2008 R2 Standard com Service Pack 1

  - O sistema operacional Windows Server 2008 R2 Enterprise com Service Pack 1

  - O sistema operacional Windows Server 2008 R2 Datacenter com Service Pack 1

  - O sistema operacional Windows Server 2012 Standard

  - O sistema operacional Windows Server 2012 datacenter

O Lync Server 2013 também exige a instalação dos seguintes programas e atualizações detalhados no tópico [suporte adicional de servidor e requisitos no Lync server 2013](lync-server-2013-additional-server-support-and-requirements.md).

</div>

<div>

## <a name="supported-collocation"></a>Colocação suportada

A função de servidor diretor não pode ser posicionada com qualquer outra função de servidor no Lync Server 2013. No entanto, se você não implantar um diretor, os servidores front-end assumirão a função.

</div>

</div>

<span> </span>

</div>

</div>

</div>

