---
title: Remover servidores de Arquivamento e de Monitoramento herdados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: dcca1687a91f3ec3bd35fceab9ae6cdf58292292
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "34844147"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="f4440-102">Remover servidores de Arquivamento e de Monitoramento herdados</span><span class="sxs-lookup"><span data-stu-id="f4440-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="f4440-103">_**Tópico da última modificação:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="f4440-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="f4440-104">Se a sua implantação do Office Communications Server 2007 R2 continha um servidor de arquivamento ou um servidor de monitoramento, após a migração para o Lync Server 2013, esses servidores podem ser removidos do ambiente herdado desde que todos os usuários tenham sido removidos de todos os outros Pools do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f4440-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="f4440-105">Você pode remover o servidor de arquivamento ou o servidor de monitoramento em qualquer sequência.</span><span class="sxs-lookup"><span data-stu-id="f4440-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="f4440-106">O requisito chave é que todos os usuários foram removidos de todos os pools remanescentes do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="f4440-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="f4440-107">Você pode mover os usuários do Office Communications Server 2007 R2 para o Lync Server 2013 seguindo os procedimentos descritos na [fase 6: mover usuários para o pool piloto](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="f4440-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="f4440-108">Depois de confirmar que todos os usuários foram removidos de todos os grupos restantes, siga o procedimento em "removendo servidores e funções de servidor [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887)" em.</span><span class="sxs-lookup"><span data-stu-id="f4440-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

