---
title: Tabela UserSite
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
ms.assetid: 1c2a3cf2-dc05-472e-8097-a31f3a1aafcb
description: A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido nas configurações de rede.
ms.openlocfilehash: 88df08875ea3254ee355a96aa3b12d3ee7f5ccaf
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799911"
---
# <a name="usersite-table"></a><span data-ttu-id="8f502-104">Tabela UserSite</span><span class="sxs-lookup"><span data-stu-id="8f502-104">UserSite table</span></span>
 
<span data-ttu-id="8f502-p102">A tabela UserSite é uma tabela de suporte. Cada registro representa um site de usuário definido nas configurações de rede.</span><span class="sxs-lookup"><span data-stu-id="8f502-p102">The UserSite table is a supporting table. Each record represents one user site defined in network configuration setting.</span></span>
  
|<span data-ttu-id="8f502-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8f502-107">**Column**</span></span>|<span data-ttu-id="8f502-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="8f502-108">**Data Type**</span></span>|<span data-ttu-id="8f502-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="8f502-109">**Key/Index**</span></span>|<span data-ttu-id="8f502-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="8f502-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8f502-111">**UserSiteKey**</span><span class="sxs-lookup"><span data-stu-id="8f502-111">**UserSiteKey**</span></span> <br/> |<span data-ttu-id="8f502-112">int</span><span class="sxs-lookup"><span data-stu-id="8f502-112">int</span></span>  <br/> |<span data-ttu-id="8f502-113">Primário</span><span class="sxs-lookup"><span data-stu-id="8f502-113">Primary</span></span>  <br/> |<span data-ttu-id="8f502-114">Número único de identificação do site de usuário.</span><span class="sxs-lookup"><span data-stu-id="8f502-114">Unique number identifying the user site.</span></span>  <br/> |
|<span data-ttu-id="8f502-115">**UserSiteName**</span><span class="sxs-lookup"><span data-stu-id="8f502-115">**UserSiteName**</span></span> <br/> |<span data-ttu-id="8f502-116">nvarchar(128)</span><span class="sxs-lookup"><span data-stu-id="8f502-116">nvarchar(128)</span></span>  <br/> |<span data-ttu-id="8f502-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="8f502-117">Unique</span></span>  <br/> |<span data-ttu-id="8f502-118">Nome do site do usuário.</span><span class="sxs-lookup"><span data-stu-id="8f502-118">User site's name.</span></span>  <br/> |
|<span data-ttu-id="8f502-119">**RegionKey**</span><span class="sxs-lookup"><span data-stu-id="8f502-119">**RegionKey**</span></span> <br/> |<span data-ttu-id="8f502-120">int</span><span class="sxs-lookup"><span data-stu-id="8f502-120">int</span></span>  <br/> |<span data-ttu-id="8f502-121">Externo</span><span class="sxs-lookup"><span data-stu-id="8f502-121">Foreign</span></span>  <br/> |<span data-ttu-id="8f502-122">Referenciado da [tabela Region](region.md).</span><span class="sxs-lookup"><span data-stu-id="8f502-122">Referenced from [Region table](region.md).</span></span>  <br/> |
   

