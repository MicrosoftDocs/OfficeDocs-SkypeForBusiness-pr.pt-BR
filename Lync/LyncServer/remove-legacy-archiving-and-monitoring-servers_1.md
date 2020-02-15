---
title: Remover servidores de arquivamento e monitoramento herdados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Remove legacy Archiving and Monitoring servers
ms:assetid: bca6b419-d5bc-4a46-af42-1dd51b99a26b
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ205215(v=OCS.15)
ms:contentKeyID: 48185261
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 331a6f24cd2cc176679f628bc54460a6c3c7a718
ms.sourcegitcommit: 88a16c09dd91229e1a8c156445eb3c360c942978
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/14/2020
ms.locfileid: "42008897"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="93865-102">Remover servidores de arquivamento e monitoramento herdados</span><span class="sxs-lookup"><span data-stu-id="93865-102">Remove legacy Archiving and Monitoring servers</span></span>

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

<span data-ttu-id="93865-103">_**Última modificação do tópico:** 2012-09-26_</span><span class="sxs-lookup"><span data-stu-id="93865-103">_**Topic Last Modified:** 2012-09-26_</span></span>

<span data-ttu-id="93865-104">Se sua implantação do Office Communications Server 2007 R2 contiver um servidor de arquivamento ou um servidor de monitoramento, após a migração para o Lync Server 2013, esses servidores poderão ser removidos do ambiente herdado, desde que todos os usuários tenham sido removidos de qualquer outro Pools do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93865-104">If your Office Communications Server 2007 R2 deployment contained an Archiving Server or a Monitoring Server, after migrating to Lync Server 2013, those servers can be removed from the legacy environment provided all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span> <span data-ttu-id="93865-105">É possível remover o Servidor de Arquivamento ou o Monitoring Server em qualquer sequência.</span><span class="sxs-lookup"><span data-stu-id="93865-105">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="93865-106">O requisito chave é que todos os usuários tenham sido removidos de todos os pools restantes do Office Communications Server 2007 R2.</span><span class="sxs-lookup"><span data-stu-id="93865-106">The key requirement is that all users have been removed from any remaining Office Communications Server 2007 R2 pools.</span></span>

<span data-ttu-id="93865-107">Você pode mover os usuários do Office Communications Server 2007 R2 para o Lync Server 2013 seguindo os procedimentos descritos na [fase 6: mover usuários para o pool piloto](phase-6-move-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="93865-107">You can move users from Office Communications Server 2007 R2 to Lync Server 2013 by following the procedures outlined in [Phase 6: Move users to the pilot pool](phase-6-move-users-to-the-pilot-pool.md).</span></span>

<span data-ttu-id="93865-108">Após confirmar que todos os usuários foram removidos de todos os pools restantes, siga o procedimento em "removendo servidores e funções de servidor [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887)" em.</span><span class="sxs-lookup"><span data-stu-id="93865-108">After you have confirmed that all users have been removed from any remaining pools, follow the procedure in "Removing Servers and Server Roles" at [http://go.microsoft.com/fwlink/p/?linkId=205887](http://go.microsoft.com/fwlink/p/?linkid=205887).</span></span>

</div>

<span> </span>

</div>

</div>

</div>

