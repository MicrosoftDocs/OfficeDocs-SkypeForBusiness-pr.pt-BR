---
title: Tabela ContentTypes no Skype for Business Server 2015
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
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e em sessões de conferência. Cada registro na tabela representa um tipo de conteúdo.
ms.openlocfilehash: 6dadf7de0107005cca751e27f0c0250bc8f9f03a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815299"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e6eed-104">Tabela ContentTypes no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e6eed-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e6eed-105">A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e em sessões de conferência.</span><span class="sxs-lookup"><span data-stu-id="e6eed-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="e6eed-106">Cada registro na tabela representa um tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e6eed-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="e6eed-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e6eed-107">**Column**</span></span>|<span data-ttu-id="e6eed-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e6eed-108">**Data Type**</span></span>|<span data-ttu-id="e6eed-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="e6eed-109">**Key/Index**</span></span>|<span data-ttu-id="e6eed-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e6eed-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e6eed-111">**ContentTypeid**</span><span class="sxs-lookup"><span data-stu-id="e6eed-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="e6eed-112">int</span><span class="sxs-lookup"><span data-stu-id="e6eed-112">int</span></span>  <br/> |<span data-ttu-id="e6eed-113">Primária</span><span class="sxs-lookup"><span data-stu-id="e6eed-113">Primary</span></span>  <br/> |<span data-ttu-id="e6eed-114">Número exclusivo que identifica o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e6eed-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="e6eed-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="e6eed-115">**ContentType**</span></span> <br/> |<span data-ttu-id="e6eed-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e6eed-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="e6eed-117">Nome do tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="e6eed-117">Content type name.</span></span>  <br/> |
   

