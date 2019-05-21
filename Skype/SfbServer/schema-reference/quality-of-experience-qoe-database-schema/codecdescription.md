---
title: Tabela CodecDescription
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: A tabela CodecDescription mapeia identificadores de codec exclusivos para o codec correspondente. Codecs são usados para codificar sinais digitais para transmissão e transmissão e, em seguida, decodificar esses sinais para reprodução. Esta tabela foi introduzida no Microsoft Lync Server 2013
ms.openlocfilehash: 678b458757c54385b608d89efd6b2c621c6cd42f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295038"
---
# <a name="codecdescription-table"></a><span data-ttu-id="efa65-105">Tabela CodecDescription</span><span class="sxs-lookup"><span data-stu-id="efa65-105">CodecDescription table</span></span>
 
<span data-ttu-id="efa65-106">A tabela CodecDescription mapeia identificadores de codec exclusivos para o codec correspondente.</span><span class="sxs-lookup"><span data-stu-id="efa65-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="efa65-107">Codecs são usados para codificar sinais digitais para transmissão e transmissão e, em seguida, decodificar esses sinais para reprodução.</span><span class="sxs-lookup"><span data-stu-id="efa65-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="efa65-108">Esta tabela foi introduzida no Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="efa65-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="efa65-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="efa65-109">**Column**</span></span>|<span data-ttu-id="efa65-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="efa65-110">**Data Type**</span></span>|<span data-ttu-id="efa65-111">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="efa65-111">**Key/Index**</span></span>|<span data-ttu-id="efa65-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="efa65-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="efa65-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="efa65-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="efa65-114">smallint</span><span class="sxs-lookup"><span data-stu-id="efa65-114">smallint</span></span>  <br/> |<span data-ttu-id="efa65-115">Primária</span><span class="sxs-lookup"><span data-stu-id="efa65-115">Primary</span></span>  <br/> |<span data-ttu-id="efa65-116">Identificador exclusivo atribuído ao codec.</span><span class="sxs-lookup"><span data-stu-id="efa65-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="efa65-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="efa65-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="efa65-118">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="efa65-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="efa65-119">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="efa65-119">Unique</span></span>  <br/> |<span data-ttu-id="efa65-120">Descrição exclusiva do codec correspondente ao CodecDescriptionKey.</span><span class="sxs-lookup"><span data-stu-id="efa65-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

