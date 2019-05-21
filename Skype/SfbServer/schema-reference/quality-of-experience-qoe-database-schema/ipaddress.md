---
title: Tabela IPAddress
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP exclusivos usados em outro lugar no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 74d74636b7183d1369db85c363997460a434d8f3
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34294919"
---
# <a name="ipaddress-table"></a><span data-ttu-id="a7e8a-104">Tabela IPAddress</span><span class="sxs-lookup"><span data-stu-id="a7e8a-104">IPAddress table</span></span>
 
<span data-ttu-id="a7e8a-105">A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP exclusivos usados em outro lugar no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="a7e8a-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="a7e8a-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7e8a-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a7e8a-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a7e8a-107">**Column**</span></span>|<span data-ttu-id="a7e8a-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a7e8a-108">**Data Type**</span></span>|<span data-ttu-id="a7e8a-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="a7e8a-109">**Key/Index**</span></span>|<span data-ttu-id="a7e8a-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a7e8a-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7e8a-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="a7e8a-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="a7e8a-112">int</span><span class="sxs-lookup"><span data-stu-id="a7e8a-112">int</span></span>  <br/> |<span data-ttu-id="a7e8a-113">Primária</span><span class="sxs-lookup"><span data-stu-id="a7e8a-113">Primary</span></span>  <br/> |<span data-ttu-id="a7e8a-114">Identificador exclusivo do endereço IP especificado.</span><span class="sxs-lookup"><span data-stu-id="a7e8a-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="a7e8a-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="a7e8a-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="a7e8a-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="a7e8a-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="a7e8a-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="a7e8a-117">Unique</span></span>  <br/> |<span data-ttu-id="a7e8a-118">Endereço IP exclusivo (por exemplo, 189.168.1.1) que é mapeado para o IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="a7e8a-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="a7e8a-119">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="a7e8a-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

