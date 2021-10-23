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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- seo-marvel-mar2020
description: 'Saiba mais sobre quais informações são enviadas automaticamente aos usuários por email quando suas configurações de conferência discada mudarem Microsoft Teams. '
ms.openlocfilehash: ad61f7886d5a71fb8753b887ebfd6cd90f4f6a82
ms.sourcegitcommit: 75adb0cc163974772617c5e78a1678d9dbd9d76f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 10/22/2021
ms.locfileid: "60536472"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>E-mails enviados para os usuários quando suas configurações são alteradas no Microsoft Teams

Os emails serão enviados automaticamente para usuários habilitados para [Audioconferência](set-up-audio-conferencing-in-teams.md) usando a Microsoft como provedor de audioconferência.

Por padrão, há quatro tipos de email que serão enviados aos usuários habilitados para Audioconferência. No entanto, se você quiser limitar o número de emails enviados aos usuários, poderá desativar. A audioconferência Microsoft 365 ou Office 365 enviará emails para o email dos usuários quando:

- **Uma licença de Audioconferência é atribuída a eles ou quando você está alterando o provedor de audioconferência para a Microsoft.**

     Este email inclui a ID da conferência, o número de telefone de conferência padrão para as reuniões, o PIN de audioconferência para o usuário e as instruções e o link para usar a Ferramenta de Atualização de Reunião do Skype for Business Online usada para atualizar reuniões existentes para o usuário. Consulte [Atribuir Microsoft Teams licenças](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md) de complemento ou [Atribuir à Microsoft como provedor de audioconferência](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).

    > [!NOTE]
    > [!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas. Você pode configurar [IDs dinâmicas de Audioconferência em sua organização.](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user) 

    Aqui está um exemplo desse email:

     ![Skype for Business Verificar Licença.](media/teams-emails-sent-to-users-when-settings-change-image1.png)

    Para saber mais sobre licenciamento, [consulte Microsoft Teams licenciamento de complemento.](./teams-add-on-licensing/microsoft-teams-add-on-licensing.md)

- **A ID de conferência ou número de telefone de conferência padrão de um usuário for alterado.**

    Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário. Mas esse email não inclui o PIN de audioconferência do usuário. Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).

    Aqui está um exemplo desse email:

     ![As informações sobre conferência discada foram alteradas.](media/teams-emails-sent-to-users-when-settings-change-image2.png)

- **O PIN de audioconferência de um usuário é redefinido.**

    Este email contém o PIN de audioconferência do organizador, a ID de conferência existente e o número de telefone de conferência padrão para o usuário. Consulte [Redefinir o PIN de Audioconferência](reset-the-audio-conferencing-pin-in-teams.md).
    
     Aqui está um exemplo desse email:
    
     ![PIN para conferência discada alterado.](media/teams-emails-sent-to-users-when-settings-change-image3.png)
  
- **A licença de um usuário é removida ou quando o provedor de audioconferência muda da Microsoft para outro provedor ou Nenhum.**

    Isso acontece quando a **licença de Audioconferência** é removida de um usuário ou ao definir o provedor de audioconferência como **Nenhum**.

    Consulte [Atribuir ou remover licenças para Microsoft 365 para empresas.](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc)

    Aqui está um exemplo desse email:

     ![A conferência discada está desativada.](media/teams-emails-sent-to-users-when-settings-change-image4.png)

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Alterar as mensagens de email enviadas a eles

Você pode fazer alterações no email que é enviado automaticamente aos usuários. Por padrão, o remetente dos emails será de Microsoft 365 ou Office 365, mas você pode alterar o nome de exibição usando Windows PowerShell. Consulte a [Microsoft Teams referência do PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>E se você não quiser que eles recebam emails?

Ao desativar o envio de emails para os usuários, o email não será enviado mesmo quando o usuário receber uma licença. Nesse caso, a ID da conferência, o número de telefone de conferência padrão e, o mais importante, o PIN de audioconferência não serão enviados ao usuário. Quando isso acontecer, você deve informar ao usuário, enviando um email separado ou ligando para eles.

Por padrão, os emails serão enviados para seus usuários, mas se você quiser impedir que eles recebam emails para audioconferência, você pode usar Microsoft Teams ou Windows PowerShell. 

 **Usando o centro de administração do Microsoft Teams**

1. Na navegação à esquerda, vá para **Reuniões** > **Pontes de conferência**. 

2. Na parte superior da página **Pontes de Conferência,** clique em **Configurações de ponte.** 

3. No painel **Configurações de** ponte, habilita ou desabilita Enviar emails automaticamente aos usuários se suas configurações de **discagem mudarem**.

4. Clique em **Salvar**.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

**Usando Windows PowerShell**

Você também pode usar o módulo Microsoft Teams PowerShell e executar:

```PowerShell
Set-CsOnlineDialInConferencingTenantSettings -AutomaticallySendEmailsToUsers $true|$false
```

Você pode usar [o Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/set-csonlinedialinconferencingtenantsettings) para gerenciar outras configurações para sua organização, incluindo email.

Consulte a [Microsoft Teams referência do PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.

## <a name="want-to-know-more-about-windows-powershell"></a>Deseja saber mais sobre o Windows PowerShell?

Por padrão, o remetente dos emails será de Microsoft 365 ou Office 365, mas você pode alterar o endereço de email e o nome de exibição usando Windows PowerShell. 

O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](/previous-versions//dn568025(v=technet.10))

Para obter mais informações sobre o Windows PowerShell, consulte a [referência do Microsoft Teams PowerShell](/powershell/module/teams/?view=teams-ps) para obter mais informações.


## <a name="related-topics"></a>Tópicos relacionados

[Ativar ou desativar o envio de emails quando alterar configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change-in-teams.md)

[Enviar um email para um usuário com suas informações de conferência de áudio](send-an-email-to-a-user-with-their-dial-in-information-in-teams.md)
