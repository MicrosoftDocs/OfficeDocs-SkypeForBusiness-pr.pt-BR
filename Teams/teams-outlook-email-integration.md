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
description: Saiba mais sobre como habilitar e desabilitar emails de atividade acionáveis de conversas do Microsoft Teams
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 43435c436685c53e0ad077887a9fe9d991cf2d61
ms.sourcegitcommit: f5480d0ca34b3160980a4b46b5afa34271293a26
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 11/09/2022
ms.locfileid: "68899685"
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
