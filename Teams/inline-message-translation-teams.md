---
title: Ativar a tradução de mensagem em linha
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
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba como ativar a tradução em linha no Microsoft Teams usando o centro de administração Microsoft Teams ou o PowerShell.
f1.keywords:
- CSH
ms.custom:
- NewAdminCenter_Update
- seo-marvel-apr2020
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4bfaa03ff8fa8654fca48fbd2bd31d8d6518e2de
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593075"
---
# <a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Desativar a conversão de mensagens em Microsoft Teams

A conversão em linha de mensagens é um recurso Microsoft Teams [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) que permite que os usuários traduzam Teams mensagens para o idioma especificado por suas configurações de idioma pessoal.

A conversão de mensagens em linha é rolada por padrão para sua organização. Você não precisa fazer alterações se quiser permitir que os usuários usem esse recurso no Teams cliente.

> [!NOTE]
>Essa adoção é excluída Office 365 assinaturas em nossos ambientes Office 365 Government Community Cloud e Office 365 Alemanha.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Usar o PowerShell para desativar a conversão de mensagens em linha

Você pode usar a política de mensagens para desativar a tradução de mensagem em linha.

Desativar a política usando o cmdlet [Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) A política leva alguns minutos para ser aplicada. Os usuários podem precisar sair e entrar novamente Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Use o Microsoft Teams de administração para desativar a conversão de mensagens em linha

No centro **de** administração Microsoft Teams,  selecione Políticas de Mensagens na navegação à esquerda, crie uma nova política ou edite uma política existente e de definir a opção **Traduzir** mensagens como **Off**.

> [!NOTE]
> O serviço faz a conversão e a entrega ao cliente sem efeito no conteúdo capturado nos registros de conformidade. Para saber mais sobre tradução, consulte [O que é Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)