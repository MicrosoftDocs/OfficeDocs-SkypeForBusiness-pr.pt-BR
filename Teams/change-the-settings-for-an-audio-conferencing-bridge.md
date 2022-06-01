---
title: Alterar as configurações de uma ponte de audioconferência
ms.author: heidip
author: MicrosoftHeidi
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
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Audio Conferencing
- ms.teamsadmincenter.audioconferencing.bridgesettings
- seo-marvel-mar2020
description: Altere as configurações da ponte de audioconferência, incluindo notificações de entrada e saída, nomes de reprodução ou números de telefone, tons e solicita que os chamadores registrem seu nome.
ms.openlocfilehash: 48925c30d9ac42c76b6f00d8416d767c6e0ab14d
ms.sourcegitcommit: 2b1290b763c73f64c84c7568b16962e4ae48acf6
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/01/2022
ms.locfileid: "65823037"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Alterar as configurações de uma ponte de audioconferência

Ao configurar o Audioconferência no Microsoft 365 ou Office 365, você receberá números de telefone para os usuários do que é chamado de ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone. Esses números de telefone são usados quando os chamadores discam para uma reunião. O número de telefone está incluído na parte inferior do Skype for Business ou Microsoft Teams de reunião.
  
A ponte de conferência atende uma chamada e solicita ao chamador prompts de voz usando um atendedor automático de reunião e, dependendo de suas configurações, ele pode reproduzir notificações, solicitar que os chamadores registrem seu nome e controlar as configurações de PIN. Os PINs são fornecidos aos organizadores da reunião para permitir que eles iniciem uma reunião quando não estiverem usando um aplicativo Skype for Business Microsoft Teams aplicativo.

  > [!IMPORTANT]
  > Um PIN só é necessário para o organizador da reunião quando um Skype for Business ou Microsoft Teams usuário do aplicativo ainda não iniciou a reunião. Se todos estão discando para a reunião, o PIN é necessário para o organizador da reunião iniciar a reunião.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. No painel de navegação esquerdo, vá para pontes **de Conferência** > **de Reuniões**.

2. Na parte superior da página **Pontes de** Conferência, clique em **Configurações de ponte**.

3. No painel **Configurações do** Bridge, selecione:
   - **Notificações de entrada e saída da reunião** Se você desativar isso, os usuários que já ingressaram na reunião não serão notificados quando alguém entrar ou sair da reunião.

     Ao ativar as **notificações de entrada e saída da Reunião**, você pode selecionar estas opções:

   - **Nomes ou números de telefone** Quando os usuários discam para uma reunião, seu número de telefone será reproduzido quando ingressarem nela.

   - **Tons** Quando os usuários discam para uma reunião, um tom de áudio será reproduzido quando eles ingressarem nela.

   - **Peça aos chamadores para gravarem seu nome antes de ingressar na reunião** Se você desativar isso, os chamadores não serão solicitados a gravar seu nome antes de ingressarem em uma reunião.

4. Para definir o tamanho do PIN para reuniões, selecione o número de dígitos desejados para o PIN na lista **de comprimento do PIN** .

5. Para especificar se deseja enviar emails aos usuários, habilite ou desabilite o envio automático de emails aos usuários se a configuração **de audioconferência for alterada**.
    Consulte Emails enviados automaticamente aos usuários quando [suas configurações](emails-sent-to-users-when-their-settings-change-in-teams.md) de Audioconferência forem alteradas no Microsoft Teams ou emails enviados aos usuários quando suas configurações forem [alteradas no Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obter mais informações.

6. Clique em **Salvar**.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar esse processo, você pode usar o cmdlet [Set-CsDialinConferencingBridge](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge) .

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a serem executadas. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em vez de usar apenas o Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](/skypeforbusiness/set-up-your-computer-for-windows-powershell/download-and-install-windows-powershell-5-1).
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurar o Audioconferência para o Skype for Business Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
