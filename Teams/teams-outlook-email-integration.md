---
title: Integração de email do Teams e do Outlook
author: cichur
ms.author: v-cichur
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre os recursos de integração de email do Teams e do Outlook, incluindo recursos que permitem que os usuários compartilhem informações entre emails no Outlook e conversas de chat ou canal no Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: c6e260148cfcdb45c516958bae03ecfadc1bbd64
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/12/2021
ms.locfileid: "49802391"
---
# <a name="teams-and-outlook-email-integration"></a>Integração de email do Teams e do Outlook

O Microsoft Teams inclui recursos que facilitam para os usuários em sua organização compartilhar informações entre email no Outlook e conversas de chat ou canal no Teams e para ficar por dentro das conversas perdidas. Este artigo fornece uma visão geral desses recursos e os controles de administrador que se aplicam.

## <a name="share-to-outlook"></a>Compartilhar com o Outlook

**Compartilhar com o Outlook** permite que os usuários compartilhem uma cópia de uma conversa do Teams para um email no Outlook, sem precisar sair do Teams. Esse recurso é útil se os usuários precisam compartilhar conversas ou atualizações de status com usuários fora da equipe imediata ou até mesmo da sua organização. Vá para o início da conversa no Teams, selecione **̇ ̇ ̇ Mais** opções e selecione Compartilhar com **o Outlook.**  Para saber mais, confira [Compartilhar com o Outlook no Teams.](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)

![Captura de tela mostrando o recurso Compartilhar com o Outlook no Teams](media/share-to-outlook.png)

Para usar esse recurso, o Outlook na Web deve estar ligado para o usuário. Se o Outlook na Web estiver desligado, a opção Compartilhar com **o Outlook** não será exibida no Teams para o usuário. Para ver as etapas sobre como ativar e desativar o Outlook na Web, confira [Habilitar](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)ou desabilitar o Outlook na Web para uma caixa de correio.

## <a name="actionable-activity-emails"></a>Emails de atividade a actionable

Os usuários receberão automaticamente emails de atividades perdidas ativos que os ajudam a acompanhar as conversas perdidas no Teams. Os emails de atividade perdida mostram as respostas mais recentes de uma conversa, incluindo mensagens enviadas após a mensagem perdida, e os usuários podem clicar em **Responder** para responder diretamente do Outlook. Para saber mais, confira [Responder a emails de atividade perdida do Outlook.](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) 

> [!NOTE]
> Esse recurso não é suportado no Outlook para Mac ou em algumas versões mais antigas do Outlook para Windows. Para obter mais informações, consulte [Mensagens ativas no Outlook e nos Grupos do Office 365.](https://docs.microsoft.com/outlook/actionable-messages/)

![Captura de tela mostrando um email de atividade perdida](media/missed-activity-email.png)

![Captura de tela mostrando como responder a um email de atividade perdida](media/missed-activity-email-reply.png)

Você pode usar o cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) junto com o parâmetro **SmtpActionableMessagesEnabled** para desativar emails a ação. Por padrão, o **parâmetro SmtpActionableMessagesEnabled** é definido como **true**. A configuração do parâmetro como **false** desliga as mensagens de email ativas no Office 365. Para usuários do Teams, isso significa que a opção **Responder** para responder diretamente no Outlook não está disponível em emails de atividades perdidas. Em vez disso, os emails de atividade perdida incluem uma **opção Responder** no Teams para que os usuários respondam no Teams.
