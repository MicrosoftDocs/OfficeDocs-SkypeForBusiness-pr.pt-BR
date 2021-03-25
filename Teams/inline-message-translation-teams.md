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
ms.openlocfilehash: 5c9e34c5e539d32b25259098973e9bfe6795ad7c
ms.sourcegitcommit: 01087be29daa3abce7d3b03a55ba5ef8db4ca161
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51120622"
---
<a name="turn-off-inline-message-translation-in-microsoft-teams"></a>Desativar a conversão de mensagens em linha no Microsoft Teams
=================================================

A conversão em linha de mensagens é um recurso [](https://support.office.com/article/translate-a-message-in-teams-d8926ce9-d6a6-47df-a416-f1adb62d3194) do Microsoft Teams que permite que os usuários traduzam mensagens do Teams no idioma especificado por suas configurações de idioma pessoal.

A conversão de mensagens em linha é rolada por padrão para sua organização. Você não precisa fazer alterações se quiser permitir que os usuários usem esse recurso dentro do cliente do Teams.

> [!NOTE]
>Essa adoção é excluída das assinaturas do Office 365 em nossos ambientes do Office 365 Government Community Cloud e Office 365 Germany.

## <a name="use-powershell-to-turn-off-inline-message-translation"></a>Usar o PowerShell para desativar a conversão de mensagens em linha

Você pode usar a política de mensagens para desativar a tradução de mensagem em linha.

Desativar a política usando o cmdlet [Set-CsTeamsMessagingPolicy.](/powershell/module/skype/set-csteamsmessagingpolicy?view=skype-ps) A política leva alguns minutos para ser aplicada. Os usuários podem precisar sair e entrar novamente no Teams.

## <a name="use-the-microsoft-teams-admin-center-to-turn-off-inline-message-translation"></a>Usar o centro de administração do Microsoft Teams para desativar a conversão de mensagens em linha

No Centro de administração  do **Microsoft Teams,** selecione Políticas de Mensagens na navegação à esquerda, crie uma nova política ou edite uma política existente e desdole a opção **Traduzir** mensagens como **Off**.

> [!NOTE]
> O serviço faz a conversão e a entrega ao cliente sem efeito no conteúdo capturado nos registros de conformidade. Para saber mais sobre tradução, consulte [O que é o Microsoft Translator?](/azure/cognitive-services/translator/translator-info-overview)