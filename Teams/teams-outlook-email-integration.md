---
title: Gerenciar emails de atividade acionáveis
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre como habilitar e desabilitar emails de atividade acionáveis de Microsoft conversas do Teams
ms.collection:
- M365-collaboration
ms.custom: chat-teams-channels-revamp
appliesto:
- Microsoft Teams
ms.openlocfilehash: de1bd12a0f079154a37156e3a01c3e5791bef10c
ms.sourcegitcommit: dc5b3870fd338f7e9ab0a602a44eaf9feb595b2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/30/2022
ms.locfileid: "69198503"
---
# <a name="manage-actionable-activity-emails"></a>Gerenciar emails de atividade acionáveis

Os emails de atividade acionáveis são habilitados por padrão e notificam os usuários em sua organização de conversas perdidas no Microsoft Teams.

Um email de atividade perdida mostra as últimas respostas a uma conversa, incluindo mensagens enviadas após a mensagem perdida. Esse recurso permite que os usuários respondam diretamente do Outlook selecionando **Responder**.

## <a name="disable-actionability-in-missed-activity-emails"></a>Desabilitar a capacidade de ação em emails de atividades perdidas

Embora esse recurso esteja definido como habilitado por padrão, você pode desativar a capacidade de ação em emails de atividade em toda a sua organização executando o seguinte comando:

```Powershell
Set-OrganizationConfig -SmtpActionableMessagesEnabled $false
```

Depois que o recurso é desabilitado, a opção **Responder** é substituída pela **Resposta no Teams** , fazendo com que os emails de atividade ausentes não sejam mais considerados acionáveis. Os usuários não poderão mais responder diretamente do Outlook e são orientados a continuar a conversa no Teams.

> [!NOTE]
> Esse recurso não tem suporte em Outlook para Mac ou em algumas versões mais antigas do Outlook para Windows. Para obter mais informações, consulte [Mensagens acionáveis no Outlook e grupos de Office 365](/outlook/actionable-messages/).

## <a name="related-topics"></a>Tópicos relacionados

[Responder a emails de atividades perdidas do Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381).

[Mensagens acionáveis em Grupos do Outlook e Office 365](/outlook/actionable-messages/).
