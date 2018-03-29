---
title: Tabela Dialog
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 2/1/2018
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: A tabela de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo de iniciação de sessão (SIP).
ms.openlocfilehash: 0380f9c7c48ff7d3b26b9ea5442fb5ac2155f785
ms.sourcegitcommit: 7d819bc9eb63bfd85f5dada09f1b8e5354c56f6b
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/28/2018
---
# <a name="dialog-table"></a><span data-ttu-id="41c46-103">Tabela Dialog</span><span class="sxs-lookup"><span data-stu-id="41c46-103">Dialog table</span></span>
 
<span data-ttu-id="41c46-104">A tabela de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo de iniciação de sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="41c46-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="41c46-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="41c46-105">**Column**</span></span>|<span data-ttu-id="41c46-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="41c46-106">**Data Type**</span></span>|<span data-ttu-id="41c46-107">**Índice de chaves /**</span><span class="sxs-lookup"><span data-stu-id="41c46-107">**Key/Index**</span></span>|<span data-ttu-id="41c46-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="41c46-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="41c46-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="41c46-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="41c46-110">datetime</span><span class="sxs-lookup"><span data-stu-id="41c46-110">datetime</span></span>  <br/> |<span data-ttu-id="41c46-111">Primária</span><span class="sxs-lookup"><span data-stu-id="41c46-111">Primary</span></span>  <br/> |<span data-ttu-id="41c46-112">Hora de quando o agente de qualidade de excelência (QoE) recebe o primeiro relatório do chamador ou o receptor.</span><span class="sxs-lookup"><span data-stu-id="41c46-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="41c46-113">Usado em conjunto com SessionSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="41c46-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="41c46-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="41c46-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="41c46-115">int</span><span class="sxs-lookup"><span data-stu-id="41c46-115">int</span></span>  <br/> |<span data-ttu-id="41c46-116">Primária</span><span class="sxs-lookup"><span data-stu-id="41c46-116">Primary</span></span>  <br/> |<span data-ttu-id="41c46-117">Número de sequência para diferenciar sessões quando tiverem o mesmo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="41c46-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="41c46-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="41c46-118">**DialogID**</span></span> <br/> |<span data-ttu-id="41c46-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="41c46-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="41c46-120">ID de diálogo que é globalmente exclusiva.</span><span class="sxs-lookup"><span data-stu-id="41c46-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="41c46-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="41c46-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="41c46-122">int</span><span class="sxs-lookup"><span data-stu-id="41c46-122">int</span></span>  <br/> |<span data-ttu-id="41c46-123">índice</span><span class="sxs-lookup"><span data-stu-id="41c46-123">index</span></span>  <br/> |<span data-ttu-id="41c46-124">Soma de verificação da ID do diálogo.</span><span class="sxs-lookup"><span data-stu-id="41c46-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

