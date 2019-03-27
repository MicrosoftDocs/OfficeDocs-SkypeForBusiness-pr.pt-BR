---
title: Tabela de localizações em Skype para Business Server 2015
ms.reviewer: ''
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
ms.openlocfilehash: 180a094ef10cc54b4fd65a30adb0909789afa3d6
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876941"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="32e09-103">Tabela de localizações em Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="32e09-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="32e09-104">Cada registro representa uma referência de local em uma chamada de emergência, como uma chamada de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="32e09-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="32e09-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="32e09-105">**Column**</span></span>|<span data-ttu-id="32e09-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="32e09-106">**Data Type**</span></span>|<span data-ttu-id="32e09-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="32e09-107">**Key/Index**</span></span>|<span data-ttu-id="32e09-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="32e09-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="32e09-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="32e09-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="32e09-110">datetime</span><span class="sxs-lookup"><span data-stu-id="32e09-110">datetime</span></span>  <br/> |<span data-ttu-id="32e09-111">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="32e09-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="32e09-112">Hora da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="32e09-112">Time of session request.</span></span> <span data-ttu-id="32e09-113">Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="32e09-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="32e09-114">Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="32e09-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="32e09-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="32e09-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="32e09-116">int</span><span class="sxs-lookup"><span data-stu-id="32e09-116">int</span></span>  <br/> |<span data-ttu-id="32e09-117">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="32e09-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="32e09-118">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="32e09-118">ID number to identify the session.</span></span> <span data-ttu-id="32e09-119">Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="32e09-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="32e09-120">Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="32e09-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="32e09-121">**Local**</span><span class="sxs-lookup"><span data-stu-id="32e09-121">**Location**</span></span> <br/> |<span data-ttu-id="32e09-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="32e09-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="32e09-123">Local da chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="32e09-123">Location of emergency call.</span></span>  <br/> |
   

