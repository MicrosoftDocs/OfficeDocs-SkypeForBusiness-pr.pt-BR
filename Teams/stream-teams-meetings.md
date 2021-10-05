---
title: Transmitir Teams reuniões
author: KarliStites
ms.author: kastites
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
ms.openlocfilehash: d5cc83e1ea75d1c28ea4c30bac7cdabc4e60143d
ms.sourcegitcommit: 99503baa8b5183972caa8fe61e92a362213599d9
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/05/2021
ms.locfileid: "60127538"
---
# <a name="stream-teams-meetings"></a>Transmitir Teams reuniões

Este artigo ajudará você a configurar o streaming para Teams reuniões.

## <a name="what-is-streaming-and-how-does-it-work"></a>O que é streaming e como funciona?

O streaming permite que sua organização expanda seu alcance e oferece aos participantes da reunião mais opções de reunião. Quando você habilita o streaming, os organizadores podem transmitir reuniões e webinars para pontos de extremidade externos fornecendo uma URL do Protocolo de Mensagens (RTMP) do Real-Time e a chave para o aplicativo de Streaming Personalizado interno em Teams.

> [!NOTE]
> Não é possível transmitir eventos ao vivo.

## <a name="set-up-streaming-with-powershell"></a>Configurar streaming com o PowerShell

Você pode configurar sua organização para streaming com o PowerShell. Atualmente, essa política não está disponível no Teams de administração. A política por usuário é usada para especificar **quem pode** habilitar o streaming ao vivo. Ela está desativada por padrão.

Você pode usar o atributo a seguir no cmdlet **set-CsTeamsMeetingPolicy Windows PowerShell set-CsTeamsMeetingPolicy** para configurar o streaming. Para obter mais informações sobre o cmdlet, consulte [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy).

- LiveStreamingMode

De **definir LiveStreamingMode** **como Habilitado para** ativar recursos de streaming para um ou mais usuários.

> [!IMPORTANT]
> Você precisa ativar o registro de reunião antes que seus organizadores possam transmitir webinars. Para obter mais informações, [consulte Configurar webinars](set-up-webinars.md).

### <a name="assign-the-policy"></a>Atribuir a política

Para obter mais informações sobre como atribuir políticas com o PowerShell, consulte [Assign policies in Teams](policy-assignment-overview.md).

## <a name="related-topics"></a>Tópicos relacionados

- [Atribuir políticas em Teams](policy-assignment-overview.md)
- [Set-CsTeamsMeetingPolicy](/powershell/module/skype/set-csteamsmeetingpolicy)
- [Início rápido - reuniões, seminários via web e eventos ao vivo](quick-start-meetings-live-events.md)