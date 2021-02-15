---
title: Alterar as configurações de uma ponte de audioconferência
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 783fad3f-b77c-422b-b91f-7c8b0af324fb
ms.tgt.pltfrm: cloud
ms.service: msteams
search.appverid: MET150
ms.collection:
- M365-voice
- M365-collaboration
audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Altere as configurações da ponte de audioconferência, incluindo notificações de entrada e saída, reproduzir nomes ou números de telefone, tons e solicitar que os chamadores gravem seu nome.
ms.openlocfilehash: 9694ac0cddecc5b00c0df133c5c494e4b5bc0d17
ms.sourcegitcommit: 212b2985591ca1109eb3643fbb49d8b18ab07a70
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/21/2021
ms.locfileid: "49918697"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Alterar as configurações de uma ponte de audioconferência

Quando você estiver configurando a Audioconferência no Microsoft 365 ou no Office 365, receberá números de telefone para os usuários da chamada ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone. Esses números de telefone são usados quando os chamadores discam para uma reunião. O número de telefone está incluído na parte inferior do convite de reunião do Skype for Business ou do Microsoft Teams.
  
A ponte de conferência atende uma chamada e solicita que o chamador use um atendedor automático de reunião e, dependendo das configurações, pode reproduzir notificações, pedir que os chamadores gravem seu nome e controlar as configurações de PIN. Os PINs são dados aos organizadores da reunião para permitir que eles iniciem uma reunião quando não estão usando um aplicativo do Skype for Business ou do Microsoft Teams.

  > [!IMPORTANT]
  > Um PIN só é necessário para o organizador da reunião quando um usuário do aplicativo Skype for Business ou do Microsoft Teams ainda não iniciou a reunião. Se todos discam para a reunião, o PIN é necessário para que o organizador da reunião inicie a reunião. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="an-icon-showing-the-microsoft-teams-logo-using-the-microsoft-teams-admin-center"></a>![Um ícone mostrando o logotipo do Microsoft Teams](media/teams-logo-30x30.png) Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, vá para  >  **pontes de Conferência de Reuniões.** 

2. Na parte superior da página **Pontes de** conferência, clique em **Configurações da ponte.** 

3. No painel **de configurações da** Ponte, selecione: 
   - **Notificações de entrada e saída da reunião** Se você desativar isso, os usuários que já ingressaram na reunião não serão notificados quando alguém entrar ou sair da reunião.
    
     Ao ativar as notificações de entrada e saída **da Reunião,** você pode selecionar estas opções:
    
   - **Nomes ou números de telefone** Quando os usuários discam para uma reunião, seu número de telefone será tocado quando eles ingressarem.
    
   - **Tons** Quando os usuários discam para uma reunião, um tom de áudio será tocado quando eles ingressarem.
      
   - **Peça aos chamadores para gravarem o nome antes de ingressar na reunião** Se você desativar isso, os chamadores não serão solicitados a gravar o nome antes de ingressar em uma reunião.

4. Para definir o tamanho do PIN para reuniões, selecione o número de dígitos que você deseja para o PIN na lista **de tamanhos de PIN.**

5. Para especificar se você deve enviar emails para seus usuários, habilitar ou desabilitar o envio automático de emails para os usuários se a configuração **da audioconferência mudar.**
    Veja [emails enviados automaticamente](emails-sent-to-users-when-their-settings-change-in-teams.md) aos usuários quando suas configurações de Audioconferência mudarem no Microsoft Teams ou emails enviados aos usuários quando suas configurações mudarem [no Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obter mais informações.
 
6. Clique em **Salvar**. 

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar esse processo, você pode usar o cmdlet [Set-CsDialinConferencingBridge.](https://go.microsoft.com/fwlink/?LinkId=617686)
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Microsoft 365 ou o Office 365 usando um ponto único de administração que pode simplificar seu trabalho diário quando você tiver várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Microsoft 365 ou o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação ao uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurar a audioconferência para o Skype for Business Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
