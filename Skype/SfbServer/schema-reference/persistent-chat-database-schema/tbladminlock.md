---
title: tblAdminLock
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.
ms.openlocfilehash: 919ead84ed9baab859e1e85eb2f30f5ff6902531
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tbladminlock"></a><span data-ttu-id="89312-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="89312-103">tblAdminLock</span></span>
 
<span data-ttu-id="89312-104">tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="89312-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="89312-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="89312-105">**Columns**</span></span>

|<span data-ttu-id="89312-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="89312-106">**Column**</span></span>|<span data-ttu-id="89312-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="89312-107">**Type**</span></span>|<span data-ttu-id="89312-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="89312-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="89312-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="89312-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="89312-110">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="89312-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="89312-111">Bloquear a expiração de data e hora.</span><span class="sxs-lookup"><span data-stu-id="89312-111">Lock expiration date and time.</span></span> <span data-ttu-id="89312-112">O proprietário pode estender esse valor periodicamente.</span><span class="sxs-lookup"><span data-stu-id="89312-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="89312-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="89312-113">lockServerID</span></span>  <br/> |<span data-ttu-id="89312-114">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="89312-114">int, not null</span></span>  <br/> |<span data-ttu-id="89312-115">ID do servidor que possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="89312-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="89312-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="89312-116">lockActorID</span></span>  <br/> |<span data-ttu-id="89312-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="89312-117">int, not null</span></span>  <br/> |<span data-ttu-id="89312-118">ID da entidade que possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="89312-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

