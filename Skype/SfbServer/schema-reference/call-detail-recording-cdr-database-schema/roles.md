---
title: Tabela Roles
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.
ms.openlocfilehash: e0088d059d6e4ed536e5f52e1290211377438889
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930301"
---
# <a name="roles-table"></a><span data-ttu-id="97c48-103">Tabela Roles</span><span class="sxs-lookup"><span data-stu-id="97c48-103">Roles table</span></span>
 
<span data-ttu-id="97c48-104">A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.</span><span class="sxs-lookup"><span data-stu-id="97c48-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="97c48-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="97c48-105">**Column**</span></span>|<span data-ttu-id="97c48-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="97c48-106">**Data Type**</span></span>|<span data-ttu-id="97c48-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="97c48-107">**Key/Index**</span></span>|<span data-ttu-id="97c48-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="97c48-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="97c48-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="97c48-109">**RoleId**</span></span> <br/> |<span data-ttu-id="97c48-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="97c48-110">tinyint</span></span>  <br/> |<span data-ttu-id="97c48-111">Primária</span><span class="sxs-lookup"><span data-stu-id="97c48-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="97c48-112">**Função**</span><span class="sxs-lookup"><span data-stu-id="97c48-112">**Role**</span></span> <br/> |<span data-ttu-id="97c48-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="97c48-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="97c48-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="97c48-114">Allowed values:</span></span> <br/>  <span data-ttu-id="97c48-115">0 - desconhecido</span><span class="sxs-lookup"><span data-stu-id="97c48-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="97c48-116">1 - apresentador</span><span class="sxs-lookup"><span data-stu-id="97c48-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="97c48-117">2 - participante</span><span class="sxs-lookup"><span data-stu-id="97c48-117">2 - Attendee</span></span> <br/> |
   

