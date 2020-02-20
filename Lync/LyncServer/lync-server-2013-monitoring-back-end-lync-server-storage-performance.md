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

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="560e4-102">Monitorando o desempenho de armazenamento do Lync Server 2013 de back-end</span><span class="sxs-lookup"><span data-stu-id="560e4-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="560e4-103">_**Última modificação do tópico:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="560e4-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="560e4-104">Os bancos de dados de back-end do Lync Server 2013 são uma parte muito importante da implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="560e4-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="560e4-105">Recomendamos monitorar constantemente os bancos de dados e os respectivos logs de transações para ajudar a garantir que o back-end do Lync Server 2013 seja executado de forma ideal.</span><span class="sxs-lookup"><span data-stu-id="560e4-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="560e4-106">A tabela a seguir identifica contadores de desempenho que devem ser monitorados para obter informações sobre o desempenho de armazenamento.</span><span class="sxs-lookup"><span data-stu-id="560e4-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="560e4-107">Os valores de linha de base desses contadores devem ser determinados primeiro (quando o sistema está em sua carga normal e esperada) para entender as alterações de desempenho quando o sistema é testado.</span><span class="sxs-lookup"><span data-stu-id="560e4-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="560e4-108">Contadores de desempenho a serem monitorados</span><span class="sxs-lookup"><span data-stu-id="560e4-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="560e4-109">Contador de Desempenho</span><span class="sxs-lookup"><span data-stu-id="560e4-109">Performance Counter</span></span></th>
<th><span data-ttu-id="560e4-110">Limites da linha de base</span><span class="sxs-lookup"><span data-stu-id="560e4-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="560e4-111">Transações/seg (RTC)</span><span class="sxs-lookup"><span data-stu-id="560e4-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="560e4-112">Transações/s (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="560e4-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="560e4-113">Transações/s (tempdb)</span><span class="sxs-lookup"><span data-stu-id="560e4-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="560e4-114">Liberações de log/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="560e4-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="560e4-115">Liberações de log/s (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="560e4-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="560e4-116">Liberações de log/s (tempdb)</span><span class="sxs-lookup"><span data-stu-id="560e4-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="560e4-117">Transferências de disco/seg (leitura + gravação)-BD RTC</span><span class="sxs-lookup"><span data-stu-id="560e4-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="560e4-118">Transferências de disco/s-log RTC</span><span class="sxs-lookup"><span data-stu-id="560e4-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="560e4-119">Transferências de disco/s-RTCDyn DB</span><span class="sxs-lookup"><span data-stu-id="560e4-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="560e4-120">Transferências de disco/log s-RTCDyn</span><span class="sxs-lookup"><span data-stu-id="560e4-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

