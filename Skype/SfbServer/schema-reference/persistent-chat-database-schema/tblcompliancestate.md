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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: ea82e56c-3cca-4d89-b4e6-6bcaeb1f2830
description: tblComplianceState contém informações de estado de conformidade em todo o pool.
ms.openlocfilehash: 6f3a7b1b7744260d0630a5328021b1752137a797
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814629"
---
# <a name="tblcompliancestate"></a><span data-ttu-id="d4e08-103">tblComplianceState</span><span class="sxs-lookup"><span data-stu-id="d4e08-103">tblComplianceState</span></span>
 
<span data-ttu-id="d4e08-104">tblComplianceState contém informações de estado de conformidade em todo o pool.</span><span class="sxs-lookup"><span data-stu-id="d4e08-104">tblComplianceState contains pool-wide compliance state information.</span></span>
  
<span data-ttu-id="d4e08-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d4e08-105">**Columns**</span></span>

|<span data-ttu-id="d4e08-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d4e08-106">**Column**</span></span>|<span data-ttu-id="d4e08-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d4e08-107">**Type**</span></span>|<span data-ttu-id="d4e08-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d4e08-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d4e08-109">lastProcessedEntryID</span><span class="sxs-lookup"><span data-stu-id="d4e08-109">lastProcessedEntryID</span></span>  <br/> |<span data-ttu-id="d4e08-110">bigint, e não nulo</span><span class="sxs-lookup"><span data-stu-id="d4e08-110">bigint, not null</span></span>  <br/> |<span data-ttu-id="d4e08-111">ID do evento de conformidade processado mais recente.</span><span class="sxs-lookup"><span data-stu-id="d4e08-111">ID of the latest processed compliance event.</span></span>  <br/> |
|<span data-ttu-id="d4e08-112">activeServerID</span><span class="sxs-lookup"><span data-stu-id="d4e08-112">activeServerID</span></span>  <br/> |<span data-ttu-id="d4e08-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d4e08-113">int, not null</span></span>  <br/> |<span data-ttu-id="d4e08-114">ID do servidor de conformidade que mantém o bloqueio exclusivo no banco de dados ou-1 se nenhum.</span><span class="sxs-lookup"><span data-stu-id="d4e08-114">ID of the Compliance server holding the exclusive lock on the database, or -1 if none.</span></span>  <br/> |
|<span data-ttu-id="d4e08-115">lockExpirationTime</span><span class="sxs-lookup"><span data-stu-id="d4e08-115">lockExpirationTime</span></span>  <br/> |<span data-ttu-id="d4e08-116">datetime2, não nulo</span><span class="sxs-lookup"><span data-stu-id="d4e08-116">datetime2, not null</span></span>  <br/> |<span data-ttu-id="d4e08-117">Bloquear o tempo de expiração (se activeServerID não for-1).</span><span class="sxs-lookup"><span data-stu-id="d4e08-117">Lock expiration time (if activeServerID is not -1).</span></span>  <br/> |
   

