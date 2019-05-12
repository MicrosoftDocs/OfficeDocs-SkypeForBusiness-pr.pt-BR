---
title: Tabela Dialog
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: A tabela de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo de iniciação de sessão (SIP).
ms.openlocfilehash: 36ab76d147673ca85371ca4cdfb151fa953e29b2
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33920086"
---
# <a name="dialog-table"></a><span data-ttu-id="4738c-103">Tabela Dialog</span><span class="sxs-lookup"><span data-stu-id="4738c-103">Dialog table</span></span>
 
<span data-ttu-id="4738c-104">A tabela de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo de iniciação de sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="4738c-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="4738c-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="4738c-105">**Column**</span></span>|<span data-ttu-id="4738c-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="4738c-106">**Data Type**</span></span>|<span data-ttu-id="4738c-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="4738c-107">**Key/Index**</span></span>|<span data-ttu-id="4738c-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="4738c-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="4738c-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="4738c-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="4738c-110">datetime</span><span class="sxs-lookup"><span data-stu-id="4738c-110">datetime</span></span>  <br/> |<span data-ttu-id="4738c-111">Primária</span><span class="sxs-lookup"><span data-stu-id="4738c-111">Primary</span></span>  <br/> |<span data-ttu-id="4738c-112">Hora de quando o agente de qualidade de excelência (QoE) recebe o primeiro relatório do chamador ou o receptor.</span><span class="sxs-lookup"><span data-stu-id="4738c-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="4738c-113">Usado em conjunto com SessionSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="4738c-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="4738c-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="4738c-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="4738c-115">int</span><span class="sxs-lookup"><span data-stu-id="4738c-115">int</span></span>  <br/> |<span data-ttu-id="4738c-116">Primária</span><span class="sxs-lookup"><span data-stu-id="4738c-116">Primary</span></span>  <br/> |<span data-ttu-id="4738c-117">Número de sequência para diferenciar sessões quando tiverem o mesmo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="4738c-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="4738c-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="4738c-118">**DialogID**</span></span> <br/> |<span data-ttu-id="4738c-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="4738c-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="4738c-120">ID de diálogo que é globalmente exclusiva.</span><span class="sxs-lookup"><span data-stu-id="4738c-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="4738c-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="4738c-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="4738c-122">int</span><span class="sxs-lookup"><span data-stu-id="4738c-122">int</span></span>  <br/> |<span data-ttu-id="4738c-123">índice</span><span class="sxs-lookup"><span data-stu-id="4738c-123">index</span></span>  <br/> |<span data-ttu-id="4738c-124">Soma de verificação da ID do diálogo.</span><span class="sxs-lookup"><span data-stu-id="4738c-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

