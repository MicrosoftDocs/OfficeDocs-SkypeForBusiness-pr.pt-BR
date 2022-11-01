---
title: Entrada e liberação de sala nos painéis do Microsoft Teams
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
description: Este artigo fornece diretrizes sobre como habilitar o check-in e a versão da sala dispositivos de painéis do Teams.
ms.openlocfilehash: d5998049faf1e3c8c25b3e49470291bb20f97eea
ms.sourcegitcommit: ab8f8e101e41774668b5e607fa72442105ca796e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/01/2022
ms.locfileid: "68801852"
---
# <a name="check-in-and-room-release-on-microsoft-teams-panels"></a>Entrada e liberação de sala nos painéis do Microsoft Teams

Quando o check-in e a versão da sala estão habilitados, os usuários fazem check-in nos painéis do Teams na sala reservada no início da reunião. Se um usuário não fizer check-in dentro de um tempo definido após o horário de início da reunião, a sala de reunião recusará o convite da reunião, enviará uma mensagem de cancelamento ao organizador da reunião e a sala ficará disponível para outras pessoas reservarem.  

## <a name="requirements"></a>Requisitos 

Esse recurso pode ser usado em uma implantação de painel do Teams autônoma. Você também pode emparelhar painéis do Teams com Salas do Teams no Android com a versão 1449/1.0.96.202201305 ou posterior para funcionalidades adicionais, como notificações de check-in.

A caixa de correio compartilhada associada ao painel do Teams precisa ter o fuso horário correto definido para que esse recurso funcione corretamente. Para obter informações sobre como definir o fuso horário para caixas de correio compartilhadas, consulte [Configurações de fuso horário para caixas de correio compartilhadas em Outlook na Web](/exchange/troubleshoot/outlook-on-the-web-issues/shared-mailboxes-time-zone-setting).

## <a name="enable-check-in-and-room-release"></a>Habilitar o check-in e a versão do quarto 

O check-in e a versão do quarto estão desativados por padrão. Para ativá-lo,  

1. No painel do Teams, entre usando suas credenciais de administrador.  

2. Acesse **Configurações > Configurações do dispositivo > Administração configurações > configurações de administrador do Teams > Reuniões**.

3. Ative **a sala De liberação se ninguém fizer check-in**.

4. Para ajustar o tempo que os usuários precisam fazer check-in antes que a sala seja liberada, acesse **Liberar depois:** e selecione uma opção na lista suspensa.  

Quando os painéis do Teams são emparelhados com uma Sala do Teams no Android, um usuário pode fazer check-in na reunião na Sala do Teams.  

## <a name="turn-on-check-in-notifications"></a>Ativar notificações de check-in

> [!NOTE]
> Atualmente, esse recurso só está disponível em painéis do Teams emparelhados com uma Sala do Teams no Android. A sala painel do Teams e teams deve ser inscrevida na mesma conta de recurso. Consulte [Emparelhar um painel do Teams com uma Sala do Microsoft Teams no Android](use-teams-panels.md#pair-a-teams-panel-with-a-microsoft-teams-room-on-android) para saber mais.  

As notificações de check-in são enviadas quando uma reunião continua após o horário reservado. Depois que um usuário da próxima reunião fizer a verificação, a notificação aparecerá na frente da exibição da sala na hora de início da reunião agendada para permitir que os participantes da reunião anterior saibam que sua reserva acabou e as pessoas estão esperando pelo espaço.  

Para ativar notificações de check-in,  

1. No painel do Teams, entre usando suas credenciais de administrador. 

2. Acesse **Configurações > Configurações do dispositivo > Administração configurações > configurações de administrador do Teams > Reuniões**.

3. Acesse **Check-in** e ative **Enviar notificação de check-in**.

## <a name="related-topics"></a>Tópicos relacionados

- [Como usar painéis do Microsoft Teams](use-teams-panels.md)

- [Painéis do Microsoft Teams](teams-panels.md)
