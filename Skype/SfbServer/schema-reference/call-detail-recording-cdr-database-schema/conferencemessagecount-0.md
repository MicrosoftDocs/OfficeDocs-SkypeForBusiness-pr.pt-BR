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
localization_priority: Normal
ms.assetid: 8ee3ee95-fb78-4d4e-bcdd-6ce5a0a23b44
description: A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência. Este modo de exibição foi apresentado no Microsoft Lync Server 2013.
ms.openlocfilehash: 890a5912c6f828f614fbff89627c94c4e12ba7e1
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34296487"
---
# <a name="conferencemessagecount-view"></a><span data-ttu-id="a7586-104">Exibição ConferenceMessageCount</span><span class="sxs-lookup"><span data-stu-id="a7586-104">ConferenceMessageCount view</span></span>
 
<span data-ttu-id="a7586-105">A exibição ConferenceMessageCount armazena informações sobre quantas mensagens foram enviadas por um usuário para uma conferência.</span><span class="sxs-lookup"><span data-stu-id="a7586-105">The ConferenceMessageCount view stores information about how many messages were sent by a user to a conference.</span></span> <span data-ttu-id="a7586-106">Este modo de exibição foi apresentado no Microsoft Lync Server 2013.</span><span class="sxs-lookup"><span data-stu-id="a7586-106">This view was introduced in Microsoft Lync Server 2013.</span></span>
  
> [!NOTE]
> <span data-ttu-id="a7586-107">A exibição ConferenceMessageCount contém todas as colunas na [exibição ConferenceSessionDetails](conferencesessiondetails.md) , além das colunas listadas abaixo.</span><span class="sxs-lookup"><span data-stu-id="a7586-107">The ConferenceMessageCount view contains all of the columns in the [ConferenceSessionDetails view](conferencesessiondetails.md) in addition the columns listed below.</span></span>
  
|<span data-ttu-id="a7586-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a7586-108">**Column**</span></span>|<span data-ttu-id="a7586-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a7586-109">**Data Type**</span></span>|<span data-ttu-id="a7586-110">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a7586-110">**Details**</span></span>|
|:-----|:-----|:-----|
|<span data-ttu-id="a7586-111">**UserUri**</span><span class="sxs-lookup"><span data-stu-id="a7586-111">**UserUri**</span></span> <br/> |<span data-ttu-id="a7586-112">nvarchar (450)</span><span class="sxs-lookup"><span data-stu-id="a7586-112">nvarchar(450)</span></span>  <br/> |<span data-ttu-id="a7586-113">URL do usuário que enviou a mensagem.</span><span class="sxs-lookup"><span data-stu-id="a7586-113">URI of the user who sent the message.</span></span>  <br/> |
|<span data-ttu-id="a7586-114">**UserUriType**</span><span class="sxs-lookup"><span data-stu-id="a7586-114">**UserUriType**</span></span> <br/> |<span data-ttu-id="a7586-115">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a7586-115">nvarchar(256)</span></span>  <br/> |<span data-ttu-id="a7586-116">Tipo de URI do usuário que enviou as mensagens.</span><span class="sxs-lookup"><span data-stu-id="a7586-116">Type of URI of the user who sent the messages.</span></span> <span data-ttu-id="a7586-117">Consulte a [tabela UriTypes](uritypes.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a7586-117">See the [UriTypes table](uritypes.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a7586-118">**Userlocatário**</span><span class="sxs-lookup"><span data-stu-id="a7586-118">**UserTenant**</span></span> <br/> |<span data-ttu-id="a7586-119">identificador</span><span class="sxs-lookup"><span data-stu-id="a7586-119">uniqueidentifier</span></span>  <br/> |<span data-ttu-id="a7586-120">Locatário do usuário que enviou as mensagens.</span><span class="sxs-lookup"><span data-stu-id="a7586-120">Tenant of user who sent the messages.</span></span> <span data-ttu-id="a7586-121">Consulte a [tabela locatários](tenants.md) para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="a7586-121">See the [Tenants table](tenants.md) for more information.</span></span> <br/> |
|<span data-ttu-id="a7586-122">**UserMessageCount**</span><span class="sxs-lookup"><span data-stu-id="a7586-122">**UserMessageCount**</span></span> <br/> |<span data-ttu-id="a7586-123">smallint</span><span class="sxs-lookup"><span data-stu-id="a7586-123">smallint</span></span>  <br/> |<span data-ttu-id="a7586-124">Número de mensagens enviadas pelo usuário durante a sessão de conferência.</span><span class="sxs-lookup"><span data-stu-id="a7586-124">Number of messages sent by the user during the conference session.</span></span>  <br/> |
   

