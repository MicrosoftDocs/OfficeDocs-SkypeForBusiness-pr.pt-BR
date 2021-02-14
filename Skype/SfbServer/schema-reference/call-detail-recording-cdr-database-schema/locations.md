---
title: Tabela Locais no Skype for Business Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa uma referência de local em uma chamada de emergência, como uma chamada do tipo 9-1-1 Avançado.
ms.openlocfilehash: b177e79217f8586d7655b2a4645a603bd8e2f97f
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49821511"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="6f646-103">Tabela Locais no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6f646-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="6f646-104">Cada registro representa uma referência de local em uma chamada de emergência, como uma chamada do tipo 9-1-1 Avançado.</span><span class="sxs-lookup"><span data-stu-id="6f646-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="6f646-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6f646-105">**Column**</span></span>|<span data-ttu-id="6f646-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="6f646-106">**Data Type**</span></span>|<span data-ttu-id="6f646-107">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="6f646-107">**Key/Index**</span></span>|<span data-ttu-id="6f646-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="6f646-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="6f646-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="6f646-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="6f646-110">datetime</span><span class="sxs-lookup"><span data-stu-id="6f646-110">datetime</span></span>  <br/> |<span data-ttu-id="6f646-111">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="6f646-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6f646-112">Tempo da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="6f646-112">Time of session request.</span></span> <span data-ttu-id="6f646-113">Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6f646-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="6f646-114">Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6f646-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6f646-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="6f646-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="6f646-116">int</span><span class="sxs-lookup"><span data-stu-id="6f646-116">int</span></span>  <br/> |<span data-ttu-id="6f646-117">Primário, Estrangeiro</span><span class="sxs-lookup"><span data-stu-id="6f646-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="6f646-118">O número de ID para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="6f646-118">ID number to identify the session.</span></span> <span data-ttu-id="6f646-119">Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="6f646-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="6f646-120">Consulte a [tabela Dialogs no Skype for Business Server 2015](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6f646-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6f646-121">**Location**</span><span class="sxs-lookup"><span data-stu-id="6f646-121">**Location**</span></span> <br/> |<span data-ttu-id="6f646-122">nvarchar(max)</span><span class="sxs-lookup"><span data-stu-id="6f646-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="6f646-123">Local da chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="6f646-123">Location of emergency call.</span></span>  <br/> |
   

