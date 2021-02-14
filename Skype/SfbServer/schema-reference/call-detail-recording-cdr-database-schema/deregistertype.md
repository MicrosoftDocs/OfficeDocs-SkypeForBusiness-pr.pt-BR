---
title: Tabela DeRegisterType no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: A tabela DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de registro de usuário, como "iniciado pelo cliente", "registro expirado" ou "o cliente parou de responder".
ms.openlocfilehash: 388aebc1ac180e1298addd54859cff6759b28be0
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49816071"
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="1f664-103">Tabela DeRegisterType no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="1f664-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="1f664-104">A tabela DeRegisterType é uma tabela estática que armazena a lista de possíveis tipos de registro de usuário, como "iniciado pelo cliente", "registro expirado" ou "o cliente parou de responder".</span><span class="sxs-lookup"><span data-stu-id="1f664-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="1f664-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="1f664-105">**Column**</span></span>|<span data-ttu-id="1f664-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="1f664-106">**Data Type**</span></span>|<span data-ttu-id="1f664-107">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="1f664-107">**Key/Index**</span></span>|<span data-ttu-id="1f664-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="1f664-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="1f664-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="1f664-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="1f664-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="1f664-110">tinyint</span></span>  <br/> |<span data-ttu-id="1f664-111">Primário</span><span class="sxs-lookup"><span data-stu-id="1f664-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="1f664-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="1f664-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="1f664-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="1f664-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="1f664-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="1f664-114">Allowed values:</span></span> <br/>  <span data-ttu-id="1f664-115">0 -- Desconhecido</span><span class="sxs-lookup"><span data-stu-id="1f664-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="1f664-116">Iniciado o cancelamento do registro pelo cliente</span><span class="sxs-lookup"><span data-stu-id="1f664-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="1f664-117">2 -- Registro expirado</span><span class="sxs-lookup"><span data-stu-id="1f664-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="1f664-118">3 - O cliente parou de ser</span><span class="sxs-lookup"><span data-stu-id="1f664-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="1f664-119">Atributos do usuário mudaram</span><span class="sxs-lookup"><span data-stu-id="1f664-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="1f664-120">5 - Registrador Preferencial Alterado</span><span class="sxs-lookup"><span data-stu-id="1f664-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="1f664-121">6 -- Cliente herdado em Modo de sobrevivência</span><span class="sxs-lookup"><span data-stu-id="1f664-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

