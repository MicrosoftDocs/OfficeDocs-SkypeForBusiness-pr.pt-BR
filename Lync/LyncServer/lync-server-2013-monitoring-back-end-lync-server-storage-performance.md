---
title: 'Lync Server 2013: monitorando o desempenho de armazenamento do Lync Server back-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7c4d3741564cd0228213400d7ee1fbb7271c4ddd
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/04/2020
ms.locfileid: "41756855"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Monitorando o back-end do Lync Server 2013 Storage performance

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Tópico da última modificação:** 2014-05-02_

Os bancos de dados back-end do Lync Server 2013 são uma parte muito importante da implantação do Lync Server 2013. Recomendamos que você monitore constantemente os bancos de dados e os respectivos registros de transações para ajudar a garantir que o back-end do Lync Server 2013 seja executado de forma ideal.

A tabela a seguir identifica contadores de desempenho que devem ser monitorados para obter informações sobre o desempenho do armazenamento. Os valores da linha de base desses contadores devem ser determinados primeiro (quando o sistema está em sua carga normal, esperada) para entender as alterações de desempenho quando o sistema é testado.

### <a name="performance-counters-to-be-monitored"></a>Contadores de desempenho a serem monitorados

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contador de desempenho</th>
<th>Limites da linha de base</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transações/s (RTC)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transações/s (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transações/s (tempdb)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Liberações de log/s (RTC)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Liberações de log/s (RTCDyn)</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Liberações de log/s (tempdb)</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transferências de disco/s (leitura + gravação)-BD RTC</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transferências de disco/s-log de RTC</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transferências de disco/s-RTCDyn DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transferências de disco/log SEC-RTCDyn</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

