---
title: Ativar a tradução de mensagens embutidas no Microsoft Teams
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
description: Saiba como usar a tradução embutida no Microsoft Teams.
ms.custom:
- NewAdminCenter_Update
appliesto:
- Microsoft Teams
ms.openlocfilehash: 24f6c6a2eca313b70640dbf61a87c6c5742ea318
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/17/2019
ms.locfileid: "37570730"
---
<a name="turn-on-inline-message-translation-in-microsoft-teams"></a>Ativar a tradução de mensagens embutidas no Microsoft Teams 
=================================================

A tradução da mensagem embutida é um novo recurso do Microsoft Teams que permite aos usuários traduzir mensagens de equipes para o [idioma](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) especificado pelas configurações de idioma pessoal do Office 365.

A tradução de mensagem embutida está sendo lançada por padrão para sua organização. Se você quiser permitir que os usuários usem esse recurso dentro do cliente do Teams, deverá ativar essa configuração.

> [!NOTE]
>Esta distribuição é excluída das assinaturas do Office 365 na nuvem da Comunidade do governo do Office 365 e nos ambientes do Office 365 Alemanha.

## <a name="use-powershell-to-turn-on-inline-message-translation"></a>Usar o PowerShell para ativar a tradução de mensagens embutidas

Você pode usar a política de mensagens para ativar a tradução embutida da mensagem.

Ative a política usando o cmdlet [set-CsTeamsMessagingPolicy](https://docs.microsoft.com/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) . A política demora alguns minutos para se aplicar. Os usuários podem precisar sair e entrar novamente no Microsoft Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-on-inline-message-translation"></a>Usar o centro de administração do Microsoft Teams para ativar a tradução de mensagens embutidas

No **centro de administração do Microsoft Teams**, selecione **políticas de mensagens** da navegação à esquerda, crie uma nova política ou edite uma política existente e defina a opção **permitir que os usuários traduzam mensagens** para **ativado**.

> [!NOTE]
> O serviço faz a tradução e a entrega para o cliente sem nenhum efeito sobre o conteúdo capturado nos registros de conformidade. Para saber mais sobre a tradução, confira [o que é o Microsoft Translator?](https://docs.microsoft.com/azure/cognitive-services/translator/translator-info-overview).