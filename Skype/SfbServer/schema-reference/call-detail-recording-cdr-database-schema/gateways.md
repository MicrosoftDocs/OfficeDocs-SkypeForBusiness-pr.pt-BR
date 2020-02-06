---
title: Tabela gateways no Skype for Business Server 2015
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
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: A tabela gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway envolvido em chamadas PSTN (rede telefônica pública comutada) que têm registros no banco de dados.
ms.openlocfilehash: ce85b36d5ad587a096c99ca3f3f496642d3a3dd5
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815159"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="32f92-104">Tabela gateways no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="32f92-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="32f92-105">A tabela gateways é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="32f92-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="32f92-106">Cada registro armazena informações sobre um gateway envolvido em chamadas PSTN (rede telefônica pública comutada) que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="32f92-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="32f92-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="32f92-107">**Column**</span></span>|<span data-ttu-id="32f92-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="32f92-108">**Data Type**</span></span>|<span data-ttu-id="32f92-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="32f92-109">**Key/Index**</span></span>|<span data-ttu-id="32f92-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="32f92-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="32f92-111">**Gatewayid**</span><span class="sxs-lookup"><span data-stu-id="32f92-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="32f92-112">int</span><span class="sxs-lookup"><span data-stu-id="32f92-112">int</span></span>  <br/> |<span data-ttu-id="32f92-113">Primária</span><span class="sxs-lookup"><span data-stu-id="32f92-113">Primary</span></span>  <br/> |<span data-ttu-id="32f92-114">Número exclusivo que identifica esse gateway.</span><span class="sxs-lookup"><span data-stu-id="32f92-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="32f92-115">**Gateway**</span><span class="sxs-lookup"><span data-stu-id="32f92-115">**Gateway**</span></span> <br/> |<span data-ttu-id="32f92-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="32f92-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="32f92-117">Nome do gateway.</span><span class="sxs-lookup"><span data-stu-id="32f92-117">Gateway name.</span></span>  <br/> |
   

