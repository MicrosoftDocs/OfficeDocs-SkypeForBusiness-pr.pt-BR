---
title: 'Lync Server 2013: Requisitos de hardware e de software para o Diretor'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Hardware and software requirements for the Director
ms:assetid: 747b701e-7f97-46fe-91c5-1e8d9addf9f7
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398560(v=OCS.15)
ms:contentKeyID: 48184517
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a3b1b2a3f642c01d3a4743281554834e9ddda55f
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34829079"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="hardware-and-software-requirements-for-the-director-in-lync-server-2013"></a>Requisitos de hardware e de software para o Diretor no Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2012-10-20_

Esta seção detalha os requisitos de hardware e software para o diretor e os cenários de localização compatíveis para o diretor.

<div>

## <a name="hardware-requirements-for-the-director"></a>Requisitos de hardware para o diretor

A tabela a seguir lista os requisitos de hardware para o diretor:

### <a name="hardware-requirements-for-the-director"></a>Requisitos de hardware para o diretor

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
<li><p>processador de 64 bits, Quad-Core, 2,0 GHz ou mais</p></li>
<li><p>processador dual de 64 bits, Dual-Core, 2,0 GHz ou superior</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Memória</p></td>
<td><p>4 gigabytes (GB)</p></td>
</tr>
<tr class="odd">
<td><p>Disco</p></td>
<td><ul>
<li><p>unidade de disco rígido de 10K RPM (HDD)</p></li>
<li><p>Unidade de estado sólido (SSD) de alto desempenho com desempenho igual ou melhor do que o HDD de 10K RPM</p></li>
<li><p>RAID 10 (distribuído e espelhado) 2 mil discos de 15.000 RPM para arquivos de dados de banco de dados</p></li>
</ul></td>
</tr>
<tr class="even">
<td><p>Rede</p></td>
<td><ul>
<li><p>Adaptadores de rede duplos de 1 gigabit por segundo (Gbps) (recomendado)</p></li>
<li><p>Um único adaptador de rede de 1 Gbps (aceito)</p></li>
</ul></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="software-requirements-for-the-director"></a>Requisitos de software para o diretor

A função de diretor pode ser implantada somente em servidores que executam o Lync Server 2013 Enterprise Edition.

Um dos seguintes sistemas operacionais de 64 bits é necessário para os directors:

  - O sistema operacional padrão do Windows Server 2008 R2 com Service Pack 1

  - O sistema operacional Windows Server 2008 R2 Enterprise com Service Pack 1

  - O sistema operacional Windows Server 2008 R2 Datacenter com Service Pack 1

  - O sistema operacional padrão do Windows Server 2012

  - O sistema operacional Windows Server 2012 datacenter

O Lync Server 2013 também exige a instalação dos seguintes programas e atualizações detalhados no tópico [suporte adicional do servidor e requisitos no Lync Server 2013](lync-server-2013-additional-server-support-and-requirements.md).

</div>

<div>

## <a name="supported-collocation"></a>Colocação compatível

A função de servidor diretor não pode ser posicionada com qualquer função de servidor no Lync Server 2013. No entanto, se você não implantar um director, os servidores front-end assumirão a função.

</div>

</div>

<span> </span>

</div>

</div>

</div>

