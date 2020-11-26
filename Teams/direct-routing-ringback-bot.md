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
ms.openlocfilehash: 26738002ab333d2490ef0dac5674a1f7cdc19efd
ms.sourcegitcommit: 8974cd7a693bc879fed8222f551fd7ce3205dd65
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49420951"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurar o bot de retoque para roteamento direto

Este artigo descreve o bot de retoque, que você pode usar para ajudar a evitar silêncios inesperados que podem ocorrer quando demora mais tempo para que as chamadas sejam estabelecidas. O bot de retoque está disponível para roteamento direto no modo de bypass de não mídia.

Às vezes, as chamadas recebidas da rede de telefonia pública comutada (PSTN) para clientes do teams podem levar mais tempo do que o esperado para serem estabelecidas. Isso pode ocorrer por vários motivos. Quando isso acontece, o chamador pode não ouvir nada, o cliente do Teams não está tocando e alguns provedores de telecomunicações podem cancelar a chamada.

O bot de toque ajuda a evitar silêncios inesperados que podem ocorrer nesse cenário. Para chamadas recebidas da PSTN para os clientes do Teams, o bot de toque executa um sinal de áudio distintivo para o autor para indicar que as equipes estão no processo de estabelecer a chamada.

> [!NOTE]
> O bot de toque gera a mídia antecipada do backend do teams. Em alguns países e regiões, você poderá ser cobrado pela chamada quando a mídia começar a fluir.

## <a name="configure-the-ringback-bot"></a>Configurar o bot de retoque

Use o cmdlet [set-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) para modificar uma configuração de controlador de borda de sessão (SBC) definida anteriormente ou o cmdlet [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) para criar uma nova configuração de SBC, juntamente com o parâmetro **GenerateRingingWhileLocatingUser** para configurar o bot de retoque:

- Para ativar o bot de retorno de toque, defina o parâmetro **GenerateRingingWhileLocatingUser** como **$true**. Esse é o valor padrão. 

- Para desativar o bot de retorno de toque, defina o parâmetro **GenerateRingingWhileLocatingUser** como **$false**. 

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)
