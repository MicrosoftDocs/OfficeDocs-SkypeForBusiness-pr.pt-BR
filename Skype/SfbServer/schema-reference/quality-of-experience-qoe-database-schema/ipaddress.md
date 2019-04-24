---
title: Tabela IPAddress
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: A tabela IPAddress mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outros locais no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: b118d85eff7c0f8e355a43e354f97de3c66da7d0
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32212204"
---
# <a name="ipaddress-table"></a><span data-ttu-id="4a31c-104">Tabela IPAddress</span><span class="sxs-lookup"><span data-stu-id="4a31c-104">IPAddress table</span></span>
 
<span data-ttu-id="4a31c-105">A tabela IPAddress mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outros locais no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="4a31c-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="4a31c-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="4a31c-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="4a31c-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4a31c-107">**Column**</span></span>|<span data-ttu-id="4a31c-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4a31c-108">**Data Type**</span></span>|<span data-ttu-id="4a31c-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="4a31c-109">**Key/Index**</span></span>|<span data-ttu-id="4a31c-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="4a31c-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4a31c-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="4a31c-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="4a31c-112">int</span><span class="sxs-lookup"><span data-stu-id="4a31c-112">int</span></span>  <br/> |<span data-ttu-id="4a31c-113">Primária</span><span class="sxs-lookup"><span data-stu-id="4a31c-113">Primary</span></span>  <br/> |<span data-ttu-id="4a31c-114">Identificador exclusivo para o endereço IP especificado.</span><span class="sxs-lookup"><span data-stu-id="4a31c-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="4a31c-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="4a31c-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="4a31c-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="4a31c-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="4a31c-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="4a31c-117">Unique</span></span>  <br/> |<span data-ttu-id="4a31c-118">Endereço IP exclusivo (por exemplo, 189.168.1.1) que mapeia para o IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="4a31c-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="4a31c-119">Isso pode ser um IPv4 ou um endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="4a31c-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

