---
title: Detalhes de exibição de QoE
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Os modos de exibição abrangem os cenários mais comuns para retornar dados do banco de dados do QoE SQL. Ele é recomendado para a criação de relatórios personalizados, em vez de acessar diretamente as tabelas de banco de dados; Isso porque os modos de exibição são mais prováveis de manter a compatibilidade retroativa com versões futuras.
ms.openlocfilehash: d207c2cff86c398fed62023b30d193e974cbca7a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41807169"
---
# <a name="qoe-view-details"></a><span data-ttu-id="55082-104">Detalhes de exibição de QoE</span><span class="sxs-lookup"><span data-stu-id="55082-104">QoE view details</span></span>
 
<span data-ttu-id="55082-105">Os modos de exibição abrangem os cenários mais comuns para retornar dados do banco de dados do QoE SQL.</span><span class="sxs-lookup"><span data-stu-id="55082-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="55082-106">Ele é recomendado para a criação de relatórios personalizados, em vez de acessar diretamente as tabelas de banco de dados; Isso porque os modos de exibição são mais prováveis de manter a compatibilidade retroativa com versões futuras.</span><span class="sxs-lookup"><span data-stu-id="55082-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="55082-107">**Nome do modo de exibição**</span><span class="sxs-lookup"><span data-stu-id="55082-107">**View Name**</span></span>|<span data-ttu-id="55082-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="55082-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="55082-109">Exibição AudioStreamDetail</span><span class="sxs-lookup"><span data-stu-id="55082-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="55082-110">Armazena informações sobre cada fluxo de áudio no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55082-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="55082-111">Modo de exibição de mídia</span><span class="sxs-lookup"><span data-stu-id="55082-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="55082-112">Armazena informações sobre cada linha de mídia no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55082-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="55082-113">Uma sessão de áudio geralmente contém uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="55082-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="55082-114">Uma sessão de áudio e vídeo (A/V) geralmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência for usado ou se o modo de exibição de galeria for usado.</span><span class="sxs-lookup"><span data-stu-id="55082-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="55082-115">Exibição NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="55082-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="55082-116">Armazena informações sobre a configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="55082-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="55082-117">Modo de exibição sessão</span><span class="sxs-lookup"><span data-stu-id="55082-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="55082-118">Armazena informações sobre sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55082-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="55082-119">Exibição do UserAgent</span><span class="sxs-lookup"><span data-stu-id="55082-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="55082-120">Armazena informações sobre os agentes de usuário envolvidos em sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55082-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="55082-121">Exibição VideoStreamDetail</span><span class="sxs-lookup"><span data-stu-id="55082-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="55082-122">Armazena informações sobre cada fluxo de vídeo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="55082-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

