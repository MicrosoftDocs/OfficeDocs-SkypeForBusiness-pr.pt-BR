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
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30898934"
---
# <a name="tblconfig"></a><span data-ttu-id="1111d-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="1111d-103">tblConfig</span></span>
 
<span data-ttu-id="1111d-104">tblConfig contém algumas configuração não suportada do servidor de Chat persistente, em uma linha.</span><span class="sxs-lookup"><span data-stu-id="1111d-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="1111d-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="1111d-105">**Columns**</span></span>

|<span data-ttu-id="1111d-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="1111d-106">**Column**</span></span>|<span data-ttu-id="1111d-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="1111d-107">**Type**</span></span>|<span data-ttu-id="1111d-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1111d-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="1111d-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="1111d-109">configLabel</span></span>  <br/> |<span data-ttu-id="1111d-110">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="1111d-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="1111d-111">Contém "pool".</span><span class="sxs-lookup"><span data-stu-id="1111d-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="1111d-112">configContent</span><span class="sxs-lookup"><span data-stu-id="1111d-112">configContent</span></span>  <br/> |<span data-ttu-id="1111d-113">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="1111d-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="1111d-114">Conteúdo da configuração.</span><span class="sxs-lookup"><span data-stu-id="1111d-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="1111d-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="1111d-115">configPoolID</span></span>  <br/> |<span data-ttu-id="1111d-116">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="1111d-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="1111d-117">ID exclusiva da instância do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="1111d-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="1111d-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="1111d-118">**Key**</span></span>

|<span data-ttu-id="1111d-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="1111d-119">**Column**</span></span>|<span data-ttu-id="1111d-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="1111d-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="1111d-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="1111d-121">configLabel</span></span>  <br/> |<span data-ttu-id="1111d-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="1111d-122">Primary key.</span></span>  <br/> |
   

