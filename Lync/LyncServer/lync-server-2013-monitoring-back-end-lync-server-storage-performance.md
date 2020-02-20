---
title: 'Lync Server 2013: monitorando o desempenho de armazenamento do Lync Server do back-end'
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
ms.openlocfilehash: e48db772a35177571b1affe7c69674cc7fce07ac
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/19/2020
ms.locfileid: "42149350"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a>Monitorando o desempenho de armazenamento do Lync Server 2013 de back-end

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Última modificação do tópico:** 2014-05-02_

Os bancos de dados de back-end do Lync Server 2013 são uma parte muito importante da implantação do Lync Server 2013. Recomendamos monitorar constantemente os bancos de dados e os respectivos logs de transações para ajudar a garantir que o back-end do Lync Server 2013 seja executado de forma ideal.

A tabela a seguir identifica contadores de desempenho que devem ser monitorados para obter informações sobre o desempenho de armazenamento. Os valores de linha de base desses contadores devem ser determinados primeiro (quando o sistema está em sua carga normal e esperada) para entender as alterações de desempenho quando o sistema é testado.

### <a name="performance-counters-to-be-monitored"></a>Contadores de desempenho a serem monitorados

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Contador de Desempenho</th>
<th>Limites da linha de base</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Transações/seg (RTC)</p></td>
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
<td><p>Transferências de disco/seg (leitura + gravação)-BD RTC</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transferências de disco/s-log RTC</p></td>
<td></td>
</tr>
<tr class="odd">
<td><p>Transferências de disco/s-RTCDyn DB</p></td>
<td></td>
</tr>
<tr class="even">
<td><p>Transferências de disco/log s-RTCDyn</p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

