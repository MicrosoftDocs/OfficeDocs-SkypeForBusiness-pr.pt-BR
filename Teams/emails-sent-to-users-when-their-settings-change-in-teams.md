---
title: E-mails enviados para os usuários quando suas configurações são alteradas no Microsoft Teams
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1b46da6d-f93a-4cc0-9ae8-af765935b007
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- Teams_ITAdmin_Help
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Saiba as informações que são enviadas automaticamente aos usuários por e-mail quando suas configurações de conferência discada são alteradas no Microsoft Teams. '
ms.openlocfilehash: db9b2c2d99aad64bd9d607e5acbac99afc36d978
ms.sourcegitcommit: 31827526894ffb75d64fcb0a7c76ee874ad3c269
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 02/06/2019
ms.locfileid: "29754669"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>E-mails enviados para os usuários quando suas configurações são alteradas no Microsoft Teams

Serão enviados e-mails automaticamente para usuários que estão [habilitados para audioconferência](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) e usam a Microsoft como provedor de audioconferência.

Por padrão, existem quatro tipos de e-mail que são enviados aos usuários habilitados para audioconferência. No entanto, se você deseja limitar o número de e-mails enviados aos usuários, é possível desativá-los. A audioconferência no Office 365 enviará um e-mail para o e-mail de seus usuários quando:

- **Uma licença de Audioconferência PSTN for atribuída a eles ou quando você alterar o provedor de audioconferência para a Microsoft.**

     Esse e-mail inclui o ID de conferência, o número de telefone de conferência padrão para as reuniões, o PIN de audioconferência do usuário, além das instruções e do link para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário. Consulte [Atribuir licenças do Skype for Business e do Microsoft Teams](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [Atribuir a Microsoft como o provedor de audioconferência](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

    > [!NOTE]
    > Se a sua organização estiver habilitada para IDs de conferência dinâmicos, todas as reuniões agendadas de um usuário terão IDs de conferência exclusivos. Você pode configurar [IDs dinâmicos de audioconferência na sua organização](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user). 

    Aqui está um exemplo desse e-mail:

     ![Verificar licença do Skype for Business](media/audio-conferencing-user-enabled.png)

    Você pode saber mais sobre as licenças em [Licenciamento de complementos do Skype for Business e do Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).

- **O ID de conferência ou número de telefone de conferência padrão de um usuário é alterado.**

    Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário. Mas esse e-mail não inclui o PIN de audioconferência do usuário. Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).

    Aqui está um exemplo desse e-mail:

     ![As informações sobre conferência discada foram alteradas.](media/audio-conferencing-info-change.png)

- **O PIN de audioconferência de um usuário é redefinido.**

    Esse e-mail contém o PIN de audioconferência do organizador, o ID de conferência existente e o número de telefone de conferência padrão do usuário. Veja [Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md).
    
     Aqui está um exemplo desse e-mail:
    
     ![O PIN de conferência discada foi alterado.](media/audio-conferencing-pin-has-changed.png)
  
- **A licença do usuário for removida ou quando o provedor de audioconferência é alterado da Microsoft para outro provedor ou Nenhum.**

    Isso ocorre quando a licença de **Audioconferência** é removida de um usuário ou quando o provedor de conferência discada é alterado da Microsoft para um provedor de serviços de audioconferência de terceiros ou é definido como **Nenhum**. Esse e-mail contém as instruções e as informações para o usuário usar a Ferramenta de atualização de reunião do Skype for Business Online para remover informações específicas da audioconferência, como o número de telefone de conferência padrão ou o ID de conferência.

    Consulte [Atribuir ou remover licenças do Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    Aqui está um exemplo desse e-mail:

     ![A conferência discada está desativada.](media/audio-conferencing-turned-off.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Alterar as mensagens de e-mail enviadas a eles

Você pode fazer alterações nos e-mails enviados automaticamente para os usuários, incluindo o endereço de e-mail e o nome de exibição incluído em *De* nas informações de contato. Por padrão, o remetente dos e-mails será o Office 365, mas é possível alterar o endereço de e-mail e o nome exibido com o Windows PowerShell. Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>E se você não quiser que eles recebam e-mails?

Ao desativar o envio de e-mails aos usuários, o e-mail não será enviado mesmo quando o usuário receber uma licença. Se esse for o caso, o ID de conferência, o número de telefone de conferência padrão e, mais importante, o PIN de audioconferência não serão enviados para o usuário. Quando isso acontecer, você deverá informar ao usuário, enviando um e-mail separado ou ligando para ele.

Seus usuários receberão e-mails por padrão, mas, se você deseja evitar que eles recebam e-mails sobre audioconferência, você pode usar o Microsoft Teams ou o Windows PowerShell. 

![as equipes de logotipo-30x30.png](media/teams-logo-30x30.png) **usando o Centro de administração de equipes da Microsoft**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. No topo da página **Pontes de conferência**, clique em **Configurações da ponte**. 

3. No painel **Configurações de ponte**, habilite ou desabilite **Enviar e-mails aos usuários automaticamente de suas configurações de discagem forem alteradas**.

4. Clique em **Salvar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Usar o Windows PowerShell**

Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.


## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

Por padrão, o remetente dos e-mails será o Office 365, mas é possível alterar o endereço de e-mail e o nome exibido com o Windows PowerShell. 

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:

  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.


## <a name="related-topics"></a>Tópicos relacionados

[Ativar ou desativar o envio de e-mails quando alterar configurações de Audioconferência](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
