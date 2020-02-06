---
title: Tabela Phones
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: A tabela de telefones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.
ms.openlocfilehash: 3a78d2aba302041ce7db6e904e20f18fe71aa631
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814999"
---
# <a name="phones-table"></a><span data-ttu-id="cc830-104">Tabela Phones</span><span class="sxs-lookup"><span data-stu-id="cc830-104">Phones table</span></span>
 
<span data-ttu-id="cc830-105">A tabela de telefones é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="cc830-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="cc830-106">Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="cc830-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="cc830-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="cc830-107">**Column**</span></span>|<span data-ttu-id="cc830-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="cc830-108">**Data Type**</span></span>|<span data-ttu-id="cc830-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="cc830-109">**Key/Index**</span></span>|<span data-ttu-id="cc830-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="cc830-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="cc830-111">**PHONEID**</span><span class="sxs-lookup"><span data-stu-id="cc830-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="cc830-112">int</span><span class="sxs-lookup"><span data-stu-id="cc830-112">int</span></span>  <br/> |<span data-ttu-id="cc830-113">Primária</span><span class="sxs-lookup"><span data-stu-id="cc830-113">Primary</span></span>  <br/> |<span data-ttu-id="cc830-114">Número exclusivo que identifica este telefone.</span><span class="sxs-lookup"><span data-stu-id="cc830-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="cc830-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="cc830-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="cc830-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="cc830-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="cc830-117">Número de telefone.</span><span class="sxs-lookup"><span data-stu-id="cc830-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="cc830-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="cc830-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="cc830-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="cc830-119">dateTime</span></span>  <br/> ||<span data-ttu-id="cc830-120">Carimbo de data/hora (apenas para uso interno).</span><span class="sxs-lookup"><span data-stu-id="cc830-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="cc830-121">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="cc830-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

