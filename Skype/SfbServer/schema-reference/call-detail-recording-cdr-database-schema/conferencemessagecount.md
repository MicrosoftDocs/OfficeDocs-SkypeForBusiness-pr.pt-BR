---
title: Tabela ConferenceMessageCount Skype para Business Server 2015
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro desta tabela representa um usuário em uma conferência de mensagem Instantânea e inclui o número de mensagens enviadas pelo usuário. Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.
ms.openlocfilehash: 60fa79de17c2db14116bd0ffe211e25a61ec9136
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213274"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="227b8-104">Tabela ConferenceMessageCount Skype para Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="227b8-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="227b8-105">Cada registro desta tabela representa um usuário em uma conferência de mensagem Instantânea e inclui o número de mensagens enviadas pelo usuário.</span><span class="sxs-lookup"><span data-stu-id="227b8-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="227b8-106">Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="227b8-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="227b8-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="227b8-107">**Column**</span></span>|<span data-ttu-id="227b8-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="227b8-108">**Data Type**</span></span>|<span data-ttu-id="227b8-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="227b8-109">**Key/Index**</span></span>|<span data-ttu-id="227b8-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="227b8-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="227b8-111">**SessionIdTime**</span><span class="sxs-lookup"><span data-stu-id="227b8-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="227b8-112">datetime</span><span class="sxs-lookup"><span data-stu-id="227b8-112">datetime</span></span>  <br/> |<span data-ttu-id="227b8-113">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="227b8-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="227b8-114">Hora da ocorrência de conferência.</span><span class="sxs-lookup"><span data-stu-id="227b8-114">Time of conference instance.</span></span> <span data-ttu-id="227b8-115">Usado em conjunto com **SessionIdSeq** para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="227b8-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="227b8-116">Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="227b8-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="227b8-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="227b8-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="227b8-118">int</span><span class="sxs-lookup"><span data-stu-id="227b8-118">int</span></span>  <br/> |<span data-ttu-id="227b8-119">Primária, estrangeira</span><span class="sxs-lookup"><span data-stu-id="227b8-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="227b8-120">Número de identificação para identificar a instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="227b8-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="227b8-121">Usado em conjunto com **SessionIdTime** para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="227b8-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="227b8-122">Consulte a [tabela de conferências em Skype para Business Server 2015](conferences.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="227b8-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="227b8-123">**UserId**</span><span class="sxs-lookup"><span data-stu-id="227b8-123">**UserId**</span></span> <br/> |<span data-ttu-id="227b8-124">int</span><span class="sxs-lookup"><span data-stu-id="227b8-124">int</span></span>  <br/> |<span data-ttu-id="227b8-125">Externa</span><span class="sxs-lookup"><span data-stu-id="227b8-125">Foreign</span></span>  <br/> |<span data-ttu-id="227b8-126">Número exclusivo que identifica este usuário, referenciado de [Users table](users.md).</span><span class="sxs-lookup"><span data-stu-id="227b8-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="227b8-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="227b8-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="227b8-128">smallint</span><span class="sxs-lookup"><span data-stu-id="227b8-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="227b8-129">O número de mensagens enviadas por esse usuário durante esta conferência.</span><span class="sxs-lookup"><span data-stu-id="227b8-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

