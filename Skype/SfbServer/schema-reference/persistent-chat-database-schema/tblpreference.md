---
title: tblPreference
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contém as preferências do cliente dos usuários. Isso geralmente é usado por clientes anteriores ao Lync 2013.
ms.openlocfilehash: b646bbe65c8090295c070a4fdc88b8339a62e4ab
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295339"
---
# <a name="tblpreference"></a><span data-ttu-id="6c713-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="6c713-104">tblPreference</span></span>

<span data-ttu-id="6c713-105">tblPreference contém as preferências do cliente dos usuários.</span><span class="sxs-lookup"><span data-stu-id="6c713-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="6c713-106">Isso geralmente é usado por clientes anteriores ao Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="6c713-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="6c713-107">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="6c713-107">**Columns**</span></span>


| <span data-ttu-id="6c713-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6c713-108">**Column**</span></span>            | <span data-ttu-id="6c713-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6c713-109">**Type**</span></span>                        | <span data-ttu-id="6c713-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6c713-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="6c713-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="6c713-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="6c713-112">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="6c713-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="6c713-113">Rótulo com um formato como: \<URI de SIP do usuário\></span><span class="sxs-lookup"><span data-stu-id="6c713-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="6c713-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="6c713-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="6c713-115">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6c713-115">int, not null</span></span>  <br/>            | <span data-ttu-id="6c713-116">Um número sequencial (por rótulo) para fins de controle de versão.</span><span class="sxs-lookup"><span data-stu-id="6c713-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="6c713-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="6c713-117">prefContent</span></span>  <br/>    | <span data-ttu-id="6c713-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="6c713-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="6c713-119">Conteúdo codificado.</span><span class="sxs-lookup"><span data-stu-id="6c713-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="6c713-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="6c713-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="6c713-121">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="6c713-121">int, not null</span></span>  <br/>            | <span data-ttu-id="6c713-122">ID da entidade de segurança que atualizou a preferência.</span><span class="sxs-lookup"><span data-stu-id="6c713-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="6c713-123">**Chave**</span><span class="sxs-lookup"><span data-stu-id="6c713-123">**Key**</span></span>

|<span data-ttu-id="6c713-124">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6c713-124">**Column**</span></span>|<span data-ttu-id="6c713-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6c713-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="6c713-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="6c713-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="6c713-127">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="6c713-127">Primary key.</span></span>  <br/> |


