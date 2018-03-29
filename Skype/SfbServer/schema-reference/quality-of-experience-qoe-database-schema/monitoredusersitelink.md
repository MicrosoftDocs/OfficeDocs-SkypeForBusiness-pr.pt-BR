---
title: Tabela MonitoredUserSiteLink
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
ms.openlocfilehash: 7b9b2ddab3bff48105a24f586816666b15c0b9b6
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="07710-104">Tabela MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="07710-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="07710-105">A tabela MonitoredUserSiteLink é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="07710-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="07710-106">Cada registro representa um vínculo entre dois sites do usuário.</span><span class="sxs-lookup"><span data-stu-id="07710-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="07710-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="07710-107">**Column**</span></span>|<span data-ttu-id="07710-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="07710-108">**Data Type**</span></span>|<span data-ttu-id="07710-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="07710-109">**Key/Index**</span></span>|<span data-ttu-id="07710-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="07710-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="07710-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="07710-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="07710-112">int</span><span class="sxs-lookup"><span data-stu-id="07710-112">int</span></span>  <br/> |<span data-ttu-id="07710-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="07710-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="07710-114">Referenciado de [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="07710-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="07710-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="07710-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="07710-116">int</span><span class="sxs-lookup"><span data-stu-id="07710-116">int</span></span>  <br/> |<span data-ttu-id="07710-117">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="07710-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="07710-118">Referência de [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="07710-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

