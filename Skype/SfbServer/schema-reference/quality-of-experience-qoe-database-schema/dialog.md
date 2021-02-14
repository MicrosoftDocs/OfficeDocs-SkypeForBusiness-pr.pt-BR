---
title: Tabela Dialog
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 2/1/2018
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 4d93424f-9072-43f5-83c2-3d539e3e9ca6
description: A tabela da Caixa de Diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo SIP.
ms.openlocfilehash: 05d9519c9aef20b8c82d904a9d5718a4de8c092c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49815841"
---
# <a name="dialog-table"></a><span data-ttu-id="baa26-103">Tabela Dialog</span><span class="sxs-lookup"><span data-stu-id="baa26-103">Dialog table</span></span>
 
<span data-ttu-id="baa26-104">A tabela da Caixa de Diálogo é uma tabela de suporte; cada registro representa uma caixa de diálogo de protocolo SIP.</span><span class="sxs-lookup"><span data-stu-id="baa26-104">The Dialog table is a supporting table; each record represents one Session Initiation Protocol (SIP) dialog.</span></span>
  
|<span data-ttu-id="baa26-105">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="baa26-105">**Column**</span></span>|<span data-ttu-id="baa26-106">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="baa26-106">**Data Type**</span></span>|<span data-ttu-id="baa26-107">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="baa26-107">**Key/Index**</span></span>|<span data-ttu-id="baa26-108">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="baa26-108">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="baa26-109">**ConferenceDateTime**</span><span class="sxs-lookup"><span data-stu-id="baa26-109">**ConferenceDateTime**</span></span> <br/> |<span data-ttu-id="baa26-110">datetime</span><span class="sxs-lookup"><span data-stu-id="baa26-110">datetime</span></span>  <br/> |<span data-ttu-id="baa26-111">Primário</span><span class="sxs-lookup"><span data-stu-id="baa26-111">Primary</span></span>  <br/> |<span data-ttu-id="baa26-p101">Horário em que o agente de QoE (Qualidade de Excelência) recebe o primeiro relatório do chamador ou receptor. Usado em conjunto com SessionSeq para identificar exclusivamente uma sessão.</span><span class="sxs-lookup"><span data-stu-id="baa26-p101">Time when the Quality of Excellence (QoE) agent receives the first report from either caller or callee. Used in conjunction with SessionSeq to uniquely identify a session.</span></span>  <br/> |
|<span data-ttu-id="baa26-114">**SessionSeq**</span><span class="sxs-lookup"><span data-stu-id="baa26-114">**SessionSeq**</span></span> <br/> |<span data-ttu-id="baa26-115">int</span><span class="sxs-lookup"><span data-stu-id="baa26-115">int</span></span>  <br/> |<span data-ttu-id="baa26-116">Primário</span><span class="sxs-lookup"><span data-stu-id="baa26-116">Primary</span></span>  <br/> |<span data-ttu-id="baa26-117">Número de sequência para diferenciar sessões quando tiverem o mesmo ConferenceDateTime.</span><span class="sxs-lookup"><span data-stu-id="baa26-117">Sequence number to differentiate sessions when they have the same ConferenceDateTime.</span></span>  <br/> |
|<span data-ttu-id="baa26-118">**DialogID**</span><span class="sxs-lookup"><span data-stu-id="baa26-118">**DialogID**</span></span> <br/> |<span data-ttu-id="baa26-119">varchar(256)</span><span class="sxs-lookup"><span data-stu-id="baa26-119">varchar(256)</span></span>  <br/> ||<span data-ttu-id="baa26-120">ID da caixa de diálogo que é globalmente exclusiva.</span><span class="sxs-lookup"><span data-stu-id="baa26-120">Dialog ID which is globally unique.</span></span>  <br/> |
|<span data-ttu-id="baa26-121">**DialogIDChecksum**</span><span class="sxs-lookup"><span data-stu-id="baa26-121">**DialogIDChecksum**</span></span> <br/> |<span data-ttu-id="baa26-122">int</span><span class="sxs-lookup"><span data-stu-id="baa26-122">int</span></span>  <br/> |<span data-ttu-id="baa26-123">index</span><span class="sxs-lookup"><span data-stu-id="baa26-123">index</span></span>  <br/> |<span data-ttu-id="baa26-124">Soma de verificação da ID da Caixa de Diálogo.</span><span class="sxs-lookup"><span data-stu-id="baa26-124">Checksum of the Dialog ID.</span></span>  <br/> |
   

