---
title: Tabela MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: A tabela MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um vínculo entre dois sites do usuário.
ms.openlocfilehash: 18f0931feb46e69db76c93225ccc11398b4d6daf
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920009"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="1b6d5-104">Tabela MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="1b6d5-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="1b6d5-105">A tabela MonitoredUserSiteLink é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="1b6d5-106">Cada registro representa um vínculo entre dois sites do usuário.</span><span class="sxs-lookup"><span data-stu-id="1b6d5-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="1b6d5-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="1b6d5-107">**Column**</span></span>|<span data-ttu-id="1b6d5-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="1b6d5-108">**Data Type**</span></span>|<span data-ttu-id="1b6d5-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="1b6d5-109">**Key/Index**</span></span>|<span data-ttu-id="1b6d5-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="1b6d5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1b6d5-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="1b6d5-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="1b6d5-112">int</span><span class="sxs-lookup"><span data-stu-id="1b6d5-112">int</span></span>  <br/> |<span data-ttu-id="1b6d5-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="1b6d5-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="1b6d5-114">Referenciado de [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="1b6d5-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="1b6d5-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="1b6d5-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="1b6d5-116">int</span><span class="sxs-lookup"><span data-stu-id="1b6d5-116">int</span></span>  <br/> |<span data-ttu-id="1b6d5-117">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="1b6d5-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="1b6d5-118">Referência de [UserSite table](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="1b6d5-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

