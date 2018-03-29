---
title: tabela Siopwhitelist
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: a tabela Siopwhitelist é a lista de suplementos registrados que podem ser associados a nós.
ms.openlocfilehash: 0653ec7f4a663479f7b7d4787eee4dc0a1045aac
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="dfc6b-103">tabela Siopwhitelist</span><span class="sxs-lookup"><span data-stu-id="dfc6b-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="dfc6b-104">a tabela Siopwhitelist é a lista de suplementos registrados que podem ser associados a nós.</span><span class="sxs-lookup"><span data-stu-id="dfc6b-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="dfc6b-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="dfc6b-105">**Columns**</span></span>

|<span data-ttu-id="dfc6b-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="dfc6b-106">**Column**</span></span>|<span data-ttu-id="dfc6b-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="dfc6b-107">**Type**</span></span>|<span data-ttu-id="dfc6b-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="dfc6b-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="dfc6b-109">siopID</span><span class="sxs-lookup"><span data-stu-id="dfc6b-109">siopID</span></span>  <br/> |<span data-ttu-id="dfc6b-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="dfc6b-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="dfc6b-111">GUID do suplemento.</span><span class="sxs-lookup"><span data-stu-id="dfc6b-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="dfc6b-112">siopName</span><span class="sxs-lookup"><span data-stu-id="dfc6b-112">siopName</span></span>  <br/> |<span data-ttu-id="dfc6b-113">nvarchar (50), não nulo</span><span class="sxs-lookup"><span data-stu-id="dfc6b-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="dfc6b-114">Nome de exibição do add-in.</span><span class="sxs-lookup"><span data-stu-id="dfc6b-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="dfc6b-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="dfc6b-115">siopUrl</span></span>  <br/> |<span data-ttu-id="dfc6b-116">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="dfc6b-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="dfc6b-117">URL do add-in.</span><span class="sxs-lookup"><span data-stu-id="dfc6b-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="dfc6b-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="dfc6b-118">**Key**</span></span>

|<span data-ttu-id="dfc6b-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="dfc6b-119">**Column**</span></span>|<span data-ttu-id="dfc6b-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="dfc6b-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="dfc6b-121">siopID</span><span class="sxs-lookup"><span data-stu-id="dfc6b-121">siopID</span></span>  <br/> |<span data-ttu-id="dfc6b-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="dfc6b-122">Primary key.</span></span>  <br/> |
   

