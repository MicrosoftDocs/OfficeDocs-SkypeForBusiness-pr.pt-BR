---
title: tblAdminLock
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
ms.assetid: 785a43c0-6892-474c-821c-fa9cdbeb99d8
description: tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.
ms.openlocfilehash: aed7720a9b74483a34704c0009958ea91a786fc1
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809881"
---
# <a name="tbladminlock"></a><span data-ttu-id="52a86-103">tblAdminLock</span><span class="sxs-lookup"><span data-stu-id="52a86-103">tblAdminLock</span></span>
 
<span data-ttu-id="52a86-104">tblAdminLock contém o bloqueio do administrador necessário para a execução de alguns comandos de administrador.</span><span class="sxs-lookup"><span data-stu-id="52a86-104">tblAdminLock contains the administrator lock that is needed to run some administrator commands.</span></span>
  
<span data-ttu-id="52a86-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="52a86-105">**Columns**</span></span>

|<span data-ttu-id="52a86-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="52a86-106">**Column**</span></span>|<span data-ttu-id="52a86-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="52a86-107">**Type**</span></span>|<span data-ttu-id="52a86-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="52a86-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="52a86-109">lockExpiresTime</span><span class="sxs-lookup"><span data-stu-id="52a86-109">lockExpiresTime</span></span>  <br/> |<span data-ttu-id="52a86-110">datetime, não nulo</span><span class="sxs-lookup"><span data-stu-id="52a86-110">datetime, not null</span></span>  <br/> |<span data-ttu-id="52a86-p101">Data de expiração de bloqueio. O proprietário pode estender esse valor periodicamente.</span><span class="sxs-lookup"><span data-stu-id="52a86-p101">Lock expiration date and time. The owner can extend this value periodically.</span></span>  <br/> |
|<span data-ttu-id="52a86-113">lockServerID</span><span class="sxs-lookup"><span data-stu-id="52a86-113">lockServerID</span></span>  <br/> |<span data-ttu-id="52a86-114">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="52a86-114">int, not null</span></span>  <br/> |<span data-ttu-id="52a86-115">Identificação do servidor que possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="52a86-115">ID of the server that owns the lock.</span></span>  <br/> |
|<span data-ttu-id="52a86-116">lockActorID</span><span class="sxs-lookup"><span data-stu-id="52a86-116">lockActorID</span></span>  <br/> |<span data-ttu-id="52a86-117">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="52a86-117">int, not null</span></span>  <br/> |<span data-ttu-id="52a86-118">Identificação da entidade que possui o bloqueio.</span><span class="sxs-lookup"><span data-stu-id="52a86-118">ID of the principal that owns the lock.</span></span>  <br/> |
   

