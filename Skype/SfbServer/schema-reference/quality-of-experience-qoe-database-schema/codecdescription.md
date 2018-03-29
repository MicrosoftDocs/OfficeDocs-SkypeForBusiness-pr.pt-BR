---
title: Tabela CodecDescription
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: A tabela CodecDescription mapeia identificadores exclusivos de codec ao codec correspondente. Codecs são usados para codificar sinais digitais para transmissão e difusão e depois para decodificar esses sinais para reprodução. Esta tabela foi introduzida no Microsoft Lync Server 2013
ms.openlocfilehash: 49dea2867ef7614fab3015efbd24e6ec47da8c55
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="codecdescription-table"></a><span data-ttu-id="f0a79-105">Tabela CodecDescription</span><span class="sxs-lookup"><span data-stu-id="f0a79-105">CodecDescription table</span></span>
 
<span data-ttu-id="f0a79-106">A tabela CodecDescription mapeia identificadores exclusivos de codec ao codec correspondente.</span><span class="sxs-lookup"><span data-stu-id="f0a79-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="f0a79-107">Codecs são usados para codificar sinais digitais para transmissão e difusão e depois para decodificar esses sinais para reprodução.</span><span class="sxs-lookup"><span data-stu-id="f0a79-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="f0a79-108">Esta tabela foi introduzida no Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="f0a79-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="f0a79-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f0a79-109">**Column**</span></span>|<span data-ttu-id="f0a79-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="f0a79-110">**Data Type**</span></span>|<span data-ttu-id="f0a79-111">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="f0a79-111">**Key/Index**</span></span>|<span data-ttu-id="f0a79-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="f0a79-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f0a79-113">**Chave**</span><span class="sxs-lookup"><span data-stu-id="f0a79-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="f0a79-114">smallint</span><span class="sxs-lookup"><span data-stu-id="f0a79-114">smallint</span></span>  <br/> |<span data-ttu-id="f0a79-115">Primária</span><span class="sxs-lookup"><span data-stu-id="f0a79-115">Primary</span></span>  <br/> |<span data-ttu-id="f0a79-116">Identificador exclusivo atribuído ao codec.</span><span class="sxs-lookup"><span data-stu-id="f0a79-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="f0a79-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="f0a79-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="f0a79-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="f0a79-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="f0a79-119">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="f0a79-119">Unique</span></span>  <br/> |<span data-ttu-id="f0a79-120">Descrição exclusiva do codec correspondendo à chave.</span><span class="sxs-lookup"><span data-stu-id="f0a79-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

