---
title: tblSiopWhiteList
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
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: A tabela SiopWhiteList é a lista de suplementos registrados que podem ser associados aos nós.
ms.openlocfilehash: cf7a727bd34e5c6f29f5bf0b203411983c90ae53
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831481"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="0a084-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="0a084-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="0a084-104">A tabela SiopWhiteList é a lista de suplementos registrados que podem ser associados aos nós.</span><span class="sxs-lookup"><span data-stu-id="0a084-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="0a084-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="0a084-105">**Columns**</span></span>

|<span data-ttu-id="0a084-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0a084-106">**Column**</span></span>|<span data-ttu-id="0a084-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="0a084-107">**Type**</span></span>|<span data-ttu-id="0a084-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0a084-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="0a084-109">siopID</span><span class="sxs-lookup"><span data-stu-id="0a084-109">siopID</span></span>  <br/> |<span data-ttu-id="0a084-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="0a084-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="0a084-111">GUID do suplemento.</span><span class="sxs-lookup"><span data-stu-id="0a084-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="0a084-112">siopName</span><span class="sxs-lookup"><span data-stu-id="0a084-112">siopName</span></span>  <br/> |<span data-ttu-id="0a084-113">nvarchar (50), não nulo</span><span class="sxs-lookup"><span data-stu-id="0a084-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="0a084-114">Nome de exibição do suplemento.</span><span class="sxs-lookup"><span data-stu-id="0a084-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="0a084-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="0a084-115">siopUrl</span></span>  <br/> |<span data-ttu-id="0a084-116">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="0a084-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="0a084-117">URL do suplemento.</span><span class="sxs-lookup"><span data-stu-id="0a084-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="0a084-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="0a084-118">**Key**</span></span>

|<span data-ttu-id="0a084-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0a084-119">**Column**</span></span>|<span data-ttu-id="0a084-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="0a084-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="0a084-121">siopID</span><span class="sxs-lookup"><span data-stu-id="0a084-121">siopID</span></span>  <br/> |<span data-ttu-id="0a084-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="0a084-122">Primary key.</span></span>  <br/> |
   

