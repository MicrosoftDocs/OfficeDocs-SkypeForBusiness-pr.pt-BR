---
title: Tabela UserAgent
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que tenham participado em sessões gravadas no banco de dados. Cada registro na tabela representa um agente do usuário
ms.openlocfilehash: 5b9bcc35fbad3d20a006410aeb3538b6f5daa77e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="useragent-table"></a><span data-ttu-id="05cfc-104">Tabela UserAgent</span><span class="sxs-lookup"><span data-stu-id="05cfc-104">UserAgent table</span></span>
 
<span data-ttu-id="05cfc-105">A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que tenham participado em sessões gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="05cfc-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="05cfc-106">Cada registro na tabela representa um agente do usuário</span><span class="sxs-lookup"><span data-stu-id="05cfc-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="05cfc-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="05cfc-107">**Column**</span></span>|<span data-ttu-id="05cfc-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="05cfc-108">**Data Type**</span></span>|<span data-ttu-id="05cfc-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="05cfc-109">**Key/Index**</span></span>|<span data-ttu-id="05cfc-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="05cfc-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="05cfc-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="05cfc-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="05cfc-112">int</span><span class="sxs-lookup"><span data-stu-id="05cfc-112">int</span></span>  <br/> |<span data-ttu-id="05cfc-113">Primária</span><span class="sxs-lookup"><span data-stu-id="05cfc-113">Primary</span></span>  <br/> |<span data-ttu-id="05cfc-114">Número exclusivo que identifica esse agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="05cfc-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="05cfc-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="05cfc-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="05cfc-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="05cfc-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="05cfc-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="05cfc-117">Unique</span></span>  <br/> |<span data-ttu-id="05cfc-118">Cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="05cfc-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="05cfc-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="05cfc-119">**UAType**</span></span> <br/> |<span data-ttu-id="05cfc-120">smallint</span><span class="sxs-lookup"><span data-stu-id="05cfc-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="05cfc-121">1 é o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="05cfc-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="05cfc-122">2 é A / V Conferencing Server.</span><span class="sxs-lookup"><span data-stu-id="05cfc-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="05cfc-123">4 é Skype para negócios.</span><span class="sxs-lookup"><span data-stu-id="05cfc-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="05cfc-124">8 é telefone IP.</span><span class="sxs-lookup"><span data-stu-id="05cfc-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="05cfc-125">16 é o Console do Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="05cfc-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="05cfc-126">32 é a Deployment Validation Tool (DVT).</span><span class="sxs-lookup"><span data-stu-id="05cfc-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="05cfc-127">64 é Skype para Business Server em computadores Macintosh.</span><span class="sxs-lookup"><span data-stu-id="05cfc-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="05cfc-128">128 é Skype para Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="05cfc-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="05cfc-129">256 é o serviço de anúncio de conferência.</span><span class="sxs-lookup"><span data-stu-id="05cfc-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="05cfc-130">512 é atendedor automático de conferência.</span><span class="sxs-lookup"><span data-stu-id="05cfc-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="05cfc-131">1024 é o aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="05cfc-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="05cfc-132">2048 é o controle de voz externo.</span><span class="sxs-lookup"><span data-stu-id="05cfc-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

