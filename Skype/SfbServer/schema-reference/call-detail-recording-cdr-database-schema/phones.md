---
title: Tabela Phones
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: A tabela de telefones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.
ms.openlocfilehash: 733adec46e948c3b7f1d804f57011110355078f4
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212884"
---
# <a name="phones-table"></a><span data-ttu-id="aaabf-104">Tabela Phones</span><span class="sxs-lookup"><span data-stu-id="aaabf-104">Phones table</span></span>
 
<span data-ttu-id="aaabf-105">A tabela de telefones é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="aaabf-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="aaabf-106">Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="aaabf-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="aaabf-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="aaabf-107">**Column**</span></span>|<span data-ttu-id="aaabf-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="aaabf-108">**Data Type**</span></span>|<span data-ttu-id="aaabf-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="aaabf-109">**Key/Index**</span></span>|<span data-ttu-id="aaabf-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="aaabf-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="aaabf-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="aaabf-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="aaabf-112">int</span><span class="sxs-lookup"><span data-stu-id="aaabf-112">int</span></span>  <br/> |<span data-ttu-id="aaabf-113">Primária</span><span class="sxs-lookup"><span data-stu-id="aaabf-113">Primary</span></span>  <br/> |<span data-ttu-id="aaabf-114">Número exclusivo que identifica esse telefone.</span><span class="sxs-lookup"><span data-stu-id="aaabf-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="aaabf-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="aaabf-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="aaabf-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="aaabf-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="aaabf-117">Número de telefone.</span><span class="sxs-lookup"><span data-stu-id="aaabf-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="aaabf-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="aaabf-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="aaabf-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="aaabf-119">dateTime</span></span>  <br/> ||<span data-ttu-id="aaabf-120">Carimbo de hora (somente para uso interno).</span><span class="sxs-lookup"><span data-stu-id="aaabf-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="aaabf-121">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="aaabf-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

