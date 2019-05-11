---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contém a última ID de convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.
ms.openlocfilehash: f57ca67a91b71b9245644a53eb3e5c5771ca6fb0
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929900"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="fa13d-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="fa13d-103">tblLastInviteId</span></span>
 
<span data-ttu-id="fa13d-104">tblLastInviteId contém a última ID de convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="fa13d-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="fa13d-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="fa13d-105">**Columns**</span></span>

|<span data-ttu-id="fa13d-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="fa13d-106">**Column**</span></span>|<span data-ttu-id="fa13d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="fa13d-107">**Type**</span></span>|<span data-ttu-id="fa13d-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fa13d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="fa13d-109">prinID</span><span class="sxs-lookup"><span data-stu-id="fa13d-109">prinID</span></span>  <br/> |<span data-ttu-id="fa13d-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="fa13d-110">int, not null</span></span>  <br/> |<span data-ttu-id="fa13d-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="fa13d-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="fa13d-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="fa13d-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="fa13d-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="fa13d-113">int, not null</span></span>  <br/> |<span data-ttu-id="fa13d-114">ID do último convite usado.</span><span class="sxs-lookup"><span data-stu-id="fa13d-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="fa13d-115">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="fa13d-115">**Keys**</span></span>

|<span data-ttu-id="fa13d-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="fa13d-116">**Column**</span></span>|<span data-ttu-id="fa13d-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="fa13d-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="fa13d-118">prinID</span><span class="sxs-lookup"><span data-stu-id="fa13d-118">prinID</span></span>  <br/> |<span data-ttu-id="fa13d-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="fa13d-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="fa13d-120">prinID</span><span class="sxs-lookup"><span data-stu-id="fa13d-120">prinID</span></span>  <br/> |<span data-ttu-id="fa13d-121">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="fa13d-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="fa13d-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="fa13d-122">See also</span></span>

[<span data-ttu-id="fa13d-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="fa13d-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
