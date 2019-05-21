---
title: Definir o comprimento do PIN para reuniões de conferência de áudio no Skype for Business Online
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
localization_priority: Normal
f1keywords: None
ms.custom:
- Audio Conferencing
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 95bc1c69e59e125d451a68eeee23ea15febd420f
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 05/20/2019
ms.locfileid: "34283806"
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings-in-skype-for-business-online"></a>Definir o comprimento do PIN para reuniões de conferência de áudio no Skype for Business Online


> [!NOTE]
> Para obter informações sobre como definir o comprimento do PIN no Microsoft Teams, consulte [definir o comprimento do PIN para reuniões de conferência de áudio no Microsoft Teams](/en-us/MicrosoftTeams/Set-the-PIN-length-for-Audio-Conferencing-meetings-in-teams).

Ao configurar a conferência de áudio para o Skype for Business, você receberá uma ponte de áudio de audioconferência. Uma ponte de conferência pode conter um ou mais números de telefone. O número de telefone que você define será incluído nos convites de reunião do aplicativo Skype for Business.
  
A ponte de audioconferência atende a uma chamada para as pessoas que estão discando para uma reunião usando um telefone. Ele responde ao chamador com prompts de voz de um atendedor automático e, em seguida, dependendo das suas configurações, pode reproduzir notificações e pedir para os chamadores gravarem o nome. **As configurações de ponte da Microsoft** permitem que você altere as configurações de notificações de reunião e da experiência de junção de reunião e defina o comprimento dos Pins que são usados pelos organizadores da reunião. Os organizadores da reunião usam PINs para iniciar reuniões se não puderem ingressar na reunião usando o aplicativo Skype for Business.

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="setting-the-pin-length"></a>Configurar o tamanho do PIN
 
1. No **centro de administração do Skype for Business**, no painel de navegação à esquerda, vá para **conferência** > de áudio**configurações da ponte da Microsoft**.
    
2. Em **** > **tamanho do pino**de segurança, selecione o número de dígitos que você deseja para o PIN e clique em **salvar**.
    
> [!NOTE]
> [!OBSERVAçãO] Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião. 

## <a name="want-to-know-more-about-pin-settings"></a>Quer saber mais sobre as configurações de PIN?

- Os pinos podem ter de 4 a 12 dígitos; o padrão é 5. Somente números são usados para criar PINs. Letras e caracteres especiais não são usados.
    
- Um PIN só é necessário para o organizador da reunião quando um usuário do Skype for Business ainda não iniciou a reunião. Se todos entrarem na reunião com discagem, o PIN é necessário para o organizador começar a reunião.
    
- As configurações de segurança do PIN são aplicadas a todos os números de telefone associados a uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a determinada ponte. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
- Para definir o número de dígitos do PIN como 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o centro de administração do Office 365, como quando você está realizando alterações de configurações para muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="see-also"></a>Confira também

[Experimentar ou comprar audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
