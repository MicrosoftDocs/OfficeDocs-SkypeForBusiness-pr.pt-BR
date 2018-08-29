---
title: Definir um novo tronco
ms.author: heidip
author: microsoftheidi
manager: serdars
ms.date: 11/17/2018
ms.audience: ITPro
ms.topic: article
f1_keywords:
- ms.lync.tb.AddTrunkPage
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: e5d97b27-5ae8-41e0-8ee9-0c3f6d5dd123
description: 'Você pode definir um tronco de (SIP) do protocolo de iniciação de nova sessão, fornecendo as seguintes informações:'
ms.openlocfilehash: 7c9675989b6282e7af5aa117213093cf55ae583b
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/28/2018
ms.locfileid: "23250826"
---
# <a name="define-a-new-trunk"></a><span data-ttu-id="10f1d-103">Definir um novo tronco</span><span class="sxs-lookup"><span data-stu-id="10f1d-103">Define a New Trunk</span></span>

<span data-ttu-id="10f1d-104">Você pode definir um tronco de (SIP) do protocolo de iniciação de nova sessão, fornecendo as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="10f1d-104">You define a new session initiation protocol (SIP) trunk by providing the following information:</span></span>

- <span data-ttu-id="10f1d-105">**Nome do tronco**: nome exclusivo na sua topologia que identificará esse tronco</span><span class="sxs-lookup"><span data-stu-id="10f1d-105">**Trunk name**: unique name in your topology that will identify this trunk</span></span>

- <span data-ttu-id="10f1d-106">**Gateway de PSTN associado**: selecione um gateway PSTN implantado e configurado em sua implantação da lista</span><span class="sxs-lookup"><span data-stu-id="10f1d-106">**Associated PSTN Gateway**: select a deployed and configured PSTN gateway in your deployment from the list</span></span>

- <span data-ttu-id="10f1d-107">**Porta de escuta do gateway IP/PSTN**: porta na qual o gateway IP-PBX ou PSTN escutará.</span><span class="sxs-lookup"><span data-stu-id="10f1d-107">**Listening port for the IP/PSTN gateway**: port that the IP-PBX or PSTN gateway will listen on.</span></span> <span data-ttu-id="10f1d-108">Deve ser exclusivo de todos os outras tronco portas de escuta configuradas em sua implantação</span><span class="sxs-lookup"><span data-stu-id="10f1d-108">Must be unique from all other trunk listening ports configured in your deployment</span></span>

- <span data-ttu-id="10f1d-109">**Protocolo de transporte SIP**: selecione na lista TCP ou TLS</span><span class="sxs-lookup"><span data-stu-id="10f1d-109">**SIP Transport Protocol**: select from the list either TCP or TLS</span></span>

- <span data-ttu-id="10f1d-110">**Servidor de mediação associado**: selecione na lista um servidor de mediação que é implantado e configurado em sua implantação</span><span class="sxs-lookup"><span data-stu-id="10f1d-110">**Associated Mediation Server**: select from the list a Mediation Server that is deployed and configured in your deployment</span></span>

- <span data-ttu-id="10f1d-111">**Porta do servidor de mediação associado**: defina o valor da porta igual ao valor de porta TCP ou TLS do servidor de mediação que usará esse tronco SIP</span><span class="sxs-lookup"><span data-stu-id="10f1d-111">**Associated Mediation Server port**: set the port value equal to the TCP or TLS port value of the Mediation Server that this SIP trunk will use</span></span>

## <a name="see-also"></a><span data-ttu-id="10f1d-112">Consulte também</span><span class="sxs-lookup"><span data-stu-id="10f1d-112">See also</span></span>

[<span data-ttu-id="10f1d-113">Tronco M:N no Skype for Business Server 2015</span><span class="sxs-lookup"><span data-stu-id="10f1d-113">M:N trunk in Skype for Business Server 2015</span></span>](../../plan-your-deployment/enterprise-voice-solution/m-n-trunk.md)

[<span data-ttu-id="10f1d-114">Como implementar tronco SIP?</span><span class="sxs-lookup"><span data-stu-id="10f1d-114">How do I implement SIP trunking?</span></span>](https://technet.microsoft.com/library/273a22b1-8a4c-4187-acf8-c57d5c6598ce.aspx)