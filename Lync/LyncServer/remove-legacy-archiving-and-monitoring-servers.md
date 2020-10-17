---
title: Remover servidores de Arquivamento e de Monitoramento herdados
description: Remover servidores de arquivamento e monitoramento herdados.
ms.reviewer: ''
ms.author: serdars
author: serdarsoysal
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: befa586b-615c-496e-996e-395a6e36a826
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205221(v=OCS.15)
ms:contentKeyID: 48185278
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 0155fb18e298d2538e3bad8dc4a5626bb1ce01d7
ms.sourcegitcommit: d42a21b194f4a45e828188e04b25c1ce28a5d1ae
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2020
ms.locfileid: "48545917"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="6bf55-103">Remover servidores de Arquivamento e de Monitoramento herdados</span><span class="sxs-lookup"><span data-stu-id="6bf55-103">Remove legacy Archiving and Monitoring servers</span></span>

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="6bf55-104">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="6bf55-104">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="6bf55-105">Se sua implantação herdada contiver um servidor de arquivamento ou um servidor de monitoramento, após a migração para o Lync Server 2013, esses servidores poderão ser removidos do ambiente herdado, desde que todos os usuários tenham sido removidos de qualquer pool herdado remanescente.</span><span class="sxs-lookup"><span data-stu-id="6bf55-105">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="6bf55-106">É possível remover o Servidor de Arquivamento ou o Monitoring Server em qualquer sequência.</span><span class="sxs-lookup"><span data-stu-id="6bf55-106">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="6bf55-107">O requisito principal é que todos os usuários sejam removidos de quaisquer pools herdados restantes.</span><span class="sxs-lookup"><span data-stu-id="6bf55-107">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="6bf55-108">Você pode mover os usuários do Lync Server 2010 para o Lync Server 2013 seguindo os procedimentos descritos na [fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="6bf55-108">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="6bf55-109">Após confirmar que todos os usuários foram removidos de todos os pools restantes, siga o procedimento em "Desinstalando o Microsoft Lync Server 2010 e removendo funções de servidor", que podem ser baixados em [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) .</span><span class="sxs-lookup"><span data-stu-id="6bf55-109">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

