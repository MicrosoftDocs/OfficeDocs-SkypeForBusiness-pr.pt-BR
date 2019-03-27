---
title: tblComplianceState
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contém informações de estado de conformidade de todo o pool.
ms.openlocfilehash: 4e9f103ef019e743b5dfcb4ef554ff6a28c340b8
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899289"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="9798b-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="9798b-103">tblComplianceState</span></span>
 
<span data-ttu-id="9798b-104">tblComplianceState contém informações de estado de conformidade de todo o pool.</span><span class="sxs-lookup"><span data-stu-id="9798b-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="9798b-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="9798b-105">**Columns**</span></span>

|<span data-ttu-id="9798b-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9798b-106">**Column**</span></span>|<span data-ttu-id="9798b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9798b-107">**Type**</span></span>|<span data-ttu-id="9798b-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9798b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9798b-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="9798b-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="9798b-110">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="9798b-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="9798b-111">ID do evento mais recente de conformidade processado.</span><span class="sxs-lookup"><span data-stu-id="9798b-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="9798b-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="9798b-112">activeServerID</span></span>  <br/> |<span data-ttu-id="9798b-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="9798b-113">int, not null</span></span>  <br/> |<span data-ttu-id="9798b-114">ID do servidor de conformidade, mantendo o bloqueio exclusivo no banco de dados, ou -1 se nenhum.</span><span class="sxs-lookup"><span data-stu-id="9798b-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="9798b-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="9798b-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="9798b-116">datetime2, não nulo</span><span class="sxs-lookup"><span data-stu-id="9798b-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="9798b-117">Tempo de expiração de bloqueio (se activeServerID não for -1).</span><span class="sxs-lookup"><span data-stu-id="9798b-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

