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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 16edc24a-2718-4bb4-b05c-bc7aafa97963
description: A tabela MonitoredUserSiteLink é uma tabela de suporte. Cada registro representa um link entre dois sites de usuário.
ms.openlocfilehash: 2cf229947da143fb01b3009020cfa432a4b558a0
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807789"
---
# <a name="monitoredusersitelink-table"></a><span data-ttu-id="fd4f5-104">Tabela MonitoredUserSiteLink</span><span class="sxs-lookup"><span data-stu-id="fd4f5-104">MonitoredUserSiteLink table</span></span>
 
<span data-ttu-id="fd4f5-105">A tabela MonitoredUserSiteLink é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-105">The MonitoredUserSiteLink table is a supporting table.</span></span> <span data-ttu-id="fd4f5-106">Cada registro representa um link entre dois sites de usuário.</span><span class="sxs-lookup"><span data-stu-id="fd4f5-106">Each record represents one link between two user sites.</span></span>
  
|<span data-ttu-id="fd4f5-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="fd4f5-107">**Column**</span></span>|<span data-ttu-id="fd4f5-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="fd4f5-108">**Data Type**</span></span>|<span data-ttu-id="fd4f5-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="fd4f5-109">**Key/Index**</span></span>|<span data-ttu-id="fd4f5-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="fd4f5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="fd4f5-111">**UserSite1Key**</span><span class="sxs-lookup"><span data-stu-id="fd4f5-111">**UserSite1Key**</span></span> <br/> |<span data-ttu-id="fd4f5-112">int</span><span class="sxs-lookup"><span data-stu-id="fd4f5-112">int</span></span>  <br/> |<span data-ttu-id="fd4f5-113">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="fd4f5-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="fd4f5-114">Referenciado da [tabela usersite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="fd4f5-114">Referenced from the [UserSite table](usersite.md).</span></span>  <br/> |
|<span data-ttu-id="fd4f5-115">**UserSite2Key**</span><span class="sxs-lookup"><span data-stu-id="fd4f5-115">**UserSite2Key**</span></span> <br/> |<span data-ttu-id="fd4f5-116">int</span><span class="sxs-lookup"><span data-stu-id="fd4f5-116">int</span></span>  <br/> |<span data-ttu-id="fd4f5-117">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="fd4f5-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="fd4f5-118">Referência a partir da [tabela do usersite](usersite.md).</span><span class="sxs-lookup"><span data-stu-id="fd4f5-118">Reference from the [UserSite table](usersite.md).</span></span>  <br/> |
   

