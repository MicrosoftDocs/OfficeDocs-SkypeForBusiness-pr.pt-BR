---
title: Tabela ErrorCategory no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 0fde3b73-9a2f-44dd-b8dc-6df512303ff1
description: 'A tabela ErrorCategory contém o nome amigável para cada classificação de diagnóstico do Skype for Business Server 2015. Por padrão, o Skype for Business Server 2015 usa as seguintes classificações:'
ms.openlocfilehash: ca3719f6d284cf715be1a87b1c7a5dc04ae84b04
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813141"
---
# <a name="errorcategory-table-in-skype-for-business-server-2015"></a><span data-ttu-id="5e5c1-104">Tabela ErrorCategory no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="5e5c1-104">ErrorCategory table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="5e5c1-105">A tabela ErrorCategory contém o nome amigável para cada classificação de diagnóstico do Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="5e5c1-105">The ErrorCategory table contains the friendly name for each Skype for Business Server 2015 diagnostic classification.</span></span> <span data-ttu-id="5e5c1-106">Por padrão, o Skype for Business Server 2015 usa as seguintes classificações:</span><span class="sxs-lookup"><span data-stu-id="5e5c1-106">By default, Skype for Business Server 2015 uses the following classifications:</span></span>
  
- <span data-ttu-id="5e5c1-107">0 -- Sucesso</span><span class="sxs-lookup"><span data-stu-id="5e5c1-107">0 -- Success</span></span>
    
- <span data-ttu-id="5e5c1-108">1 -- Falha esperada</span><span class="sxs-lookup"><span data-stu-id="5e5c1-108">1 -- Expected failure</span></span>
    
- <span data-ttu-id="5e5c1-109">2 - Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="5e5c1-109">2 - Unexpected failure</span></span>
    
<span data-ttu-id="5e5c1-110">Esta tabela foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5e5c1-110">This table was introduced in Microsoft Lync Server 2013.</span></span>
  
|<span data-ttu-id="5e5c1-111">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="5e5c1-111">**Column**</span></span>|<span data-ttu-id="5e5c1-112">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5e5c1-112">**Data Type**</span></span>|<span data-ttu-id="5e5c1-113">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="5e5c1-113">**Key/Index**</span></span>|<span data-ttu-id="5e5c1-114">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="5e5c1-114">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="5e5c1-115">**CategoryId**</span><span class="sxs-lookup"><span data-stu-id="5e5c1-115">**CategoryId**</span></span> <br/> |<span data-ttu-id="5e5c1-116">tinyint</span><span class="sxs-lookup"><span data-stu-id="5e5c1-116">tinyint</span></span>  <br/> |<span data-ttu-id="5e5c1-117">Primário</span><span class="sxs-lookup"><span data-stu-id="5e5c1-117">Primary</span></span>  <br/> |<span data-ttu-id="5e5c1-118">Identificador único para a classificação.</span><span class="sxs-lookup"><span data-stu-id="5e5c1-118">Unique identifier for the classification.</span></span>  <br/> |
|<span data-ttu-id="5e5c1-119">**Nome**</span><span class="sxs-lookup"><span data-stu-id="5e5c1-119">**Name**</span></span> <br/> |<span data-ttu-id="5e5c1-120">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5e5c1-120">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="5e5c1-p103">Valor e nome amigável atribuídos à classificação. Os valores permitidos são:</span><span class="sxs-lookup"><span data-stu-id="5e5c1-p103">Value and friendly name assigned to the classification. Allowed values are:</span></span> <br/>  <span data-ttu-id="5e5c1-123">0 -- Sucesso</span><span class="sxs-lookup"><span data-stu-id="5e5c1-123">0 -- Success</span></span> <br/>  <span data-ttu-id="5e5c1-124">1 -- Falha esperada</span><span class="sxs-lookup"><span data-stu-id="5e5c1-124">1 -- Expected failure</span></span> <br/>  <span data-ttu-id="5e5c1-125">2 - Falha inesperada</span><span class="sxs-lookup"><span data-stu-id="5e5c1-125">2 - Unexpected failure</span></span> <br/> |
   

