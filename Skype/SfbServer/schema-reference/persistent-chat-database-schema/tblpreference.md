---
title: tblPreference
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contém preferências do cliente dos usuários. Isso é geralmente usado pelos clientes anterior para o Lync 2013.
ms.openlocfilehash: 28656951c80e6e4010e6ca559e3f650e2b9bac4b
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblpreference"></a><span data-ttu-id="77216-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="77216-104">tblPreference</span></span>
 
<span data-ttu-id="77216-105">tblPreference contém preferências do cliente dos usuários.</span><span class="sxs-lookup"><span data-stu-id="77216-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="77216-106">Isso é geralmente usado pelos clientes anterior para o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="77216-106">This is generally used by clients previous to Lync 2013.</span></span>
  
<span data-ttu-id="77216-107">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="77216-107">**Columns**</span></span>

|<span data-ttu-id="77216-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="77216-108">**Column**</span></span>|<span data-ttu-id="77216-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="77216-109">**Type**</span></span>|<span data-ttu-id="77216-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="77216-110">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="77216-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="77216-111">prefLabel</span></span>  <br/> |<span data-ttu-id="77216-112">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="77216-112">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="77216-113">Etiqueta com um formato como: \<uri de sip do usuário\></span><span class="sxs-lookup"><span data-stu-id="77216-113">Label with a format such as: \<user sip uri\></span></span>|<span data-ttu-id="77216-114">nome de usuário. \<preferência set\>.</span><span class="sxs-lookup"><span data-stu-id="77216-114">username.\<preference set\>.</span></span>  <br/> |
|<span data-ttu-id="77216-115">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="77216-115">prefSeqID</span></span>  <br/> |<span data-ttu-id="77216-116">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="77216-116">int, not null</span></span>  <br/> |<span data-ttu-id="77216-117">Um número sequencial (por etiqueta) para fins de controle de versão.</span><span class="sxs-lookup"><span data-stu-id="77216-117">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
|<span data-ttu-id="77216-118">prefContent</span><span class="sxs-lookup"><span data-stu-id="77216-118">prefContent</span></span>  <br/> |<span data-ttu-id="77216-119">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="77216-119">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="77216-120">Conteúdo codificado.</span><span class="sxs-lookup"><span data-stu-id="77216-120">Encoded content.</span></span>  <br/> |
|<span data-ttu-id="77216-121">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="77216-121">lastModifiedBy</span></span>  <br/> |<span data-ttu-id="77216-122">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="77216-122">int, not null</span></span>  <br/> |<span data-ttu-id="77216-123">ID da entidade que atualizou a preferência.</span><span class="sxs-lookup"><span data-stu-id="77216-123">ID of the principal that updated the preference.</span></span>  <br/> |
   
<span data-ttu-id="77216-124">**Chave**</span><span class="sxs-lookup"><span data-stu-id="77216-124">**Key**</span></span>

|<span data-ttu-id="77216-125">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="77216-125">**Column**</span></span>|<span data-ttu-id="77216-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="77216-126">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="77216-127">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="77216-127">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="77216-128">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="77216-128">Primary key.</span></span>  <br/> |
   

