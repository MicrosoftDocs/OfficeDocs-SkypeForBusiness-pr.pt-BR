---
title: Tabela UserSite
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela de usersite é uma tabela de suporte. Cada registro representa um site de usuário definido na configuração de rede.
ms.openlocfilehash: 21f60afdb1690024f85dc74e11f856642413e6a8
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294569"
---
# <a name="usersite-table"></a><span data-ttu-id="3d0cc-104">Tabela UserSite</span><span class="sxs-lookup"><span data-stu-id="3d0cc-104">UserSite table</span></span>
 
<span data-ttu-id="3d0cc-105">A tabela de usersite é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="3d0cc-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="3d0cc-106">Cada registro representa um site de usuário definido na configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="3d0cc-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="3d0cc-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3d0cc-107">**Column**</span></span>|<span data-ttu-id="3d0cc-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="3d0cc-108">**Data Type**</span></span>|<span data-ttu-id="3d0cc-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="3d0cc-109">**Key/Index**</span></span>|<span data-ttu-id="3d0cc-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="3d0cc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3d0cc-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="3d0cc-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="3d0cc-112">int</span><span class="sxs-lookup"><span data-stu-id="3d0cc-112">int</span></span>  <br/> |<span data-ttu-id="3d0cc-113">Primária</span><span class="sxs-lookup"><span data-stu-id="3d0cc-113">Primary</span></span>  <br/> |<span data-ttu-id="3d0cc-114">Número exclusivo que identifica o site do usuário.</span><span class="sxs-lookup"><span data-stu-id="3d0cc-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="3d0cc-115">**Usersitename**</span><span class="sxs-lookup"><span data-stu-id="3d0cc-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="3d0cc-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="3d0cc-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="3d0cc-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="3d0cc-117">Unique</span></span>  <br/> |<span data-ttu-id="3d0cc-118">Nome do site do usuário.</span><span class="sxs-lookup"><span data-stu-id="3d0cc-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="3d0cc-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="3d0cc-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="3d0cc-120">int</span><span class="sxs-lookup"><span data-stu-id="3d0cc-120">int</span></span>  <br/> |<span data-ttu-id="3d0cc-121">Exterior</span><span class="sxs-lookup"><span data-stu-id="3d0cc-121">Foreign</span></span>  <br/> |<span data-ttu-id="3d0cc-122">Referenciado da [tabela Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="3d0cc-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

