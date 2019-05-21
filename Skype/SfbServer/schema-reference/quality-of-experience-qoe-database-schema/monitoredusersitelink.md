---
title: Tabela MonitoredUserSiteLink
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: A tabela MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois sites de usuário.
ms.openlocfilehash: 789c1a721e1a8c204ff6e214f419de77d1b7f7bf
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294849"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="3b2b1-104">Tabela MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="3b2b1-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="3b2b1-105">A tabela MonitoredUserSiteLink é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="3b2b1-106">Cada registro representa um link entre dois sites de usuário.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="3b2b1-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3b2b1-107">**Column**</span></span>|<span data-ttu-id="3b2b1-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="3b2b1-108">**Data Type**</span></span>|<span data-ttu-id="3b2b1-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="3b2b1-109">**Key/Index**</span></span>|<span data-ttu-id="3b2b1-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="3b2b1-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3b2b1-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="3b2b1-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="3b2b1-112">int</span><span class="sxs-lookup"><span data-stu-id="3b2b1-112">int</span></span>  <br/> |<span data-ttu-id="3b2b1-113">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="3b2b1-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3b2b1-114">Referenciado da [tabela usersite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="3b2b1-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="3b2b1-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="3b2b1-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="3b2b1-116">int</span><span class="sxs-lookup"><span data-stu-id="3b2b1-116">int</span></span>  <br/> |<span data-ttu-id="3b2b1-117">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="3b2b1-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="3b2b1-118">Referência a partir da [tabela](usersite.md)do usersite.</span><span class="sxs-lookup"><span data-stu-id="3b2b1-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

