---
title: tblLastInviteId
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contém a última ID de convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.
ms.openlocfilehash: 55eb9d9f5edbb3cc0e8c786b650e51cdc1e3d141
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tbllastinviteid"></a><span data-ttu-id="c9557-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="c9557-103">tblLastInviteId</span></span>
 
<span data-ttu-id="c9557-104">tblLastInviteId contém a última ID de convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="c9557-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="c9557-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="c9557-105">**Columns**</span></span>

|<span data-ttu-id="c9557-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c9557-106">**Column**</span></span>|<span data-ttu-id="c9557-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="c9557-107">**Type**</span></span>|<span data-ttu-id="c9557-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c9557-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="c9557-109">prinID</span><span class="sxs-lookup"><span data-stu-id="c9557-109">prinID</span></span>  <br/> |<span data-ttu-id="c9557-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="c9557-110">int, not null</span></span>  <br/> |<span data-ttu-id="c9557-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="c9557-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="c9557-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="c9557-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="c9557-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="c9557-113">int, not null</span></span>  <br/> |<span data-ttu-id="c9557-114">ID do último convite usado.</span><span class="sxs-lookup"><span data-stu-id="c9557-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="c9557-115">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="c9557-115">**Keys**</span></span>

|<span data-ttu-id="c9557-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="c9557-116">**Column**</span></span>|<span data-ttu-id="c9557-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="c9557-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="c9557-118">prinID</span><span class="sxs-lookup"><span data-stu-id="c9557-118">prinID</span></span>  <br/> |<span data-ttu-id="c9557-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="c9557-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="c9557-120">prinID</span><span class="sxs-lookup"><span data-stu-id="c9557-120">prinID</span></span>  <br/> |<span data-ttu-id="c9557-121">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="c9557-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="c9557-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="c9557-122">See also</span></span>

#### 

[<span data-ttu-id="c9557-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="c9557-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)

