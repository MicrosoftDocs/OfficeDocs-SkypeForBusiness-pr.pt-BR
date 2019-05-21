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
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: o tblConfig contém uma configuração sem suporte do servidor de chat persistente, em uma linha.
ms.openlocfilehash: 244eebcb88c67b521022f9d64888678f221d2369
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295451"
---
# <a name="tblconfig"></a><span data-ttu-id="2b4d7-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="2b4d7-103">tblConfig</span></span>
 
<span data-ttu-id="2b4d7-104">o tblConfig contém uma configuração sem suporte do servidor de chat persistente, em uma linha.</span><span class="sxs-lookup"><span data-stu-id="2b4d7-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="2b4d7-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="2b4d7-105">**Columns**</span></span>

|<span data-ttu-id="2b4d7-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2b4d7-106">**Column**</span></span>|<span data-ttu-id="2b4d7-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="2b4d7-107">**Type**</span></span>|<span data-ttu-id="2b4d7-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2b4d7-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="2b4d7-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="2b4d7-109">configLabel</span></span>  <br/> |<span data-ttu-id="2b4d7-110">nvarchar (255), NOT NULL</span><span class="sxs-lookup"><span data-stu-id="2b4d7-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="2b4d7-111">Contém "pool".</span><span class="sxs-lookup"><span data-stu-id="2b4d7-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="2b4d7-112">configContent</span><span class="sxs-lookup"><span data-stu-id="2b4d7-112">configContent</span></span>  <br/> |<span data-ttu-id="2b4d7-113">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="2b4d7-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="2b4d7-114">Conteúdo de configuração.</span><span class="sxs-lookup"><span data-stu-id="2b4d7-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="2b4d7-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="2b4d7-115">configPoolID</span></span>  <br/> |<span data-ttu-id="2b4d7-116">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="2b4d7-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="2b4d7-117">ID exclusiva da instância do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="2b4d7-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="2b4d7-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="2b4d7-118">**Key**</span></span>

|<span data-ttu-id="2b4d7-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2b4d7-119">**Column**</span></span>|<span data-ttu-id="2b4d7-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="2b4d7-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="2b4d7-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="2b4d7-121">configLabel</span></span>  <br/> |<span data-ttu-id="2b4d7-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="2b4d7-122">Primary key.</span></span>  <br/> |
   

