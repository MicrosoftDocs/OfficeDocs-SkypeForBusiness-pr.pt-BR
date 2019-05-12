---
title: Tabela IPAddress
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: A tabela IPAddress mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outros locais no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: d7d3b5f9192c2385836f42f9c430da5b99752892
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920030"
---
# <a name="ipaddress-table"></a><span data-ttu-id="7b5ec-104">Tabela IPAddress</span><span class="sxs-lookup"><span data-stu-id="7b5ec-104">IPAddress table</span></span>
 
<span data-ttu-id="7b5ec-105">A tabela IPAddress mapeia endereços IP para os identificadores de endereços IP exclusivos usados em outros locais no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="7b5ec-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="7b5ec-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="7b5ec-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="7b5ec-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="7b5ec-107">**Column**</span></span>|<span data-ttu-id="7b5ec-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="7b5ec-108">**Data Type**</span></span>|<span data-ttu-id="7b5ec-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="7b5ec-109">**Key/Index**</span></span>|<span data-ttu-id="7b5ec-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="7b5ec-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="7b5ec-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="7b5ec-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="7b5ec-112">int</span><span class="sxs-lookup"><span data-stu-id="7b5ec-112">int</span></span>  <br/> |<span data-ttu-id="7b5ec-113">Primária</span><span class="sxs-lookup"><span data-stu-id="7b5ec-113">Primary</span></span>  <br/> |<span data-ttu-id="7b5ec-114">Identificador exclusivo para o endereço IP especificado.</span><span class="sxs-lookup"><span data-stu-id="7b5ec-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="7b5ec-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="7b5ec-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="7b5ec-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="7b5ec-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="7b5ec-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="7b5ec-117">Unique</span></span>  <br/> |<span data-ttu-id="7b5ec-118">Endereço IP exclusivo (por exemplo, 189.168.1.1) que mapeia para o IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="7b5ec-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="7b5ec-119">Isso pode ser um IPv4 ou um endereço IPv6.</span><span class="sxs-lookup"><span data-stu-id="7b5ec-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

