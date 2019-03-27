---
title: Exibir ClientVersions
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: O modo de exibição ClientVersions armazena informações sobre os diversos tipos de cliente e versões que tenham participado em sessões gravadas no banco de dados. Cada registro no modo de exibição representa uma versão de cliente. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: abf1436a2c3309e95bec8371b586c017e11b816d
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30881692"
---
# <a name="clientversions-view"></a><span data-ttu-id="443c0-105">Exibir ClientVersions</span><span class="sxs-lookup"><span data-stu-id="443c0-105">ClientVersions view</span></span>
 
<span data-ttu-id="443c0-106">O modo de exibição ClientVersions armazena informações sobre os diversos tipos de cliente e versões que tenham participado em sessões gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="443c0-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="443c0-107">Cada registro no modo de exibição representa uma versão de cliente.</span><span class="sxs-lookup"><span data-stu-id="443c0-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="443c0-108">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="443c0-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="443c0-109">Podem haver vários registros para determinadas colunas.</span><span class="sxs-lookup"><span data-stu-id="443c0-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="443c0-110">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="443c0-110">**Column**</span></span>|<span data-ttu-id="443c0-111">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="443c0-111">**Data Type**</span></span>|<span data-ttu-id="443c0-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="443c0-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="443c0-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="443c0-113">**VersionId**</span></span> <br/> |<span data-ttu-id="443c0-114">int</span><span class="sxs-lookup"><span data-stu-id="443c0-114">int</span></span>  <br/> |<span data-ttu-id="443c0-115">Número exclusivo identificando este tipo de cliente e versão.</span><span class="sxs-lookup"><span data-stu-id="443c0-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="443c0-116">**Versão**</span><span class="sxs-lookup"><span data-stu-id="443c0-116">**Version**</span></span> <br/> |<span data-ttu-id="443c0-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="443c0-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="443c0-118">Representa o agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="443c0-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="443c0-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="443c0-119">**ClientType**</span></span> <br/> |<span data-ttu-id="443c0-120">int</span><span class="sxs-lookup"><span data-stu-id="443c0-120">int</span></span>  <br/> |<span data-ttu-id="443c0-121">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="443c0-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="443c0-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="443c0-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="443c0-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="443c0-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="443c0-124">Categoria à qual o cliente pertencer a.</span><span class="sxs-lookup"><span data-stu-id="443c0-124">Category that the client belongs to.</span></span> <span data-ttu-id="443c0-125">Por exemplo, o cliente Conferencing_Attendant_1.0 pertence o CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="443c0-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

