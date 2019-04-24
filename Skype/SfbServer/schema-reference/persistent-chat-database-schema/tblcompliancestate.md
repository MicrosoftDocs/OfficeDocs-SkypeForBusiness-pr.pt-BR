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
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212632"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="b2fc2-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="b2fc2-103">tblComplianceState</span></span>
 
<span data-ttu-id="b2fc2-104">tblComplianceState contém informações de estado de conformidade de todo o pool.</span><span class="sxs-lookup"><span data-stu-id="b2fc2-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="b2fc2-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="b2fc2-105">**Columns**</span></span>

|<span data-ttu-id="b2fc2-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b2fc2-106">**Column**</span></span>|<span data-ttu-id="b2fc2-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b2fc2-107">**Type**</span></span>|<span data-ttu-id="b2fc2-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b2fc2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b2fc2-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="b2fc2-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="b2fc2-110">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="b2fc2-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="b2fc2-111">ID do evento mais recente de conformidade processado.</span><span class="sxs-lookup"><span data-stu-id="b2fc2-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="b2fc2-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="b2fc2-112">activeServerID</span></span>  <br/> |<span data-ttu-id="b2fc2-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="b2fc2-113">int, not null</span></span>  <br/> |<span data-ttu-id="b2fc2-114">ID do servidor de conformidade, mantendo o bloqueio exclusivo no banco de dados, ou -1 se nenhum.</span><span class="sxs-lookup"><span data-stu-id="b2fc2-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="b2fc2-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="b2fc2-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="b2fc2-116">datetime2, não nulo</span><span class="sxs-lookup"><span data-stu-id="b2fc2-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="b2fc2-117">Tempo de expiração de bloqueio (se activeServerID não for -1).</span><span class="sxs-lookup"><span data-stu-id="b2fc2-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

