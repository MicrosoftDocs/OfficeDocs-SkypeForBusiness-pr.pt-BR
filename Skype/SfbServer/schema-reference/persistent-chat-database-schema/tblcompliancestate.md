---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contém informações de estado de conformidade de todo o pool.
ms.openlocfilehash: 6f6b3891638fc3d769c0b0f4f4a42ca5f94a5a54
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929844"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="a6ffb-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="a6ffb-103">tblComplianceState</span></span>
 
<span data-ttu-id="a6ffb-104">tblComplianceState contém informações de estado de conformidade de todo o pool.</span><span class="sxs-lookup"><span data-stu-id="a6ffb-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="a6ffb-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="a6ffb-105">**Columns**</span></span>

|<span data-ttu-id="a6ffb-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a6ffb-106">**Column**</span></span>|<span data-ttu-id="a6ffb-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="a6ffb-107">**Type**</span></span>|<span data-ttu-id="a6ffb-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a6ffb-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a6ffb-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="a6ffb-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="a6ffb-110">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="a6ffb-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="a6ffb-111">ID do evento mais recente de conformidade processado.</span><span class="sxs-lookup"><span data-stu-id="a6ffb-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="a6ffb-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="a6ffb-112">activeServerID</span></span>  <br/> |<span data-ttu-id="a6ffb-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="a6ffb-113">int, not null</span></span>  <br/> |<span data-ttu-id="a6ffb-114">ID do servidor de conformidade, mantendo o bloqueio exclusivo no banco de dados, ou -1 se nenhum.</span><span class="sxs-lookup"><span data-stu-id="a6ffb-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="a6ffb-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="a6ffb-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="a6ffb-116">datetime2, não nulo</span><span class="sxs-lookup"><span data-stu-id="a6ffb-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="a6ffb-117">Tempo de expiração de bloqueio (se activeServerID não for -1).</span><span class="sxs-lookup"><span data-stu-id="a6ffb-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

