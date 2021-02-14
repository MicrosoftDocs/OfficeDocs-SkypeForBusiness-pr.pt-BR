---
title: tblComplianceState
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contém informações sobre o estado de conformidade de todo o pool.
ms.openlocfilehash: 82c775b315976b0e5b112c476a41a8f5adc6a24c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809721"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="e7710-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="e7710-103">tblComplianceState</span></span>
 
<span data-ttu-id="e7710-104">tblComplianceState contém informações sobre o estado de conformidade de todo o pool.</span><span class="sxs-lookup"><span data-stu-id="e7710-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="e7710-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="e7710-105">**Columns**</span></span>

|<span data-ttu-id="e7710-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e7710-106">**Column**</span></span>|<span data-ttu-id="e7710-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="e7710-107">**Type**</span></span>|<span data-ttu-id="e7710-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="e7710-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="e7710-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="e7710-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="e7710-110">bigint, não nulo</span><span class="sxs-lookup"><span data-stu-id="e7710-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="e7710-111">ID do último evento de conformidade processado.</span><span class="sxs-lookup"><span data-stu-id="e7710-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="e7710-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="e7710-112">activeServerID</span></span>  <br/> |<span data-ttu-id="e7710-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="e7710-113">int, not null</span></span>  <br/> |<span data-ttu-id="e7710-114">ID do servidor de conformidade que possui o bloqueio exclusivo no banco de dados, ou -1 se nenhum.</span><span class="sxs-lookup"><span data-stu-id="e7710-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="e7710-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="e7710-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="e7710-116">datetime2, não nulo</span><span class="sxs-lookup"><span data-stu-id="e7710-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="e7710-117">Hora de expiração do bloqueio (se activeServerID não for igual a -1).</span><span class="sxs-lookup"><span data-stu-id="e7710-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

