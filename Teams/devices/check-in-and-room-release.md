---
title: Check-in e liberação de sala Microsoft Teams painéis
ms.author: dstrome
author: dstrome
manager: serdars
ms.reviewer: gary.lai
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
f1.keywords:
- NOCSH
ms.collection:
- M365-voice
ms.topic: reference
search.appverid: MET150
description: Este artigo fornece diretrizes sobre como habilitar o check-in e a versão da sala Teams de painéis.
ms.openlocfilehash: a1fc01b349a2189ab2f5ca09ff6b856338fbcdbb
ms.sourcegitcommit: 726df9ecac561bda18e349a5adab9bc85e52844d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/27/2022
ms.locfileid: "65761273"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Check-in e liberação de sala Microsoft Teams painéis

Quando o check-in e a versão da sala estão habilitados, os usuários fazem check-in Teams painéis na sala reservada no início da reunião. Se um usuário não faz check-in dentro de um período definido após a hora de início da reunião, a sala de reunião recusa o convite da reunião, envia uma mensagem de cancelamento para o organizador da reunião e a sala fica disponível para que outras pessoas reservem.  

## <a name="requirements"></a>Requisitos 

Esse recurso pode ser usado em uma implantação painel do Teams autônoma. Você também pode emparelhar painéis Teams com o Salas do Teams no Android com a versão do aplicativo 1449/1.0.96.2022011305 ou posterior para obter funcionalidades adicionais, como notificações de check-in.  

## <a name="enable-check-in-and-room-release"></a>Habilitar check-in e liberação de sala 

O check-in e a liberação da sala estão desativados por padrão. Para ativá-lo,  

1. No painel do Teams, entre usando suas credenciais de administrador.  

2. Vá para **Configurações > configurações do dispositivo > Administração configurações > Teams de administrador > Reuniões**.

3. Ative a Sala de lançamento se ninguém fizer o logon.

4. Para ajustar a quantidade de tempo que os usuários precisam fazer check-in antes que a sala seja liberada, vá para Liberar depois **:** e selecione uma opção na lista suspensa.  

Quando Teams painéis são emparelhados com uma Sala Teams no Android, um usuário pode fazer check-in in ingressando na reunião na Teams Sala.  

## <a name="turn-on-check-in-notifications"></a>Ativar notificações de check-in

> [!NOTE]
> Atualmente, esse recurso só está disponível em Teams painéis que são emparelhados com uma sala Teams no Android. As painel do Teams e Teams devem ser conectadas à mesma conta de recurso. Consulte [Emparelhar um painel do Teams com uma sala Microsoft Teams no Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android) para saber mais.  

As notificações de check-in são enviadas quando uma reunião continua após seu intervalo de tempo reservado. Depois que um usuário da próxima reunião fizer o logon, a notificação aparecerá na frente da sala na hora de início da reunião agendada para permitir que os participantes da reunião anterior saibam que sua reserva acabou e que as pessoas estão aguardando o espaço.  

Para ativar as notificações de check-in,  

1. No painel do Teams, entre usando suas credenciais de administrador. 

2. Vá para **Configurações > configurações do dispositivo > Administração configurações > Teams de administrador > Reuniões**.

3. Vá para **Check-in** e **ative a notificação de envio de check-in**.

## <a name="related-topics"></a>Tópicos relacionados

- [Como usar painéis Microsoft Teams dados](use-teams-panels.md)

- [Microsoft Teams painéis](teams-panels.md)
