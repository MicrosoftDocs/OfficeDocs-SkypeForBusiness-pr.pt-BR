---
title: Ativar a tradução de mensagens embutidas
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
description: Saiba como ativar a tradução embutida no Microsoft Teams usando o centro de administração do Microsoft Teams ou o PowerShell.
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
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Desativar a tradução da mensagem embutida no Microsoft Teams
=================================================

A tradução de mensagem embutida é um recurso do Microsoft Teams que permite aos usuários traduzir mensagens de equipes para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado pelas configurações de idioma pessoal.

A tradução da mensagem embutida é implementada por padrão para sua organização. Não é necessário fazer alterações se você deseja permitir que os usuários usem esse recurso dentro do cliente do teams.

> [!NOTE]
>Esta distribuição é excluída das assinaturas do Office 365 na nuvem da Comunidade do governo do Office 365 e nos ambientes do Office 365 Alemanha.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Usar o PowerShell para desativar a tradução da mensagem embutida

Você pode usar a política de mensagens para desativar a tradução da mensagem embutida.

Desative a política usando o cmdlet [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) . A política demora alguns minutos para se aplicar. Os usuários podem precisar sair e entrar novamente no Microsoft Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Usar o centro de administração do Microsoft Teams para desativar a tradução da mensagem embutida

No **centro de administração do Microsoft Teams**, selecione **políticas de mensagens** da navegação à esquerda e, em seguida, crie uma nova política ou edite uma política existente e defina a opção **traduzir mensagens** como **desativada**.

> [!NOTE]
> O serviço faz a tradução e a entrega para o cliente sem nenhum efeito sobre o conteúdo capturado nos registros de conformidade. Para saber mais sobre a tradução, confira [o que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview)
