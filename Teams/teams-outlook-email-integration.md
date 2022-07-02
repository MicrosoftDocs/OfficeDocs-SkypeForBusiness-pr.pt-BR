---
title: Integração de email do Teams e do Outlook
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
ms.localizationpriority: medium
search.appverid: MET150
description: Saiba mais sobre os recursos de integração de email do Teams e do Outlook, incluindo recursos que permitem que os usuários compartilhem informações entre emails no Outlook e conversas de chat ou canal no Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 76a2ecf05a8769b51ffcb9827c0fe6ff75df7b18
ms.sourcegitcommit: 79ada2140b110239deff96e4854ebd5dd9b77881
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 07/01/2022
ms.locfileid: "66606230"
---
# <a name="teams-and-outlook-email-integration"></a>Integração de email do Teams e do Outlook

O Microsoft Teams inclui recursos que facilitam para os usuários em sua organização compartilhar informações entre emails no Outlook e conversas de chat ou canal no Teams e para se manter por dentro das conversas perdidas. Este artigo fornece uma visão geral desses recursos e dos controles de administrador que se aplicam.

## <a name="share-to-outlook"></a>Compartilhar com o Outlook

**Compartilhar com o Outlook** permite que os usuários compartilhem uma cópia de uma conversa do Teams para um email no Outlook, sem precisar sair do Teams. Esse recurso é útil se os usuários precisam compartilhar conversas ou atualizações de status com usuários fora de sua equipe imediata ou até mesmo com sua organização. Vá para o início da conversa no Teams, selecione **... Mais opções** e, em seguida, selecione **Compartilhar com o Outlook**.  Para saber mais, confira [Compartilhar com o Outlook no Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Captura de tela mostrando o recurso Compartilhar com o Outlook no Teams.](media/share-to-outlook.png)

Para usar esse recurso, Outlook na Web deve ser ativado para o usuário. Se Outlook na Web estiver desativada, a opção Compartilhar com **o Outlook** não será exibida no Teams para o usuário. Para obter etapas sobre como ativar e desativar Outlook na Web, consulte Habilitar ou [desabilitar Outlook na Web para uma caixa de correio](/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Emails de atividade acionáveis

Os usuários obtêm automaticamente emails de atividades perdidas acionáveis que os ajudam a acompanhar as conversas perdidas no Teams. Os emails de atividade perdidas mostram as respostas mais recentes de uma conversa, incluindo mensagens que foram enviadas após a mensagem perdida, e os usuários  podem clicar em Responder para responder diretamente de dentro do Outlook. Para saber mais, confira [Responder a emails de atividade perdidas do Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381). 

> [!NOTE]
> Não há suporte para esse recurso no Outlook para Mac ou em algumas versões mais antigas do Outlook para Windows. Para obter mais informações, [consulte Mensagens acionáveis no Outlook e Office 365 Grupos](/outlook/actionable-messages/).

![Captura de tela mostrando um email de atividade perdida.](media/missed-activity-email.png)

![Captura de tela mostrando como responder a um email de atividade perdida.](media/missed-activity-email-reply.png)

Você pode usar o cmdlet [Set-OrganizationConfig](/powershell/module/exchange/organization/set-organizationconfig) junto com o parâmetro **SmtpActionableMessagesEnabled** para desativar emails acionáveis. Por padrão, o **parâmetro SmtpActionableMessagesEnabled** é definido como **true**. Definir o parâmetro como **false desativa** mensagens de email acionáveis em Office 365. Para usuários do Teams, isso significa que a **opção Responder** para responder diretamente no Outlook não está disponível em emails de atividades perdidas. Em vez disso, os emails de atividade perdida incluem uma **opção responder no Teams** para que os usuários respondam no Teams.

Consulte também [mensagens acionáveis no Outlook e Office 365 Grupos](/outlook/actionable-messages/).
