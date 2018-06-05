---
title: Defina o telefone convidam números incluídos no
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.reviewer: oscarr
ms.topic: article
ms.assetid: 32954439-d365-4125-872f-b37466ecb035
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection:
- Adm_Skype4B_Online
- Strat_SB_PSTN
ms.audience: Admin
appliesto:
- Skype for Business
- Microsoft Teams
localization_priority: Priority
f1keywords: None
ms.custom:
- Audio Conferencing
description: 'Get the steps to create a default phone number for callers to join a Skype for Business Online meeting. '
ms.openlocfilehash: 5ddc20d1b9166315581a6f894c5d630d9e247881
ms.sourcegitcommit: a79668bb45b73a63bea5c249d76a4c4c2530a096
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/05/2018
ms.locfileid: "19568277"
---
# <a name="set-the-phone-numbers-included-on-invites"></a>Defina o telefone convidam números incluídos no

Serviços de audioconferência no Office 365 permite aos usuários em sua organização criar Skype para reuniões de negócios e Teams da Microsoft e, em seguida, permitir que os usuários discam para essas reuniões usando um telefone. No Office 365, você tem a opção de usar uma ponte de conferência de áudio da Microsoft ou uma ponte de conferência de áudio de terceiros que é hospedada por um provedor de serviços de audioconferência aprovada (ACP).
  
> [!NOTE]
> Não há um recurso com uma listagem de todos os números de discagem para a Audioconferência. Se você estiver procurando para ver se existem números de telefone de discagem disponíveis na sua área ou país/região, use o **Skype para centro de administração de negócios** > **voz** > **Números de telefone**, clique em **Adicionar** e em seguida **novos números de serviço **. Use as listas de **País/região**, estado/região do **** e **cidade** para filtrar search. > Além disso, se você estiver procurando por números de serviço gratuito tarifados, selecione **chamada gratuita** do estado/região **** lista.
  
Uma ponte de conferência oferece um conjunto de números de telefone de discagem para sua organização. Todos eles podem ser usados para ingressar as reuniões que criou um organizador de reunião, mas você pode selecionar quais serão incluídos em seus convites de reunião.
  
> [!NOTE]
> Pode haver um máximo de chamada um Tarifada e um número de telefone gratuitos no convite da reunião para um organizador de reunião, mas também existe um link localizado na parte inferior de cada convite de reunião que abre a lista completa de todos os números de telefone de discagem que podem ser usados para ingressar em uma reunião. 
  
## <a name="set-the-default-dial-in-phone-number-for-a-meeting-organizer"></a>Definir o número de telefone de discagem padrão para o organizador da reunião

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

    ![Mostra a seleção de usuários no Microsoft Teams e Skype para centro de administração do Business](../images/teamsselectusers.png)

2. Na parte superior da página, clique em **Editar**.

    ![Clique em Editar no Microsoft equipes e Skype para Business Admin Center](../images/teamsedituser.png)

3. Ao lado de **Conferência de áudio**, clique em **Editar**. 
    
    ![Clique em Editar ao lado de conferência de áudio](../images/teamseditaudioconf.png)

4. Use os campos de **número de Chamada Tarifada** ou **número de chamada gratuito** para inserir os números para o usuário.

> [!Note]
> [!INCLUDE [updating-admin-interfaces](../includes/updating-admin-interfaces.md)]

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

1. Entre no Office 365 com sua conta corporativa ou de estudante.
    
2. Escolha **Centros de administração** > **Skype for Business**.
    
3. Escolha **Usuários**.
    
    ![Mostra a seleção de usuários no Skype para centro de administração do Business](../images/abc9ce4e-2250-474d-b053-b3bea8162c77.png)
  
4. Escolha os usuários que você deseja editar:
    
  - Para selecionar um único usuário, selecione o nome do usuário.
    
  - Para selecionar todos os usuários na página, marque a caixa ao lado do **nome para exibição** na parte superior da lista.
    
  - Para selecionar vários usuários, marque a caixa ao lado do nome de cada usuário.
    
5. No painel direito, escolha **Editar**.
    
    ![Choose the edit icon.](../images/5dd7c5bc-b8fa-4201-b6a6-1436ad8f88fb.png)
  
6. Escolha a **conferência de áudio**.
    
7. Na página **Propriedades** , na lista **nome do provedor** , escolha o provedor para o usuário. Dependendo do provedor, preencha as seguintes caixas.
    
  - **A Microsoft tem o provedor**: Use o **número de Chamada Tarifada padrão** e **número de chamada gratuito padrão** lista para selecionar os números de padrão para o usuário.
    
    > [!NOTE]
    > Pelo menos um número de chamada gratuito deve ser atribuído à sua ponte de conferência antes que ela pode ser definida como o número de chamada gratuita do padrão de um usuário. Para obter um número de discagem gratuito, consulte [Getting números de telefone de serviço para Skype para equipes da Microsoft e de negócios](../what-is-phone-system-in-office-365/getting-service-phone-numbers.md). 
  
  - **Um terceiro é o provedor**: Use os campos de **número de Chamada Tarifada** e **número de chamada gratuito** para inserir os números para o usuário.


## <a name="change-the-audio-conferencing-phone-number-for-users"></a>Alterar o número de telefone de conferência de áudio para usuários

![as equipes de logotipo-30x30.png](../images/teams-logo-30x30.png) **usando as equipes da Microsoft e Skype para Business Admin Center**

1. No painel de navegação esquerdo, clique em **usuários**e, em seguida, selecione o usuário da lista de usuários disponíveis.

2. Na parte superior da página, clique em **Editar**.

3. Ao lado de **Conferência de áudio**, clique em **Editar**. 
    
4. Use os campos de **número de Chamada Tarifada** ou **número de chamada gratuito** para inserir os números para o usuário.

## <a name="reset-audio-conferencing-phone-numbers"></a>Redefinir os números de telefone de conferência de áudio

![logotipo-sfb-30x30.png](../images/sfb-logo-30x30.png) **usando o Skype para centro de administração de negócios**

1. No **Skype para centro de administração de negócios**, escolha a **conferência de áudio**.
    
2. Na parte superior da página, escolha **usuários**.
    
3. Escolha os usuários que você deseja redefinir e, em seguida, no painel de ações, clique em **Limpar**.
    
Por padrão, quando você altera as configurações de conferência de um usuário, um email é enviado ao usuário. Para alterar essa opção, consulte [Habilitar ou desabilitar o envio de emails ao alteram as configurações de conferência de áudio](enable-or-disable-sending-emails-when-their-settings-change.md).
  
> [!IMPORTANT]
> Quando você altera as configurações de conferência de áudio de um usuário, Skype recorrente e futura para reuniões de negócios e Teams da Microsoft deve ser atualizado e enviado aos participantes. 
  
## <a name="want-to-know-how-to-manage-with-windows-powershell"></a>Quer saber como gerenciar com o Windows PowerShell?

- Para economizar tempo ou automatizar o processo, você pode usar o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688).
    
- Use o cmdlet [Set-CsOnlineDialInConferencingUser](https://go.microsoft.com/fwlink/?LinkId=617688) para mudar o número de chamada tarifada ou gratuita padrão de usuários específicos.
    
    Para mudar o número de chamada gratuita padrão de um usuário, execute:
    
  ```
  Set-CsOnlineDialinConferencingUser -Identity amos.marble@Contoso.com -TollFreeServiceNumber   +180045551234
  ```

- Use o cmdlet **Set-CsOnlineDialInConferencingUserDefaultNumber** para mudar o número de chamada tarifada ou gratuita padrão de usuários com base no número padrão original ou no local.
    
    > [!NOTE]
    > Para localizar o BridgeID, use o cmdlet **Get-CsOnlineDialInConferencingBridge** .
  
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id> -RescheduleMeetings 
  ```

  - Para definir o número de chamada gratuita padrão para todos os usuários sem um para +18005551234, execute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber $null -ToNumber +18005551234 -NumberType TollFree -BridgeId <Bridge Id>  
  ```

  - Para alterar o número de chamada gratuita do padrão de todos os usuários que possuem +18005551234 como seu número de chamada gratuita padrão para +18005551239, execute:
    
  ```
  Set-CsOnlineDialInConferencingUserDefaultNumber -FromNumber +18005551234 -ToNumber +18005551239 NumberType TollFree -BridgeId <Bridge Id>
  ```

  - Para definir o número de chamada gratuita do padrão de todos os usuários localizados nos EUA para +18005551234, execute:
    
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

[Experimentar ou comprar a audioconferência no Office 365](../audio-conferencing-in-office-365/try-or-purchase-audio-conferencing-in-office-365.md)
