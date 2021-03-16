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
description: Saiba mais sobre os recursos de integração de email do Teams e do Outlook, incluindo recursos que permitem que os usuários compartilhem informações entre email no Outlook e conversas de chat ou canal no Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: e469017eb9d03cbba55017ca609f49da9ebfe07a
ms.sourcegitcommit: c6b630f9193d7f82f0416bd567a1de390d4b260f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 03/15/2021
ms.locfileid: "50819357"
---
# <a name="teams-and-outlook-email-integration"></a>Integração de email do Teams e do Outlook

O Microsoft Teams inclui recursos que facilitam que os usuários da sua organização compartilhem informações entre email no Outlook e conversas de chat ou canal no Teams e fiquem atentos às conversas perdidas. Este artigo fornece uma visão geral desses recursos e os controles de administrador que se aplicam.

## <a name="share-to-outlook"></a>Compartilhar com o Outlook

**Compartilhar com o Outlook** permite que os usuários compartilhem uma cópia de uma conversa do Teams para um email no Outlook, sem precisar sair do Teams. Esse recurso é útil se os usuários precisam compartilhar conversas ou atualizações de status com usuários fora de sua equipe imediata ou até mesmo sua organização. Vá para a parte superior da conversa no Teams, selecione **̇ ̇ ̇ Mais opções** e selecione Compartilhar para o **Outlook**.  Para saber mais, confira [Compartilhar com o Outlook do Teams.](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d)

![Captura de tela mostrando o recurso Compartilhar com o Outlook no Teams](media/share-to-outlook.png)

Para usar esse recurso, o Outlook na Web deve estar ligado para o usuário. Se o Outlook na Web estiver desligado, a opção Compartilhar com o **Outlook** não será exibida no Teams para o usuário. Para ver as etapas sobre como ativar e desativar o Outlook na Web, consulte Habilitar ou [desabilitar](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app)o Outlook na Web para uma caixa de correio .

## <a name="actionable-activity-emails"></a>Emails de atividade a ação

Os usuários receberão automaticamente emails de atividade perdida ativos que os ajudam a acompanhar as conversas perdidas no Teams. Os emails de atividade perdida mostram as respostas mais recentes de uma conversa, incluindo mensagens enviadas após a mensagem perdida, e os usuários podem clicar em **Responder** para responder diretamente de dentro do Outlook. Para saber mais, confira [Responder aos emails de atividade perdida do Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Esse recurso não é suportado no Outlook para Mac ou em algumas versões mais antigas do Outlook para Windows. Para obter mais informações, consulte Mensagens ativas nos Grupos do [Outlook e do Office 365.](https://docs.microsoft.com/outlook/actionable-messages/)

![Captura de tela mostrando um email de atividade perdida](media/missed-activity-email.png)

![Captura de tela mostrando como responder a um email de atividade perdida](media/missed-activity-email-reply.png)

Você pode usar o cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) juntamente com o parâmetro **SmtpActionableMessagesEnabled** para desativar emails ativas. Por padrão, o **parâmetro SmtpActionableMessagesEnabled** é definido como **true**. A configuração do parâmetro como **false** desliga mensagens de email ativas no Office 365. Para usuários do Teams, isso significa que a opção **Responder** para responder diretamente no Outlook não está disponível em emails de atividade perdida. Em vez disso, os emails de atividade perdida incluem uma **opção Responder no Teams** para os usuários responderem no Teams.
