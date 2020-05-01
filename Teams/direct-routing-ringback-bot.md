---
title: Configurar o bot de retoque para roteamento direto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Saiba como usar o bot de retoque para roteamento direto para evitar silêncios inesperados que podem ocorrer quando uma chamada está sendo estabelecida.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1db113a610c153f821a0d92187744e6ca34e3ce3
ms.sourcegitcommit: 69ff557c79d6b1a3d1089fe5c8f5c8ed8ff7431e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/30/2020
ms.locfileid: "43951186"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="5cd1d-103">Configurar o bot de retoque para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="5cd1d-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="5cd1d-104">Este artigo descreve o bot de retoque, que você pode usar para ajudar a evitar silêncios inesperados que podem ocorrer quando demora mais tempo para que as chamadas sejam estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="5cd1d-105">O bot de retoque está disponível para roteamento direto no modo de bypass de não mídia.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="5cd1d-106">Às vezes, as chamadas recebidas da rede de telefonia pública comutada (PSTN) para clientes do teams podem levar mais tempo do que o esperado para serem estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="5cd1d-107">Isso pode ocorrer por vários motivos.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-107">This can occur for various reasons.</span></span> <span data-ttu-id="5cd1d-108">Quando isso acontece, o chamador pode não ouvir nada, o cliente do Teams não entra em contato e a chamada pode ser cancelada por alguns provedores de telecomunicações.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and the call might be canceled by some telecommunications providers.</span></span>

<span data-ttu-id="5cd1d-109">O bot de toque ajuda a evitar silêncios inesperados que podem ocorrer nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="5cd1d-110">Para chamadas recebidas da PSTN para os clientes do Teams, o bot de toque executa um sinal de áudio distintivo para o autor para indicar que as equipes estão no processo de estabelecer a chamada.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="5cd1d-111">O bot de toque gera a mídia antecipada do backend do teams.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="5cd1d-112">Em alguns países e regiões, você poderá ser cobrado pela chamada quando a mídia começar a fluir.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="5cd1d-113">Configurar o bot de retoque</span><span class="sxs-lookup"><span data-stu-id="5cd1d-113">Configure the Ringback bot</span></span>

<span data-ttu-id="5cd1d-114">Use os cmdlets [set-CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) e [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) juntos com o parâmetro **GenerateRingingWhileLocatingUser** para configurar o bot de retoque.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-114">Use the [Set-CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) and [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlets together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot.</span></span>

<span data-ttu-id="5cd1d-115">Para ativar o bot de retorno de toque, defina o parâmetro **GenerateRingingWhileLocatingUser** como **$true**.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="5cd1d-116">Esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-116">This is the default value.</span></span> 

<span data-ttu-id="5cd1d-117">Para desativar o bot de retorno de toque, defina o parâmetro **GenerateRingingWhileLocatingUser** como **$false**.</span><span class="sxs-lookup"><span data-stu-id="5cd1d-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="5cd1d-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="5cd1d-118">Related topics</span></span>

- [<span data-ttu-id="5cd1d-119">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="5cd1d-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)