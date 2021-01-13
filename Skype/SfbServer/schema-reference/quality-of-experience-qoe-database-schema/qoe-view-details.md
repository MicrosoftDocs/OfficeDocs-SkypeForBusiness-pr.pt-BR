---
title: Detalhes de exibição de QoE
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
ms.assetid: 6a658318-a317-4546-a44c-a9c473d8e86a
description: As exibições abrangem os cenários mais comuns para retornar dados do banco de dados SQL de QoE. São exibições recomendadas usadas para criar relatórios personalizados em vez de acessar diretamente as tabelas de banco de dados; isso porque as exibições têm mais probabilidade de manter a compatibilidade com versões futuras.
ms.openlocfilehash: cabe483da624d801b9b87d51ba61caed7a22f7d4
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49834471"
---
# <a name="qoe-view-details"></a><span data-ttu-id="afc36-104">Detalhes de exibição de QoE</span><span class="sxs-lookup"><span data-stu-id="afc36-104">QoE view details</span></span>
 
<span data-ttu-id="afc36-105">As exibições abrangem os cenários mais comuns para retornar dados do banco de dados SQL de QoE.</span><span class="sxs-lookup"><span data-stu-id="afc36-105">Views cover the most common scenarios for returning data from the QoE SQL database.</span></span> <span data-ttu-id="afc36-106">São exibições recomendadas usadas para criar relatórios personalizados em vez de acessar diretamente as tabelas de banco de dados; isso porque as exibições têm mais probabilidade de manter a compatibilidade com versões futuras.</span><span class="sxs-lookup"><span data-stu-id="afc36-106">It is recommended views used for building custom reports instead of directly accessing the database tables; that's because views are more likely to maintain backwards compatibility with future releases.</span></span>
  
|<span data-ttu-id="afc36-107">**Nome do Modo de Exibição**</span><span class="sxs-lookup"><span data-stu-id="afc36-107">**View Name**</span></span>|<span data-ttu-id="afc36-108">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="afc36-108">**Description**</span></span>|
|:-----|:-----|
|[<span data-ttu-id="afc36-109">Exibição AudioStreamDetail</span><span class="sxs-lookup"><span data-stu-id="afc36-109">AudioStreamDetail view</span></span>](audiostreamdetail.md) <br/> |<span data-ttu-id="afc36-110">Armazena informações sobre cada fluxo de áudio no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afc36-110">Stores information about each audio stream in the database.</span></span>  <br/> |
|[<span data-ttu-id="afc36-111">Exibição MediaLine</span><span class="sxs-lookup"><span data-stu-id="afc36-111">MediaLine view</span></span>](medialine.md) <br/> |<span data-ttu-id="afc36-112">Armazena informações sobre cada linha de mídia no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afc36-112">Stores information about each media line in the database.</span></span> <span data-ttu-id="afc36-113">Uma sessão de áudio normalmente contém uma linha de mídia de áudio.</span><span class="sxs-lookup"><span data-stu-id="afc36-113">One audio session typically contains one audio media line.</span></span> <span data-ttu-id="afc36-114">Uma sessão de áudio e vídeo (A/V) normalmente contém uma linha de mídia de áudio e uma linha de mídia de vídeo; no entanto, a sessão pode conter duas linhas de mídia de vídeo se um dispositivo de conferência ou o modo de exibição de galeria for usado.</span><span class="sxs-lookup"><span data-stu-id="afc36-114">One audio and video (A/V) session typically contains one audio media line and one video media line; however, the session might contain two video media lines if a conferencing device is used or if Gallery View is used.</span></span>  <br/> |
|[<span data-ttu-id="afc36-115">Exibição NetworkConfigurationSettings</span><span class="sxs-lookup"><span data-stu-id="afc36-115">NetworkConfigurationSettings view</span></span>](networkconfigurationsettings.md) <br/> |<span data-ttu-id="afc36-116">Armazena informações sobre a configuração de rede.</span><span class="sxs-lookup"><span data-stu-id="afc36-116">Stores information about the network configuration.</span></span>  <br/> |
|[<span data-ttu-id="afc36-117">Exibição de sessão</span><span class="sxs-lookup"><span data-stu-id="afc36-117">Session view</span></span>](session-0.md) <br/> |<span data-ttu-id="afc36-118">Armazena informações sobre sessões que tenham registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afc36-118">Stores information about sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="afc36-119">Exibição UserAgent</span><span class="sxs-lookup"><span data-stu-id="afc36-119">UserAgent view</span></span>](useragent-0.md) <br/> |<span data-ttu-id="afc36-120">Armazena informações sobre os agentes do usuário envolvidos em sessões com registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afc36-120">Stores information about the user agents that have been involved in sessions that have records in the database.</span></span>  <br/> |
|[<span data-ttu-id="afc36-121">Exibição VideoStreamDetail</span><span class="sxs-lookup"><span data-stu-id="afc36-121">VideoStreamDetail view</span></span>](videostreamdetail.md) <br/> |<span data-ttu-id="afc36-122">Armazena informações sobre cada fluxo de vídeo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="afc36-122">Stores information about each video stream in the database.</span></span>  <br/> |
   

