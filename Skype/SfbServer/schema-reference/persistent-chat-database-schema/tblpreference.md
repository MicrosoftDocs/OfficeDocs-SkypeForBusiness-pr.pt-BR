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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contém as preferências do cliente dos usuários. Isso geralmente é usado por clientes anteriores ao Lync 2013.
ms.openlocfilehash: 426a9f6aebe6cc6e510e2a75093b9210d3a0ba46
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814549"
---
# <a name="tblpreference"></a><span data-ttu-id="70453-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="70453-104">tblPreference</span></span>

<span data-ttu-id="70453-105">tblPreference contém as preferências do cliente dos usuários.</span><span class="sxs-lookup"><span data-stu-id="70453-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="70453-106">Isso geralmente é usado por clientes anteriores ao Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="70453-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="70453-107">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="70453-107">**Columns**</span></span>


| <span data-ttu-id="70453-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="70453-108">**Column**</span></span>            | <span data-ttu-id="70453-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="70453-109">**Type**</span></span>                        | <span data-ttu-id="70453-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="70453-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="70453-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="70453-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="70453-112">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="70453-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="70453-113">Rótulo com um formato como: \<URI de SIP do usuário\></span><span class="sxs-lookup"><span data-stu-id="70453-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="70453-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="70453-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="70453-115">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="70453-115">int, not null</span></span>  <br/>            | <span data-ttu-id="70453-116">Um número sequencial (por rótulo) para fins de controle de versão.</span><span class="sxs-lookup"><span data-stu-id="70453-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="70453-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="70453-117">prefContent</span></span>  <br/>    | <span data-ttu-id="70453-118">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="70453-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="70453-119">Conteúdo codificado.</span><span class="sxs-lookup"><span data-stu-id="70453-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="70453-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="70453-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="70453-121">int, não nulo</span><span class="sxs-lookup"><span data-stu-id="70453-121">int, not null</span></span>  <br/>            | <span data-ttu-id="70453-122">ID da entidade de segurança que atualizou a preferência.</span><span class="sxs-lookup"><span data-stu-id="70453-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="70453-123">**Chave**</span><span class="sxs-lookup"><span data-stu-id="70453-123">**Key**</span></span>

|<span data-ttu-id="70453-124">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="70453-124">**Column**</span></span>|<span data-ttu-id="70453-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="70453-125">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="70453-126">\<prefLabel, prefSeqID\></span><span class="sxs-lookup"><span data-stu-id="70453-126">\<prefLabel, prefSeqID\></span></span>  <br/> |<span data-ttu-id="70453-127">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="70453-127">Primary key.</span></span>  <br/> |


