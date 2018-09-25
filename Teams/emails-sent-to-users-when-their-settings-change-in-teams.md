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
ms.openlocfilehash: b1bd7764f7780267d9f2a98a3203f49d2c0e938e
ms.sourcegitcommit: 9acf2f80cbd55ba2ff6aab034757cc053287485f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/25/2018
ms.locfileid: "25016161"
---
# <a name="emails-sent-to-users-when-their-settings-change-in-microsoft-teams"></a>E-mails enviados para os usuários quando suas configurações são alteradas no Microsoft Teams

Serão enviados e-mails automaticamente para usuários que estão [habilitados para audioconferência](/SkypeForBusiness/audio-conferencing-in-office-365/set-up-audio-conferencing) e usam a Microsoft como provedor de audioconferência.
  
Por padrão, há quatro tipos de email que será enviada para os usuários habilitados para conferência de áudio. No entanto, se desejar limitar o número de emails enviados aos usuários, você pode desativá-lo. Serviços de audioconferência no Office 365 enviará o email para seus usuários de email quando:
  
- **Uma licença de Audioconferência PSTN for atribuída a eles ou quando você alterar o provedor de audioconferência para a Microsoft.**
    
     Este email inclui o ID de conferência, o número de telefone de conferência padrão para as reuniões, os serviços de audioconferência PIN para o usuário e as instruções e link usar o Skype para negócios Online Meeting Update Tool que é usado para atualizar as reuniões existentes para o usuário. Consulte [Atribuir Skype para licenças de negócios e equipes da Microsoft](/SkypeForBusiness/skype-for-business-and-microsoft-teams-add-on-licensing/assign-skype-for-business-and-microsoft-teams-licenses) ou [Atribuir Microsoft como um provedor de serviços de audioconferência](/SkypeForBusiness/audio-conferencing-in-office-365/assign-microsoft-as-the-audio-conferencing-provider).
    
    > [!NOTE]
    > [!OBSERVAçãO] Se a sua organização estiver habilitada para IDs de conferência dinâmicas, todas as reuniões de um usuário agendadas terão IDs de conferência exclusivas. Você pode configurar as [IDs de conferência de áudio dinâmicos em sua organização](/skypeforbusiness/audio-conferencing-in-office-365/reset-a-conference-id-for-a-user). 
  
    Aqui está um exemplo desse e-mail:
    
     ![Verificar licença do Skype for Business](media/audio-conferencing-user-enabled.png)
  
    Você pode saber mais sobre as licenças em [Licenciamento de complementos do Skype for Business e do Microsoft Teams](/skypeforbusiness/skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing).
    
- **O ID de conferência ou número de telefone de conferência padrão de um usuário é alterado.**
    
    Esse email contém a ID de conferência, o número de conferência padrão, as instruções e links para usar a Ferramenta de atualização de reunião do Skype for Business Online usada para atualizar reuniões existentes do usuário. Mas este email não inclui serviços de audioconferência PIN do usuário. Consulte [Redefinir o ID de conferência de um usuário](reset-a-conference-id-for-a-user-in-teams.md).
  
    Aqui está um exemplo desse e-mail:
    
     ![As informações sobre conferência discada foram alteradas.](media/audio-conferencing-info-change.png)
  
- **O PIN de audioconferência de um usuário é redefinido.**
    
    Este email contém serviços de audioconferência do organizador PIN, o ID de conferência existente e número de telefone de conferência padrão para o usuário. Consulte [Redefinir o PIN de conferência de áudio](reset-the-audio-conferencing-pin-in-teams.md).
    
  
    Aqui está um exemplo desse e-mail:
    
     ![O PIN de conferência discada foi alterado.](media/audio-conferencing-pin-has-changed.png)
  
- **A licença do usuário for removida ou quando o provedor de audioconferência é alterado da Microsoft para outro provedor ou Nenhum.**
    
    Isso acontece quando a licença de **Conferência de áudio** é removida de um usuário ou quando a alteração do provedor de serviços de audioconferência de um usuário da Microsoft a um provedor de serviços de audioconferência de terceiros ou ao configurar o provedor como **Nenhum**. Este email contém as instruções e informações para o usuário usar o Skype para ferramenta de atualização de Reunião Online comercial para remover informações específicas de conferência de áudio, como o padrão ID de conferência telefônica número ou conferência.
    
    Consulte [Atribuir ou remover licenças do Office 365 for business](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc).
    
    Aqui está um exemplo desse e-mail:
    
     ![A conferência discada está desativada.](media/audio-conferencing-turned-off.png)
  
> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="make-changes-to-the-email-messages-that-are-sent-to-them"></a>Alterar as mensagens de e-mail enviadas a eles

Você pode fazer alterações para email que será enviado automaticamente aos usuários, incluindo o endereço de email e o nome de exibição que está incluído nas informações de contato *do* . Por padrão, o remetente dos e-mails será do Office 365, mas você pode alterar o endereço de email e usando o Windows PowerShell de nome de exibição. Consulte a [referência do PowerShell de equipes da Microsoft](https://docs.microsoft.com/powershell/module/teams/?view=teams-ps) para obter mais informações.
  
## <a name="what-if-you-dont-want-email-to-be-sent-to-them"></a>E se você não quiser que eles recebam e-mails?

Ao desativar o envio de emails para os usuários, o email não será enviado mesmo quando o usuário receber uma licença. Neste caso, o ID de conferência, padrão o número de telefone de conferência e, mais importante, o seu PIN de conferência de áudio não será enviada ao usuário. Quando isso acontecer, você deve informar ao usuário, enviando um email separado ou ligando para eles.
  
Seus usuários receberão e-mails por padrão, mas, se você deseja evitar que eles recebam e-mails sobre audioconferência, você pode usar o Microsoft Teams ou o Windows PowerShell. 

![teams-logo-30x30.png](media/teams-logo-30x30.png) **Usar o centro de administração do Microsoft Teams e do Skype para Business:**

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
