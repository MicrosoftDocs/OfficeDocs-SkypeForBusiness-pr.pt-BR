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
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP exclusivos usados em outro lugar no banco de dados de qualidade da experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 2789d436b007a5208d98a4b32dca14517fbaaa57
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809539"
---
# <a name="ipaddress-table"></a><span data-ttu-id="a1a37-104">Tabela IPAddress</span><span class="sxs-lookup"><span data-stu-id="a1a37-104">IPAddress table</span></span>
 
<span data-ttu-id="a1a37-105">A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP exclusivos usados em outro lugar no banco de dados de qualidade da experiência.</span><span class="sxs-lookup"><span data-stu-id="a1a37-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="a1a37-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a1a37-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="a1a37-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a1a37-107">**Column**</span></span>|<span data-ttu-id="a1a37-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a1a37-108">**Data Type**</span></span>|<span data-ttu-id="a1a37-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="a1a37-109">**Key/Index**</span></span>|<span data-ttu-id="a1a37-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a1a37-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a1a37-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="a1a37-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="a1a37-112">int</span><span class="sxs-lookup"><span data-stu-id="a1a37-112">int</span></span>  <br/> |<span data-ttu-id="a1a37-113">Primária</span><span class="sxs-lookup"><span data-stu-id="a1a37-113">Primary</span></span>  <br/> |<span data-ttu-id="a1a37-114">Identificador exclusivo do endereço IP especificado.</span><span class="sxs-lookup"><span data-stu-id="a1a37-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="a1a37-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="a1a37-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="a1a37-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="a1a37-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="a1a37-117">Exclusividade</span><span class="sxs-lookup"><span data-stu-id="a1a37-117">Unique</span></span>  <br/> |<span data-ttu-id="a1a37-118">Endereço IP exclusivo (por exemplo, 189.168.1.1) que é mapeado para o IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="a1a37-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="a1a37-119">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="a1a37-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

