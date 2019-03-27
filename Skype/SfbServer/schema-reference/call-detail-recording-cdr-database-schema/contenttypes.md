---
title: Tabela ContentTypes Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e de sessões de conferência. Cada registro na tabela representa um tipo de conteúdo.
ms.openlocfilehash: 77bbe375a5870d11c7e4a17a0f32392fe14975a0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30894983"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="892f2-104">Tabela ContentTypes Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="892f2-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="892f2-105">A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e de sessões de conferência.</span><span class="sxs-lookup"><span data-stu-id="892f2-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="892f2-106">Cada registro na tabela representa um tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="892f2-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="892f2-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="892f2-107">**Column**</span></span>|<span data-ttu-id="892f2-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="892f2-108">**Data Type**</span></span>|<span data-ttu-id="892f2-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="892f2-109">**Key/Index**</span></span>|<span data-ttu-id="892f2-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="892f2-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="892f2-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="892f2-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="892f2-112">int</span><span class="sxs-lookup"><span data-stu-id="892f2-112">int</span></span>  <br/> |<span data-ttu-id="892f2-113">Primária</span><span class="sxs-lookup"><span data-stu-id="892f2-113">Primary</span></span>  <br/> |<span data-ttu-id="892f2-114">Número exclusivo que identifica o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="892f2-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="892f2-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="892f2-115">**ContentType**</span></span> <br/> |<span data-ttu-id="892f2-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="892f2-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="892f2-117">Nome do tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="892f2-117">Content type name.</span></span>  <br/> |
   

