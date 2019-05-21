---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contém informações de estado de conformidade em todo o pool.
ms.openlocfilehash: 1c5571d7150c3859978f8d217f0264f67ee993d5
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295472"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="800e2-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="800e2-103">tblComplianceState</span></span>
 
<span data-ttu-id="800e2-104">tblComplianceState contém informações de estado de conformidade em todo o pool.</span><span class="sxs-lookup"><span data-stu-id="800e2-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="800e2-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="800e2-105">**Columns**</span></span>

|<span data-ttu-id="800e2-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="800e2-106">**Column**</span></span>|<span data-ttu-id="800e2-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="800e2-107">**Type**</span></span>|<span data-ttu-id="800e2-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="800e2-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="800e2-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="800e2-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="800e2-110">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="800e2-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="800e2-111">ID do evento de conformidade processado mais recente.</span><span class="sxs-lookup"><span data-stu-id="800e2-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="800e2-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="800e2-112">activeServerID</span></span>  <br/> |<span data-ttu-id="800e2-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="800e2-113">int, not null</span></span>  <br/> |<span data-ttu-id="800e2-114">ID do servidor de conformidade que mantém o bloqueio exclusivo no banco de dados ou-1 se nenhum.</span><span class="sxs-lookup"><span data-stu-id="800e2-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="800e2-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="800e2-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="800e2-116">datetime2, não nulo</span><span class="sxs-lookup"><span data-stu-id="800e2-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="800e2-117">Bloquear o tempo de expiração (se activeServerID não for-1).</span><span class="sxs-lookup"><span data-stu-id="800e2-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

