---
title: Transmitir Teams reuniões
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
- m365initiative-meetings
description: Saiba como configurar e gerenciar o streaming para suas Teams reuniões.
ms.openlocfilehash: 352a0c2e7a0584640e466b5e46456906e4912d00
ms.sourcegitcommit: 9532eb79310cd653010565607fa394f2b8dd182d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/23/2022
ms.locfileid: "65646340"
---
# <a name="stream-teams-meetings"></a>Transmitir Teams reuniões

Este artigo ajudará você a configurar o streaming para Teams reuniões.

## <a name="what-is-streaming-and-how-does-it-work"></a>O que é streaming e como ele funciona?

O streaming permite que sua organização expanda seu alcance e fornece aos participantes da reunião mais opções de reunião. Quando você habilita o streaming, os organizadores podem transmitir reuniões e webinars para pontos de extremidade externos fornecendo uma URL e uma chave do protocolo Real-Time Messaging Protocol (RTMP) para o aplicativo de Streaming Personalizado interno no Teams.

> [!NOTE]
> Não é possível transmitir eventos ao vivo.

## <a name="set-up-streaming-with-powershell"></a>Configurar o streaming com o PowerShell

Você pode configurar sua organização para streaming com o PowerShell. Atualmente, essa política não está disponível no centro Teams administrador. A política por usuário é usada para especificar **quem pode habilitar** a transmissão ao vivo. Ela está desativada por padrão.

Você pode usar o atributo a seguir Windows PowerShell cmdlet **Set-CsTeamsMeetingPolicy** para configurar o streaming. Para obter mais informações sobre o cmdlet, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

**Defina LiveStreamingMode** **como Habilitado para** ativar os recursos de streaming para um ou mais usuários.

> [!IMPORTANT]
> Você precisa ativar o registro da reunião antes que os organizadores possam transmitir webinars. Para obter mais informações, [consulte Configurar webinars](set-up-webinars.md).

### <a name="assign-the-policy"></a>Atribuir a política

Para obter mais informações sobre como atribuir políticas com o PowerShell, consulte [Atribuir políticas Teams](policy-assignment-overview.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas no Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Início rápido - reuniões, seminários via web e eventos ao vivo](quick-start-meetings-live-events.md)