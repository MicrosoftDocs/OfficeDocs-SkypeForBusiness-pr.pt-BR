---
title: Check-in e versão da sala nos painéis do Microsoft Teams
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
- Teams_ITAdmin_Devices
ms.topic: reference
search.appverid: MET150
description: Este artigo fornece diretrizes sobre como habilitar check-in e dispositivos de painéis do Teams de versão de sala.
ms.openlocfilehash: 31cdab94ddb6a5c6fdc017b537f446e58aa1c2c5
ms.sourcegitcommit: 6e677c7d0dfe9e380d70adaca748eea88ca95705
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/09/2022
ms.locfileid: "67298321"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Check-in e versão da sala nos painéis do Microsoft Teams

Quando o check-in e a versão da sala estão habilitados, os usuários fazem check-in nos painéis do Teams na sala reservada no início da reunião. Se um usuário não faz check-in dentro de um período definido após a hora de início da reunião, a sala de reunião recusa o convite da reunião, envia uma mensagem de cancelamento para o organizador da reunião e a sala fica disponível para que outras pessoas reservem.  

## <a name="requirements"></a>Requisitos 

Esse recurso pode ser usado em uma implantação painel do Teams autônoma. Você também pode emparelhar painéis do Teams com o Salas do Teams no Android com a versão 1449/1.0.96.2022011305 ou posterior para obter funcionalidades adicionais, como notificações de check-in.

A caixa de correio compartilhada associada ao painel do Teams precisa ter o fuso horário correto definido para que esse recurso funcione corretamente. Para obter informações sobre como definir o fuso horário para caixas de correio compartilhadas, consulte Configurações de fuso horário para caixas de correio [compartilhadas Outlook na Web](/exchange/troubleshoot/outlook-on-the-web-issues/shared-mailboxes-time-zone-setting).

## <a name="enable-check-in-and-room-release"></a>Habilitar check-in e liberação de sala 

O check-in e a liberação da sala estão desativados por padrão. Para ativá-lo,  

1. No painel do Teams, entre usando suas credenciais de administrador.  

2. Vá para **Configurações > configurações do dispositivo > Administração configurações** > de administração do Teams > Reuniões.

3. Ative a Sala de lançamento se ninguém fizer o logon.

4. Para ajustar a quantidade de tempo que os usuários precisam fazer check-in antes que a sala seja liberada, vá para Liberar depois **:** e selecione uma opção na lista suspensa.  

Quando os painéis do Teams são emparelhados com uma Sala do Teams no Android, um usuário pode fazer check-in in ingressando na reunião na Sala do Teams.  

## <a name="turn-on-check-in-notifications"></a>Ativar notificações de check-in

> [!NOTE]
> Atualmente, esse recurso só está disponível nos painéis do Teams que estão emparelhados com uma Sala do Teams no Android. A painel do Teams e a sala do Teams devem estar conectadas à mesma conta de recurso. Consulte [Emparelhar um painel do Teams com uma Sala do Microsoft Teams no Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android) para saber mais.  

As notificações de check-in são enviadas quando uma reunião continua após seu intervalo de tempo reservado. Depois que um usuário da próxima reunião fizer o logon, a notificação aparecerá na frente da sala na hora de início da reunião agendada para permitir que os participantes da reunião anterior saibam que sua reserva acabou e que as pessoas estão aguardando o espaço.  

Para ativar as notificações de check-in,  

1. No painel do Teams, entre usando suas credenciais de administrador. 

2. Vá para **Configurações > configurações do dispositivo > Administração configurações** > de administração do Teams > Reuniões.

3. Vá para **Check-in** e **ative a notificação de envio de check-in**.

## <a name="related-topics"></a>Tópicos relacionados

- [Como usar painéis do Microsoft Teams](use-teams-panels.md)

- [Painéis do Microsoft Teams](teams-panels.md)
