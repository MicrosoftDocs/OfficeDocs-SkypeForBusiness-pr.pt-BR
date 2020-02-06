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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela de usersite é uma tabela de suporte. Cada registro representa um site de usuário definido na configuração de rede.
ms.openlocfilehash: e1d6c4ddc3a756f2e5df0713d6abe1cb7b61295f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41804999"
---
# <a name="usersite-table"></a><span data-ttu-id="8b435-104">Tabela UserSite</span><span class="sxs-lookup"><span data-stu-id="8b435-104">UserSite table</span></span>
 
<span data-ttu-id="8b435-105">A tabela de usersite é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="8b435-105">The UserSite table is a supporting table.</span></span> <span data-ttu-id="8b435-106">Cada registro representa um site de usuário definido na configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="8b435-106">Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="8b435-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8b435-107">**Column**</span></span>|<span data-ttu-id="8b435-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="8b435-108">**Data Type**</span></span>|<span data-ttu-id="8b435-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="8b435-109">**Key/Index**</span></span>|<span data-ttu-id="8b435-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="8b435-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8b435-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="8b435-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="8b435-112">int</span><span class="sxs-lookup"><span data-stu-id="8b435-112">int</span></span>  <br/> |<span data-ttu-id="8b435-113">Primária</span><span class="sxs-lookup"><span data-stu-id="8b435-113">Primary</span></span>  <br/> |<span data-ttu-id="8b435-114">Número exclusivo que identifica o site do usuário.</span><span class="sxs-lookup"><span data-stu-id="8b435-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="8b435-115">**Usersitename**</span><span class="sxs-lookup"><span data-stu-id="8b435-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="8b435-116">nvarchar(128</span><span class="sxs-lookup"><span data-stu-id="8b435-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="8b435-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="8b435-117">Unique</span></span>  <br/> |<span data-ttu-id="8b435-118">Nome do site do usuário.</span><span class="sxs-lookup"><span data-stu-id="8b435-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="8b435-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="8b435-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="8b435-120">int</span><span class="sxs-lookup"><span data-stu-id="8b435-120">int</span></span>  <br/> |<span data-ttu-id="8b435-121">Exterior</span><span class="sxs-lookup"><span data-stu-id="8b435-121">Foreign</span></span>  <br/> |<span data-ttu-id="8b435-122">Referenciado da [tabela Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="8b435-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

