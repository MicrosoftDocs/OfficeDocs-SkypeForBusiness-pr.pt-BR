---
title: Tabela MCUs no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: A tabela MCUs é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de conferência de mensagem instantânea e o serviço de conferência de telefonia (que são executados como processos em servidores front-end) e o serviço de conferência via Web e o serviço de conferência A/V.
ms.openlocfilehash: fcd12bcc8da7aa6513d78e1a9c4a6f11930065aa
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296039"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="e42fe-105">Tabela MCUs no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="e42fe-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="e42fe-106">A tabela MCUs é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="e42fe-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="e42fe-107">Cada registro armazena informações sobre um serviço de conferência.</span><span class="sxs-lookup"><span data-stu-id="e42fe-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="e42fe-108">Eles podem incluir o serviço de conferência de mensagem instantânea e o serviço de conferência de telefonia (que são executados como processos em servidores front-end) e o serviço de conferência via Web e o serviço de conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="e42fe-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="e42fe-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e42fe-109">**Column**</span></span>|<span data-ttu-id="e42fe-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e42fe-110">**Data Type**</span></span>|<span data-ttu-id="e42fe-111">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="e42fe-111">**Key/Index**</span></span>|<span data-ttu-id="e42fe-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e42fe-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e42fe-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="e42fe-113">**McuId**</span></span> <br/> |<span data-ttu-id="e42fe-114">int</span><span class="sxs-lookup"><span data-stu-id="e42fe-114">int</span></span>  <br/> |<span data-ttu-id="e42fe-115">Primária</span><span class="sxs-lookup"><span data-stu-id="e42fe-115">Primary</span></span>  <br/> |<span data-ttu-id="e42fe-116">Número exclusivo que identifica esse servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="e42fe-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="e42fe-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="e42fe-117">**McuUri**</span></span> <br/> |<span data-ttu-id="e42fe-118">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="e42fe-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="e42fe-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="e42fe-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="e42fe-120">inyint</span><span class="sxs-lookup"><span data-stu-id="e42fe-120">inyint</span></span>  <br/> | <span data-ttu-id="e42fe-121">Exterior</span><span class="sxs-lookup"><span data-stu-id="e42fe-121">Foreign</span></span> <br/> |<span data-ttu-id="e42fe-122">Tipo de servidor de conferência, como conf: Chat (para IMs) ou conf: Audio-Video.</span><span class="sxs-lookup"><span data-stu-id="e42fe-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="e42fe-123">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="e42fe-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

