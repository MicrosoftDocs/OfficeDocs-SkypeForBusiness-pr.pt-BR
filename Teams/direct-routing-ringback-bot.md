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
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurar o bot ringback para roteamento direto

Este artigo descreve o bot ringback, que você pode usar para ajudar a evitar silêncios inesperados que podem ocorrer quando as chamadas demoram mais tempo para serem estabelecidas. O bot ringback está disponível para Roteamento Direto no modo de bypass de não mídia.

Às vezes, as chamadas de entrada da PSTN (rede telefônica pública comutado) para clientes do Teams podem demorar mais do que o esperado para serem estabelecidas. Isso pode ocorrer por vários motivos. Quando isso acontece, o chamador pode não ouvir nada, o cliente do Teams não toca e alguns provedores de telecomunicações podem cancelar a chamada.

O bot ringback ajuda a evitar silêncios inesperados que podem ocorrer nesse cenário. Para chamadas de entrada dos clientes PSTN para Teams, o bot ringback reproduz um sinal de áudio distinto para o chamador para indicar que o Teams está no processo de estabelecimento da chamada.

> [!NOTE]
> O bot ringback gera mídia inicial a partir do back-back do Teams. Em alguns países e regiões, você pode ser cobrado pela chamada quando a mídia começar a fluir.

## <a name="configure-the-ringback-bot"></a>Configurar o bot ringback

Use o cmdlet [Set-CsOnlinePSTNGateway](/powershell/module/skype/set-csonlinepstngateway) para modificar uma configuração do Controlador de Borda de Sessão (SBC) definida anteriormente ou o cmdlet [New-CsOnlinePSTNGateway](/powershell/module/skype/new-csonlinepstngateway) para criar uma nova configuração SBC, juntamente com o parâmetro **GenerateRingingWhileLocatingUser** para configurar o bot ringback:

- Para ativar o bot ringback, de definir o **parâmetro GenerateRingingWhileLocatingUser** como **$True**. Esse é o valor padrão. 

- Para desativar o bot ringback, de definir o **parâmetro GenerateRingingWhileLocatingUser** como **$False**. 

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)