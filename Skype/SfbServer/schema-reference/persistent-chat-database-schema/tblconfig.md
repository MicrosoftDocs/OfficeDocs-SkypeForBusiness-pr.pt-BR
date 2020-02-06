---
title: tblConfig
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
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: o tblConfig contém uma configuração sem suporte do servidor de chat persistente, em uma linha.
ms.openlocfilehash: f79af00d6a9f97f0ce0836684a284779be662c1d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814619"
---
# <a name="tblconfig"></a><span data-ttu-id="41794-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="41794-103">tblConfig</span></span>
 
<span data-ttu-id="41794-104">o tblConfig contém uma configuração sem suporte do servidor de chat persistente, em uma linha.</span><span class="sxs-lookup"><span data-stu-id="41794-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="41794-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="41794-105">**Columns**</span></span>

|<span data-ttu-id="41794-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="41794-106">**Column**</span></span>|<span data-ttu-id="41794-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="41794-107">**Type**</span></span>|<span data-ttu-id="41794-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="41794-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="41794-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="41794-109">configLabel</span></span>  <br/> |<span data-ttu-id="41794-110">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="41794-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="41794-111">Contém "pool".</span><span class="sxs-lookup"><span data-stu-id="41794-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="41794-112">configContent</span><span class="sxs-lookup"><span data-stu-id="41794-112">configContent</span></span>  <br/> |<span data-ttu-id="41794-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="41794-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="41794-114">Conteúdo de configuração.</span><span class="sxs-lookup"><span data-stu-id="41794-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="41794-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="41794-115">configPoolID</span></span>  <br/> |<span data-ttu-id="41794-116">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="41794-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="41794-117">ID exclusiva da instância do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="41794-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="41794-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="41794-118">**Key**</span></span>

|<span data-ttu-id="41794-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="41794-119">**Column**</span></span>|<span data-ttu-id="41794-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="41794-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="41794-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="41794-121">configLabel</span></span>  <br/> |<span data-ttu-id="41794-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="41794-122">Primary key.</span></span>  <br/> |
   

