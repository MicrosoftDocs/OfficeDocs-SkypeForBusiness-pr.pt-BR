---
title: Exibição ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: A exibição ClientVersions armazena informações sobre os vários tipos de cliente e versões que participaram de sessões registradas no banco de dados. Cada registro na exibição representa uma versão do cliente. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: d37e2a1599eaf8906d11fdb8faf545aa3447f00f
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815409"
---
# <a name="clientversions-view"></a><span data-ttu-id="6e56b-105">Exibição ClientVersions</span><span class="sxs-lookup"><span data-stu-id="6e56b-105">ClientVersions view</span></span>
 
<span data-ttu-id="6e56b-106">A exibição ClientVersions armazena informações sobre os vários tipos de cliente e versões que participaram de sessões registradas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6e56b-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="6e56b-107">Cada registro na exibição representa uma versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="6e56b-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="6e56b-108">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6e56b-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e56b-109">Pode haver vários registros para determinadas colunas.</span><span class="sxs-lookup"><span data-stu-id="6e56b-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="6e56b-110">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6e56b-110">**Column**</span></span>|<span data-ttu-id="6e56b-111">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="6e56b-111">**Data Type**</span></span>|<span data-ttu-id="6e56b-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="6e56b-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6e56b-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="6e56b-113">**VersionId**</span></span> <br/> |<span data-ttu-id="6e56b-114">int</span><span class="sxs-lookup"><span data-stu-id="6e56b-114">int</span></span>  <br/> |<span data-ttu-id="6e56b-115">Número exclusivo que identifica esse tipo de cliente e a versão.</span><span class="sxs-lookup"><span data-stu-id="6e56b-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="6e56b-116">**Versão**</span><span class="sxs-lookup"><span data-stu-id="6e56b-116">**Version**</span></span> <br/> |<span data-ttu-id="6e56b-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6e56b-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6e56b-118">Representa o agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="6e56b-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="6e56b-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="6e56b-119">**ClientType**</span></span> <br/> |<span data-ttu-id="6e56b-120">int</span><span class="sxs-lookup"><span data-stu-id="6e56b-120">int</span></span>  <br/> |<span data-ttu-id="6e56b-121">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="6e56b-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="6e56b-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="6e56b-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="6e56b-123">nvarchar (64)</span><span class="sxs-lookup"><span data-stu-id="6e56b-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="6e56b-124">Categoria à qual o cliente pertence.</span><span class="sxs-lookup"><span data-stu-id="6e56b-124">Category that the client belongs to.</span></span> <span data-ttu-id="6e56b-125">Por exemplo, o cliente Conferencing_Attendant_1 0 pertence à CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="6e56b-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

