---
title: Tabela CodecDescription
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 3598acb8-7ea6-4748-8417-149c971c32a2
description: A tabela CodecDescription associa identificadores exclusivos de codec a seus codecs correspondentes. Os codecs são usados para codificar sinais digitais para transmissão e divulgação e, depois, para decodificar esses sinais para reprodução. Esta tabela foi introduzida no Microsoft Lync Server 2013
ms.openlocfilehash: 95ba2218ff20aa6c67de6f60d6966916b6648a58
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49831341"
---
# <a name="codecdescription-table"></a><span data-ttu-id="76a9f-105">Tabela CodecDescription</span><span class="sxs-lookup"><span data-stu-id="76a9f-105">CodecDescription table</span></span>
 
<span data-ttu-id="76a9f-106">A tabela CodecDescription associa identificadores exclusivos de codec a seus codecs correspondentes.</span><span class="sxs-lookup"><span data-stu-id="76a9f-106">The CodecDescription table maps unique codec identifiers to their corresponding codec.</span></span> <span data-ttu-id="76a9f-107">Os codecs são usados para codificar sinais digitais para transmissão e divulgação e, depois, para decodificar esses sinais para reprodução.</span><span class="sxs-lookup"><span data-stu-id="76a9f-107">Codecs are used to encode digital signals for transmission and broadcast, and then to decode those signals for playback.</span></span> <span data-ttu-id="76a9f-108">Esta tabela foi introduzida no Microsoft Lync Server 2013</span><span class="sxs-lookup"><span data-stu-id="76a9f-108">This table was introduced in Microsoft Lync Server 2013</span></span>
  
|<span data-ttu-id="76a9f-109">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="76a9f-109">**Column**</span></span>|<span data-ttu-id="76a9f-110">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="76a9f-110">**Data Type**</span></span>|<span data-ttu-id="76a9f-111">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="76a9f-111">**Key/Index**</span></span>|<span data-ttu-id="76a9f-112">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="76a9f-112">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="76a9f-113">**CodecDescriptionKey**</span><span class="sxs-lookup"><span data-stu-id="76a9f-113">**CodecDescriptionKey**</span></span> <br/> |<span data-ttu-id="76a9f-114">smallint</span><span class="sxs-lookup"><span data-stu-id="76a9f-114">smallint</span></span>  <br/> |<span data-ttu-id="76a9f-115">Primário</span><span class="sxs-lookup"><span data-stu-id="76a9f-115">Primary</span></span>  <br/> |<span data-ttu-id="76a9f-116">Identificador exclusivo atribuído ao codec.</span><span class="sxs-lookup"><span data-stu-id="76a9f-116">Unique identifier assigned to the codec.</span></span>  <br/> |
|<span data-ttu-id="76a9f-117">**CodecDescription**</span><span class="sxs-lookup"><span data-stu-id="76a9f-117">**CodecDescription**</span></span> <br/> |<span data-ttu-id="76a9f-118">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="76a9f-118">varchar(256)</span></span>  <br/> |<span data-ttu-id="76a9f-119">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="76a9f-119">Unique</span></span>  <br/> |<span data-ttu-id="76a9f-120">Descrição exclusiva do codec correspondendo à chave de descrição do codec.</span><span class="sxs-lookup"><span data-stu-id="76a9f-120">Unique description of the codec corresponding to the CodecDescriptionKey.</span></span>  <br/> |
   

