---
title: tblLastInviteId
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contém a última ID de convite gerada (e usada na tabela tblPrincipalInvites) para cada usuário.
ms.openlocfilehash: 9d5ec67a4f5c3db8558c58834582d489fde00ab6
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815961"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="6d125-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="6d125-103">tblLastInviteId</span></span>
 
<span data-ttu-id="6d125-104">tblLastInviteId contém a última ID de convite gerada (e usada na tabela tblPrincipalInvites) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="6d125-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="6d125-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="6d125-105">**Columns**</span></span>

|<span data-ttu-id="6d125-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6d125-106">**Column**</span></span>|<span data-ttu-id="6d125-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6d125-107">**Type**</span></span>|<span data-ttu-id="6d125-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6d125-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6d125-109">prinID</span><span class="sxs-lookup"><span data-stu-id="6d125-109">prinID</span></span>  <br/> |<span data-ttu-id="6d125-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6d125-110">int, not null</span></span>  <br/> |<span data-ttu-id="6d125-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="6d125-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="6d125-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="6d125-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="6d125-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6d125-113">int, not null</span></span>  <br/> |<span data-ttu-id="6d125-114">ID do último convite usado.</span><span class="sxs-lookup"><span data-stu-id="6d125-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="6d125-115">**Teclas**</span><span class="sxs-lookup"><span data-stu-id="6d125-115">**Keys**</span></span>

|<span data-ttu-id="6d125-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6d125-116">**Column**</span></span>|<span data-ttu-id="6d125-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6d125-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6d125-118">prinID</span><span class="sxs-lookup"><span data-stu-id="6d125-118">prinID</span></span>  <br/> |<span data-ttu-id="6d125-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="6d125-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="6d125-120">prinID</span><span class="sxs-lookup"><span data-stu-id="6d125-120">prinID</span></span>  <br/> |<span data-ttu-id="6d125-121">Chave estrangeira com pesquisa na tabela tblPrincipal.prinID.</span><span class="sxs-lookup"><span data-stu-id="6d125-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="6d125-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="6d125-122">See also</span></span>

[<span data-ttu-id="6d125-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="6d125-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
