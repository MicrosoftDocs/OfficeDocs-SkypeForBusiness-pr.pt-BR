---
title: tblPreference
ms.reviewer: ''
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
ms.openlocfilehash: b5036d9c71feaea6406ecdcaa6f15b61f64d5ad3
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30879788"
---
# <a name="tblpreference"></a><span data-ttu-id="12046-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="12046-104">tblPreference</span></span>

<span data-ttu-id="12046-105">tblPreference contém preferências do cliente dos usuários.</span><span class="sxs-lookup"><span data-stu-id="12046-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="12046-106">Isso é geralmente usado pelos clientes anterior para o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="12046-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="12046-107">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="12046-107">**Columns**</span></span>


| <span data-ttu-id="12046-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="12046-108">**Column**</span></span>            | <span data-ttu-id="12046-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="12046-109">**Type**</span></span>                        | <span data-ttu-id="12046-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="12046-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="12046-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="12046-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="12046-112">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="12046-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="12046-113">Etiqueta com um formato como: \<uri de sip do usuário\></span><span class="sxs-lookup"><span data-stu-id="12046-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="12046-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="12046-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="12046-115">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="12046-115">int, not null</span></span>  <br/>            | <span data-ttu-id="12046-116">Um número sequencial (por etiqueta) para fins de controle de versão.</span><span class="sxs-lookup"><span data-stu-id="12046-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="12046-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="12046-117">prefContent</span></span>  <br/>    | <span data-ttu-id="12046-118">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="12046-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="12046-119">Conteúdo codificado.</span><span class="sxs-lookup"><span data-stu-id="12046-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="12046-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="12046-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="12046-121">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="12046-121">int, not null</span></span>  <br/>            | <span data-ttu-id="12046-122">ID da entidade que atualizou a preferência.</span><span class="sxs-lookup"><span data-stu-id="12046-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="12046-123">**Chave**</span><span class="sxs-lookup"><span data-stu-id="12046-123">**Key**</span></span>

|<span data-ttu-id="12046-124">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="12046-124">**Column**</span></span>|<span data-ttu-id="12046-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="12046-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="12046-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="12046-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="12046-127">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="12046-127">Primary key.</span></span>  <br/> |


