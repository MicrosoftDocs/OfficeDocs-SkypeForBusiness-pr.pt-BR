---
title: tblLastInviteId
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
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contém a ID do último convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.
ms.openlocfilehash: 17d1b725da034f79f8efc9ff9071c36430efde7d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814569"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="9eead-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="9eead-103">tblLastInviteId</span></span>
 
<span data-ttu-id="9eead-104">tblLastInviteId contém a ID do último convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="9eead-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="9eead-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="9eead-105">**Columns**</span></span>

|<span data-ttu-id="9eead-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9eead-106">**Column**</span></span>|<span data-ttu-id="9eead-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="9eead-107">**Type**</span></span>|<span data-ttu-id="9eead-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9eead-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="9eead-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="9eead-109">prinID</span></span>  <br/> |<span data-ttu-id="9eead-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="9eead-110">int, not null</span></span>  <br/> |<span data-ttu-id="9eead-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="9eead-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="9eead-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="9eead-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="9eead-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="9eead-113">int, not null</span></span>  <br/> |<span data-ttu-id="9eead-114">ID do convite usado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="9eead-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="9eead-115">**As**</span><span class="sxs-lookup"><span data-stu-id="9eead-115">**Keys**</span></span>

|<span data-ttu-id="9eead-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9eead-116">**Column**</span></span>|<span data-ttu-id="9eead-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="9eead-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="9eead-118">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="9eead-118">prinID</span></span>  <br/> |<span data-ttu-id="9eead-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="9eead-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="9eead-120">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="9eead-120">prinID</span></span>  <br/> |<span data-ttu-id="9eead-121">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="9eead-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="9eead-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="9eead-122">See also</span></span>

[<span data-ttu-id="9eead-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="9eead-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
