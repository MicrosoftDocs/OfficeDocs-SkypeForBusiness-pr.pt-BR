---
title: Exibição ConferenceMessageCount
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 3/9/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: a766e63fbca5c30cec3c3891c9ccfc2355f16d2d
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41815379"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="a0372-104">Exibição ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="a0372-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="a0372-105">A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência.</span><span class="sxs-lookup"><span data-stu-id="a0372-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="a0372-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a0372-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a0372-107">A exibição ConferenceMessageCount contém todas as colunas na [exibição ConferenceSessionDetails](conferencesessiondetails.md) , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="a0372-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="a0372-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a0372-108">**Column**</span></span>|<span data-ttu-id="a0372-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a0372-109">**Data Type**</span></span>|<span data-ttu-id="a0372-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a0372-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a0372-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="a0372-111">**UserUri**</span></span> <br/> |<span data-ttu-id="a0372-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a0372-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a0372-113">URL do usuário que enviou a mensagem.</span><span class="sxs-lookup"><span data-stu-id="a0372-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="a0372-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="a0372-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="a0372-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a0372-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a0372-116">Tipo de URI do usuário que enviou as mensagens.</span><span class="sxs-lookup"><span data-stu-id="a0372-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="a0372-117">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a0372-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a0372-118">**Userlocatário**</span><span class="sxs-lookup"><span data-stu-id="a0372-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="a0372-119">identificador</span><span class="sxs-lookup"><span data-stu-id="a0372-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="a0372-120">Locatário do usuário que enviou as mensagens.</span><span class="sxs-lookup"><span data-stu-id="a0372-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="a0372-121">Consulte a [tabela locatários](tenants.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a0372-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a0372-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="a0372-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="a0372-123">smallint</span><span class="sxs-lookup"><span data-stu-id="a0372-123">smallint</span></span>  <br/> |<span data-ttu-id="a0372-124">Número de mensagens enviadas pelo usuário durante a sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="a0372-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

