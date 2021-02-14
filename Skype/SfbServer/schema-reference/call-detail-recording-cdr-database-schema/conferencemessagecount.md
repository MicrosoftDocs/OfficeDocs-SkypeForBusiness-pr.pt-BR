---
title: Tabela ConferenceMessageCount no Skype for Business Server 2015
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
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro nesta tabela representa um usuário em uma conferência de IM e inclui o número de mensagens enviadas por esse usuário. Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.
ms.openlocfilehash: b931b45915fc12fb01ea36f81bee62f36914e903
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813271"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="8a138-104">Tabela ConferenceMessageCount no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="8a138-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="8a138-105">Cada registro nesta tabela representa um usuário em uma conferência de IM e inclui o número de mensagens enviadas por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="8a138-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="8a138-106">Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="8a138-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="8a138-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8a138-107">**Column**</span></span>|<span data-ttu-id="8a138-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="8a138-108">**Data Type**</span></span>|<span data-ttu-id="8a138-109">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="8a138-109">**Key/Index**</span></span>|<span data-ttu-id="8a138-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="8a138-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="8a138-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="8a138-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="8a138-112">datetime</span><span class="sxs-lookup"><span data-stu-id="8a138-112">datetime</span></span>  <br/> |<span data-ttu-id="8a138-113">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="8a138-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="8a138-114">Hora da instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="8a138-114">Time of conference instance.</span></span> <span data-ttu-id="8a138-115">Usado em conjunto com **SessionIdSeq para** identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="8a138-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="8a138-116">Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="8a138-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8a138-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="8a138-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="8a138-118">int</span><span class="sxs-lookup"><span data-stu-id="8a138-118">int</span></span>  <br/> |<span data-ttu-id="8a138-119">Primário, externo</span><span class="sxs-lookup"><span data-stu-id="8a138-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="8a138-120">Número de ID para identificar a instância da conferência.</span><span class="sxs-lookup"><span data-stu-id="8a138-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="8a138-121">Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="8a138-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="8a138-122">Consulte a [tabela Conferências no Skype for Business Server 2015](conferences.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="8a138-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8a138-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="8a138-123">**UserId**</span></span> <br/> |<span data-ttu-id="8a138-124">int</span><span class="sxs-lookup"><span data-stu-id="8a138-124">int</span></span>  <br/> |<span data-ttu-id="8a138-125">Externo</span><span class="sxs-lookup"><span data-stu-id="8a138-125">Foreign</span></span>  <br/> |<span data-ttu-id="8a138-126">Número exclusivo que identifica esse usuário, referenciado na [tabela Usuários.](users.md)</span><span class="sxs-lookup"><span data-stu-id="8a138-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="8a138-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="8a138-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="8a138-128">smallint</span><span class="sxs-lookup"><span data-stu-id="8a138-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="8a138-129">O número de mensagens enviadas por esse usuário durante a conferência.</span><span class="sxs-lookup"><span data-stu-id="8a138-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

