---
title: Teams e Outlook email
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre Teams e Outlook integração de email, incluindo recursos que permitem que os usuários compartilhem informações entre emails no Outlook e conversas de chat ou canal no Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: cd1226cddb41ee40139029b64c65d6c151c3993b
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681752"
---
# <a name="teams-and-outlook-email-integration"></a>Teams e Outlook email

Microsoft Teams inclui recursos que facilitam para os usuários em sua organização compartilhar informações entre emails no Outlook e conversas de chat ou canal no Teams e para manter o controle das conversas perdidas. Este artigo fornece uma visão geral desses recursos e dos controles de administrador que se aplicam.

## <a name="share-to-outlook"></a>Compartilhar com Outlook

**Compartilhar com Outlook** permite que os usuários compartilhem uma cópia de uma conversa Teams para um email no Outlook, sem precisar sair Teams. Esse recurso é útil se os usuários precisam compartilhar conversas ou atualizações de status com usuários fora de sua equipe imediata ou até mesmo com sua organização. Vá para o início da conversa no Teams, selecione **... Mais opções** e, em seguida, **selecione Compartilhar para Outlook**.  Para saber mais, confira [Compartilhar Outlook de Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Captura de tela mostrando o recurso Compartilhar Outlook no Teams.](media/share-to-outlook.png)

Para usar esse recurso, Outlook na Web deve ser ativado para o usuário. Se Outlook na Web estiver desativada, **a** opção Compartilhar para Outlook não será exibida no Teams para o usuário. Para obter etapas sobre como ativar e desativar Outlook na Web, consulte Habilitar ou [desabilitar Outlook na Web para uma caixa de correio](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Emails de atividade acionáveis

Os usuários obtêm automaticamente emails de atividades perdidas acionáveis que os ajudam a acompanhar as conversas perdidas Teams. Os emails de atividade perdidas mostram as respostas mais recentes de uma conversa, incluindo mensagens que foram enviadas após a mensagem perdida, e os usuários  podem clicar em Responder para responder diretamente de dentro Outlook. Para saber mais, confira [Responder a emails de atividade perdidas do Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Esse recurso não tem suporte no Outlook para Mac ou em algumas versões mais antigas do Outlook para Windows. Para obter mais informações, [consulte Mensagens acionáveis em Outlook e Office 365 grupos](/outlook/actionable-messages/).

![Captura de tela mostrando um email de atividade perdida.](media/missed-activity-email.png)

![Captura de tela mostrando como responder a um email de atividade perdida.](media/missed-activity-email-reply.png)

Você pode usar o cmdlet [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) junto com o parâmetro **SmtpActionableMessagesEnabled** para desativar emails acionáveis. Por padrão, o **parâmetro SmtpActionableMessagesEnabled** é definido como **true**. Definir o parâmetro como **false desativa** mensagens de email acionáveis em Office 365. Para Teams, isso significa que a opção De resposta  para responder diretamente Outlook não está disponível em emails de atividade perdidas. Em vez disso, os emails de atividade perdida incluem **uma Teams** de resposta para que os usuários respondam Teams.

Consulte também [mensagens acionáveis em Outlook e Office 365 grupos](/outlook/actionable-messages/).
