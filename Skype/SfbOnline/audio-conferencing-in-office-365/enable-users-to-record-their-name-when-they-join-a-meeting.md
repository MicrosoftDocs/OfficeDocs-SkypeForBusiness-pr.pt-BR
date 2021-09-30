---
title: Permitir que os usuários gravem seu nome quando ingressarem em uma reunião no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 1d649328-ada7-422d-a074-d6da4da36970
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
audience: Admin
appliesto:
- Skype for Business
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.custom:
- Audio Conferencing
description: Saiba como habilitar ou desabilitar se os usuários podem gravar seus nomes quando ingressarem em uma reunião no Skype for Business Online.
ms.openlocfilehash: 6f1c6c5d582665f411eaa17b76e7c1922ee9e468
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012945"
---
# <a name="enable-users-to-record-their-name-when-they-join-a-meeting-in-skype-for-business-online"></a>Permitir que os usuários gravem seu nome quando ingressarem em uma reunião no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Se você quiser permitir que os usuários registrem seus nomes no Teams, consulte [Permitir que os usuários registrem seus nomes quando ingressam em uma reunião no Microsoft Teams](/MicrosoftTeams/enable-users-to-record-their-name-when-they-join-a-meeting-in-teams).

Ao configurar a Audioconferência em Microsoft 365 ou Office 365, você receberá números de telefone e o que é chamado de ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone.
  
A ponte de conferência atende uma chamada feita por um usuário que discou para uma reunião utilizando um telefone. A ponte de conferência atende o chamador com prompts de voz de um atendedor automático e, dependendo de suas configurações, pode reproduzir notificações, solicitar que os chamadores gravem seus nomes e configurar a segurança de PIN para organizadores da reunião. Os PINs são dados aos organizadores da reunião para permitir que eles iniciem uma reunião. Entretanto, você pode configurar a reunião sem a necessidade de um PIN para começar.

## <a name="set-whether-callers-should-record-their-name"></a>Definir se os chamadores devem gravar o nome
    
1. No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Configurações** de ponte da Microsoft de audioconferência.  >  
    
2. Em **Experiência de participação da reunião**, veja a caixa de seleção **Habilitar a ativação de notificações de entrada e saída na reunião**.
    
   - **Selected** Os chamadores serão solicitados a gravar seu nome antes de entrarem na reunião. Esta opção é selecionada por padrão.
    
   - **Desapurado** Os chamadores não serão solicitados a gravar seus nomes antes de entrarem na reunião.
    
3. Depois de fazer suas alterações, clique em **Salvar**.
    
> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).
    
- Windows PowerShell se trata de gerenciar usuários e o que os usuários têm permissão para fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que é suportado apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em Baixar e instalar o módulo [Teams PowerShell](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md).
  
## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
