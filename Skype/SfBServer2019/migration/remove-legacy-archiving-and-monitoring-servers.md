---
title: Remover servidores de Arquivamento e de Monitoramento herdados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se sua implantação herdada contido um servidor de arquivamento ou um Monitoring Server, após a migração para Skype para Business Server 2019, esses servidores poderão ser removidos do ambiente herdado, desde que todos os usuários foram removidos de quaisquer pools restantes de legado. Você pode remover o servidor de arquivamento ou o Monitoring Server em qualquer sequência. O requisito de chave é que todos os usuários foram removidos de quaisquer pools restantes de legado.
ms.openlocfilehash: 5a3a691c8f2e8a4ad3610ccf1ea947ce23b74111
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32231420"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="499d8-105">Remover servidores de Arquivamento e de Monitoramento herdados</span><span class="sxs-lookup"><span data-stu-id="499d8-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="499d8-106">Se sua implantação herdada contido um servidor de arquivamento ou um Monitoring Server, após a migração para Skype para Business Server 2019, esses servidores pode ser removido do ambiente herdado, fornecidas a todos os usuários foram removidos de quaisquer pools restantes de legado.</span><span class="sxs-lookup"><span data-stu-id="499d8-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="499d8-107">Você pode remover o servidor de arquivamento ou o Monitoring Server em qualquer sequência.</span><span class="sxs-lookup"><span data-stu-id="499d8-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="499d8-108">O requisito de chave é que todos os usuários foram removidos de quaisquer pools restantes de legado.</span><span class="sxs-lookup"><span data-stu-id="499d8-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="499d8-109">Você pode mover usuários para Skype para Business Server 2019 seguindo os procedimentos descritos em [fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="499d8-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="499d8-110">Depois de confirmar que todos os usuários foram removidos de quaisquer pools restantes, decommision o servidor e remover funções.</span><span class="sxs-lookup"><span data-stu-id="499d8-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="499d8-111">Uma datados, mas é relevante, exemplo "Desinstalação do Microsoft Lync Server e Removing Server Roles," que pode ser baixado em [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="499d8-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

