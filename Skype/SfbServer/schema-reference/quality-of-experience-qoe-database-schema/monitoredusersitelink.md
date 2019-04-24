---
title: Tabela MonitoredUserSiteLink
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: A tabela MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um vínculo entre dois sites do usuário.
ms.openlocfilehash: 8022286289d4acd5fab8ea821c72897d9500597b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212520"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="f6b3a-104">Tabela MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="f6b3a-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="f6b3a-105">A tabela MonitoredUserSiteLink é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="f6b3a-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="f6b3a-106">Cada registro representa um vínculo entre dois sites do usuário.</span><span class="sxs-lookup"><span data-stu-id="f6b3a-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="f6b3a-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f6b3a-107">**Column**</span></span>|<span data-ttu-id="f6b3a-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="f6b3a-108">**Data Type**</span></span>|<span data-ttu-id="f6b3a-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="f6b3a-109">**Key/Index**</span></span>|<span data-ttu-id="f6b3a-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="f6b3a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f6b3a-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="f6b3a-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="f6b3a-112">int</span><span class="sxs-lookup"><span data-stu-id="f6b3a-112">int</span></span>  <br/> |<span data-ttu-id="f6b3a-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="f6b3a-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f6b3a-114">Referenciado de [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="f6b3a-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="f6b3a-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="f6b3a-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="f6b3a-116">int</span><span class="sxs-lookup"><span data-stu-id="f6b3a-116">int</span></span>  <br/> |<span data-ttu-id="f6b3a-117">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="f6b3a-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f6b3a-118">Referência de [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="f6b3a-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

