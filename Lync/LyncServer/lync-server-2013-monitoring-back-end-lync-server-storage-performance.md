---
title: 'Lync Server 2013: monitorando o desempenho de armazenamento do Lync Server back-end'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Monitoring back end Lync Server 2013 storage performance
ms:assetid: 71627c70-1953-4ac2-afbe-f3ad85be0f44
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720917(v=OCS.15)
ms:contentKeyID: 63969619
ms.date: 01/27/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: b4c63956cebc7f532f92b6e0729bdfe811d0fdfb
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34826756"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="monitoring-back-end-lync-server-2013-storage-performance"></a><span data-ttu-id="ab2fb-102">Monitorando o back-end do Lync Server 2013 Storage performance</span><span class="sxs-lookup"><span data-stu-id="ab2fb-102">Monitoring back end Lync Server 2013 storage performance</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="ab2fb-103">_**Tópico da última modificação:** 2014-05-02_</span><span class="sxs-lookup"><span data-stu-id="ab2fb-103">_**Topic Last Modified:** 2014-05-02_</span></span>

<span data-ttu-id="ab2fb-104">Os bancos de dados back-end do Lync Server 2013 são uma parte muito importante da implantação do Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ab2fb-104">The Lync Server 2013 back-end databases are a very important part of the Lync Server 2013 deployment.</span></span> <span data-ttu-id="ab2fb-105">Recomendamos que você monitore constantemente os bancos de dados e os respectivos registros de transações para ajudar a garantir que o back-end do Lync Server 2013 seja executado de forma ideal.</span><span class="sxs-lookup"><span data-stu-id="ab2fb-105">We recommend constantly monitoring the databases and respective transaction logs to help to make sure that the Lync Server 2013 back end is performing optimally.</span></span>

<span data-ttu-id="ab2fb-106">A tabela a seguir identifica contadores de desempenho que devem ser monitorados para obter informações sobre o desempenho do armazenamento.</span><span class="sxs-lookup"><span data-stu-id="ab2fb-106">The following table identifies performance counters that should be monitored to learn information about Storage Performance.</span></span> <span data-ttu-id="ab2fb-107">Os valores da linha de base desses contadores devem ser determinados primeiro (quando o sistema está em sua carga normal, esperada) para entender as alterações de desempenho quando o sistema é testado.</span><span class="sxs-lookup"><span data-stu-id="ab2fb-107">The baseline values for these counters must be determined first (when system is at its normal, expected load) to understand the performance changes when system is stressed.</span></span>

### <a name="performance-counters-to-be-monitored"></a><span data-ttu-id="ab2fb-108">Contadores de desempenho a serem monitorados</span><span class="sxs-lookup"><span data-stu-id="ab2fb-108">Performance counters to be monitored</span></span>

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th><span data-ttu-id="ab2fb-109">Contador de desempenho</span><span class="sxs-lookup"><span data-stu-id="ab2fb-109">Performance Counter</span></span></th>
<th><span data-ttu-id="ab2fb-110">Limites da linha de base</span><span class="sxs-lookup"><span data-stu-id="ab2fb-110">Baseline thresholds</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="ab2fb-111">Transações/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="ab2fb-111">Transactions/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2fb-112">Transações/s (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="ab2fb-112">Transactions/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2fb-113">Transações/s (tempdb)</span><span class="sxs-lookup"><span data-stu-id="ab2fb-113">Transactions/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2fb-114">Liberações de log/s (RTC)</span><span class="sxs-lookup"><span data-stu-id="ab2fb-114">Log Flushes/sec (RTC)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2fb-115">Liberações de log/s (RTCDyn)</span><span class="sxs-lookup"><span data-stu-id="ab2fb-115">Log Flushes/sec (rtcdyn)</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2fb-116">Liberações de log/s (tempdb)</span><span class="sxs-lookup"><span data-stu-id="ab2fb-116">Log Flushes/sec (tempdb)</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2fb-117">Transferências de disco/s (leitura + gravação)-BD RTC</span><span class="sxs-lookup"><span data-stu-id="ab2fb-117">Disk Transfers/sec (read+write) - RTC db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2fb-118">Transferências de disco/s-log de RTC</span><span class="sxs-lookup"><span data-stu-id="ab2fb-118">Disk Transfers/sec - RTC log</span></span></p></td>
<td></td>
</tr>
<tr class="odd">
<td><p><span data-ttu-id="ab2fb-119">Transferências de disco/s-RTCDyn DB</span><span class="sxs-lookup"><span data-stu-id="ab2fb-119">Disk Transfers/sec - rtcdyn db</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><p><span data-ttu-id="ab2fb-120">Transferências de disco/log SEC-RTCDyn</span><span class="sxs-lookup"><span data-stu-id="ab2fb-120">Disk Transfers/sec - rtcdyn log</span></span></p></td>
<td></td>
</tr>
</tbody>
</table>


</div>

<span> </span>

</div>

</div>

</div>

