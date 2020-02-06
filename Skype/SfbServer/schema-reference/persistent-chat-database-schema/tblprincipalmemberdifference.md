---
title: tblPrincipalMemberDifference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0b94f555-6888-4fe0-a048-4660a2513276
description: tblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processados pelas etapas de sincronização dos serviços de domínio Active Directory mais recentes.
ms.openlocfilehash: c7e965658c9e351a7a2d079921b7abe8166b48ad
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814069"
---
# <a name="tblprincipalmemberdifference"></a><span data-ttu-id="b4fdf-103">tblPrincipalMemberDifference</span><span class="sxs-lookup"><span data-stu-id="b4fdf-103">tblPrincipalMemberDifference</span></span>
 
<span data-ttu-id="b4fdf-104">tblPrincipalMemberDifference contém alterações de associação de grupo (membros adicionados e removidos) que ainda não foram processados pelas etapas de sincronização dos serviços de domínio Active Directory mais recentes.</span><span class="sxs-lookup"><span data-stu-id="b4fdf-104">tblPrincipalMemberDifference contains group membership changes (both added and removed members) that have not yet been processed by the later Active Directory Domain Services Sync steps.</span></span>
  
<span data-ttu-id="b4fdf-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="b4fdf-105">**Columns**</span></span>

|<span data-ttu-id="b4fdf-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b4fdf-106">**Column**</span></span>|<span data-ttu-id="b4fdf-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b4fdf-107">**Type**</span></span>|<span data-ttu-id="b4fdf-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b4fdf-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="b4fdf-109">prinGuid</span><span class="sxs-lookup"><span data-stu-id="b4fdf-109">prinGuid</span></span>  <br/> |<span data-ttu-id="b4fdf-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="b4fdf-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="b4fdf-111">O principal GUID do grupo que foi alterado.</span><span class="sxs-lookup"><span data-stu-id="b4fdf-111">Principal GUID of the group that changed.</span></span>  <br/> |
|<span data-ttu-id="b4fdf-112">memberADPath</span><span class="sxs-lookup"><span data-stu-id="b4fdf-112">memberADPath</span></span>  <br/> |<span data-ttu-id="b4fdf-113">nvarchar (256)</span><span class="sxs-lookup"><span data-stu-id="b4fdf-113">nvarchar (256)</span></span>  <br/> |<span data-ttu-id="b4fdf-114">Nome diferenciado do membro.</span><span class="sxs-lookup"><span data-stu-id="b4fdf-114">Distinguished name of the member.</span></span>  <br/> |
|<span data-ttu-id="b4fdf-115">memberRemoved</span><span class="sxs-lookup"><span data-stu-id="b4fdf-115">memberRemoved</span></span>  <br/> |<span data-ttu-id="b4fdf-116">bit, e não nulo</span><span class="sxs-lookup"><span data-stu-id="b4fdf-116">bit, not null</span></span>  <br/> |<span data-ttu-id="b4fdf-117">Falso se o membro tiver sido adicionado.</span><span class="sxs-lookup"><span data-stu-id="b4fdf-117">False if the member was added.</span></span> <span data-ttu-id="b4fdf-118">Verdadeiro se o membro tiver sido removido.</span><span class="sxs-lookup"><span data-stu-id="b4fdf-118">True if the member was removed.</span></span>  <br/> |
   
<span data-ttu-id="b4fdf-119">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b4fdf-119">**Key**</span></span>

|<span data-ttu-id="b4fdf-120">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b4fdf-120">**Column**</span></span>|<span data-ttu-id="b4fdf-121">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b4fdf-121">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="b4fdf-122">\<prinGuid, memberADPath\></span><span class="sxs-lookup"><span data-stu-id="b4fdf-122">\<prinGuid, memberADPath\></span></span>  <br/> |<span data-ttu-id="b4fdf-123">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="b4fdf-123">Primary key.</span></span>  <br/> |
   

