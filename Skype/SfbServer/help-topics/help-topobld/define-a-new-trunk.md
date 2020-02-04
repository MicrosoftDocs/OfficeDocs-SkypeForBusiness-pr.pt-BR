---
title: Definir um Novo Tronco
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
ms.date: 11/17/2018
audience: ITPro
ms.topic: article
f1.keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Você define um novo tronco de protocolo SIP fornecendo as seguintes informações:'
ms.openlocfilehash: 9de4808bc7a53aae79c2373116e74be98c7ae9ea
ms.sourcegitcommit: 19f534bfafbc74dbc2d381672b0650a3733cb982
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/03/2020
ms.locfileid: "41684834"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="ed669-103">Definir um Novo Tronco</span><span class="sxs-lookup"><span data-stu-id="ed669-103">Define a New Trunk</span></span>

<span data-ttu-id="ed669-104">Você define um novo tronco de protocolo SIP fornecendo as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="ed669-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="ed669-105">**Nome do tronco**: nome exclusivo na sua topologia que identificará esse tronco</span><span class="sxs-lookup"><span data-stu-id="ed669-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="ed669-106">**Gateway PSTN associado**: selecione um gateway PSTN implantado e configurado na sua implantação na lista</span><span class="sxs-lookup"><span data-stu-id="ed669-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="ed669-107">**Porta de escuta do gateway IP/PSTN**: porta na qual o PBX IP ou o gateway PSTN escutará.</span><span class="sxs-lookup"><span data-stu-id="ed669-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="ed669-108">Deve ser exclusivo de todas as outras portas de escuta de tronco configuradas na sua implantação</span><span class="sxs-lookup"><span data-stu-id="ed669-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="ed669-109">**Protocolo de transporte SIP**: selecione na lista o TCP ou o TLS</span><span class="sxs-lookup"><span data-stu-id="ed669-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="ed669-110">**Servidor de mediação associado**: selecione na lista um servidor de mediação que é implantado e configurado em sua implantação</span><span class="sxs-lookup"><span data-stu-id="ed669-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="ed669-111">**Porta do servidor de mediação associada**: defina o valor de porta igual ao valor de porta TCP ou TLS do servidor de mediação que o tronco SIP usará</span><span class="sxs-lookup"><span data-stu-id="ed669-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="ed669-112">Confira também</span><span class="sxs-lookup"><span data-stu-id="ed669-112">See also</span></span>

[<span data-ttu-id="ed669-113">Tronco M:N no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="ed669-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="ed669-114">Como faço para implementar o entroncamento SIP?</span><span class="sxs-lookup"><span data-stu-id="ed669-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)
