---
title: tblConfig
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contém algumas configuração não suportada do servidor de Chat persistente, em uma linha.
ms.openlocfilehash: 9d28c0506b905975e2a72eeb83605fe4e32e7cfd
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213064"
---
# <a name="tblconfig"></a><span data-ttu-id="222ee-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="222ee-103">tblConfig</span></span>
 
<span data-ttu-id="222ee-104">tblConfig contém algumas configuração não suportada do servidor de Chat persistente, em uma linha.</span><span class="sxs-lookup"><span data-stu-id="222ee-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="222ee-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="222ee-105">**Columns**</span></span>

|<span data-ttu-id="222ee-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="222ee-106">**Column**</span></span>|<span data-ttu-id="222ee-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="222ee-107">**Type**</span></span>|<span data-ttu-id="222ee-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="222ee-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="222ee-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="222ee-109">configLabel</span></span>  <br/> |<span data-ttu-id="222ee-110">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="222ee-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="222ee-111">Contém "pool".</span><span class="sxs-lookup"><span data-stu-id="222ee-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="222ee-112">configContent</span><span class="sxs-lookup"><span data-stu-id="222ee-112">configContent</span></span>  <br/> |<span data-ttu-id="222ee-113">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="222ee-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="222ee-114">Conteúdo da configuração.</span><span class="sxs-lookup"><span data-stu-id="222ee-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="222ee-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="222ee-115">configPoolID</span></span>  <br/> |<span data-ttu-id="222ee-116">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="222ee-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="222ee-117">ID exclusiva da instância do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="222ee-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="222ee-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="222ee-118">**Key**</span></span>

|<span data-ttu-id="222ee-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="222ee-119">**Column**</span></span>|<span data-ttu-id="222ee-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="222ee-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="222ee-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="222ee-121">configLabel</span></span>  <br/> |<span data-ttu-id="222ee-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="222ee-122">Primary key.</span></span>  <br/> |
   

