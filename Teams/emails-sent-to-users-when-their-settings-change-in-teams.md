---
title: Emails enviados para os usuários quando suas configurações são alteradas
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
- M365-collaboration
audience: Admin
appliesto:
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Saiba as informações que são enviadas automaticamente aos usuários por e-mail quando suas configurações de conferência discada são alteradas no Microsoft Teams. '
ms.openlocfilehash: 15c35570d509ae69a41e4c6d9522a5a62d32dd59
ms.sourcegitcommit: 1807ea5509f8efa6abba8462bce2f3646117e8bf
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/10/2020
ms.locfileid: "44691477"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>E-mails enviados para os usuários quando suas configurações são alteradas no Microsoft Teams

Serão enviados e-mails automaticamente para usuários que estão [habilitados para audioconferência](set-up-audio-conferencing-in-teams.md) e usam a Microsoft como provedor de audioconferência.

Por padrão, existem quatro tipos de e-mail que são enviados aos usuários habilitados para audioconferência. No entanto, se você deseja limitar o número de e-mails enviados aos usuários, é possível desativá-los. Conferências de áudio no Microsoft 365 ou no Office 365 enviarão emails ao email dos usuários quando:

- **Uma licença de Audioconferência PSTN for atribuída a eles ou quando você alterar o provedor de audioconferência para a Microsoft.**

     Esse e-mail inclui o ID de conferência, o número de telefone de conferência padrão para as reuniões, o PIN de audioconferência do usuário, além das instruções e do link para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário. Consulte [atribuir licenças de Complementos do Microsoft Teams](teams-add-on-licensing/assign-teams-add-on-licenses.md) ou [atribuir a Microsoft como o provedor de serviços de audioconferência](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

    > [!NOTE]
    > Se a sua organização estiver habilitada para IDs de conferência dinâmicos, todas as reuniões agendadas de um usuário terão IDs de conferência exclusivos. Você pode configurar [IDs dinâmicos de audioconferência na sua organização](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user). 

    Aqui está um exemplo desse e-mail:

     ![Verificar licença do Skype for Business](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Para saber mais sobre licenciamento, consulte [Licenciamento de Complementos do Microsoft Teams](teams-add-on-licensing/microsoft-teams-add-on-licensing.md).

- **O ID de conferência ou número de telefone de conferência padrão de um usuário é alterado.**

    Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário. Mas esse e-mail não inclui o PIN de audioconferência do usuário. Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).

    Aqui está um exemplo desse e-mail:

     ![As informações sobre conferência discada foram alteradas.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **O PIN de audioconferência de um usuário é redefinido.**

    Esse e-mail contém o PIN de audioconferência do organizador, o ID de conferência existente e o número de telefone de conferência padrão do usuário. Veja [Redefinir o PIN de audioconferência](reset-the-audio-conferencing-pin-in-teams.md).
    
     Aqui está um exemplo desse e-mail:
    
     ![O PIN de conferência discada foi alterado.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **A licença do usuário for removida ou quando o provedor de audioconferência é alterado da Microsoft para outro provedor ou Nenhum.**

    Isso acontece quando a licença de **conferência de áudio** é removida de um usuário ou ao configurar o provedor de serviços de audioconferência para **nenhum**.

    Consulte [atribuir ou remover licenças para o Microsoft 365 para empresas](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).

    Aqui está um exemplo desse email:

     ![A conferência discada está desativada.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Alterar as mensagens de email enviadas a eles

Você pode fazer alterações ao email que será enviado automaticamente aos usuários. Por padrão, o remetente dos emails será do Microsoft 365 ou do Office 365, mas você pode alterar o nome de exibição usando o Windows PowerShell. Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>E se você não quiser que eles recebam emails?

Ao desativar o envio de emails para os usuários, o email não será enviado mesmo quando o usuário receber uma licença. Nesse caso, a ID de conferência, o número de telefone de conferência padrão e, o mais importante, o PIN de audioconferência não será enviado ao usuário. Quando isso acontecer, você deve informar ao usuário, enviando um email separado ou ligando para eles.

Por padrão, os emails serão enviados aos seus usuários, mas se você quiser impedir que eles recebam emails para videoconferências, você pode usar o Microsoft Teams ou o Windows PowerShell. 

![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **pontes de conferência** , clique em **configurações de ponte**. 

3. No painel **configurações de ponte** , habilite ou desabilite **enviar emails automaticamente aos usuários se as configurações de discagem forem alteradas**.

4. Clique em **Salvar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Usando o Windows PowerShell**

Consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.


## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

Por padrão, o remetente dos emails será do Microsoft 365 ou do Office 365, mas você pode alterar o endereço de email e o nome de exibição usando o Windows PowerShell. 

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)

  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)

Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.


## <a name="related-topics"></a>Tópicos relacionados

[Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
