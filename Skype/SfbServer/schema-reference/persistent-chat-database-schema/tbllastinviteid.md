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
ms.openlocfilehash: 5f94714bfe42d6777907f3ce3e467e4add7a00d8
ms.sourcegitcommit: b14cfca231b618ec28cf9f4efe11cb3e8aceb34b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/19/2018
ms.locfileid: "19504849"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="dd1de-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="dd1de-103">tblLastInviteId</span></span>
 
<span data-ttu-id="dd1de-104">tblLastInviteId contém a última ID de convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="dd1de-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="dd1de-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="dd1de-105">**Columns**</span></span>

|<span data-ttu-id="dd1de-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="dd1de-106">**Column**</span></span>|<span data-ttu-id="dd1de-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dd1de-107">**Type**</span></span>|<span data-ttu-id="dd1de-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="dd1de-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dd1de-109">prinID</span><span class="sxs-lookup"><span data-stu-id="dd1de-109">prinID</span></span>  <br/> |<span data-ttu-id="dd1de-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="dd1de-110">int, not null</span></span>  <br/> |<span data-ttu-id="dd1de-111">ID principal.</span><span class="sxs-lookup"><span data-stu-id="dd1de-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="dd1de-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="dd1de-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="dd1de-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="dd1de-113">int, not null</span></span>  <br/> |<span data-ttu-id="dd1de-114">ID do último convite usado.</span><span class="sxs-lookup"><span data-stu-id="dd1de-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="dd1de-115">**Chaves**</span><span class="sxs-lookup"><span data-stu-id="dd1de-115">**Keys**</span></span>

|<span data-ttu-id="dd1de-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="dd1de-116">**Column**</span></span>|<span data-ttu-id="dd1de-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="dd1de-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dd1de-118">prinID</span><span class="sxs-lookup"><span data-stu-id="dd1de-118">prinID</span></span>  <br/> |<span data-ttu-id="dd1de-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="dd1de-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="dd1de-120">prinID</span><span class="sxs-lookup"><span data-stu-id="dd1de-120">prinID</span></span>  <br/> |<span data-ttu-id="dd1de-121">Chave estrangeira com pesquisa na tabela Tblprincipal.</span><span class="sxs-lookup"><span data-stu-id="dd1de-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="dd1de-122">Consulte também</span><span class="sxs-lookup"><span data-stu-id="dd1de-122">See also</span></span>

[<span data-ttu-id="dd1de-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="dd1de-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)