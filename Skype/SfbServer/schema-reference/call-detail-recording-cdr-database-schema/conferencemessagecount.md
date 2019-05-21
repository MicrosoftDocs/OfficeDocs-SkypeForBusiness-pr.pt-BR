---
title: Tabela ConferenceMessageCount no Skype for Business Server 2015
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 78569dbf-5217-42fa-ba1a-4380f56e2a3d
description: Cada registro nessa tabela representa um usuário em uma conferência de mensagem instantânea e inclui o número de mensagens enviadas por esse usuário. Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.
ms.openlocfilehash: ef343536c34b3bd27d71ee37813e4b4e65156094
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296452"
---
# <a name="conferencemessagecount-table-in-skype-for-business-server-2015"></a><span data-ttu-id="dd6d0-104">Tabela ConferenceMessageCount no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="dd6d0-104">ConferenceMessageCount table in Skype for Business Server 2015</span></span>
 
<span data-ttu-id="dd6d0-105">Cada registro nessa tabela representa um usuário em uma conferência de mensagem instantânea e inclui o número de mensagens enviadas por esse usuário.</span><span class="sxs-lookup"><span data-stu-id="dd6d0-105">Each record in this table represents one user in one IM conference and includes the number of messages sent by that user.</span></span> <span data-ttu-id="dd6d0-106">Cada conferência é representada por vários registros nesta tabela; um registro para cada usuário.</span><span class="sxs-lookup"><span data-stu-id="dd6d0-106">Each conference is represented by multiple records in this table; one record for each user.</span></span>
  
|<span data-ttu-id="dd6d0-107">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="dd6d0-107">**Column**</span></span>|<span data-ttu-id="dd6d0-108">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="dd6d0-108">**Data Type**</span></span>|<span data-ttu-id="dd6d0-109">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="dd6d0-109">**Key/Index**</span></span>|<span data-ttu-id="dd6d0-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="dd6d0-110">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="dd6d0-111">**Id_da_sessãotime**</span><span class="sxs-lookup"><span data-stu-id="dd6d0-111">**SessionIdTime**</span></span> <br/> |<span data-ttu-id="dd6d0-112">datetime</span><span class="sxs-lookup"><span data-stu-id="dd6d0-112">datetime</span></span>  <br/> |<span data-ttu-id="dd6d0-113">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="dd6d0-113">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="dd6d0-114">Hora da ocorrência da conferência.</span><span class="sxs-lookup"><span data-stu-id="dd6d0-114">Time of conference instance.</span></span> <span data-ttu-id="dd6d0-115">Usado em conjunto com **SessionIdSeq** para identificar uma instância de conferência de maneira exclusiva.</span><span class="sxs-lookup"><span data-stu-id="dd6d0-115">Used in conjunction with **SessionIdSeq** to uniquely identify a conference instance.</span></span> <span data-ttu-id="dd6d0-116">Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="dd6d0-116">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="dd6d0-117">**SessionIdSeq**</span><span class="sxs-lookup"><span data-stu-id="dd6d0-117">**SessionIdSeq**</span></span> <br/> |<span data-ttu-id="dd6d0-118">int</span><span class="sxs-lookup"><span data-stu-id="dd6d0-118">int</span></span>  <br/> |<span data-ttu-id="dd6d0-119">Primário, estrangeiro</span><span class="sxs-lookup"><span data-stu-id="dd6d0-119">Primary, Foreign</span></span>  <br/> |<span data-ttu-id="dd6d0-120">Número de identificação para identificar a instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="dd6d0-120">ID number to identify the conference instance.</span></span> <span data-ttu-id="dd6d0-121">Usado em conjunto com \*\*\*\* a identificação_da_sessãotime para identificar exclusivamente uma instância de conferência.</span><span class="sxs-lookup"><span data-stu-id="dd6d0-121">Used in conjunction with **SessionIdTime** to uniquely identify a conference instance.</span></span> <span data-ttu-id="dd6d0-122">Consulte a [tabela conferências no Skype for Business Server 2015](conferences.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="dd6d0-122">See the [Conferences table in Skype for Business Server 2015](conferences.md) for more information.</span></span> <br/> |
|<span data-ttu-id="dd6d0-123">**ID**</span><span class="sxs-lookup"><span data-stu-id="dd6d0-123">**UserId**</span></span> <br/> |<span data-ttu-id="dd6d0-124">int</span><span class="sxs-lookup"><span data-stu-id="dd6d0-124">int</span></span>  <br/> |<span data-ttu-id="dd6d0-125">Exterior</span><span class="sxs-lookup"><span data-stu-id="dd6d0-125">Foreign</span></span>  <br/> |<span data-ttu-id="dd6d0-126">Número exclusivo que identifica esse usuário, referenciado pela [tabela usuários](users.md).</span><span class="sxs-lookup"><span data-stu-id="dd6d0-126">Unique number identifying this user, referenced from the [Users table](users.md).</span></span>  <br/> |
|<span data-ttu-id="dd6d0-127">**MessageCount**</span><span class="sxs-lookup"><span data-stu-id="dd6d0-127">**MessageCount**</span></span> <br/> |<span data-ttu-id="dd6d0-128">smallint</span><span class="sxs-lookup"><span data-stu-id="dd6d0-128">smallint</span></span>  <br/> | <br/> |<span data-ttu-id="dd6d0-129">O número de mensagens enviadas por este usuário durante esta conferência.</span><span class="sxs-lookup"><span data-stu-id="dd6d0-129">The number of messages sent by this user during this conference.</span></span>  <br/> |
   

