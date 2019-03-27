---
title: Tabela Dialog
ms.reviewer: ''
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
ms.openlocfilehash: 017da65154d12c89aeed63ea59269639d23b2129
ms.sourcegitcommit: da8c037bb30abf5d5cf3b60d4b71e3a10e553402
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/27/2019
ms.locfileid: "30876624"
---
# <a name="dialog-table"></a><span data-ttu-id="adb5a-103">Tabela Dialog</span><span class="sxs-lookup"><span data-stu-id="adb5a-103">Dialog table</span></span>
 
<span data-ttu-id="adb5a-104">A tabela de diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo de iniciação de sessão (SIP).</span><span class="sxs-lookup"><span data-stu-id="adb5a-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="adb5a-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="adb5a-105">**Column**</span></span>|<span data-ttu-id="adb5a-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="adb5a-106">**Data Type**</span></span>|<span data-ttu-id="adb5a-107">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="adb5a-107">**Key/Index**</span></span>|<span data-ttu-id="adb5a-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="adb5a-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="adb5a-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="adb5a-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="adb5a-110">datetime</span><span class="sxs-lookup"><span data-stu-id="adb5a-110">datetime</span></span>  <br/> |<span data-ttu-id="adb5a-111">Primária</span><span class="sxs-lookup"><span data-stu-id="adb5a-111">Primary</span></span>  <br/> |<span data-ttu-id="adb5a-112">Hora de quando o agente de qualidade de excelência (QoE) recebe o primeiro relatório do chamador ou o receptor.</span><span class="sxs-lookup"><span data-stu-id="adb5a-112">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee.</span></span> <span data-ttu-id="adb5a-113">Usado em conjunto com SessionSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="adb5a-113">Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="adb5a-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="adb5a-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="adb5a-115">int</span><span class="sxs-lookup"><span data-stu-id="adb5a-115">int</span></span>  <br/> |<span data-ttu-id="adb5a-116">Primária</span><span class="sxs-lookup"><span data-stu-id="adb5a-116">Primary</span></span>  <br/> |<span data-ttu-id="adb5a-117">Número de sequência para diferenciar sessões quando tiverem o mesmo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="adb5a-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="adb5a-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="adb5a-118">**DialogID**</span></span> <br/> |<span data-ttu-id="adb5a-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="adb5a-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="adb5a-120">ID de diálogo que é globalmente exclusiva.</span><span class="sxs-lookup"><span data-stu-id="adb5a-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="adb5a-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="adb5a-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="adb5a-122">int</span><span class="sxs-lookup"><span data-stu-id="adb5a-122">int</span></span>  <br/> |<span data-ttu-id="adb5a-123">índice</span><span class="sxs-lookup"><span data-stu-id="adb5a-123">index</span></span>  <br/> |<span data-ttu-id="adb5a-124">Soma de verificação da ID do diálogo.</span><span class="sxs-lookup"><span data-stu-id="adb5a-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

