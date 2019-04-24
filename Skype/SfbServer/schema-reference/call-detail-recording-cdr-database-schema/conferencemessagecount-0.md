---
title: Exibir ConferenceMessageCount
ms.reviewer: ''
ms.author: serdars
author: SerdarSoysal
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: f2290eef7d2738831ed3ce72c794a36659858b8b
ms.sourcegitcommit: 111bf6255fa877b3fce70fa8166e8ec5a6643434
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32213708"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="8b6d7-104">Exibir ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="8b6d7-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="8b6d7-105">A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="8b6d7-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="8b6d7-107">A exibição ConferenceMessageCount contém todas as colunas na [ConferenceSessionDetails view](conferencesessiondetails.md) além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="8b6d7-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="8b6d7-108">**Column**</span></span>|<span data-ttu-id="8b6d7-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="8b6d7-109">**Data Type**</span></span>|<span data-ttu-id="8b6d7-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="8b6d7-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="8b6d7-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="8b6d7-111">**UserUri**</span></span> <br/> |<span data-ttu-id="8b6d7-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="8b6d7-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="8b6d7-113">URI do usuário que enviou a mensagem.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="8b6d7-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="8b6d7-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="8b6d7-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="8b6d7-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="8b6d7-116">Tipo de URI do usuário que enviou as mensagens.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="8b6d7-117">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8b6d7-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="8b6d7-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="8b6d7-119">Identificador exclusivo</span><span class="sxs-lookup"><span data-stu-id="8b6d7-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="8b6d7-120">Locatário do usuário que enviou as mensagens.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="8b6d7-121">Consulte a [tabela de inquilinos](tenants.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="8b6d7-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="8b6d7-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="8b6d7-123">smallint</span><span class="sxs-lookup"><span data-stu-id="8b6d7-123">smallint</span></span>  <br/> |<span data-ttu-id="8b6d7-124">Número de mensagens enviadas pelo usuário durante a sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="8b6d7-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

