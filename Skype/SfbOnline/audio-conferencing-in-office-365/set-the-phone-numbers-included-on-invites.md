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
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Veja as etapas para criar um número de telefone padrão para que os autores de chamadas participem de uma reunião do Skype for Business Online. '
ms.openlocfilehash: d4ab76fc99483812d2be6b2f7009be361f33c3c9
ms.sourcegitcommit: 2a6e499165424fe2d189ad140951e222c8ba9c81
ms.translationtype: HT
ms.contentlocale: pt-BR
ms.lasthandoff: 09/07/2018
ms.locfileid: "23851481"
---
# <a name="set-the-phone-numbers-included-on-invites-in-skype-for-business-online"></a>Definir os números de telefone incluídos nos convites no Skype for Business Online

> [!Note]
> Para obter informações sobre os números de telefone incluídos nos convites no Microsoft Teams, consulte [Definir os números de telefone incluídos nos convites no Microsoft Teams](/MicrosoftTeams/set-the-phone-numbers-included-on-invites-in-teams).

Os serviços de audioconferência no Office 365 permitem que os usuários em sua organização criem reuniões no Skype for Business e, em seguida, permite que os usuários disquem para essas reuniões usando um telefone. No Office 365, você tem a opção de usar uma ponte de audioconferência da Microsoft ou uma ponte de audioconferência de terceiros hospedada por um provedor de serviços de audioconferência (ACP).
  
> [!NOTE]
> Não há um recurso com uma listagem de todos os números de discagem para a Audioconferência. Para descobrir se há números de telefone disponíveis em sua área ou em seu país/região, acesse o **centro de administração do Skype for Business** > **Voz** > **Números de Telefone**, clique em **Adicionar** e em **Novos Números de Serviço**. Use as listas de **País/região**, **Estado/região** e **Cidade** para filtrar sua busca. Além disso, se você estiver procurando por números de serviço gratuitos, selecione **Números gratuitos** da lista **Estado/região**.
  
Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização. Todos eles podem ser usados para participar das reuniões que um organizador da reunião criou, mas você pode selecionar quais serão incluídos nos convites da reunião.
  
> [!NOTE]
> Pode haver no máximo um número de telefone tarifado e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também há um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone que podem ser usados para ingressar em uma reunião. 

> [!NOTE]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Definir o número de telefone padrão para o organizador da reunião

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Escolha **Centros de administração** > **Skype for Business**.
    
3. Escolha **Usuários**.
    
    ![Mostra os usuários que podem ser selecionados no centro de administração do Skype for Business](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Escolha os usuários que você deseja editar:
    
  - Para selecionar um único usuário, selecione o nome do usuário.
    
  - Para selecionar todos os usuários na página, marque a caixa ao lado do **Nome de exibição** na parte superior da lista.
    
  - Para selecionar vários usuários, marque a caixa ao lado do nome de cada usuário.
    
5. No painel à direita, escolha **Editar**.
    
    ![Escolha o ícone de edição.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Escolha **Audioconferência**.
    
7. Na página **Propriedades** , na lista **Nome do provedor** , escolha o provedor para o usuário. Dependendo do provedor, preencha as seguintes caixas.
    
  - **A Microsoft é o provedor**: Use as listas **Número de chamada tarifada padrão** e **Número de chamada gratuita padrão** para selecionar os números padrão para o usuário.
    
    > [!NOTE]
    > Pelo menos um número de chamada gratuita deve ser atribuído à sua ponte de conferência antes que ela possa ser definida como o número de chamada gratuita padrão de um usuário. Para obter um número gratuito, consulte [Obter números de telefone de serviço para o Skype for Business](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md). 
  
  - **Um terceiro é o provedor**: Use os campos de **Número de chamada tarifada** e **Número de chamada gratuita** para inserir os números para o usuário.


## <a name="reset-audio-conferencing-phone-numbers"></a>Redefinir os números de telefone de conferência de áudio

1. No **centro de administração do Skype for Business**, escolha **Audioconferência**.
    
2. Na parte superior da página, escolha **Usuários**.
    
3. Escolha os usuários que você deseja redefinir e, em seguida, no painel de Ações, clique em **Limpar**.
    
Por padrão, quando você altera as configurações de conferência de um usuário, um email é enviado ao usuário. Para alterar essa opção, consulte [Habilitar ou desabilitar o envio de emails ao alterar as configurações de Audioconferência](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Quando você altera as configurações de audioconferência de um usuário, as reuniões recorrentes e futuras do Skype for Business devem ser atualizadas e enviadas aos participantes. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).
    
- Use o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.
    
    Para mudar o número de chamada gratuita padrão de um usuário, execute:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base em seu número padrão original ou em sua localização.
    
    > [!NOTE]
    > Para saber qual é o BridgeID, use o cmdlet **Get-CsOnlineDialInConferencingBridge**.
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Para definir +18005551234 como número de chamada gratuita padrão de todos os usuários que não têm um número, execute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Para mudar o número de chamada gratuita padrão de todos os usuários que têm +18005551234 como seu número de chamada gratuita padrão para +18005551239, execute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para definir o número de chamada gratuita padrão de todos os usuários localizados nos EUA para +18005551234, execute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -Country US -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>
  ```
## <a name="want-to-learn-more-about-windows-powershell"></a>Quer saber mais sobre o Windows PowerShell?
- O Windows PowerShell serve para o gerenciamento de usuários e do que os usuários podem ou não podem fazer. Com o Windows PowerShell, você pode gerenciar o Office 365 e o Skype for Business Online usando um único ponto de administração, o que pode simplificar o seu trabalho diário quando tiver várias tarefas para fazer. Para começar a trabalhar com o Windows PowerShell, confira estes tópicos:
    
  - [Uma introdução ao Windows PowerShell e ao Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525039)
    
  - [Por que você precisa usar o PowerShell do Office 365](https://go.microsoft.com/fwlink/?LinkId=525041)
    
- O Windows PowerShell tem muitas vantagens em velocidade, simplicidade e produtividade em relação a usar somente o centro de administração do Office 365, como para fazer alterações de configuração para vários usuários ao mesmo tempo. Saiba mais sobre essas vantagens nos seguintes tópicos:
    
  - [Melhores maneiras de gerenciar o Office 365 com o Windows PowerShell](https://go.microsoft.com/fwlink/?LinkId=525142)
    
  - [Usar o Windows PowerShell para gerenciar o Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525453)
    
  - [Usando o Windows PowerShell para realizar tarefas comuns de gerenciamento do Skype for Business Online](https://go.microsoft.com/fwlink/?LinkId=525038)
    
## <a name="related-topics"></a>Tópicos relacionados

[Experimentar ou comprar a Audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
