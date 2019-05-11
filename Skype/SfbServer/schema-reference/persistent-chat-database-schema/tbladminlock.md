---
title: tblAdminLock
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.
ms.openlocfilehash: ea1cff137e58ef65eda172a9c09e5dd38e66d8a4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929809"
---
# <a name="tbladminlock"></a><span data-ttu-id="d8cc8-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="d8cc8-103">tblAdminLock</span></span>
 
<span data-ttu-id="d8cc8-104">tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="d8cc8-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="d8cc8-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="d8cc8-105">**Columns**</span></span>

|<span data-ttu-id="d8cc8-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="d8cc8-106">**Column**</span></span>|<span data-ttu-id="d8cc8-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="d8cc8-107">**Type**</span></span>|<span data-ttu-id="d8cc8-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="d8cc8-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="d8cc8-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="d8cc8-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="d8cc8-110">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="d8cc8-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="d8cc8-111">Bloquear a expiração de data e hora.</span><span class="sxs-lookup"><span data-stu-id="d8cc8-111">Lock expiration date and time.</span></span> <span data-ttu-id="d8cc8-112">O proprietário pode estender esse valor periodicamente.</span><span class="sxs-lookup"><span data-stu-id="d8cc8-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="d8cc8-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="d8cc8-113">lockServerID</span></span>  <br/> |<span data-ttu-id="d8cc8-114">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d8cc8-114">int, not null</span></span>  <br/> |<span data-ttu-id="d8cc8-115">ID do servidor que possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="d8cc8-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="d8cc8-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="d8cc8-116">lockActorID</span></span>  <br/> |<span data-ttu-id="d8cc8-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="d8cc8-117">int, not null</span></span>  <br/> |<span data-ttu-id="d8cc8-118">ID da entidade que possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="d8cc8-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

