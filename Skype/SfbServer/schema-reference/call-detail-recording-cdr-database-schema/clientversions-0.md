---
title: Exibição ClientVersions
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
ms.assetid: caf7678f-83a0-46c8-83cc-fee4c3991f52
description: A exibição ClientVersions armazena informações sobre os vários tipos de cliente e versões que participaram de sessões gravadas no banco de dados. Cada registro na exibição representa uma versão do cliente. Essa exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: b38e00c0a860b94b72c7d0dc396ff44357c2741f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813351"
---
# <a name="clientversions-view"></a><span data-ttu-id="53a87-105">Exibição ClientVersions</span><span class="sxs-lookup"><span data-stu-id="53a87-105">ClientVersions view</span></span>
 
<span data-ttu-id="53a87-106">A exibição ClientVersions armazena informações sobre os vários tipos de cliente e versões que participaram de sessões gravadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="53a87-106">The ClientVersions view stores information about the various client types and versions that have participated in sessions recorded in the database.</span></span> <span data-ttu-id="53a87-107">Cada registro na exibição representa uma versão do cliente.</span><span class="sxs-lookup"><span data-stu-id="53a87-107">Each record in the view represents one client version.</span></span> <span data-ttu-id="53a87-108">Essa exibição foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="53a87-108">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="53a87-109">Pode haver vários registros para determinadas colunas.</span><span class="sxs-lookup"><span data-stu-id="53a87-109">There may be multiple records for certain columns.</span></span> 
  
|<span data-ttu-id="53a87-110">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="53a87-110">**Column**</span></span>|<span data-ttu-id="53a87-111">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="53a87-111">**Data Type**</span></span>|<span data-ttu-id="53a87-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="53a87-112">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="53a87-113">**VersionId**</span><span class="sxs-lookup"><span data-stu-id="53a87-113">**VersionId**</span></span> <br/> |<span data-ttu-id="53a87-114">int</span><span class="sxs-lookup"><span data-stu-id="53a87-114">int</span></span>  <br/> |<span data-ttu-id="53a87-115">Número exclusivo que identifica esse tipo de cliente e a versão.</span><span class="sxs-lookup"><span data-stu-id="53a87-115">Unique number identifying this client type and version.</span></span>  <br/> |
|<span data-ttu-id="53a87-116">**Versão**</span><span class="sxs-lookup"><span data-stu-id="53a87-116">**Version**</span></span> <br/> |<span data-ttu-id="53a87-117">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="53a87-117">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="53a87-118">Representa o agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="53a87-118">Represents the user agent.</span></span>  <br/> |
|<span data-ttu-id="53a87-119">**ClientType**</span><span class="sxs-lookup"><span data-stu-id="53a87-119">**ClientType**</span></span> <br/> |<span data-ttu-id="53a87-120">int</span><span class="sxs-lookup"><span data-stu-id="53a87-120">int</span></span>  <br/> |<span data-ttu-id="53a87-121">Tipo de cliente.</span><span class="sxs-lookup"><span data-stu-id="53a87-121">Type of client.</span></span>  <br/> |
|<span data-ttu-id="53a87-122">**ClientCategory**</span><span class="sxs-lookup"><span data-stu-id="53a87-122">**ClientCategory**</span></span> <br/> |<span data-ttu-id="53a87-123">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="53a87-123">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="53a87-p103">Categoria na qual o cliente pertence. Por exemplo, o cliente Conferencing_Attendant_1.pertence ao CAA ClientCategory.</span><span class="sxs-lookup"><span data-stu-id="53a87-p103">Category that the client belongs to. For example, the client Conferencing_Attendant_1.0 belongs to the ClientCategory CAA.</span></span>  <br/> |
   

