---
title: Tabela de gateways no Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: a909daad-d137-45e0-b149-1de9f8e1e029
description: A tabela de Gateways é uma tabela de suporte. Cada registro armazena informações sobre um gateway que está envolvido em chamadas de (PSTN) da rede telefônica pública comutada que têm registros no banco de dados.
ms.openlocfilehash: 16860e924fb69f1dfe337e05c13d54fb66a8ed81
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30899078"
---
# <a name="gateways-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9cc23-104">Tabela de gateways no Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9cc23-104">Gateways table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9cc23-105">A tabela de Gateways é uma tabela de suporte.</span><span class="sxs-lookup"><span data-stu-id="9cc23-105">The Gateways table is a supporting table.</span></span> <span data-ttu-id="9cc23-106">Cada registro armazena informações sobre um gateway que está envolvido em chamadas de (PSTN) da rede telefônica pública comutada que têm registros no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9cc23-106">Each record stores information about one gateway that is involved in public switched telephone network (PSTN) calls that have records in the database.</span></span>
  
|<span data-ttu-id="9cc23-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9cc23-107">**Column**</span></span>|<span data-ttu-id="9cc23-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9cc23-108">**Data Type**</span></span>|<span data-ttu-id="9cc23-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="9cc23-109">**Key/Index**</span></span>|<span data-ttu-id="9cc23-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="9cc23-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9cc23-111">**GatewayId**</span><span class="sxs-lookup"><span data-stu-id="9cc23-111">**GatewayId**</span></span> <br/> |<span data-ttu-id="9cc23-112">int</span><span class="sxs-lookup"><span data-stu-id="9cc23-112">int</span></span>  <br/> |<span data-ttu-id="9cc23-113">Primária</span><span class="sxs-lookup"><span data-stu-id="9cc23-113">Primary</span></span>  <br/> |<span data-ttu-id="9cc23-114">Número exclusivo que identifica este gateway.</span><span class="sxs-lookup"><span data-stu-id="9cc23-114">Unique number identifying this gateway.</span></span>  <br/> |
|<span data-ttu-id="9cc23-115">**Gateway**</span><span class="sxs-lookup"><span data-stu-id="9cc23-115">**Gateway**</span></span> <br/> |<span data-ttu-id="9cc23-116">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9cc23-116">nvarchar(256)</span></span>  <br/> | <br/> |<span data-ttu-id="9cc23-117">Nome do gateway.</span><span class="sxs-lookup"><span data-stu-id="9cc23-117">Gateway name.</span></span>  <br/> |
   

