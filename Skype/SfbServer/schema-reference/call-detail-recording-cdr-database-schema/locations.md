---
title: Tabela de localizações em Skype para Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa uma referência de local em uma chamada de emergência, como uma chamada de E9-1-1.
ms.openlocfilehash: 389aa56dfaf6d8b732692909ff3375a992b504b6
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930238"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="f079e-103">Tabela de localizações em Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="f079e-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="f079e-104">Cada registro representa uma referência de local em uma chamada de emergência, como uma chamada de E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="f079e-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="f079e-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="f079e-105">**Column**</span></span>|<span data-ttu-id="f079e-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="f079e-106">**Data Type**</span></span>|<span data-ttu-id="f079e-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="f079e-107">**Key/Index**</span></span>|<span data-ttu-id="f079e-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="f079e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="f079e-109">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="f079e-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="f079e-110">datetime</span><span class="sxs-lookup"><span data-stu-id="f079e-110">datetime</span></span>  <br/> |<span data-ttu-id="f079e-111">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="f079e-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f079e-112">Hora da solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="f079e-112">Time of session request.</span></span> <span data-ttu-id="f079e-113">Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="f079e-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="f079e-114">Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f079e-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f079e-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="f079e-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="f079e-116">int</span><span class="sxs-lookup"><span data-stu-id="f079e-116">int</span></span>  <br/> |<span data-ttu-id="f079e-117">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="f079e-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="f079e-118">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="f079e-118">ID number to identify the session.</span></span> <span data-ttu-id="f079e-119">Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="f079e-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="f079e-120">Consulte a [tabela no Skype para Business Server 2015 de diálogos](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="f079e-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="f079e-121">**Local**</span><span class="sxs-lookup"><span data-stu-id="f079e-121">**Location**</span></span> <br/> |<span data-ttu-id="f079e-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="f079e-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="f079e-123">Local da chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="f079e-123">Location of emergency call.</span></span>  <br/> |
   

