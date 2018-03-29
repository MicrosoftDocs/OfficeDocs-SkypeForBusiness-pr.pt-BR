---
title: Tabela Phones
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
ms.openlocfilehash: 8ec2095b857ba474a92bf0766d86119500919f51
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="phones-table"></a><span data-ttu-id="e8968-104">Tabela Phones</span><span class="sxs-lookup"><span data-stu-id="e8968-104">Phones table</span></span>
 
<span data-ttu-id="e8968-105">A tabela de telefones é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="e8968-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="e8968-106">Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e8968-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="e8968-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="e8968-107">**Column**</span></span>|<span data-ttu-id="e8968-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="e8968-108">**Data Type**</span></span>|<span data-ttu-id="e8968-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="e8968-109">**Key/Index**</span></span>|<span data-ttu-id="e8968-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="e8968-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="e8968-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="e8968-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="e8968-112">int</span><span class="sxs-lookup"><span data-stu-id="e8968-112">int</span></span>  <br/> |<span data-ttu-id="e8968-113">Primária</span><span class="sxs-lookup"><span data-stu-id="e8968-113">Primary</span></span>  <br/> |<span data-ttu-id="e8968-114">Número exclusivo que identifica esse telefone.</span><span class="sxs-lookup"><span data-stu-id="e8968-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="e8968-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="e8968-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="e8968-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="e8968-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="e8968-117">Número de telefone.</span><span class="sxs-lookup"><span data-stu-id="e8968-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="e8968-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="e8968-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="e8968-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="e8968-119">dateTime</span></span>  <br/> ||<span data-ttu-id="e8968-120">Carimbo de hora (somente para uso interno).</span><span class="sxs-lookup"><span data-stu-id="e8968-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="e8968-121">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="e8968-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

