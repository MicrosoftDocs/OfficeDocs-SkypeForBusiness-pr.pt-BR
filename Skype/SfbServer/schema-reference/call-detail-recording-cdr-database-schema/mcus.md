---
title: Tabela Mcus no Skype for Business Server 2015
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
ms.assetid: 271b7963-8fd8-4d92-a701-1a62aaf895ee
description: A tabela Mcus é uma tabela de suporte. Cada registro armazena informações sobre um serviço de conferência. Eles podem incluir o serviço de Conferência de IM e o serviço de Conferência de Telefonia (que é executado como processos em servidores front-end), o serviço de Webconferência e o serviço de Conferência A/V.
ms.openlocfilehash: fe43bfc747cd08febe00a68925ad520b6add5846
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821421"
---
# <a name="mcus-table-in-skype-for-business-server-2015"></a><span data-ttu-id="0780b-105">Tabela Mcus no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="0780b-105">Mcus table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="0780b-106">A tabela Mcus é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="0780b-106">The Mcus table is a supporting table.</span></span> <span data-ttu-id="0780b-107">Cada registro armazena informações sobre um serviço de conferência.</span><span class="sxs-lookup"><span data-stu-id="0780b-107">Each record stores information about one conferencing service.</span></span> <span data-ttu-id="0780b-108">Eles podem incluir o serviço de Conferência de IM e o serviço de Conferência de Telefonia (que é executado como processos em servidores front-end), o serviço de Webconferência e o serviço de Conferência A/V.</span><span class="sxs-lookup"><span data-stu-id="0780b-108">These can include the IM Conferencing service and the Telephony Conferencing service (which run as processes on front-end servers), and the Web Conferencing service and A/V Conferencing service.</span></span> 
  
|<span data-ttu-id="0780b-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="0780b-109">**Column**</span></span>|<span data-ttu-id="0780b-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="0780b-110">**Data Type**</span></span>|<span data-ttu-id="0780b-111">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="0780b-111">**Key/Index**</span></span>|<span data-ttu-id="0780b-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="0780b-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="0780b-113">**McuId**</span><span class="sxs-lookup"><span data-stu-id="0780b-113">**McuId**</span></span> <br/> |<span data-ttu-id="0780b-114">int</span><span class="sxs-lookup"><span data-stu-id="0780b-114">int</span></span>  <br/> |<span data-ttu-id="0780b-115">Primário</span><span class="sxs-lookup"><span data-stu-id="0780b-115">Primary</span></span>  <br/> |<span data-ttu-id="0780b-116">Número exclusivo que identifica este servidor de conferência.</span><span class="sxs-lookup"><span data-stu-id="0780b-116">Unique number identifying this conferencing server.</span></span>  <br/> |
|<span data-ttu-id="0780b-117">**McuUri**</span><span class="sxs-lookup"><span data-stu-id="0780b-117">**McuUri**</span></span> <br/> |<span data-ttu-id="0780b-118">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="0780b-118">nvarchar(450)</span></span>  <br/> | <br/> | <br/> |
|<span data-ttu-id="0780b-119">**McuTypeId**</span><span class="sxs-lookup"><span data-stu-id="0780b-119">**McuTypeId**</span></span> <br/> |<span data-ttu-id="0780b-120">inyint</span><span class="sxs-lookup"><span data-stu-id="0780b-120">inyint</span></span>  <br/> | <span data-ttu-id="0780b-121">Externo</span><span class="sxs-lookup"><span data-stu-id="0780b-121">Foreign</span></span> <br/> |<span data-ttu-id="0780b-122">Tipo de servidor de conferência, como conf:chat (para IMs) ou conf:audio-video.</span><span class="sxs-lookup"><span data-stu-id="0780b-122">Conferencing server type, such as conf:chat (for IMs) or conf:audio-video.</span></span> <span data-ttu-id="0780b-123">Consulte a [tabela UriTypes para](uritypes.md) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="0780b-123">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
   

