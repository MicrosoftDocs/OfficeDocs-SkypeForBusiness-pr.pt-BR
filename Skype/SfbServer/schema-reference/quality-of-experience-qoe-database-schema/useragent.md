---
title: Tabela UserAgent
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: d6bda1c0-b053-457a-9ffa-2ae859788775
description: A tabela UserAgent é uma tabela de suporte que armazena uma lista dos vários agentes do usuário que participaram de sessões gravadas no banco de dados. Cada registro na tabela representa um agente do usuário
ms.openlocfilehash: a1d0e647ff78d409555988a27592228fac2643be
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799926"
---
# <a name="useragent-table"></a><span data-ttu-id="e2506-104">Tabela UserAgent</span><span class="sxs-lookup"><span data-stu-id="e2506-104">UserAgent table</span></span>
 
<span data-ttu-id="e2506-105">A tabela UserAgent é uma tabela de suporte que armazena uma lista dos vários agentes do usuário que participaram de sessões gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e2506-105">The UserAgent table is a supporting table that stores a list of the various user agents that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="e2506-106">Cada registro na tabela representa um agente do usuário</span><span class="sxs-lookup"><span data-stu-id="e2506-106">Each record in the table represents one user agent</span></span>
  
|<span data-ttu-id="e2506-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e2506-107">**Column**</span></span>|<span data-ttu-id="e2506-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e2506-108">**Data Type**</span></span>|<span data-ttu-id="e2506-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="e2506-109">**Key/Index**</span></span>|<span data-ttu-id="e2506-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e2506-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e2506-111">**UserAgentKey**</span><span class="sxs-lookup"><span data-stu-id="e2506-111">**UserAgentKey**</span></span> <br/> |<span data-ttu-id="e2506-112">int</span><span class="sxs-lookup"><span data-stu-id="e2506-112">int</span></span>  <br/> |<span data-ttu-id="e2506-113">Primário</span><span class="sxs-lookup"><span data-stu-id="e2506-113">Primary</span></span>  <br/> |<span data-ttu-id="e2506-114">Número exclusivo que identifica esse agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="e2506-114">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="e2506-115">**UserAgent**</span><span class="sxs-lookup"><span data-stu-id="e2506-115">**UserAgent**</span></span> <br/> |<span data-ttu-id="e2506-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="e2506-116">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="e2506-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="e2506-117">Unique</span></span>  <br/> |<span data-ttu-id="e2506-118">Cadeia de caracteres do Agente do Usuário.</span><span class="sxs-lookup"><span data-stu-id="e2506-118">User Agent string.</span></span>  <br/> |
|<span data-ttu-id="e2506-119">**UAType**</span><span class="sxs-lookup"><span data-stu-id="e2506-119">**UAType**</span></span> <br/> |<span data-ttu-id="e2506-120">smallint</span><span class="sxs-lookup"><span data-stu-id="e2506-120">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="e2506-121">1 é o Servidor de Mediação.</span><span class="sxs-lookup"><span data-stu-id="e2506-121">1 is Mediation Server.</span></span>  <br/> <span data-ttu-id="e2506-122">2 é Servidor de Conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="e2506-122">2 is A/V Conferencing Server.</span></span>  <br/> <span data-ttu-id="e2506-123">4 é o Skype for Business.</span><span class="sxs-lookup"><span data-stu-id="e2506-123">4 is Skype for Business.</span></span>  <br/> <span data-ttu-id="e2506-124">8 é o Telefone IP.</span><span class="sxs-lookup"><span data-stu-id="e2506-124">8 is IP Phone.</span></span>  <br/> <span data-ttu-id="e2506-125">16 é o Live Meeting Console.</span><span class="sxs-lookup"><span data-stu-id="e2506-125">16 is Live Meeting Console.</span></span>  <br/> <span data-ttu-id="e2506-126">32 é a Ferramenta de Validação de Implantação (DVT).</span><span class="sxs-lookup"><span data-stu-id="e2506-126">32 is Deployment Validation Tool (DVT).</span></span>  <br/> <span data-ttu-id="e2506-127">64 é Skype for Business Server em computadores Macintosh.</span><span class="sxs-lookup"><span data-stu-id="e2506-127">64 is Skype for Business Server on Macintosh computers.</span></span>  <br/> <span data-ttu-id="e2506-128">128 é o Skype for Business Server Attendant.</span><span class="sxs-lookup"><span data-stu-id="e2506-128">128 is Skype for Business Server Attendant.</span></span>  <br/> <span data-ttu-id="e2506-129">256 é o serviço de Comunicado de Conferência.</span><span class="sxs-lookup"><span data-stu-id="e2506-129">256 is Conferencing Announcement service.</span></span>  <br/> <span data-ttu-id="e2506-130">512 é o Atendente Automático de Conferência.</span><span class="sxs-lookup"><span data-stu-id="e2506-130">512 is Conferencing Auto Attendant.</span></span>  <br/> <span data-ttu-id="e2506-131">1024 é o aplicativo grupo de resposta.</span><span class="sxs-lookup"><span data-stu-id="e2506-131">1024 is Response Group application.</span></span>  <br/> <span data-ttu-id="e2506-132">2048 é Outside Voice Control.</span><span class="sxs-lookup"><span data-stu-id="e2506-132">2048 is Outside Voice Control.</span></span>  <br/> |
   

