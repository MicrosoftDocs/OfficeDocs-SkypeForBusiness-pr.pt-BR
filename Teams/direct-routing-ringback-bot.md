---
title: Configurar o bot ringback para roteamento direto
author: cichur
ms.author: v-cichur
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
description: Saiba como usar o bot ringback para Roteamento Direto para evitar silêncios inesperados que podem ocorrer quando uma chamada está sendo estabelecida.
localization_priority: Normal
search.appverid: MET150
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3ec53f1d4f9cd21d3b28c87c07c1bc91d48b9b58
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51098417"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a><span data-ttu-id="83266-103">Configurar o bot ringback para roteamento direto</span><span class="sxs-lookup"><span data-stu-id="83266-103">Set up the Ringback bot for Direct Routing</span></span>

<span data-ttu-id="83266-104">Este artigo descreve o bot ringback, que você pode usar para ajudar a evitar silêncios inesperados que podem ocorrer quando as chamadas demoram mais tempo para serem estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="83266-104">This article describes the Ringback bot, which you can use to help avoid unexpected silences that can occur when it takes a longer time for calls to be established.</span></span> <span data-ttu-id="83266-105">O bot ringback está disponível para Roteamento Direto no modo de bypass de não mídia.</span><span class="sxs-lookup"><span data-stu-id="83266-105">The Ringback bot is available for Direct Routing in non-media bypass mode.</span></span>

<span data-ttu-id="83266-106">Às vezes, as chamadas de entrada da PSTN (rede telefônica pública comutado) para clientes do Teams podem demorar mais do que o esperado para serem estabelecidas.</span><span class="sxs-lookup"><span data-stu-id="83266-106">Sometimes inbound calls from the public switched telephone network (PSTN) to Teams clients can take longer than expected to be established.</span></span> <span data-ttu-id="83266-107">Isso pode ocorrer por vários motivos.</span><span class="sxs-lookup"><span data-stu-id="83266-107">This can occur for various reasons.</span></span> <span data-ttu-id="83266-108">Quando isso acontece, o chamador pode não ouvir nada, o cliente do Teams não toca e alguns provedores de telecomunicações podem cancelar a chamada.</span><span class="sxs-lookup"><span data-stu-id="83266-108">When this happens, the caller might not hear anything, the Teams client doesn't ring, and some telecommunications providers might cancel the call.</span></span>

<span data-ttu-id="83266-109">O bot ringback ajuda a evitar silêncios inesperados que podem ocorrer nesse cenário.</span><span class="sxs-lookup"><span data-stu-id="83266-109">The Ringback bot helps to avoid unexpected silences that can occur in this scenario.</span></span> <span data-ttu-id="83266-110">Para chamadas de entrada dos clientes PSTN para Teams, o bot ringback reproduz um sinal de áudio distinto para o chamador para indicar que o Teams está no processo de estabelecimento da chamada.</span><span class="sxs-lookup"><span data-stu-id="83266-110">For inbound calls from the PSTN to Teams clients, the Ringback bot plays a distinctive audio signal to the caller to indicate that Teams is in the process of establishing the call.</span></span>

> [!NOTE]
> <span data-ttu-id="83266-111">O bot ringback gera mídia inicial a partir do back-back do Teams.</span><span class="sxs-lookup"><span data-stu-id="83266-111">The Ringback bot generates early media from the Teams backend.</span></span> <span data-ttu-id="83266-112">Em alguns países e regiões, você pode ser cobrado pela chamada quando a mídia começar a fluir.</span><span class="sxs-lookup"><span data-stu-id="83266-112">In some countries and regions, you might be charged for the call when the media starts flowing.</span></span>

## <a name="configure-the-ringback-bot"></a><span data-ttu-id="83266-113">Configurar o bot ringback</span><span class="sxs-lookup"><span data-stu-id="83266-113">Configure the Ringback bot</span></span>

<span data-ttu-id="83266-114">Use o cmdlet [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) para modificar uma configuração do Controlador de Borda de Sessão (SBC) definida anteriormente ou o cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) para criar uma nova configuração SBC, juntamente com o parâmetro **GenerateRingingWhileLocatingUser** para configurar o bot ringback:</span><span class="sxs-lookup"><span data-stu-id="83266-114">Use the [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) cmdlet to modify a previously defined Session Border Controller (SBC) configuration, or the [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) cmdlet to create a new SBC configuration, together with the **GenerateRingingWhileLocatingUser** parameter to configure the Ringback bot:</span></span>

- <span data-ttu-id="83266-115">Para ativar o bot ringback, de definir o **parâmetro GenerateRingingWhileLocatingUser** como **$True**.</span><span class="sxs-lookup"><span data-stu-id="83266-115">To turn on the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$True**.</span></span> <span data-ttu-id="83266-116">Esse é o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="83266-116">This is the default value.</span></span> 

- <span data-ttu-id="83266-117">Para desativar o bot ringback, de definir o **parâmetro GenerateRingingWhileLocatingUser** como **$False**.</span><span class="sxs-lookup"><span data-stu-id="83266-117">To turn off the Ringback bot, set the **GenerateRingingWhileLocatingUser** parameter to **$False**.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="83266-118">Tópicos relacionados</span><span class="sxs-lookup"><span data-stu-id="83266-118">Related topics</span></span>

- [<span data-ttu-id="83266-119">Visão Geral do PowerShell do Teams</span><span class="sxs-lookup"><span data-stu-id="83266-119">Teams PowerShell overview</span></span>](teams-powershell-overview.md)