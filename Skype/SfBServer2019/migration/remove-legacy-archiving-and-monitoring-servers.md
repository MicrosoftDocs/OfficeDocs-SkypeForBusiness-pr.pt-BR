---
title: Remover servidores de Arquivamento e de Monitoramento herdados
ms.reviewer: ''
ms.author: kenwith
author: kenwith
manager: serdars
audience: ITPro
ms.topic: quickstart
ms.prod: skype-for-business-itpro
localization_priority: Normal
description: Se sua implantação herdada continha um servidor de arquivamento ou um servidor de monitoramento, após a migração para o Skype for Business Server 2019, esses servidores podem ser removidos do ambiente herdado desde que todos os usuários tenham sido removidos de todos os pools herdados restantes. Você pode remover o servidor de arquivamento ou o servidor de monitoramento em qualquer sequência. O requisito chave é que todos os usuários foram removidos de todos os pools herdados restantes.
ms.openlocfilehash: 06d6287438e4b470017b00601b1e2ab472bea9b6
ms.sourcegitcommit: e1c8a62577229daf42f1a7bcfba268a9001bb791
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2019
ms.locfileid: "36244225"
---
# <a name="remove-legacy-archiving-and-monitoring-servers"></a><span data-ttu-id="e1aab-105">Remover servidores de Arquivamento e de Monitoramento herdados</span><span class="sxs-lookup"><span data-stu-id="e1aab-105">Remove legacy Archiving and Monitoring servers</span></span>

<span data-ttu-id="e1aab-106">Se sua implantação herdada continha um servidor de arquivamento ou um servidor de monitoramento, após a migração para o Skype for Business Server 2019, esses servidores podem ser removidos do ambiente herdado, contanto que todos os usuários tenham sido removidos de todos os pools herdados restantes.</span><span class="sxs-lookup"><span data-stu-id="e1aab-106">If your legacy deployment contained an Archiving Server or a Monitoring Server, after migrating to Skype for Business Server 2019, those servers can be removed from the legacy environment, provided all users have been removed from any remaining legacy pools.</span></span> <span data-ttu-id="e1aab-107">Você pode remover o servidor de arquivamento ou o servidor de monitoramento em qualquer sequência.</span><span class="sxs-lookup"><span data-stu-id="e1aab-107">You can remove the Archiving Server or Monitoring Server in any sequence.</span></span> <span data-ttu-id="e1aab-108">O requisito chave é que todos os usuários foram removidos de todos os pools herdados restantes.</span><span class="sxs-lookup"><span data-stu-id="e1aab-108">The key requirement is that all users have been removed from any remaining legacy pools.</span></span>
  
<span data-ttu-id="e1aab-109">Você pode mover usuários para o Skype for Business Server 2019 seguindo os procedimentos descritos na [fase 4: mover os usuários de teste para o pool piloto](phase-4-move-test-users-to-the-pilot-pool.md).</span><span class="sxs-lookup"><span data-stu-id="e1aab-109">You can move users to Skype for Business Server 2019 by following the procedures outlined in [Phase 4: Move test users to the pilot pool](phase-4-move-test-users-to-the-pilot-pool.md).</span></span>
  
<span data-ttu-id="e1aab-110">Depois de confirmar que todos os usuários foram removidos de todos os grupos restantes, decommision o servidor e remova as funções.</span><span class="sxs-lookup"><span data-stu-id="e1aab-110">After you have confirmed that all users have been removed from any remaining pools, decommision the server and remove roles.</span></span> <span data-ttu-id="e1aab-111">Um exemplo de data e mais relevante é "desinstalar o Microsoft Lync Server e remover funções de servidor", cujo download pode ser feito [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227)em.</span><span class="sxs-lookup"><span data-stu-id="e1aab-111">A dated, but relevant, example is "Uninstalling Microsoft Lync Server and Removing Server Roles," which can be downloaded at [https://go.microsoft.com/fwlink/p/?linkId=246227](https://go.microsoft.com/fwlink/p/?linkId=246227).</span></span>
  

