---
title: Tabela SIPResponseMetaData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: O SIPResponseMetaDataTable contém uma lista de códigos de resposta SIP e a classificação e definição de cada um desses códigos. Esses códigos são gerados em resposta a eventos que afetam dispositivos SIP e sessões de comunicação SIP; por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor recusa para honrar essa solicitação.
ms.openlocfilehash: 2c302793dc9f9c53d445d231a261bf43a0c385df
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2020
ms.locfileid: "41814889"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="65192-104">Tabela SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="65192-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="65192-105">O SIPResponseMetaDataTable contém uma lista de códigos de resposta SIP e a classificação e definição de cada um desses códigos.</span><span class="sxs-lookup"><span data-stu-id="65192-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="65192-106">Esses códigos são gerados em resposta a eventos que afetam dispositivos SIP e sessões de comunicação SIP; por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor recusa para honrar essa solicitação.</span><span class="sxs-lookup"><span data-stu-id="65192-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="65192-107">Esta tabela foi introduzida no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="65192-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="65192-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="65192-108">**Column**</span></span>|<span data-ttu-id="65192-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="65192-109">**Data Type**</span></span>|<span data-ttu-id="65192-110">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="65192-110">**Key/Index**</span></span>|<span data-ttu-id="65192-111">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="65192-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="65192-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="65192-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="65192-113">int</span><span class="sxs-lookup"><span data-stu-id="65192-113">int</span></span>  <br/> |<span data-ttu-id="65192-114">Primária</span><span class="sxs-lookup"><span data-stu-id="65192-114">Primary</span></span>  <br/> |<span data-ttu-id="65192-115">Valor numérico que representa o código de resposta SIP.</span><span class="sxs-lookup"><span data-stu-id="65192-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="65192-116">**Classe**</span><span class="sxs-lookup"><span data-stu-id="65192-116">**Class**</span></span> <br/> |<span data-ttu-id="65192-117">int</span><span class="sxs-lookup"><span data-stu-id="65192-117">int</span></span>  <br/> || <span data-ttu-id="65192-118">Classificação geral do código de resposta.</span><span class="sxs-lookup"><span data-stu-id="65192-118">General classification for the response code.</span></span> <span data-ttu-id="65192-119">As classificações incluem:</span><span class="sxs-lookup"><span data-stu-id="65192-119">Classifications include:</span></span> <br/>  <span data-ttu-id="65192-120">1-respostas informativas</span><span class="sxs-lookup"><span data-stu-id="65192-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="65192-121">2-respostas bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="65192-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="65192-122">3-respostas de redirecionamento</span><span class="sxs-lookup"><span data-stu-id="65192-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="65192-123">4-respostas de falha do cliente</span><span class="sxs-lookup"><span data-stu-id="65192-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="65192-124">5--respostas de falha do servidor</span><span class="sxs-lookup"><span data-stu-id="65192-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="65192-125">6-resposta de falha global</span><span class="sxs-lookup"><span data-stu-id="65192-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="65192-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="65192-126">**Description**</span></span> <br/> |<span data-ttu-id="65192-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="65192-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="65192-128">Descrição do código de resposta SIP.</span><span class="sxs-lookup"><span data-stu-id="65192-128">Description of the SIP response code.</span></span> <span data-ttu-id="65192-129">Por exemplo, o código de resposta 181 tem a seguinte descrição:</span><span class="sxs-lookup"><span data-stu-id="65192-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="65192-130">A chamada está sendo encaminhada</span><span class="sxs-lookup"><span data-stu-id="65192-130">Call Is Being Forwarded</span></span>  <br/> |
   

