---
title: Detalhes de exibição de QoE
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: Modos de exibição abordam os cenários mais comuns para retornar dados do banco de dados SQL de QoE. É recomendável exibições usadas para a criação de relatórios personalizados em vez de acessar diretamente as tabelas de banco de dados; Isso ocorre porque os modos de exibição estão mais prováveis manter a compatibilidade com versões futuras com versões anteriores.
ms.openlocfilehash: f384f75ecc0c8a0dfdb2cdaedacdcef81bdba9b4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212141"
---
# <a name="qoe-view-details"></a><span data-ttu-id="6ab74-104">Detalhes de exibição de QoE</span><span class="sxs-lookup"><span data-stu-id="6ab74-104">QoE view details</span></span>
 
<span data-ttu-id="6ab74-105">Modos de exibição abordam os cenários mais comuns para retornar dados do banco de dados SQL de QoE.</span><span class="sxs-lookup"><span data-stu-id="6ab74-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="6ab74-106">É recomendável exibições usadas para a criação de relatórios personalizados em vez de acessar diretamente as tabelas de banco de dados; Isso ocorre porque os modos de exibição estão mais prováveis manter a compatibilidade com versões futuras com versões anteriores.</span><span class="sxs-lookup"><span data-stu-id="6ab74-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="6ab74-107">**Nome da exibição**</span><span class="sxs-lookup"><span data-stu-id="6ab74-107">**View Name**</span></span>|<span data-ttu-id="6ab74-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="6ab74-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="6ab74-109">Exibir audiostreamdetail</span><span class="sxs-lookup"><span data-stu-id="6ab74-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="6ab74-110">Armazena informações sobre cada transmissão de áudio no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6ab74-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="6ab74-111">Exibir MediaLine</span><span class="sxs-lookup"><span data-stu-id="6ab74-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="6ab74-112">Armazena informações sobre cada linha de mídia no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6ab74-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="6ab74-113">Normalmente, uma sessão de áudio conterá uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="6ab74-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="6ab74-114">Um áudio e vídeo (A / V) sessão normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; No entanto, a sessão pode conter duas linhas de mídia de vídeo, se um dispositivo de conferência for usado, ou se o modo de exibição de galeria é usado.</span><span class="sxs-lookup"><span data-stu-id="6ab74-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="6ab74-115">Exibir NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="6ab74-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="6ab74-116">Armazena informações sobre a configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="6ab74-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="6ab74-117">Modo de exibição de sessão</span><span class="sxs-lookup"><span data-stu-id="6ab74-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="6ab74-118">Armazena informações sobre sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6ab74-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="6ab74-119">Exibir UserAgent</span><span class="sxs-lookup"><span data-stu-id="6ab74-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="6ab74-120">Armazena informações sobre os agentes de usuário que participaram de sessões que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6ab74-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="6ab74-121">Exibir videostreamdetail</span><span class="sxs-lookup"><span data-stu-id="6ab74-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="6ab74-122">Armazena informações sobre cada transmissão de vídeo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="6ab74-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

