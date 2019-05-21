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
localization_priority: Normal
ms.assetid: e3e38035-457c-4173-bdb9-d53a7420eba2
description: A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e em sessões de conferência. Cada registro na tabela representa um tipo de conteúdo.
ms.openlocfilehash: b8422cbe95425ac79495c0506f4a94e70be3f9af
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296368"
---
# <a name="contenttypes-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2863c-104">Tabela ContentTypes no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2863c-104">ContentTypes table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2863c-105">A tabela ContentTypes é uma tabela de suporte que armazena uma lista dos tipos de conteúdo usados em sessões ponto a ponto e em sessões de conferência.</span><span class="sxs-lookup"><span data-stu-id="2863c-105">The ContentTypes table is a supporting table that stores a list of the content types used in both peer-to-peer sessions and conference sessions.</span></span> <span data-ttu-id="2863c-106">Cada registro na tabela representa um tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="2863c-106">Each record in the table represents one content type.</span></span>
  
|<span data-ttu-id="2863c-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2863c-107">**Column**</span></span>|<span data-ttu-id="2863c-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="2863c-108">**Data Type**</span></span>|<span data-ttu-id="2863c-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="2863c-109">**Key/Index**</span></span>|<span data-ttu-id="2863c-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2863c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2863c-111">**ContentTypeid**</span><span class="sxs-lookup"><span data-stu-id="2863c-111">**ContentTypeId**</span></span> <br/> |<span data-ttu-id="2863c-112">int</span><span class="sxs-lookup"><span data-stu-id="2863c-112">int</span></span>  <br/> |<span data-ttu-id="2863c-113">Primária</span><span class="sxs-lookup"><span data-stu-id="2863c-113">Primary</span></span>  <br/> |<span data-ttu-id="2863c-114">Número exclusivo que identifica o tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="2863c-114">Unique number identifying the content type.</span></span>  <br/> |
|<span data-ttu-id="2863c-115">**ContentType**</span><span class="sxs-lookup"><span data-stu-id="2863c-115">**ContentType**</span></span> <br/> |<span data-ttu-id="2863c-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="2863c-116">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="2863c-117">Nome do tipo de conteúdo.</span><span class="sxs-lookup"><span data-stu-id="2863c-117">Content type name.</span></span>  <br/> |
   

