---
title: Tabela Phones
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: A tabela de telefones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.
ms.openlocfilehash: ba13a059e043cf2a18c41c28dce1a2a54e694b9b
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930613"
---
# <a name="phones-table"></a><span data-ttu-id="8e891-104">Tabela Phones</span><span class="sxs-lookup"><span data-stu-id="8e891-104">Phones table</span></span>
 
<span data-ttu-id="8e891-105">A tabela de telefones é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="8e891-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="8e891-106">Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="8e891-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="8e891-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8e891-107">**Column**</span></span>|<span data-ttu-id="8e891-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="8e891-108">**Data Type**</span></span>|<span data-ttu-id="8e891-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="8e891-109">**Key/Index**</span></span>|<span data-ttu-id="8e891-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="8e891-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8e891-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="8e891-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="8e891-112">int</span><span class="sxs-lookup"><span data-stu-id="8e891-112">int</span></span>  <br/> |<span data-ttu-id="8e891-113">Primária</span><span class="sxs-lookup"><span data-stu-id="8e891-113">Primary</span></span>  <br/> |<span data-ttu-id="8e891-114">Número exclusivo que identifica esse telefone.</span><span class="sxs-lookup"><span data-stu-id="8e891-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="8e891-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="8e891-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="8e891-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="8e891-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="8e891-117">Número de telefone.</span><span class="sxs-lookup"><span data-stu-id="8e891-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="8e891-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="8e891-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="8e891-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="8e891-119">dateTime</span></span>  <br/> ||<span data-ttu-id="8e891-120">Carimbo de hora (somente para uso interno).</span><span class="sxs-lookup"><span data-stu-id="8e891-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="8e891-121">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8e891-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

