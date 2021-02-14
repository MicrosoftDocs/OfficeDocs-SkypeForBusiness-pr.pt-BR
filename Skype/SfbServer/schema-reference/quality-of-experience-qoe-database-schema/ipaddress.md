---
title: Tabela IPAddress
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ec018b9-158e-4bbe-ad46-869e60315555
description: A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP exclusivos usados em outro lugar no banco de dados de Qualidade da Experiência. Esta tabela foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 31334c553641088a5b77d0bb24517791e5f84ebe
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802771"
---
# <a name="ipaddress-table"></a><span data-ttu-id="bcb4e-104">Tabela IPAddress</span><span class="sxs-lookup"><span data-stu-id="bcb4e-104">IPAddress table</span></span>
 
<span data-ttu-id="bcb4e-105">A tabela IPAddress mapeia endereços IP para os identificadores de endereço IP exclusivos usados em outro lugar no banco de dados de Qualidade da Experiência.</span><span class="sxs-lookup"><span data-stu-id="bcb4e-105">The IPAddress table maps IP addresses to the unique IP address identifiers used elsewhere in the Quality of Experience database.</span></span> <span data-ttu-id="bcb4e-106">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="bcb4e-106">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="bcb4e-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="bcb4e-107">**Column**</span></span>|<span data-ttu-id="bcb4e-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="bcb4e-108">**Data Type**</span></span>|<span data-ttu-id="bcb4e-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="bcb4e-109">**Key/Index**</span></span>|<span data-ttu-id="bcb4e-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="bcb4e-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="bcb4e-111">**IPAddressKey**</span><span class="sxs-lookup"><span data-stu-id="bcb4e-111">**IPAddressKey**</span></span> <br/> |<span data-ttu-id="bcb4e-112">int</span><span class="sxs-lookup"><span data-stu-id="bcb4e-112">int</span></span>  <br/> |<span data-ttu-id="bcb4e-113">Primário</span><span class="sxs-lookup"><span data-stu-id="bcb4e-113">Primary</span></span>  <br/> |<span data-ttu-id="bcb4e-114">Identificador exclusivo do endereço IP especificado.</span><span class="sxs-lookup"><span data-stu-id="bcb4e-114">Unique identifier for the specified IP address.</span></span>  <br/> |
|<span data-ttu-id="bcb4e-115">**IPAddress**</span><span class="sxs-lookup"><span data-stu-id="bcb4e-115">**IPAddress**</span></span> <br/> |<span data-ttu-id="bcb4e-116">varchar(50)</span><span class="sxs-lookup"><span data-stu-id="bcb4e-116">varchar(50)</span></span>  <br/> |<span data-ttu-id="bcb4e-117">Exclusivo</span><span class="sxs-lookup"><span data-stu-id="bcb4e-117">Unique</span></span>  <br/> |<span data-ttu-id="bcb4e-118">Endereço IP exclusivo (por exemplo, 189.168.1.1) mapeada para IpAddressKey.</span><span class="sxs-lookup"><span data-stu-id="bcb4e-118">Unique IP address (for example, 189.168.1.1) that maps to the IpAddressKey.</span></span> <span data-ttu-id="bcb4e-119">Pode ser um endereço IPv4 ou IPv6.</span><span class="sxs-lookup"><span data-stu-id="bcb4e-119">This may be either an IPv4 or an IPv6 address.</span></span>  <br/> |
   

