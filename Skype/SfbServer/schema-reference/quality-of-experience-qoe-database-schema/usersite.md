---
title: Tabela UserSite
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido na definição de configuração de rede.
ms.openlocfilehash: a52f5cd9aa7059e2b545dec3bcc7ccb86191347a
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212043"
---
# <a name="usersite-table"></a><span data-ttu-id="39941-104">Tabela UserSite</span><span class="sxs-lookup"><span data-stu-id="39941-104">UserSite table</span></span>
 
<span data-ttu-id="39941-105">A tabela UserSite é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="39941-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="39941-106">Cada registro representa um site de usuário definido na definição de configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="39941-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="39941-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="39941-107">**Column**</span></span>|<span data-ttu-id="39941-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="39941-108">**Data Type**</span></span>|<span data-ttu-id="39941-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="39941-109">**Key/Index**</span></span>|<span data-ttu-id="39941-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="39941-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="39941-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="39941-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="39941-112">int</span><span class="sxs-lookup"><span data-stu-id="39941-112">int</span></span>  <br/> |<span data-ttu-id="39941-113">Primária</span><span class="sxs-lookup"><span data-stu-id="39941-113">Primary</span></span>  <br/> |<span data-ttu-id="39941-114">Número exclusivo que identifica o site de usuário.</span><span class="sxs-lookup"><span data-stu-id="39941-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="39941-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="39941-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="39941-116">nvarchar (128)</span><span class="sxs-lookup"><span data-stu-id="39941-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="39941-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="39941-117">Unique</span></span>  <br/> |<span data-ttu-id="39941-118">Nome do site do usuário.</span><span class="sxs-lookup"><span data-stu-id="39941-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="39941-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="39941-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="39941-120">int</span><span class="sxs-lookup"><span data-stu-id="39941-120">int</span></span>  <br/> |<span data-ttu-id="39941-121">Externa</span><span class="sxs-lookup"><span data-stu-id="39941-121">Foreign</span></span>  <br/> |<span data-ttu-id="39941-122">Citada em [Region table](region.md).</span><span class="sxs-lookup"><span data-stu-id="39941-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

