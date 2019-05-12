---
title: tblSiopWhiteList
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 05fc1df4-32eb-4d46-9d1c-e0b607091142
description: a tabela Siopwhitelist é a lista de suplementos registrados que podem ser associados a nós.
ms.openlocfilehash: f3389f3d4a956e00180303c09bd3eb264d786b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33924770"
---
# <a name="tblsiopwhitelist"></a><span data-ttu-id="7b8ce-103">tblSiopWhiteList</span><span class="sxs-lookup"><span data-stu-id="7b8ce-103">tblSiopWhiteList</span></span>
 
<span data-ttu-id="7b8ce-104">a tabela Siopwhitelist é a lista de suplementos registrados que podem ser associados a nós.</span><span class="sxs-lookup"><span data-stu-id="7b8ce-104">tblSiopWhiteList is the list of registered add-ins that can be associated with nodes.</span></span>
  
<span data-ttu-id="7b8ce-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="7b8ce-105">**Columns**</span></span>

|<span data-ttu-id="7b8ce-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7b8ce-106">**Column**</span></span>|<span data-ttu-id="7b8ce-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="7b8ce-107">**Type**</span></span>|<span data-ttu-id="7b8ce-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7b8ce-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="7b8ce-109">siopID</span><span class="sxs-lookup"><span data-stu-id="7b8ce-109">siopID</span></span>  <br/> |<span data-ttu-id="7b8ce-110">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="7b8ce-110">GUID, not null</span></span>  <br/> |<span data-ttu-id="7b8ce-111">GUID do suplemento.</span><span class="sxs-lookup"><span data-stu-id="7b8ce-111">GUID of the add-in.</span></span>  <br/> |
|<span data-ttu-id="7b8ce-112">siopName</span><span class="sxs-lookup"><span data-stu-id="7b8ce-112">siopName</span></span>  <br/> |<span data-ttu-id="7b8ce-113">nvarchar (50), não nulo</span><span class="sxs-lookup"><span data-stu-id="7b8ce-113">nvarchar (50), not null</span></span>  <br/> |<span data-ttu-id="7b8ce-114">Nome de exibição do add-in.</span><span class="sxs-lookup"><span data-stu-id="7b8ce-114">Display-name of the add-in.</span></span>  <br/> |
|<span data-ttu-id="7b8ce-115">siopUrl</span><span class="sxs-lookup"><span data-stu-id="7b8ce-115">siopUrl</span></span>  <br/> |<span data-ttu-id="7b8ce-116">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="7b8ce-116">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="7b8ce-117">URL do add-in.</span><span class="sxs-lookup"><span data-stu-id="7b8ce-117">URL of the add-in.</span></span>  <br/> |
   
<span data-ttu-id="7b8ce-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="7b8ce-118">**Key**</span></span>

|<span data-ttu-id="7b8ce-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7b8ce-119">**Column**</span></span>|<span data-ttu-id="7b8ce-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="7b8ce-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="7b8ce-121">siopID</span><span class="sxs-lookup"><span data-stu-id="7b8ce-121">siopID</span></span>  <br/> |<span data-ttu-id="7b8ce-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="7b8ce-122">Primary key.</span></span>  <br/> |
   

