---
title: Remover servidores de Arquivamento e de Monitoramento herdados
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
ms.openlocfilehash: 8d77292fe478fa95deec50df84a78907af4290e3
ms.sourcegitcommit: 62946d7515ccaa7a622d44b736e9e919a2e102d0
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/16/2020
ms.locfileid: "44757102"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="b0d18-102">Remover servidores de Arquivamento e de Monitoramento herdados</span><span class="sxs-lookup"><span data-stu-id="b0d18-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="b0d18-103">_**Última modificação do tópico:** 2012-10-19_</span><span class="sxs-lookup"><span data-stu-id="b0d18-103">_**Topic Last Modified:** 2012-10-19_</span></span>

<span data-ttu-id="b0d18-104">Se sua implantação herdada contiver um servidor de arquivamento ou um servidor de monitoramento, após a migração para o Lync Server 2013, esses servidores poderão ser removidos do ambiente herdado, desde que todos os usuários tenham sido removidos de qualquer pool herdado remanescente.</span><span class="sxs-lookup"><span data-stu-id="b0d18-104">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="b0d18-105">É possível remover o Servidor de Arquivamento ou o Monitoring Server em qualquer sequência.</span><span class="sxs-lookup"><span data-stu-id="b0d18-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="b0d18-106">O requisito principal é que todos os usuários sejam removidos de quaisquer pools herdados restantes.</span><span class="sxs-lookup"><span data-stu-id="b0d18-106">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>

<span data-ttu-id="b0d18-107">Você pode mover os usuários do Lync Server 2010 para o Lync Server 2013 seguindo os procedimentos descritos na [fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="b0d18-107">You can move users from Lync Server 2010 to Lync Server 2013 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="b0d18-108">Após confirmar que todos os usuários foram removidos de todos os pools restantes, siga o procedimento em "Desinstalando o Microsoft Lync Server 2010 e removendo funções de servidor", que podem ser baixados em [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227) .</span><span class="sxs-lookup"><span data-stu-id="b0d18-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Uninstalling Microsoft Lync Server 2010 and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkid=246227).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

