---
title: Teams e integração de email do Outlook
author: LanaChin
ms.author: v-lanac
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
ms.reviewer: kblevens
localization_priority: Normal
search.appverid: MET150
description: Saiba mais sobre o Teams e os recursos de integração de email do Outlook, incluindo recursos que permitem que os usuários compartilhem informações entre emails no Outlook e chat ou conversas de canal no Teams.
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 34498b73b70937eefcff267bc7a3b01068ab9557
ms.sourcegitcommit: 430aac8c5848fbcaf680ea447bfa2f9d5fa994e2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/09/2020
ms.locfileid: "47420605"
---
# <a name="teams-and-outlook-email-integration"></a>Teams e integração de email do Outlook

O Microsoft Teams inclui recursos que tornam mais fácil para os usuários da sua organização compartilhar informações entre emails no Outlook e chat ou conversas de canal no Teams e manter-se à frente das conversas perdidas. Este artigo oferece uma visão geral desses recursos e dos controles de administração que se aplicam.

## <a name="share-to-outlook"></a>Compartilhar no Outlook

**Compartilhar com o Outlook** permite que os usuários compartilhem uma cópia de uma conversa do teams para um email no Outlook, sem precisar sair do teams. Esse recurso é útil se os usuários precisam compartilhar conversas ou atualizações de status com usuários de fora de sua equipe imediata ou até mesmo à sua organização. Vá para a parte superior da conversa no Teams, selecione **̇ ̇ ̇ mais opções**e, em seguida, selecione **compartilhar com o Outlook**.  Para saber mais, confira [compartilhar com o Outlook no Teams](https://support.office.com/article/share-to-outlook-from-teams-f9dabbe9-9e9b-4e35-99dd-2eeeb67c4f6d).

![Captura de tela mostrando o recurso compartilhar com o Outlook no Microsoft Teams](media/share-to-outlook.png)

Para usar esse recurso, o Outlook na Web deve estar ativado para o usuário. Se o Outlook na Web estiver desativado, a opção **compartilhar com o Outlook** não será exibida no Teams para o usuário. Para ver as etapas sobre como ativar e desativar o Outlook na Web, confira [habilitar ou desabilitar o Outlook na Web para uma caixa de correio](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/enable-or-disable-outlook-web-app).

## <a name="actionable-activity-emails"></a>Emails de atividades acionáveis

Os usuários recebem automaticamente emails de atividade ausentes que o ajudam a acompanhar conversas perdidas no Teams. Os emails da atividade perdida mostram as respostas mais recentes de uma conversa, incluindo mensagens que foram enviadas após a mensagem perdida, e os usuários podem clicar em **responder** para responder diretamente no Outlook. Para saber mais, confira [responder a emails de atividades perdidas do Outlook](https://support.office.com/article/reply-to-missed-activity-emails-from-outlook-bc0cf587-db26-4946-aac7-8eebd84f1381) e [mensagens acionáveis no Outlook e grupos do Office 365](https://docs.microsoft.com/outlook/actionable-messages/).

![Captura de tela mostrando um email de atividade perdida](media/missed-activity-email.png)

![Captura de tela mostrando como responder a um email de atividade perdida](media/missed-activity-email-reply.png)

Você pode usar o cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/organization/set-organizationconfig) juntos com o parâmetro **SmtpActionableMessagesEnabled** para desativar emails acionáveis. Por padrão, o parâmetro **SmtpActionableMessagesEnabled** é definido como **true**. Definir o parâmetro como **false** desativa mensagens de email acionáveis no Office 365. Para usuários do Teams, isso significa que a opção de **resposta** para responder diretamente no Outlook não está disponível em emails de atividade ausentes. Em vez disso, os emails de atividade ausentes incluem uma opção **responder do teams** para que os usuários respondam ao Teams.
