---
title: Definir um Novo Tronco
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- CSH
ms.custom:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Defina um novo tronco SIP (session initiation protocol) fornecendo as seguintes informações:'
ms.openlocfilehash: 1b58da8880c65b0beecbd2756d0b5a5028f45e19
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51095585"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="6037d-103">Definir um Novo Tronco</span><span class="sxs-lookup"><span data-stu-id="6037d-103">Define a New Trunk</span></span>

<span data-ttu-id="6037d-104">Defina um novo tronco SIP (session initiation protocol) fornecendo as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="6037d-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="6037d-105">**Nome do tronco**: nome exclusivo em sua topologia que identificará esse tronco</span><span class="sxs-lookup"><span data-stu-id="6037d-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="6037d-106">**Gateway PSTN Associado**: selecione na lista um gateway PSTN implantado e configurado em sua implantação</span><span class="sxs-lookup"><span data-stu-id="6037d-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="6037d-p101">**Porta de escuta para o gateway IP/PSTN**: porta na qual o gateway IP-PBX ou PSTN escutará. Precisa ser exclusiva, diferente de todas as outras portas de escuta de tronco configuradas em sua implantação</span><span class="sxs-lookup"><span data-stu-id="6037d-p101">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on. Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="6037d-109">**Protocolo de Transporte SIP**: selecione na lista TCP ou TLS.</span><span class="sxs-lookup"><span data-stu-id="6037d-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="6037d-110">**Servidor de Mediação Associado**: selecione na lista um Servidor de Mediação implantado e configurado em sua implantação</span><span class="sxs-lookup"><span data-stu-id="6037d-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="6037d-111">**Porta do Servidor de Mediação** Associada : defina o valor da porta igual ao valor da porta TCP ou TLS do Servidor de Mediação que este tronco SIP usará</span><span class="sxs-lookup"><span data-stu-id="6037d-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="6037d-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="6037d-112">See also</span></span>

[<span data-ttu-id="6037d-113">Tronco M:N no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="6037d-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="6037d-114">Como implementar tronco SIP?</span><span class="sxs-lookup"><span data-stu-id="6037d-114">How do I implement SIP trunking?</span></span>](/previous-versions/office/lync-server-2013/lync-server-2013-how-do-i-implement-sip-trunking)