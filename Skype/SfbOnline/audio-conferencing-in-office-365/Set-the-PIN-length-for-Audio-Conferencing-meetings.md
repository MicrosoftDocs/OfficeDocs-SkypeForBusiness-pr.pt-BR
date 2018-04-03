---
title: Definir o tamanho PIN para reuniões de conferência de áudio
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.date: 01/22/2018
ms.topic: article
ms.assetid: b86d31c6-1543-478f-b8c6-4b71e708403a
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Normal
f1keywords: None
ms.custom:
- Strat_SB_PSTN
- Audio Conferencing
description: Learn the parameters for the length and requirements of a PIN and see how to set the length for meetings in Skype for Business.
ms.openlocfilehash: 442ec6f4395b71acaf3296bdd6ec6317451dc36f
ms.sourcegitcommit: 627d3108e3e2f232e911162d9d2db9558e8ead0c
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 04/03/2018
---
# <a name="set-the-pin-length-for-audio-conferencing-meetings"></a>Definir o tamanho PIN para reuniões de conferência de áudio

Quando você estiver configurando serviços de audioconferência para Skype para negócios ou Teams da Microsoft, você receberá uma ponte de conferência de áudio. Uma ponte de conferência pode conter um ou mais números de telefone. O número de telefone que você definir será incluído em convites de reunião para Skype para aplicativos de negócios e Teams da Microsoft.
  
A ponte de conferência de áudio atende uma chamada para pessoas que estão discando para uma reunião usando um telefone. Ela atende do chamador com prompts de voz de um atendedor automático e em seguida, dependendo de suas definições, pode reproduzir notificações e será feita aos chamadores a registrar seu nome. **Configurações de ponte da Microsoft** permitem que você alterar as configurações de notificações de reunião e experiência de ingresso na reunião e definir o tamanho dos pinos que são usados pelo organizadores de reunião. Organizadores de reunião usam PINs para iniciar reuniões, se eles não podem ingressar na reunião usando o Skype para aplicativos de negócios ou Teams da Microsoft.
  
## <a name="setting-the-pin-length"></a>Configurar o tamanho do PIN

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Vá para o **Centro de administração do Office 365** > **Skype for Business**.
    
3. No **Skype para centro de administração de negócios**, no painel de navegação esquerdo, vá para a **conferência de áudio** > **configurações de ponte da Microsoft**.
    
4. Em **segurança** > **comprimento do PIN**, selecione o número de dígitos que você deseja para o PIN e clique em **Salvar**.
    
> [!NOTE]
> [!OBSERVAçãO] Um PIN é diferente de um ID de conferência. IDs de conferência são usados pelos chamadores quando eles participam da reunião. São usados para identificar a reunião. O PIN é usado para autenticar um chamador como organizador da reunião. 
  
## <a name="want-to-know-more-about-pin-settings"></a>Quer saber mais sobre configurações de PIN?

- PINs podem ter entre 4 para 12 dígitos; o padrão é 5. Somente números são usados para criar PINs. Letras e caracteres especiais não são usados.
    
- Um PIN só é necessário para o organizador da reunião quando um Skype para usuário de negócios ou Microsoft Teams já não tiver iniciado a reunião. Se todos entrarem na reunião com discagem, o PIN é necessário para o organizador começar a reunião.
    
- As configurações de segurança do PIN são aplicadas a todos os números de telefone associados a uma ponte da Microsoft. Elas serão aplicadas a todas as reuniões que usam os números de telefone associados a determinada ponte. 
    
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingTenantSettings](https://go.microsoft.com/fwlink/?LinkId=715757).
    
- Para definir o número de dígitos do PIN como 8:  `Set-CsOnlineDialInConferencingTenantSettings -PinLength 8`
    
- O Windows PowerShell gerencia os usuários e o que eles podem ou não fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 usando um ponto único de administração para simplificar seu trabalho diário quando houver várias tarefas a serem feitas. Para começar a usar o Windows PowerShell, consulte estes tópicos:
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade apenas usando o Centro de administração do Office 365, como quando você estiver fazendo alterações nas configurações de muitos usuários de uma só vez. Saiba mais sobre essas vantagens nos seguintes tópicos: 
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Como usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
    [Como usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Uso do Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
    > [!NOTE]
    > [!OBSERVAçãO] O módulo Windows PowerShell para Skype for Business Online permite que você crie uma sessão remota do Windows PowerShell que se conecta ao Skype for Business Online. Esse módulo, que tem suporte apenas em computadores de 64 bits, pode ser baixado do Centro de Download da Microsoft em [Módulo Windows PowerShell para Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=294688).
  
## <a name="see-also"></a>Ver também

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
