---
title: Configurar o bot de retoque para roteamento direto
author: LanaChin
ms.author: v-lanac
manager: serdars
ms.topic: article
ms.reviewer: filippse
ms.service: msteams
audience: admin
description: Saiba como usar o bot de retoque para roteamento direto para evitar silêncios inesperados que podem ocorrer quando uma chamada está sendo estabelecida.
localization_priority: Normal
ms.collection:
- M365-voice
appliesto:
- Microsoft Teams
ms.openlocfilehash: 3fcb69ba1bc612fe940054ec982eb7462c6679be
ms.sourcegitcommit: a23f45ab3a2cb7b5c279356edddf61c4030c41bd
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 12/10/2019
ms.locfileid: "39962498"
---
# <a name="set-up-the-ringback-bot-for-direct-routing"></a>Configurar o bot de retoque para roteamento direto

Este artigo descreve o bot de retoque, que você pode usar para ajudar a evitar silêncios inesperados que podem ocorrer quando demora mais tempo para que as chamadas sejam estabelecidas. O bot de retoque está disponível para roteamento direto no modo de bypass de não mídia.

Às vezes, as chamadas recebidas da rede de telefonia pública comutada (PSTN) para clientes do teams podem levar mais tempo do que o esperado para serem estabelecidas. Isso pode ocorrer por vários motivos. Quando isso acontece, o chamador pode não ouvir nada, o cliente do Teams não entra em contato e a chamada pode ser cancelada por alguns provedores de telecomunicações.

O bot de toque ajuda a evitar silêncios inesperados que podem ocorrer nesse cenário. Para chamadas recebidas da PSTN para os clientes do Teams, o bot de toque executa um sinal de áudio distintivo para o autor para indicar que as equipes estão no processo de estabelecer a chamada.

> [!NOTE]
> O bot de toque gera a mídia antecipada do backend do teams. Em alguns países e regiões, você poderá ser cobrado pela chamada quando a mídia começar a fluir.

## <a name="configure-the-ringback-bot"></a>Configurar o bot de retoque

Use os cmdlets [set-CsOnlineGateway](https://docs.microsoft.com/powershell/module/skype/set-csonlinepstngateway) e [New-CsOnlinePSTNGateway](https://docs.microsoft.com/powershell/module/skype/new-csonlinepstngateway) juntos com o parâmetro **GenerateRingingWhileLocatingUser** para configurar o bot de retoque.

Para ativar o bot de retorno de toque, defina o parâmetro **GenerateRingingWhileLocatingUser** como **$true**. Esse é o valor padrão. 

Para desativar o bot de retorno de toque, defina o parâmetro **GenerateRingingWhileLocatingUser** como **$false**. 

## <a name="related-topics"></a>Tópicos relacionados

- [Visão Geral do PowerShell do Teams](teams-powershell-overview.md)