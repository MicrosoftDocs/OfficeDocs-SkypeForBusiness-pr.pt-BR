---
title: tblConfig
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contém algumas configuração não suportada do servidor de Chat persistente, em uma linha.
ms.openlocfilehash: 79cd7e2303210bb07f35fa2c6b7ecc5c86b7e8cc
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930019"
---
# <a name="tblconfig"></a><span data-ttu-id="19de1-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="19de1-103">tblConfig</span></span>
 
<span data-ttu-id="19de1-104">tblConfig contém algumas configuração não suportada do servidor de Chat persistente, em uma linha.</span><span class="sxs-lookup"><span data-stu-id="19de1-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="19de1-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="19de1-105">**Columns**</span></span>

|<span data-ttu-id="19de1-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="19de1-106">**Column**</span></span>|<span data-ttu-id="19de1-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="19de1-107">**Type**</span></span>|<span data-ttu-id="19de1-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="19de1-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="19de1-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="19de1-109">configLabel</span></span>  <br/> |<span data-ttu-id="19de1-110">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="19de1-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="19de1-111">Contém "pool".</span><span class="sxs-lookup"><span data-stu-id="19de1-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="19de1-112">configContent</span><span class="sxs-lookup"><span data-stu-id="19de1-112">configContent</span></span>  <br/> |<span data-ttu-id="19de1-113">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="19de1-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="19de1-114">Conteúdo da configuração.</span><span class="sxs-lookup"><span data-stu-id="19de1-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="19de1-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="19de1-115">configPoolID</span></span>  <br/> |<span data-ttu-id="19de1-116">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="19de1-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="19de1-117">ID exclusiva da instância do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="19de1-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="19de1-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="19de1-118">**Key**</span></span>

|<span data-ttu-id="19de1-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="19de1-119">**Column**</span></span>|<span data-ttu-id="19de1-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="19de1-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="19de1-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="19de1-121">configLabel</span></span>  <br/> |<span data-ttu-id="19de1-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="19de1-122">Primary key.</span></span>  <br/> |
   

