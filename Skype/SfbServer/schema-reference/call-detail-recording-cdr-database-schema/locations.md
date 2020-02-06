---
title: Tabela locais no Skype for Business Server 2015
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
ms.assetid: 78dc1b14-5394-4f8e-89d3-4ba593272a04
description: Cada registro representa uma referência de localização em uma chamada de emergência, como uma chamada E9-1-1.
ms.openlocfilehash: a1dd7dfdf84ef196b24fa97b1b24950c326b0241
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815109"
---
# <a name="locations-table-in-skype-for-business-server-2015"></a><span data-ttu-id="33b8e-103">Tabela locais no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="33b8e-103">Locations table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="33b8e-104">Cada registro representa uma referência de localização em uma chamada de emergência, como uma chamada E9-1-1.</span><span class="sxs-lookup"><span data-stu-id="33b8e-104">Each record represents one location reference in an emergency call, like an E9-1-1 call.</span></span>
  
|<span data-ttu-id="33b8e-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="33b8e-105">**Column**</span></span>|<span data-ttu-id="33b8e-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="33b8e-106">**Data Type**</span></span>|<span data-ttu-id="33b8e-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="33b8e-107">**Key/Index**</span></span>|<span data-ttu-id="33b8e-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="33b8e-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="33b8e-109">**Id_da_sessãotime**</span><span class="sxs-lookup"><span data-stu-id="33b8e-109">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="33b8e-110">datetime</span><span class="sxs-lookup"><span data-stu-id="33b8e-110">datetime</span></span>  <br/> |<span data-ttu-id="33b8e-111">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="33b8e-111">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="33b8e-112">Tempo de solicitação de sessão.</span><span class="sxs-lookup"><span data-stu-id="33b8e-112">Time of session request.</span></span> <span data-ttu-id="33b8e-113">Usado em conjunto com o **SessionIdSeq** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="33b8e-113">Used in conjunction with **SessionIdSeq** to uniquely identify a session.</span></span> <span data-ttu-id="33b8e-114">Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="33b8e-114">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="33b8e-115">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="33b8e-115">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="33b8e-116">int</span><span class="sxs-lookup"><span data-stu-id="33b8e-116">int</span></span>  <br/> |<span data-ttu-id="33b8e-117">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="33b8e-117">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="33b8e-118">Número de identificação para identificar a sessão.</span><span class="sxs-lookup"><span data-stu-id="33b8e-118">ID number to identify the session.</span></span> <span data-ttu-id="33b8e-119">Usado em conjunto com a **identificação_da_sessãotime** para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="33b8e-119">Used in conjunction with **SessionIdTime** to uniquely identify a session.</span></span> <span data-ttu-id="33b8e-120">Consulte a [tabela de diálogos no Skype for Business Server 2015](dialogs.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="33b8e-120">See the [Dialogs table in Skype for Business Server 2015](dialogs.md) for more information.</span></span> <br/> |
|<span data-ttu-id="33b8e-121">**Local**</span><span class="sxs-lookup"><span data-stu-id="33b8e-121">**Location**</span></span> <br/> |<span data-ttu-id="33b8e-122">nvarchar (max)</span><span class="sxs-lookup"><span data-stu-id="33b8e-122">nvarchar(max)</span></span>  <br/> ||<span data-ttu-id="33b8e-123">Local de chamada de emergência.</span><span class="sxs-lookup"><span data-stu-id="33b8e-123">Location of emergency call.</span></span>  <br/> |
   

