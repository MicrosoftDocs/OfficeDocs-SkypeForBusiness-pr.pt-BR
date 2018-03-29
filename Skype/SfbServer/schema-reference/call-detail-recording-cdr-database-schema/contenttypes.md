---
title: Tabela ContentTypes Skype para Business Server 2015
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
ms.openlocfilehash: 207e2a4e6ba605950181c437c236205fc8b2778f
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="36c46-104">Tabela ContentTypes Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="36c46-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="36c46-105">A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e de sessões de conferência.</span><span class="sxs-lookup"><span data-stu-id="36c46-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="36c46-106">Cada registro na tabela representa um tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="36c46-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="36c46-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="36c46-107">**Column**</span></span>|<span data-ttu-id="36c46-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="36c46-108">**Data Type**</span></span>|<span data-ttu-id="36c46-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="36c46-109">**Key/Index**</span></span>|<span data-ttu-id="36c46-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="36c46-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="36c46-111">**ContentTypeId**</span><span class="sxs-lookup"><span data-stu-id="36c46-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="36c46-112">int</span><span class="sxs-lookup"><span data-stu-id="36c46-112">int</span></span>  <br/> |<span data-ttu-id="36c46-113">Primária</span><span class="sxs-lookup"><span data-stu-id="36c46-113">Primary</span></span>  <br/> |<span data-ttu-id="36c46-114">Número exclusivo que identifica o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="36c46-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="36c46-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="36c46-115">**ContentType**</span></span> <br/> |<span data-ttu-id="36c46-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="36c46-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="36c46-117">Nome do tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="36c46-117">Content type name.</span></span>  <br/> |
   

