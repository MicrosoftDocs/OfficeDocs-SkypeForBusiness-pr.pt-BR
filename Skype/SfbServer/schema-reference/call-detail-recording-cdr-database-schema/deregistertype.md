---
title: Tabela DeRegisterType Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 09148118-6209-4fd7-a494-99118689a245
description: A tabela DeRegisterType é uma tabela estática que armazena a lista de possível usuário registra desprovisionamento tipos, como "cliente iniciado", "registro vencido" ou 'cliente parado de responder.'
ms.openlocfilehash: 97b342a8d0175da0517aa36e0fea477e32df4dd9
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="deregistertype-table-in-skype-for-business-server-2015"></a><span data-ttu-id="a65ea-103">Tabela DeRegisterType Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="a65ea-103">DeRegisterType table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="a65ea-104">A tabela DeRegisterType é uma tabela estática que armazena a lista de possível usuário registra desprovisionamento tipos, como "cliente iniciado", "registro vencido" ou 'cliente parado de responder.'</span><span class="sxs-lookup"><span data-stu-id="a65ea-104">The DeRegisterType table is a static table that stores the list of possible user de-registers types, such as 'client initiated', 'registration expired', or 'client stopped responding.'</span></span>
  
|<span data-ttu-id="a65ea-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a65ea-105">**Column**</span></span>|<span data-ttu-id="a65ea-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a65ea-106">**Data Type**</span></span>|<span data-ttu-id="a65ea-107">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="a65ea-107">**Key/Index**</span></span>|<span data-ttu-id="a65ea-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a65ea-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a65ea-109">**DeRegisterTypeId**</span><span class="sxs-lookup"><span data-stu-id="a65ea-109">**DeRegisterTypeId**</span></span> <br/> |<span data-ttu-id="a65ea-110">tinyint</span><span class="sxs-lookup"><span data-stu-id="a65ea-110">tinyint</span></span>  <br/> |<span data-ttu-id="a65ea-111">Primária</span><span class="sxs-lookup"><span data-stu-id="a65ea-111">Primary</span></span>  <br/> ||
|<span data-ttu-id="a65ea-112">**DeRegisterReason**</span><span class="sxs-lookup"><span data-stu-id="a65ea-112">**DeRegisterReason**</span></span> <br/> |<span data-ttu-id="a65ea-113">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a65ea-113">nvarchar(256)</span></span>  <br/> || <span data-ttu-id="a65ea-114">Valores permitidos:</span><span class="sxs-lookup"><span data-stu-id="a65ea-114">Allowed values:</span></span> <br/>  <span data-ttu-id="a65ea-115">0--desconhecido</span><span class="sxs-lookup"><span data-stu-id="a65ea-115">0 -- Unknown</span></span> <br/>  <span data-ttu-id="a65ea-116">1-- cliente iniciado o cancelamento do registro</span><span class="sxs-lookup"><span data-stu-id="a65ea-116">1 -- Client Initiated Deregistration</span></span> <br/>  <span data-ttu-id="a65ea-117">2-- registro expirado</span><span class="sxs-lookup"><span data-stu-id="a65ea-117">2 -- Registration Expired</span></span> <br/>  <span data-ttu-id="a65ea-118">3 - cliente paralisado</span><span class="sxs-lookup"><span data-stu-id="a65ea-118">3 - Client crashed</span></span> <br/>  <span data-ttu-id="a65ea-119">4 atributos do usuário mudaram</span><span class="sxs-lookup"><span data-stu-id="a65ea-119">4 -- User Attributes Changed</span></span> <br/>  <span data-ttu-id="a65ea-120">5 - registrador preferido mudou</span><span class="sxs-lookup"><span data-stu-id="a65ea-120">5 - Preferred Registrar Changed</span></span> <br/>  <span data-ttu-id="a65ea-121">6-- Cliente de herdado em modo de sobrevivência</span><span class="sxs-lookup"><span data-stu-id="a65ea-121">6 -- Legacy Client In Survival Mode</span></span> <br/> |
   

