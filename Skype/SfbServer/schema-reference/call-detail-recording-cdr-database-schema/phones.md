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
localization_priority: Normal
ms.assetid: 41cb356d-9cc8-42b6-ac23-98a61b25aadc
description: A tabela de telefones é uma tabela de suporte. Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.
ms.openlocfilehash: 684586f21b16c785bcc75458e5330c42aad2ccb4
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34295941"
---
# <a name="phones-table"></a><span data-ttu-id="50e59-104">Tabela Phones</span><span class="sxs-lookup"><span data-stu-id="50e59-104">Phones table</span></span>
 
<span data-ttu-id="50e59-105">A tabela de telefones é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="50e59-105">The Phones table is a supporting table.</span></span> <span data-ttu-id="50e59-106">Cada registro na tabela armazena informações sobre um número de telefone envolvido em chamadas VoIP que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="50e59-106">Each record in the table stores information about one phone number involved in VoIP calls that have records in the database.</span></span>
  
|<span data-ttu-id="50e59-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="50e59-107">**Column**</span></span>|<span data-ttu-id="50e59-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="50e59-108">**Data Type**</span></span>|<span data-ttu-id="50e59-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="50e59-109">**Key/Index**</span></span>|<span data-ttu-id="50e59-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="50e59-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="50e59-111">**PHONEID**</span><span class="sxs-lookup"><span data-stu-id="50e59-111">**PhoneId**</span></span> <br/> |<span data-ttu-id="50e59-112">int</span><span class="sxs-lookup"><span data-stu-id="50e59-112">int</span></span>  <br/> |<span data-ttu-id="50e59-113">Primária</span><span class="sxs-lookup"><span data-stu-id="50e59-113">Primary</span></span>  <br/> |<span data-ttu-id="50e59-114">Número exclusivo que identifica este telefone.</span><span class="sxs-lookup"><span data-stu-id="50e59-114">Unique number identifying this phone.</span></span>  <br/> |
|<span data-ttu-id="50e59-115">**PhoneUri**</span><span class="sxs-lookup"><span data-stu-id="50e59-115">**PhoneUri**</span></span> <br/> |<span data-ttu-id="50e59-116">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="50e59-116">nvarchar(450)</span></span>  <br/> | <br/> |<span data-ttu-id="50e59-117">Número de telefone.</span><span class="sxs-lookup"><span data-stu-id="50e59-117">Phone number.</span></span>  <br/> |
|<span data-ttu-id="50e59-118">**NextUpdateTS**</span><span class="sxs-lookup"><span data-stu-id="50e59-118">**NextUpdateTS**</span></span> <br/> |<span data-ttu-id="50e59-119">dateTime</span><span class="sxs-lookup"><span data-stu-id="50e59-119">dateTime</span></span>  <br/> ||<span data-ttu-id="50e59-120">Carimbo de data/hora (apenas para uso interno).</span><span class="sxs-lookup"><span data-stu-id="50e59-120">Time stamp (for internal use only).</span></span>  <br/> <span data-ttu-id="50e59-121">Este campo foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="50e59-121">This field was introduced in Microsoft Lync Server 2013.</span></span>  <br/> |
   

