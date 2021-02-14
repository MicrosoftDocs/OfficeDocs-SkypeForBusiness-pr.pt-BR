---
title: tblPreference
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
ms.assetid: f94eb128-f782-42ff-a568-ed3529573bc8
description: tblPreference contém as preferências do cliente dos usuários. Isso geralmente é usado por clientes anteriores ao Lync 2013.
ms.openlocfilehash: 96cd017dd67a05f3240269f5bdcbd23f30fffd28
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815901"
---
# <a name="tblpreference"></a><span data-ttu-id="b4988-104">tblPreference</span><span class="sxs-lookup"><span data-stu-id="b4988-104">tblPreference</span></span>

<span data-ttu-id="b4988-105">tblPreference contém as preferências do cliente dos usuários.</span><span class="sxs-lookup"><span data-stu-id="b4988-105">tblPreference contains the users' client preferences.</span></span> <span data-ttu-id="b4988-106">Isso geralmente é usado por clientes anteriores ao Lync 2013.</span><span class="sxs-lookup"><span data-stu-id="b4988-106">This is generally used by clients previous to Lync 2013.</span></span>

<span data-ttu-id="b4988-107">**Columns**</span><span class="sxs-lookup"><span data-stu-id="b4988-107">**Columns**</span></span>


| <span data-ttu-id="b4988-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b4988-108">**Column**</span></span>            | <span data-ttu-id="b4988-109">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="b4988-109">**Type**</span></span>                        | <span data-ttu-id="b4988-110">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b4988-110">**Description**</span></span>                                                 |
|:----------------------|:--------------------------------|:----------------------------------------------------------------|
| <span data-ttu-id="b4988-111">prefLabel</span><span class="sxs-lookup"><span data-stu-id="b4988-111">prefLabel</span></span>  <br/>      | <span data-ttu-id="b4988-112">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="b4988-112">nvarchar (255), not null</span></span>  <br/> | <span data-ttu-id="b4988-113">Rótulo com um formato como: \<user sip uri\></span><span class="sxs-lookup"><span data-stu-id="b4988-113">Label with a format such as: \<user sip uri\></span></span>                   |
| <span data-ttu-id="b4988-114">prefSeqID</span><span class="sxs-lookup"><span data-stu-id="b4988-114">prefSeqID</span></span>  <br/>      | <span data-ttu-id="b4988-115">int, not null</span><span class="sxs-lookup"><span data-stu-id="b4988-115">int, not null</span></span>  <br/>            | <span data-ttu-id="b4988-116">Um número sequencial (por rótulo) para fins de versão.</span><span class="sxs-lookup"><span data-stu-id="b4988-116">A sequential number (per label) for versioning purposes.</span></span>  <br/> |
| <span data-ttu-id="b4988-117">prefContent</span><span class="sxs-lookup"><span data-stu-id="b4988-117">prefContent</span></span>  <br/>    | <span data-ttu-id="b4988-118">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="b4988-118">nvarchar (max)</span></span>  <br/>           | <span data-ttu-id="b4988-119">Conteúdo codificado.</span><span class="sxs-lookup"><span data-stu-id="b4988-119">Encoded content.</span></span>  <br/>                                         |
| <span data-ttu-id="b4988-120">lastModifiedBy</span><span class="sxs-lookup"><span data-stu-id="b4988-120">lastModifiedBy</span></span>  <br/> | <span data-ttu-id="b4988-121">int, not null</span><span class="sxs-lookup"><span data-stu-id="b4988-121">int, not null</span></span>  <br/>            | <span data-ttu-id="b4988-122">ID da entidade de entidade que atualizou a preferência.</span><span class="sxs-lookup"><span data-stu-id="b4988-122">ID of the principal that updated the preference.</span></span>  <br/>         |

<span data-ttu-id="b4988-123">**Chave**</span><span class="sxs-lookup"><span data-stu-id="b4988-123">**Key**</span></span>

|<span data-ttu-id="b4988-124">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="b4988-124">**Column**</span></span>|<span data-ttu-id="b4988-125">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="b4988-125">**Description**</span></span>|
|:-----|:-----|
|\<prefLabel, prefSeqID\>  <br/> |<span data-ttu-id="b4988-126">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="b4988-126">Primary key.</span></span>  <br/> |


