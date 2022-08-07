---
title: Transmitir reuniões do Teams
author: mkbond007
ms.author: mabond
manager: serdars
ms.reviewer: suchakr
ms.topic: article
ms.tgt.pltfrm: cloud
ms.service: msteams
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- CSH
ms.custom: ''
ms.collection:
- M365-collaboration
description: Saiba como configurar e gerenciar o streaming para suas reuniões do Teams.
ms.openlocfilehash: 5e1e84fc3b0b4ed2f81b3f3a8c84450dc3cee56c
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/07/2022
ms.locfileid: "67270176"
---
# <a name="stream-teams-meetings"></a>Transmitir reuniões do Teams

Este artigo ajudará você a configurar o streaming para reuniões do Teams.

## <a name="what-is-streaming-and-how-does-it-work"></a>O que é streaming e como ele funciona?

O streaming permite que sua organização expanda seu alcance e fornece aos participantes da reunião mais opções de reunião. Quando você habilita o streaming, os organizadores podem transmitir reuniões e webinars para pontos de extremidade externos fornecendo uma URL do Real-Time protocolo RTMP e uma chave para o aplicativo de Streaming Personalizado interno no Teams.

> [!NOTE]
> Não é possível transmitir eventos ao vivo.

## <a name="set-up-streaming-with-powershell"></a>Configurar o streaming com o PowerShell

Você pode configurar sua organização para streaming com o PowerShell. Atualmente, essa política não está disponível no centro de administração do Teams. A política por usuário é usada para especificar **quem pode habilitar** a transmissão ao vivo. Ela está desativada por padrão.

Você pode usar o atributo a seguir Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** para configurar o streaming. Para obter mais informações sobre o cmdlet, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

**Defina LiveStreamingMode** **como Habilitado para** ativar os recursos de streaming para um ou mais usuários.

> [!IMPORTANT]
> Você precisa ativar o registro da reunião antes que os organizadores possam transmitir webinars. Para obter mais informações, [consulte Configurar webinars](set-up-webinars.md).

### <a name="assign-the-policy"></a>Atribuir a política

Para obter mais informações sobre como atribuir políticas com o PowerShell, consulte [Atribuir políticas no Teams](policy-assignment-overview.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas no Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Início rápido - reuniões, seminários via web e eventos ao vivo](quick-start-meetings-live-events.md)