---
title: Tabela Roles
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
ms.openlocfilehash: a9f35c510eaca054dd504db4045686cb4eeaac4c
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="roles-table"></a><span data-ttu-id="91695-103">Tabela Roles</span><span class="sxs-lookup"><span data-stu-id="91695-103">Roles table</span></span>
 
<span data-ttu-id="91695-104">A tabela Roles é uma tabela estática que armazena a lista de possíveis funções de conferência, como participante e apresentador.</span><span class="sxs-lookup"><span data-stu-id="91695-104">The Roles table is a static table that stores the list of possible conference roles, such as attendee and presenter.</span></span>
  
|<span data-ttu-id="91695-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="91695-105">**Column**</span></span>|<span data-ttu-id="91695-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="91695-106">**Data Type**</span></span>|<span data-ttu-id="91695-107">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="91695-107">**Key/Index**</span></span>|<span data-ttu-id="91695-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="91695-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="91695-109">**RoleId**</span><span class="sxs-lookup"><span data-stu-id="91695-109">**RoleId**</span></span> <br/> |<span data-ttu-id="91695-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="91695-110">tinyint</span></span>  <br/> |<span data-ttu-id="91695-111">Primária</span><span class="sxs-lookup"><span data-stu-id="91695-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="91695-112">**Função**</span><span class="sxs-lookup"><span data-stu-id="91695-112">**Role**</span></span> <br/> |<span data-ttu-id="91695-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="91695-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="91695-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="91695-114">Allowed values:</span></span> <br/>  <span data-ttu-id="91695-115">0 - desconhecido</span><span class="sxs-lookup"><span data-stu-id="91695-115">0 - Unknown</span></span> <br/>  <span data-ttu-id="91695-116">1 - apresentador</span><span class="sxs-lookup"><span data-stu-id="91695-116">1 - Presenter</span></span> <br/>  <span data-ttu-id="91695-117">2 - participante</span><span class="sxs-lookup"><span data-stu-id="91695-117">2 - Attendee</span></span> <br/> |
   

