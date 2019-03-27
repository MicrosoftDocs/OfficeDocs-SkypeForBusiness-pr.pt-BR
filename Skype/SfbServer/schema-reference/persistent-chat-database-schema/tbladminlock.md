---
title: tblAdminLock
ms.reviewer: ''
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
ms.openlocfilehash: bf7537b7d1081bd415ff2e8fe3615864c71f593a
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898949"
---
# <a name="tbladminlock"></a><span data-ttu-id="d741d-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="d741d-103">tblAdminLock</span></span>
 
<span data-ttu-id="d741d-104">tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="d741d-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="d741d-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d741d-105">**Columns**</span></span>

|<span data-ttu-id="d741d-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d741d-106">**Column**</span></span>|<span data-ttu-id="d741d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d741d-107">**Type**</span></span>|<span data-ttu-id="d741d-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d741d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d741d-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="d741d-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="d741d-110">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="d741d-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="d741d-111">Bloquear a expiração de data e hora.</span><span class="sxs-lookup"><span data-stu-id="d741d-111">Lock expiration date and time.</span></span> <span data-ttu-id="d741d-112">O proprietário pode estender esse valor periodicamente.</span><span class="sxs-lookup"><span data-stu-id="d741d-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="d741d-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="d741d-113">lockServerID</span></span>  <br/> |<span data-ttu-id="d741d-114">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d741d-114">int, not null</span></span>  <br/> |<span data-ttu-id="d741d-115">ID do servidor que possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="d741d-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="d741d-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="d741d-116">lockActorID</span></span>  <br/> |<span data-ttu-id="d741d-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d741d-117">int, not null</span></span>  <br/> |<span data-ttu-id="d741d-118">ID da entidade que possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="d741d-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

