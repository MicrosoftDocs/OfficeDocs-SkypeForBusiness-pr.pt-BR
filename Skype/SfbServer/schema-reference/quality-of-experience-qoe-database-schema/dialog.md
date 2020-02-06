---
title: Tabela Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: A tabela de caixa de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo SIP (protocolo de início de sessão).
ms.openlocfilehash: 85d4a9f16a88db386565c065161eedeb61fba913
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41809529"
---
# <a name="dialog-table"></a><span data-ttu-id="a9411-103">Tabela Dialog</span><span class="sxs-lookup"><span data-stu-id="a9411-103">Dialog table</span></span>
 
<span data-ttu-id="a9411-104">A tabela de caixa de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo SIP (protocolo de início de sessão).</span><span class="sxs-lookup"><span data-stu-id="a9411-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="a9411-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a9411-105">**Column**</span></span>|<span data-ttu-id="a9411-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a9411-106">**Data Type**</span></span>|<span data-ttu-id="a9411-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="a9411-107">**Key/Index**</span></span>|<span data-ttu-id="a9411-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a9411-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a9411-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="a9411-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="a9411-110">datetime</span><span class="sxs-lookup"><span data-stu-id="a9411-110">datetime</span></span>  <br/> |<span data-ttu-id="a9411-111">Primária</span><span class="sxs-lookup"><span data-stu-id="a9411-111">Primary</span></span>  <br/> |<span data-ttu-id="a9411-112">Tempo quando o agente de Quality of Excellence (QoE) recebe o primeiro relatório do chamador ou do receptor.</span><span class="sxs-lookup"><span data-stu-id="a9411-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="a9411-113">Usado em conjunto com o SessionSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="a9411-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="a9411-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="a9411-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="a9411-115">int</span><span class="sxs-lookup"><span data-stu-id="a9411-115">int</span></span>  <br/> |<span data-ttu-id="a9411-116">Primária</span><span class="sxs-lookup"><span data-stu-id="a9411-116">Primary</span></span>  <br/> |<span data-ttu-id="a9411-117">Número de sequência para diferenciar sessões quando elas tiverem o mesmo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="a9411-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="a9411-118">**Caixa de diálogo**</span><span class="sxs-lookup"><span data-stu-id="a9411-118">**DialogID**</span></span> <br/> |<span data-ttu-id="a9411-119">varchar (256)</span><span class="sxs-lookup"><span data-stu-id="a9411-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="a9411-120">IDENTIFICAÇÃO da caixa de diálogo que é globalmente exclusiva.</span><span class="sxs-lookup"><span data-stu-id="a9411-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="a9411-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="a9411-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="a9411-122">int</span><span class="sxs-lookup"><span data-stu-id="a9411-122">int</span></span>  <br/> |<span data-ttu-id="a9411-123">dedo</span><span class="sxs-lookup"><span data-stu-id="a9411-123">index</span></span>  <br/> |<span data-ttu-id="a9411-124">Checksum da ID da caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="a9411-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

