---
title: Exibição ConferenceMessageCount
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
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Esta exibição foi introduzida no Microsoft Lync Server 2013.
ms.openlocfilehash: 8394ed37d4b85e8ec5fcda4234b4c28f4276fb17
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49813291"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="5a99a-104">Exibição ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="5a99a-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="5a99a-105">A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência.</span><span class="sxs-lookup"><span data-stu-id="5a99a-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="5a99a-106">Essa exibição foi introduzida no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="5a99a-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5a99a-107">O visualização ConferenceMessageCount contém todas as colunas no visualização [ConferenceSessionDetails,](conferencesessiondetails.md) além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="5a99a-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="5a99a-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="5a99a-108">**Column**</span></span>|<span data-ttu-id="5a99a-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="5a99a-109">**Data Type**</span></span>|<span data-ttu-id="5a99a-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="5a99a-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="5a99a-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="5a99a-111">**UserUri**</span></span> <br/> |<span data-ttu-id="5a99a-112">nvarchar(450)</span><span class="sxs-lookup"><span data-stu-id="5a99a-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="5a99a-113">URI do usuário que enviou a mensagem.</span><span class="sxs-lookup"><span data-stu-id="5a99a-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="5a99a-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="5a99a-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="5a99a-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="5a99a-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="5a99a-116">Tipo de URI do usuário que enviou as mensagens.</span><span class="sxs-lookup"><span data-stu-id="5a99a-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="5a99a-117">Consulte a [tabela UriTypes para](uritypes.md) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5a99a-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="5a99a-118">**UserTenant**</span><span class="sxs-lookup"><span data-stu-id="5a99a-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="5a99a-119">uniqueidentifier</span><span class="sxs-lookup"><span data-stu-id="5a99a-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="5a99a-120">Locatário do usuário que enviou as mensagens.</span><span class="sxs-lookup"><span data-stu-id="5a99a-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="5a99a-121">Consulte a [tabela Tenants para](tenants.md) obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="5a99a-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="5a99a-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="5a99a-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="5a99a-123">smallint</span><span class="sxs-lookup"><span data-stu-id="5a99a-123">smallint</span></span>  <br/> |<span data-ttu-id="5a99a-124">Número de mensagens enviadas pelo usuário durante a sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="5a99a-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

