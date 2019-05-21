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
localization_priority: Normal
ms.assetid: 222b3508-5963-4ddc-b4f3-e8412767e61b
description: tblLastInviteId contém a ID do último convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.
ms.openlocfilehash: f36b0824bb8e9dbf2cb0aa14575cc1649bde708a
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295353"
---
# <a name="tbllastinviteid"></a><span data-ttu-id="df7ca-103">tblLastInviteId</span><span class="sxs-lookup"><span data-stu-id="df7ca-103">tblLastInviteId</span></span>
 
<span data-ttu-id="df7ca-104">tblLastInviteId contém a ID do último convite que foi gerada (e usada na tabela tblPrincipalInvites) para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="df7ca-104">tblLastInviteId contains the last invite ID that was generated (and used in the tblPrincipalInvites table) for each user.</span></span>
  
<span data-ttu-id="df7ca-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="df7ca-105">**Columns**</span></span>

|<span data-ttu-id="df7ca-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="df7ca-106">**Column**</span></span>|<span data-ttu-id="df7ca-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="df7ca-107">**Type**</span></span>|<span data-ttu-id="df7ca-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="df7ca-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="df7ca-109">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="df7ca-109">prinID</span></span>  <br/> |<span data-ttu-id="df7ca-110">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="df7ca-110">int, not null</span></span>  <br/> |<span data-ttu-id="df7ca-111">ID da entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="df7ca-111">Principal ID.</span></span>  <br/> |
|<span data-ttu-id="df7ca-112">lastInviteID</span><span class="sxs-lookup"><span data-stu-id="df7ca-112">lastInviteID</span></span>  <br/> |<span data-ttu-id="df7ca-113">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="df7ca-113">int, not null</span></span>  <br/> |<span data-ttu-id="df7ca-114">ID do convite usado pela última vez.</span><span class="sxs-lookup"><span data-stu-id="df7ca-114">Last used invite ID.</span></span>  <br/> |
   
<span data-ttu-id="df7ca-115">**As**</span><span class="sxs-lookup"><span data-stu-id="df7ca-115">**Keys**</span></span>

|<span data-ttu-id="df7ca-116">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="df7ca-116">**Column**</span></span>|<span data-ttu-id="df7ca-117">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="df7ca-117">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="df7ca-118">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="df7ca-118">prinID</span></span>  <br/> |<span data-ttu-id="df7ca-119">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="df7ca-119">Primary key.</span></span>  <br/> |
|<span data-ttu-id="df7ca-120">multiimprimir</span><span class="sxs-lookup"><span data-stu-id="df7ca-120">prinID</span></span>  <br/> |<span data-ttu-id="df7ca-121">Chave estrangeira com Lookup na tabela tblPrincipal. retoid.</span><span class="sxs-lookup"><span data-stu-id="df7ca-121">Foreign key with lookup in tblPrincipal.prinID table.</span></span>  <br/> |
   
## <a name="see-also"></a><span data-ttu-id="df7ca-122">Confira também</span><span class="sxs-lookup"><span data-stu-id="df7ca-122">See also</span></span>

[<span data-ttu-id="df7ca-123">tblPrincipalInvites</span><span class="sxs-lookup"><span data-stu-id="df7ca-123">tblPrincipalInvites</span></span>](tblprincipalinvites.md)
