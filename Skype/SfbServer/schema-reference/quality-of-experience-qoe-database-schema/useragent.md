---
title: Tabela UserAgent
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que participaram de sessões registradas no banco de dados. Cada registro na tabela representa um agente do usuário
ms.openlocfilehash: f0c8a2f182611887db1324d17b6b7c28d6a9393d
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294583"
---
# <a name="useragent-table"></a><span data-ttu-id="83c2b-104">Tabela UserAgent</span><span class="sxs-lookup"><span data-stu-id="83c2b-104">UserAgent table</span></span>
 
<span data-ttu-id="83c2b-105">A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que participaram de sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="83c2b-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="83c2b-106">Cada registro na tabela representa um agente do usuário</span><span class="sxs-lookup"><span data-stu-id="83c2b-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="83c2b-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="83c2b-107">**Column**</span></span>|<span data-ttu-id="83c2b-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="83c2b-108">**Data Type**</span></span>|<span data-ttu-id="83c2b-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="83c2b-109">**Key/Index**</span></span>|<span data-ttu-id="83c2b-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="83c2b-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="83c2b-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="83c2b-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="83c2b-112">int</span><span class="sxs-lookup"><span data-stu-id="83c2b-112">int</span></span>  <br/> |<span data-ttu-id="83c2b-113">Primária</span><span class="sxs-lookup"><span data-stu-id="83c2b-113">Primary</span></span>  <br/> |<span data-ttu-id="83c2b-114">Número exclusivo que identifica esse agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="83c2b-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="83c2b-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="83c2b-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="83c2b-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="83c2b-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="83c2b-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="83c2b-117">Unique</span></span>  <br/> |<span data-ttu-id="83c2b-118">Cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="83c2b-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="83c2b-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="83c2b-119">**UAType**</span></span> <br/> |<span data-ttu-id="83c2b-120">smallint</span><span class="sxs-lookup"><span data-stu-id="83c2b-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="83c2b-121">1 é o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="83c2b-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="83c2b-122">2 é um servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="83c2b-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="83c2b-123">4 é o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="83c2b-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="83c2b-124">8 é o telefone IP.</span><span class="sxs-lookup"><span data-stu-id="83c2b-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="83c2b-125">16 é o console do Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="83c2b-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="83c2b-126">o 32 é uma ferramenta de validação de implantação (DVT).</span><span class="sxs-lookup"><span data-stu-id="83c2b-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="83c2b-127">o 64 é o Skype for Business Server em computadores Macintosh.</span><span class="sxs-lookup"><span data-stu-id="83c2b-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="83c2b-128">o 128 é o Skype for Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="83c2b-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="83c2b-129">o 256 é o serviço de anúncio de conferências.</span><span class="sxs-lookup"><span data-stu-id="83c2b-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="83c2b-130">o 512 é o atendedor automático da conferência.</span><span class="sxs-lookup"><span data-stu-id="83c2b-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="83c2b-131">o 1024 é um aplicativo de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="83c2b-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="83c2b-132">2048 está fora do controle de voz.</span><span class="sxs-lookup"><span data-stu-id="83c2b-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

