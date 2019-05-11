---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contém preferências do cliente dos usuários. Isso é geralmente usado pelos clientes anterior para o Lync 2013.
ms.openlocfilehash: 1c8b098d308802428dcb314d2163b9e32863b547
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33929914"
---
# <a name="tblpreference"></a><span data-ttu-id="8ca20-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="8ca20-104">tblPreference</span></span>

<span data-ttu-id="8ca20-105">tblPreference contém preferências do cliente dos usuários.</span><span class="sxs-lookup"><span data-stu-id="8ca20-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="8ca20-106">Isso é geralmente usado pelos clientes anterior para o Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="8ca20-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="8ca20-107">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="8ca20-107">**Columns**</span></span>


| <span data-ttu-id="8ca20-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8ca20-108">**Column**</span></span>            | <span data-ttu-id="8ca20-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8ca20-109">**Type**</span></span>                        | <span data-ttu-id="8ca20-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8ca20-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="8ca20-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="8ca20-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="8ca20-112">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="8ca20-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="8ca20-113">Etiqueta com um formato como: \<uri de sip do usuário\></span><span class="sxs-lookup"><span data-stu-id="8ca20-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="8ca20-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="8ca20-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="8ca20-115">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="8ca20-115">int, not null</span></span>  <br/>            | <span data-ttu-id="8ca20-116">Um número sequencial (por etiqueta) para fins de controle de versão.</span><span class="sxs-lookup"><span data-stu-id="8ca20-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="8ca20-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="8ca20-117">prefContent</span></span>  <br/>    | <span data-ttu-id="8ca20-118">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="8ca20-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="8ca20-119">Conteúdo codificado.</span><span class="sxs-lookup"><span data-stu-id="8ca20-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="8ca20-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="8ca20-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="8ca20-121">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="8ca20-121">int, not null</span></span>  <br/>            | <span data-ttu-id="8ca20-122">ID da entidade que atualizou a preferência.</span><span class="sxs-lookup"><span data-stu-id="8ca20-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="8ca20-123">**Chave**</span><span class="sxs-lookup"><span data-stu-id="8ca20-123">**Key**</span></span>

|<span data-ttu-id="8ca20-124">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8ca20-124">**Column**</span></span>|<span data-ttu-id="8ca20-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="8ca20-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="8ca20-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="8ca20-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="8ca20-127">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="8ca20-127">Primary key.</span></span>  <br/> |


