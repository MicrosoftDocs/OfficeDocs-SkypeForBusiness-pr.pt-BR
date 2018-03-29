---
title: tblConfig
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
ms.openlocfilehash: 099060f0957ae21c14b285eac1b753ad0b8c1719
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="tblconfig"></a><span data-ttu-id="3c926-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="3c926-103">tblConfig</span></span>
 
<span data-ttu-id="3c926-104">tblConfig contém algumas configuração não suportada do servidor de Chat persistente, em uma linha.</span><span class="sxs-lookup"><span data-stu-id="3c926-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="3c926-105">**Colunas**</span><span class="sxs-lookup"><span data-stu-id="3c926-105">**Columns**</span></span>

|<span data-ttu-id="3c926-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3c926-106">**Column**</span></span>|<span data-ttu-id="3c926-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="3c926-107">**Type**</span></span>|<span data-ttu-id="3c926-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3c926-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="3c926-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="3c926-109">configLabel</span></span>  <br/> |<span data-ttu-id="3c926-110">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="3c926-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="3c926-111">Contém "pool".</span><span class="sxs-lookup"><span data-stu-id="3c926-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="3c926-112">configContent</span><span class="sxs-lookup"><span data-stu-id="3c926-112">configContent</span></span>  <br/> |<span data-ttu-id="3c926-113">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="3c926-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="3c926-114">Conteúdo da configuração.</span><span class="sxs-lookup"><span data-stu-id="3c926-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="3c926-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="3c926-115">configPoolID</span></span>  <br/> |<span data-ttu-id="3c926-116">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="3c926-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="3c926-117">ID exclusiva da instância do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3c926-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="3c926-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="3c926-118">**Key**</span></span>

|<span data-ttu-id="3c926-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3c926-119">**Column**</span></span>|<span data-ttu-id="3c926-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3c926-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="3c926-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="3c926-121">configLabel</span></span>  <br/> |<span data-ttu-id="3c926-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="3c926-122">Primary key.</span></span>  <br/> |
   

