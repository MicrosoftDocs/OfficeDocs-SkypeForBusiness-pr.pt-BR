---
title: Tabela MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois locais de usuários.
ms.openlocfilehash: 88b4d385f3c96dc93a519274c584e1f99584982f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806351"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="badfa-104">Tabela MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="badfa-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="badfa-p102">MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois locais de usuários.</span><span class="sxs-lookup"><span data-stu-id="badfa-p102">The MonitoredUserSiteLink table is a supporting table. Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="badfa-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="badfa-107">**Column**</span></span>|<span data-ttu-id="badfa-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="badfa-108">**Data Type**</span></span>|<span data-ttu-id="badfa-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="badfa-109">**Key/Index**</span></span>|<span data-ttu-id="badfa-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="badfa-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="badfa-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="badfa-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="badfa-112">int</span><span class="sxs-lookup"><span data-stu-id="badfa-112">int</span></span>  <br/> |<span data-ttu-id="badfa-113">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="badfa-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="badfa-114">Referenciado na tabela [UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="badfa-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="badfa-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="badfa-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="badfa-116">int</span><span class="sxs-lookup"><span data-stu-id="badfa-116">int</span></span>  <br/> |<span data-ttu-id="badfa-117">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="badfa-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="badfa-118">Referência da [tabela UserSite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="badfa-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

