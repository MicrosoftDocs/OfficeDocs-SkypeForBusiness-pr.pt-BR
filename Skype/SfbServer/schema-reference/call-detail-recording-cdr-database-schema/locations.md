---
title: Tabela de localizações em Skype para Business Server 2015
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa uma referência de local em uma chamada de emergência, como uma chamada de E9-1-1.
ms.openlocfilehash: b15e7f0b7930871b97dc3341a47153965529810e
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="2f6bb-103">Tabela de localizações em Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="2f6bb-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="2f6bb-104">Cada registro representa uma referência de local em uma chamada de emergência, como uma chamada de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="2f6bb-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="2f6bb-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="2f6bb-105">**Column**</span></span>|<span data-ttu-id="2f6bb-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="2f6bb-106">**Data Type**</span></span>|<span data-ttu-id="2f6bb-107">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="2f6bb-107">**Key/Index**</span></span>|<span data-ttu-id="2f6bb-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="2f6bb-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="2f6bb-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="2f6bb-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="2f6bb-110">datetime</span><span class="sxs-lookup"><span data-stu-id="2f6bb-110">datetime</span></span>  <br/> |<span data-ttu-id="2f6bb-111">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="2f6bb-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2f6bb-112">Hora da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="2f6bb-112">Time of session request.</span></span> <span data-ttu-id="2f6bb-113">Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="2f6bb-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="2f6bb-114">Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2f6bb-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2f6bb-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="2f6bb-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="2f6bb-116">int</span><span class="sxs-lookup"><span data-stu-id="2f6bb-116">int</span></span>  <br/> |<span data-ttu-id="2f6bb-117">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="2f6bb-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="2f6bb-118">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="2f6bb-118">ID number to identify the session.</span></span> <span data-ttu-id="2f6bb-119">Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="2f6bb-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="2f6bb-120">Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="2f6bb-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="2f6bb-121">**Local**</span><span class="sxs-lookup"><span data-stu-id="2f6bb-121">**Location**</span></span> <br/> |<span data-ttu-id="2f6bb-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="2f6bb-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="2f6bb-123">Local da chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="2f6bb-123">Location of emergency call.</span></span>  <br/> |
   

