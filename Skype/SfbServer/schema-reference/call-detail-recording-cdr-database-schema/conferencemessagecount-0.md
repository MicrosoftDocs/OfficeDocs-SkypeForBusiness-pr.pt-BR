---
title: Exibir ConferenceMessageCount
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Este modo de exibição foi introduzido no Microsoft Lync Server 2013.
ms.openlocfilehash: ce94cd13637b70b87a92fd688ca8ce8aefd2c69e
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33901412"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="6c318-104">Exibir ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="6c318-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="6c318-105">A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência.</span><span class="sxs-lookup"><span data-stu-id="6c318-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="6c318-106">Este modo de exibição foi introduzido no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="6c318-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6c318-107">A exibição ConferenceMessageCount contém todas as colunas na [ConferenceSessionDetails view](conferencesessiondetails.md) além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="6c318-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="6c318-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="6c318-108">**Column**</span></span>|<span data-ttu-id="6c318-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="6c318-109">**Data Type**</span></span>|<span data-ttu-id="6c318-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="6c318-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="6c318-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="6c318-111">**UserUri**</span></span> <br/> |<span data-ttu-id="6c318-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="6c318-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="6c318-113">URI do usuário que enviou a mensagem.</span><span class="sxs-lookup"><span data-stu-id="6c318-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="6c318-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="6c318-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="6c318-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="6c318-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="6c318-116">Tipo de URI do usuário que enviou as mensagens.</span><span class="sxs-lookup"><span data-stu-id="6c318-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="6c318-117">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6c318-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6c318-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="6c318-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="6c318-119">Identificador exclusivo</span><span class="sxs-lookup"><span data-stu-id="6c318-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="6c318-120">Locatário do usuário que enviou as mensagens.</span><span class="sxs-lookup"><span data-stu-id="6c318-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="6c318-121">Consulte a [tabela de inquilinos](tenants.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6c318-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="6c318-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="6c318-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="6c318-123">smallint</span><span class="sxs-lookup"><span data-stu-id="6c318-123">smallint</span></span>  <br/> |<span data-ttu-id="6c318-124">Número de mensagens enviadas pelo usuário durante a sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="6c318-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

