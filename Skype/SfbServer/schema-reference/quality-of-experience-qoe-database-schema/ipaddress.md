---
title: Tabela IPAddress
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
ms.openlocfilehash: 6372d46b69046f944ba33d4deff6d29e923a94cb
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="ipaddress-table"></a><span data-ttu-id="3f3b5-104">Tabela IPAddress</span><span class="sxs-lookup"><span data-stu-id="3f3b5-104">IPAddress table</span></span>
 
<span data-ttu-id="3f3b5-105">A tabela IPAddress mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outros locais no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="3f3b5-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="3f3b5-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="3f3b5-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="3f3b5-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3f3b5-107">**Column**</span></span>|<span data-ttu-id="3f3b5-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="3f3b5-108">**Data Type**</span></span>|<span data-ttu-id="3f3b5-109">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="3f3b5-109">**Key/Index**</span></span>|<span data-ttu-id="3f3b5-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="3f3b5-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3f3b5-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="3f3b5-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="3f3b5-112">int</span><span class="sxs-lookup"><span data-stu-id="3f3b5-112">int</span></span>  <br/> |<span data-ttu-id="3f3b5-113">Primária</span><span class="sxs-lookup"><span data-stu-id="3f3b5-113">Primary</span></span>  <br/> |<span data-ttu-id="3f3b5-114">Identificador exclusivo para o endereço IP especificado.</span><span class="sxs-lookup"><span data-stu-id="3f3b5-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="3f3b5-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="3f3b5-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="3f3b5-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="3f3b5-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="3f3b5-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="3f3b5-117">Unique</span></span>  <br/> |<span data-ttu-id="3f3b5-118">Endereço IP exclusivo (por exemplo, 189.168.1.1) que mapeia para o IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="3f3b5-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="3f3b5-119">Isso pode ser um IPv4 ou um endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="3f3b5-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

