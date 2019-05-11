---
title: Exibir ClientVersions
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: O modo de exibição ClientVersions armazena informações sobre os diversos tipos de cliente e versões que tenham participado em sessões gravadas no banco de dados. Cada registro no modo de exibição representa uma versão de cliente. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: cc4024a7e2644a177eb6962c8fdc7078fd6b397d
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901519"
---
# <a name="clientversions-view"></a><span data-ttu-id="ed66a-105">Exibir ClientVersions</span><span class="sxs-lookup"><span data-stu-id="ed66a-105">ClientVersions view</span></span>
 
<span data-ttu-id="ed66a-106">O modo de exibição ClientVersions armazena informações sobre os diversos tipos de cliente e versões que tenham participado em sessões gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ed66a-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="ed66a-107">Cada registro no modo de exibição representa uma versão de cliente.</span><span class="sxs-lookup"><span data-stu-id="ed66a-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="ed66a-108">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="ed66a-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="ed66a-109">Podem haver vários registros para determinadas colunas.</span><span class="sxs-lookup"><span data-stu-id="ed66a-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="ed66a-110">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="ed66a-110">**Column**</span></span>|<span data-ttu-id="ed66a-111">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="ed66a-111">**Data Type**</span></span>|<span data-ttu-id="ed66a-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="ed66a-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="ed66a-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="ed66a-113">**VersionId**</span></span> <br/> |<span data-ttu-id="ed66a-114">int</span><span class="sxs-lookup"><span data-stu-id="ed66a-114">int</span></span>  <br/> |<span data-ttu-id="ed66a-115">Número exclusivo identificando este tipo de cliente e versão.</span><span class="sxs-lookup"><span data-stu-id="ed66a-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="ed66a-116">**Versão**</span><span class="sxs-lookup"><span data-stu-id="ed66a-116">**Version**</span></span> <br/> |<span data-ttu-id="ed66a-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="ed66a-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="ed66a-118">Representa o agente de usuário.</span><span class="sxs-lookup"><span data-stu-id="ed66a-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="ed66a-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="ed66a-119">**ClientType**</span></span> <br/> |<span data-ttu-id="ed66a-120">int</span><span class="sxs-lookup"><span data-stu-id="ed66a-120">int</span></span>  <br/> |<span data-ttu-id="ed66a-121">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="ed66a-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="ed66a-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="ed66a-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="ed66a-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="ed66a-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="ed66a-124">Categoria à qual o cliente pertencer a.</span><span class="sxs-lookup"><span data-stu-id="ed66a-124">Category that the client belongs to.</span></span> <span data-ttu-id="ed66a-125">Por exemplo, o cliente Conferencing_Attendant_1.0 pertence o CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="ed66a-125">For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

