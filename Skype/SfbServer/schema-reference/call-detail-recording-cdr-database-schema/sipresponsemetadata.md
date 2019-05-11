---
title: Tabela SIPResponseMetaData
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 10/20/2015
ms.audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: O SIPResponseMetaDataTable contém uma lista dos códigos de resposta SIP e a classificação e a definição de cada um desses códigos. Esses códigos são gerados em resposta a eventos que afetam os dispositivos SIP e SIP sessões de comunicação; Por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor recusar aceitar esse pedido.
ms.openlocfilehash: edd1f4e60376b367f701864ff15d334c4d971e47
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/11/2019
ms.locfileid: "33930281"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="a7dcb-104">Tabela SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="a7dcb-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="a7dcb-105">O SIPResponseMetaDataTable contém uma lista dos códigos de resposta SIP e a classificação e a definição de cada um desses códigos.</span><span class="sxs-lookup"><span data-stu-id="a7dcb-105">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes.</span></span> <span data-ttu-id="a7dcb-106">Esses códigos são gerados em resposta a eventos que afetam os dispositivos SIP e SIP sessões de comunicação; Por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor recusar aceitar esse pedido.</span><span class="sxs-lookup"><span data-stu-id="a7dcb-106">These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="a7dcb-107">Esta tabela foi introduzida no Skype para Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="a7dcb-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="a7dcb-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="a7dcb-108">**Column**</span></span>|<span data-ttu-id="a7dcb-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="a7dcb-109">**Data Type**</span></span>|<span data-ttu-id="a7dcb-110">**Chave/índice**</span><span class="sxs-lookup"><span data-stu-id="a7dcb-110">**Key/Index**</span></span>|<span data-ttu-id="a7dcb-111">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="a7dcb-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="a7dcb-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="a7dcb-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="a7dcb-113">int</span><span class="sxs-lookup"><span data-stu-id="a7dcb-113">int</span></span>  <br/> |<span data-ttu-id="a7dcb-114">Primária</span><span class="sxs-lookup"><span data-stu-id="a7dcb-114">Primary</span></span>  <br/> |<span data-ttu-id="a7dcb-115">Valor numérico que representa o código de resposta SIP.</span><span class="sxs-lookup"><span data-stu-id="a7dcb-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="a7dcb-116">**Classe**</span><span class="sxs-lookup"><span data-stu-id="a7dcb-116">**Class**</span></span> <br/> |<span data-ttu-id="a7dcb-117">int</span><span class="sxs-lookup"><span data-stu-id="a7dcb-117">int</span></span>  <br/> || <span data-ttu-id="a7dcb-118">Classificação geral para o código de resposta.</span><span class="sxs-lookup"><span data-stu-id="a7dcb-118">General classification for the response code.</span></span> <span data-ttu-id="a7dcb-119">Classificações incluem:</span><span class="sxs-lookup"><span data-stu-id="a7dcb-119">Classifications include:</span></span> <br/>  <span data-ttu-id="a7dcb-120">1 - respostas informacionais</span><span class="sxs-lookup"><span data-stu-id="a7dcb-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="a7dcb-121">2 - respostas bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="a7dcb-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="a7dcb-122">3 - respostas de redirecionamento de</span><span class="sxs-lookup"><span data-stu-id="a7dcb-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="a7dcb-123">4 - respostas de falha de cliente</span><span class="sxs-lookup"><span data-stu-id="a7dcb-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="a7dcb-124">5-- Respostas de falha do servidor</span><span class="sxs-lookup"><span data-stu-id="a7dcb-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="a7dcb-125">6 - resposta de falha global</span><span class="sxs-lookup"><span data-stu-id="a7dcb-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="a7dcb-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="a7dcb-126">**Description**</span></span> <br/> |<span data-ttu-id="a7dcb-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="a7dcb-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="a7dcb-128">Descrição do código de resposta SIP.</span><span class="sxs-lookup"><span data-stu-id="a7dcb-128">Description of the SIP response code.</span></span> <span data-ttu-id="a7dcb-129">Por exemplo, o código de resposta 181 tem a seguinte descrição:</span><span class="sxs-lookup"><span data-stu-id="a7dcb-129">For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="a7dcb-130">Chamada está sendo encaminhada</span><span class="sxs-lookup"><span data-stu-id="a7dcb-130">Call Is Being Forwarded</span></span>  <br/> |
   

