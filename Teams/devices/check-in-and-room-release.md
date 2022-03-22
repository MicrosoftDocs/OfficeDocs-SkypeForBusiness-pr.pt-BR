---
title: Check-in e versão de sala em Microsoft Teams painéis
ms.author: czawideh
author: cazawideh
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
description: Este artigo fornece orientações sobre como habilitar o check-in e a versão de sala Teams painéis.
ms.openlocfilehash: 9e90916c5db4d5ec32a40f0e021f9bf7b294d09f
ms.sourcegitcommit: f8b935e009895138eddfc1ae360b7b2ace747d3c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/02/2022
ms.locfileid: "63689038"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Check-in e versão de sala em Microsoft Teams painéis

Quando o check-in e a versão da sala estão habilitados, os usuários fazem check-in Teams painéis na sala reservada no início da reunião. Se um usuário não faz check-in dentro de um período de tempo definido após o horário de início da reunião, a sala de reunião recusa o convite da reunião, envia uma mensagem de cancelamento para o organizador da reunião e a sala fica disponível para outras pessoas reservarem.  

## <a name="requirements"></a>Requisitos 

Esse recurso pode ser usado em uma implantação autônoma Teams painel. Você também pode emparelhar Teams painéis com o Salas do Teams no Android com o aplicativo versão 1449/1.0.96.2022011305 ou posterior para obter funcionalidades adicionais, como notificações de check-in.  

## <a name="enable-check-in-and-room-release"></a>Habilitar o check-in e a versão de sala 

O check-in e a versão da sala estão desligadas por padrão. Para a ativar,  

1. No painel Teams, entre usando suas credenciais de administrador.  

2. Vá para **o Configurações > de Configurações > de Configurações > De Configurações > de Painel**.

3. Ativar a sala de versão se ninguém entrar.

4. Para ajustar a quantidade de tempo que os usuários têm para fazer check-in antes da sala ser liberada, vá para **Liberar depois:** e selecione uma opção no menu suspenso.  

Quando Teams painéis são emparelhados com uma sala Teams no Android, um usuário pode fazer check-in in in-the meeting on the Teams Room.  

## <a name="turn-on-check-in-notifications"></a>Ativar notificações de check-in

> [!NOTE]
> Atualmente, esse recurso só está disponível Teams painéis que estão emparelhados com uma sala Teams no Android. O Teams e Teams sala devem ser assinados na mesma conta de recurso. Consulte [Emparelhar um Teams com uma sala Microsoft Teams no Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android) para saber mais.  

As notificações de check-in são enviadas quando uma reunião continua após seu intervalo de tempo reservado. Depois que um usuário da próxima reunião faz o logons, a notificação aparecerá na frente da sala exibida no horário de início da reunião agendada para permitir que os participantes da reunião anterior saibam que sua reserva terminou e as pessoas estão aguardando o espaço.  

Para ativar notificações de check-in,  

1. No painel Teams, entre usando suas credenciais de administrador. 

2. Vá para **o Configurações > de Configurações > de Configurações > De Configurações > de Painel**.

3. Vá para **Check-in e** ative **a notificação de check-in enviar**.

## <a name="related-topics"></a>Tópicos relacionados

- [Como usar Microsoft Teams painéis](use-teams-panels.md)

- [Microsoft Teams painéis](teams-panels.md)