---
title: Tabela Roles
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e8eb8a10-26b5-488b-bc8c-f9ef93f98bdb
description: A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.
ms.openlocfilehash: 2b7759cc600471a8bf1b989ce429f6b2a4149ee0
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30891710"
---
# <a name="roles-table"></a><span data-ttu-id="11ef6-103">Tabela Roles</span><span class="sxs-lookup"><span data-stu-id="11ef6-103">Roles table</span></span>
 
<span data-ttu-id="11ef6-104">A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.</span><span class="sxs-lookup"><span data-stu-id="11ef6-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="11ef6-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="11ef6-105">**Column**</span></span>|<span data-ttu-id="11ef6-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="11ef6-106">**Data Type**</span></span>|<span data-ttu-id="11ef6-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="11ef6-107">**Key/Index**</span></span>|<span data-ttu-id="11ef6-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="11ef6-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="11ef6-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="11ef6-109">**RoleId**</span></span> <br/> |<span data-ttu-id="11ef6-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="11ef6-110">tinyint</span></span>  <br/> |<span data-ttu-id="11ef6-111">Primária</span><span class="sxs-lookup"><span data-stu-id="11ef6-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="11ef6-112">**Função**</span><span class="sxs-lookup"><span data-stu-id="11ef6-112">**Role**</span></span> <br/> |<span data-ttu-id="11ef6-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="11ef6-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="11ef6-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="11ef6-114">Allowed values:</span></span> <br/>  <span data-ttu-id="11ef6-115">0 - desconhecido</span><span class="sxs-lookup"><span data-stu-id="11ef6-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="11ef6-116">1 - apresentador</span><span class="sxs-lookup"><span data-stu-id="11ef6-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="11ef6-117">2 - participante</span><span class="sxs-lookup"><span data-stu-id="11ef6-117">2 - Attendee</span></span> <br/> |
   

