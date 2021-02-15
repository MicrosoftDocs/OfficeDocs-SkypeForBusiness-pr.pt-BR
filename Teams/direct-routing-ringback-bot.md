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
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurar o bot Ringback para Roteamento Direto

Este artigo descreve o bot Ringback, que você pode usar para ajudar a evitar silêncios inesperados que podem ocorrer quando leva mais tempo para que as chamadas sejam estabelecidas. O bot Ringback está disponível para Roteamento Direto no modo de bypass sem mídia.

Às vezes, as chamadas de entrada da rede telefônica pública comutado (PSTN) para clientes do Teams podem levar mais tempo do que o esperado para serem estabelecidas. Isso pode ocorrer por vários motivos. Quando isso acontece, o chamador pode não ouvir nada, o cliente do Teams não toca e alguns provedores de telecomunicações podem cancelar a chamada.

O bot Ringback ajuda a evitar silêncios inesperados que podem ocorrer nesse cenário. Para chamadas de entrada do PSTN para clientes do Teams, o bot Ringback reproduz um sinal de áudio distinto para o chamador para indicar que o Teams está em processo de estabelecimento da chamada.

> [!NOTE]
> O bot Ringback gera mídia antecipada a partir do back-end do Teams. Em alguns países e regiões, você pode ser cobrado pela chamada quando a mídia começar a fluir.

## <a name="configure-the-ringback-bot"></a>Configurar o bot Ringback

Use o cmdlet [Set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) para modificar uma configuração SBC (Controlador de Borda de Sessão) definida anteriormente ou o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) para criar uma nova configuração SBC, juntamente com o parâmetro **GenerateRingingWhileLocUser** para configurar o bot Ringback:

- Para ativar o bot Ringback, de definir o parâmetro **GenerateRingingWhileLocUser** **como $True.** Esse é o valor padrão. 

- Para desativar o bot Ringback, de definir o parâmetro **GenerateRingingWhileLocUser** **como $False.** 

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
