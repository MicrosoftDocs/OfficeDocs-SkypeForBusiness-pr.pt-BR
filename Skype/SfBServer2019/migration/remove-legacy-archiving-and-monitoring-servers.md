---
title: Remover o arquivamento de legado e servidores de monitoramento
ms.author: kenwith
author: kenwith
manager: serdars
ms.audience: ITPro
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se sua implantação herdada contido um servidor de arquivamento ou um Monitoring Server, após a migração para Skype para Business Server 2019, esses servidores poderão ser removidos do ambiente herdado, desde que todos os usuários foram removidos de quaisquer pools restantes de legado. Você pode remover o servidor de arquivamento ou o Monitoring Server em qualquer sequência. O requisito de chave é que todos os usuários foram removidos de quaisquer pools restantes de legado.
ms.openlocfilehash: 4de6d9db5538864646f978e9fc33a79b39d4c2a4
ms.sourcegitcommit: e9f277dc96265a193c6298c3556ef16ff640071d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/24/2018
ms.locfileid: "25028611"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="32fc4-105">Remover o arquivamento de legado e servidores de monitoramento</span><span class="sxs-lookup"><span data-stu-id="32fc4-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="32fc4-106">Se sua implantação herdada contido um servidor de arquivamento ou um Monitoring Server, após a migração para Skype para Business Server 2019, esses servidores pode ser removido do ambiente herdado, fornecidas a todos os usuários foram removidos de quaisquer pools restantes de legado.</span><span class="sxs-lookup"><span data-stu-id="32fc4-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="32fc4-107">Você pode remover o servidor de arquivamento ou o Monitoring Server em qualquer sequência.</span><span class="sxs-lookup"><span data-stu-id="32fc4-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="32fc4-108">O requisito de chave é que todos os usuários foram removidos de quaisquer pools restantes de legado.</span><span class="sxs-lookup"><span data-stu-id="32fc4-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="32fc4-109">Você pode mover usuários para Skype para Business Server 2019 seguindo os procedimentos descritos em [fase 4: mover usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="32fc4-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="32fc4-110">Depois de confirmar que todos os usuários foram removidos de quaisquer pools restantes, decommision o servidor e remover funções.</span><span class="sxs-lookup"><span data-stu-id="32fc4-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="32fc4-111">Uma datados, mas é relevante, exemplo "Desinstalação do Microsoft Lync Server e Removing Server Roles," que pode ser baixado em [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span><span class="sxs-lookup"><span data-stu-id="32fc4-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

