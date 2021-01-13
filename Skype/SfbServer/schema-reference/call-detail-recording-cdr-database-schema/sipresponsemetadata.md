---
title: Tabela SIPResponseMetaData
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 10/20/2015
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: cf723737-4a75-4352-829b-f4954aa59716
description: O SIPResponseMetaDataTable contém uma lista de códigos de resposta SIP e a classificação e definição de cada um destes códigos. Estes códigos são gerados em resposta aos eventos que afetam dispositivos SIP e sessões de comunicação SIP. Por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor declina esta solicitação.
ms.openlocfilehash: 3d6714e9c5b5c154d19381fad33821b02ec8a73e
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49809921"
---
# <a name="sipresponsemetadata-table"></a><span data-ttu-id="3751e-104">Tabela SIPResponseMetaData</span><span class="sxs-lookup"><span data-stu-id="3751e-104">SIPResponseMetaData table</span></span>
 
<span data-ttu-id="3751e-p102">O SIPResponseMetaDataTable contém uma lista de códigos de resposta SIP e a classificação e definição de cada um destes códigos. Estes códigos são gerados em resposta aos eventos que afetam dispositivos SIP e sessões de comunicação SIP. Por exemplo, o código de resposta 403 é gerado quando um dispositivo SIP faz uma solicitação, mas o servidor declina esta solicitação.</span><span class="sxs-lookup"><span data-stu-id="3751e-p102">The SIPResponseMetaDataTable contains a list of SIP response codes and the classification and definition of each of those codes. These codes are generated in response to events affecting SIP devices and SIP communication sessions; for example, the response code 403 is generated when a SIP device makes a request, but the server declines to honor that request.</span></span>
  
<span data-ttu-id="3751e-107">Esta tabela foi introduzida no Skype for Business Server 2015.</span><span class="sxs-lookup"><span data-stu-id="3751e-107">This table was introduced in Skype for Business Server 2015.</span></span>
  
|<span data-ttu-id="3751e-108">**Coluna**</span><span class="sxs-lookup"><span data-stu-id="3751e-108">**Column**</span></span>|<span data-ttu-id="3751e-109">**Tipo de dados**</span><span class="sxs-lookup"><span data-stu-id="3751e-109">**Data Type**</span></span>|<span data-ttu-id="3751e-110">**Chave/Índice**</span><span class="sxs-lookup"><span data-stu-id="3751e-110">**Key/Index**</span></span>|<span data-ttu-id="3751e-111">**Detalhes**</span><span class="sxs-lookup"><span data-stu-id="3751e-111">**Details**</span></span>|
|:-----|:-----|:-----|:-----|
|<span data-ttu-id="3751e-112">**ResponseCode**</span><span class="sxs-lookup"><span data-stu-id="3751e-112">**ResponseCode**</span></span> <br/> |<span data-ttu-id="3751e-113">int</span><span class="sxs-lookup"><span data-stu-id="3751e-113">int</span></span>  <br/> |<span data-ttu-id="3751e-114">Primário</span><span class="sxs-lookup"><span data-stu-id="3751e-114">Primary</span></span>  <br/> |<span data-ttu-id="3751e-115">Valor numérico que representa o código de resposta SIP.</span><span class="sxs-lookup"><span data-stu-id="3751e-115">Numeric value that represents the SIP response code.</span></span>  <br/> |
|<span data-ttu-id="3751e-116">**Classe**</span><span class="sxs-lookup"><span data-stu-id="3751e-116">**Class**</span></span> <br/> |<span data-ttu-id="3751e-117">int</span><span class="sxs-lookup"><span data-stu-id="3751e-117">int</span></span>  <br/> || <span data-ttu-id="3751e-p103">Classificação geral do código de resposta. As classificações incluem:</span><span class="sxs-lookup"><span data-stu-id="3751e-p103">General classification for the response code. Classifications include:</span></span> <br/>  <span data-ttu-id="3751e-120">1 - Respostas Informativas</span><span class="sxs-lookup"><span data-stu-id="3751e-120">1 - Informational Responses</span></span> <br/>  <span data-ttu-id="3751e-121">2 - Respostas bem-sucedidas</span><span class="sxs-lookup"><span data-stu-id="3751e-121">2 - Successful Responses</span></span> <br/>  <span data-ttu-id="3751e-122">3 - Respostas de redirecionamento</span><span class="sxs-lookup"><span data-stu-id="3751e-122">3 - Redirection Responses</span></span> <br/>  <span data-ttu-id="3751e-123">4 - Respostas de falha do cliente</span><span class="sxs-lookup"><span data-stu-id="3751e-123">4 - Client Failure Responses</span></span> <br/>  <span data-ttu-id="3751e-124">5 -- Respostas de falha do servidor</span><span class="sxs-lookup"><span data-stu-id="3751e-124">5 -- Server Failure Responses</span></span> <br/>  <span data-ttu-id="3751e-125">6 - Resposta a Falhas Globais</span><span class="sxs-lookup"><span data-stu-id="3751e-125">6 - Global Failure Response</span></span> <br/> |
|<span data-ttu-id="3751e-126">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="3751e-126">**Description**</span></span> <br/> |<span data-ttu-id="3751e-127">nvarchar(256)</span><span class="sxs-lookup"><span data-stu-id="3751e-127">nvarchar(256)</span></span>  <br/> ||<span data-ttu-id="3751e-p104">Descrição do código de resposta SIP. Por exemplo, o código de resposta 181 possui a seguinte descrição:</span><span class="sxs-lookup"><span data-stu-id="3751e-p104">Description of the SIP response code. For example, response code 181 has the following description:</span></span>  <br/> <span data-ttu-id="3751e-130">A chamada está sendo encaminhada</span><span class="sxs-lookup"><span data-stu-id="3751e-130">Call Is Being Forwarded</span></span>  <br/> |
   

