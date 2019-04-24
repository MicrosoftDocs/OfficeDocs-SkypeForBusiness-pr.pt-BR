---
title: Tabela MCUs Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: A tabela Mcus é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de conferência de mensagens Instantâneas e o serviço de conferência com telefonia (que são executados como processos em servidores front-end) e o serviço de webconferência e uma / serviço V Conferencing.
ms.openlocfilehash: e051af3a77d4f9b8231c122c596a3b6915f6f3e1
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212970"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="65873-105">Tabela MCUs Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="65873-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="65873-106">A tabela Mcus é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="65873-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="65873-107">Cada registro armazena informações sobre um serviço de conferência.</span><span class="sxs-lookup"><span data-stu-id="65873-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="65873-108">Eles podem incluir o serviço de conferência de mensagens Instantâneas e o serviço de conferência com telefonia (que são executados como processos em servidores front-end) e o serviço de webconferência e uma / serviço V Conferencing.</span><span class="sxs-lookup"><span data-stu-id="65873-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="65873-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="65873-109">**Column**</span></span>|<span data-ttu-id="65873-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="65873-110">**Data Type**</span></span>|<span data-ttu-id="65873-111">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="65873-111">**Key/Index**</span></span>|<span data-ttu-id="65873-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="65873-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65873-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="65873-113">**McuId**</span></span> <br/> |<span data-ttu-id="65873-114">int</span><span class="sxs-lookup"><span data-stu-id="65873-114">int</span></span>  <br/> |<span data-ttu-id="65873-115">Primária</span><span class="sxs-lookup"><span data-stu-id="65873-115">Primary</span></span>  <br/> |<span data-ttu-id="65873-116">Número exclusivo que identifica este servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="65873-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="65873-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="65873-117">**McuUri**</span></span> <br/> |<span data-ttu-id="65873-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="65873-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="65873-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="65873-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="65873-120">inyint</span><span class="sxs-lookup"><span data-stu-id="65873-120">inyint</span></span>  <br/> | <span data-ttu-id="65873-121">Externa</span><span class="sxs-lookup"><span data-stu-id="65873-121">Foreign</span></span> <br/> |<span data-ttu-id="65873-122">Tipo de servidor de conferência, como conf:chat (para mensagens instantâneas) ou conf:audio-vídeo.</span><span class="sxs-lookup"><span data-stu-id="65873-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="65873-123">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="65873-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

