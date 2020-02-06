---
title: Tabela canregistertype no Skype for Business Server 2015
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
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: A tabela canregistertype é uma tabela estática que armazena a lista de possíveis tipos de registros de usuário possíveis, como ' cliente iniciado ', ' registro expirado ' ou ' cliente parou de responder '.
ms.openlocfilehash: ae9afafe91336b1e5c74fd0a854e2975a3b4ba8e
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815289"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="9f738-103">Tabela canregistertype no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="9f738-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="9f738-104">A tabela canregistertype é uma tabela estática que armazena a lista de possíveis tipos de registros de usuário possíveis, como ' cliente iniciado ', ' registro expirado ' ou ' cliente parou de responder '.</span><span class="sxs-lookup"><span data-stu-id="9f738-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="9f738-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="9f738-105">**Column**</span></span>|<span data-ttu-id="9f738-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="9f738-106">**Data Type**</span></span>|<span data-ttu-id="9f738-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="9f738-107">**Key/Index**</span></span>|<span data-ttu-id="9f738-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="9f738-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="9f738-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="9f738-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="9f738-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="9f738-110">tinyint</span></span>  <br/> |<span data-ttu-id="9f738-111">Primária</span><span class="sxs-lookup"><span data-stu-id="9f738-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="9f738-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="9f738-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="9f738-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="9f738-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="9f738-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="9f738-114">Allowed values:</span></span> <br/>  <span data-ttu-id="9f738-115">0--desconhecido</span><span class="sxs-lookup"><span data-stu-id="9f738-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="9f738-116">1--cliente iniciou o registro</span><span class="sxs-lookup"><span data-stu-id="9f738-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="9f738-117">2--registro expirado</span><span class="sxs-lookup"><span data-stu-id="9f738-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="9f738-118">3-cliente travado</span><span class="sxs-lookup"><span data-stu-id="9f738-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="9f738-119">4--atributos de usuário alterados</span><span class="sxs-lookup"><span data-stu-id="9f738-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="9f738-120">5-registrador preferencial alterado</span><span class="sxs-lookup"><span data-stu-id="9f738-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="9f738-121">6 – cliente herdado no modo de sobrevivência</span><span class="sxs-lookup"><span data-stu-id="9f738-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

