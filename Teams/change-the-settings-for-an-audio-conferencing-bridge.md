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
description: Altere as configurações da ponte de audioconferência, incluindo notificações de entrada e saída, reproduza nomes ou números de telefone, tons e chamadores de prompt para registrar seu nome.
ms.openlocfilehash: 804bea41639ecbcd0db289f6df004d71e5faa820
ms.sourcegitcommit: 8f999bd2e20f177c6c6d8b174ededbff43ff5076
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 01/15/2022
ms.locfileid: "62055911"
---
# <a name="change-the-settings-for-an-audio-conferencing-bridge"></a>Alterar as configurações de uma ponte de audioconferência

Ao configurar a Audioconferência no Microsoft 365 ou Office 365, você receberá números de telefone para seus usuários do que é chamado de ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone. Esses números de telefone são usados quando os chamadores discam para uma reunião. O número de telefone está incluído na parte inferior do Skype for Business ou Microsoft Teams de reunião.
  
A ponte de conferência atende a uma chamada e solicita ao chamador prompts de voz usando um atendedor automático de reunião e, dependendo das configurações, pode reproduzir notificações, pedir que os chamadores gravem seus nomes e controlem as configurações de PIN. Os PINs são dados aos organizadores da reunião para permitir que eles iniciem uma reunião quando não estão usando um aplicativo Skype for Business ou Microsoft Teams.

  > [!IMPORTANT]
  > Um PIN só é necessário para o organizador da reunião quando um usuário Skype for Business ou Microsoft Teams aplicativo ainda não iniciou a reunião. Se todos estão discando para a reunião, o PIN será necessário para que o organizador da reunião inicie a reunião.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](includes/updating-admin-interfaces.md)]

## <a name="using-the-microsoft-teams-admin-center"></a>Usando o centro de administração do Microsoft Teams

1. Na navegação à esquerda, vá para   >  **Pontes de Conferência de Reuniões.**

2. Na parte superior da página **Pontes de** Conferência, clique em **Configurações de ponte.**

3. No painel **Configurações de** ponte, selecione:
   - **Notificações de entrada e saída de reunião** Se você desativar isso, os usuários que já ingressaram na reunião não serão notificados quando alguém entrar ou sair da reunião.

     Ao ativar as notificações de entrada e saída **de reunião,** você pode selecionar estas opções:

   - **Nomes ou números de telefone** Quando os usuários discam para uma reunião, seu número de telefone será tocado quando eles ingressarem.

   - **Tons** Quando os usuários discam para uma reunião, um tom de áudio será tocado quando eles ingressarem.

   - **Peça que os chamadores gravem seu nome antes de ingressar na reunião** Se você desativar isso, os chamadores não serão solicitados a gravar seus nomes antes de ingressarem em uma reunião.

4. Para definir o tamanho do PIN para reuniões, selecione o número de dígitos que você deseja para o PIN na lista de comprimento **do PIN.**

5. Para especificar se deve enviar emails para seus usuários, habilitar ou desabilitar Enviar emails automaticamente para os usuários se a configuração **de audioconferência** mudar.
    Consulte [Emails enviados automaticamente](emails-sent-to-users-when-their-settings-change-in-teams.md) aos usuários quando suas configurações de Audioconferência mudarem no Microsoft Teams ou Emails enviados aos usuários quando suas configurações mudarem no [Skype for Business Online](/SkypeForBusiness/audio-conferencing-in-office-365/emails-sent-to-users-when-their-settings-change) para obter mais informações.

6. Clique em **Salvar**.

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar esse processo, você pode usar o cmdlet [Set-CsDialinConferencingBridge.](/powershell/module/skype/Set-CsOnlineDialInConferencingBridge)

- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:

  - [Por que você precisa usar o PowerShell do Office 365](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)

  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))

- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:

  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](/SkypeForBusiness/set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell)

    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="related-topics"></a>Tópicos relacionados

[Configurar Audioconferência no Microsoft Teams](set-up-audio-conferencing-in-teams.md)

[Configurar Audioconferência para Skype for Business Online](/skypeforbusiness/audio-conferencing-in-office-365/set-up-audio-conferencing)
