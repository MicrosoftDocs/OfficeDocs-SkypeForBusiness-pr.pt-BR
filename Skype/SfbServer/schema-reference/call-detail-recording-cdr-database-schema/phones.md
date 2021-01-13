---
title: Tabela Phones
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
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: A tabela Phones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que possuem registros no banco de dados.
ms.openlocfilehash: 12825423b9a03bff93e0d70705a4083bb8c881c9
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49823261"
---
# <a name="phones-table"></a><span data-ttu-id="de72f-104">Tabela Phones</span><span class="sxs-lookup"><span data-stu-id="de72f-104">Phones table</span></span>
 
<span data-ttu-id="de72f-105">A tabela Phones é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="de72f-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="de72f-106">Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que possuem registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="de72f-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="de72f-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="de72f-107">**Column**</span></span>|<span data-ttu-id="de72f-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="de72f-108">**Data Type**</span></span>|<span data-ttu-id="de72f-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="de72f-109">**Key/Index**</span></span>|<span data-ttu-id="de72f-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="de72f-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="de72f-111">**PhoneId**</span><span class="sxs-lookup"><span data-stu-id="de72f-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="de72f-112">int</span><span class="sxs-lookup"><span data-stu-id="de72f-112">int</span></span>  <br/> |<span data-ttu-id="de72f-113">Primário</span><span class="sxs-lookup"><span data-stu-id="de72f-113">Primary</span></span>  <br/> |<span data-ttu-id="de72f-114">Número exclusivo que identifica este telefone.</span><span class="sxs-lookup"><span data-stu-id="de72f-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="de72f-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="de72f-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="de72f-116">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="de72f-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="de72f-117">Número de telefone.</span><span class="sxs-lookup"><span data-stu-id="de72f-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="de72f-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="de72f-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="de72f-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="de72f-119">dateTime</span></span>  <br/> ||<span data-ttu-id="de72f-120">Carimbo de data/hora (somente para uso interno).</span><span class="sxs-lookup"><span data-stu-id="de72f-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="de72f-121">Este campo foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="de72f-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

