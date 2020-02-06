---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contém o bloqueio do administrador necessário para executar alguns comandos de administrador.
ms.openlocfilehash: cb3a03fa7404004df37da2adf07eff1e37ff334f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814689"
---
# <a name="tbladminlock"></a><span data-ttu-id="20e2c-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="20e2c-103">tblAdminLock</span></span>
 
<span data-ttu-id="20e2c-104">tblAdminLock contém o bloqueio do administrador necessário para executar alguns comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="20e2c-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="20e2c-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="20e2c-105">**Columns**</span></span>

|<span data-ttu-id="20e2c-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="20e2c-106">**Column**</span></span>|<span data-ttu-id="20e2c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="20e2c-107">**Type**</span></span>|<span data-ttu-id="20e2c-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="20e2c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="20e2c-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="20e2c-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="20e2c-110">DateTime, não nulo</span><span class="sxs-lookup"><span data-stu-id="20e2c-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="20e2c-111">Bloquear data e hora de expiração.</span><span class="sxs-lookup"><span data-stu-id="20e2c-111">Lock expiration date and time.</span></span> <span data-ttu-id="20e2c-112">O proprietário pode estender esse valor periodicamente.</span><span class="sxs-lookup"><span data-stu-id="20e2c-112">The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="20e2c-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="20e2c-113">lockServerID</span></span>  <br/> |<span data-ttu-id="20e2c-114">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="20e2c-114">int, not null</span></span>  <br/> |<span data-ttu-id="20e2c-115">ID do servidor que é proprietário do bloqueio.</span><span class="sxs-lookup"><span data-stu-id="20e2c-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="20e2c-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="20e2c-116">lockActorID</span></span>  <br/> |<span data-ttu-id="20e2c-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="20e2c-117">int, not null</span></span>  <br/> |<span data-ttu-id="20e2c-118">ID da entidade de segurança que é proprietária do bloqueio.</span><span class="sxs-lookup"><span data-stu-id="20e2c-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

