---
title: Definir os números de telefone incluídos nos convites no Skype for Business Online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
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
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 7136a8108a5ecd9e55d2def1e4cedd1076b270ff
ms.sourcegitcommit: 15e90083c47eb5bcb03ca80c2e83feffe67646f2
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/30/2021
ms.locfileid: "58729050"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Definir os números de telefone incluídos nos convites no Skype for Business Online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

> [!Note]
> Para obter informações sobre os números de telefone incluídos nos convites no Microsoft Teams, consulte [Definir os números de telefone incluídos nos convites no Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).

A audioconferência em Microsoft 365 ou Office 365 permite que os usuários em sua organização criem reuniões Skype for Business e, em seguida, permitam que os usuários discem para essas reuniões usando um telefone. Em Microsoft 365 e Office 365, você tem a opção de usar uma ponte de audioconferência da Microsoft ou uma ponte de audioconferência de terceiros hospedada por um provedor de audioconferência aprovado (ACP).
  
> [!NOTE]
> Não há um recurso que contenha uma lista de todos os números de discagem para Audioconferência. Se você estiver procurando ver se há números de telefone discados disponíveis em sua área ou país/região, use o centro de administração do **Skype for Business** Voz Telefone  >    >  **Números**, clique em **Adicionar** novos números de **serviço**. Use as listas de **País/região**, **Estado/região** e **Cidade** para filtrar sua busca. Além disso, se você estiver procurando por números de serviço gratuitos, selecione **Números gratuitos** da lista **Estado/região**.
  
Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização. Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.
  
> [!NOTE]
> Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Definir o número de telefone padrão para o organizador da reunião

1. Entre com sua conta de trabalho ou de estudante.
    
2. Escolha **Centros de administração** > **Skype for Business**.
    
3. Escolha **Usuários**.
    
    ![Mostra a seleção de usuários no Skype for Business de administração.](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Escolha os usuários que você deseja editar:
    
   - Para selecionar um único usuário, selecione o nome do usuário.
    
   - Para selecionar todos os usuários na página, marque a caixa ao lado do **Nome de exibição** na parte superior da lista.
    
   - Para selecionar vários usuários, marque a caixa ao lado do nome de cada usuário.
    
5. No painel direito, escolha **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Escolha **Audioconferência**.
    
7. Na página **Propriedades** , na lista **Nome do provedor** , escolha o provedor para o usuário. Dependendo do provedor, preencha as seguintes caixas.
    
   - **A Microsoft é o provedor**: Use as listas **Número de chamada tarifada padrão** e **Número de chamada gratuita padrão** para selecionar os números padrão para o usuário.
    
     > [!NOTE]
     > Pelo menos um número de chamada gratuita deve ser atribuído à sua ponte de conferência antes que ela possa ser definida como o número de chamada gratuita padrão de um usuário. Para obter um número de chamada gratuita, consulte Obter números de telefone [de serviço para](/microsoftteams/getting-service-phone-numbers)Skype for Business . 
  
   - **Um terceiro é o provedor**: Use os campos de **Número de chamada tarifada** e **Número de chamada gratuita** para inserir os números para o usuário.


## <a name="reset-audio-conferencing-phone-numbers"></a>Redefinir os números de telefone de conferência de áudio

1. No centro **Skype for Business de administração,** escolha **Audioconferência**.
    
2. Na parte superior da página, escolha **Usuários**.
    
3. Escolha os usuários que você deseja redefinir e, em seguida, no painel de Ações, clique em **Limpar**.
    
Por padrão, quando você altera as configurações de conferência de um usuário, um email é enviado ao usuário. Para alterar isso, consulte [Enable or disable sending emails when Audio Conferencing settings change](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Quando você altera as configurações de audioconferência de um usuário, as reuniões recorrentes e futuras do Skype for Business devem ser atualizadas e enviadas aos participantes. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser).
    
- Use o cmdlet [Set-CsOnlineDialInConferencingUser](/powershell/module/skype/Set-CsOnlineDialInConferencingUser) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.
    
    Para mudar o número de chamada gratuita padrão de um usuário, execute:
    
  ```PowerShell
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.
    
    > [!NOTE]
    > Para encontrar o BridgeID, use o cmdlet **Get-CsOnlineDialInConferencingBridge.**
  
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Para definir o número de gratuito padrão para todos os usuários sem um como +18005551234, execute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Para alterar o número de gratuito padrão de todos os usuários que têm +18005551234 como seu número de gratuito padrão para +18005551239, execute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para definir o número padrão de gratuitos de todos os usuários localizados nos EUA como +18005551234, execute:
    
  ```PowerShell
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
  ## <a name="want-to-learn-more-about-windows-powershell"></a>Quer saber mais sobre Windows PowerShell?
- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Por que você precisa usar Microsoft 365 ou Office 365 PowerShell](/microsoft-365/enterprise/why-you-need-to-use-microsoft-365-powershell)
    
- Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade sobre apenas o uso do Centro de administração do Microsoft 365, como quando você está fazendo alterações de configuração para muitos usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar Microsoft 365 ou Office 365 com Windows PowerShell](/previous-versions//dn568025(v=technet.10))
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](../set-up-your-computer-for-windows-powershell/set-up-your-computer-for-windows-powershell.md)
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimente ou compre Audioconferência em Microsoft 365 ou Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
