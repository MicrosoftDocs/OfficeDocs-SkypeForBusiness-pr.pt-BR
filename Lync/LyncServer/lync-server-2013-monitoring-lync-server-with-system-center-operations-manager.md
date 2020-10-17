---
title: 'Lync Server 2013: monitorando o Lync Server com o System Center Operations Manager'
description: 'Lync Server 2013: monitorando o Lync Server com o System Center Operations Manager.'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Monitoring Lync 2013 with SCOM
ms:assetid: a74bde92-97ff-4d90-acb9-7a70272f0f31
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn720343(v=OCS.15)
ms:contentKeyID: 63969636
ms.date: 05/06/2015
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2ad93c47ab8d157b1e18b4bccc5094408f3d68ee
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48548087"
---
# <a name="monitoring-lync-server-2013-with-system-center-operations-manager"></a><span data-ttu-id="b9868-103">Monitoramento do Lync Server 2013 com o System Center Operations Manager</span><span class="sxs-lookup"><span data-stu-id="b9868-103">Monitoring Lync Server 2013 with System Center Operations Manager</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b9868-104">_**Última modificação do tópico:** 2015-05-06_</span><span class="sxs-lookup"><span data-stu-id="b9868-104">_**Topic Last Modified:** 2015-05-06_</span></span>

<span data-ttu-id="b9868-105">O pacote de gerenciamento do Lync Server (MP) é a solução de monitoramento escolhida para o monitoramento de qualquer implantação do Lync Server.</span><span class="sxs-lookup"><span data-stu-id="b9868-105">The Lync Server Management Pack (MP) is your monitoring solution of choice for monitoring any Lync Server deployment.</span></span>

<span data-ttu-id="b9868-106">O MP implementa o log de eventos tradicional e a instrumentação baseada em contador de desempenho e habilita a instrumentação recentemente disponível no Lync Server, como eventos de pares (falha/sucesso) para vários indicadores de integridade principais, e também implementa totalmente as novas transações sintéticas (cmdlets Test-cs do \* Windows PowerShell).</span><span class="sxs-lookup"><span data-stu-id="b9868-106">The MP implements traditional Event Log and Performance counter-based instrumentation and enables newly available instrumentation in Lync Server, such as pair events (failure/success) for several Key Health Indicators, and also fully implements the new Synthetic Transactions (Test-Cs\* Windows PowerShell cmdlets).</span></span>

<span data-ttu-id="b9868-107">Você pode encontrar o pacote de gerenciamento do Lync Server 2013 e a documentação relacionada em [https://go.microsoft.com/fwlink/p/?LinkId=400468](https://go.microsoft.com/fwlink/p/?linkid=400468) .</span><span class="sxs-lookup"><span data-stu-id="b9868-107">You can find the Lync Server 2013 Management Pack and its related documentation at [https://go.microsoft.com/fwlink/p/?LinkId=400468](https://go.microsoft.com/fwlink/p/?linkid=400468).</span></span> <span data-ttu-id="b9868-108">Isso é recomendável se você estiver executando o System Center Operations Manager 2012.</span><span class="sxs-lookup"><span data-stu-id="b9868-108">This is recommended if you are running System Center Operations Manager 2012.</span></span>

</div>

<span> </span>

</div>

</div>

</div>

