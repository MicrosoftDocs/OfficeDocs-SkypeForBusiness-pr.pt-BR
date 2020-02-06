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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que participaram de sessões registradas no banco de dados. Cada registro na tabela representa um agente do usuário
ms.openlocfilehash: d0a287881a352801d237894c5b150b5a08d91fc8
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41805049"
---
# <a name="useragent-table"></a><span data-ttu-id="9c291-104">Tabela UserAgent</span><span class="sxs-lookup"><span data-stu-id="9c291-104">UserAgent table</span></span>
 
<span data-ttu-id="9c291-105">A tabela UserAgent é uma tabela de suporte que armazena uma lista de vários agentes de usuário que participaram de sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9c291-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="9c291-106">Cada registro na tabela representa um agente do usuário</span><span class="sxs-lookup"><span data-stu-id="9c291-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="9c291-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9c291-107">**Column**</span></span>|<span data-ttu-id="9c291-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9c291-108">**Data Type**</span></span>|<span data-ttu-id="9c291-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="9c291-109">**Key/Index**</span></span>|<span data-ttu-id="9c291-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="9c291-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9c291-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="9c291-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="9c291-112">int</span><span class="sxs-lookup"><span data-stu-id="9c291-112">int</span></span>  <br/> |<span data-ttu-id="9c291-113">Primária</span><span class="sxs-lookup"><span data-stu-id="9c291-113">Primary</span></span>  <br/> |<span data-ttu-id="9c291-114">Número exclusivo que identifica esse agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="9c291-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="9c291-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="9c291-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="9c291-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9c291-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="9c291-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="9c291-117">Unique</span></span>  <br/> |<span data-ttu-id="9c291-118">Cadeia de caracteres do agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="9c291-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="9c291-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="9c291-119">**UAType**</span></span> <br/> |<span data-ttu-id="9c291-120">smallint</span><span class="sxs-lookup"><span data-stu-id="9c291-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="9c291-121">1 é o servidor de mediação.</span><span class="sxs-lookup"><span data-stu-id="9c291-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="9c291-122">2 é um servidor de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="9c291-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="9c291-123">4 é o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="9c291-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="9c291-124">8 é o telefone IP.</span><span class="sxs-lookup"><span data-stu-id="9c291-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="9c291-125">16 é o console do Live Meeting.</span><span class="sxs-lookup"><span data-stu-id="9c291-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="9c291-126">o 32 é uma ferramenta de validação de implantação (DVT).</span><span class="sxs-lookup"><span data-stu-id="9c291-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="9c291-127">o 64 é o Skype for Business Server em computadores Macintosh.</span><span class="sxs-lookup"><span data-stu-id="9c291-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="9c291-128">o 128 é o Skype for Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="9c291-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="9c291-129">o 256 é o serviço de anúncio de conferências.</span><span class="sxs-lookup"><span data-stu-id="9c291-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="9c291-130">o 512 é o atendedor automático da conferência.</span><span class="sxs-lookup"><span data-stu-id="9c291-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="9c291-131">o 1024 é um aplicativo de grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="9c291-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="9c291-132">2048 está fora do controle de voz.</span><span class="sxs-lookup"><span data-stu-id="9c291-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

