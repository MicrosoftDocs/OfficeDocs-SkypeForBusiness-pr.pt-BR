---
title: Exibição UserAgent
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
ms.assetid: b986f76f-f16e-4e5e-96cb-6e8f7f9b42ee
description: A Exibição UserAgent armazena informações sobre os agentes do usuário que foram envolvidos em sessões com registros no banco de dados. Esta exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 90db61df5bd947b101823172602103e47d4182a9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49800011"
---
# <a name="useragent-view"></a><span data-ttu-id="debd3-104">Exibição UserAgent</span><span class="sxs-lookup"><span data-stu-id="debd3-104">UserAgent view</span></span>
 
<span data-ttu-id="debd3-105">A Exibição UserAgent armazena informações sobre os agentes do usuário que foram envolvidos em sessões com registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="debd3-105">The UserAgent View stores information about the user agents that have been involved in sessions that have records in the database.</span></span> <span data-ttu-id="debd3-106">Esta exibição foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="debd3-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="debd3-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="debd3-107">**Column**</span></span>|<span data-ttu-id="debd3-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="debd3-108">**Data Type**</span></span>|<span data-ttu-id="debd3-109">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="debd3-109">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="debd3-110">UserAgentKey</span><span class="sxs-lookup"><span data-stu-id="debd3-110">UserAgentKey</span></span>  <br/> |<span data-ttu-id="debd3-111">int</span><span class="sxs-lookup"><span data-stu-id="debd3-111">int</span></span>  <br/> |<span data-ttu-id="debd3-112">Número exclusivo que identifica esse agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="debd3-112">Unique number identifying this user agent.</span></span>  <br/> |
|<span data-ttu-id="debd3-113">UserAgent</span><span class="sxs-lookup"><span data-stu-id="debd3-113">UserAgent</span></span>  <br/> |<span data-ttu-id="debd3-114">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="debd3-114">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="debd3-115">Cadeia de caracteres de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="debd3-115">User agent string.</span></span>  <br/> |
|<span data-ttu-id="debd3-116">UAType</span><span class="sxs-lookup"><span data-stu-id="debd3-116">UAType</span></span>  <br/> |<span data-ttu-id="debd3-117">smallint</span><span class="sxs-lookup"><span data-stu-id="debd3-117">smallint</span></span>  <br/> |<span data-ttu-id="debd3-118">Tipo de agente do usuário.</span><span class="sxs-lookup"><span data-stu-id="debd3-118">Type of user agent.</span></span> <span data-ttu-id="debd3-119">Consulte a [tabela UserAgent](useragent.md) para obter mais detalhes.</span><span class="sxs-lookup"><span data-stu-id="debd3-119">See the [UserAgent table](useragent.md) for more details.</span></span> <br/> |
|<span data-ttu-id="debd3-120">UACategory</span><span class="sxs-lookup"><span data-stu-id="debd3-120">UACategory</span></span>  <br/> |<span data-ttu-id="debd3-121">nvarchar(64)</span><span class="sxs-lookup"><span data-stu-id="debd3-121">nvarchar(64)</span></span>  <br/> |<span data-ttu-id="debd3-p104">Categoria que o agente do usuário pertence. Por exemplo, o agente do usuário Conferencing_Attendant_1.0 pertence à UACategory CAA.</span><span class="sxs-lookup"><span data-stu-id="debd3-p104">Category that the user agent belongs to. For example, the user agent Conferencing_Attendant_1.0 belongs to the UACategory CAA.</span></span>  <br/> |
   

