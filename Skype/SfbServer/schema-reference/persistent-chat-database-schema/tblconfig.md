---
title: tblConfig
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 7445e7db-c574-46fa-b964-8640d77047a8
description: tblConfig contém algumas configurações não compatíveis com o Servidor de Chat Persistente, em uma linha.
ms.openlocfilehash: 614e4e6514d695777c39a9d76482f775bd1a0981
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809731"
---
# <a name="tblconfig"></a><span data-ttu-id="af42c-103">tblConfig</span><span class="sxs-lookup"><span data-stu-id="af42c-103">tblConfig</span></span>
 
<span data-ttu-id="af42c-104">tblConfig contém algumas configurações não compatíveis com o Servidor de Chat Persistente, em uma linha.</span><span class="sxs-lookup"><span data-stu-id="af42c-104">tblConfig contains some Persistent Chat Server unsupported configuration, in one row.</span></span>
  
<span data-ttu-id="af42c-105">**Columns**</span><span class="sxs-lookup"><span data-stu-id="af42c-105">**Columns**</span></span>

|<span data-ttu-id="af42c-106">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="af42c-106">**Column**</span></span>|<span data-ttu-id="af42c-107">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="af42c-107">**Type**</span></span>|<span data-ttu-id="af42c-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="af42c-108">**Description**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="af42c-109">configLabel</span><span class="sxs-lookup"><span data-stu-id="af42c-109">configLabel</span></span>  <br/> |<span data-ttu-id="af42c-110">nvarchar (255), não nulo</span><span class="sxs-lookup"><span data-stu-id="af42c-110">nvarchar (255), not null</span></span>  <br/> |<span data-ttu-id="af42c-111">Contém "pool."</span><span class="sxs-lookup"><span data-stu-id="af42c-111">Contains "pool."</span></span>  <br/> |
|<span data-ttu-id="af42c-112">configContent</span><span class="sxs-lookup"><span data-stu-id="af42c-112">configContent</span></span>  <br/> |<span data-ttu-id="af42c-113">nvarchar (máx.)</span><span class="sxs-lookup"><span data-stu-id="af42c-113">nvarchar (max)</span></span>  <br/> |<span data-ttu-id="af42c-114">Conteúdo de configuração.</span><span class="sxs-lookup"><span data-stu-id="af42c-114">Configuration content.</span></span>  <br/> |
|<span data-ttu-id="af42c-115">configPoolID</span><span class="sxs-lookup"><span data-stu-id="af42c-115">configPoolID</span></span>  <br/> |<span data-ttu-id="af42c-116">GUID, não nulo</span><span class="sxs-lookup"><span data-stu-id="af42c-116">GUID, not null</span></span>  <br/> |<span data-ttu-id="af42c-117">ID exclusivo da instância de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="af42c-117">Unique ID of the database instance.</span></span>  <br/> |
   
<span data-ttu-id="af42c-118">**Chave**</span><span class="sxs-lookup"><span data-stu-id="af42c-118">**Key**</span></span>

|<span data-ttu-id="af42c-119">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="af42c-119">**Column**</span></span>|<span data-ttu-id="af42c-120">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="af42c-120">**Description**</span></span>|
|:-----|:-----|
|<span data-ttu-id="af42c-121">configLabel</span><span class="sxs-lookup"><span data-stu-id="af42c-121">configLabel</span></span>  <br/> |<span data-ttu-id="af42c-122">Chave primária.</span><span class="sxs-lookup"><span data-stu-id="af42c-122">Primary key.</span></span>  <br/> |
   

