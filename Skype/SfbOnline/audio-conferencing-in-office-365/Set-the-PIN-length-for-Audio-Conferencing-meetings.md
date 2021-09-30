---
title: Definir o comprimento do PIN para reuniões de Audioconferência no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
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
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: a9a7ec819fef23aac0ff334aebae95a83180316c
ms.sourcegitcommit: efd56988b22189dface73c156f6f8738f273fa61
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/30/2021
ms.locfileid: "60012895"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>Definir o comprimento do PIN para reuniões de Audioconferência no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]


> [!NOTE]
> Para obter informações sobre como definir o comprimento do PIN Microsoft Teams, consulte Definir o comprimento do PIN para reuniões de [Audioconferência em Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).

Ao configurar a audioconferência para Skype for Business, você receberá uma ponte de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone. O número de telefone definido será incluído nos convites de reunião para o Skype for Business app.
  
A ponte de audioconferência atende uma chamada feita por um usuário que discou para a reunião utilizando um telefone. Ele atende o chamador com prompts de voz de um atendedor automático e, dependendo de suas configurações, pode reproduzir notificações e pedir que os chamadores gravem seu nome. **As configurações** de ponte da Microsoft permitem alterar as configurações para notificações de reunião e a experiência de junção de reunião e definir o tamanho dos PINs usados pelos organizadores da reunião. Os organizadores da reunião usam PINs para iniciar reuniões se não puderem ingressar na reunião usando o Skype for Business app.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Configurar o tamanho do PIN
 
1. No centro **Skype for Business de** administração , na navegação à esquerda, vá para **Configurações** de ponte da Microsoft de audioconferência.  >  
    
2. Em **Comprimento do** PIN de  >  **segurança,** selecione o número de dígitos que você deseja para o PIN e clique em **Salvar**.
    
> [!NOTE]
> [!OBSERVAçãO] Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião. 

## <a name="want-to-know-more-about-pin-settings"></a>Deseja saber mais sobre configurações de PIN?

- PiNs podem ter de 4 a 12 dígitos; o padrão é 5. Somente números são usados para criar PINs. Letras e caracteres especiais não são usados.
    
- Um PIN só é necessário para o organizador da reunião quando um Skype for Business usuário ainda não iniciou a reunião. Se todos entrarem na reunião com discagem, o PIN é necessário para o organizador começar a reunião.
    
- As configurações de segurança do PIN são aplicadas a todos os números de telefone associados a uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a determinada ponte. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](/powershell/module/skype/Set-CsOnlineDialInConferencingTenantSettings).
    
- Para definir o número de dígitos do PIN como 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com Windows PowerShell, você pode gerenciar Microsoft 365 ou Office 365 usando um único ponto de administração que pode simplificar seu trabalho diário quando você tem várias tarefas a fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre o uso apenas do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configurações para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Como usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    [Como usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que é suportado apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em Baixar e instalar o módulo [Teams PowerShell](../set-up-your-computer-for-windows-powershell/download-and-install-the-skype-for-business-online-connector.md).
  
## <a name="see-also"></a>Confira também

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
