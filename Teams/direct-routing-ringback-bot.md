---
title: Configurar o bot Ringback para Roteamento Direto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Saiba como usar o bot Ringback para Roteamento Direto para evitar silêncios inesperados que podem ocorrer quando uma chamada está sendo estabelecida.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 91cea9183a85a804ca43464aab08f417ccaff1e8
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49827511"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="4b0c4-103">Configurar o bot Ringback para Roteamento Direto</span><span class="sxs-lookup"><span data-stu-id="4b0c4-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="4b0c4-104">Este artigo descreve o bot Ringback, que você pode usar para ajudar a evitar silêncios inesperados que podem ocorrer quando leva mais tempo para que as chamadas sejam estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="4b0c4-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="4b0c4-105">O bot Ringback está disponível para Roteamento Direto no modo de bypass sem mídia.</span><span class="sxs-lookup"><span data-stu-id="4b0c4-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="4b0c4-106">Às vezes, as chamadas de entrada da rede telefônica pública comutado (PSTN) para clientes do Teams podem levar mais tempo do que o esperado para serem estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="4b0c4-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="4b0c4-107">Isso pode ocorrer por vários motivos.</span><span class="sxs-lookup"><span data-stu-id="4b0c4-107">This can occur for various reasons.</span></span> <span data-ttu-id="4b0c4-108">Quando isso acontece, o chamador pode não ouvir nada, o cliente do Teams não toca e alguns provedores de telecomunicações podem cancelar a chamada.</span><span class="sxs-lookup"><span data-stu-id="4b0c4-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="4b0c4-109">O bot Ringback ajuda a evitar silêncios inesperados que podem ocorrer nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="4b0c4-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="4b0c4-110">Para chamadas de entrada do PSTN para clientes do Teams, o bot Ringback reproduz um sinal de áudio distinto para o chamador para indicar que o Teams está em processo de estabelecimento da chamada.</span><span class="sxs-lookup"><span data-stu-id="4b0c4-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="4b0c4-111">O bot Ringback gera mídia antecipada a partir do back-end do Teams.</span><span class="sxs-lookup"><span data-stu-id="4b0c4-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="4b0c4-112">Em alguns países e regiões, você pode ser cobrado pela chamada quando a mídia começar a fluir.</span><span class="sxs-lookup"><span data-stu-id="4b0c4-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="4b0c4-113">Configurar o bot Ringback</span><span class="sxs-lookup"><span data-stu-id="4b0c4-113">Configure the Ringback bot</span></span>

<span data-ttu-id="4b0c4-114">Use o cmdlet [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) para modificar uma configuração SBC (Controlador de Borda de Sessão) definida anteriormente ou o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) para criar uma nova configuração SBC, juntamente com o parâmetro **GenerateRingingWhileLocUser** para configurar o bot Ringback:</span><span class="sxs-lookup"><span data-stu-id="4b0c4-114">Use the [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="4b0c4-115">Para ativar o bot Ringback, de definir o parâmetro **GenerateRingingWhileLocUser** **como $True.**</span><span class="sxs-lookup"><span data-stu-id="4b0c4-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="4b0c4-116">Esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="4b0c4-116">This is the default value.</span></span> 

- <span data-ttu-id="4b0c4-117">Para desativar o bot Ringback, de definir o parâmetro **GenerateRingingWhileLocUser** **como $False.**</span><span class="sxs-lookup"><span data-stu-id="4b0c4-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="4b0c4-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="4b0c4-118">Related topics</span></span>

- [<span data-ttu-id="4b0c4-119">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="4b0c4-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)
