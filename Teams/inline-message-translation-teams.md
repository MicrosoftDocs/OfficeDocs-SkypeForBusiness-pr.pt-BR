---
title: Ativar a tradução de mensagens em linha
author: ChuckEdmonson
ms.author: chucked
manager: serdars
ms.date: 06/21/2019
audience: Admin
ms.topic: article
ms.service: msteams
ms.collection:
- M365-collaboration
ms.reviewer: salilda
localization_priority: Normal
search.appverid: MET150
description: Saiba como ativar a tradução em linha no Microsoft Teams usando o Centro de administração do Microsoft Teams ou o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 012f2431ec7fb249a2f2e3b963c41166c4649a5c
ms.sourcegitcommit: 2e6b0930645cd97dbd597e9346a6fe1788c6facf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/04/2020
ms.locfileid: "47395380"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Desativar a tradução de mensagens em linha no Microsoft Teams
=================================================

A tradução em linha de mensagens é um recurso [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) do Microsoft Teams que permite que os usuários traduzam mensagens do Teams para o idioma especificado por suas configurações de idioma pessoal.

A tradução em linha de mensagens é enviada por padrão para sua organização. Você não precisará fazer alterações se quiser permitir que os usuários usem esse recurso no cliente do Teams.

> [!NOTE]
>Essa adoção é excluída das assinaturas do Office 365 em nossos ambientes do Office 365 Government Community Cloud e Office 365 Germany.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Usar o PowerShell para desativar a tradução de mensagens em linha

Você pode usar a política de mensagens para desativar a tradução de mensagens em linha.

Desativar a política usando o cmdlet [Set-CsTeamsMessagingPolicy.](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) A política leva alguns minutos para ser aplicada. Talvez os usuários precisem sair e entrar novamente no Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Usar o Centro de administração do Microsoft Teams para desativar a tradução de mensagens em linha

No Centro de administração  do **Microsoft Teams,** selecione Políticas de Mensagens na navegação à esquerda,  crie uma nova política ou edite uma política existente e de definir a opção Traduzir mensagens como **Desabilitada.**

> [!NOTE]
> O serviço faz a tradução e a entrega ao cliente sem nenhum efeito sobre o conteúdo capturado nos registros de conformidade. Para saber mais sobre tradução, consulte [O que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)
